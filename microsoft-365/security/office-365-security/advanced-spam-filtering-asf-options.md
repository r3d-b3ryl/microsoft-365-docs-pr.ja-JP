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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のスパム対策ポリシーで利用できる高度なスパムフィルター (ASF) 設定について学習できます。
ms.openlocfilehash: f9295de6fb524cff16394d305ca9247d9f7ce07b
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49020929"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP の高度なスパムフィルター (ASF) 設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 現在、スパム対策ポリシーで使用可能な ASF 設定は、廃止されるプロセスに含まれています。 スパム対策ポリシーでは、これらの設定を使用しないことをお勧めします。 これらの ASF 設定の機能は、フィルター処理スタックの他の部分に組み込まれています。 詳細については、「 [EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」を参照してください。

すべての Microsoft 365 組織で、EOP のスパム対策ポリシーにある Advanced Spam Filter (ASF) 設定により、管理者は特定のメッセージプロパティに基づいてメッセージをスパムとしてマークできます。 ASF は特に、スパムによく見られるため、これらのプロパティを対象としています。 プロパティによっては、ASF 検出によってメッセージが **スパム** または **信頼度の高いスパム** としてマークされます。

> [!NOTE]
> 1つ以上の ASF 設定を有効にすることは、スパムフィルタリングに対して積極的にアプローチすることです。 ASF によってフィルター処理されたメッセージを誤検知として報告することはできません。 ASF によってフィルター処理されたメッセージを特定するには、次のようにします。
>
> - 定期的なエンドユーザーのスパム検疫通知。
>
> - フィルター処理されたメッセージが検疫に存在する。
>
> - `X-CustomSpam:`このトピックで説明されているように、メッセージに追加される特定の X-ヘッダーフィールド。

次のセクションでは、セキュリティ & コンプライアンスセンター、および Exchange Online PowerShell またはスタンドアロン EOP PowerShell ([set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) および [set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)) で使用可能な ASF 設定とオプションについて説明します。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="enable-disable-or-test-asf-settings"></a>ASF 設定を有効化、無効化、またはテストする

ASF 設定ごとに、次のオプションがスパム対策ポリシーで利用可能になります。

