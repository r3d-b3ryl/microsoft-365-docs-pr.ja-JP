---
title: EOP とセキュリティ設定のDefender for Office 365 Microsoft の推奨事項
keywords: Office 365 のセキュリティ推奨事項、Sender Policy Framework、ドメイン ベースのメッセージレポートと準拠、DomainKeys Identified Mail、手順、動作方法、セキュリティ ベースライン、EOP のベースライン、Defender for Office 365 のベースライン、Defender for Office 365 のセットアップ、EOP のセットアップ、構成Defender for Office 365、EOP、セキュリティ構成を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: セキュリティ設定 (EOP) とExchange Online Protectionのベスト プラクティスDefender for Office 365は何ですか? 標準保護に関する現在の推奨事項は何ですか? より厳密にしたい場合は、何を使用する必要がありますか? また、この機能も使用する場合、どのような追加Defender for Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4b6c9df3b8c458aaf548ff9c8cfe8cc51fa5824
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507174"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP および Microsoft Defender for Office 365 セキュリティの推奨設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** は、Microsoft 365 サブスクリプションのセキュリティの中核であり、悪意のあるメールが従業員の受信トレイに届かされるのを防ごうのに役立ちます。 しかし、より高度な新しい攻撃が毎日出現する中で、多くの場合、保護の強化が必要になります。 **Microsoft Defender for Office 365** 1 またはプラン 2 には、管理者にセキュリティ、制御、調査の層を追加する追加機能が含まれている。

セキュリティ管理者はセキュリティ設定をカスタマイズすることができますが、EOP には 2 つのセキュリティ レベルと、推奨Microsoft Defender for Office 365標準と Strict の 2 つのセキュリティ レベル  **があります**。 お客様の環境とニーズは異なりますが、これらのレベルのフィルター処理は、ほとんどの状況で望ましくないメールが従業員の受信トレイに届かされるのを防ぐのに役立ちます。

標準設定または厳密な設定をユーザーに自動的に適用するには、「EOP およびサーバーのセキュリティ ポリシーを事前に設定する[」を参照](preset-security-policies.md)Microsoft Defender for Office 365。

