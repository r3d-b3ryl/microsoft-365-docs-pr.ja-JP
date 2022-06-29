---
title: EOP とDefender for Office 365セキュリティ設定に関する Microsoft の推奨事項
keywords: Office 365セキュリティに関する推奨事項、Sender Policy Framework、ドメイン ベースのメッセージレポートと準拠、DomainKeys 識別メール、手順、動作方法、セキュリティ ベースライン、EOP のベースライン、Defender for Office 365のベースライン、Defender for Office 365の設定、EOP のセットアップ、構成Defender for Office 365、EOP の構成、セキュリティ構成
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
description: Exchange Online Protection (EOP) とDefender for Office 365セキュリティ設定のベスト プラクティスは何ですか? 標準保護に関する現在の推奨事項は何ですか? より厳しくしたい場合は、何を使用する必要がありますか? また、Defender for Office 365も使用すると、どのような追加機能が得られますか?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7798bc177cf6d3a864644fdfa6563ced14cd0ab8
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489793"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP および Microsoft Defender for Office 365 セキュリティの推奨設定

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** は、Microsoft 365 サブスクリプションのセキュリティの中核であり、悪意のあるメールが従業員の受信トレイに届かないようにするのに役立ちます。 しかし、新しいより高度な攻撃が毎日出現する中で、多くの場合、強化された保護が必要になります。 **Microsoft Defender for Office 365** プラン 1 またはプラン 2 には、管理者により多くのセキュリティ、制御、および調査のレイヤーを提供する追加機能が含まれています。

セキュリティ管理者はセキュリティ設定をカスタマイズできますが、EOP とMicrosoft Defender for Office 365には **Standard** と **Strict** の 2 つのセキュリティ レベルが推奨されています。 顧客の環境とニーズは異なりますが、これらのフィルター処理のレベルは、ほとんどの状況で不要なメールが従業員の受信トレイに届くのを防ぐのに役立ちます。

Standard または Strict の設定をユーザーに自動的に適用するには、「[EOP とMicrosoft Defender for Office 365のプリセット セキュリティ ポリシー](preset-security-policies.md)」を参照してください。

この記事では、既定の設定と、ユーザーを保護するために推奨される Standard と Strict の設定についても説明します。 テーブルには、Microsoft 365 Defender ポータルと PowerShell (Exchange Online メールボックスのない組織の PowerShell またはスタンドアロン Exchange Online Protection PowerShell Exchange Online) の設定が含まれています。

