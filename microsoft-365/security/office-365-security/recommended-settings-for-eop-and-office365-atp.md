---
title: 365 セキュリティ設定に関する EOP Office Defender に関する Microsoft の推奨事項
keywords: Office 365 のセキュリティ推奨事項、Sender Policy Framework、ドメイン ベースのメッセージ報告と準拠、DomainKeys Identified Mail、手順、動作方法、セキュリティベースライン、EOP のベースライン、Office 365 用 Defender のベースライン、Office 365 用 Defender のセットアップ、EOP のセットアップ、Office 365 用の Defender の構成、EOP、セキュリティ構成の構成
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Exchange Online Protection (EOP) および Defender for Office 365 セキュリティ設定のベスト プラクティスは何ですか? 標準的な保護に関する現在の推奨事項は何ですか? より厳しくしたい場合は、何を使用する必要がありますか。 また、Defender を 365 用に使用する場合、どのようなOfficeがありますか?
ms.openlocfilehash: c9a9774e0866b009965eeb574384095c26fa780e
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760232"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP と Microsoft Defender の 365 セキュリティOffice推奨設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** は、Microsoft 365 サブスクリプションのセキュリティの中核であり、悪意のあるメールが従業員の受信トレイに届かされるのを防きます。 しかし、より高度な新しい攻撃が毎日出現する中、多くの場合、強化された保護が必要になります。 **Microsoft Defender for Office 365** プラン 1 またはプラン 2 には、管理者にセキュリティ、制御、調査のレイヤーを強化する追加機能が含まれている。

セキュリティ管理者はセキュリティ設定をカスタマイズすることができますが、推奨される Office 365 の EOP と Microsoft Defender には **、Standard** と **Strict** の 2 つのセキュリティ レベルがあります。 お客様の環境とニーズは異なりますが、これらのレベルのフィルタリングは、ほとんどの状況で不要なメールが従業員の受信トレイに届くのを防ぐのに役立ちます。

標準または厳密な設定をユーザーに自動的に適用するには、EOP および Microsoft Defender for [Office 365](preset-security-policies.md)の事前設定のセキュリティ ポリシーを参照してください。

> [!NOTE]
> フィルター処理が正しく機能するには、メールボックスで迷惑メール ルールを有効にする必要があります。 既定では有効になっていますが、フィルター処理が機能していないと思われる場合はチェックする必要があります。 詳細については、「[Office 365 で Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

この記事では、既定の設定と、ユーザーを保護するために推奨される [標準] および [厳密] の設定について説明します。

> [!TIP]
> PowerShell Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) モジュールを使用すると、(管理者) これらの設定の現在の値を見つけるのに役立ちます。 具体的には **、Get-ORCAReport** コマンドレットは、スパム対策、フィッシング対策、その他のメッセージ検疫設定の評価を生成します。 ORCA モジュールは、以下からダウンロードできます <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング対策の保護

スパム対策、マルウェア対策、フィッシング詐欺対策は、管理者が構成できる EOP 機能です。 次の Standard または Strict 構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>「EOP のスパム対策ポリシーの設定」