この記事では、既定の設定と、ユーザーを保護するために推奨される Standard と Strict の設定について説明します。 この表には、Microsoft 365 Defender ポータルと PowerShell (Exchange Online PowerShell またはスタンドアロン Exchange Online Protection PowerShell のメールボックスのない組織の設定Exchange Onlineされています。

> [!TIP]
> このポータルでは、推奨される標準設定と厳密な設定をMicrosoft 365 Defenderできません。 [ユーザーの保護を有効 **にする]** のような推奨値を変更するには、[PowerShell でExchange Online必要があります](/powershell/exchange/connect-to-exchange-online-powershell)。
>
> PowerShell Office 365高度な脅威保護推奨構成アナライザー (ORCA) モジュールを使用すると、(管理者) これらの設定の現在の値を見つけるのに役立ちます。 具体的には、 **Get-ORCAReport** コマンドレットは、スパム対策、フィッシング対策、その他のメッセージの衛生設定の評価を生成します。 ORCA モジュールは、 からダウンロードできます <https://www.powershellgallery.com/packages/ORCA/>。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング対策の保護

スパム対策、マルウェア対策、フィッシング対策は、管理者が構成できる EOP 機能です。 次の標準構成または厳密な構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>「EOP のスパム対策ポリシーの設定」

スパム対策ポリシーを作成および構成するには、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。

|セキュリティ機能名|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**迷惑メールのプロパティ&メールの一括しきい値**|||||
|**バルク メールのしきい値** <br/><br/> _BulkThreshold_|7 |6 |4|詳細については、「 [EOP のバルク 苦情レベル (BCL)」を参照してください](bulk-complaint-level-values.md)。|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|この設定は PowerShell でのみ使用できます。|
|**スパム スコアの設定を増やす**|Off|Off|Off|これらの設定はすべて、高度なスパム フィルター (ASF) の一部です。 詳細については、この記事の「 [スパム対策ポリシーの ASF](#asf-settings-in-anti-spam-policies) 設定」セクションを参照してください。|
|**スパム設定としてマーク** する|Off|Off|Off|これらの設定の大部分は ASF の一部です。 詳細については、この記事の「 [スパム対策ポリシーの ASF](#asf-settings-in-anti-spam-policies) 設定」セクションを参照してください。|
|**特定の言語が含まれる** <br/><br/> _EnableLanguageBlockList_ <br/><br/> _LanguageBlockList_|**オフ** <br/><br/> `$false` <br/><br/> 空白|**オフ** <br/><br/> `$false` <br/><br/> 空白|**オフ** <br/><br/> `$false` <br/><br/> 空白|この設定に関する具体的な推奨事項はありません。 ビジネス ニーズに基づいて、特定の言語でメッセージをブロックできます。|
|**これらの国から** <br/><br/> _EnableRegionBlockList_ <br/><br/> _RegionBlockList_|**オフ** <br/><br/> `$false` <br/><br/> 空白|**オフ** <br/><br/> `$false` <br/><br/> 空白|**オフ** <br/><br/> `$false` <br/><br/> 空白|この設定に関する具体的な推奨事項はありません。 ビジネス ニーズに基づいて、特定の国からのメッセージをブロックできます。|
|**テスト モード** (_TestModeAction_)|**なし**|**なし**|**なし**|この設定は ASF の一部です。 詳細については、この記事の「 [スパム対策ポリシーの ASF](#asf-settings-in-anti-spam-policies) 設定」セクションを参照してください。|
|**アクション**||||[検疫メッセージ] **を選択した場合** は、[ **検疫ポリシーの選択] ボックス** を使用できます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作を定義します。 <br/><br/> 新しいスパム対策ポリシーを作成する場合、空白の値は、既定の検疫ポリシーを使用して、その特定の評決によって検疫されたメッセージの履歴機能を定義します (AdminOnlyAccessPolicy for High **confidence** フィッシング;それ以外の場合は DefaultFullAccessPolicy)。 <br/><br/> 管理者は、ユーザーに対して制限の厳しい機能または制限の少ない機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**スパム** 検出アクション <br/><br/> _SpamAction_|**メッセージを迷惑メール フォルダーに移動する** <br/><br/> `MoveToJmf`|**メッセージを迷惑メール フォルダーに移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**信頼度の高いスパム** 検出アクション <br/><br/> _HighConfidenceSpamAction_|**検疫メッセージ** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**フィッシング検出** アクション <br/><br/> _PhishSpamAction_|**検疫メッセージ** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**高信頼フィッシング検出** アクション <br/><br/> _HighConfidencePhishAction_|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**一括** 検出アクション <br/><br/> _BulkSpamAction_|**メッセージを迷惑メール フォルダーに移動する** <br/><br/> `MoveToJmf`|**メッセージを迷惑メール フォルダーに移動する** <br/><br/> `MoveToJmf`|**検疫メッセージ** <br/><br/> `Quarantine`||
|**この数日間、検疫にスパムを保持する** <br/><br/> _QuarantineRetentionPeriod_|15 日間<sup>\*</sup>|30 日間|30 日間|<sup>\*</sup> 既定値は、既定のスパム対策ポリシーでは 15 日間、PowerShell で作成する新しいスパム対策ポリシーでは 15 日間です。 Microsoft 365Defender ポータルで作成する新しいスパム対策ポリシーの規定値は30日です。 <br/><br/> この値は、フィッシング対策ポリシーによって検疫されるメッセージにも影響します。 詳細については、「 [EOP の検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。|
|**スパムの安全に関するヒントを有効にする** <br/><br/> _InlineSafetyTipsEnabled_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|フィッシング メッセージに対してゼロ時間自動削除 (ZAP) を有効にする <br/><br/> _PhishZapEnabled_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|スパム メッセージの ZAP を有効にする <br/><br/> _SpamZapEnabled_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**[ブロック&を許可する]**|||||
|許可されている送信者 <br/><br/> _AllowedSenders_|なし|なし|なし||
|許可されている送信者ドメイン <br/><br/> _AllowedSenderDomains_|なし|なし|なし|許可された送信者リストにドメインを追加すると、非常に悪い考えです。 攻撃者は、それ以外の場合はフィルター処理される電子メールを送信できます。 <br/><br/> スプー [フィン](learn-about-spoof-intelligence.md) グ インテリジェンスインサイトとテナント許可 [/](tenant-allow-block-list.md) ブロックリストを使用して、組織の電子メール ドメイン内の送信者の電子メール アドレスをスプーフィングしているすべての送信者、または外部ドメインの送信者の電子メール アドレスをスプーフィングしているすべての送信者を確認します。|
|受信拒否の送信者 <br/><br/> _BlockedSenders_|なし|なし|なし||
|受信拒否ドメイン <br/><br/> _BlockedSenderDomains_|なし|なし|なし||

#### <a name="asf-settings-in-anti-spam-policies"></a>スパム対策ポリシーの ASF 設定

このセクションの表では、スパム対策ポリシーで使用できる高度なスパム フィルター (ASF) 設定について説明します。 これらの設定はすべて、標準 **レベルと厳密** レベル **の両方** で **Off** です。 ASF 設定の詳細については、「EOP の高度なスパム [フィルター (ASF) 設定」を参照してください](advanced-spam-filtering-asf-options.md)。

|セキュリティ機能名|Comment|
|---|---|
|**リモート サイトへのイメージ リンク** (_IncreaseScoreWithImageLinks_)||
|**URL の数値 IP アドレス** (_IncreaseScoreWithNumericIps_)||
|**他のポートへの URL リダイレクト** (_IncreaseScoreWithRedirectToOtherPort_)||
|**.biz または .info Web** サイトへのリンク (_IncreaseScoreWithBizOrInfoUrls_)||
|**空のメッセージ** (_MarkAsSpamEmptyMessages_)||
|**HTML にタグを埋** め込む (_MarkAsSpamEmbedTagsInHtml_)||
|**HTML の JavaScript または VBScript** (_MarkAsSpamJavaScriptInHtml_)||
|**HTML のフォーム タグ** (_MarkAsSpamFormTagsInHtml_)||
|**HTML のフレームタグまたは iframe タグ** (_MarkAsSpamFramesInHtml_)||
|**HTML の Web バグ** (_MarkAsSpamWebBugsInHtml_)||
|**HTML のオブジェクト タグ** (_MarkAsSpamObjectTagsInHtml_)||
|**機密性の高** い単語 (_MarkAsSpamSensitiveWordList_)||
|**SPF レコード: ハードフェール** (_MarkAsSpamSpfRecordHardFail_)||
|**送信者 ID フィルターのハード失敗** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|**テスト モード** (_TestModeAction_)|アクションとしてテストをサポートする  ASF 設定の場合は、テスト モード アクションを **[** なし]、既定 **の X-Header** テキストの追加、**または BCC** メッセージの送信 (`None``AddXHeader`、または) に構成できます`BccMessage`。 詳細については、「 [ASF 設定を有効、無効、またはテストする」を参照してください](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)。|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパム ポリシー設定

送信スパム ポリシーを作成および構成するには、「EOP で送信スパム フィルターを構成する [」を参照してください](configure-the-outbound-spam-policy.md)。

サービスの既定の送信制限の詳細については、「送信制限 [」を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

> [!NOTE]
> 送信スパム ポリシーは、Standard または Strict の事前設定されたセキュリティ ポリシーの一部ではありません。 Standard **と** **Strict の値は**、既定の送信スパム ポリシーまたは作成したカスタム ポリシーで推奨される値を示します。

|セキュリティ機能名|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**外部メッセージの制限を設定する** <br/><br/> _RecipientLimitExternalPerHour_|0|500|400|既定値 0 は、サービスの既定値を使用します。|
|**内部メッセージの制限を設定する** <br/><br/> _RecipientLimitInternalPerHour_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**1 日のメッセージ制限を設定する** <br/><br/> _RecipientLimitPerDay_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**メッセージの制限に達したユーザーに対する制限** <br/><br/> _ActionWhenThresholdReached_|**メールの送信を次の日までユーザーに制限する** <br/><br/> `BlockUserForToday`|**ユーザーによるメールの送信を制限する** <br/><br/> `BlockUser`|**ユーザーによるメールの送信を制限する** <br/><br/> `BlockUser`||
|**自動転送ルール** <br/><br/> _AutoForwardingMode_|**自動 - システム制御** <br/><br/> `Automatic`|**自動 - システム制御** <br/><br/> `Automatic`|**自動 - システム制御** <br/><br/> `Automatic`|
|**これらの制限を超える送信メッセージのコピーをこれらのユーザーとグループに送信する** <br/><br/> _BccSuspiciousOutboundMail_ <br/><br/> _BccSuspiciousOutboundAdditionalRecipients_|未選択 <br/><br/> `$false` <br/><br/> 空白|未選択 <br/><br/> `$false` <br/><br/> 空白|未選択 <br/><br/> `$false` <br/><br/> 空白|この設定に関する具体的な推奨事項はありません。 <br/><br/> この設定は、既定の送信スパム ポリシーでのみ機能します。 作成したカスタム送信スパム ポリシーでは機能しません。|
|**送信スパムの送信によって送信者がブロックされた場合、これらのユーザーとグループに通知する** <br/><br/> _NotifyOutboundSpam_ <br/><br/> _NotifyOutboundSpamRecipients_|未選択 <br/><br/> `$false` <br/><br/> 空白|未選択 <br/><br/> `$false` <br/><br/> 空白|未選択 <br/><br/> `$false` <br/><br/> 空白|ポリシー [の制限](../../compliance/alert-policies.md)を超えてユーザーがブロックされた場合、ユーザーが電子メールの送信を制限された既定のアラート ポリシーは、**TenantAdmins (Global admins**) グループのメンバーに既に電子メール通知を送信します。 **送信スパム ポリシーでこの** 設定ではなく、アラート ポリシーを使用して管理者や他のユーザーに通知することを強く推奨します。 手順については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成および構成するには、「 [EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

|セキュリティ機能名|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**保護設定**|||||
|**共通の添付ファイル フィルターを有効にする** <br/><br/> _EnableFileFilter_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|この設定は、添付ファイルの内容に関係なく、ファイルの種類に基づいて実行可能な添付ファイルを含むメッセージを検疫します。|
|**マルウェアに対して 0 時間自動削除を有効にする** <br/><br/> _ZapEnabled_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**検疫ポリシー**|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|新しいマルウェア対策ポリシーを作成する場合、空白の値は、既定の検疫ポリシーを使用して、マルウェアとして検疫されたメッセージの履歴機能を定義します (AdminOnlyAccessPolicy)。 <br/><br/> 管理者は、ユーザーに対してより多くの機能を定義するカスタム検疫ポリシーを作成および選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**受信者の通知**|||||
|**メッセージがマルウェアとして検疫された場合に受信者に通知する** <br/><br/> _操作_|未選択 <br/><br/> _DeleteMessage_|未選択 <br/><br/> _DeleteMessage_|未選択 <br/><br/> _DeleteMessage_|電子メールの添付ファイルでマルウェアが検出された場合、メッセージは検疫され、管理者だけが解放できます。|
|**送信者の通知**|||||
|**メッセージがマルウェアとして検疫された場合に内部送信者に通知する** <br/><br/> _EnableInternalSenderNotifications_|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`||
|**メッセージがマルウェアとして検疫された場合に外部送信者に通知する** <br/><br/> _EnableExternalSenderNotifications_|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`||
|**管理者の通知**|||||
|**内部送信者からの配信不能メッセージについて管理者に通知する** <br/><br/> _EnableInternalSenderAdminNotifications_ <br/><br/> _InternalSenderAdminAddress_|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|この設定に関する具体的な推奨事項はありません。|
|**外部送信者からの配信不能メッセージについて管理者に通知する** <br/><br/> _EnableExternalSenderAdminNotifications_ <br/><br/> _ExternalSenderAdminAddress_|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|この設定に関する具体的な推奨事項はありません。|
|**通知のカスタマイズ**||||これらの設定に関する具体的な推奨事項はありません。|
|**カスタマイズされた通知テキストを使用する** <br/><br/> _CustomNotifications_|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`||
|**From name** <br/><br/> _CustomFromName_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**差出人アドレス** <br/><br/> _CustomFromAddress_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**内部送信者からのメッセージの通知をカスタマイズする**||||これらの設定は、メッセージがマルウェアとして検疫された場合に内部送信者に通知するか、内部送信者からの未配信メッセージについて管理者に通知するが選択されている場合にのみ使用されます。|
|**件名** <br/><br/> _CustomInternalSubject_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**メッセージ** <br/><br/> _CustomInternalBody_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**外部送信者からのメッセージの通知をカスタマイズする**||||これらの設定は、メッセージがマルウェアとして検疫された場合に外部送信者に通知するか、外部送信者からの配信不能メッセージについて管理者に通知するが選択されている場合にのみ使用されます。|
|**[件名]** <br/><br/> _CustomExternalSubject_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||
|**メッセージ** <br/><br/> _CustomExternalBody_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`||

### <a name="eop-anti-phishing-policy-settings"></a>EOP フィッシング対策ポリシー設定

これらの設定の詳細については、「スプーフィング設定 [」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。 これらの設定を構成するには、「 [EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

|セキュリティ機能名|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**フィッシングのしきい値&保護**|||||
|**スプーフィング インテリジェンスを有効にする** <br/><br/> _EnableSpoofIntelligence_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**アクション**|||||
|**メッセージがスプーフィングとして検出された場合** <br/><br/> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**メッセージを検疫する** <br/><br/> `Quarantine`|この設定は、スプーフィング インテリジェンスの分析情報に示すように自動的にブロック[](learn-about-spoof-intelligence.md)されたスプーフィングされた送信者、またはテナント許可/ブロック一覧で手動でブロックされた送信者に[適用されます](tenant-allow-block-list.md)。 <br/><br/> [メッセージの **検疫] を** 選択すると、[検疫ポリシーの適用] ボックスを使用して、スプーフィングとして検疫されたメッセージに対してユーザーが実行できる操作を定義する検疫ポリシーを選択できます。 新しいフィッシング対策ポリシーを作成すると、空白の値を指定すると、スプーフィングとして検疫されたメッセージの履歴機能を定義するために既定の検疫ポリシーが使用されます (DefaultFullAccessPolicy)。 <br/><br/> 管理者は、ユーザーに対して制限の厳しい機能または制限の少ない機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**最初の連絡先を表示安全性のヒント** <br/><br/> _EnableFirstContactSafetyTips_|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|詳細については、「First [contact 安全性のヒント」を参照してください](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**スプーフィング用の認証されていない送信者の表示 (?)** <br/><br/> _EnableUnauthenticatedSender_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|未確認のスプーフィングされた送信者に対して、Outlookに疑問符 (?) を追加します。 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**"via" タグを表示する** <br/><br/> _EnableViaTag_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|DKIM 署名または MAIL FROM アドレスのドメインと異なる場合は、from アドレスに via タグ (chris@contoso.com 経由で fabrikam.com) を **追加** します。 <br/><br/> 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365セキュリティ

追加のセキュリティ上の利点には、サブスクリプションMicrosoft Defender for Office 365があります。 最新のニュースと情報については、「新機能[」](whats-new-in-defender-for-office-365.md)を参照Defender for Office 365。

> [!IMPORTANT]
>
> - すべての受信者にスプーフィング保護とメールボックス インテリジェンスMicrosoft Defender for Office 365既定[](set-up-anti-phishing-policies.md#spoof-settings)のフィッシング対策ポリシーが提供されます。 ただし、既定のポリシーでは、[他の](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)利用可能[](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)な偽装保護機能と高度な設定が構成または有効になっていません。 すべての保護機能を有効にするには、既定のフィッシング対策ポリシーを変更するか、追加のフィッシング対策ポリシーを作成します。
>
> - 既定の セーフ 添付ファイル ポリシーまたは セーフ リンク ポリシーは使用できませんが、組み込みの保護プリセット セキュリティ ポリシーは、セーフ 添付ファイル保護と セーフ リンク保護をすべての受信者 (カスタム セーフ 添付ファイル ポリシーまたは セーフ リンク ポリシーで定義されていないユーザー) に提供します。 詳細については、「EOP および EOP のセキュリティ ポリシーを事前に設定[する」を参照Microsoft Defender for Office 365](preset-security-policies.md)。
>
> - [セーフ SharePoint、](mdo-for-spo-odb-and-teams.md)OneDrive、Microsoft Teams [セーフ](safe-docs.md) ドキュメント保護の添付ファイルは、セーフ リンク ポリシーに依存します。

サブスクリプションに Microsoft Defender for Office 365が含まれる場合、またはアドオンとして Defender for Office 365を購入した場合は、次の Standard 構成または Strict 構成を設定します。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>フィッシング対策ポリシーの設定 (Microsoft Defender for Office 365

EOP のお客様は、前述のように基本的なフィッシング対策を受け取りますが、Defender for Office 365 には、攻撃の防止、検出、修復に役立つ機能と制御が含まれています。 これらのポリシーを作成および構成するには、「[フィッシング](configure-mdo-anti-phishing-policies.md)対策ポリシーを構成する」を参照Defender for Office 365。

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>アプリ内のフィッシング対策ポリシーの詳細設定Microsoft Defender for Office 365

この設定の詳細については、「フィッシング対策ポリシーの高度なフィッシングしきい値」を参照[Microsoft Defender for Office 365。](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) この設定を構成するには、「[フィッシング](configure-mdo-anti-phishing-policies.md)対策ポリシーを構成する」を参照Defender for Office 365。

|セキュリティ機能名|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**フィッシングメールのしきい値** <br/><br/> _PhishThresholdLevel_|**1 - Standard** <br/><br/> `1`|**2 - アグレッシブ** <br/><br/> `2`|**3 - より積極的** <br/><br/> `3`||

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>アプリ内のフィッシング対策ポリシーの偽装設定Microsoft Defender for Office 365

これらの設定の詳細については、「アプリのフィッシング対策ポリシーの偽装[設定」を参照](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Microsoft Defender for Office 365。 これらの設定を構成するには、「[フィッシング](configure-mdo-anti-phishing-policies.md)対策ポリシーを構成する」を参照Defender for Office 365。

|セキュリティ機能名|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**フィッシングのしきい値&保護**|||||
|**ユーザーによる保護の有効化** (偽装ユーザー保護) <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|未選択 <br/><br/> `$false` <br/><br/> none|選択済み <br/><br/> `$true` <br/><br/> \<list of users\>|選択済み <br/><br/> `$true` <br/><br/> \<list of users\>|主要な役割にユーザー (メッセージ送信者) を追加することをお勧めします。 内部的には、保護された送信者は、CEO、CFO、その他の上級リーダーである可能性があります。 外部的には、保護された送信者には、評議会のメンバーまたは取締役会が含まれる可能性があります。 <br/><br/> 事前設定されたセキュリティ ポリシーでは、保護するユーザーを指定できます。 事前設定されたセキュリティ ポリシーを無効にし、カスタムのフィッシング対策ポリシーを使用して、推奨される主要な役割にユーザーを追加する必要があります。|
|**ドメインの保護を有効にする** (偽装されたドメイン保護)|未選択|選択済み|選択済み||
|**所有するドメインを含める** <br/><br/> _EnableOrganizationDomainsProtection_|Off <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**カスタム ドメインを含める** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Off <br/><br/> `$false` <br/><br/> none|選択済み <br/><br/> `$true` <br/><br/> \<list of domains\>|選択済み <br/><br/> `$true` <br/><br/> \<list of domains\>|所有しているのではなく、頻繁に操作するドメイン (送信者ドメイン) を追加することをお勧めします。 <br/><br/> 事前設定されたセキュリティ ポリシーでは、保護する custm ドメインを指定できない。 事前設定されたセキュリティ ポリシーを無効にし、カスタムフィッシング対策ポリシーを使用してカスタム ドメインを追加して、推奨される保護を行う必要があります。|
|**信頼できる送信者とドメインの追加** <br/><br/> _ExcludedSenders_ <br/><br/> _ExcludedDomains_|なし|なし|なし|組織によっては、偽装の試行として誤って識別される送信者またはドメインを追加することをお勧めします。|
|**メールボックス インテリジェンスを有効にする** <br/><br/> _EnableMailboxIntelligence_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**偽装保護のインテリジェンスを有効にする** <br/><br/> _EnableMailboxIntelligenceProtection_|Off <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|この設定では、メールボックス インテリジェンスによる偽装検出に対して指定されたアクションを使用できます。|
|**アクション**||||[メッセージの **検疫] を選択した場合は**、[ **検疫ポリシーの選択] ボックス** を使用できます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作を定義します。 <br/><br/> 新しいフィッシング対策ポリシーを作成する場合、空白の値は、既定の検疫ポリシーを使用して、その評決によって検疫されたメッセージの履歴機能を定義します (すべての偽装検出の種類に対する DefaultFullAccessPolicy)。 <br/><br/> 管理者は、ユーザーの制限が少ない、または制限の厳しい機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**偽装ユーザーとしてメッセージが検出された場合** <br/><br/> _TargetedUserProtectionAction_|**アクションを適用しない** <br/><br/> `NoAction`|**メッセージを検疫する** <br/><br/> `Quarantine`|**メッセージを検疫する** <br/><br/> `Quarantine`|事前に設定されたセキュリティ ポリシーでは、保護するユーザーを指定できないので、この設定は、事前設定されたセキュリティ ポリシーでは効果的に何も行いません。|
|**偽装ドメインとしてメッセージが検出された場合** <br/><br/> _TargetedDomainProtectionAction_|**アクションを適用しない** <br/><br/> `NoAction`|**メッセージを検疫する** <br/><br/> `Quarantine`|**メッセージを検疫する** <br/><br/> `Quarantine`|事前に設定されたセキュリティ ポリシーでは、保護するカスタム ドメインを指定できないので、この設定はユーザーが所有するドメインにのみ影響し、カスタム ドメインには影響を与えないので注意してください。|
|**メールボックス インテリジェンスがユーザーを検出して偽装した場合** <br/><br/> _MailboxIntelligenceProtectionAction_|**アクションを適用しない** <br/><br/> `NoAction`|**受信者の迷惑メール フォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**メッセージを検疫する** <br/><br/> `Quarantine`||
|**ユーザーの偽装を表示安全性のヒント** <br/><br/> _EnableSimilarUsersSafetyTips_|Off <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**ドメイン偽装の表示安全性のヒント** <br/><br/> _EnableSimilarDomainsSafetyTips_|Off <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**ユーザー偽装の異常な文字を表示安全性のヒント** <br/><br/> _EnableUnusualCharactersSafetyTips_|Off <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>EOP フィッシング対策ポリシーの設定 (Microsoft Defender for Office 365

これらは、EOP のスパム対策ポリシー設定で使用できるのと同 [じ設定です](#eop-anti-spam-policy-settings)。

スプーフィング設定は相互関連ですが、[最初の連絡先を表示する] **安全性のヒントスプー** フィング設定に依存はありません。

|セキュリティ機能名|既定値|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**フィッシングのしきい値&保護**|||||
|**スプーフィング インテリジェンスを有効にする** <br/><br/> _EnableSpoofIntelligence_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**アクション**|||||
|**メッセージがスプーフィングとして検出された場合** <br/><br/> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <br/><br/> `MoveToJmf`|**メッセージを検疫する** <br/><br/> `Quarantine`|この設定は、スプーフィング インテリジェンスの分析情報に示すように自動的にブロック[](learn-about-spoof-intelligence.md)されたスプーフィングされた送信者、またはテナント許可/ブロック一覧で手動でブロックされた送信者に[適用されます](tenant-allow-block-list.md)。 <br/><br/> [メッセージの **検疫] を** 選択すると、[検疫ポリシーの適用] ボックスを使用して、検疫メッセージに対してユーザーが実行できる操作を定義する検疫ポリシーを選択できます。 新しいフィッシング対策ポリシーを作成すると、空白の値は、既定の検疫ポリシーを使用して、スプーフィング検疫されたメッセージの履歴機能を定義します (DefaultFullAccessPolicy)。 <br/><br/> 管理者は、検疫でこれらのメッセージに対して受信者が実行できる操作を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**最初の連絡先を表示安全性のヒント** <br/><br/> _EnableFirstContactSafetyTips_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|詳細については、「First [contact 安全性のヒント」を参照してください](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**スプーフィング用の認証されていない送信者の表示 (?)** <br/><br/> _EnableUnauthenticatedSender_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|未確認のスプーフィングされた送信者に対して、Outlookに疑問符 (?) を追加します。 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**"via" タグを表示する** <br/><br/> _EnableViaTag_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|DKIM 署名または MAIL FROM アドレスのドメインと異なる場合は、from アドレスに via タグ (chris@contoso.com 経由で fabrikam.com) を **追加** します。 <br/><br/> 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。|

### <a name="safe-attachments-settings"></a>セーフ添付ファイルの設定

セーフ Microsoft Defender for Office 365の添付ファイルには、セーフ 添付ファイル ポリシーとの関係を持つグローバル設定と、セーフ リンク ポリシーごとに固有の設定が含まれます。 詳細については、「添付ファイル[のセーフ」を参照Defender for Office 365](safe-attachments.md)。

既定の セーフ 添付ファイル ポリシーは使用できませんが、組み込みの保護プリセット セキュリティ ポリシーは、すべての受信者 (カスタム セーフ 添付ファイル ポリシーで定義されていないユーザー) に セーフ 添付ファイル保護を提供します。 詳細については、「EOP および EOP のセキュリティ ポリシーを事前に設定[する」を参照Microsoft Defender for Office 365](preset-security-policies.md)。

#### <a name="global-settings-for-safe-attachments"></a>添付ファイルのセーフ設定

> [!NOTE]
> 添付ファイルのセーフ設定は、組み込みの保護プリセット  セキュリティ ポリシーによって設定されますが、**Standard** または **Strict** の事前設定されたセキュリティ ポリシーでは設定されません。 いずれの方法でも、管理者は、これらのグローバル セーフ添付ファイルの設定をいつでも変更できます。
>
> [ **既定]** 列には、組み込みの保護プリセット セキュリティ ポリシーが存在する前 **の値が** 表示されます。 [**組み込みの保護]** 列には、組み込み保護の事前設定されたセキュリティ ポリシーによって設定された値が表示されます。これは、推奨される値です。

これらの設定を構成するには、「セーフ ドキュメントの セーフ [SharePoint](turn-on-mdo-for-spo-odb-and-teams.md)、OneDrive、Microsoft Teams、セーフ ドキュメントの添付ファイルを有効にする[Microsoft 365 E5。](safe-docs.md)

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

|セキュリティ機能名|既定値|組み込みの保護|Comment|
|---|:---:|:---:|---|
|**SharePoint、OneDrive、Microsoft Teams 用の Microsoft Defender for Office 365 を有効にする** <br/><br/> _EnableATPForSPOTeamsODB_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|ユーザーが悪意のあるファイルをダウンロードするのを防ぐには、「ユーザーが悪意のあるファイルをダウンロードSharePoint[オンライン PowerShell を使用する」を参照してください](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。|
|**クライアントのセーフドキュメントを有効Officeする** <br/><br/> _EnableSafeDocs_|オフ <br/><br/> `$false`|オン <br/><br/> `$true`|この機能は、Defender for Office 365に含まれていないライセンス (たとえば、Microsoft 365 E5またはMicrosoft 365 E5 Security)。 詳細については、「ドキュメントのセーフ[」を参照Microsoft 365 E5](safe-docs.md)。|
|**[ドキュメントがファイルを悪意のあるファイルとしてセーフ場合でも、保護されたビューをクリックするユーザーを許可する** <br/><br/> _AllowSafeDocsOpen_|Off <br/><br/> `$false`|Off <br/><br/> `$false`|この設定は、ドキュメントのセーフです。|

#### <a name="safe-attachments-policy-settings"></a>セーフ添付ファイルポリシーの設定

これらの設定を構成するには、「セーフ の添付ファイル ポリシーを設定[する」を参照Defender for Office 365](set-up-safe-attachments-policies.md)。

PowerShell では、これらの設定に [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) コマンドレットと [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定の添付ファイル ポリシーセーフはありませんが、セーフ 添付ファイル保護は、組み込みの保護事前設定セキュリティ ポリシーによってすべての受信者に[割り当てられます](preset-security-policies.md)。
>
> [**既定のユーザー設定]** 列は、作成した新しい添付ファイル セーフの既定値を参照します。 残りの列は、対応する事前設定されたセキュリティ ポリシーで構成されている値を (特に指定しない限り) 示します。

|セキュリティ機能名|既定のカスタム|組み込みの保護|Standard|Strict|Comment|
|---|:---:|:---:|:---:|:---:|---|
|**セーフ添付ファイル不明のマルウェア応答** <br/><br/> _有効にして__操作する_|**オフ** <br/><br/> `-Enable $false` と `-Action Block`|**Block** <br/><br/> `-Enable $true` と `-Action Block`|**Block** <br/><br/> `-Enable $true` と `-Action Block`|**Block** <br/><br/> `-Enable $true` と `-Action Block`|Enable パラメーター _を_ 指定$false Action パラメーター _の値は_ 関係ありません。|
|**検疫ポリシー** (_QuarantineTag_)|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|新しい セーフ 添付ファイル ポリシーを作成すると、空白の値は、既定の検疫ポリシーを使用して、セーフ 添付ファイル (AdminOnlyAccessPolicy) によって検疫されたメッセージの履歴機能を定義します。 <br/><br/> 管理者は、ユーザーに対してより多くの機能を定義するカスタム検疫ポリシーを作成および選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**検出された添付ファイルを含む添付ファイルのリダイレクト** : **リダイレクトを有効にする** <br/><br/> _リダイレクトする_ <br/><br/> _RedirectAddress_|選択されていないと、電子メール アドレスが指定されていません。 <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress が_ 空白 (`$null`)|選択されていないと、電子メール アドレスが指定されていません。 <br/><br/> `-Redirect $false` <br/><br/> _RedirectAddress が_ 空白 (`$null`)|電子メール アドレスを選択して指定します。 <br/><br/> `$true` <br/><br/> 電子メール アドレス|電子メール アドレスを選択して指定します。 <br/><br/> `$true` <br/><br/> 電子メール アドレス|メッセージをセキュリティ管理者にリダイレクトして確認します。 <br/><br/> **注**: この設定は、Standard、Strict、**または組** み込みの保護 **プリセット セキュリティ ポリシーでは** 構成されていません。 Standard **と** **Strict の値は**、**新しい添付** ファイル ポリシーでセーフ値を示します。|
|**スキャンが完了できないセーフ添付ファイル検出応答を適用する (タイムアウトまたはエラー)** <br/><br/> _ActionOnError_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||

### <a name="safe-links-settings"></a>セーフリンクの設定

セーフ Defender for Office 365 のリンクには、アクティブな セーフ リンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定と、各 セーフ リンク ポリシーに固有の設定が含まれます。 詳細については、「セーフ[リンク」を参照Defender for Office 365](safe-links.md)。

既定の セーフ リンク ポリシーは使用されませんが、組み込みの保護プリセット セキュリティ ポリシーは、すべての受信者 (カスタム セーフ リンク ポリシーで定義されていないユーザー) に セーフ リンク保護を提供します。 詳細については、「EOP および EOP のセキュリティ ポリシーを事前に設定[する」を参照Microsoft Defender for Office 365](preset-security-policies.md)。

#### <a name="global-settings-for-safe-links"></a>リンクのグローバルセーフ設定

> [!NOTE]
> セーフ リンクのグローバル設定は、組み込みの保護事前設定セキュリティ ポリシーによって設定されますが、**Standard** または **Strict** の事前設定されたセキュリティ ポリシーでは設定されます。 いずれの方法でも、管理者は、これらのグローバル リンク セーフ設定をいつでも変更できます。
>
> [ **既定]** 列には、組み込みの保護プリセット セキュリティ ポリシーが存在する前 **の値が** 表示されます。 [**組み込みの保護]** 列には、組み込み保護の事前設定されたセキュリティ ポリシーによって設定された値が表示されます。これは、推奨される値です。

これらの設定を構成するには、「グループリンクのグローバル設定[を構成セーフ」をDefender for Office 365](configure-global-settings-for-safe-links.md)。

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

|セキュリティ機能名|既定値|組み込みの保護|Comment|
|---|:---:|:---:|---|
|**次の URL をブロックする** <br/><br/> _ExcludedUrls_|空白 <br/><br/> `$null`|空白 <br/><br/> `$null`|この設定に関する具体的な推奨事項はありません。 <br/><br/> 詳細については、「リンク」の「次の URL をブロックする[」をセーフしてください](safe-links.md#block-the-following-urls-list-for-safe-links)。
|**アプリセーフリンクをOffice 365する** <br/><br/> _EnableSafeLinksForO365Clients_|オン <br/><br/> `$true`|オン <br/><br/> `$true`|デスクトップセーフモバイル (iOS Office 365 Android) アプリでサポートされているリンクを使用します。 詳細については、「[Office 365 アプリ向けの安全なリンク設定](safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。|
|**ユーザーがアプリで保護されたリンクをクリックOffice 365しない** <br/><br/> _TrackClicks_|オン <br/><br/> `$false`|オフ <br/><br/> `$true`|この設定をオフにします (_TrackClicks_ `$true`をに設定) は、サポートされているアプリでユーザーのクリックOffice 365追跡します。|
|**ユーザーがアプリの元の URL をクリックOffice 365しない** <br/><br/> _AllowClickThrough_|オン <br/><br/> `$false`|オン <br/><br/> `$false`|この設定 (_AllowClickThrough_ `$false`をに設定) をオンにすると、サポートされているアプリの元の URL をクリックOffice 365します。|

#### <a name="safe-links-policy-settings"></a>セーフ リンク ポリシーの設定

これらの設定を構成するには、「セーフ[のリンク ポリシーを設定する」を参照Microsoft Defender for Office 365](set-up-safe-links-policies.md)。

PowerShell では、これらの設定に [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) コマンドレットと [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述したように、既定の セーフ リンク ポリシーは使用されませんが、セーフ リンク保護は組み込みの保護事前設定セキュリティ ポリシーによってすべての受信者に[割り当てられます](preset-security-policies.md)。
>
> [**既定のユーザー設定]** 列は、作成した新しいリンク セーフの既定値を参照します。 残りの列は、対応する事前設定されたセキュリティ ポリシーで構成されている値を (特に指定しない限り) 示します。

|セキュリティ機能名|既定のカスタム|組み込みの保護|Standard|Strict|Comment|
|---|:---:|:---:|:---:|:---:|---|
|**URL &保護の設定**||||||
|**メール内の潜在的に悪意のある URL に対するアクション**||||||
|**On: セーフリンクは、ユーザーがメール内のリンクをクリックすると、既知の悪意のあるリンクの一覧をチェックします。** <br/><br/> _EnableSafeLinksForEmail_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**[セーフ組織内で送信された電子メール メッセージへのリンクを適用する** <br/><br/> _EnableForInternalSenders_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する** <br/><br/> _ScanUrls_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**メッセージを配信する前に URL のスキャンが完了するのを待ちます** <br/><br/> _DeliverMessageAfterScan_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**URL を書き換えない、リンク API のみを使用セーフチェックする** <br/><br/> _DisableURLRewrite_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`||
|**メールで次の URL を書き換えない** <br/><br/> _DoNotRewriteUrls_|未選択 <br/><br/> 空白|未選択 <br/><br/> 空白|未選択 <br/><br/> 空白|未選択 <br/><br/> 空白|この設定に関する具体的な推奨事項はありません。 詳細については、「リンク ポリシー」の「次の URL を書き換えない[セーフ参照してください](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)。|
|**悪意のある可能性のある URL に対するアクション (Microsoft Teams**||||||
|**On: セーフ リンクは、ユーザーがリンクをクリックすると、既知の悪意のあるリンクの一覧をMicrosoft Teams** <br/><br/> _EnableSafeLinksForTeams_|未選択 <br/><br/> `$false`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**[保護の設定] をクリックします。**||||||
|**ユーザーのクリック数を追跡する** <br/><br/> _TrackUserClicks_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`||
|**ユーザーに元の URL へのクリックを許可する** <br/><br/> _AllowClickThrough_|選択済み <br/><br/> `$true`|選択済み <br/><br/> `$true`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|この設定 ( _AllowClickThrough_ `$false`をに設定) をオフにすると、元の URL へのクリックスルーが防止されます。|
|**通知ページと警告ページに組織のブランド化を表示する** <br/><br/> _EnableOrganizationBranding_|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|未選択 <br/><br/> `$false`|この設定に関する具体的な推奨事項はありません。 <br/><br/> この設定を有効にする前に、「組織のカスタム テーマをカスタマイズMicrosoft 365[](../../admin/setup/customize-your-organization-theme.md)、会社のロゴをアップロードする」の手順に従う必要があります。|
|**通知**||||||
|**ユーザーに通知する方法**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|この設定に関する具体的な推奨事項はありません。 <br/><br/> [カスタム通知 **テキストを使用する** ] (_CustomNotificationText_) を選択して、使用するカスタマイズされた通知テキストを入力できます。 カスタム通知テキストをユーザーの **Microsoft 翻訳ツール** に翻訳するには、[自動ローカライズに使用する] (_UseTranslatedNotificationText_) を選択します。

## <a name="related-articles"></a>関連記事

- メール フロー ルール (トランスポート ルールとも呼Exchange) のベスト プラクティス **をお探しですか**? 「[メール フロー ルールを構成するためのベスト プラクティス」を参照Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 管理者とユーザーは、誤検知 (良い電子メールが不良とマークされている) と誤検知 (悪いメールが許可されている) を分析のために Microsoft に提出できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- EOP サービスをセットアップし、[EOP](/exchange/standalone-eop/set-up-your-eop-service) **サービスを** 構成する方法については、次の [Microsoft Defender for Office 365](defender-for-office-365.md)。 「脅威から保護する」の役[に](protect-against-threats.md)立つ指示を忘Office 365。

- **Windows** のセキュリティ基準については、GPO/オンプレミス オプションのセキュリティ 基準 [](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)を取得できる場所と、Intune ベースのセキュリティ用に [Intune で Windows](/intune/protect/security-baselines) デバイスを構成するためのセキュリティ 基準を使用する方法を示します。 最後に、セキュリティ ベースラインとMicrosoft Defender for EndpointとMicrosoft Intuneの比較は、「セキュリティとセキュリティの比較Microsoft Defender for Endpoint[」でWindows Intuneできます。ベースライン。](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
