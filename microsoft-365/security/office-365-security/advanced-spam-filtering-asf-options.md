---
title: EOP での ASF 設定
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
description: 管理者は、Exchange Online Protection (EOP) のスパム対策ポリシーで使用可能な高度なスパム フィルター (ASF) 設定について説明できます。
ms.openlocfilehash: 2a79a6721a587e3033e71e6e46856a21cffe7bcc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827339"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP での高度なスパム フィルター (ASF) の設定

> [!NOTE]
> 迷惑メール対策ポリシーで現在使用可能な ASF 設定は廃止プロセス中です。 スパム対策ポリシーではこれらの設定を使用しないことをお勧めします。 これらの ASF 設定の機能は、フィルタリング スタックの他の部分に組み込まれます。 詳細については [、「EOP スパム対策ポリシーの設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、スパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) の高度なスパム フィルター (ASF) 設定で、管理者は特定のメッセージ プロパティに基づいてメッセージをスパムとしてマークできます。 ASF はスパムで一般的に見つかるため、これらのプロパティを具体的にターゲットとしています。 プロパティに応じて、ASF 検出はメッセージを **スパムまたは** 精度の高 **いスパムのどちらかとしてマークします**。

> [!NOTE]
> 1 つ以上の ASF 設定を有効にすると、スパム フィルターに対する総合的なアプローチとすることができます。 ASF でフィルター処理されたメッセージを誤検知としてレポートすることはできません。 次の方法で ASF でフィルター処理されたメッセージを識別できます。
>
> - 定期的なエンドユーザー スパム検疫通知
>
> - 検疫内のフィルター処理されたメッセージの存在。
>
> - このトピック `X-CustomSpam:` で説明するメッセージに追加される特定の X ヘッダー フィールド。

