---
title: 365 セキュリティ設定に関する EOP と Defender Office Microsoft の推奨事項
keywords: Office 365 のセキュリティ推奨事項、Sender Policy Framework、ドメイン ベースのメッセージ報告と準拠、DomainKeys 識別メール、手順、動作方法、セキュリティ ベースライン、EOP のベースライン、Office 365 の Defender のベースライン、Office 365 の Defender のセットアップ、EOP のセットアップ、Defender の Office 365 の構成、EOP、セキュリティ構成の構成
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Exchange Online Protection (EOP) と Defender for Office 365 セキュリティ設定のベスト プラクティスは何ですか? 標準保護に関する現在の推奨事項は何ですか? より厳密にしたい場合は、何を使用する必要がありますか? また、Defender を 365 で使用する場合、どのようなOfficeしますか?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3a4447d6eaeeb907eb750d2ad668fdbb9031c28b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274870"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP と Microsoft Defender の 365 セキュリティOffice設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** は、Microsoft 365 サブスクリプションのセキュリティの中核であり、悪意のあるメールが従業員の受信トレイに届かされるのを防ごうのに役立ちます。 しかし、より高度な新しい攻撃が毎日出現する中で、多くの場合、保護の強化が必要になります。 **Microsoft Defender for Office 365** プラン 1 またはプラン 2 には、管理者にセキュリティ、制御、調査の層を追加する追加機能が含まれている。

セキュリティ管理者がセキュリティ設定をカスタマイズする権限を与える一方で、EOP と Microsoft Defender for Office 365 には、Standard と **Strict** の 2 つのセキュリティ レベルがあります。  各顧客の環境とニーズは異なりますが、これらのレベルのフィルター処理は、ほとんどの状況で望ましくないメールが従業員の受信トレイに届かされるのを防ぐのに役立つと考えています。

標準または厳密な設定をユーザーに自動的に適用するには、「EOP および Microsoft Defender for Office [365」を](preset-security-policies.md)参照してください。

> [!NOTE]
> フィルター処理が適切に機能するには、メールボックスで迷惑メール ルールを有効にする必要があります。 既定では有効になっていますが、フィルター処理が機能していないように見える場合は、チェックする必要があります。 詳細については、「[Office 365 で Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

この記事では、既定の設定と、ユーザーを保護するために推奨される Standard と Strict の設定について説明します。

> [!TIP]
> PowerShell Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) モジュールを使用すると、(管理者) これらの設定の現在の値を見つけるのに役立ちます。 具体的には **、Get-ORCAReport** コマンドレットは、スパム対策、フィッシング対策、その他のメッセージの衛生設定の評価を生成します。 ORCA モジュールは、 からダウンロードできます <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング対策の保護

スパム対策、マルウェア対策、フィッシング対策は、管理者が構成できる EOP 機能です。 次の標準構成または厳密な構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>「EOP のスパム対策ポリシーの設定」

スパム対策ポリシーを作成および構成するには [、「Configure anti-spam policies in Office 365」を参照してください](configure-your-spam-filter-policies.md)。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**スパム** 検出アクション <p> _SpamAction_|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|**信頼度の高いスパム** 検出アクション <p> _HighConfidenceSpamAction_|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**フィッシングメール検出** アクション <p> _PhishSpamAction_|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**信頼度の高いフィッシングメール検出** アクション <p> _HighConfidencePhishAction_|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**一括メール検出** アクション <p> _BulkSpamAction_|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|バルク メールのしきい値 <p> _BulkThreshold_|7|6|4|詳細については、「一括苦情[レベル (BCL)」を参照Office 365.](bulk-complaint-level-values.md)|
|検疫の保持期間 <p> _QuarantineRetentionPeriod_|15 日|30 日間|30 日間||
|**安全に関するヒント** <p> _InlineSafetyTipsEnabled_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|許可されている送信者 <p> _AllowedSenders_|なし|なし|なし||
|許可される送信者ドメイン <p> _AllowedSenderDomains_|なし|なし|なし|許可された送信者リストにドメインを追加すると、非常に悪い考えです。 攻撃者は、それ以外の場合はフィルター処理される電子メールを送信できます。 <p> [[スパム](learn-about-spoof-intelligence.md)対策の設定] ページの [セキュリティ &コンプライアンス センター] のスプーフィング インテリジェンスを使用して、組織のメール ドメイン内の送信者の電子メール アドレスをスプーフィングしているすべての送信者、または外部ドメインの送信者の電子メール アドレスをスプーフィングしているすべての送信者を確認します。|
|受信拒否の送信者 <p> _BlockedSenders_|なし|なし|なし||
|受信拒否ドメイン <p> _BlockedSenderDomains_|なし|なし|なし||
|**[エンド ユーザーのスパム通知を有効にする]**  このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。 <p> _EnableEndUserSpamNotifications_|無効 <p> `$false`|有効 <p> `$true`|有効 <p> `$true`||
|**エンド ユーザーのスパム通知を 1 日ごとに送信する** <p> _EndUserSpamNotificationFrequency_|3 日間|3 日間|3 日間||
|**スパム ZAP** <p> _SpamZapEnabled_|有効 <p> `$true`|有効 <p> `$true`|有効 <p> `$true`||
|**フィッシング ZAP** <p> _PhishZapEnabled_|有効 <p> `$true`|有効 <p> `$true`|有効 <p> `$true`||
|_MarkAsSpamBulkMail_|オン|オン|オン|この設定は PowerShell でのみ使用できます。|
|

