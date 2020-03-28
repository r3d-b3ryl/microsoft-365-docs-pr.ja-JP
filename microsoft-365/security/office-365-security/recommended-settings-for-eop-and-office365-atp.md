---
title: EOP および Office 365 に関する Microsoft の推奨事項、推奨事項、Sender Policy Framework、ドメインベースのメッセージの報告と適合性、DomainKeys で識別されたメール、手順、使用方法、セキュリティ基準、EOP のベースラインATP、段取り ATP、セットアップ EOP、ATP の構成、EOP、セキュリティ構成の構成
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Exchange Online Protection (EOP) と Advanced Threat Protection (ATP) のセキュリティ設定のベストプラクティスについて 標準保護に関する現在の推奨事項 より厳しくするには、何を使用する必要がありますか。 Advanced Threat Protection (ATP) も使用している場合、どのようなエクストラを利用できますか?
ms.openlocfilehash: 9ddf704f767dfa5ff5c93888e51b91b2079a6c43
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032854"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP および Office 365 の ATP セキュリティに関する推奨設定

**Exchange Online Protection (EOP)** は、Office 365 サブスクリプションのセキュリティの中核で、悪意のある電子メールが従業員の受信トレイに届かないようにするために使用されます。 しかし、毎日新しい高度な攻撃が発生すると、多くの場合、保護が強化されます。 **Office 365 Advanced Threat Protection (ATP)** ATP プラン1または ATP Plan 2 には、管理者によるセキュリティ、統制、調査の層をさらに強化する追加機能が含まれています。

セキュリティ管理者はセキュリティ設定をカスタマイズすることができますが、EOP と Office 365 ATP には、**標準**と**Strict**の2つのセキュリティレベルがあります。 お客様の環境とニーズは異なりますが、これらのレベルのメールフィルター構成は、ほとんどの状況で、不要なメールが従業員の受信トレイに届くことを防ぐために役立ちます。