スパム対策ポリシーを作成して構成するには、「Office [365](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**スパム検出** アクション <p> _SpamAction_|**メッセージを [迷惑メール] フォルダーに移動する** <p> `MoveToJmf`|**メッセージを [迷惑メール] フォルダーに移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`||
|**信頼度の高いスパム** 検出アクション <p> _HighConfidenceSpamAction_|**メッセージを [迷惑メール] フォルダーに移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**フィッシング メール検出** アクション <p> _PhishSpamAction_|**メッセージを [迷惑メール] フォルダーに移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**信頼度の高いフィッシングメール** 検出アクション <p> _HighConfidencePhishAction_|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**バルク メール検出** アクション <p> _BulkSpamAction_|**メッセージを [迷惑メール] フォルダーに移動する** <p> `MoveToJmf`|**メッセージを [迷惑メール] フォルダーに移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`||
|バルク メールのしきい値 <p> _BulkThreshold_|7 |6 |4 |詳細については、第 365 条の「バルク苦情 [レベル (BCL)」Office覧ください](bulk-complaint-level-values.md)。|
|検疫の保存期間 <p> _QuarantineRetentionPeriod_|15 日|30 日間|30 日間||
|**安全性のヒント** <p> _InlineSafetyTipsEnabled_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|許可された送信者 <p> _AllowedSenders_|なし|なし|なし||
|許可された送信者ドメイン <p> _AllowedSenderDomains_|なし|なし|なし|許可された送信者の一覧にドメインを追加する方法は、非常に悪い考えです。 攻撃者は、それ以外の場合はフィルタリングされる電子メールを送信できます。 <p> [[](learn-about-spoof-intelligence.md)スパム対策の設定] ページのセキュリティ & コンプライアンスセンターでスプーフィング インテリジェンスを使用して、組織の電子メール ドメイン内の送信者の電子メール アドレスをスプーフィングしているすべての送信者、または外部ドメインのスプーフィング送信者の電子メール アドレスを確認します。|
|受信拒否リスト <p> _BlockedSenders_|なし|なし|なし||
|受信拒否ドメイン <p> _BlockedSenderDomains_|なし|なし|なし||
|**[エンド ユーザーのスパム通知を有効にする]**  このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。 <p> _EnableEndUserSpamNotifications_|無効 <p> `$false`|有効 <p> `$true`|有効 <p> `$true`||
|**エンドユーザーのスパム通知を毎日送信する** <p> _EndUserSpamNotificationFrequency_|3 日間|3 日間|3 日間||
|**スパム ZAP** <p> _SpamZapEnabled_|有効 <p> `$true`|有効 <p> `$true`|有効 <p> `$true`||
|**フィッシング ZAP** <p> _PhishZapEnabled_|有効 <p> `$true`|有効 <p> `$true`|有効 <p> `$true`||
|_MarkAsSpamBulkMail_|オン|オン|オン|この設定は PowerShell でのみ使用できます。|
|

他にも、非推奨にされているスパム対策ポリシーには、高度なスパム フィルター (ASF) の設定がいくつかあります。 これらの機能の減価償却費のタイムラインに関する詳細については、この記事の外部で伝達されます。

これらの ASF 設定は、Standardレベルと Strict レベルの両方でオフ **に** することをお **勧** めします。 ASF 設定の詳細については、Office 365 の「高度なスパム フィルター [(ASF) 設定](advanced-spam-filtering-asf-options.md)」を参照してください。

****

|セキュリティ機能名|コメント|
|---|---|
|**リモート サイトへの画像リンク** (_IncreaseScoreWithImageLinks_)||
|**URL の数値 IP アドレス** (_IncreaseScoreWithNumericIps_)||
|**他のポートへの UL** リダイレクト (_IncreaseScoreWithRedirectToOtherPort_)||
|**.biz または .info Web サイト** への URL (_IncreaseScoreWithBizOrInfoUrls_)||
|**空のメッセージ** (_MarkAsSpamEmptyMessages_)||
|**HTML の JavaScript または VBScript** (_MarkAsSpamJavaScriptInHtml_)||
|**HTML の Frame タグまたは IFrame** タグ (_MarkAsSpamFramesInHtml_)||
|**HTML のオブジェクト タグ** (_MarkAsSpamObjectTagsInHtml_)||
|**HTML 内の埋め** 込みタグ (_MarkAsSpamEmbedTagsInHtml_)||
|**HTML のフォーム タグ** (_MarkAsSpamFormTagsInHtml_)||
|**HTML の Web バグ** (_MarkAsSpamWebBugsInHtml_)||
|**機密単語の一覧を適用** する (_MarkAsSpamSensitiveWordList_)||
|**SPF レコード: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**条件付き送信者 ID フィルター: hard fail** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR バックスカター** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパム ポリシー設定

送信スパム ポリシーを作成して構成するには、「Configure [outbound spam filtering in Office 365](configure-the-outbound-spam-policy.md)」を参照してください。

サービスの既定の送信制限の詳細については、「送信の制限」 [を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**ユーザーあたりの最大受信者数: 外部時間制限** <p> _RecipientLimitExternalPerHour_|0|500|400|既定値 0 は、サービスの既定値を使用します。|
|**ユーザーあたりの最大受信者数: 内部時間制限** <p> _RecipientLimitInternalPerHour_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**ユーザーあたりの最大受信者数: 1 日あたりの制限** <p> _RecipientLimitPerDay_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**ユーザーが制限を超えた場合のアクション** <p> _ActionWhenThresholdReached_|**次の日までメールを送信するユーザーを制限する** <p> `BlockUserForToday`|**ユーザーによるメールの送信を制限する** <p> `BlockUser`|**ユーザーによるメールの送信を制限する** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成して構成するには、「Office [365](configure-anti-malware-policies.md)でマルウェア対策ポリシーを構成する」を参照してください。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**受信者のメッセージが検疫された場合に受信者に通知しますか?** <p> _操作_|いいえ <p> _DeleteMessage_|いいえ <p> _DeleteMessage_|いいえ <p> _DeleteMessage_|電子メールの添付ファイルでマルウェアが検出された場合、メッセージは検疫され、管理者だけが解放できます。|
|**一般的な添付ファイルの種類のフィルター** <p> _EnableFileFilter_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`|この設定は、添付ファイルの内容に関係なく、ファイルの種類に基づいて実行可能な添付ファイルを含むメッセージを検疫します。|
|**マルウェアゼロアワー自動消去** <p> _ZapEnabled_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**未配信のメッセージ** を内部送信者に通知する <p> _EnableInternalSenderNotifications_|無効 <p> `$false`|無効 <p> `$false`|無効 <p> `$false`||
|**未配信のメッセージ** を外部送信者に通知する <p> _EnableExternalSenderNotifications_|無効 <p> `$false`|無効 <p> `$false`|無効 <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP の既定のフィッシング対策ポリシー設定

これらの設定の詳細については、「スプーフィング設定」 [を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。 これらの設定を構成するには [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**スプーフィング対策保護を有効にする** <p> _EnableSpoofIntelligence_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**認証されていない送信者を有効にする** <p> _EnableUnauthenticatedSender_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|不明なスプーフィングされた送信者の Outlook の送信者の写真に疑問符 (?) を追加します。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md)。|
|**ドメインのスプーフィングが許可されていないユーザーからメールが送信された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、スプーフィング インテリジェンスのブロックされた送信者 [に適用されます](learn-about-spoof-intelligence.md)。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 セキュリティ

追加のセキュリティ上の利点は、Microsoft Defender for Office 365 サブスクリプションに適用されます。 最新のニュースと情報については、Defender for Office [365](whats-new-in-office-365-atp.md)の新機能をご覧ください。

> [!IMPORTANT]
>
> - Office 365 用 Microsoft Defender の既定のフィッシング対策ポリシー[](set-up-anti-phishing-policies.md#spoof-settings)は、すべての受信者にスプーフィング保護とメールボックス インテリジェンスを提供します。 ただし、その他の利用可能な [偽装保護](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 機能と [詳細設定](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) は、既定のポリシーでは構成または有効化されていません。 すべての保護機能を有効にするには、既定のフィッシング対策ポリシーを変更するか、追加のフィッシング対策ポリシーを作成します。
>
> - 組織内のすべての受信者を自動的に保護する既定の安全なリンク ポリシーや安全な添付ファイル ポリシーはありません。 保護を取得するには、少なくとも 1 つの安全なリンク ポリシーと安全な添付ファイル ポリシーを作成する必要があります。
>
> - [SharePoint、OneDrive、および Microsoft Teams](atp-for-spo-odb-and-teams.md) の保護と [安全](safe-docs.md) なドキュメント保護用の ATP は、安全なリンク ポリシーに依存します。

サブスクリプションに Office 365 用の Microsoft Defender が含まれる場合、または Office 365 の Defender をアドオンとして購入した場合は、次の Standard または Strict 構成を設定します。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシー設定

EOP のお客様は、前述のように基本的なフィッシング詐欺対策を受け取りますが、Microsoft Defender for Office 365 には、攻撃を防止、検出、修復するためのより多くの機能と制御が含まれています。 これらのポリシーを作成して構成するには、「Defender でフィッシング詐欺対策ポリシーを構成する(Office [365)」を参照](configure-atp-anti-phishing-policies.md)してください。

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーの偽装設定

これらの設定について詳しくは、「Microsoft Defender for Office 365 のフィッシング対策ポリシーの [偽装設定」をご覧](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)ください。 これらの設定を構成するには、「Defender でフィッシング詐欺対策ポリシーを構成する(Office [365)」を参照](configure-atp-anti-phishing-policies.md)してください。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|保護されたユーザー: 保護 **するユーザーを追加する** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|オフ <p> `$false` <p> なし|オン <p> `$true` <p> \<list of users\>|オン <p> `$true` <p> \<list of users\>|組織によっては、主要な役割にユーザー (メッセージ送信者) を追加することをお勧めします。 内部的には、保護された送信者は、CEO、CFO、その他の上級リーダーである可能性があります。 外部では、保護された送信者には、会議メンバーまたはお客様の役員が含まれる場合があります。|
|保護されたドメイン: **所有しているドメインを自動的に含める** <p> _EnableOrganizationDomainsProtection_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|保護されたドメイン: **カスタム ドメインを含める** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|オフ <p> `$false` <p> なし|オン <p> `$true` <p> \<list of domains\>|オン <p> `$true` <p> \<list of domains\>|組織によっては、所有しているが、頻繁にやり取りするドメイン (送信者ドメイン) を追加することをお勧めします。|
|保護されたユーザー: **偽装されたユーザーによって電子メールが送信される場合** <p> _TargetedUserProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|保護されたドメイン: **偽装されたドメインによって電子メールが送信される場合** <p> _TargetedDomainProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**偽装ユーザーのヒントを表示する** <p> _EnableSimilarUsersSafetyTips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**偽装ドメインのヒントを表示する** <p> _EnableSimilarDomainsSafetyTips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**通常と異なっている文字のヒントを表示する** <p> _EnableUnusualCharactersSafetyTips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メールボックス インテリジェンスを有効にする** <p> _EnableMailboxIntelligence_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**メールボックス インテリジェンス ベースの偽装保護を有効にする** <p> _EnableMailboxIntelligenceProtection_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メールボックス インテリジェンスによって保護された偽装ユーザーによって電子メールが送信される場合** <p> _MailboxIntelligenceProtectionAction_|**アクションを適用しない** <p> `NoAction`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`||
|**信頼された差出人** <p> _ExcludedSenders_|なし|なし|なし|組織によっては、偽装のみのためフィッシングとして誤ってマークされるユーザーを追加することをお勧めします。他のフィルターは追加しません。|
|**信頼済みドメイン** <p> _ExcludedDomains_|なし|なし|なし|組織によっては、偽装のみのためフィッシングとして誤ってマークされるドメインを追加することをお勧めします。他のフィルターは追加しません。|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーのスプーフィング設定

これらは、EOP のスパム対策ポリシー設定 [で使用可能な設定と同じ設定です](#eop-anti-spam-policy-settings)。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|---|---|---|---|
|**スプーフィング対策保護を有効にする** <p> _EnableSpoofIntelligence_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**認証されていない送信者を有効にする** <p> _EnableUnauthenticatedSender_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|不明なスプーフィングされた送信者の Outlook の送信者の写真に疑問符 (?) を追加します。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md)。|
|**ドメインのスプーフィングが許可されていないユーザーからメールが送信された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、スプーフィング インテリジェンスのブロックされた送信者 [に適用されます](learn-about-spoof-intelligence.md)。|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーの詳細設定

この設定について詳しくは、Microsoft Defender for Office [365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)のフィッシング対策ポリシーの高度なフィッシングしきい値をご覧ください。 この設定を構成するには [、「Defender for Office 365](configure-atp-anti-phishing-policies.md)でのフィッシング詐欺対策ポリシーの構成」を参照してください。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**高度なフィッシングのしきい値** <p> _PhishThresholdLevel_|**1 - 標準** <p> `1`|**2 - 積極的** <p> `2`|**3 - より積極的** <p> `3`||
|

### <a name="safe-links-settings"></a>安全なリンクの設定

defender for Office 365 の安全なリンクには、アクティブな安全なリンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定と、各安全なリンク ポリシーに固有の設定が含まれます。 詳細については [、「Defender 365 の安全なリンク」をOfficeしてください](atp-safe-links.md)。

#### <a name="global-settings-for-safe-links"></a>安全なリンクのグローバル設定

これらの設定を構成するには、「Defender で安全なリンクのグローバル設定を構成する(Office [365)」を参照](configure-global-settings-for-safe-links.md)してください。

PowerShell では、これらの設定に [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**安全なリンクの使用: Office 365 アプリケーション** <p> _EnableSafeLinksForO365Clients_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|サポートされている 365 デスクトップOffice (iOS および Android) アプリで安全なリンクを使用します。 詳細については、「365 アプリの安全なリンク [設定Office参照してください](atp-safe-links.md#safe-links-settings-for-office-365-apps)。|
|**ユーザーが [安全なリンク] をクリックしても追跡しない** <p> _TrackClicks_|オン <p> `$false`|オフ <p> `$true`|オフ <p> `$true`|この設定をオフにする _(TrackClicks_ を設定する) と、サポートされている `$true` 365 アプリOfficeを追跡します。|
|**ユーザーが元の URL への安全なリンクをクリックさせない** <p> _AllowClickThrough_|オン <p> `$false`|オン <p> `$false`|オン <p> `$false`|この設定 _(AllowClickThrough を AllowClickThrough_ に設定) をオンにすると、サポートされている 365 アプリの元の `$false` URL Officeクリックスルーされません。|
|

#### <a name="safe-links-policy-settings"></a>安全なリンクのポリシー設定

これらの設定を構成するには、「Microsoft Defender で安全なリンク ポリシーをセットアップする(Office [365)」を参照](set-up-atp-safe-links-policies.md)してください。

PowerShell では、これらの設定に [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) コマンドレットと [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定の安全なリンク ポリシーはありません。 [既定] 列の値は、作成する新しい安全なリンク ポリシーの既定値です。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**メッセージ内の悪意のある可能性のある不明な URL のアクションを選択する** <p> _IsEnabled_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**Microsoft Teams 内の不明な URL または悪意のある可能性のある URL のアクションを選択する** <p> _EnableSafeLinksForTeams_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**ファイルを指す疑わしいリンクやリンクのリアルタイム URL スキャンを適用する** <p> _ScanUrls_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メッセージを配信する前に URL のスキャンが完了するのを待つ** <p> _DeliverMessageAfterScan_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**組織内で送信される電子メール メッセージに安全なリンクを適用する** <p> _EnableForInternalSenders_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**ユーザーのクリックを追跡しない** <p> _DoNotTrackUserClicks_|オフ <p> `$false`|オフ <p> `$false`|オフ <p> `$false`|この設定 _(DoNotTrackUserClicks_ を設定) をオフにすると、ユーザーの `$false` クリックが追跡されます。|
|**ユーザーがクリックスルーして元の URL にアクセスできない** <p> _DoNotAllowClickThrough_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`|この設定 _(DoNotAllowClickThrough_ を設定) をオンにすると、元の URL へのクリック `$true` スルーが禁止されます。|
|

### <a name="safe-attachments-settings"></a>安全な添付ファイルの設定

Office 365 用 Microsoft Defender の安全な添付ファイルには、安全な添付ファイル ポリシーと関係がないグローバル設定と、各安全なリンク ポリシーに固有の設定が含まれます。 詳細については [、「Defender 365 の安全な添付ファイル」Office参照してください](atp-safe-attachments.md)。

#### <a name="global-settings-for-safe-attachments"></a>安全な添付ファイルのグローバル設定

これらの設定を構成するには [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) の ATP と [Microsoft 365 E5](safe-docs.md)の安全なドキュメントを有効にする」を参照してください。

PowerShell では、これらの設定に [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする** <p> _EnableATPForSPOTeamsODB_|オン <p> `$true`|オン <p> `$true`||
|**クライアントの安全なドキュメントをOfficeする** <p> _EnableSafeDocs_|オン <p> `$true`|オン <p> `$true`|この設定は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンスでのみ使用できます。 詳細については [、「Microsoft Defender の安全なドキュメント(Office 365)」を参照](safe-docs.md)してください。|
|**安全なドキュメントでファイルが悪意のあるものとして識別された場合でも、ユーザーが保護ビューをクリックできる** <p> _AllowSafeDocsOpen_|オフ <p> `$false`|オフ <p> `$false`|この設定は、安全なドキュメントに関連しています。|
|

#### <a name="safe-attachments-policy-settings"></a>安全な添付ファイルポリシーの設定

これらの設定を構成するには、「Defender で安全な添付ファイル ポリシーをセットアップする(Office [365)」を参照](set-up-atp-safe-attachments-policies.md)してください。

PowerShell では、これらの設定に [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) コマンドレットと [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定の安全な添付ファイル ポリシーはありません。 [既定] 列の値は、新しく作成した安全な添付ファイル ポリシーの既定値です。

****

|セキュリティ機能名|既定値|標準|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**「安全な添付ファイル」の不明なマルウェアの応答** <p> _操作_|ブロック <p> `Block`|ブロック <p> `Block`|ブロック <p> `Block`||
|**検出時に添付ファイルをリダイレクト** する: **リダイレクトを有効にする** <p> _リダイレクト_ <p> _RedirectAddress_|オフ。電子メール アドレスは指定されていません。 <p> `$true` <p> なし|オンにし、メール アドレスを指定します。 <p> `$true` <p> メール アドレス|オンにし、メール アドレスを指定します。 <p> `$true` <p> メール アドレス|確認のためにメッセージをセキュリティ管理者にリダイレクトします。|
|**添付ファイルのマルウェア スキャンがタイム アウトした場合やエラーが発生した場合は、上記の選択を適用します。** <p> _ActionOnError_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|

## <a name="related-articles"></a>関連記事

- Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) のベスト **プラクティスをお探しの** 場合 [Exchange Online でメール フロー ルールを構成するためのベスト プラクティスを参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 管理者とユーザーは、分析のために誤検知 (良いメールが悪いとマークされている) と偽陰性 (許可された悪いメール) を Microsoft に送信できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- [EOP](set-up-your-eop-service.md)サービスのセットアップ方法、および[365 年 365](office-365-atp.md)日に Microsoft Defender を構成する方法については、次Officeしてください。 [「365 年 365](protect-against-threats.md)日の脅威から保護する」の役立つOffice忘れないでください。

- **Windows** のセキュリティベースラインは、次の場所にあります。セキュリティベースラインはどこで取得できますか [?GPO/](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) オンプレミス オプションの場合、セキュリティベースラインを使用して Intune で Intune ベースのセキュリティ用に [Windows 10](https://docs.microsoft.com/intune/protect/security-baselines) デバイスを構成します。 最後に、Microsoft Defender for Endpoint と Microsoft Intune のセキュリティベースラインの比較については [、「Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)と Windows Intune のセキュリティベースラインを比較する」を参照してください。