- **On** : ASF は対応する X-ヘッダーフィールドをメッセージに追加し、メッセージを **スパム** としてマークします ( [迷惑メールの設定を増やす](#increase-spam-score-settings)ために scl 5 または6を使用) か、 **信頼度の高いスパム** (迷惑メールの [設定](#mark-as-spam-settings)の場合は scl 9) を使用します。

- **Off** : ASF 設定が無効になります。 これは既定値であり、変更しないことをお勧めします。

- **Test** : ASF は、対応する X-ヘッダーフィールドをメッセージに追加します。 メッセージに対して行われる処理は、 **テストモードオプション** ( *testmodeaction* ) 値によって決まります。

  - **None** : メッセージ配信が ASF 検出によって影響を受けることはありません。 このメッセージは、EOP の他の種類のフィルター処理およびルールの対象になります。

  - **既定の x-ヘッダーテキスト ( *addxheader* ) を追加** する: x-ヘッダー値 `X-CustomSpam: This message was filtered by the custom spam filter option` がメッセージに追加されます。 この値を受信トレイルールまたはメールフロールール (トランスポートルールとも呼ばれる) で使用して、メッセージの配信に影響を与えることができます。

  - **Bcc Bcc メッセージ ( *BccMessage* )** : 指定された電子メールアドレス (PowerShell の *TestModeBccToRecipients* パラメーター値) がメッセージの bcc フィールドに追加され、メッセージが追加の Bcc 受信者に配信されます。 セキュリティ & コンプライアンスセンターでは、複数の電子メールアドレスをセミコロン (;) で区切ります。 PowerShell では、複数の電子メールアドレスをコンマで区切ります。

  **注** :

  - テストモードは、次の ASF 設定では使用できません。

    - **条件付き送信者 ID フィルター: hard fail** ( *MarkAsSpamFromAddressAuthFail* )
    - **NDR バック散布** ( *MarkAsSpamNdrBackscatter* )
    - **SPF レコード: hard fail** ( *MarkAsSpamSpfRecordHardFail* )

  - **テスト** に設定されている *すべて* の ASF 設定に同じテストモードアクションが適用されます。 異なる ASF 設定に対して異なるテストモードアクションを構成することはできません。

## <a name="increase-spam-score-settings"></a>スパムスコアの設定を増やす

次の ASF 設定は、検出されたメッセージのスパム信頼レベル (SCL) を5または6に設定します。これは、 **スパム** フィルター verdict およびスパム対策ポリシーの対応するアクションに対応します。

****

|スパム対策ポリシー設定|説明|X-ヘッダーの追加|
|---|---|---|
|**リモート サイトへのイメージ リンク** <p> *IncreaseScoreWithImageLinks*|`<Img>`リモートサイトへの HTML タグリンク (たとえば、http を使用する) を含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: Image links to remote sites`|
|**別のポートに対する URL リダイレクト** <p> *IncreaseScoreWithRedirectToOtherPort*|80 (HTTP)、8080 (代替 HTTP)、または 443 (HTTPS) 以外の TCP ポートにリダイレクトするハイパーリンクを含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL redirect to other port`|
|**URL 内の数値 IP アドレス** <p> *IncreaseScoreWithNumericIps*|数値ベースの Url (通常は IP アドレス) を含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: Numeric IP in URL`|
|**.biz Web サイトまたは .info Web サイトへの URL** <p> *IncreaseScoreWithBizOrInfoUrls*|`.biz`または `.info` メッセージ本文内のリンクを含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>スパム設定としてマークする

次の ASF 設定では、検出されたメッセージの SCL を9に設定します。これは、 **信頼度の高いスパム** フィルター verdict およびスパム対策ポリシーの対応するアクションに対応します。

****

|スパム対策ポリシー設定|説明|X-ヘッダーの追加|
|---|---|---|
|**空メッセージ** <p> *MarkAsSpamEmptyMessages*|件名がなく、メッセージ本文にコンテンツがないメッセージ。添付ファイルは、信頼度の高いスパムとしてマークされません。|`X-CustomSpam: Empty Message`|
|**HTML 内の JavaScript または VBScript** <p> *MarkAsSpamJavaScriptInHtml*|HTML で JavaScript または Visual Basic Script Edition を使用するメッセージは、信頼度の高いスパムとしてマークされます。 <p> これらのスクリプト言語は、特定のアクションが自動的に実行されるように電子メールメッセージで使用されます。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 内の Frame タグまたは IFrame タグ** <p> *MarkAsSpamFramesInHtml*|`<frame>`または HTML タグを含むメッセージ `<iframe>` は、信頼度の高いスパムとしてマークされます。 <p> これらのタグは、テキストやグラフィックスを表示するようにページを書式設定するために、電子メールメッセージで使用されます。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 内の Object タグ** <p> *MarkAsSpamObjectTagsInHtml*|HTML タグを含むメッセージ `<object>` は、信頼度の高いスパムとしてマークされます。 <p> このタグを使用すると、プラグインまたはアプリケーションを HTML ウィンドウで実行できます。|`X-CustomSpam: Object tag in html`|
|**HTML 内の Embed タグ** <p> *MarkAsSpamEmbedTagsInHtml*|HTML タグを含むメッセージ `<embed>` は、信頼度の高いスパムとしてマークされます。 <p> このタグを使用すると、HTML ドキュメントにさまざまな種類のドキュメントを埋め込むことができます (例: サウンド、ビデオ、画像)。|`X-CustomSpam: Embed tag in html`|
|**HTML 内の Form タグ** <p> *MarkAsSpamFormTagsInHtml*|HTML タグを含むメッセージ `<form>` は、信頼度の高いスパムとしてマークされます。 <p> このタグは、web サイトフォームを作成するために使用されます。 広告メールには、受信者から情報を要求するために、このタグが含まれていることがよくあります。|`X-CustomSpam: Form tag in html`|
|**HTML 内の Web バグ** <p> *MarkAsSpamWebBugsInHtml*|*Web バグ* ( *web ビーコン* とも呼ばれます) は、電子メールメッセージでメッセージが受信者に開封されたかどうかを判断するために使用されるグラフィック要素 (多くの場合、1ピクセル×1ピクセルです) です。 <p> Web バグが含まれているメッセージは、信頼度の高いスパムとしてマークされます。 <p> 正当なニュースレターでは web バグを使用することもありますが、多くの場合、プライバシーの侵害を検討しています。 |`X-CustomSpam: Web bug`|
|**機密用語の適用** <p> *MarkAsSpamSensitiveWordList*|Microsoft は、不快感を与える可能性のあるメッセージに関連付けられている単語の動的ではなく、編集可能ではないリストを保持しています。 <p> 件名またはメッセージ本文の機密単語リストからの単語が含まれているメッセージは、信頼度の高いスパムとしてマークされます。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF レコード:Hard Fail** <p> *MarkAsSpamSpfRecordHardFail*|送信元の電子メールドメインに対して DNS の SPF Sender Policy Framework (SPF) レコードに指定されていない IP アドレスから送信されたメッセージは、信頼度の高いスパムとしてマークされます。 <p> この設定ではテストモードを使用できません。|`X-CustomSpam: SPF Record Fail`|
|**条件付き Sender ID フィルター処理:Hard Fail** <p> *MarkAsSpamFromAddressAuthFail*|条件付き Sender ID チェックにハードエラーが発生するメッセージは、スパムとしてマークされます。 <p> この設定は、SPF チェックと Sender ID チェックを組み合わせて、偽造された送信者を含むメッセージヘッダーから保護するのに役立ちます。 <p> この設定ではテストモードを使用できません。|`X-CustomSpam: SPF From Record Fail`|
|**NDR バックスキャター** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* は、電子メールメッセージ内の偽造された送信者によって発生した、不要な配信不能レポート (ndr またはバウンスメッセージとも呼ばれる) です。 詳細については、「 [Backscatter messages AND EOP](backscatter-messages-and-eop.md)」を参照してください。 <p> 正当な ndr が配信され、バックスキャターがスパムとしてマークされているため、次の環境でこの設定を構成する必要はありません。 <ul><li>Microsoft 365 組織と Exchange Online メールボックス</li><li>EOP を経由して *送信* 電子メールをルーティングする社内電子メール組織。</li></ul><br/> 受信メールを社内メールボックスに保護するスタンドアロン EOP 環境では、この設定をオンまたはオフにすると、次の結果が得られます。 <ul><li> **オン** : 正当な ndr が配信され、バックスキャターがスパムとしてマークされます。</li><li>**Off** : 正当な ndr とバックスキャッターが通常のスパムフィルタリングを通過します。 正当な Ndr は、元のメッセージの送信者に配信されます。 すべてではありませんが、一部のバックスキャターは、信頼度の高いスパムとしてマークされます。 定義上、バックスキャターは、元の送信者ではなく、スプーフィングされた送信者にのみ配信できます。</li></ul><br/> この設定ではテストモードを使用できません。|`X-CustomSpam: Backscatter NDR`|
|
