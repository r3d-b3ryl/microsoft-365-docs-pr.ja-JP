---
title: EOP の ASF 設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、スパム対策ポリシー (EOP) で使用できる高度なスパム フィルター (ASF) Exchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6a34507866be90a197fcbed7bd1038cbcec61c84
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682309"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP の高度なスパム フィルター (ASF) 設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

すべての組織Microsoft 365、EOP のスパム対策ポリシーの高度なスパム フィルター (ASF) 設定を使用すると、管理者は特定のメッセージ プロパティに基づいてメッセージをスパムとしてマークできます。 ASF は、スパムでよく見つかるので、これらのプロパティを具体的に対象とします。 プロパティに応じて、ASF 検出によってメッセージがスパムまたは高信頼 **スパム****としてマークされます**。

> [!NOTE]
> 1 つ以上の ASF 設定を有効にすることで、スパム フィルター処理を積極的に行います。 ASF でフィルター処理されたメッセージを誤検知として報告できない。 ASF でフィルター処理されたメッセージは、次の方法で識別できます。
>
> - スパムと信頼性の高いスパム フィルターの評決からの定期的な検疫通知。
> - 検疫でフィルター処理されたメッセージの存在。
> - この記事 `X-CustomSpam:` の説明に従ってメッセージに追加される特定の X ヘッダー フィールド。

以下のセクションでは、Microsoft 365 Defender ポータルおよび Exchange Online PowerShell またはスタンドアロン EOP PowerShell ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) および [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)) でスパム対策ポリシーで使用できる ASF 設定とオプションについて説明します。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="enable-disable-or-test-asf-settings"></a>ASF 設定を有効、無効、またはテストする

ASF 設定ごとに、スパム対策ポリシーで次のオプションを使用できます。

- **On**: ASF は、対応する X ヘッダー フィールドをメッセージに追加し、メッセージを **スパム (** SCL 5 または 6 のスパム スコア設定の [増加) または](#increase-spam-score-settings)高信頼 **スパム (** SCL 9 for [Mark](#mark-as-spam-settings) as spam settings) としてマークします。
- **オフ**: ASF 設定は無効です。 これは既定値であり、変更は行なう必要があります。
- **テスト**: ASF は、対応する X ヘッダー フィールドをメッセージに追加します。 メッセージに何が起こるかは、テスト **モード (***TestModeAction) の値によって* 決まります。
  - **なし**: メッセージの配信は、ASF 検出の影響を受けません。 メッセージは、EOP の他の種類のフィルター処理とルールの対象です。
  - **既定の X ヘッダー テキスト (*AddXHeader*)** を追加する: X ヘッダー `X-CustomSpam: This message was filtered by the custom spam filter option` 値がメッセージに追加されます。 受信トレイ ルールまたはメール フロー ルール (トランスポート ルールとも呼ばれる) でこの値を使用すると、メッセージの配信に影響を与える可能性があります。
  - **Bcc メッセージの送信 (*BccMessage*)**: 指定した電子メール アドレス ( *PowerShell の TestModeBccToRecipients* パラメーター値) がメッセージの Bcc フィールドに追加され、メッセージは追加の BCC 受信者に配信されます。 このポータルMicrosoft 365 Defender、複数の電子メール アドレスをセミコロン (;)) で区切ります。 PowerShell では、複数の電子メール アドレスをコンマで区切ります。

  **注意**:

  - テスト モードは、次の ASF 設定では使用できません。
    - **条件付き送信者 ID フィルター: ハード失敗** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF レコード: ハードフェール** (*MarkAsSpamSpfRecordHardFail*)
  - 同じテスト モード アクションが、Test に設定 *されている* すべての ASF 設定に適用 **されます**。 ASF 設定ごとに異なるテスト モードアクションを構成できません。

## <a name="increase-spam-score-settings"></a>スパム スコアの設定を増やす

次の **[スパム** スコアの向上] ASF 設定では、検出されたメッセージのスパム信頼レベル (SCL) を 5 または 6 に設定します。これはスパム フィルターの評決とスパム対策ポリシーの対応するアクションに対応します。

|スパム対策ポリシー設定|[説明]|X ヘッダーの追加|
|---|---|---|
|**リモート Web サイトへの画像リンク** <p> *IncreaseScoreWithImageLinks*|リモート サイトへの `<Img>` HTML タグ リンクを含むメッセージ (http など) は、スパムとしてマークされます。|`X-CustomSpam: Image links to remote sites`|
|**URL 内の数値 IP アドレス** <p> *IncreaseScoreWithNumericIps*|数値ベースの URL (通常は IP アドレス) を含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: Numeric IP in URL`|
|**別のポートに対する URL リダイレクト** <p> *IncreaseScoreWithRedirectToOtherPort*|80 (HTTP)、8080 (代替 HTTP)、または 443 (HTTPS) 以外の TCP ポートにリダイレクトするハイパーリンクを含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL redirect to other port`|
|**.biz または .info Web サイトへのリンク** <p> *IncreaseScoreWithBizOrInfoUrls*|メッセージの本文に `.biz` 含 `.info` まれるメッセージまたはリンクは、スパムとしてマークされます。|`X-CustomSpam: URL to .biz or .info websites`|

## <a name="mark-as-spam-settings"></a>スパム設定としてマークする

次の **[スパム** ASF としてマーク] 設定では、検出されたメッセージの SCL を 9 に設定します。これは、高信頼スパム フィルターの評決とスパム対策ポリシーの対応するアクションに対応します。

