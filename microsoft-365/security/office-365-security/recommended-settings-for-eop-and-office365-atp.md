---
title: Microsoft の推奨事項 EOP および Defender for Office 365 のセキュリティ設定、推奨事項、Sender Policy Framework、ドメインベースのメッセージの報告と適合性、DomainKeys 識別されたメール、手順、EOP の機能、セキュリティ基準、のベースライン、office 365 のためのベースラインの 365 365 設定、EOP、セキュリティ構成の構成
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
description: Exchange Online Protection (EOP) および Defender for Office 365 のセキュリティ設定のベストプラクティスとは 標準保護に関する現在の推奨事項 より厳しくするには、何を使用する必要がありますか。 また、Office 365 に Defender も使用している場合は、どのような機能を利用できますか。
ms.openlocfilehash: 032cd6a50f56fd3e1e47faebfaea5f6665553a4b
ms.sourcegitcommit: 09518b7c9146cda7fd42839ee644ad418d48491a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49001527"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP および Microsoft Defender for Office 365 のセキュリティに関する推奨設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** は、Microsoft 365 サブスクリプションのセキュリティの中核であり、悪意のある電子メールが従業員の受信トレイに届かないようにするために使用します。 しかし、毎日新しい高度な攻撃が発生すると、多くの場合、保護が強化されます。 **Microsoft Defender For Office 365** プラン1またはプラン2には、より多くのセキュリティ、統制、調査を管理できる追加機能が含まれています。

セキュリティ管理者はセキュリティ設定をカスタマイズすることができますが、EOP には2つのセキュリティレベルがあり、Microsoft Defender for Office 365 が推奨されています。 **標準** と **Strict** 。 お客様の環境とニーズはそれぞれ異なりますが、これらのレベルのフィルター処理によって、ほとんどの状況で、不要なメールが従業員の受信トレイに到達するのを防ぐことができると考えられます。

標準設定または厳密な設定をユーザーに自動的に適用するには、「EOP の事前設定された [セキュリティポリシー」および「Microsoft Defender For Office 365](preset-security-policies.md)」を参照してください。