> [!IMPORTANT]
> フィルター処理を正しく動作させるには、メールボックスで迷惑メールルールを有効にする必要があります。 これは既定で有効になっていますが、フィルターが機能していないように見える場合は、それをチェックする必要があります。 詳細については、「 [Office 365 の Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

このトピックでは、Office 365 ユーザーを保護するために Microsoft が推奨する設定について説明します。

> [!TIP]
> これらの設定の一部を決定するのに役立つ、Office 365 Advanced Threat Protection 推奨構成アナライザー (ORCA) と呼ばれる、ダウンロードできる新しい PowerShell モジュールがあります。 テナントで管理者として実行すると、ORCAReport はスパム対策、フィッシング、その他のメッセージの検疫設定の評価を作成するのに役立ちます。 このモジュールは、にhttps://www.powershellgallery.com/packages/ORCA/ダウンロードできます。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング対策保護

スパム対策、マルウェア対策、およびフィッシング対策は、管理者が構成できる EOP の機能です。 次の構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>EOP スパム対策ポリシーの設定

スパム対策ポリシーを作成して構成するには、「 [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

|||||
|---|---|---|---|
|**セキュリティ機能の名前**|**Standard**|**Strict**|**Comment**|
|**スパム**検出アクション <br/><br/> _SpamAction_|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**信頼度の高いスパム**検出アクション <br/><br/> _HighConfidenceSpamAction_|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**フィッシング電子メール**の検出アクション <br/><br/> _PhishSpamAction_|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**高信頼フィッシング電子メール**検出アクション <br/><br/> _HighConfidencePhishAction_|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**電子メールの一括**検出アクション <br/><br/> _BulkSpamAction_|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`||
|バルクメールのしきい値 <br/><br/> _BulkThreshold_|6 |4 |現在、既定値は7ですが、これは6に変更することをお勧めします。 詳細については、「 [Office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。|
|検疫の保存期間 <br/><br/> _QuarantineRetentionPeriod_|30 日間|30 日間||
|**安全性に関するヒント** <br/><br/> _InlineSafetyTipsEnabled_|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|許可された送信者 <br/><br/> _AllowedSenders_|なし|なし||
|許可される送信者ドメイン <br/><br/> _AllowedSenderDomains_|なし|なし|自分が所有する (_承認済みドメイン_とも呼ばれる) ドメインを許可された送信者の一覧に追加する必要はありません。 実際には、悪意のある俳優が、フィルターによって除外されるメールを送信するような機会を作成するため、高いリスクと見なされます。[**スパム対策設定**] ページの [セキュリティ & コンプライアンスセンター] で[スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)を使用して、組織の一部であるドメインを偽装している、または外部ドメインのスプーフィングを行っているすべての送信者を確認します。|
|受信拒否リスト <br/><br/> _BlockedSenders_|なし|なし||
|受信拒否された送信者ドメイン <br/><br/> _BlockedSenderDomains_|なし|なし||
|**[エンド ユーザーのスパム通知を有効にする]**  このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。 <br/><br/> _EnableEndUserSpamNotifications_|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`||
|**エンドユーザーのスパム通知を毎日送信する (日数)** <br/><br/> _EndUserSpamNotificationFrequency_|3 日間|3 日間||
|**スパム ZAP** <br/><br/> _SpamZapEnabled_|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`||
|**フィッシング ZAP** <br/><br/> _PhishZapEnabled_|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|オン|オン|この設定は、PowerShell でのみ使用できます。|
|

使用されなくなっているスパム対策ポリシーには、他にもいくつかの高度なスパムフィルター (ASF) 設定があります。 これらの機能の減価償却のタイムラインの詳細については、このトピックの外に連絡します。

**標準**レベルと**厳密**なレベルの両方で、これらの ASF 設定を**オフ**にすることをお勧めします。 ASF 設定の詳細については、「 [Office 365 の高度なスパムフィルター (ASF) 設定](advanced-spam-filtering-asf-options.md)」を参照してください。

|||
|----|---|
|**セキュリティ機能の名前**|**コメント**|
|**リモートサイトへの画像リンク**(_IncreaseScoreWithImageLinks_)||
|**URL の数値の IP アドレス**(_IncreaseScoreWithNumericIps_)||
|**UL リダイレクト (その他のポート**) (_IncreaseScoreWithRedirectToOtherPort_)||
|**.Url または info web サイトへの URL** (_IncreaseScoreWithBizOrInfoUrls_)||
|**空のメッセージ**(_MarkAsSpamEmptyMessages_)||
|**HTML の JavaScript または VBScript** (_MarkAsSpamJavaScriptInHtml_)||
|**HTML の Frame または IFrame タグ**(_MarkAsSpamFramesInHtml_)||
|**HTML のオブジェクトタグ**(_MarkAsSpamObjectTagsInHtml_)||
|**HTML にタグを埋め込む**(_MarkAsSpamEmbedTagsInHtml_)||
|**HTML の Form タグ**(_MarkAsSpamFormTagsInHtml_)||
|**HTML での Web バグ**(_MarkAsSpamWebBugsInHtml_)||
|**機密単語リストを適用**する (_MarkAsSpamSensitiveWordList_)||
|**SPF レコード: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**条件付き送信者 ID フィルター: hard fail** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR バック散布**(_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパムポリシーの設定

送信スパムポリシーを作成して構成するには、「 [Office 365 で送信スパムフィルターを構成](configure-the-outbound-spam-policy.md)する」を参照してください。

||||
|---|---|---|---|
|**セキュリティ機能の名前**|**Standard**|**Strict**|**Comment**|
|**ユーザーあたりの最大受信者数: 外部時間の制限** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**ユーザーあたりの最大受信者数: 内部時間の制限** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**ユーザーあたりの最大受信者数: 毎日の制限** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**ユーザーが制限を超えた場合のアクション** <br/><br/> _ActionWhenThresholdReached_|**ユーザーがメールを送信するのを制限する** <br/><br/> `BlockUser`|**ユーザーがメールを送信するのを制限する** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成して構成するには、「 [configure マルウェア対策ポリシーを Office 365 で構成](configure-anti-malware-policies.md)する」を参照してください。

|||||
|---|---|---|---|
|**セキュリティ機能の名前**|**Standard**|**Strict**|**Comment**|
|**受信者にメッセージが検疫されたことを通知するかどうか。** <br/><br/> _操作_|いいえ <br/><br/> _DeleteMessage_|いいえ <br/><br/> _DeleteMessage_|電子メールの添付ファイルでマルウェアが検出されると、メッセージは検疫され、管理者のみが解放できるようになります。|
|**一般的な添付ファイルの種類のフィルター** <br/><br/> _EnableFileFilter_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|この設定では、添付ファイルの内容に関係なく、実行可能な添付ファイルが含まれているファイルの種類に基づいてメッセージを検疫します。|
|**マルウェアのゼロ時間の自動削除** <br/><br/> _ZapEnabled_|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|配信されていないメッセージの**内部送信者に通知**する <br/><br/> _EnableInternalSenderNotifications_|無効 <br/><br/> `$false`|無効 <br/><br/> `$false`||
|配信されていないメッセージの**外部送信者に通知**する <br/><br/> _EnableExternalSenderNotifications_|無効 <br/><br/> `$false`|無効 <br/><br/> `$false`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP フィッシング対策ポリシー設定

|セキュリティ機能の名前|標準|Strict|コメント|
|---------|---------|---------|---------|
|スプーフィング対策保護を有効にする|オン|オン||
|認証されていない送信者を有効にする (タグ付け)|オン|オン||
|ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信された場合|受信者の迷惑メールフォルダーにメッセージを移動する|メッセージを検疫する||

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 Advanced Threat Protection セキュリティ

その他のセキュリティ上の利点には、Office 365 Advanced Threat Protection (ATP) サブスクリプションが付属しています。 最新のニュースと情報については、「 [Office 365 ATP の新機能](whats-new-in-office-365-atp.md)」を参照してください。

Office 365 ATP には、悪意のある添付ファイルを含む電子メールを配信できないようにする安全な添付ファイルおよび安全なリンクのポリシーが含まれており、ユーザーは安全でない可能性のある Url をクリックすることになります。

> [!IMPORTANT]
> 高度なフィッシング対策は、Office 365 ATP サブスクリプションの利点の1つです。 既定では有効になっていますが、メールのフィルターを開始する前に、少なくとも1つのフィッシング対策ポリシーを構成***する必要があり***ます。 フィッシング対策ポリシーの構成を忘れると、ユーザーが危険な電子メールに公開される可能性があります。 Office 365 ATP サブスクリプションを追加した後は、必ずフィッシング対策ポリシーを構成してください。

EOP に Office 365 ATP サブスクリプションを追加した場合は、次の構成を設定します。

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP のフィッシング対策ポリシー設定

EOP のお客様は、前述したように基本的なフィッシング対策を行いますが、Office 365 ATP には、攻撃を防止、検出、修復するのに役立つ機能と制御が追加されています。

|偽装セキュリティ機能の名前|標準|Strict|コメント|
|---------|---------|---------|---------|
|(偽装ポリシーの編集)保護するユーザーを追加する|オン|オン|組織によって異なりますが、主要な役割でユーザーを追加することをお勧めします。 内部的には、CEO、CFO、その他のシニアリーダーである可能性があります。 外部には、協議会のメンバーまたは取締役会を含めることができます。|
|(偽装ポリシーの編集)自分が所有しているドメインを自動的に追加する|オン|オン||
|(偽装ポリシーの編集)カスタムドメインを含める|オン|オン|組織によって異なりますが、自分が所有していない大部分のドメインを追加することをお勧めします。|
|指定した偽装ユーザーによって電子メールが送信された場合|メッセージを検疫する|メッセージを検疫する||
|指定した偽装ドメインによって電子メールが送信される場合|メッセージを検疫する|メッセージを検疫する||
|偽装ユーザーのヒントを表示する|オン|オン||
|偽装ドメインのヒントを表示する|オン|オン||
|通常と異なる文字にヒントを表示する|オン|オン||
|メールボックスインテリジェンスを有効にする|オン|オン||
|メールボックスインテリジェンスベースの偽装保護を有効にする|オン|オン||
|メールボックスインテリジェンスで保護された偽装ユーザーによって電子メールが送信される場合|受信者の迷惑メールフォルダーにメッセージを移動する|メッセージを検疫する||
|(偽装ポリシーの編集)信頼できる差出人とドメインを追加する|なし|なし|組織によって異なりますが、誤ってフィッシングとしてマークされるユーザーまたはドメインを追加することをお勧めします。|

|スプーフィングセキュリティ機能の名前|標準|Strict|コメント|
|---------|---------|---------|---------|
|スプーフィング対策保護を有効にする|オン|オン||
|認証されていない送信者を有効にする (タグ付け)|オン|オン||
|ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信された場合|受信者の迷惑メールフォルダーにメッセージを移動する|メッセージを検疫する||
|EnableSuspiciousSafetyTip|False|True|この設定は、PowerShell でのみ使用できます。|
|TreatSoftPassAsAuthenticated|True|False|この設定は、PowerShell でのみ使用できます。|


|詳細設定のセキュリティ機能の名前|標準|Strict|コメント|
|---------|---------|---------|---------|
|高度なフィッシングしきい値|2-アグレッシブ|3つ以上のアグレッシブ||

### <a name="safe-links-settings"></a>安全なリンクの設定

|セキュリティ機能の名前|標準|Strict|コメント|
|---------|---------|---------|---------|
|Office 365 アプリの ATP Safe Links、Office for iOS、および Android を使用する|有効|有効|これは、組織全体に適用される ATP の安全なリンクポリシーに該当します。|
ユーザーが [安全なリンク] をクリックしたときに追跡しない|無効|無効|これは、組織全体に適用されるポリシーと、特定の受信者に適用されるポリシーの両方に適用されます。|
|ユーザーが元の URL への安全なリンクをクリックできないようにする|有効|有効|これは、組織全体に適用されるポリシーと特定の受信者に適用されるポリシーの両方に適用されます。|
|メッセージ内の不明な潜在的な悪意のある Url に対するアクション|オン|オン||
|疑わしいリンクおよびファイルを指すリンクのリアルタイム URL スキャンを適用する|有効|有効||
|メッセージを配信する前に URL スキャンが完了するまで待機する|有効|有効||
|組織内で送信される電子メールメッセージに安全なリンクを適用する|有効|有効||

### <a name="safe-attachments"></a>添付ファイル保護

|セキュリティ機能の名前|標準|Strict|コメント|
|---------|---------|---------|---------|
|SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする|有効|有効||
|ATP の安全な添付ファイルの不明なマルウェア応答|Block|Block||
|検出時に添付ファイルをリダイレクトする|有効|有効|添付ファイルがマルウェアであるかどうかを判断する方法を把握しているセキュリティ管理者の電子メールアドレスにリダイレクトする|
|添付ファイルのマルウェアスキャンがタイムアウトまたはエラーが発生した場合の、ATP の安全な添付ファイル応答|有効|有効||

## <a name="related-topics"></a>関連項目

- **Exchange メールフロー/Exchange トランスポートルール**のベストプラクティスについては、こちらを参照してください。 詳細については、[この記事](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop)を参照してください。

- 管理者とユーザーは、誤検知 (不良としてマークされている正常なメール) と誤検知 (無効な電子メールを許可) を分析のために Microsoft に送信できます。 詳細については、「 [Microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- [EOP サービス](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)を**セットアップする方法**、および[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)を**構成**する方法に関する情報については、次のリンクを使用してください。 (「[365 Office での脅威からの保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」にある、役に立つ指示を参照してください。

- [この記事](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)では、GPO/オンプレミスのオプション、および Intune ベースのセキュリティについては、[ここ](https://docs.microsoft.com/intune/protect/security-baselines)に記載されている**Windows のセキュリティベースライン**について説明します。 最後に、Microsoft Defender Advanced Threat Protection (ATP) と Windows Intune セキュリティベースラインの比較は[こちらで](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)ご覧いただけます。