スパム対策ポリシーには、非推奨のプロセスにある他のいくつかの高度なスパム フィルター (ASF) 設定があります。 これらの機能の減価償却のタイムラインの詳細については、この記事の外部で伝達されます。

標準レベルと厳密レベルの両方でこれらの ASF 設定 **を****オフにすることをお****勧** めします。 ASF 設定の詳細については、「Advanced [Spam Filter (ASF) settings in Office 365 」 を参照してください](advanced-spam-filtering-asf-options.md)。

<br>

****

|セキュリティ機能名|Comment|
|---|---|
|**リモート サイトへのイメージ リンク** (_IncreaseScoreWithImageLinks_)||
|**URL の数値 IP アドレス** (_IncreaseScoreWithNumericIps_)||
|**他のポートへの UL リダイレクト** (_IncreaseScoreWithRedirectToOtherPort_)||
|**.biz または .info Web** サイトへの URL (_IncreaseScoreWithBizOrInfoUrls_)||
|**空のメッセージ** (_MarkAsSpamEmptyMessages_)||
|**HTML の JavaScript または VBScript** (_MarkAsSpamJavaScriptInHtml_)||
|**HTML のフレームタグまたは IFrame** タグ (_MarkAsSpamFramesInHtml_)||
|**HTML のオブジェクト タグ** (_MarkAsSpamObjectTagsInHtml_)||
|**HTML にタグを埋** め込む (_MarkAsSpamEmbedTagsInHtml_)||
|**HTML のフォーム タグ** (_MarkAsSpamFormTagsInHtml_)||
|**HTML の Web バグ** (_MarkAsSpamWebBugsInHtml_)||
|**機密性の高い単語一覧** を適用する (_MarkAsSpamSensitiveWordList_)||
|**SPF レコード: ハードフェール** (_MarkAsSpamSpfRecordHardFail_)||
|**条件付き送信者 ID フィルター: ハード失敗** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパム ポリシー設定

送信スパム ポリシーを作成および構成するには [、「Configure outbound spam filtering in Office 365」を参照してください](configure-the-outbound-spam-policy.md)。

