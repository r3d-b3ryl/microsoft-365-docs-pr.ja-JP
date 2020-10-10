---
title: EOP および Office 365 に関する Microsoft の推奨事項、推奨事項、Sender Policy Framework、ドメインベースのメッセージの報告と適合性、DomainKeys で識別されたメール、手順、EOP の基準、セキュリティ基準、EOP の設定、atp の設定、の設定、atp の設定、および構成 EOP、セキュリティ構成
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
- m365-initiative-m365-defender
description: Exchange Online Protection (EOP) と Advanced Threat Protection (ATP) のセキュリティ設定のベストプラクティスについて 標準保護に関する現在の推奨事項 より厳しくするには、何を使用する必要がありますか。 Advanced Threat Protection (ATP) も使用している場合、どのようなエクストラを利用できますか?
ms.openlocfilehash: f12610d2f5517461deb828f1b364b30ce3d5202a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413868"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP および Office 365 の ATP セキュリティに関する推奨設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** は、Microsoft 365 サブスクリプションのセキュリティの中核であり、悪意のある電子メールが従業員の受信トレイに届かないようにするために使用します。 しかし、毎日新しい高度な攻撃が発生すると、多くの場合、保護が強化されます。 **Office 365 Advanced Threat Protection (ATP)** ATP プラン1または ATP Plan 2 には、管理者によるセキュリティ、統制、調査の層をさらに強化する追加機能が含まれています。

セキュリティ管理者はセキュリティ設定をカスタマイズすることができますが、EOP と Office 365 ATP には、 **標準** と **Strict**の2つのセキュリティレベルがあります。 お客様の環境とニーズはそれぞれ異なりますが、これらのレベルのフィルター処理によって、ほとんどの状況で、不要なメールが従業員の受信トレイに到達するのを防ぐことができると考えられます。

標準設定または厳密な設定をユーザーに自動的に適用するには、「 [EOP And Office 365 ATP」の「事前にセキュリティポリシー](preset-security-policies.md)を設定する」を参照してください。