|スパム対策ポリシー設定|[説明]|X ヘッダーの追加|
|---|---|---|
|**空メッセージ** <p> *MarkAsSpamEmptyMessages*|件名がないメッセージ、メッセージ本文にコンテンツがない、添付ファイルがないメッセージは、高信頼スパムとしてマークされます。|`X-CustomSpam: Empty Message`|
|**HTML の埋め込みタグ** <p> *MarkAsSpamEmbedTagsInHtml*|HTML タグを含む `<embed>` メッセージは、高信頼スパムとしてマークされます。 <p> このタグを使用すると、HTML ドキュメント (サウンド、ビデオ、画像など) にさまざまな種類のドキュメントを埋め込みできます。|`X-CustomSpam: Embed tag in html`|
|**HTML 内の JavaScript または VBScript** <p> *MarkAsSpamJavaScriptInHtml*|Html で JavaScript またはスクリプト エディションVisual Basicを使用するメッセージは、高信頼スパムとしてマークされます。 <p> これらのスクリプト言語は、電子メール メッセージで使用され、特定のアクションが自動的に発生します。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 内の Form タグ** <p> *MarkAsSpamFormTagsInHtml*|HTML タグを含む `<form>` メッセージは、高信頼スパムとしてマークされます。 <p> このタグは、Web サイト フォームの作成に使用されます。 広告メールには、受信者から情報を要求するために、このタグが含まれていることがよくあります。|`X-CustomSpam: Form tag in html`|
|**HTML のフレームタグまたは iframe タグ** <p> *MarkAsSpamFramesInHtml*|タグまたは HTML タグを `<frame>` 含 `<iframe>` むメッセージは、高信頼スパムとしてマークされます。 <p> これらのタグは、テキストまたはグラフィックスを表示するためのページの書式を設定するために電子メール メッセージで使用されます。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 内の Web バグ** <p> *MarkAsSpamWebBugsInHtml*|*Web バグ* (Web *ビーコンとも呼* ばれる) は、メッセージが受信者によって読み取られたかどうかを判断するために電子メール メッセージで使用されるグラフィック要素 (多くの場合、1 ピクセル単位で小さい) です。 <p> Web バグを含むメッセージは、高信頼スパムとしてマークされます。 <p> 正規のニュースレターでは Web バグが使用される場合があります。ただし、多くの場合、これはプライバシー侵害であると考える人も多い。 |`X-CustomSpam: Web bug`|
|**HTML 内の Object タグ** <p> *MarkAsSpamObjectTagsInHtml*|HTML タグを含む `<object>` メッセージは、高信頼スパムとしてマークされます。 <p> このタグを使用すると、プラグインまたはアプリケーションを HTML ウィンドウで実行できます。|`X-CustomSpam: Object tag in html`|
|**機密性の高い単語** <p> *MarkAsSpamSensitiveWordList*|Microsoft は、不快な可能性のあるメッセージに関連付けられている単語の動的で編集できないリストを保持しています。 <p> 件名またはメッセージ本文の機密性の高い単語リストの単語を含むメッセージは、高信頼スパムとしてマークされます。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF レコード:Hard Fail** <p> *MarkAsSpamSpfRecordHardFail*|送信元メール ドメインの DNS の SPF Sender Policy Framework (SPF) レコードで指定されていない IP アドレスから送信されたメッセージは、高信頼スパムとしてマークされます。 <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: SPF Record Fail`|

次の **[スパム** ASF としてマーク] 設定では、検出されたメッセージの SCL を 6 に設定します。これはスパム フィルターの評決とスパム対策ポリシーの対応するアクションに対応します。

|スパム対策ポリシー設定|[説明]|X ヘッダーの追加|
|---|---|---|
|**送信者 ID のフィルター処理が失敗する** <p> *MarkAsSpamFromAddressAuthFail*|条件付き送信者 ID チェックに失敗したメッセージは、スパムとしてマークされます。 <p> この設定では、SPF チェックと送信者 ID チェックを組み合わせ、偽造された送信者を含むメッセージ ヘッダーから保護します。 <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: SPF From Record Fail`|
|**Backscatter** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* は、電子メール メッセージ内の偽造送信者によって引き起こされた配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) です。 詳細については、「 [Backscatter メッセージと EOP」を参照してください](backscatter-messages-and-eop.md)。 <p> 正当な NDRs が配信され、バックスカッターがスパムとしてマークされるので、次の環境でこの設定を構成する必要があります。 <ul><li>Microsoft 365メールボックスを持Exchange Online組織。</li><li>EOP を介して *送信* メールをルーティングするオンプレミスのメール組織。</li></ul> <p> 受信メールをオンプレミスメールボックスに保護するスタンドアロン EOP 環境では、この設定をオンまたはオフにすると、次の結果が得られます。 <ul><li> **On**: 正当なNDRsが配信され、バックスカッターはスパムとしてマークされます。</li><li>**オフ**: 正当な NDRs とバックスカッターは、通常のスパム フィルター処理を実行します。 ほとんどの正当なNDRsは、元のメッセージ送信者に配信されます。 すべてではないが、一部のバックスカッターはスパムとしてマークされます。 定義上、backscatter はスプーフィングされた送信者にのみ配信できます。元の送信者には配信されません。</li></ul> <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: Backscatter NDR`|