> [!NOTE]
> フィルター処理を正しく動作させるには、メールボックスで迷惑メールルールを有効にする必要があります。 これは既定で有効になっていますが、フィルターが機能していないように見える場合は、それをチェックする必要があります。 詳細については、「[Office 365 で Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

この記事では、ユーザーを保護するための既定の設定と、推奨される標準および厳密な設定について説明します。

> [!TIP]
> Office 365 Advanced Threat Protection の推奨構成アナライザー (ORCA) モジュールを使用すると、(管理者) がこれらの設定の現在の値を見つけるのに役立ちます。 具体的には、 **ORCAReport** コマンドレットでは、スパム対策、フィッシング対策、およびその他のメッセージ検疫設定の評価を生成します。 シャチモジュールは、にダウンロードでき <https://www.powershellgallery.com/packages/ORCA/> ます。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング対策保護

スパム対策、マルウェア対策、およびフィッシング対策は、管理者が構成できる EOP 機能です。 次の標準または厳密な構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>「EOP のスパム対策ポリシーの設定」

スパム対策ポリシーを作成して構成するには、「 [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**スパム** 検出アクション <p> _SpamAction_|**迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|**信頼度の高いスパム** 検出アクション <p> _HighConfidenceSpamAction_|**迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**フィッシング電子メール** の検出アクション <p> _PhishSpamAction_|**迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**高信頼フィッシング電子メール** 検出アクション <p> _HighConfidencePhishAction_|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**電子メールの一括** 検出アクション <p> _BulkSpamAction_|**迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|バルクメールのしきい値 <p> _BulkThreshold_|7 |6 |4 |詳細については、「 [Office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。|
|検疫の保存期間 <p> _QuarantineRetentionPeriod_|15 日|30 日間|30 日間||
|**安全性に関するヒント** <p> _InlineSafetyTipsEnabled_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|許可された送信者 <p> _AllowedSenders_|なし|なし|なし||
|許可される送信者ドメイン <p> _AllowedSenderDomains_|なし|なし|なし|許可された送信者の一覧にドメインを追加するのは、非常にわかりません。 攻撃者は、他の方法ではフィルターを適用しない電子メールを送信することができます。 <p> [ **スパム対策設定** ] ページの [セキュリティ & コンプライアンスセンター] で [スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)を使用して、組織の電子メールドメインにある送信者の電子メールアドレスをスプーフィングしている、または外部ドメインの送信者の電子メールアドレスをスプーフィングしているすべての送信者を確認します。|
|受信拒否リスト <p> _BlockedSenders_|なし|なし|なし||
|受信拒否された送信者ドメイン <p> _BlockedSenderDomains_|なし|なし|なし||
|**[エンド ユーザーのスパム通知を有効にする]**  このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。 <p> _EnableEndUserSpamNotifications_|無効 <p> `$false`|有効 <p> `$true`|有効 <p> `$true`||
|**エンドユーザーのスパム通知を毎日送信する (日数)** <p> _EndUserSpamNotificationFrequency_|3 日間|3 日間|3 日間||
|**スパム ZAP** <p> _SpamZapEnabled_|有効 <p> `$true`|有効 <p> `$true`|有効 <p> `$true`||
|**フィッシング ZAP** <p> _PhishZapEnabled_|有効 <p> `$true`|有効 <p> `$true`|有効 <p> `$true`||
|_MarkAsSpamBulkMail_|オン|オン|オン|この設定は、PowerShell でのみ使用できます。|
|

使用されなくなっているスパム対策ポリシーには、他にもいくつかの高度なスパムフィルター (ASF) 設定があります。 これらの機能の減価償却のタイムラインの詳細については、この記事の外部に連絡してください。

**標準** レベルと **厳密** なレベルの両方で、これらの ASF 設定を **オフ** にすることをお勧めします。 ASF 設定の詳細については、「 [Office 365 の高度なスパムフィルター (ASF) 設定](advanced-spam-filtering-asf-options.md)」を参照してください。

****

|セキュリティ機能の名前|Comment|
|---|---|
|**リモートサイトへの画像リンク** ( _IncreaseScoreWithImageLinks_ )||
|**URL の数値の IP アドレス** ( _IncreaseScoreWithNumericIps_ )||
|**UL リダイレクト (その他のポート** ) ( _IncreaseScoreWithRedirectToOtherPort_ )||
|**.Url または info web サイトへの URL** ( _IncreaseScoreWithBizOrInfoUrls_ )||
|**空のメッセージ** ( _MarkAsSpamEmptyMessages_ )||
|**HTML の JavaScript または VBScript** ( _MarkAsSpamJavaScriptInHtml_ )||
|**HTML の Frame または IFrame タグ** ( _MarkAsSpamFramesInHtml_ )||
|**HTML のオブジェクトタグ** ( _MarkAsSpamObjectTagsInHtml_ )||
|**HTML にタグを埋め込む** ( _MarkAsSpamEmbedTagsInHtml_ )||
|**HTML の Form タグ** ( _MarkAsSpamFormTagsInHtml_ )||
|**HTML での Web バグ** ( _MarkAsSpamWebBugsInHtml_ )||
|**機密単語リストを適用** する ( _MarkAsSpamSensitiveWordList_ )||
|**SPF レコード: hard fail** ( _MarkAsSpamSpfRecordHardFail_ )||
|**条件付き送信者 ID フィルター: hard fail** ( _MarkAsSpamFromAddressAuthFail_ )||
|**NDR バック散布** ( _MarkAsSpamNdrBackscatter_ )||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパムポリシーの設定

送信スパムポリシーを作成して構成するには、「 [Office 365 で送信スパムフィルターを構成](configure-the-outbound-spam-policy.md)する」を参照してください。

サービスの既定の送信制限の詳細については、「 [送信制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**ユーザーあたりの最大受信者数: 外部時間の制限** <p> _RecipientLimitExternalPerHour_|.0|500|400|既定値0は、サービスの既定値を使用することを意味します。|
|**ユーザーあたりの最大受信者数: 内部時間の制限** <p> _RecipientLimitInternalPerHour_|.0|1000|800|既定値0は、サービスの既定値を使用することを意味します。|
|**ユーザーあたりの最大受信者数: 毎日の制限** <p> _RecipientLimitPerDay_|.0|1000|800|既定値0は、サービスの既定値を使用することを意味します。|
|**ユーザーが制限を超えた場合のアクション** <p> _ActionWhenThresholdReached_|**次の日までメールを送信することをユーザーに制限する** <p> `BlockUserForToday`|**ユーザーがメールを送信するのを制限する** <p> `BlockUser`|**ユーザーがメールを送信するのを制限する** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成して構成するには、「 [configure マルウェア対策ポリシーを Office 365 で構成](configure-anti-malware-policies.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**受信者にメッセージが検疫されたことを通知するかどうか。** <p> _操作_|いいえ <p> _DeleteMessage_|いいえ <p> _DeleteMessage_|いいえ <p> _DeleteMessage_|電子メールの添付ファイルでマルウェアが検出されると、メッセージは検疫され、管理者のみが解放できるようになります。|
|**一般的な添付ファイルの種類のフィルター** <p> _EnableFileFilter_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`|この設定では、添付ファイルの内容に関係なく、実行可能な添付ファイルが含まれているファイルの種類に基づいてメッセージを検疫します。|
|**マルウェアのゼロ時間の自動削除** <p> _ZapEnabled_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|配信されていないメッセージの **内部送信者に通知** する <p> _EnableInternalSenderNotifications_|無効 <p> `$false`|無効 <p> `$false`|無効 <p> `$false`||
|配信されていないメッセージの **外部送信者に通知** する <p> _EnableExternalSenderNotifications_|無効 <p> `$false`|無効 <p> `$false`|無効 <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP の既定のフィッシング対策ポリシー設定

これらの設定の詳細については、「 [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。 これらの設定を構成するには、「 [CONFIGURE EOP」の「フィッシング対策ポリシーを構成](configure-anti-phishing-policies-eop.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**スプーフィング対策保護を有効にする** <p> _EnableAntispoofEnforcement_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**認証されていない送信者を有効にする** <p> _Enable/認証 Atedsender_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|Outlook の送信者の写真に、未識別のスプーフィングされた送信者を示す疑問符 (?) を追加します。 詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md)」を参照してください。|
|**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、 [スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)の受信拒否リストに適用されます。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 のセキュリティ

その他のセキュリティ上の利点は、Microsoft Defender for Office 365 サブスクリプションに付属しています。 最新のニュースと情報については、「 [Office 365 の Defender の新機能](whats-new-in-office-365-atp.md)」を参照してください。

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365 の既定のフィッシング対策ポリシーにより、すべての受信者に対して [スプーフィングによる保護](set-up-anti-phishing-policies.md#spoof-settings) が提供されます。 ただし、特定の送信者または送信者のドメインに対して使用可能な [偽装保護](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) の設定は、既定のポリシーで構成されていないか、有効になっていません。 偽装保護を有効にするには、既定のポリシーを構成するか、Office 365 の Defender で追加のフィッシング対策ポリシーを作成します。
>
> - 組織内のすべての受信者を自動的に保護する、安全なリンクポリシーまたは安全な添付ファイルポリシーはありません。 保護を得るには、少なくとも1つの安全なリンクポリシーと安全な添付ファイルポリシーを作成する必要があります。
>
> - [SharePoint、OneDrive、Microsoft Teams の](atp-for-spo-odb-and-teams.md) 保護および安全な [ドキュメント](safe-docs.md) の保護のための ATP は、安全なリンクポリシーに依存しません。

サブスクリプションに Microsoft Defender for Office 365 が含まれている場合、またはアドオンとして Office 365 の Defender を購入した場合は、次の標準構成または厳密な構成を設定します。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシー設定

前述のように、EOP のお客様は基本的なフィッシング対策を行いますが、Microsoft Defender for Office 365 には、攻撃を防止、検出、修復するのに役立つ機能と制御が追加されています。 これらのポリシーを作成して構成するには、「 [Office 365 の Defender でのフィッシング対策ポリシーの構成](configure-atp-anti-phishing-policies.md)」を参照してください。

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーの偽装設定

これらの設定の詳細については、「 [Microsoft Defender のフィッシング対策ポリシーの偽装設定 (Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365))」を参照してください。 これらの設定を構成するには、「 [Office 365 の Defender でフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)する」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|保護されたユーザー: **保護するユーザーを追加する** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|オフ <p> `$false` <p> none|オン <p> `$true` <p> \<list of users\>|オン <p> `$true` <p> \<list of users\>|組織によっては、主な役割にユーザー (メッセージ送信者) を追加することをお勧めします。 内部的には、保護された送信者は CEO、CFO、その他のシニアリーダーである場合があります。 外部では、保護された送信者は協議会のメンバーまたは取締役会を含めることができます。|
|保護されたドメイン: **自分が所有しているドメインを自動的に追加する** <p> _Enable組織 Domainsprotection_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|保護されたドメイン: **カスタムドメインを含める** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|オフ <p> `$false` <p> none|オン <p> `$true` <p> \<list of domains\>|オン <p> `$true` <p> \<list of domains\>|組織によっては、所有していないが頻繁に操作するドメイン (送信者ドメイン) を追加することをお勧めします。|
|保護されたユーザー: **偽装ユーザーによって電子メールが送信される場合** <p> _され_|**どの操作も適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|保護されたドメイン: **偽装ドメインによって電子メールが送信される場合** <p> _TargetedDomainProtectionAction_|**どの操作も適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**偽装ユーザーのヒントを表示する** <p> _Enablesimilarユーザーヒント Etytips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**偽装ドメインのヒントを表示する** <p> _Enablesimilardomainssaf Etytips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**通常と異なる文字にヒントを表示する** <p> _EnableUnusualCharactersSafetyTips_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メールボックスインテリジェンスを有効にする** <p> _EnableMailboxIntelligence_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|**メールボックスインテリジェンスベースの偽装保護を有効にする** <p> _EnableMailboxIntelligenceProtection_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メールボックスインテリジェンスで保護された偽装ユーザーによって電子メールが送信される場合** <p> _MailboxIntelligenceProtectionAction_|**どの操作も適用しない** <p> `NoAction`|**受信者の迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`||
|**信頼された差出人** <p> _ExcludedSenders_|なし|なし|なし|組織によっては、誤ってフィッシングとしてマークされるユーザーを追加することをお勧めします。|
|**信頼されたドメイン** <p> _ExcludedDomains_|なし|なし|なし|組織によっては、誤ってフィッシングとしてマークされたドメインを、他のフィルターではなく偽装によってのみ追加することをお勧めします。|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーのスプーフィング設定

これらは、 [EOP のスパム対策ポリシー設定](#eop-anti-spam-policy-settings)で使用可能な設定と同じであることに注意してください。

****

|セキュリティ機能の名前|Standard|Strict|Comment|
|---|---|---|---|
|**スプーフィング対策保護を有効にする** <p> _EnableAntispoofEnforcement_|オン <p> `$true`|オン <p> `$true`||
|**認証されていない送信者を有効にする** <p> _Enable/認証 Atedsender_|オン <p> `$true`|オン <p> `$true`|Outlook の送信者の写真に、未識別のスプーフィングされた送信者を示す疑問符 (?) を追加します。 詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md)」を参照してください。|
|**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メールフォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、 [スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)の受信拒否リストに適用されます。|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーの詳細設定

この設定の詳細については、「 [Microsoft Defender 365 のフィッシング対策ポリシー」の「Advanced フィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。 この設定を構成するには、「 [Office 365 の Defender でのフィッシング対策ポリシーの構成](configure-atp-anti-phishing-policies.md)」を参照してください。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**高度なフィッシングしきい値** <p> _PhishThresholdLevel_|**1-標準** <p> `1`|**2-アグレッシブ** <p> `2`|**3つ以上のアグレッシブ** <p> `3`||
|

### <a name="safe-links-settings"></a>安全なリンクの設定

Defender in Office 365 の「安全なリンク」には、アクティブな安全リンクポリシーに含まれるすべてのユーザーに適用されるグローバル設定と、各安全リンクポリシーに固有の設定が含まれています。 詳細については、「 [Office 365 の Defender の安全なリンク](atp-safe-links.md)」を参照してください。

#### <a name="global-settings-for-safe-links"></a>安全なリンクのグローバル設定

これらの設定を構成するには、「 [configure global settings For Safe Links In Office 365](configure-global-settings-for-safe-links.md)」を参照してください。

PowerShell では、これらの設定には [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**安全なリンクの使用: Office 365 アプリケーション** <p> _EnableSafeLinksForO365Clients_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|サポートされている Office 365 デスクトップおよびモバイル (iOS および Android) アプリでは安全なリンクを使用します。 詳細については、「 [Office 365 アプリの安全なリンク設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。|
|**ユーザーが [安全なリンク] をクリックしたときに追跡しない** <p> _トラッククリック_|オン <p> `$false`|オフ <p> `$true`|オフ <p> `$true`|この設定をオフにする ( _Trackclicks クリック_ を設定する) と、 `$true` サポートされている Office 365 アプリのユーザークリックが追跡されます。|
|**ユーザーが元の URL への安全なリンクをクリックできないようにする** <p> _AllowClickThrough スルー_|オン <p> `$false`|オン <p> `$false`|オン <p> `$false`|この設定を有効にする ( _allowclickthrough_ に設定) を使用すると `$false` 、サポートされている Office 365 アプリの元の URL にクリックして移動することができなくなります。|
|

#### <a name="safe-links-policy-settings"></a>安全リンクポリシーの設定

これらの設定を構成するには、「 [Set Up Safe Links policies In office 365](set-up-atp-safe-links-policies.md)」を参照してください。

PowerShell では、これらの設定に [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) および [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定の安全なリンクポリシーはありません。 [既定] 列の値は、作成する新しい安全なリンクポリシーの既定値です。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**メッセージ内の不明な潜在的な悪意のある Url に対するアクションを選択する** <p> _IsEnabled_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**Microsoft Teams 内の不明なまたは悪意のある Url に対するアクションを選択する** <p> _EnableSafeLinksForTeams_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**疑わしいリンクおよびファイルを指すリンクのリアルタイム URL スキャンを適用する** <p> _スキャン Url_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**メッセージを配信する前に URL スキャンが完了するまで待機する** <p> _DeliverMessageAfterScan_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**組織内で送信される電子メールメッセージに安全なリンクを適用する** <p> _EnableForInternalSenders_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**ユーザーのクリックを追跡しない** <p> _ユーザーがクリックしたトラック_|オフ <p> `$false`|オフ <p> `$false`|オフ <p> `$false`|この _設定をオフ_ にすると (自動切り替えの設定)、ユーザーがクリックしたことが `$false` 追跡されます。|
|**ユーザーが元の URL にクリックできないようにする** <p> _/クリックスルー_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`|この設定をオンにすると、[] を [オン] _に設定する_ と `$true` 、元の URL に移動できなくなります。|
|

### <a name="safe-attachments-settings"></a>安全な添付ファイルの設定

「Microsoft Defender for Office 365 の安全な添付ファイル」には、安全な添付ファイルのポリシーとの関係を持たないグローバル設定と、各安全なリンクポリシーに固有の設定が含まれています。 詳細については、「 [Office 365 の Defender の安全な添付ファイル](atp-safe-attachments.md)」を参照してください。

#### <a name="global-settings-for-safe-attachments"></a>安全な添付ファイルのグローバル設定

これらの設定を構成するには、 [microsoft 365 E5](safe-docs.md)の「 [SharePoint、OneDrive、Microsoft Teams および安全なドキュメントの ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。

PowerShell では、これらの設定には [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする** <p> _EnableATPForSPOTeamsODB_|オン <p> `$true`|オン <p> `$true`||
|**Office クライアントの安全なドキュメントを有効にする**<bt/><br/> _EnableSafeDocs_|オン <p> `$true`|オン <p> `$true`|この設定は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティライセンスでのみ使用できます。 詳細については、「 [Microsoft Defender For Office 365](safe-docs.md)」の「Safe Documents」を参照してください。|
|**安全なドキュメントが悪意のあるファイルとして識別された場合でも、保護されたビューのクリックをユーザーに許可** する <bt/><br/> _AllowSafeDocsOpen_|オフ <p> `$false`|オフ <p> `$false`|この設定は、安全なドキュメントに関連しています。|
|

#### <a name="safe-attachments-policy-settings"></a>安全な添付ファイルのポリシー設定

これらの設定を構成するには、「 [Office 365 の Defender で安全な添付ファイルポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」を参照してください。

PowerShell では、これらの設定に対して、 [新しい-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) および [Set-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定の安全な添付ファイルポリシーはありません。 [既定] 列の値は、作成する新しい安全な添付ファイルポリシーの既定値です。

****

|セキュリティ機能の名前|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**安全な添付ファイルの不明なマルウェア応答** <p> _操作_|ブロック <p> `Block`|ブロック <p> `Block`|ブロック <p> `Block`||
|**検出時に接続をリダイレクト****する: リダイレクトを有効にする** <p> _リダイレクトする_ <p> _RedirectAddress_|Off で、電子メールアドレスが指定されていません。 <p> `$true` <p> none|で、電子メールアドレスを指定します。 <p> `$true` <p> 電子メールアドレス|で、電子メールアドレスを指定します。 <p> `$true` <p> 電子メールアドレス|メッセージをセキュリティ管理者にレビュー用にリダイレクトします。|
|**マルウェアスキャンによる添付ファイルのタイムアウトまたはエラーが発生した場合は、上記の選択を適用します。** <p> _ActionOnError_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`||
|

## <a name="related-articles"></a>関連記事

- **Exchange メールフロールール (トランスポートルールとも呼ば** れます) のベストプラクティスについては、こちらを参照してください。 「 [Exchange Online でメールフロールールを構成するためのベストプラクティス」を](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)参照してください。

- 管理者とユーザーは、誤検知 (不良としてマークされている正常なメール) と誤検知 (無効な電子メールを許可) を分析のために Microsoft に送信できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- これらのリンクは、 [EOP サービス](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)を **セットアップする方法** 、および [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)を **構成** する方法に関する情報を対象としています。 「[Office 365 での脅威からの保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」にある、役に立つ手順を忘れないでください。

- **Windows のセキュリティベースライン** は、次の場所にあります。 [セキュリティベースラインを取得できますか](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) 。また、セキュリティベースラインを使用して intune で intune ベースセキュリティ用の [Windows 10 デバイスを構成する](https://docs.microsoft.com/intune/protect/security-baselines) ことができます。 最後に、エンドポイントと Microsoft Intune セキュリティベースラインの microsoft defender の比較については、「 [Microsoft defender と Windows intune セキュリティベースラインの比較](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)」を参照してください。