サービスの既定の送信制限の詳細については、「送信制限」 [を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**ユーザーあたりの最大受信者数: 外部時間制限** <p> _RecipientLimitExternalPerHour_|0|500|400|既定値 0 は、サービスの既定値を使用します。|
|**ユーザーあたりの最大受信者数: 内部時間制限** <p> _RecipientLimitInternalPerHour_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**ユーザーあたりの最大受信者数: 1 日の制限** <p> _RecipientLimitPerDay_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**ユーザーが制限を超えた場合のアクション** <p> _ActionWhenThresholdReached_|**メールの送信を次の日までユーザーに制限する** <p> `BlockUserForToday`|**ユーザーによるメールの送信を制限する** <p> `BlockUser`|**ユーザーによるメールの送信を制限する** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成および構成するには [、「Configure anti-malware policies in Office 365」を参照してください](configure-anti-malware-policies.md)。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**メッセージが検疫された場合、受信者に通知しますか?** <p> _Action_|いいえ <p> _DeleteMessage_|いいえ <p> _DeleteMessage_|いいえ <p> _DeleteMessage_|電子メールの添付ファイルでマルウェアが検出された場合、メッセージは検疫され、管理者だけが解放できます。|
|**共通の添付ファイルの種類フィルター** <p> _EnableFileFilter_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`|この設定は、添付ファイルの内容に関係なく、ファイルの種類に基づいて実行可能な添付ファイルを含むメッセージを検疫します。|
|**マルウェアゼロ時間自動削除** <p> _ZapEnabled_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**未配信メッセージの** 内部送信者に通知する <p> _EnableInternalSenderNotifications_|無効 <p> `$false`|無効 <p> `$false`|無効 <p> `$false`||
|**未配信メッセージの** 外部送信者に通知する <p> _EnableExternalSenderNotifications_|無効 <p> `$false`|無効 <p> `$false`|無効 <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP の既定のフィッシング対策ポリシー設定

これらの設定の詳細については、「スプーフィング設定」 [を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。 これらの設定を構成するには [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**スプーフィング対策の保護を有効にする** <p> _EnableSpoofIntelligence_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**認証されていない送信者を有効にする** <p> _EnableUnauthenticatedSender_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|不明なスプーフィングされた送信者の Outlook の送信者の写真に疑問符 (?) を追加します。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md)。|
|**ドメインのスプーフィングが許可されていないユーザーからメールが送信された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、スプーフィング インテリジェンスのブロックされた送信者 [に適用されます](learn-about-spoof-intelligence.md)。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 セキュリティ

その他のセキュリティ上の利点には、Microsoft Defender for Office 365 サブスクリプションがあります。 最新のニュースと情報については、「Defender for Office [365」を参照してください](whats-new-in-defender-for-office-365.md)。

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365 の既定のフィッシング対策ポリシー[](set-up-anti-phishing-policies.md#spoof-settings)は、すべての受信者にスプーフィング保護とメールボックス インテリジェンスを提供します。 ただし、既定のポリシーでは、[他の](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)利用可能[](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)な偽装保護機能と高度な設定が構成または有効になっていません。 すべての保護機能を有効にするには、既定のフィッシング対策ポリシーを変更するか、追加のフィッシング対策ポリシーを作成します。
>
> - 組織内のすべての受信者を自動的に保護する既定のセーフ リンク ポリシーや安全な添付ファイル ポリシーはありません。 保護を取得するには、少なくとも 1 つの安全なリンク ポリシーと安全な添付ファイル ポリシーを作成する必要があります。
>
> - [SharePoint、OneDrive、Microsoft Teams](mdo-for-spo-odb-and-teams.md)の保護と安全[](safe-docs.md)なドキュメント保護の安全な添付ファイルは、セーフ リンク ポリシーに依存します。

サブスクリプションに microsoft Defender for Office 365 が含まれる場合、または Office 365 の Defender をアドオンとして購入した場合は、次の Standard 構成または Strict 構成を設定します。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender for Office 365

EOP のお客様は、前述のように基本的なフィッシング対策を受け取りますが、microsoft Defender for Office 365 には、攻撃を防止、検出、修復するためのより多くの機能と制御が含まれています。 これらのポリシーを作成および構成するには [、「Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender のフィッシング対策ポリシーの偽装設定 (Office 365)

これらの設定の詳細については、「Microsoft Defender for microsoft Defender for Office [365」](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)の「偽装設定」を参照してください。 これらの設定を構成するには [、「Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|保護されたユーザー: **保護するユーザーを追加する** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|オフ <p> `$false` <p> none|オン <p> `$true` <p> \<list of users\>|オン <p> `$true` <p> \<list of users\>|組織によっては、主要な役割にユーザー (メッセージ送信者) を追加することをお勧めします。 内部的には、保護された送信者は、CEO、CFO、その他の上級リーダーである可能性があります。 外部的には、保護された送信者には、評議会のメンバーまたは取締役会が含まれる可能性があります。|
|保護されたドメイン: **所有するドメインを自動的に含める** <p> _EnableOrganizationDomainsProtection_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|保護されたドメイン: **カスタム ドメインを含める** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|オフ <p> `$false` <p> none|オン <p> `$true` <p> \<list of domains\>|オン <p> `$true` <p> \<list of domains\>|組織によっては、所有しているが頻繁に操作するドメイン (送信者ドメイン) を追加することをお勧めします。|
|保護されたユーザー: **偽装ユーザーから電子メールが送信される場合** <p> _TargetedUserProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|保護されたドメイン: **偽装ドメインからメールが送信される場合** <p> _TargetedDomainProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**偽装ユーザーのヒントを表示する** <p> _EnableSimilarUsersSafetyTips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**偽装ドメインのヒントを表示する** <p> _EnableSimilarDomainsSafetyTips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**異常な文字のヒントを表示する** <p> _EnableUnusualCharactersSafetyTips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メールボックス インテリジェンスを有効にする** <p> _EnableMailboxIntelligence_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**メールボックス インテリジェンスベースの偽装保護を有効にする** <p> _EnableMailboxIntelligenceProtection_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メールボックス インテリジェンスによって保護された偽装ユーザーによって電子メールが送信される場合** <p> _MailboxIntelligenceProtectionAction_|**アクションを適用しない** <p> `NoAction`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`||
|**信頼された差出人** <p> _ExcludedSenders_|なし|なし|なし|組織によっては、偽装のみのため、他のフィルターではなく、フィッシングとして誤ってマークされたユーザーを追加することをお勧めします。|
|**信頼済みドメイン** <p> _ExcludedDomains_|なし|なし|なし|組織によっては、偽装のみのため、他のフィルターではなく、フィッシングとして誤ってマークされるドメインを追加することをお勧めします。|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender のフィッシング対策ポリシーのスプーフィング設定 (Office 365)

これらは、EOP のスパム対策ポリシー設定で使用できるのと同 [じ設定です](#eop-anti-spam-policy-settings)。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|---|---|---|---|
|**スプーフィング対策の保護を有効にする** <p> _EnableSpoofIntelligence_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**認証されていない送信者を有効にする** <p> _EnableUnauthenticatedSender_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|不明なスプーフィングされた送信者の Outlook の送信者の写真に疑問符 (?) を追加します。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md)。|
|**ドメインのスプーフィングが許可されていないユーザーからメールが送信された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、スプーフィング インテリジェンスのブロックされた送信者 [に適用されます](learn-about-spoof-intelligence.md)。|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender for Office 365 のフィッシング対策ポリシーの詳細設定

この設定の詳細については、「Microsoft Defender for microsoft Defender for Office [365」](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)を参照してください。 この設定を構成するには [、「Defender for Office 365」を参照](configure-atp-anti-phishing-policies.md)してください。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**高度なフィッシングのしきい値** <p> _PhishThresholdLevel_|**1 - Standard** <p> `1`|**2 - アグレッシブ** <p> `2`|**3 - より積極的** <p> `3`||
|

### <a name="safe-links-settings"></a>セーフ リンクの設定

defender for Office 365 のセーフ リンクには、アクティブなセーフ リンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定と、各セーフ リンク ポリシーに固有の設定が含まれます。 詳細については、「Safe [Links in Defender for Office 365」を参照してください](safe-links.md)。

#### <a name="global-settings-for-safe-links"></a>セーフ リンクのグローバル設定

これらの設定を構成するには、「Defender for Office 365 のセーフ リンクのグローバル [設定を構成する」を参照してください](configure-global-settings-for-safe-links.md)。

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**安全なリンクを使用する: Office 365 アプリケーション** <p> _EnableSafeLinksForO365Clients_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|365 デスクトップおよびモバイル (iOS と Android) Officeサポートされているアプリで安全なリンクを使用します。 詳細については、「セーフ リンクの [設定」を参照Office 365 アプリを参照してください](safe-links.md#safe-links-settings-for-office-365-apps)。|
|**ユーザーが [安全なリンク] をクリックしても追跡しない** <p> _TrackClicks_|オン <p> `$false`|オフ <p> `$true`|オフ <p> `$true`|この設定をオフにすると _(TrackClicks_ に設定)、サポートされている 365 アプリのユーザークリック `$true` Office追跡します。|
|**ユーザーが元の URL への安全なリンクをクリックさせない** <p> _AllowClickThrough_|オン <p> `$false`|オン <p> `$false`|オン <p> `$false`|この設定 _(AllowClickThrough_ をに設定) をオンにすると、サポートされている 365 アプリで元の URL をクリックOffice `$false` 表示されません。|
|

#### <a name="safe-links-policy-settings"></a>セーフ リンク ポリシーの設定

これらの設定を構成するには、「Set up Safe [Links policies in Microsoft Defender for microsoft Defender for Office 365」を参照してください](set-up-safe-links-policies.md)。

PowerShell では、これらの設定に [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) コマンドレットと [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定のセーフ リンク ポリシーはありません。 [既定] 列の値は、作成する新しいセーフ リンク ポリシーの既定値です。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する** <p> _IsEnabled_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**Microsoft Teams 内の不明または潜在的に悪意のある URL のアクションを選択する** <p> _EnableSafeLinksForTeams_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する** <p> _ScanUrls_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メッセージを配信する前に URL のスキャンが完了するのを待ちます** <p> _DeliverMessageAfterScan_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**組織内で送信された電子メール メッセージに安全なリンクを適用する** <p> _EnableForInternalSenders_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**ユーザーのクリックを追跡しない** <p> _DoNotTrackUserClicks_|オフ <p> `$false`|オフ <p> `$false`|オフ <p> `$false`|この設定をオフにします _(DoNotTrackUserClicks_ を設定 `$false` ) は、ユーザーのクリックを追跡します。|
|**ユーザーに元の URL へのクリックを許可しない** <p> _DoNotAllowClickThrough_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`|この設定 _(DoNotAllowClickThrough_ をに設定) をオンにすると `$true` 、元の URL へのクリックスルーが禁止されます。|
|

### <a name="safe-attachments-settings"></a>安全な添付ファイルの設定

Microsoft Defender for Office 365 の安全な添付ファイルには、安全な添付ファイル ポリシーとの関係がないグローバル設定と、各セーフ リンク ポリシーに固有の設定が含まれます。 詳細については、「Safe [Attachments in Defender for Office 365」を参照してください](safe-attachments.md)。

#### <a name="global-settings-for-safe-attachments"></a>安全な添付ファイルのグローバル設定

これらの設定を構成するには [、「SharePoint、OneDrive、Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) の安全な添付ファイルを有効にする」および [「Microsoft 365 E5](safe-docs.md)の安全なドキュメント」を参照してください。

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**SharePoint、OneDrive、Microsoft Teams 用の Microsoft Defender for Office 365 を有効にする** <p> _EnableATPForSPOTeamsODB_|オン <p> `$true`|オン <p> `$true`||
|**クライアントの安全なドキュメントを有効Officeする** <p> _EnableSafeDocs_|オン <p> `$true`|オン <p> `$true`|この設定は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンスでのみ使用できます。 詳細については [、「Safe Documents in Microsoft Defender for Office 365」を参照してください](safe-docs.md)。|
|**安全なドキュメントがファイルを悪意のあるファイルとして識別した場合でも、保護されたビューをクリックするユーザーを許可する** <p> _AllowSafeDocsOpen_|オフ <p> `$false`|オフ <p> `$false`|この設定は、安全なドキュメントに関連しています。|
|

#### <a name="safe-attachments-policy-settings"></a>安全な添付ファイルポリシーの設定

これらの設定を構成するには [、「Defender for Office 365」を参照してください](set-up-safe-attachments-policies.md)。

PowerShell では、これらの設定に [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) コマンドレットと [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定の安全な添付ファイル ポリシーはありません。 [既定] 列の値は、作成する新しい安全な添付ファイル ポリシーの既定値です。

<br>

****

|セキュリティ機能名|既定値|標準|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**安全な添付ファイル不明のマルウェアの応答** <p> _Action_|ブロック <p> `Block`|ブロック <p> `Block`|ブロック <p> `Block`||
|**検出時に添付ファイルをリダイレクト** する: **リダイレクトを有効にする** <p> _リダイレクト_ <p> _RedirectAddress_|オフで、電子メール アドレスが指定されていません。 <p> `$true` <p> none|をオンにし、電子メール アドレスを指定します。 <p> `$true` <p> 電子メール アドレス|をオンにし、電子メール アドレスを指定します。 <p> `$true` <p> 電子メール アドレス|メッセージをセキュリティ管理者にリダイレクトして確認します。|
|**添付ファイルのマルウェア スキャンが時間切れまたはエラーが発生した場合は、上記の選択を適用します。** <p> _ActionOnError_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|

## <a name="related-articles"></a>関連記事

- Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) のベスト プラクティス **をお探し** ですか? [「Exchange Online でメール フロー ルールを構成するためのベスト プラクティス」を参照してください](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 管理者とユーザーは、誤検知 (良い電子メールが不良とマークされている) と誤検知 (悪いメールが許可されている) を分析のために Microsoft に提出できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- これらのリンクを使用して[、EOP](set-up-your-eop-service.md)サービスをセットアップし、Microsoft  Defender for Office [365 に設定します](defender-for-office-365.md)。  [「365」](protect-against-threats.md)の「脅威に対する保護」の役に立つOffice忘れないでください。

- **Windows** のセキュリティ基準については、GPO/オンプレミス [](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)オプションのセキュリティ 基準はどこで取得できますか、Intune ベースのセキュリティ用に Intune で [Windows 10](/intune/protect/security-baselines)デバイスを構成するには、セキュリティ 基準を使用します。 最後に、Microsoft Defender for Endpoint と Microsoft Intune のセキュリティ ベースラインの比較については、「Microsoft Defender for Endpoint と Windows Intune セキュリティ ベースラインの比較」 [を参照してください](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)。
