---
title: EOP の ASF 設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のスパム対策ポリシーで使用できる高度なスパム フィルター (ASF) 設定について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0b6db02815f5b50d199e10685e2895a174997fd2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288683"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP の高度なスパム フィルター (ASF) 設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> スパム対策ポリシーで現在使用可能な ASF 設定は、廃止中です。 スパム対策ポリシーでは、これらの設定を使用することをお勧めします。 これらの ASF 設定の機能は、フィルタリング スタックの他の部分に組み込まれる中です。 詳細については [、「EOP スパム対策ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

すべての Microsoft 365 組織では、EOP のスパム対策ポリシーの高度なスパム フィルター (ASF) 設定により、管理者は特定のメッセージ プロパティに基づいてメッセージをスパムとしてマークできます。 ASF では、これらのプロパティはスパムで一般的に検出されるという理由から、特にこれらのプロパティを対象とします。 ASF の検出では、プロパティに応じて、メッセージがスパムまたは信頼度の高いスパム **としてマークされます**。

> [!NOTE]
> 1 つ以上の ASF 設定を有効にすることで、スパム フィルタリングに積極的に取り組む必要があります。 ASF によってフィルター処理されたメッセージを誤検知として報告できない。 ASF によってフィルター処理されたメッセージは、次の方法で識別できます。
>
> - エンドユーザーのスパム検疫通知を定期的に実行します。
>
> - 検疫内にフィルター処理されたメッセージが存在する。
>
> - この記事 `X-CustomSpam:` で説明するようにメッセージに追加される特定の X ヘッダー フィールド。

以下のセクションでは、セキュリティ & コンプライアンス センターのスパム対策ポリシー、および Exchange Online PowerShell またはスタンドアロンの EOP PowerShell ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) および [Set-HostedContentFilterPolicy)](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)で使用可能な ASF 設定とオプションについて説明します。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="enable-disable-or-test-asf-settings"></a>ASF 設定を有効、無効、またはテストする

ASF 設定ごとに、スパム対策ポリシーで次のオプションを使用できます。