以下のセクションでは、セキュリティ & コンプライアンス センター、および Exchange Online PowerShell またはスタンドアロン EOP PowerShell[(New-HostedContentFilterPolicy と Set-HostedContentFilterPolicy)](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) で利用できる ASF 設定と [オプションについて説明します](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="enable-disable-or-test-asf-settings"></a>ASF 設定を有効化、無効化、またはテストする

各 ASF 設定について、スパム対策ポリシーでは次のオプションを選択できます。

- **On:** ASF は対応する X-Header フィールドをメッセージに追加し、そのメッセージを**スパムとしてマーク**します (SCL 5 または 6 スパム スコア設定の場合は SCL 5 または 6)**または高信頼スパム**(Spam としての Mark を設定する SCL 9) のマークを[付けています](#mark-as-spam-settings)。 [Increase spam score settings](#increase-spam-score-settings)

- **Off:** ASF 設定は無効です。 これは既定値で、変更しないことをお勧めします。

- **テスト**: ASF は、対応する X-ヘッダー フィールドをメッセージに追加します。 メッセージがどうなったかはテスト モード オプション **(TestModeAction** )*値によって*決定されます。

  - **なし**: メッセージ ルーティングと配信は、ASF 検出の影響を受けません。 EOP では、他の種類のフィルターやルールに従う必要があります。

  - **既定の X-ヘッダー テキスト *(AddXHeader)*** を追加: X ヘッダー値 `X-CustomSpam: This message was filtered by the custom spam filter option` がメッセージに追加されます。 この値は、受信トレイ ルールまたはメール フロー ルール (トランスポート ルールとも呼ばれる) の中で、メッセージのルーティングと配信に影響を与えられてします。

  - **Bcc メッセージの送信 *(BccMessage):*** 指定された電子メール アドレス (PowerShell*の TestModeBccToRecipients*パラメーター値) がメッセージの Bcc フィールドに追加され、BCC 受信者にメッセージが配信されます。 コンプライアンス センターで複数&アドレスをセミコロン ( ; ) で区切ります。 PowerShell では、複数のメール アドレスをコンマで区切ります。

  **注**:

  - テスト モードは、次の ASF 設定では使いません。

    - **条件付き Sender ID フィルター処理: Hard Fail** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR バックスキャター***(MarkAsSpamNdrBackscatter)*
    - **SPF レコード:Hard Fail** (*MarkAsSpamSpfRecordHardFail*)

  - 同じテスト モードのアクションが、すべての ASF *設定* が [テスト] に設定されているものに **適用されます**。 異なる ASF 設定に対して、異なるテスト モードの操作を構成できません。

## <a name="increase-spam-score-settings"></a>スパム スコア設定の増加

次の ASF 設定では、検出されたメッセージの Spam Confidence Level (SCL) を 5 または 6 に設定します。これは、 **スパム** フィルターの確認と、スパム対策ポリシーの対応するアクションに対応します。

****

|スパム対策ポリシー設定|説明|X ヘッダーの追加|
|---|---|---|
|**リモート サイトへのイメージ リンク** <br/><br/> *IncreaseScoreWithImageLinks*|リモート サイトへの `<Img>` HTML タグ リンクを含むメッセージ (たとえば、http を使用) はスパムとしてマークされます。|`X-CustomSpam: Image links to remote sites`|
|**別のポートに対する URL リダイレクト** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|80 (HTTP)、8080 (代替 HTTP)、443 (HTTPS) 以外の TCP ポートにリダイレクトするハイパーリンクを含むメッセージはスパムとしてマークされます。|`X-CustomSpam: URL redirect to other port`|
|**URL 内の数値 IP アドレス** <br/><br/> *IncreaseScoreWithNumericIps*|数値ベースの URL (通常は、IP アドレス) を含むメッセージはスパムとしてマークされます。|`X-CustomSpam: Numeric IP in URL`|
|**.biz Web サイトまたは .info Web サイトへの URL** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|メッセージ本文に .biz リンクや .info リンクが含まれているメッセージは、スパムとしてマークされます。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>スパム設定としてマークする

次の ASF 設定では、検出されたメッセージの SCL を 9 に設定します。これは、 **高信頼** スパム フィルターの詳細と、スパム対策ポリシーの対応するアクションに対応します。

****

|スパム対策ポリシー設定|説明|X ヘッダーの追加|
|---|---|---|
|**空メッセージ** <br/><br/> *MarkAsSpamEmptyMessages*|件名を持っていないメッセージ、メッセージ本文にコンテンツがないメッセージ、添付ファイルがない場合、高信頼スパムとしてマークされます。|`X-CustomSpam: Empty Message`|
|**HTML 内の JavaScript または VBScript** <br/><br/> *MarkAsSpamJavaScriptInHtml*|JavaScript または Visual Basic Script Edition を HTML で使用するメッセージは、高信頼スパムとしてマークされます。 <br/><br/> これらのスクリアは、メール メッセージ内で特定のアクションが自動的に実行される原因として使用されます。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 内の Frame タグまたは IFrame タグ** <br><br/> *MarkAsSpamFramesInHtml*|または HTML タグ `<frame>` を `<iframe>` 含むメッセージは、高信頼スパムとしてマークされます。 <br/><br/> これらのタグは、テキストやグラフィックの表示用にページを書式設定するために、電子メール メッセージで使用されます。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 内の Object タグ** <br><br/> *MarkAsSpamObjectTagsInHtml*|HTML タグを `<object>` 含むメッセージは、信頼度の高いスパムとしてマークされます。 <br/><br/> このタグにより、プラグインやアプリケーションが HTML ウィンドウ内で実行されます。|`X-CustomSpam: Object tag in html`|
|**HTML 内の Embed タグ** <br><br/> *MarkAsSpamEmbedTagsInHtml*|HTML タグを `<embed>` 含むメッセージは、信頼度の高いスパムとして指定されます。 <br/><br/> このタグを使用すると、HTML ドキュメント内にさまざまなデータ型 (サウンド、映画、画像など) のさまざまな種類のドキュメントを埋め込むことができます。|`X-CustomSpam: Embed tag in html`|
|**HTML 内の Form タグ** <br><br/> *MarkAsSpamFormTagsInHtml*|HTML タグを `<form>` 含むメッセージは、信頼度の高いスパムとしてマークされます。 <br/><br/> このタグは、Web サイトのフォームを作成するために使用されます。 広告メールには、受信者から情報を要求するために、このタグが含まれていることがよくあります。|`X-CustomSpam: Form tag in html`|
|**HTML 内の Web バグ** <br><br/> *MarkAsSpamWebBugsInHtml*|Web *バグ* (Web ビ *ーCン*とも呼ばれる) はグラフィック要素で (通常は 1 ピクセル x 1 ピクセル) で、メッセージが読み取されたかどうかを判別するためにメール メッセージで使用されます。 <br/><br/> Web バグを含むメッセージは、高信頼スパムとマークされます。 <br/><br/> 正当なニュースレターでは Web バグが使用されている場合がありますが、多くはプライバシーのインバスと見なします。 |`X-CustomSpam: Web bug`|
|**機密用語の適用** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft では、潜在的な不特定メッセージに関連付けられている動的で編集不可能な単語のリストを保持しています。 <br/><br/> 件名またはメッセージ本文の機密性の高い単語の一覧の単語を含むメッセージは、高信頼スパムとしてマークされます。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF レコード:Hard Fail** <br><br/> *MarkAsSpamSpfRecordHardFail*|送信元の電子メール ドメインについて、SPF の SPF Sender Policy Framework (SPF) レコードで指定されていない IP アドレスから送信されたメッセージは、信頼度の高いスパムとしてマークされます。 <br/><br/> この設定ではテスト モードを使用できません。|`X-CustomSpam: SPF Record Fail`|
|**条件付き Sender ID フィルター処理:Hard Fail** <br><br/> *MarkAsSpamFromAddressAuthFail*|条件付き Sender ID チェックでハード障害が発生したメッセージは、スパムとしてマークされます。 <br/><br/> この設定は SPF チェックと Sender ID チェックを組み合わせ、送信者の要求された送信者を含むメッセージ ヘッダーから保護します。 <br/><br/> この設定ではテスト モードを使用できません。|`X-CustomSpam: SPF From Record Fail`|
|**NDR バックスキャター** <br><br/> *MarkAsSpamNdrBackscatter*|*バックスキャターは、* メール メッセージ内の送信者を切り分けた送信者の原因となっている配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) です。 詳細については、バック [スキャター メッセージと EOP を参照してください](backscatter-messages-and-eop.md)。 <br/><br/> 次の環境では、この設定を構成する必要はありません。適当な NDR は配信され、バックスキャターはスパムとしてマークされるからです。 <ul><li>Microsoft 365 メールボックスを使用している Microsoft 365 組織。</li><li>送信電子メールを EOP 経由でルーティングする社内 *電子メール* 組織。</li></ul><br/> オンプレミスのメールボックスに受信メールを保護するスタンドアロン EOP 環境では、この設定を有効または無効にすると次の結果になります。 <ul><li> **:** 適度 NDR は配信され、バックスキャターはスパムとしてマークされます。</li><li>**オフ**: 正当な NDR とバックスキャターは通常のスパム フィルタリングを通じて行います。 最も問題の大きな NDR は、元のメッセージの送信者に配信されます。 すべてではありませんが、一部のバックスキャターは高信頼スパムとマークされます。 定義では、バックスキャターは、元の送信者には配信され、スプーフィングされた送信者にのみ配信できます。</li></ul><br/> この設定ではテスト モードを使用できません。|`X-CustomSpam: Backscatter NDR`|
|
