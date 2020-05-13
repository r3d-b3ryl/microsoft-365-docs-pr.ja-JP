---
title: EOP の ASF 設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
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
ms.openlocfilehash: 904513780ca472efb91cfcd914ad6c72d6c720f7
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213414"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP の高度なスパムフィルター (ASF) 設定

> [!NOTE]
> 現在、スパム対策ポリシーで使用可能な ASF 設定は、廃止されるプロセスに含まれています。 スパム対策ポリシーでは、これらの設定を使用しないことをお勧めします。 これらの ASF 設定の機能は、フィルター処理スタックの他の部分に組み込まれています。 詳細については、「 [EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」を参照してください。

Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織に Exchange Online メールボックスを使用していないメールボックスを持つ Microsoft 365 組織では、スパム対策ポリシーの高度なスパムフィルター (ASF) 設定 (スパムフィルターポリシーまたはコンテンツフィルターポリシーとも呼ばれます) により、管理者は特定のメッセージプロパティに基づいてメッセージをスパムとし ASF は特に、スパムによく見られるため、これらのプロパティを対象としています。 プロパティによっては、ASF 検出によってメッセージが**スパム**または**信頼度の高いスパム**としてマークされます。

> [!NOTE]
> 1つ以上の ASF 設定を有効にすることは、スパムフィルタリングに対して積極的にアプローチすることです。 ASF によってフィルター処理されたメッセージを誤検知として報告することはできません。 ASF によってフィルター処理されたメッセージを特定するには、次のようにします。 <ul><li>定期的なエンドユーザーのスパム検疫通知。</li><li>フィルター処理されたメッセージが検疫に存在する。</li><li>`X-CustomSpam:`このトピックで説明されているように、メッセージに追加される特定の X-ヘッダーフィールド。</li></ul>

次のセクションでは、セキュリティ & コンプライアンスセンター、および Exchange Online PowerShell またはスタンドアロン EOP PowerShell ([set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy)および[set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)) で使用可能な ASF 設定とオプションについて説明します。 詳細については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="enable-disable-or-test-asf-settings"></a>ASF 設定を有効化、無効化、またはテストする

ASF 設定ごとに、次のオプションがスパム対策ポリシーで利用可能になります。

- **On**: ASF は対応する X-ヘッダーフィールドをメッセージに追加し、メッセージを**スパム**としてマークします ([迷惑メールの設定を増やす](#increase-spam-score-settings)ために scl 5 または6を使用) か、**信頼度の高いスパム**(迷惑メールの[設定](#mark-as-spam-settings)の場合は scl 9) を使用します。

- **Off**: ASF 設定が無効になります。 これは既定値であり、変更しないことをお勧めします。

- **Test**: ASF は、対応する X-ヘッダーフィールドをメッセージに追加します。 メッセージに対して行われる処理は、**テストモードオプション**(*testmodeaction*) 値によって決まります。

  - **None**: メッセージのルーティングと配信は、ASF 検出の影響を受けません。 このメッセージは、EOP の他の種類のフィルター処理およびルールの対象になります。

  - **既定の x-ヘッダーテキスト (*addxheader*) を追加**する: x-ヘッダー値 `X-CustomSpam: This message was filtered by the custom spam filter option` がメッセージに追加されます。 この値を受信トレイルールまたはメールフロールール (トランスポートルールとも呼ばれる) で使用して、メッセージのルーティングと配信に影響を与えることができます。

  - **Bcc Bcc メッセージ (*BccMessage*)**: 指定された電子メールアドレス (PowerShell の*TestModeBccToRecipients*パラメーター値) は、メッセージの bcc フィールドに追加され、メッセージは bcc 受信者に配信されます。 セキュリティ & コンプライアンスセンターでは、複数の電子メールアドレスをセミコロン (;) で区切ります。 PowerShell では、複数の電子メールアドレスをコンマで区切ります。

  **注**:

  - テストモードは、次の ASF 設定では使用できません。

    - **条件付き送信者 ID フィルター: hard fail** (*MarkAsSpamFromAddressAuthFail*)

    - **NDR バック散布**(*MarkAsSpamNdrBackscatter*)

    - **SPF レコード: hard fail** (*MarkAsSpamSpfRecordHardFail*)

  - **テスト**に設定されている*すべて*の ASF 設定に同じテストモードアクションが適用されます。 異なる ASF 設定に対して異なるテストモードアクションを構成することはできません。

## <a name="increase-spam-score-settings"></a>スパムスコアの設定を増やす

次の ASF 設定は、検出されたメッセージのスパム信頼レベル (SCL) を5または6に設定します。これは、**スパム**フィルター verdict およびスパム対策ポリシーの対応するアクションに対応します。

||||
|---|---|---|
|**スパム対策ポリシー設定**|**説明**|**X-ヘッダーの追加**|
|**リモート サイトへのイメージ リンク** <br/><br/> *IncreaseScoreWithImageLinks*|`<Img>`リモートサイトへの HTML タグリンク (たとえば、http を使用する) を含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: Image links to remote sites`|
|**別のポートに対する URL リダイレクト** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|80 (HTTP)、8080 (代替 HTTP)、または 443 (HTTPS) 以外の TCP ポートにリダイレクトするハイパーリンクを含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL redirect to other port`|
|**URL 内の数値 IP アドレス** <br/><br/> *IncreaseScoreWithNumericIps*|数値ベースの Url (通常は IP アドレス) を含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: Numeric IP in URL`|
|**.biz Web サイトまたは .info Web サイトへの URL** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|メッセージの本文にある、* または. info リンクを含むメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>スパム設定としてマークする

次の ASF 設定では、検出されたメッセージの SCL を9に設定します。これは、**信頼度の高いスパム**フィルター verdict およびスパム対策ポリシーの対応するアクションに対応します。

||||
|---|---|---|
|**スパム対策ポリシー設定**|**説明**|**X-ヘッダーの追加**|
|**空メッセージ** <br/><br/> *MarkAsSpamEmptyMessages*|件名がなく、メッセージ本文にコンテンツがないメッセージ。添付ファイルは、信頼度の高いスパムとしてマークされません。|`X-CustomSpam: Empty Message`|
|**HTML 内の JavaScript または VBScript** <br/><br/> *MarkAsSpamJavaScriptInHtml*|HTML で JavaScript または Visual Basic Script Edition を使用するメッセージは、信頼度の高いスパムとしてマークされます。 <br/><br/> これらのスクリプト言語は、特定のアクションが自動的に実行されるように電子メールメッセージで使用されます。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 内の Frame タグまたは IFrame タグ** <br><br/> *MarkAsSpamFramesInHtml*|`<frame>`または HTML タグを含むメッセージ `<iframe>` は、信頼度の高いスパムとしてマークされます。 <br/><br/> これらのタグは、テキストやグラフィックスを表示するようにページを書式設定するために、電子メールメッセージで使用されます。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 内の Object タグ** <br><br/> *MarkAsSpamObjectTagsInHtml*|HTML タグを含むメッセージ `<object>` は、信頼度の高いスパムとしてマークされます。 <br/><br/> このタグを使用すると、プラグインまたはアプリケーションを HTML ウィンドウで実行できます。|`X-CustomSpam: Object tag in html`|
|**HTML 内の Embed タグ** <br><br/> *MarkAsSpamEmbedTagsInHtml*|HTML タグを含むメッセージ `<embed>` は、信頼度の高いスパムとしてマークされます。 <br/><br/> このタグにより、さまざまな種類のドキュメントを HTML ドキュメントに埋め込むことができます (例: サウンド、ムービー、画像)。|`X-CustomSpam: Embed tag in html`|
|**HTML 内の Form タグ** <br><br/> *MarkAsSpamFormTagsInHtml*|HTML タグを含むメッセージ `<form>` は、信頼度の高いスパムとしてマークされます。 <br/><br/> このタグは、web サイトフォームを作成するために使用されます。 広告メールには、受信者から情報を要求するために、このタグが含まれていることがよくあります。|`X-CustomSpam: Form tag in html`|
|**HTML 内の Web バグ** <br><br/> *MarkAsSpamWebBugsInHtml*|*Web バグ*( *web ビーコン*とも呼ばれます) は、電子メールメッセージでメッセージが開封されたかどうかを判断するために使用するグラフィック要素 (多くの場合、1ピクセル×1ピクセルです) です。 <br/><br/> Web バグが含まれているメッセージは、信頼度の高いスパムとしてマークされます。 <br/><br/> 正当なニュースレターでは web バグを使用することもありますが、多くの場合、プライバシーの侵害を検討しています。 |`X-CustomSpam: Web bug`|
|**機密用語の適用** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft は、不快感を与える可能性のあるメッセージに関連付けられている単語の動的ではなく、編集可能ではないリストを保持しています。 <br/><br/> 件名またはメッセージ本文の機密単語リストからの単語が含まれているメッセージは、信頼度の高いスパムとしてマークされます。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF レコード:Hard Fail** <br><br/> *MarkAsSpamSpfRecordHardFail*|送信元の電子メールドメインに対して DNS の SPF Sender Policy Framework (SPF) レコードに指定されていない IP アドレスから送信されたメッセージは、信頼度の高いスパムとしてマークされます。 <br/><br/> この設定ではテストモードを使用できません。|`X-CustomSpam: SPF Record Fail`|
|**条件付き Sender ID フィルター処理:Hard Fail** <br><br/> *MarkAsSpamFromAddressAuthFail*|条件付き Sender ID チェックにハードエラーが発生するメッセージは、スパムとしてマークされます。 <br/><br/> この設定は、SPF チェックと Sender ID チェックを組み合わせて、偽造された送信者を含むメッセージヘッダーから保護するのに役立ちます。 <br/><br/> この設定ではテストモードを使用できません。|`X-CustomSpam: SPF From Record Fail`|
|**NDR バックスキャター** <br><br/> *MarkAsSpamNdrBackscatter*|*Backscatter*は、電子メールメッセージ内の偽造された送信者によって発生した、不要な配信不能レポート (ndr またはバウンスメッセージとも呼ばれる) です。 詳細については、「 [Backscatter messages AND EOP](backscatter-messages-and-eop.md)」を参照してください。 <br/><br/> 正当な ndr が配信され、バックスキャターがスパムとしてマークされているため、次の環境でこの設定を構成する必要はありません。 <ul><li>Microsoft 365 組織と Exchange Online メールボックス</li><li>EOP を経由して*送信*電子メールをルーティングする社内電子メール組織。</li></ul><br/> 受信メールを社内メールボックスに保護するスタンドアロン EOP 環境では、この設定をオンまたはオフにすると、次の結果が得られます。 <ul><li> **オン**: 正当な ndr が配信され、バックスキャターがスパムとしてマークされます。</li><li>**Off**: 正当な ndr とバックスキャッターが通常のスパムフィルタリングを通過します。 正当な Ndr は、元のメッセージの送信者に配信されます。 すべてではありませんが、一部のバックスキャターは、信頼度の高いスパムとしてマークされます。 定義上、バックスキャターは、元の送信者ではなく、スプーフィングされた送信者にのみ配信できます。</li></ul><br/> この設定ではテストモードを使用できません。|`X-CustomSpam: Backscatter NDR`|
|