- **On**: ASF は、対応する X-Header フィールドをメッセージに追加し、メッセージをスパム (SCL [](#increase-spam-score-settings)5 または 6 (スパム スコア設定の向上 [](#mark-as-spam-settings)用) または信頼度の高いスパム **(スパム** としてマークの設定の SCL 9) としてマークします。 

- **オフ**: ASF 設定は無効です。 これは既定値であり、変更を行うのはお勧めしません。

- **Test**: ASF は、対応する X-Header フィールドをメッセージに追加します。 メッセージに対する処理は、テスト モード **オプション** (*TestModeAction*) の値によって決まります。

  - **なし**: メッセージ配信は ASF 検出の影響を受けません。 メッセージは、引き続き EOP の他の種類のフィルター処理とルールの対象です。

  - **既定の X ヘッダー テキスト (*AddXHeader*)** を追加する : X ヘッダー値 `X-CustomSpam: This message was filtered by the custom spam filter option` がメッセージに追加されます。 受信トレイ ルールまたはメール フロー ルール (トランスポート ルールとも呼ばれる) でこの値を使用して、メッセージの配信に影響を与える可能性があります。

  - **Bcc メッセージの送信 (*BccMessage*)**: 指定された電子メール アドレス *(PowerShell の TestModeBccToRecipients* パラメーター値) がメッセージの BCC フィールドに追加され、メッセージは追加の BCC 受信者に配信されます。 セキュリティ/コンプライアンス センター&、複数の電子メール アドレスをセミコロン (;)。 PowerShell では、複数の電子メール アドレスをコンマで区切ります。

  **注**:

  - テスト モードは、次の ASF 設定では使用できません。

    - **条件付き送信者 ID フィルター: hard fail** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR バックスカター**(*MarkAsSpamNdrBackscatter*)
    - **SPF レコード: hard fail** (*MarkAsSpamSpfRecordHardFail*)

  - 同じテスト モードアクションが、Test に設定 *されている* ASF 設定すべてに適用 **されます**。 ASF 設定ごとに異なるテスト モードアクションを構成できません。

## <a name="increase-spam-score-settings"></a>スパム スコアの設定を増やす

次の ASF 設定では、検出されたメッセージの Spam Confidence Level (SCL) を 5または 6 に設定します。これは、スパム フィルターの判断と、スパム対策ポリシー内の対応するアクションに対応します。

****

|スパム対策ポリシー設定|説明|追加された X ヘッダー|
|---|---|---|
|**リモート サイトへのイメージ リンク** <p> *IncreaseScoreWithImageLinks*|リモート サイトへの HTML タグ リンクを含むメッセージ `<Img>` (たとえば、http を使用) はスパムとしてマークされます。|`X-CustomSpam: Image links to remote sites`|
|**別のポートに対する URL リダイレクト** <p> *IncreaseScoreWithRedirectToOtherPort*|80 (HTTP)、8080 (代替 HTTP)、または 443 (HTTPS) 以外の TCP ポートにリダイレクトするハイパーリンクを含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL redirect to other port`|
|**URL 内の数値 IP アドレス** <p> *IncreaseScoreWithNumericIps*|数値ベースの URL (通常は IP アドレス) を含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: Numeric IP in URL`|
|**.biz Web サイトまたは .info Web サイトへの URL** <p> *IncreaseScoreWithBizOrInfoUrls*|メッセージの本文 `.biz` に `.info` 含まれるメッセージまたはリンクがスパムとしてマークされます。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>迷惑メールの設定としてマークする

次の ASF 設定では、検出されたメッセージの SCL を 9に設定します。これは、信頼度の高いスパム フィルターの判断と、スパム対策ポリシー内の対応するアクションに対応します。

****

|スパム対策ポリシー設定|説明|追加された X ヘッダー|
|---|---|---|
|**空メッセージ** <p> *MarkAsSpamEmptyMessages*|件名なし、メッセージ本文にコンテンツがないメッセージ、添付ファイルがないメッセージは、信頼度の高いスパムとしてマークされます。|`X-CustomSpam: Empty Message`|
|**HTML 内の JavaScript または VBScript** <p> *MarkAsSpamJavaScriptInHtml*|HTML で JavaScript または Visual Basic Script Edition を使用するメッセージは、信頼度の高いスパムとしてマークされます。 <p> これらのスクリプト言語は、電子メール メッセージで使用され、特定のアクションが自動的に実行されます。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 内の Frame タグまたは IFrame タグ** <p> *MarkAsSpamFramesInHtml*|タグまたは `<frame>` HTML タグ `<iframe>` を含むメッセージは、信頼度の高いスパムとしてマークされます。 <p> これらのタグは、テキストまたはグラフィックスを表示するためのページの書式を設定するために電子メール メッセージで使用されます。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 内の Object タグ** <p> *MarkAsSpamObjectTagsInHtml*|HTML タグを含 `<object>` むメッセージは、信頼度の高いスパムとしてマークされます。 <p> このタグを使用すると、プラグインまたはアプリケーションを HTML ウィンドウで実行できます。|`X-CustomSpam: Object tag in html`|
|**HTML 内の Embed タグ** <p> *MarkAsSpamEmbedTagsInHtml*|HTML タグを含 `<embed>` むメッセージは、信頼度の高いスパムとしてマークされます。 <p> このタグを使用すると、さまざまな種類のドキュメントを HTML ドキュメント (サウンド、ビデオ、画像など) に埋め込むのに使用できます。|`X-CustomSpam: Embed tag in html`|
|**HTML 内の Form タグ** <p> *MarkAsSpamFormTagsInHtml*|HTML タグを含 `<form>` むメッセージは、信頼度の高いスパムとしてマークされます。 <p> このタグは、Web サイト フォームの作成に使用されます。 広告メールには、受信者から情報を要求するために、このタグが含まれていることがよくあります。|`X-CustomSpam: Form tag in html`|
|**HTML 内の Web バグ** <p> *MarkAsSpamWebBugsInHtml*|Web バグ (Web ビーコンとも呼 *ばれる)* は、メッセージが受信者によって読み取られたかどうかを判断するために電子メール メッセージで使用されるグラフィック要素 (多くの場合、1 ピクセル分の小さい要素) です。 <p> Web バグを含むメッセージは、信頼度の高いスパムとしてマークされます。 <p> 正当なニュースレターでは Web バグが使用される可能性があります。ただし、多くの場合、これをプライバシーの侵害と見なしています。 |`X-CustomSpam: Web bug`|
|**機密用語の適用** <p> *MarkAsSpamSensitiveWordList*|Microsoft は、不快なメッセージに関連付けられている単語の動的なリストを保持していますが、編集できません。 <p> 件名またはメッセージ本文に機密性の高い単語の一覧の単語が含まれるメッセージは、信頼度の高いスパムとしてマークされます。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF レコード:Hard Fail** <p> *MarkAsSpamSpfRecordHardFail*|送信元電子メール ドメインの DNS の SPF Sender Policy Framework (SPF) レコードで指定されていない IP アドレスから送信されたメッセージは、信頼度の高いスパムとしてマークされます。 <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: SPF Record Fail`|
|**条件付き Sender ID フィルター処理:Hard Fail** <p> *MarkAsSpamFromAddressAuthFail*|条件付き Sender ID チェックに失敗したメッセージは、スパムとしてマークされます。 <p> この設定では、SPF チェックと Sender ID チェックを組み合わせ、偽造された送信者を含むメッセージ ヘッダーから保護します。 <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: SPF From Record Fail`|
|**NDR バックスキャター** <p> *MarkAsSpamNdrBackscatter*|*バックスカターは* 、メール メッセージ内の偽造された送信者によって引き起こされた、使い方の良い配信以外のレポート (NDRs またはバウンス メッセージとも呼ばれる) です。 詳細については、「 [バックスカター メッセージと EOP」を参照してください](backscatter-messages-and-eop.md)。 <p> 正当なNDRS が配信され、バックスカターがスパムとしてマークされるので、次の環境でこの設定を構成する必要があります。 <ul><li>Exchange Online メールボックスを持つ Microsoft 365 組織。</li><li>EOP を介して送信電子メール *をルーティングする* オンプレミスの電子メール組織。</li></ul> <p> オンプレミスのメールボックスへの受信電子メールを保護するスタンドアロン EOP 環境では、この設定をオンまたはオフにすると、次の結果になります。 <ul><li> **オン**: 正当なNDRs が配信され、バックスカターがスパムとしてマークされます。</li><li>**オフ**: 正当なNDRs とバックスカターは、通常のスパム フィルタリングを通過します。 ほとんどの正当なNDRs は、元のメッセージ送信者に配信されます。 すべてではないが、一部のバックスカターは信頼度の高いスパムとしてマークされます。 定義上、バックスカターは、元の送信者ではなく、スプーフィングされた送信者にのみ配信できます。</li></ul> <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: Backscatter NDR`|
|
