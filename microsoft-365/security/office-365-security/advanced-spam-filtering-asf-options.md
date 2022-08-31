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
description: 管理者は、Exchange Online Protection (EOP) のスパム対策ポリシーで使用できる高度なスパム フィルター (ASF) 設定について学習できます。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 67b35aceb9507683ebe83c7a5bcde2c2bcec4d94
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67473615"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP の高度なスパム フィルター (ASF) 設定

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

すべての Microsoft 365 組織で、EOP のスパム対策ポリシーの高度なスパム フィルター (ASF) 設定により、管理者は特定のメッセージ プロパティに基づいてメッセージをスパムとしてマークできます。 ASF は、スパムでよく見つかるため、これらのプロパティを具体的に対象とします。 プロパティに応じて、ASF 検出によってメッセージが **スパム** または **高信頼スパム** としてマークされます。

> [!NOTE]
> ASF 設定の 1 つ以上を有効にすることは、スパム フィルター処理に対する積極的なアプローチです。 ASF でフィルター処理されたメッセージを誤検知として報告することはできません。 ASF によってフィルター処理されたメッセージは、次の方法で識別できます。
>
> - スパムと信頼度の高いスパム フィルターの判定からの定期的な検疫通知。
> - 検疫にフィルター処理されたメッセージが存在する。
> - この記事で説明されているように、メッセージに追加される特定 `X-CustomSpam:` の X ヘッダー フィールド。

次のセクションでは、Microsoft 365 Defender ポータルのスパム対策ポリシー、およびExchange Online PowerShell またはスタンドアロン EOP PowerShell ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) および [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)) で使用できる ASF の設定とオプションについて説明します。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="enable-disable-or-test-asf-settings"></a>ASF 設定を有効、無効、またはテストする

ASF 設定ごとに、スパム対策ポリシーで次のオプションを使用できます。