**注**: フィルター処理を正しく動作させるには、メールボックスで迷惑メールルールを有効にする必要があります。 これは既定で有効になっていますが、フィルターが機能していないように見える場合は、それをチェックする必要があります。 詳細については、「[Office 365 で Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

この記事では、ユーザーを保護するための既定の設定と、推奨される標準および厳密な設定について説明します。

> [!TIP]
> Office 365 Advanced Threat Protection の推奨構成アナライザー (ORCA) モジュールを使用すると、(管理者) がこれらの設定の現在の値を見つけるのに役立ちます。 具体的には、 **ORCAReport** コマンドレットでは、スパム対策、フィッシング対策、およびその他のメッセージ検疫設定の評価を生成します。 シャチモジュールは、にダウンロードでき <https://www.powershellgallery.com/packages/ORCA/> ます。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング対策保護

スパム対策、マルウェア対策、およびフィッシング対策は、管理者が構成できる EOP 機能です。 次の標準または厳密な構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>「EOP のスパム対策ポリシーの設定」

スパム対策ポリシーを作成して構成するには、「 [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**スパム** 検出アクション <br/><br/> _SpamAction_|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**信頼度の高いスパム** 検出アクション <br/><br/> _HighConfidenceSpamAction_|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**フィッシング電子メール** の検出アクション <br/><br/> _PhishSpamAction_|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**高信頼フィッシング電子メール** 検出アクション <br/><br/> _HighConfidencePhishAction_|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**電子メールの一括** 検出アクション <br/><br/> _BulkSpamAction_|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`||
|バルクメールのしきい値 <br/><br/> _BulkThreshold_|7 |6 |4 |詳細については、「 [Office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。|
|検疫の保存期間 <br/><br/> _QuarantineRetentionPeriod_|15 日|30 日間|30 日間||
|**安全性に関するヒント** <br/><br/> _InlineSafetyTipsEnabled_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|許可された送信者 <br/><br/> _AllowedSenders_|なし|なし|なし||
|許可される送信者ドメイン <br/><br/> _AllowedSenderDomains_|なし|なし|なし|許可された送信者の一覧に自分が所有する (_承認済みドメイン_) ドメインを追加することは、非常に悪い考えです。 攻撃者は、他の方法ではフィルターを適用しない電子メールを送信することができます。 <br/><br/> [**スパム対策設定**] ページの [セキュリティ & コンプライアンスセンター] で[スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)を使用して、組織の電子メールドメインにある送信者の電子メールアドレスをスプーフィングしている、または外部ドメインの送信者の電子メールアドレスをスプーフィングしているすべての送信者を確認します。|
|受信拒否リスト <br/><br/> _BlockedSenders_|なし|なし|なし||
|受信拒否された送信者ドメイン <br/><br/> _BlockedSenderDomains_|なし|なし|なし||
|**[エンド ユーザーのスパム通知を有効にする]**  このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。 <br/><br/> _EnableEndUserSpamNotifications_|無効 <br/><br/> `$false`|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`||
|**エンドユーザーのスパム通知を毎日送信する (日数)** <br/><br/> _EndUserSpamNotificationFrequency_|3 日間|3 日間|3 日間||
|**スパム ZAP** <br/><br/> _SpamZapEnabled_|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`||
|**フィッシング ZAP** <br/><br/> _PhishZapEnabled_|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`|有効 <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|オン|オン|オン|この設定は、PowerShell でのみ使用できます。|
|

使用されなくなっているスパム対策ポリシーには、他にもいくつかの高度なスパムフィルター (ASF) 設定があります。 これらの機能の減価償却のタイムラインの詳細については、この記事の外部に連絡してください。

**標準**レベルと**厳密**なレベルの両方で、これらの ASF 設定を**オフ**にすることをお勧めします。 ASF 設定の詳細については、「 [Office 365 の高度なスパムフィルター (ASF) 設定](advanced-spam-filtering-asf-options.md)」を参照してください。

****

|セキュリティ機能の名前|コメント|
|---|---|
|**リモートサイトへの画像リンク** (_IncreaseScoreWithImageLinks_)||
|**URL の数値の IP アドレス** (_IncreaseScoreWithNumericIps_)||
|**UL リダイレクト (その他のポート** ) (_IncreaseScoreWithRedirectToOtherPort_)||
|**.Url または info web サイトへの URL** (_IncreaseScoreWithBizOrInfoUrls_)||
|**空のメッセージ** (_MarkAsSpamEmptyMessages_)||
|**HTML の JavaScript または VBScript** (_MarkAsSpamJavaScriptInHtml_)||
|**HTML の Frame または IFrame タグ** (_MarkAsSpamFramesInHtml_)||
|**HTML のオブジェクトタグ** (_MarkAsSpamObjectTagsInHtml_)||
|**HTML にタグを埋め込む** (_MarkAsSpamEmbedTagsInHtml_)||
|**HTML の Form タグ** (_MarkAsSpamFormTagsInHtml_)||
|**HTML での Web バグ** (_MarkAsSpamWebBugsInHtml_)||
|**機密単語リストを適用** する (_MarkAsSpamSensitiveWordList_)||
|**SPF レコード: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**条件付き送信者 ID フィルター: hard fail** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR バック散布** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパムポリシーの設定

送信スパムポリシーを作成して構成するには、「 [Office 365 で送信スパムフィルターを構成](configure-the-outbound-spam-policy.md)する」を参照してください。

サービスの既定の送信制限の詳細については、「 [送信制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**ユーザーあたりの最大受信者数: 外部時間の制限** <br/><br/> _RecipientLimitExternalPerHour_|.0|500|400|既定値0は、サービスの既定値を使用することを意味します。|
|**ユーザーあたりの最大受信者数: 内部時間の制限** <br/><br/> _RecipientLimitInternalPerHour_|.0|1000|800|既定値0は、サービスの既定値を使用することを意味します。|
|**ユーザーあたりの最大受信者数: 毎日の制限** <br/><br/> _RecipientLimitPerDay_|.0|1000|800|既定値0は、サービスの既定値を使用することを意味します。|
|**ユーザーが制限を超えた場合のアクション** <br/><br/> _ActionWhenThresholdReached_|**次の日までメールを送信することをユーザーに制限する** <br/><br/> `BlockUserForToday`|**ユーザーがメールを送信するのを制限する** <br/><br/> `BlockUser`|**ユーザーがメールを送信するのを制限する** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成して構成するには、「 [configure マルウェア対策ポリシーを Office 365 で構成](configure-anti-malware-policies.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**受信者にメッセージが検疫されたことを通知するかどうか。** <br/><br/> _操作_|いいえ <br/><br/> _DeleteMessage_|不要 <br/><br/> _DeleteMessage_|不要 <br/><br/> _DeleteMessage_|電子メールの添付ファイルでマルウェアが検出されると、メッセージは検疫され、管理者のみが解放できるようになります。|
|**一般的な添付ファイルの種類のフィルター** <br/><br/> _EnableFileFilter_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`|この設定では、添付ファイルの内容に関係なく、実行可能な添付ファイルが含まれているファイルの種類に基づいてメッセージを検疫します。|
|**マルウェアのゼロ時間の自動削除** <br/><br/> _ZapEnabled_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|配信されていないメッセージの**内部送信者に通知**する <br/><br/> _EnableInternalSenderNotifications_|無効 <br/><br/> `$false`|無効 <br/><br/> `$false`|無効 <br/><br/> `$false`||
|配信されていないメッセージの**外部送信者に通知**する <br/><br/> _EnableExternalSenderNotifications_|無効 <br/><br/> `$false`|無効 <br/><br/> `$false`|無効 <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP の既定のフィッシング対策ポリシー設定

これらの設定の詳細については、「 [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。 これらの設定を構成するには、「 [CONFIGURE EOP」の「フィッシング対策ポリシーを構成](configure-anti-phishing-policies-eop.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**スプーフィング対策保護を有効にする** <br/><br/> _EnableAntispoofEnforcement_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**認証されていない送信者を有効にする** <br/><br/> _Enable/認証 Atedsender_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|オン <br/><br/> `$true`|Outlook の送信者の写真に、未識別のスプーフィングされた送信者を示す疑問符 (?) を追加します。 詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md)」を参照してください。|
|**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信された場合** <br/><br/> _AuthenticationFailAction_|**受信者の迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**受信者の迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**メッセージを検疫する** <br/><br/> `Quarantine`|この設定は、 [スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)の受信拒否リストに適用されます。|
|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 Advanced Threat Protection セキュリティ

その他のセキュリティ上の利点には、Office 365 Advanced Threat Protection (ATP) サブスクリプションが付属しています。 最新のニュースと情報については、「 [Office 365 ATP の新機能](whats-new-in-office-365-atp.md)」を参照してください。

> [!IMPORTANT]
>
> - 既定の ATP のフィッシング対策ポリシーは、すべての受信者に対して [スプーフ保護](set-up-anti-phishing-policies.md#spoof-settings) を提供します。 ただし、特定の送信者または送信者のドメインに対して使用可能な [偽装保護](#impersonation-settings-in-atp-anti-phishing-policies) の設定は、既定のポリシーで構成されていないか、有効になっていません。 偽装保護を有効にするには、既定のポリシーを構成するか、追加の ATP のフィッシング対策ポリシーを作成します。
>
> - 組織内のすべての受信者を自動的に保護する、安全なリンクポリシーまたは安全な添付ファイルポリシーはありません。 保護を得るには、少なくとも1つの安全なリンクポリシーと安全な添付ファイルポリシーを作成する必要があります。
>
> - [SharePoint、OneDrive、Microsoft Teams の](atp-for-spo-odb-and-teams.md) 保護および安全な [ドキュメント](safe-docs.md) の保護のための ATP は、安全なリンクポリシーに依存しません。

サブスクリプションに Office 365 ATP が含まれている場合、または Office 365 ATP をアドオンとして購入した場合は、次の標準構成または厳密な構成を設定します。

### <a name="atp-anti-phishing-policy-settings"></a>ATP のフィッシング対策ポリシー設定

EOP のお客様は、前述したように基本的なフィッシング対策を行いますが、Office 365 ATP には、攻撃を防止、検出、修復するのに役立つ機能と制御が追加されています。 これらのポリシーを作成して構成するには、「 [Office 365 で ATP のフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)する」を参照してください。

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP のフィッシング対策ポリシーの偽装設定

これらの設定の詳細については、「 [ATP のフィッシング対策ポリシー」の「偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)」を参照してください。 これらの設定を構成するには、「 [ATP のフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|保護されたユーザー: **保護するユーザーを追加する** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|オフ <br/><br/> `$false` <br/><br/> なし|オン <br/><br/> `$true` <br/><br/> \<list of users\>|オン <br/><br/> `$true` <br/><br/> \<list of users\>|組織によっては、主な役割にユーザー (メッセージ送信者) を追加することをお勧めします。 内部的には、保護された送信者は CEO、CFO、その他のシニアリーダーである場合があります。 外部では、保護された送信者は協議会のメンバーまたは取締役会を含めることができます。|
|保護されたドメイン: **自分が所有しているドメインを自動的に追加する** <br/><br/> _Enable組織 Domainsprotection_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|保護されたドメイン: **カスタムドメインを含める** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|オフ <br/><br/> `$false` <br/><br/> なし|オン <br/><br/> `$true` <br/><br/> \<list of domains\>|オン <br/><br/> `$true` <br/><br/> \<list of domains\>|組織によっては、所有していないが頻繁に操作するドメイン (送信者ドメイン) を追加することをお勧めします。|
|保護されたユーザー: **偽装ユーザーによって電子メールが送信される場合** <br/><br/> _され_|**どの操作も適用しない** <br/><br/> `NoAction`|**メッセージを検疫する** <br/><br/> `Quarantine`|**メッセージを検疫する** <br/><br/> `Quarantine`||
|保護されたドメイン: **偽装ドメインによって電子メールが送信される場合** <br/><br/> _TargetedDomainProtectionAction_|**どの操作も適用しない** <br/><br/> `NoAction`|**メッセージを検疫する** <br/><br/> `Quarantine`|**メッセージを検疫する** <br/><br/> `Quarantine`||
|**偽装ユーザーのヒントを表示する** <br/><br/> _Enablesimilarユーザーヒント Etytips_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**偽装ドメインのヒントを表示する** <br/><br/> _Enablesimilardomainssaf Etytips_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**通常と異なる文字にヒントを表示する** <br/><br/> _EnableUnusualCharactersSafetyTips_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**メールボックスインテリジェンスを有効にする** <br/><br/> _EnableMailboxIntelligence_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**メールボックスインテリジェンスベースの偽装保護を有効にする** <br/><br/> _EnableMailboxIntelligenceProtection_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**メールボックスインテリジェンスで保護された偽装ユーザーによって電子メールが送信される場合** <br/><br/> _MailboxIntelligenceProtectionAction_|**どの操作も適用しない** <br/><br/> `NoAction`|**受信者の迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**メッセージを検疫する** <br/><br/> `Quarantine`||
|**信頼された差出人** <br/><br/> _ExcludedSenders_|なし|なし|なし|組織によっては、誤ってフィッシングとしてマークされるユーザーを追加することをお勧めします。|
|**信頼されたドメイン** <br/><br/> _ExcludedDomains_|なし|なし|なし|組織によっては、誤ってフィッシングとしてマークされたドメインを、他のフィルターではなく偽装によってのみ追加することをお勧めします。|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>ATP のフィッシング対策ポリシーのスプーフィング設定

これらは、 [EOP のスパム対策ポリシー設定](#eop-anti-spam-policy-settings)で使用可能な設定と同じであることに注意してください。

****

|セキュリティ機能の名前|Standard|Strict|コメント|
|---|---|---|---|
|**スプーフィング対策保護を有効にする** <br/><br/> _EnableAntispoofEnforcement_|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**認証されていない送信者を有効にする** <br/><br/> _Enable/認証 Atedsender_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|Outlook の送信者の写真に、未識別のスプーフィングされた送信者を示す疑問符 (?) を追加します。 詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md)」を参照してください。|
|**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信された場合** <br/><br/> _AuthenticationFailAction_|**受信者の迷惑メールフォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**メッセージを検疫する** <br/><br/> `Quarantine`|この設定は、 [スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)の受信拒否リストに適用されます。|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>ATP のフィッシング対策ポリシーの詳細設定

この設定の詳細については、「 [ATP のフィッシング対策ポリシー」の「Advanced フィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)」を参照してください。 この設定を構成するには、「 [ATP フィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**高度なフィッシングしきい値** <br/><br/> _PhishThresholdLevel_|**1-標準** <br/><br/> `1`|**2-アグレッシブ** <br/><br/> `2`|**3つ以上のアグレッシブ** <br/><br/> `3`||
|

### <a name="safe-links-settings"></a>安全なリンクの設定

「Office 365 の安全なリンク」では、アクティブな安全なリンクポリシーに含まれるすべてのユーザーに適用されるグローバル設定と、各安全リンクポリシーに固有の設定が含まれています。 詳細については、「 [Office 365 ATP」の「安全なリンク](atp-safe-links.md)」を参照してください。

#### <a name="global-settings-for-safe-links"></a>安全なリンクのグローバル設定

これらの設定を構成するには、「 [Office 365 ATP で安全なリンクのグローバル設定を構成](configure-global-settings-for-safe-links.md)する」を参照してください。

PowerShell では、これらの設定には [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**安全なリンクの使用: Office 365 アプリケーション** <br/><br/> _EnableSafeLinksForO365Clients_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|オン <br/><br/> `$true`|サポートされている Office 365 デスクトップおよびモバイル (iOS および Android) アプリでは、ATP の安全なリンクを使用します。 詳細については、「 [Office 365 アプリの安全なリンク設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。|
|**ユーザーが [安全なリンク] をクリックしたときに追跡しない** <br/><br/> _トラッククリック_|オン <br/><br/> `$false`|オフ <br/><br/> `$true`|オフ <br/><br/> `$true`|この設定をオフにする ( _Trackclicks クリック_ を設定する) と、 `$true` サポートされている Office 365 アプリのユーザークリックが追跡されます。|
|**ユーザーが元の URL への安全なリンクをクリックできないようにする** <br/><br/> _AllowClickThrough スルー_|オン <br/><br/> `$false`|オン <br/><br/> `$false`|オン <br/><br/> `$false`|この設定を有効にする ( _allowclickthrough_ に設定) を使用すると `$false` 、サポートされている Office 365 アプリの元の URL にクリックして移動することができなくなります。|
|

#### <a name="safe-links-policy-settings"></a>安全リンクポリシーの設定

これらの設定を構成するには、「 [Office 365 ATP で安全なリンクポリシーをセットアップ](set-up-atp-safe-links-policies.md)する」を参照してください。

PowerShell では、これらの設定に [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) および [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

**注**: 前述のように、既定の安全なリンクポリシーはありません。 [既定] 列の値は、作成する新しい安全なリンクポリシーの既定値です。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**メッセージ内の不明な潜在的な悪意のある Url に対するアクションを選択する** <br/><br/> _IsEnabled_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**Microsoft Teams 内の不明なまたは悪意のある Url に対するアクションを選択する** <br/><br/> _EnableSafeLinksForTeams_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**疑わしいリンクおよびファイルを指すリンクのリアルタイム URL スキャンを適用する** <br/><br/> _スキャン Url_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**メッセージを配信する前に URL スキャンが完了するまで待機する** <br/><br/> _DeliverMessageAfterScan_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**組織内で送信される電子メールメッセージに安全なリンクを適用する** <br/><br/> _EnableForInternalSenders_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**ユーザーのクリックを追跡しない** <br/><br/> _ユーザーがクリックしたトラック_|オフ <br/><br/> `$false`|オフ <br/><br/> `$false`|オフ <br/><br/> `$false`|この _設定をオフ_ にすると (自動切り替えの設定)、ユーザーがクリックしたことが `$false` 追跡されます。|
|**ユーザーが元の URL にクリックできないようにする** <br/><br/> _/クリックスルー_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|オン <br/><br/> `$true`|この設定をオンにすると、[] を [オン] _に設定する_ と `$true` 、元の URL に移動できなくなります。|
|

### <a name="safe-attachments-settings"></a>安全な添付ファイルの設定

Office 365 の安全な添付ファイルには、安全な添付ファイルポリシーとの関係を持たないグローバル設定と、各安全なリンクポリシーに固有の設定が含まれています。 詳細については、「 [Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)」を参照してください。

#### <a name="global-settings-for-safe-attachments"></a>安全な添付ファイルのグローバル設定

これらの設定を構成するには、 [microsoft 365 E5](safe-docs.md)の「 [SharePoint、OneDrive、Microsoft Teams および安全なドキュメントの ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。

PowerShell では、これらの設定には [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする** <br/><br/> _EnableATPForSPOTeamsODB_|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|**Office クライアントの安全なドキュメントを有効にする**<bt/><br/> _EnableSafeDocs_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|この設定は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティライセンスでのみ使用できます。 詳細については、「 [Office 365 Advanced Threat Protection」の「Safe Documents](safe-docs.md)」を参照してください。|
|**安全なドキュメントが悪意のあるファイルとして識別された場合でも、保護されたビューのクリックをユーザーに許可**する <bt/><br/> _AllowSafeDocsOpen_|オフ <br/><br/> `$false`|オフ <br/><br/> `$false`|この設定は、安全なドキュメントに関連しています。|
|

#### <a name="safe-attachments-policy-settings"></a>安全な添付ファイルのポリシー設定

これらの設定を構成するには、「 [Office 365 ATP で安全な添付ファイルポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」を参照してください。

PowerShell では、これらの設定に対して、 [新しい-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) および [Set-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

**注**: 前述のように、既定の安全な添付ファイルポリシーはありません。 [既定] 列の値は、作成する新しい安全な添付ファイルポリシーの既定値です。

****

|セキュリティ機能の名前|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**安全な添付ファイルの不明なマルウェア応答** <br/><br/> _操作_|ブロック <br/><br/> `Block`|ブロック <br/><br/> `Block`|ブロック <br/><br/> `Block`||
|**検出時に接続をリダイレクト****する: リダイレクトを有効にする** <br/><br/> _リダイレクト_ <br/><br/> _RedirectAddress_|Off で、電子メールアドレスが指定されていません。 <br/><br/> `$true` <br/><br/> なし|で、電子メールアドレスを指定します。 <br/><br/> `$true` <br/><br/> 電子メールアドレス|で、電子メールアドレスを指定します。 <br/><br/> `$true` <br/><br/> 電子メールアドレス|メッセージをセキュリティ管理者にレビュー用にリダイレクトします。|
|**マルウェアスキャンによる添付ファイルのタイムアウトまたはエラーが発生した場合は、上記の選択を適用します。** <br/><br/> _ActionOnError_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|オン <br/><br/> `$true`||
|

## <a name="related-articles"></a>関連記事

- **Exchange メールフロールール (トランスポートルールとも呼ば**れます) のベストプラクティスについては、こちらを参照してください。 「 [Exchange Online でメールフロールールを構成するためのベストプラクティス」を](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)参照してください。

- 管理者とユーザーは、誤検知 (不良としてマークされている正常なメール) と誤検知 (無効な電子メールを許可) を分析のために Microsoft に送信できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- [EOP サービス](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)を**セットアップする方法**、および[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)を**構成**する方法に関する情報については、次のリンクを使用してください。 「[Office 365 での脅威からの保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」にある、役に立つ手順を忘れないでください。

- **Windows のセキュリティベースライン** は、「GPO/オンプレ [ミスのオプション](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) 」および「Intune ベースのセキュリティ」に記載さ [れてい](https://docs.microsoft.com/intune/protect/security-baselines) ます。 最後に、Microsoft Defender Advanced Threat Protection (ATP) と Microsoft Intune セキュリティベースラインの比較は [こちら](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)でご確認いただけます。
