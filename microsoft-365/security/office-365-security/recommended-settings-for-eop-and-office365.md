---
title: EOP と Defender のセキュリティ設定に関する Microsoft Office 365推奨
keywords: Office 365 セキュリティの推奨事項、Sender Policy Framework、ドメイン ベースのメッセージレポートと準拠、DomainKeys Identified Mail、手順、動作方法、セキュリティ ベースライン、EOP のベースライン、Office 365 用 Defender のベースライン、Office 365 用 Defender のセットアップ、EOP のセットアップ、Office 365 用 Defender の構成、EOP、セキュリティ構成の構成
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
description: セキュリティ設定に関する Exchange Online Protection (EOP) と Defender のベスト Office 365は何ですか? 標準保護に関する現在の推奨事項は何ですか? より厳密にしたい場合は、何を使用する必要がありますか? また、Defender をユーザーに使用する場合、どのような追加Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1cdaf1997895a3b168cc4887d3877f2f8a651ed7
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533041"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP と Microsoft Defender のセキュリティに関するOffice 365設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** は、Microsoft 365 サブスクリプションのセキュリティの中核であり、悪意のあるメールが従業員の受信トレイに届かされるのを防ごうのに役立ちます。 しかし、より高度な新しい攻撃が毎日出現する中で、多くの場合、保護の強化が必要になります。 **Microsoft Defender for Office 365** プラン 1 またはプラン 2 には、管理者にセキュリティ、制御、調査の層を追加する追加機能が含まれている。

セキュリティ管理者はセキュリティ設定のカスタマイズを強化しますが、EOP と Microsoft Defender の 2 つのセキュリティ レベルは、推奨Office 365標準と **厳密** です。 各顧客の環境とニーズは異なりますが、これらのレベルのフィルター処理は、ほとんどの状況で望ましくないメールが従業員の受信トレイに届かされるのを防ぐのに役立つと考えています。

標準または厳密な設定をユーザーに自動的に適用するには[、「EOP](preset-security-policies.md)でのセキュリティ ポリシーの事前設定」および「Microsoft Defender for microsoft Defender for Office 365」 を参照してください。

> [!NOTE]
> フィルター処理が適切に機能するには、メールボックスで迷惑メール ルールを有効にする必要があります。 既定では有効になっていますが、フィルター処理が機能していないように見える場合は、チェックする必要があります。 詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