- **オン**: ASF は、対応する X ヘッダー フィールドをメッセージに追加し、メッセージをスパム ( **スパム** [スコア](#increase-spam-score-settings)設定を増やすには SCL 5 または 6) または **高信頼スパム** (スパムとしてマーク設定の SCL 9) [としてマークします](#mark-as-spam-settings)。
- **オフ**: ASF 設定が無効です。 これは既定値であり、変更しないことをお勧めします。
- **テスト**: ASF は、対応する X ヘッダー フィールドをメッセージに追加します。 メッセージの動作は、 **テスト モード** (*TestModeAction*) 値によって決まります。
  - **なし**: メッセージ配信は ASF 検出の影響を受けません。 このメッセージは、EOP の他の種類のフィルター処理とルールの対象となります。
  - **既定の X ヘッダー テキスト (*AddXHeader*) の追加**: X ヘッダー値 `X-CustomSpam: This message was filtered by the custom spam filter option` がメッセージに追加されます。 受信トレイ ルールまたはメール フロー ルール (トランスポート ルールとも呼ばれます) でこの値を使用して、メッセージの配信に影響を与えることができます。
  - **Bcc メッセージの送信 (*BccMessage*)**: 指定した電子メール アドレス (PowerShell の *TestModeBccToRecipients* パラメーター値) がメッセージの Bcc フィールドに追加され、メッセージは追加の Bcc 受信者に配信されます。 Microsoft 365 Defender ポータルでは、複数のメール アドレスをセミコロン (;)で区切ります。 PowerShell では、複数の電子メール アドレスをコンマで区切ります。

  **注**:

  - テスト モードは、次の ASF 設定では使用できません。
    - **条件付き送信者 ID のフィルター処理: ハード エラー** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR バックスキャッター**(*MarkAsSpamNdrBackscatter*)
    - **SPF レコード: ハード エラー** (*MarkAsSpamSpfRecordHardFail*)
  - 同じテスト モードアクションが、[**テスト**] に設定 *されているすべての* ASF 設定に適用されます。 ASF 設定ごとに異なるテスト モードアクションを構成することはできません。

## <a name="increase-spam-score-settings"></a>スパム スコアの設定を増やす

次の **スパム スコア ASF の増加** 設定では、検出されたメッセージのスパム信頼レベル (SCL) を 5 または 6 に設定します。 **これは、スパム** フィルターの判定とスパム対策ポリシーの対応するアクションに対応します。

|スパム対策ポリシー設定|説明|X ヘッダーが追加されました|
|---|---|---|
|**リモート Web サイトへのイメージ リンク** <p> *IncreaseScoreWithImageLinks*|リモート サイトへの HTML タグ リンクを含む `<Img>` メッセージ (http を使用するなど) は、スパムとしてマークされます。|`X-CustomSpam: Image links to remote sites`|
|**URL 内の数値 IP アドレス** <p> *IncreaseScoreWithNumericIps*|数値ベースの URL (通常は IP アドレス) を含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: Numeric IP in URL`|
|**別のポートに対する URL リダイレクト** <p> *IncreaseScoreWithRedirectToOtherPort*|80 (HTTP)、8080 (代替 HTTP)、または 443 (HTTPS) 以外の TCP ポートにリダイレクトするハイパーリンクを含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL redirect to other port`|
|**.biz または .info Web サイトへのリンク** <p> *IncreaseScoreWithBizOrInfoUrls*|メッセージの本文に含まれる `.biz` メッセージまたは `.info` リンクは、スパムとしてマークされます。|`X-CustomSpam: URL to .biz or .info websites`|

## <a name="mark-as-spam-settings"></a>スパム設定としてマークする

次のスパム ASF **としてマーク** 設定では、検出されたメッセージの SCL を 9 に設定します。これは、 **高信頼スパム** フィルターの判定とスパム対策ポリシーでの対応するアクションに対応します。

|スパム対策ポリシー設定|説明|X ヘッダーが追加されました|
|---|---|---|
|**空メッセージ** <p> *MarkAsSpamEmptyMessages*|件名のないメッセージ、メッセージ本文にコンテンツがないメッセージ、および添付ファイルがないメッセージは、信頼度の高いスパムとしてマークされます。|`X-CustomSpam: Empty Message`|
|**HTML の埋め込みタグ** <p> *MarkAsSpamEmbedTagsInHtml*|HTML タグを含む `<embed>` メッセージは、信頼度の高いスパムとしてマークされます。 <p> このタグを使用すると、HTML ドキュメント (サウンド、ビデオ、画像など) にさまざまな種類のドキュメントを埋め込めます。|`X-CustomSpam: Embed tag in html`|
|**HTML 内の JavaScript または VBScript** <p> *MarkAsSpamJavaScriptInHtml*|HTML で JavaScript または Visual Basic Script Edition を使用するメッセージは、高信頼スパムとしてマークされます。 <p> これらのスクリプト言語は、電子メール メッセージで使用され、特定のアクションが自動的に発生します。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 内の Form タグ** <p> *MarkAsSpamFormTagsInHtml*|HTML タグを含む `<form>` メッセージは、信頼度の高いスパムとしてマークされます。 <p> このタグは、Web サイト フォームの作成に使用されます。 広告メールには、受信者から情報を要求するために、このタグが含まれていることがよくあります。|`X-CustomSpam: Form tag in html`|
|**HTML のフレーム タグまたは iframe タグ** <p> *MarkAsSpamFramesInHtml*|HTML タグを含む `<frame>` メッセージは `<iframe>` 、信頼度の高いスパムとしてマークされます。 <p> これらのタグは、テキストまたはグラフィックスを表示するためのページの書式設定に電子メール メッセージで使用されます。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 内の Web バグ** <p> *MarkAsSpamWebBugsInHtml*|*Web バグ* (*Web ビーコン* とも呼ばれます) は、受信者がメッセージを読み取ったかどうかを判断するために電子メール メッセージで使用されるグラフィック要素 (多くの場合、1 ピクセルずつ小さい) です。 <p> Web バグを含むメッセージは、信頼度の高いスパムとしてマークされます。 <p> 正当なニュースレターでは Web バグが使用される場合がありますが、多くの場合、これはプライバシーの侵害であると考えられます。 |`X-CustomSpam: Web bug`|
|**HTML 内の Object タグ** <p> *MarkAsSpamObjectTagsInHtml*|HTML タグを含む `<object>` メッセージは、信頼度の高いスパムとしてマークされます。 <p> このタグを使用すると、プラグインまたはアプリケーションを HTML ウィンドウで実行できます。|`X-CustomSpam: Object tag in html`|
|**機密性の高い単語** <p> *MarkAsSpamSensitiveWordList*|Microsoft は、不適切な可能性があるメッセージに関連付けられている単語の動的で編集不可のリストを保持しています。 <p> 件名またはメッセージ本文の機密性の高い単語リストの単語を含むメッセージは、信頼度の高いスパムとしてマークされます。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF レコード:Hard Fail** <p> *MarkAsSpamSpfRecordHardFail*|送信元電子メール ドメインの DNS の SPF 送信者ポリシー フレームワーク (SPF) レコードで指定されていない IP アドレスから送信されたメッセージは、高信頼スパムとしてマークされます。 <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: SPF Record Fail`|

次の **[スパム ASF としてマーク** ] 設定では、検出されたメッセージの SCL を 6 に設定します。 **これは、スパム** フィルターの判定とスパム対策ポリシーの対応するアクションに対応します。

|スパム対策ポリシー設定|説明|X ヘッダーが追加されました|
|---|---|---|
|**送信者 ID フィルターのハード 失敗** <p> *MarkAsSpamFromAddressAuthFail*|条件付き送信者 ID チェックにハード 失敗したメッセージは、スパムとしてマークされます。 <p> この設定は、SPF チェックと送信者 ID チェックを組み合わせて、偽造された送信者を含むメッセージ ヘッダーから保護するのに役立ちます。 <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: SPF From Record Fail`|
|**バックスキャター** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* は、電子メール メッセージ内の偽造された送信者によって引き起こされる、配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) です。 詳細については、「 [Backscatter メッセージと EOP](backscatter-messages-and-eop.md)」を参照してください。 <p> 正当な NDR が配信され、バックスキャッターがスパムとしてマークされるため、次の環境でこの設定を構成する必要はありません。 <ul><li>Exchange Onlineメールボックスを持つ Microsoft 365 組織。</li><li>EOP を介して *送信* メールをルーティングするオンプレミスのメール組織。</li></ul> <p> オンプレミスメールボックスへの受信メールを保護するスタンドアロン EOP 環境では、この設定をオンまたはオフにすると、次の結果が得られます。 <ul><li> **オン**: 正当な NDR が配信され、バックスキャッターがスパムとしてマークされます。</li><li>**オフ**: 正当な NDR とバックスキャッターは、通常のスパム フィルター処理を通過します。 ほとんどの正当な NDR は、元のメッセージ送信者に配信されます。 バックスキャッターにはスパムとしてマークされているものもありますが、すべてではありません。 定義上、バックスキャッターはスプーフィングされた送信者にのみ配信でき、元の送信者には配信できません。</li></ul> <p> この設定では、テスト モードを使用できません。|`X-CustomSpam: Backscatter NDR`|