> [!NOTE]
> PowerShell 用の Office 365 Advanced Threat Protection 推奨構成アナライザー (ORCA) モジュールは、(管理者) これらの設定の現在の値を見つけるのに役立ちます。 具体的には、 **Get-ORCAReport** コマンドレットは、スパム対策、フィッシング詐欺対策、およびその他のメッセージの検疫設定の評価を生成します。 ORCA モジュールは 、次の場所で <https://www.powershellgallery.com/packages/ORCA/>ダウンロードできます。
>
> Microsoft 365 組織では、EOP からのスパム フィルターの判定で不要な競合 (正と負の両方) を防ぐために、Outlook の迷惑メール フィルターを **[自動フィルター** なし] に設定しておくことをお勧めします。 詳細については、次の資料を参照してください。
>
> - [Exchange Online メールボックスで迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)
> - [Outlook の迷惑メール設定について](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)
> - [迷惑メール フィルターで保護レベルを変更する](https://support.microsoft.com/en-us/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)
> - [EOP で安全な差出人のリストを作成する](create-safe-sender-lists-in-office-365.md)
> - [EOP で受信拒否送信者の一覧を作成する](create-block-sender-lists-in-office-365.md)

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP でのスパム対策、マルウェア対策、フィッシング詐欺対策の保護

スパム対策、マルウェア対策、フィッシング詐欺対策は、管理者が構成できる EOP 機能です。 次の Standard または Strict 構成をお勧めします。

### <a name="eop-anti-spam-policy-settings"></a>「EOP のスパム対策ポリシーの設定」

スパム対策ポリシーを作成して構成するには、「 [EOP でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**迷惑メールのプロパティ&一括メールしきい値**|||||
|**一括メールのしきい値** <p> _BulkThreshold_|7 |6 |4|詳細については、 [EOP の一括苦情レベル (BCL) を](bulk-complaint-level-values.md)参照してください。|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|この設定は、PowerShell でのみ使用できます。|
|**スパム スコアの設定を増やす**|オフ|オフ|オフ|これらの設定はすべて、高度なスパム フィルター (ASF) の一部です。 詳細については、この記事の「 [スパム対策ポリシー」セクションの ASF 設定](#asf-settings-in-anti-spam-policies) を参照してください。|
|**スパム設定としてマークする**|オフ|オフ|オフ|これらの設定のほとんどは ASF の一部です。 詳細については、この記事の「 [スパム対策ポリシー」セクションの ASF 設定](#asf-settings-in-anti-spam-policies) を参照してください。|
|**特定の言語を含む** <p> _EnableLanguageBlockList_ <p> _LanguageBlockList_|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|この設定に関する具体的な推奨事項はありません。 ビジネス ニーズに基づいて、特定の言語でメッセージをブロックできます。|
|**これらの国から** <p> _EnableRegionBlockList_ <p> _RegionBlockList_|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|**オフ** <p> `$false` <p> 空白|この設定に関する具体的な推奨事項はありません。 ビジネス ニーズに基づいて、特定の国からのメッセージをブロックできます。|
|**テスト モード** (_TestModeAction_)|**なし**|**なし**|**なし**|この設定は ASF の一部です。 詳細については、この記事の「 [スパム対策ポリシー」セクションの ASF 設定](#asf-settings-in-anti-spam-policies) を参照してください。|
|**アクション**||||**[検疫メッセージ**] を選択すると、検疫 **ポリシーの選択** ボックスを使用できます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが許可する操作を定義します。 <p> Standard および Strict の事前設定済みセキュリティ ポリシーでは、 [次](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)の表に示すように、既定の検疫ポリシー (AdminOnlyAccessPolicy または DefaultFullAccessPolicy と検疫通知なし) が使用されます。 <p> 新しいスパム対策ポリシーを作成すると、空白の値は、既定の検疫ポリシーを使用して、特定の判定によって検疫されたメッセージの履歴機能を定義することを意味します (高 **信頼フィッシング** の検疫通知のない AdminOnlyAccessPolicy。DefaultFullAccessPolicy(それ以外のすべての検疫通知なし)。 <p> 管理者は、既定またはカスタムのスパム対策ポリシーで、ユーザーに対してより制限の厳しい機能または制限の少ない機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**スパム** 検出アクション <p> _SpamAction_|**迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|**高信頼スパム** 検出アクション <p> _HighConfidenceSpamAction_|**迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**フィッシング検出** アクション <p> _PhishSpamAction_|**迷惑メール フォルダーにメッセージを移動する**<sup>\*</sup> <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`|<sup>\*</sup> 既定値は、既定のスパム対策ポリシーと PowerShell で作成した新しいスパム対策ポリシーの [ **迷惑メールにメッセージを移動] フォルダー** です。 既定値は、Microsoft 365 Defender ポータルで作成した新しいスパム対策ポリシーの **検疫メッセージ** です。|
|**高信頼フィッシング** 検出アクション <p> _HighConfidencePhishAction_|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`|**検疫メッセージ** <p> `Quarantine`||
|**一括** 検出アクション <p> _BulkSpamAction_|**迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**検疫メッセージ** <p> `Quarantine`||
|**この数日間、検疫でスパムを保持する** <p> _QuarantineRetentionPeriod_|15 日間<sup>\*</sup>|30 日間|30 日間|<sup>\*</sup> 既定値は、既定のスパム対策ポリシーと PowerShell で作成した新しいスパム対策ポリシーで 15 日間です。 Microsoft 365Defender ポータルで作成する新しいスパム対策ポリシーの規定値は30日です。 <p> この値は、フィッシング対策ポリシーによって検疫されたメッセージにも影響します。 詳細については、「 [EOP で検疫された電子メール メッセージ](quarantine-email-messages.md)」を参照してください。|
|**スパムの安全性に関するヒントを有効にする** <p> _InlineSafetyTipsEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|フィッシング メッセージに対してゼロ時間の自動消去 (ZAP) を有効にする <p> _PhishZapEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|スパム メッセージの ZAP を有効にする <p> _SpamZapEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**ブロック リスト&許可する**|||||
|許可される送信者 <p> _AllowedSenders_|なし|なし|なし||
|許可される送信者ドメイン <p> _AllowedSenderDomains_|なし|なし|なし|許可された送信者リストにドメインを追加することは非常に悪い考えです。 攻撃者は、それ以外の場合は除外される電子メールを送信できます。 <p> [スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)と[テナント許可/ブロック リスト](tenant-allow-block-list.md)を使用して、組織の電子メール ドメインで送信者の電子メール アドレスをスプーフィングしたり、外部ドメイン内の送信者の電子メール アドレスをスプーフィングしたりしているすべての送信者を確認します。|
|ブロックされた送信者 <p> _BlockedSenders_|なし|なし|なし||
|ブロックされた送信者ドメイン <p> _BlockedSenderDomains_|なし|なし|なし||

#### <a name="asf-settings-in-anti-spam-policies"></a>スパム対策ポリシーの ASF 設定

スパム対策ポリシーの高度なスパム フィルター (ASF) 設定の詳細については、 [EOP の高度なスパム フィルター (ASF) 設定に関するページを](advanced-spam-filtering-asf-options.md)参照してください。

|セキュリティ機能名|既定値|推奨<br/>標準|推奨<br/>Strict|コメント|
|---|:---:|:---:|:---:|---|
|**リモート サイトへのイメージ リンク** <p> _IncreaseScoreWithImageLinks_|オフ|オフ|オフ||
|**URL 内の数値 IP アドレス** <p> _IncreaseScoreWithNumericIps_|オフ|オフ|オフ||
|**別のポートに対する URL リダイレクト** <p> _IncreaseScoreWithRedirectToOtherPort_|オフ|オフ|オフ||
|**.biz または .info Web サイトへのリンク** <p> _IncreaseScoreWithBizOrInfoUrls_|オフ|オフ|オフ||
|**空メッセージ** <p> _MarkAsSpamEmptyMessages_|オフ|オフ|オフ||
|**HTML 内の Embed タグ** <p> _MarkAsSpamEmbedTagsInHtml_|オフ|オフ|オフ||
|**HTML 内の JavaScript または VBScript** <p> _MarkAsSpamJavaScriptInHtml_|オフ|オフ|オフ||
|**HTML 内の Form タグ** <p> _MarkAsSpamFormTagsInHtml_|オフ|オフ|オフ||
|**HTML のフレーム タグまたは iframe タグ** <p> _MarkAsSpamFramesInHtml_|オフ|オフ|オフ||
|**HTML 内の Web バグ** <p> _MarkAsSpamWebBugsInHtml_|オフ|オフ|オフ||
|**HTML 内の Object タグ** <p> _MarkAsSpamObjectTagsInHtml_|オフ|オフ|オフ||
|**機密性の高い単語** <p> _MarkAsSpamSensitiveWordList_|オフ|オフ|オフ||
|**SPF レコード:Hard Fail** <p> _MarkAsSpamSpfRecordHardFail_|オフ|オフ|オフ||
|**送信者 ID フィルターのハード 失敗** <p> _MarkAsSpamFromAddressAuthFail_|オフ|オフ|オフ||
|**バックスキャター** <p> _MarkAsSpamNdrBackscatter_|オフ|オフ|オフ||
|**テスト モード** <p> _TestModeAction_)|なし|なし|なし|アクションとして **Test** をサポートする ASF 設定の場合、テスト モードアクションを **None**、**Add default X-Header text**、または **Send Bcc message** (`None`または `AddXHeader``BccMessage`) に構成できます。 詳細については、「 [ASF 設定を有効、無効、またはテストする](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)」を参照してください。|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 送信スパム ポリシー設定

送信スパム ポリシーを作成して構成するには、「 [EOP で送信スパム フィルターを構成する](configure-the-outbound-spam-policy.md)」を参照してください。

サービスの既定の送信制限の詳細については、「 [送信制限」を](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)参照してください。

> [!NOTE]
> 送信スパム ポリシーは、Standard または Strict の事前設定済みセキュリティ ポリシーの一部ではありません。 **Standard** と **Strict** の値は、作成する既定の送信スパム ポリシーまたはカスタム送信スパム ポリシーで **推奨** される値を示します。

|セキュリティ機能名|既定値|推奨<br/>標準|推奨<br/>Strict|コメント|
|---|:---:|:---:|:---:|---|
|**外部メッセージの制限を設定する** <p> _RecipientLimitExternalPerHour_|0|500|400|既定値 0 は、サービスの既定値を使用します。|
|**内部メッセージの制限を設定する** <p> _RecipientLimitInternalPerHour_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**1 日のメッセージ制限を設定する** <p> _RecipientLimitPerDay_|0|1000|800|既定値 0 は、サービスの既定値を使用します。|
|**メッセージの制限に達したユーザーに対する制限** <p> _ActionWhenThresholdReached_|**ユーザーのメール送信を翌日まで制限する** <p> `BlockUserForToday`|**ユーザーがメールを送信できないように制限する** <p> `BlockUser`|**ユーザーがメールを送信できないように制限する** <p> `BlockUser`||
|**自動転送ルール** <p> _AutoForwardingMode_|**自動 - システム制御** <p> `Automatic`|**自動 - システム制御** <p> `Automatic`|**自動 - システム制御** <p> `Automatic`|
|**これらの制限を超える送信メッセージのコピーをこれらのユーザーとグループに送信する** <p> _BccSuspiciousOutboundMail_ <p> _BccSuspiciousOutboundAdditionalRecipients_|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|この設定に関する具体的な推奨事項はありません。 <p> この設定は、既定の送信スパム ポリシーでのみ機能します。 作成したカスタム送信スパム ポリシーでは機能しません。|
|**送信スパムの送信が原因で送信者がブロックされている場合は、これらのユーザーとグループに通知する** <p> _NotifyOutboundSpam_ <p> _NotifyOutboundSpamRecipients_|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|未選択 <p> `$false` <p> 空白|ユーザーがポリシーの制限を超えたためにブロックされている場合、**ユーザーが電子メールの送信を制限** されたという既定の [アラート ポリシー](../../compliance/alert-policies.md)は **、TenantAdmins** (**グローバル管理者**) グループのメンバーに電子メール通知を既に送信します。 **送信スパム ポリシーのこの設定ではなく、アラート ポリシーを使用して管理者や他のユーザーに通知することを強くお勧めします**。 手順については、「 [制限付きユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。|

### <a name="eop-anti-malware-policy-settings"></a>EOP マルウェア対策ポリシー設定

マルウェア対策ポリシーを作成して構成するには、「 [EOP でマルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**保護の設定**|||||
|**一般的な添付ファイル フィルターを有効にする** <p> _EnableFileFilter_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|この設定は、添付ファイルの内容に関係なく、ファイルの種類に基づいて添付ファイルを含むメッセージを検疫します。 ファイルの種類の一覧については、「 [マルウェア対策ポリシー](anti-malware-protection.md#anti-malware-policies)」を参照してください。|
|**マルウェアのゼロ時間自動消去を有効にする** <p> _ZapEnabled_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**検疫ポリシー**|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|新しいマルウェア対策ポリシーを作成すると、空白の値は、既定の検疫ポリシーを使用して、マルウェアとして検疫されたメッセージの履歴機能を定義することを意味します (検疫通知のない AdminOnlyAccessPolicy)。 <p> Standard および Strict の事前設定済みセキュリティ ポリシーでは、 [次](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)の表に示すように、既定の検疫ポリシー (検疫通知のない AdminOnlyAccessPolicy) が使用されます。 <p> 管理者は、既定またはカスタムマルウェア対策ポリシーで、ユーザーに対してより多くの機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**管理通知**|||||
|**内部送信者からの未配信メッセージについて管理者に通知する** <p> _EnableInternalSenderAdminNotifications_ <p> _InternalSenderAdminAddress_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|この設定に関する具体的な推奨事項はありません。|
|**外部送信者からの未配信メッセージについて管理者に通知する** <p> _EnableExternalSenderAdminNotifications_ <p> _ExternalSenderAdminAddress_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|この設定に関する具体的な推奨事項はありません。|
|**通知をカスタマイズする**||||これらの設定に関する具体的な推奨事項はありません。|
|**カスタマイズされた通知テキストを使用する** <p> _CustomNotifications_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`||
|**From name** <p> _CustomFromName_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**差出人アドレス** <p> _CustomFromAddress_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**内部送信者からのメッセージの通知をカスタマイズする**||||これらの設定は、 **内部送信者からの未配信メッセージについて管理者に通知** するが選択されている場合にのみ使用されます。|
|**[件名]** <p> _CustomInternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**メッセージ** <p> _CustomInternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**外部送信者からのメッセージの通知をカスタマイズする**||||これらの設定は、 **外部送信者からの配信不能メッセージについて管理者に通知** するが選択されている場合にのみ使用されます。|
|**[件名]** <p> _CustomExternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**メッセージ** <p> _CustomExternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||

### <a name="eop-anti-phishing-policy-settings"></a>EOP フィッシング対策ポリシー設定

これらの設定の詳細については、「 [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。 これらの設定を構成するには、「 [EOP でフィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)」を参照してください。

スプーフィング設定は相互に関連していますが、[ **最初の連絡先の安全ヒントを表示** する] 設定はスプーフィング設定に依存しません。

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**フィッシングしきい値&保護**|||||
|**スプーフィング インテリジェンスを有効にする** <p> _EnableSpoofIntelligence_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**アクション**|||||
|**メッセージがスプーフィングとして検出された場合** <p> _AuthenticationFailAction_|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`|この設定は、スプーフィング インテリジェンス分析情報に示すように自動的にブロックされたス [プーフィング](learn-about-spoof-intelligence.md) された送信者、または [テナント許可/ブロック リスト](tenant-allow-block-list.md)で手動でブロックされた送信者に適用されます。 <p> **[検疫] を** 選択した場合、[**検疫ポリシーの適用**] ボックスを使用して、スプーフィングとして検疫されたメッセージに対してユーザーが許可する操作を定義する検疫ポリシーを選択できます。 新しいフィッシング対策ポリシーを作成すると、空白の値は、既定の検疫ポリシーを使用して、スプーフィングとして検疫されたメッセージの履歴機能を定義することを意味します (検疫通知のない DefaultFullAccessPolicy)。 <p> Standard および Strict の事前設定済みセキュリティ ポリシーでは、 [次](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)の表に示すように、既定の検疫ポリシー (検疫通知のない DefaultFullAccessPolicy) が使用されます。 <p> 管理者は、既定またはカスタムフィッシング対策ポリシーで、ユーザーに対してより制限の厳しい機能または制限の少ない機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**最初の連絡先の安全に関するヒントを表示する** <p> _EnableFirstContactSafetyTips_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|詳細については、「[最初の連絡先安全性のヒント](set-up-anti-phishing-policies.md#first-contact-safety-tip)」を参照してください。|
|**スプーフィングの認証されていない送信者の表示 (?)** <p> _EnableUnauthenticatedSender_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|Outlook の送信者の写真に疑問符 (?) を追加して、未確認のスプーフィング送信者を表示します。 詳細については、「 [認証されていない送信者インジケーター](set-up-anti-phishing-policies.md#unauthenticated-sender-indicators)」を参照してください。|
|**"via" タグを表示する** <p> _EnableViaTag_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|DKIM 署名または **MAIL FROM** アドレスのドメインと異なる場合は、from アドレスに via タグ (fabrikam.com 経由で chris@contoso.com) を追加します。 <p> 詳細については、「 [認証されていない送信者インジケーター](set-up-anti-phishing-policies.md#unauthenticated-sender-indicators)」を参照してください。|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365セキュリティ

追加のセキュリティ上の利点には、Microsoft Defender for Office 365 サブスクリプションが付属しています。 最新のニュースと情報については、「[Defender for Office 365の新機能」を](whats-new-in-defender-for-office-365.md)参照してください。

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365の既定のフィッシング対策ポリシーは、すべての受信者に[スプーフィング保護](set-up-anti-phishing-policies.md#spoof-settings)とメールボックス インテリジェンスを提供します。 ただし、使用可能なその他の [偽装保護機能](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) と [詳細設定](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) は、既定のポリシーでは構成または有効になっていません。 すべての保護機能を有効にするには、既定のフィッシング対策ポリシーを変更するか、追加のフィッシング対策ポリシーを作成します。
>
> - 既定の安全な添付ファイル ポリシーまたは安全なリンク ポリシーはありませんが、 **組み込みの保護** プリセット セキュリティ ポリシーは、カスタムの安全な添付ファイル ポリシーまたはセーフ リンク ポリシーにまだ含まれていない受信者に安全な添付ファイル保護と安全なリンク保護を提供します。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。
>
> - [SharePoint、OneDrive、および Microsoft Teams](mdo-for-spo-odb-and-teams.md) の保護と [安全なドキュメント保護の安全な](safe-docs.md) 添付ファイルには、セーフ リンク ポリシーに依存しません。

サブスクリプションにMicrosoft Defender for Office 365が含まれている場合、またはアドオンとしてDefender for Office 365を購入した場合は、次の Standard または Strict 構成を設定します。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のフィッシング対策ポリシー設定

EOP のお客様は、前述のように基本的なフィッシング対策を受けますが、Defender for Office 365には、攻撃の防止、検出、修復に役立つ、より多くの機能と制御が含まれています。 これらのポリシーを作成して構成するには、「[Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のフィッシング対策ポリシーの詳細設定

この設定の詳細については、「Microsoft Defender for Office 365の[フィッシング対策ポリシーの高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。 この設定を構成するには、「[Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**フィッシングメールのしきい値** <p> _PhishThresholdLevel_|**1 - Standard** <p> `1`|**2 - アグレッシブ** <p> `2`|**3 - より積極的** <p> `3`||

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のフィッシング対策ポリシーの偽装設定

これらの設定の詳細については、[Microsoft Defender for Office 365のフィッシング対策ポリシーの偽装設定に関する](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)ページを参照してください。 これらの設定を構成するには、「[Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

|セキュリティ機能名|既定値|Standard|Strict|コメント|
|---|:---:|:---:|:---:|---|
|**フィッシングしきい値&保護**|||||
|**ユーザーの保護を有効にする** (偽装されたユーザー保護) <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|未選択 <p> `$false` <p> なし|選択済み <p> `$true` <p> \<list of users\>|選択済み <p> `$true` <p> \<list of users\>|キー ロールにユーザー (メッセージ送信者) を追加することをお勧めします。 内部的には、保護された送信者は、CEO、CFO、およびその他の上級リーダーである可能性があります。 外部では、保護された送信者には、会議メンバーまたは取締役会が含まれる可能性があります。|
|**ドメインで保護を有効にする** (偽装されたドメイン保護)|未選択|選択済み|選択済み||
|**所有しているドメインを含める** <p> _EnableOrganizationDomainsProtection_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**カスタム ドメインを含める** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|オフ <p> `$false` <p> なし|選択済み <p> `$true` <p> \<list of domains\>|選択済み <p> `$true` <p> \<list of domains\>|所有していないドメイン (送信者ドメイン) を追加することをお勧めしますが、頻繁に操作します。|
|**信頼できる送信者とドメインの追加** <p> _ExcludedSenders_ <p> _ExcludedDomains_|なし|なし|なし|組織によっては、偽装の試行として誤って識別される送信者またはドメインを追加することをお勧めします。|
|**メールボックス インテリジェンスを有効にする** <p> _EnableMailboxIntelligence_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**偽装に対する保護のインテリジェンスを有効にする** <p> _EnableMailboxIntelligenceProtection_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|この設定では、メールボックス インテリジェンスによる偽装検出に対して指定されたアクションを許可します。|
|**アクション**||||**[メッセージの検疫**] を選択した場合は、検疫 **ポリシーの選択** ボックスを使用できます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが許可する操作を定義します。 <p> Standard および Strict の事前設定済みセキュリティ ポリシーでは、 [次](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)の表に示すように、既定の検疫ポリシー (検疫通知のない DefaultFullAccessPolicy) が使用されます。 <p> 新しいフィッシング対策ポリシーを作成すると、空白の値は、既定の検疫ポリシーを使用して、その判定によって検疫されたメッセージの履歴機能を定義することを意味します (すべての偽装検出の種類の DefaultFullAccessPolicy)。 <p> 管理者は、既定のフィッシング対策ポリシーまたはカスタムフィッシング対策ポリシーで、ユーザーに対して制限の少ない、またはより制限の厳しい機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**偽装されたユーザーとしてメッセージが検出された場合** <p> _TargetedUserProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**偽装されたドメインとしてメッセージが検出された場合** <p> _TargetedDomainProtectionAction_|**アクションを適用しない** <p> `NoAction`|**メッセージを検疫する** <p> `Quarantine`|**メッセージを検疫する** <p> `Quarantine`||
|**メールボックス インテリジェンスが検出され、偽装されたユーザーの場合** <p> _MailboxIntelligenceProtectionAction_|**アクションを適用しない** <p> `NoAction`|**受信者の迷惑メール フォルダーにメッセージを移動する** <p> `MoveToJmf`|**メッセージを検疫する** <p> `Quarantine`||
|**ユーザー偽装の安全性に関するヒントを表示する** <p> _EnableSimilarUsersSafetyTips_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**ドメイン偽装の安全性に関するヒントを表示する** <p> _EnableSimilarDomainsSafetyTips_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||
|**ユーザー権限借用の異常な文字の安全性のヒントを表示する** <p> _EnableUnusualCharactersSafetyTips_|オフ <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`||

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365の EOP フィッシング対策ポリシー設定

これらは、 [EOP のスパム対策ポリシー設定で使用できる設定と](#eop-anti-spam-policy-settings)同じです。

### <a name="safe-attachments-settings"></a>安全な添付ファイルの設定

Microsoft Defender for Office 365の安全な添付ファイルには、安全な添付ファイル ポリシーとは関係のないグローバル設定と、各セーフ リンク ポリシーに固有の設定が含まれます。 詳細については、「[Defender for Office 365の安全な添付ファイル](safe-attachments.md)」を参照してください。

既定の安全な添付ファイル ポリシーはありませんが、 **組み込みの保護** プリセット セキュリティ ポリシーは、カスタムの安全な添付ファイル ポリシーにまだ含まれていないすべての受信者に安全な添付ファイル保護を提供します。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

#### <a name="global-settings-for-safe-attachments"></a>安全な添付ファイルのグローバル設定

> [!NOTE]
> 安全な添付ファイルのグローバル設定は **、組み込みの保護** プリセット セキュリティ ポリシーによって設定されますが、 **Standard** または **Strict** プリセットのセキュリティ ポリシーでは設定されません。 どちらの方法でも、管理者はいつでもこれらのグローバルな安全な添付ファイルの設定を変更できます。
>
> **[既定]** 列には、**組み込みの保護** プリセット セキュリティ ポリシーが存在する前の値が表示されます。 **[組み込みの保護**] 列には、**組み込みの保護** プリセット セキュリティ ポリシーによって設定される値が表示されます。これは推奨値でもあります。

これらの設定を構成するには、「Microsoft 365 E5[で SharePoint、OneDrive、Microsoft Teams および](turn-on-mdo-for-spo-odb-and-teams.md)[安全なドキュメントの安全な](safe-docs.md)添付ファイルを有効にする」を参照してください。

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

|セキュリティ機能名|既定値|組み込みの保護|コメント|
|---|:---:|:---:|---|
|**SharePoint、OneDrive、Microsoft Teams 用の Microsoft Defender for Office 365 を有効にする** <p> _EnableATPForSPOTeamsODB_|オフ <p> `$false`|オン <p> `$true`|ユーザーが悪意のあるファイルをダウンロードできないようにするには、「 [SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする」](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)を参照してください。|
|**Office クライアントの安全なドキュメントを有効にする** <p> _EnableSafeDocs_|オフ <p> `$false`|オン <p> `$true`|この機能は、Defender for Office 365に含まれていないライセンス (Microsoft 365 E5やMicrosoft 365 E5 Securityなど) でのみ使用でき、意味があります。 詳細については、「[Microsoft 365 E5の安全なドキュメント](safe-docs.md)」を参照してください。|
|**セーフ ドキュメントでファイルが悪意のあるものとして識別された場合でも、ユーザーが保護されたビューをクリックできるようにする** <p> _AllowSafeDocsOpen_|オフ <p> `$false`|オフ <p> `$false`|この設定は、安全なドキュメントに関連しています。|

#### <a name="safe-attachments-policy-settings"></a>安全な添付ファイル ポリシー設定

これらの設定を構成するには、「[Defender for Office 365で安全な添付ファイル ポリシーを設定](set-up-safe-attachments-policies.md)する」を参照してください。

PowerShell では、これらの設定に [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) コマンドレットと [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述のように、既定の安全な添付ファイル ポリシーはありませんが、安全な添付ファイル保護は [**、組み込みの保護** プリセット セキュリティ ポリシー](preset-security-policies.md)によってすべての受信者に割り当てられます。
>
> **カスタム列の既定値** は、作成する新しい安全な添付ファイル ポリシーの既定値を参照します。 残りの列は、対応する事前設定済みセキュリティ ポリシーで構成されている値を (特に明記されていない限り) 示します。

|セキュリティ機能名|カスタムの既定値|組み込みの保護|Standard|Strict|コメント|
|---|:---:|:---:|:---:|:---:|---|
|**安全な添付ファイルの不明なマルウェアの応答** <p> _有効化_ と _アクション_|**オフ** <p> `-Enable $false` と `-Action Block`|**Block** <p> `-Enable $true` と `-Action Block`|**Block** <p> `-Enable $true` と `-Action Block`|**Block** <p> `-Enable $true` と `-Action Block`|_Enable_ パラメーターが$falseされている場合、_Action_ パラメーターの値は関係ありません。|
|**検疫ポリシー** (_QuarantineTag_)|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy| <p> Standard および Strict の事前設定済みセキュリティ ポリシーでは、 [次](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)の表に示すように、既定の検疫ポリシー (検疫通知のない AdminOnlyAccessPolicy) が使用されます。 <p> 新しい安全な添付ファイル ポリシーを作成する場合、空白の値は、既定の検疫ポリシーを使用して、安全な添付ファイル (検疫通知なしで AdminOnlyAccessPolicy) によって検疫されたメッセージの履歴機能を定義することを意味します。 <p> 管理者は、ユーザーに対してより多くの機能を定義するカスタム検疫ポリシーを作成して選択できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。|
|**検出された添付ファイルを含むリダイレクト添付ファイル** : **リダイレクトを有効にする** <p> _リダイレクトする_ <p> _RedirectAddress_|選択されておらず、電子メール アドレスが指定されていません。 <p> `-Redirect $false` <p> _RedirectAddress_ は空白です (`$null`)|選択されておらず、電子メール アドレスが指定されていません。 <p> `-Redirect $false` <p> _RedirectAddress_ は空白です (`$null`)|選択し、電子メール アドレスを指定します。 <p> `$true` <p> 電子メール アドレス|選択し、電子メール アドレスを指定します。 <p> `$true` <p> 電子メール アドレス|レビューのためにメッセージをセキュリティ管理者にリダイレクトします。 <p> **注**: この設定は、 **Standard**、 **Strict**、または **組み込みの保護** プリセット セキュリティ ポリシーでは構成されていません。 **Standard** と **Strict** の値は、作成する新しい安全な添付ファイル ポリシーで **推奨** される値を示します。|
|**スキャンが完了できない場合に安全な添付ファイル検出応答を適用する (タイムアウトまたはエラー)** <p> _ActionOnError_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||

### <a name="safe-links-settings"></a>セーフ リンクの設定

Defender for Office 365のセーフ リンクには、アクティブなセーフ リンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定と、各セーフ リンク ポリシーに固有の設定が含まれます。 詳細については、「[Defender for Office 365のセーフ リンク](safe-links.md)」を参照してください。

既定のセーフ リンク ポリシーはありませんが、 **組み込みの保護** プリセット セキュリティ ポリシーは、すべての受信者 (カスタムセーフ リンク ポリシーで定義されていないユーザー) に安全なリンク保護を提供します。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

#### <a name="global-settings-for-safe-links"></a>セーフ リンクのグローバル設定

> [!NOTE]
> セーフ リンクのグローバル設定は **、組み込みの保護** プリセット セキュリティ ポリシーによって設定されますが、 **Standard** または **Strict** の事前設定されたセキュリティ ポリシーでは設定されません。 どちらの方法でも、管理者はいつでもこれらのグローバルセーフ リンク設定を変更できます。
>
> **[既定]** 列には、**組み込みの保護** プリセット セキュリティ ポリシーが存在する前の値が表示されます。 **[組み込みの保護**] 列には、**組み込みの保護** プリセット セキュリティ ポリシーによって設定される値が表示されます。これは推奨値でもあります。

これらの設定を構成するには、「[Defender for Office 365のセーフ リンクのグローバル設定を構成](configure-global-settings-for-safe-links.md)する」を参照してください。

PowerShell では、これらの設定に [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) コマンドレットを使用します。

|セキュリティ機能名|既定値|組み込みの保護|コメント|
|---|:---:|:---:|---|
|**次の URL をブロックする** <p> _ExcludedUrls_|空白 <p> `$null`|空白 <p> `$null`|この設定に関する具体的な推奨事項はありません。 <p> 詳細については、 [セーフ リンクの「次の URL をブロックする」の一覧を参照してください](safe-links.md#block-the-following-urls-list-for-safe-links)。 <p> **注**: [テナント許可/ブロック リスト](allow-block-urls.md#create-block-url-entries-in-the-tenant-allowblock-list)でブロック URL エントリを管理できるようになりました。 "次の URL をブロックする" 一覧は非推奨のプロセスです。 既存のエントリを "次の URL をブロックする" リストから移行し、テナント許可/ブロック リストの URL エントリをブロックします。 ブロックされた URL を含むメッセージは検疫されます。|
|**Office 365 アプリで安全なリンクを使用する** <p> _EnableSafeLinksForO365Clients_|オン <p> `$true`|オン <p> `$true`|サポートされているOffice 365デスクトップおよびモバイル (iOS および Android) アプリで安全なリンクを使用します。 詳細については、「[Office 365 アプリ向けの安全なリンク設定](safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。|
|**ユーザーがOffice 365 アプリで保護されたリンクをクリックしたときに追跡しない** <p> _TrackClicks_|オン <p> `$false`|オフ <p> `$true`|この設定をオフにする (_TrackClicks_ を設定) `$true`すると、サポートされているOffice 365 アプリでユーザーのクリックが追跡されます。|
|**ユーザーがOffice 365 アプリの元の URL をクリックできないようにする** <p> _AllowClickThrough_|オン <p> `$false`|オン <p> `$false`|この設定をオンにする (_AllowClickThrough_ を設定) `$false`すると、サポートされているOffice 365 アプリの元の URL へのクリックが防止されます。|

#### <a name="safe-links-policy-settings"></a>セーフ リンク ポリシーの設定

これらの設定を構成するには、「[Microsoft Defender for Office 365でのセーフ リンク ポリシーの設定](set-up-safe-links-policies.md)」を参照してください。

PowerShell では、これらの設定に [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) コマンドレットと [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) コマンドレットを使用します。

> [!NOTE]
> 前述のように、既定のセーフ リンク ポリシーはありませんが、安全なリンク保護は [**、組み込みの保護** プリセット セキュリティ ポリシー](preset-security-policies.md)によってすべての受信者に割り当てられます。
>
> **カスタム列の既定値** は、作成した新しいセーフ リンク ポリシーの既定値を参照します。 残りの列は、対応する事前設定済みセキュリティ ポリシーで構成されている値を (特に明記されていない限り) 示します。

|セキュリティ機能名|カスタムの既定値|組み込みの保護|Standard|Strict|コメント|
|---|:---:|:---:|:---:|:---:|---|
|**URL &クリック保護設定**||||||
|**電子メール内の潜在的に悪意のある URL に対するアクション**||||||
|**オン: セーフ リンクは、ユーザーが電子メール内のリンクをクリックすると、既知の悪意のあるリンクの一覧をチェックします** <p> _EnableSafeLinksForEmail_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**組織内で送信された電子メール メッセージに安全なリンクを適用する** <p> _EnableForInternalSenders_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**不審なリンクや、ファイルを指しているリンクに対してリアルタイム URL スキャンを適用します** <p> _ScanUrls_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**URL スキャンが完了するまで待ち、その後でメッセージを配信します。** <p> _DeliverMessageAfterScan_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**URL を書き換えない、Safe Links API を使用したチェックのみ行う** <p> _DisableURLRewrite_|未選択 <p> `$false`|選択済み <p> `$true`|未選択 <p> `$false`|未選択 <p> `$false`||
|**電子メールで次の URL を書き換えないでください** <p> _DoNotRewriteUrls_|未選択 <p> 空白|未選択 <p> 空白|未選択 <p> 空白|未選択 <p> 空白|この設定に関する具体的な推奨事項はありません。 <p> **注**: [次の URL を書き換えない] 一覧の目的は、指定した URL のセーフ リンクの折り返しをスキップすることです。 この一覧を使用する代わりに、 [テナント許可/ブロック リストに許可 URL エントリを作成](allow-block-urls.md#create-allow-url-entries)できるようになりました。|
|**Microsoft Teams の潜在的に悪意のある URL に対するアクション**||||||
|**オン: 安全なリンクは、ユーザーが Microsoft Teams でリンクをクリックすると、既知の悪意のあるリンクの一覧をチェックします** <p> _EnableSafeLinksForTeams_|未選択 <p> `$false`|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**[保護の設定] をクリックする**||||||
|**ユーザーのクリックを追跡する** <p> _TrackUserClicks_|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`|選択済み <p> `$true`||
|**ユーザーが元の URL までクリックできるようにする** <p> _AllowClickThrough_|選択済み <p> `$true`|選択済み <p> `$true`|未選択 <p> `$false`|未選択 <p> `$false`|この設定をオフにする ( _AllowClickThrough_ を設定する `$false`) と、元の URL へのクリックが防止されます。|
|**通知ページと警告ページに組織のブランドを表示する** <p> _EnableOrganizationBranding_|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|未選択 <p> `$false`|この設定に関する具体的な推奨事項はありません。 <p> この設定を有効にする前に、 [組織の Microsoft 365 テーマをカスタマイズ](../../admin/setup/customize-your-organization-theme.md) して会社のロゴをアップロードする手順に従う必要があります。|
|**通知**||||||
|**ユーザーに通知する方法**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|**既定の通知テキストを使用する**|この設定に関する具体的な推奨事項はありません。 <p> [ **カスタム通知テキストを使用する** ] (_CustomNotificationText_) を選択して、使用するカスタマイズされた通知テキストを入力できます。 **自動ローカライズに Microsoft Translator を使用** する (_UseTranslatedNotificationText_) を選択して、カスタム通知テキストをユーザーの言語に翻訳することもできます。

## <a name="related-articles"></a>関連記事

- **Exchange メール フロー ルール (トランスポート ルールとも呼ばれます)** のベスト プラクティスをお探しですか? [Exchange Onlineでメール フロー ルールを構成するためのベスト プラクティスに](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)関するページを参照してください。

- 管理者とユーザーは、分析のために誤検知 (不適切とマークされた適切なメール) と偽陰性 (不適切なメールが許可されている) を Microsoft に送信できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- [EOP サービス](/exchange/standalone-eop/set-up-your-eop-service)を **設定** し、Microsoft Defender for Office 365を **構成** する方法については、次のリンク [を](defender-for-office-365.md)参照してください。 「[Office 365の脅威から保護](protect-against-threats.md)する」の便利な指示を忘れないでください。

- **Windows のセキュリティ ベースライン** については、次のページを参照してください。GPO/オンプレミス オプションの [セキュリティ ベースラインはどこで入手できます](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)。また、[セキュリティ ベースラインを使用して、Intune ベースのセキュリティをIntuneで Windows デバイスを構成](/intune/protect/security-baselines)します。 最後に、Microsoft Defender for EndpointとMicrosoft Intuneのセキュリティ ベースラインの比較は、「[Microsoft Defender for Endpointと Windows Intune セキュリティ ベースラインの比較](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)」を参照してください。