この記事では、既定の設定と、ユーザーを保護するために推奨される Standard と Strict の設定について説明します。 この表には、Microsoft 365 Defender ポータルと PowerShell (Exchange Online PowerShell またはスタンドアロン Exchange Online Protection PowerShell の設定が含まれています(Exchange Online)。

> [!TIP]
> PowerShell Office 365高度な脅威保護推奨構成アナライザー (ORCA) モジュールを使用すると、(管理者) これらの設定の現在の値を見つけるのに役立ちます。 具体的には **、Get-ORCAReport** コマンドレットは、スパム対策、フィッシング対策、その他のメッセージの衛生設定の評価を生成します。 ORCA モジュールは、 からダウンロードできます <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング対策の保護

スパム対策、マルウェア対策、フィッシング対策は、管理者が構成できる EOP 機能です。 次の標準構成または厳密な構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>「EOP のスパム対策ポリシーの設定」

スパム対策ポリシーを作成および構成するには [、「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**スパム プロパティの一括&しきい値**||||
|**バルク メールのしきい値** <p> _BulkThreshold_|7 |6 |4 |詳細については [、「EOP のバルク 苦情レベル (BCL)」を参照してください](bulk-complaint-level-values.md)。|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|この設定は PowerShell でのみ使用できます。|
|**スパム スコアの設定を増やす**|オフ|オフ|オフ|これらの設定はすべて、高度なスパム フィルター (ASF) の一部です。 詳細については、この記事の「 [スパム対策ポリシーの ASF](#asf-settings-in-anti-spam-policies) 設定」セクションを参照してください。|
|**スパム設定としてマーク** する|オフ|オフ|オフ|これらの設定の大部分は ASF の一部です。 詳細については、この記事の「 [スパム対策ポリシーの ASF](#asf-settings-in-anti-spam-policies) 設定」セクションを参照してください。|
|**特定の言語が含まれる** <p> _EnableLanguageBlockList_ <p> _LanguageBlockList_|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|この設定に関する具体的な推奨事項はありません。 ビジネス ニーズに基づいて、特定の言語でメッセージをブロックできます。|
|**これらの国から** <p> _EnableRegionBlockList_ <p> _RegionBlockList_|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|この設定に関する具体的な推奨事項はありません。 ビジネス ニーズに基づいて、特定の国からのメッセージをブロックできます。|
|**テスト モード** (_TestModeAction_)|**なし**|**なし**|**なし**|この設定は ASF の一部です。 詳細については、この記事の「 [スパム対策ポリシーの ASF](#asf-settings-in-anti-spam-policies) 設定」セクションを参照してください。|
|**Actions**|||||
|**スパム** 検出アクション <p> _SpamAction_|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|**信頼度の高いスパム** 検出アクション <p> _HighConfidenceSpamAction_|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**フィッシング検出** アクション <p> _PhishSpamAction_|**検疫メッセージ** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**高信頼フィッシング検出** アクション <p> _HighConfidencePhishAction_|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**一括** 検出アクション <p> _BulkSpamAction_|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**メッセージを迷惑メール フォルダーに移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|**この数日間、検疫にスパムを保持する** <p> _QuarantineRetentionPeriod_|15 日|30 日間|30 日間||
|**スパムの安全に関するヒントを有効にする** <p> _InlineSafetyTipsEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|フィッシング メッセージに対してゼロ時間自動削除 (ZAP) を有効にする <p> _PhishZapEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|スパム メッセージの ZAP を有効にする <p> _SpamZapEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**[エンド ユーザーのスパム通知を有効にする]**  このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。 <p> _EnableEndUserSpamNotifications_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**エンド ユーザーのスパム通知を 1 日ごとに送信する** <p> _EndUserSpamNotificationFrequency_|3 日間|3 日間|3 日間||
|**[ブロック&を許可する]**|||||
|許可されている送信者 <p> _AllowedSenders_|なし|なし|なし||
|許可されている送信者ドメイン <p> _AllowedSenderDomains_|なし|なし|なし|許可された送信者リストにドメインを追加すると、非常に悪い考えです。 攻撃者は、それ以外の場合はフィルター処理される電子メールを送信できます。 <p> スプー [フィン](learn-about-spoof-intelligence.md) グ インテリジェンスインサイトとテナント許可 [/](tenant-allow-block-list.md) ブロックリストを使用して、組織の電子メール ドメイン内の送信者の電子メール アドレスをスプーフィングしているすべての送信者、または外部ドメインの送信者の電子メール アドレスをスプーフィングしているすべての送信者を確認します。|
|受信拒否の送信者 <p> _BlockedSenders_|なし|なし|なし||
|受信拒否ドメイン <p> _BlockedSenderDomains_|なし|なし|なし||
|

#### <a name="asf-settings-in-anti-spam-policies"></a>スパム対策ポリシーの ASF 設定

非推奨のプロセスにあるスパム対策ポリシーには、多くの高度なスパム フィルター (ASF) 設定があります。 これらの機能の減価償却のタイムラインの詳細については、この記事の外部で伝達されます。

標準レベルと厳密レベルの両方で、次の ASF 設定 **をオフ****のままにすることをお****勧** めします。 ASF 設定の詳細については、「EOP の高度なスパム [フィルター (ASF) 設定」を参照してください](advanced-spam-filtering-asf-options.md)。

<br>

****

|セキュリティ機能名|コメント|
|---|---|
|**リモート サイトへのイメージ リンク** (_IncreaseScoreWithImageLinks_)||
|**URL の数値 IP アドレス** (_IncreaseScoreWithNumericIps_)||
|**他のポートへの URL リダイレクト** (_IncreaseScoreWithRedirectToOtherPort_)||
|**.biz または .info Web サイトへのリンク** (_IncreaseScoreWithBizOrInfoUrls_)||
|**空のメッセージ** (_MarkAsSpamEmptyMessages_)||
|**HTML にタグを埋** め込む (_MarkAsSpamEmbedTagsInHtml_)||
|**HTML の JavaScript または VBScript** (_MarkAsSpamJavaScriptInHtml_)||
|**HTML のフォーム タグ** (_MarkAsSpamFormTagsInHtml_)||
|**HTML のフレームタグまたは iframe** タグ (_MarkAsSpamFramesInHtml_)||
|**HTML の Web バグ** (_MarkAsSpamWebBugsInHtml_)||
|**HTML のオブジェクト タグ** (_MarkAsSpamObjectTagsInHtml_)||
|**機密性の高** い単語 (_MarkAsSpamSensitiveWordList_)||
|**SPF レコード: ハードフェール** (_MarkAsSpamSpfRecordHardFail_)||
|**送信者 ID フィルターのハード失敗** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|**テスト モード** (_TestModeAction_)|アクションとしてテストをサポートするASF 設定の場合は、テスト モード アクションを **[** なし] 、既定 **の X-Header** テキストの追加、**または [Bcc** メッセージの送信] (、または) に `None` `AddXHeader` 構成できます `BccMessage` 。 詳細については [、「ASF 設定を有効、無効、またはテストする」を参照してください](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)。|
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパム ポリシー設定

送信スパム ポリシーを作成および構成するには、「EOP で送信スパム フィルターを構成する」 [を参照してください](configure-the-outbound-spam-policy.md)。

サービスの既定の送信制限の詳細については、「送信制限」 [を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**外部メッセージの制限を設定する** <p> _RecipientLimitExternalPerHour_|0|500|400|既定値 0 は、サービスの既定値を使用します。|
|**内部メッセージの制限を設定する** <p> _RecipientLimitInternalPerHour_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**1 日のメッセージ制限を設定する** <p> _RecipientLimitPerDay_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**メッセージの制限に達したユーザーに対する制限** <p> _ActionWhenThresholdReached_|**メールの送信を次の日までユーザーに制限する** <p> `BlockUserForToday`|**ユーザーによるメールの送信を制限する** <p> `BlockUser`|**ユーザーによるメールの送信を制限する** <p> `BlockUser`||
|**自動転送ルール** <p> _AutoForwardingMode_|**自動 - システム制御** <p> `Automatic`|**自動 - システム制御** <p> `Automatic`|**自動 - システム制御** <p> `Automatic`|
|**これらの制限を超える送信メッセージのコピーをこれらのユーザーとグループに送信する** <p> _BccSuspiciousOutboundMail_ <p> _BccSuspiciousOutboundAdditionalRecipients_|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|この設定に関する具体的な推奨事項はありません。 <p> この設定は、既定の送信スパム ポリシーでのみ機能します。 作成したカスタム送信スパム ポリシーでは機能しません。|
|**送信スパムの送信によって送信者がブロックされた場合、これらのユーザーとグループに通知する** <p> _NotifyOutboundSpam_ <p> _NotifyOutboundSpamRecipients_|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|ユーザーが [ポリシー](../../compliance/alert-policies.md)の制限を超えてブロックされている場合、ユーザーが電子メールの送信を制限された既定のアラート ポリシーは **、TenantAdmins** ( Global **admins**) グループのメンバーに既に電子メール通知を送信します。 **送信スパム ポリシーでこの** 設定ではなく、アラート ポリシーを使用して管理者や他のユーザーに通知することを強く推奨します。 手順については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。|
|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成および構成するには [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**保護設定**|||||
|**共通の添付ファイル フィルターを有効にする** <p> _EnableFileFilter_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|この設定は、添付ファイルの内容に関係なく、ファイルの種類に基づいて実行可能な添付ファイルを含むメッセージを検疫します。|
|**マルウェアに対して 0 時間自動削除を有効にする** <p> _ZapEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**受信者の通知**|||||
|**メッセージがマルウェアとして検疫された場合に受信者に通知する** <p> _操作_|未選択 <p> _DeleteMessage_|未選択 <p> _DeleteMessage_|未選択 <p> _DeleteMessage_|電子メールの添付ファイルでマルウェアが検出された場合、メッセージは検疫され、管理者だけが解放できます。|
|**送信者の通知**|||||
|**メッセージがマルウェアとして検疫された場合に内部送信者に通知する** <p> _EnableInternalSenderNotifications_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`||
|**メッセージがマルウェアとして検疫された場合に外部送信者に通知する** <p> _EnableExternalSenderNotifications_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`||
|**管理者の通知**|||||
|**内部送信者からの配信不能メッセージについて管理者に通知する** <p> _EnableInternalSenderAdminNotifications_ <p> _InternalSenderAdminAddress_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|この設定に関する具体的な推奨事項はありません。|
|**外部送信者からの配信不能メッセージについて管理者に通知する** <p> _EnableExternalSenderAdminNotifications_ <p> _ExternalSenderAdminAddress_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|この設定に関する具体的な推奨事項はありません。|
|**通知のカスタマイズ**||||これらの設定に関する具体的な推奨事項はありません。|
|**カスタマイズされた通知テキストを使用する** <p> _CustomNotifications_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`||
|**From name** <p> _CustomFromName_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**差出人アドレス** <p> _CustomFromAddress_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**内部送信者からのメッセージの通知をカスタマイズする**||||これらの設定は、メッセージがマルウェアとして検疫された場合に内部送信者に通知するか、内部送信者からの未配信メッセージについて管理者に通知するが選択されている場合にのみ使用されます。|
|**件名** <p> _CustomInternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**メッセージ** <p> _CustomInternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**外部送信者からのメッセージの通知をカスタマイズする**||||これらの設定は、メッセージがマルウェアとして検疫された場合に外部送信者に通知するか、外部送信者からの配信不能メッセージについて管理者に通知するが選択されている場合にのみ使用されます。|
|**[件名]** <p> _CustomExternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**メッセージ** <p> _CustomExternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP フィッシング対策ポリシー設定

これらの設定の詳細については、「スプーフィング設定」 [を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。 これらの設定を構成するには [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**フィッシングのしきい値&保護**|||||
|**スプーフィング インテリジェンスを有効にする** <p> _EnableSpoofIntelligence_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**Actions**|||||
|**メッセージがスプーフィングとして検出された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、スプーフィング インテリジェンスの分析情報に示すように自動的に[](learn-about-spoof-intelligence.md)ブロックされたスプーフィングされた送信者、またはテナント許可/ブロック一覧で手動でブロックされた送信者に[適用されます](tenant-allow-block-list.md)。|
|**最初の連絡先を表示安全性のヒント** <p> _EnableFirstContactSafetyTips_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|詳細については、「First [contact 安全性のヒント」 を参照してください](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**スプーフィング用の認証されていない送信者の表示 (?)** <p> _EnableUnauthenticatedSender_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|未確認のスプーフィングされた送信者の場合は、Outlookに疑問符 (?) を追加します。 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**"via" タグを表示する** <p> _EnableViaTag_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|DKIM 署名または chris@contoso.com MAIL FROM アドレスのドメインと異なる場合は、from アドレスに via タグ (fabrikam.com 経由で) を **追加** します。 <p> 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365セキュリティ

その他のセキュリティ上の利点には、Microsoft Defender for microsoft Defender Office 365があります。 最新のニュースと情報については、「Defender for [Office 365」 の新機能を参照Office 365。](whats-new-in-defender-for-office-365.md)

> [!IMPORTANT]
>
> - Microsoft Defender for microsoft Defender for Office 365フィッシング対策ポリシー[](set-up-anti-phishing-policies.md#spoof-settings)は、すべての受信者にスプーフィング保護とメールボックス インテリジェンスを提供します。 ただし、既定のポリシーでは、[他の](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)利用可能[](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)な偽装保護機能と高度な設定が構成または有効になっていません。 すべての保護機能を有効にするには、既定のフィッシング対策ポリシーを変更するか、追加のフィッシング対策ポリシーを作成します。
>
> - 組織のすべての受信者をセーフ自動的に保護するセーフリンク ポリシーまたは添付ファイル ポリシーの既定のポリシーはありません。 保護を取得するには、リンク ポリシーと添付ファイル ポリシーセーフ少なくとも 1 セーフする必要があります。
>
> - [セーフ SharePoint、OneDrive、Microsoft Teams](mdo-for-spo-odb-and-teams.md)ドキュメント保護の添付ファイルには、セーフ[セーフ](safe-docs.md)リンク ポリシーにセーフはありません。

サブスクリプションに Microsoft Defender for Office 365 が含まれる場合、または Office 365 用の Defender をアドオンとして購入した場合は、次の Standard 構成または Strict 構成を設定します。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender のフィッシング対策ポリシー Office 365

EOP のお客様は、前述のように基本的なフィッシング対策を受け取りますが、Defender for Office 365 には、攻撃を防止、検出、修復するためのより多くの機能と制御が含まれています。 これらのポリシーを作成および構成するには[、「Defender で](configure-mdo-anti-phishing-policies.md)フィッシング対策ポリシーを構成する」を参照Office 365。

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender のフィッシング対策ポリシーの詳細設定 (Office 365

この設定の詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの高度なフィッシング[のしきい値」を参照してください](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 この設定を構成するには[、「Defender で](configure-mdo-anti-phishing-policies.md)フィッシング対策ポリシーを構成する」を参照Office 365。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**フィッシングメールのしきい値** <p> _PhishThresholdLevel_|**1 - Standard** <p> `1`|**2 - アグレッシブ** <p> `2`|**3 - より積極的** <p> `3`||
|

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender のフィッシング対策ポリシーの偽装Office 365

これらの設定の詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの偽装[設定」を参照してください](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 これらの設定を構成するには[、「Defender で](configure-mdo-anti-phishing-policies.md)フィッシング対策ポリシーを構成する」を参照Office 365。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**フィッシングのしきい値&保護**|||||
|**ユーザーによる保護の有効化** (偽装ユーザー保護)<p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|未選択 <p> `$false` <p> none|選択済み <p> `$true` <p> \<list of users\>|選択済み <p> `$true` <p> \<list of users\>|主要な役割にユーザー (メッセージ送信者) を追加することをお勧めします。 内部的には、保護された送信者は、CEO、CFO、その他の上級リーダーである可能性があります。 外部的には、保護された送信者には、評議会のメンバーまたは取締役会が含まれる可能性があります。|
|**ドメインの保護を有効にする** (偽装されたドメイン保護)|未選択|選択済み|選択済み||
|**所有するドメインを含める** <p> _EnableOrganizationDomainsProtection_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**カスタム ドメインを含める** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|オフ <p> `$false` <p> none|選択済み <p> `$true` <p> \<list of domains\>|選択済み <p> `$true` <p> \<list of domains\>|所有しているのではなく、頻繁に操作するドメイン (送信者ドメイン) を追加することをお勧めします。|
|**信頼できる送信者とドメインの追加** <p> _ExcludedSenders_ <p> _ExcludedDomains_|なし|なし|なし|組織によっては、偽装の試行として誤って識別される送信者またはドメインを追加することをお勧めします。|
|**メールボックス インテリジェンスを有効にする** <p> _EnableMailboxIntelligence_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**偽装保護のインテリジェンスを有効にする** <p> _EnableMailboxIntelligenceProtection_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|この設定では、メールボックス インテリジェンスによる偽装検出に対して指定されたアクションを使用できます。|
|**Actions**|||||
|**偽装ユーザーとしてメッセージが検出された場合** <p> _TargetedUserProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**偽装ドメインとしてメッセージが検出された場合** <p> _TargetedDomainProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**メールボックス インテリジェンスがユーザーを検出して偽装した場合** <p> _MailboxIntelligenceProtectionAction_|**アクションを適用しない** <p> `NoAction`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`||
|**ユーザーの偽装を表示安全性のヒント** <p> _EnableSimilarUsersSafetyTips_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**[ドメイン偽装の表示] 安全性のヒント** <p> _EnableSimilarDomainsSafetyTips_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**ユーザー偽装の異常な文字を表示する安全性のヒント** <p> _EnableUnusualCharactersSafetyTips_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender の EOP フィッシング対策ポリシー設定 (Office 365

これらは、EOP のスパム対策ポリシー設定で使用できるのと同 [じ設定です](#eop-anti-spam-policy-settings)。

スプーフィング設定は相互に関連付けされますが、[最初の連絡先を表示する]**安全性のヒントスプー** フィング設定に依存はありません。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**フィッシングのしきい値&保護**|||||
|**スプーフィング インテリジェンスを有効にする** <p> _EnableSpoofIntelligence_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**Actions**|||||
|**メッセージがスプーフィングとして検出された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、スプーフィング インテリジェンスの分析情報に示すように自動的に[](learn-about-spoof-intelligence.md)ブロックされたスプーフィングされた送信者、またはテナント許可/ブロック一覧で手動でブロックされた送信者に[適用されます](tenant-allow-block-list.md)。|
|**最初の連絡先を表示安全性のヒント** <p> _EnableFirstContactSafetyTips_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|詳細については、「First [contact 安全性のヒント」 を参照してください](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**スプーフィング用の認証されていない送信者の表示 (?)** <p> _EnableUnauthenticatedSender_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|未確認のスプーフィングされた送信者の場合は、Outlookに疑問符 (?) を追加します。 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**"via" タグを表示する** <p> _EnableViaTag_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|DKIM 署名または chris@contoso.com MAIL FROM アドレスのドメインと異なる場合は、from アドレスに via タグ (fabrikam.com 経由で) を **追加** します。 <p> 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|

### <a name="safe-attachments-settings"></a>セーフ添付ファイルの設定

セーフMicrosoft Defender for Office 365の添付ファイルには、セーフ 添付ファイル ポリシーとの関係を持つグローバル設定、および各 セーフ リンク ポリシーに固有の設定が含まれます。 詳細については、「Defender[セーフ添付ファイル」を参照Office 365。](safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>添付ファイルのセーフ設定

これらの設定を構成[セーフ](turn-on-mdo-for-spo-odb-and-teams.md)するには、「SharePoint、OneDrive、OneDrive、Microsoft Teams および セーフ ドキュメントの添付ファイルを有効にする」を参照[Microsoft 365 E5。](safe-docs.md)

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**SharePoint、OneDrive、Microsoft Teams 用の Microsoft Defender for Office 365 を有効にする** <p> _EnableATPForSPOTeamsODB_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`||
|**クライアントのセーフドキュメントを有効Officeする** <p> _EnableSafeDocs_|オフ <p> `$false`|オン <p> `$true`|オン <p> `$true`|この機能は、ライセンスまたはライセンスのMicrosoft 365 E5とMicrosoft 365 E5 Securityです。 詳細については[、「Microsoft Defender セーフドキュメント」を参照Office 365。](safe-docs.md)|
|**ドキュメントでファイルが悪意のあると特定セーフ場合でも、保護されたビューをクリックできます** <p> _AllowSafeDocsOpen_|オフ <p> `$false`|オフ <p> `$false`|オフ <p> `$false`|この設定は、ドキュメントのセーフです。|
|

#### <a name="safe-attachments-policy-settings"></a>セーフ添付ファイルポリシーの設定

これらの設定を構成するには、「Defender for セーフの添付ファイル ポリシーを設定する[」をOffice 365。](set-up-safe-attachments-policies.md)

PowerShell では、これらの設定に [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) コマンドレットと [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、添付ファイル ポリシーの既定セーフはありません。 [既定] 列の値は、新しい添付ファイル セーフの既定値です。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**セーフ添付ファイル不明のマルウェア応答** <p> _有効にして__操作する_|**オフ** <p> `-Enable $false` と `-Action Block`|**Block** <p> `-Enable $true` と `-Action Block`|**Block** <p> `-Enable $true` と `-Action Block`|Enable パラメーター _が_ 有効 _$false、Action_ パラメーターの値は関係ありません。|
|**検出された添付ファイルを含む添付ファイルのリダイレクト** : **リダイレクトを有効にする** <p> _リダイレクト_ <p> _RedirectAddress_|選択されていないと、電子メール アドレスが指定されていません。 <p> `-Redirect $false` <p> _RedirectAddress が_ 空白 ( `$null` )|電子メール アドレスを選択して指定します。 <p> `$true` <p> 電子メール アドレス|電子メール アドレスを選択して指定します。 <p> `$true` <p> 電子メール アドレス|メッセージをセキュリティ管理者にリダイレクトして確認します。|
|**スキャンが完了できないセーフ添付ファイル検出応答を適用する (タイムアウトまたはエラー)** <p> _ActionOnError_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|

### <a name="safe-links-settings"></a>セーフリンクの設定

セーフDefender for Office 365 のリンクには、アクティブな セーフ リンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定と、各 セーフ リンク ポリシーに固有の設定が含まれます。 詳細については、「Defender[セーフリンク」を参照Office 365。](safe-links.md)

#### <a name="global-settings-for-safe-links"></a>リンクのグローバルセーフ設定

これらの設定を構成するには、「Defender for セーフリンクのグローバル設定を構成する[」をOffice 365。](configure-global-settings-for-safe-links.md)

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**次の URL をブロックする** <p> _ExcludedUrls_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`|この設定に関する具体的な推奨事項はありません。 <p> 詳細については、「リンク」の「次の URL をブロックする[」をセーフしてください](safe-links.md#block-the-following-urls-list-for-safe-links)。
|**アプリセーフリンクをOffice 365する** <p> _EnableSafeLinksForO365Clients_|オン <p> `$true`|オン <p> `$true`|オン <p> `$true`|デスクトップセーフモバイル (iOS Office 365 Android) アプリでサポートされているリンクを使用します。 詳細については、「[Office 365 アプリ向けの安全なリンク設定](safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。|
|**ユーザーがアプリで保護されたリンクをクリックOffice 365しない** <p> _TrackClicks_|オン <p> `$false`|オフ <p> `$true`|オフ <p> `$true`|この設定をオフにします _(TrackClicks_ を設定) は、サポートされているアプリのユーザークリック `$true` Office 365追跡します。|
|**ユーザーがアプリの元の URL をクリックOffice 365しない** <p> _AllowClickThrough_|オン <p> `$false`|オン <p> `$false`|オン <p> `$false`|この設定 _(AllowClickThrough_ をに設定) をオンにすると、サポートされているアプリの元の URL をクリックOffice 365 `$false` されません。|
|

#### <a name="safe-links-policy-settings"></a>セーフリンク ポリシーの設定

これらの設定を構成するには、「Microsoft Defender で セーフ リンク ポリシーを設定[する」を参照Office 365。](set-up-safe-links-policies.md)

PowerShell では、これらの設定に [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) コマンドレットと [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定のリンク ポリシーセーフはありません。 [既定] 列の値は、作成した新しいリンク セーフの既定値です。

<br>

****

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**保護設定**|||||
|**メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する** <p> _IsEnabled_|**オフ** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`||
|**ネットワーク内の不明または潜在的に悪意のある URL のアクションを選択Microsoft Teams** <p> _EnableSafeLinksForTeams_|**オフ** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`||
|**ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する** <p> _ScanUrls_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**メッセージを配信する前に URL のスキャンが完了するのを待ちます** <p> _DeliverMessageAfterScan_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**[セーフ] 組織内で送信された電子メール メッセージへのリンクを適用する** <p> _EnableForInternalSenders_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**ユーザーのクリックを追跡しない** <p> _DoNotTrackUserClicks_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|この設定をオフにします _(DoNotTrackUserClicks_ を設定 `$false` ) は、ユーザーのクリックを追跡します。|
|**ユーザーに元の URL へのクリックを許可しない** <p> _DoNotAllowClickThrough_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|この設定 _(DoNotAllowClickThrough_ をに設定) をオンにすると `$true` 、元の URL へのクリックスルーが禁止されます。|
|**通知ページと警告ページに組織のブランド化を表示する** <p> _EnableOrganizationBranding_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|この設定に関する具体的な推奨事項はありません。 <p> この設定を有効にする前に、「組織の新しいテーマをカスタマイズMicrosoft 365、会社のロゴをアップロードする」の[手順](../../admin/setup/customize-your-organization-theme.md)に従う必要があります。|
|**次の URL を書き換えない** <p> _DoNotRewriteUrls_|未選択 <p> 空白|未選択 <p> 空白|未選択 <p> 空白|この設定に関する具体的な推奨事項はありません。 詳細については、「リンク ポリシー」の「次の[URL を](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)書き換セーフしてください。|
|**通知**|||||
|**ユーザーに通知する方法**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|この設定に関する具体的な推奨事項はありません。 <p> [カスタム通知 **テキストを使用する** ]_(CustomNotificationText)_ を選択して、使用するカスタマイズされた通知テキストを入力できます。 ユーザーの言語にカスタム **通知Microsoft 翻訳ツール** を翻訳するには、[自動ローカライズに使用する]_(UseTranslatedNotificationText)_ を選択します。
|

## <a name="related-articles"></a>関連記事

- メール フロー ルール (トランスポート Exchangeとも呼ばれる) のベスト プラクティス **をお探し** ですか? 「[メール フロー ルールの構成に](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)関するベスト プラクティス」を参照Exchange Online。

- 管理者とユーザーは、誤検知 (良い電子メールが不良とマークされている) と誤検知 (悪いメールが許可されている) を分析のために Microsoft に提出できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- これらのリンクを使用して[、EOP](/exchange/standalone-eop/set-up-your-eop-service)サービスをセットアップし、Microsoft  Defender for  [Office 365。](defender-for-office-365.md) 「脅威に対する保護」の「脅威に対[する保護」](protect-against-threats.md)の役に立つ指示を忘Office 365してください。

- **Windows** のセキュリティ基準については、GPO/オンプレミス オプション [](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)のセキュリティ 基準を取得できる場所と [、Intune](/intune/protect/security-baselines)ベースのセキュリティ用に Intune で Windows 10 デバイスを構成するためのセキュリティ 基準を使用します。 最後に、Microsoft Defender for Endpoint と Microsoft Intune セキュリティ ベースラインの比較については[、「Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)と Intune のセキュリティ ベースラインの比較Windows参照してください。
