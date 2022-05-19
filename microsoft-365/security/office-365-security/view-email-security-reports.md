---
title: メール セキュリティ レポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft 365 Defender ポータルで使用できる電子メール セキュリティ レポートを検索して使用する方法について説明します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 476807a03954475470a976113a2faa926862c008
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535948"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender ポータル<https://security.microsoft.com>にはさまざまなレポートがあり、Microsoft 365のスパム対策やマルウェア対策などの電子メール セキュリティ機能が組織をどのように保護しているかを確認するのに役立ちます。 [必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、この記事で説明されているように、これらのレポートを表示してダウンロードできます。

> [!NOTE]
>
> **[電子メール & コラボレーション レポート**] ページのレポートの一部には、Microsoft Defender for Office 365が必要です。 これらのレポートの詳細については、[Microsoft 365 Defender ポータルでレポートDefender for Office 365表示する方法に関するページを参照してください](view-reports-for-mdo.md)。
>
> メール フローに関連するレポートが、Exchange管理センターに表示されるようになりました。 これらのレポートの詳細については、[新しいExchange管理センターのメール フロー レポートに関する](/exchange/monitoring/mail-flow-reports/mail-flow-reports)ページを参照してください。

この短いビデオでは、レポートを使用して組織内のDefender for Office 365の有効性を理解する方法について説明します。
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBkxB]

## <a name="email-security-report-changes-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでの電子メール セキュリティ レポートの変更

置き換え、移動、または非推奨になったMicrosoft 365 Defender ポータルのExchange Online Protection (EOP) レポートとMicrosoft Defender for Office 365 レポートを次の表に示します。

|非推奨のレポートとコマンドレット|新しいレポートとコマンドレット|メッセージ センター ID|日付|
|---|---|:---:|:---:|
|**URL 追跡** <p> Get-URLTrace|[URL 保護レポート](view-reports-for-mdo.md#url-protection-report) <p> [Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <br> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|MC239999|2021 年 6 月|
|**送受信された電子メール レポート** <p> Get-MailTrafficReport <br> Get-MailDetailReport|[脅威保護の状態レポート](#threat-protection-status-report) <br> [Mailflow 状態レポート](#mailflow-status-report) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <br> [Get-MailFlowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|MC236025|2021 年 6 月|
|**転送レポート** <p> コマンドレットなし|[EAC の自動転送メッセージ レポート](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report) <p> コマンドレットなし|MC250533|2021 年 6 月|
|**セーフ添付ファイルの種類レポート** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[脅威保護の状態レポート: 電子メール \> マルウェアによるデータの表示](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250532|2021 年 6 月|
|**セーフ 添付ファイル メッセージの処理レポート** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[脅威保護の状態レポート: 電子メール \> マルウェアによるデータの表示](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250531|2021 年 6 月|
|**電子メール レポートで検出されたマルウェア** <p> Get-MailTrafficReport <br> Get-MailDetailMalwareReport|[脅威保護の状態レポート: 電子メール \> マルウェアによるデータの表示](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250530|2021 年 6 月|
|**スパム検出レポート** <p> Get-MailTrafficReport <br> Get-MailDetailSpamReport|[脅威の保護状態レポート: 電子メール \> スパムでデータを表示する](#view-data-by-email--spam-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250529|2021 年 10 月|
|Get-AdvancedThreatProtectionDocumentReport <p> Get-AdvancedThreatProtectionDocumentDetail|[Get-ContentMalwareMdoAggregateReport](/powershell/module/exchange/get-contentmalwaremdoaggregatereport) <p> [Get-ContentMalwareMdoDetailReport](/powershell/module/exchange/get-contentmalwaremdodetailreport)|未定|2022 年 5 月|
|**Exchange トランスポート ルール レポート** <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|[EAC でトランスポート ルール レポートをExchangeする](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report) <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|MC316157|2022 年 4 月|
|Get-MailTrafficTopReport|[脅威保護の状態レポート: 電子メール \> マルウェアによるデータの表示](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <p> **注**: Get-MailTrafficTopReport では、暗号化レポート機能に代わる機能はありません。|MC315742|2022 年 4 月|

## <a name="compromised-users-report"></a>侵害されたユーザー レポート

> [!NOTE]
> このレポートは、Exchange Onlineメールボックスを持つMicrosoft 365組織で使用できます。 スタンドアロン Exchange Online Protection (EOP) 組織では使用できません。

**侵害されたユーザー** レポートには、過去 7 日以内に **不審** または **制限** 付きとしてマークされたユーザー アカウントの数が表示されます。 これらの状態のいずれかに含まれるアカウントは、問題が生じるか、侵害される場合もあります。 頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントの急増、さらには傾向を特定できます。 侵害されたユーザーの詳細については、「 [侵害されたメール アカウントへの対応」を参照してください](responding-to-a-compromised-email-account.md)。

:::image type="content" source="../../media/compromised-users-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [侵害されたユーザー] ウィジェット" lightbox="../../media/compromised-users-report-widget.png":::

集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。

Microsoft 365 Defender ポータルで<https://security.microsoft.com>レポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、 **侵害されたユーザー** を見つけて、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/CompromisedUsers>。

[ **侵害されたユーザー** ] ページのグラフには、指定した日付範囲に関する次の情報が表示されます。

- **制限:** ユーザー アカウントは、非常に疑わしいパターンが原因で、電子メールの送信を制限されています。
- **疑わしい**: ユーザー アカウントから不審なメールが送信され、電子メールの送信が制限される危険性があります。

グラフの下の詳細テーブルは、次の情報を示しています。

- **作成時間**
- **[ユーザー ID]**
- **操作**
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **日付 (UTC)**: **開始日** と **終了日**。
- **アクティビティ**: **制限付き** または **疑わしい**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

[ **侵害されたユーザー** ] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

:::image type="content" source="../../media/compromised-users-report-activity-view.png" alt-text="侵害されたユーザー レポートのレポート ビュー" lightbox="../../media/compromised-users-report-activity-view.png":::

## <a name="exchange-transport-rule-report"></a>Exchange トランスポート ルール レポート

**Exchange トランスポート ルール** レポートは、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれます) の効果を示します。

Microsoft 365 Defender ポータルでレポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [**電子メール & コラボレーション レポート**] ページ **で、トランスポート ルールExchange** 見つけて、[**詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/ETRRuleReport>。

:::image type="content" source="../../media/transport-rule-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [Exchange トランスポート ルール] ウィジェット" lightbox="../../media/transport-rule-report-widget.png":::

**Exchangeトランスポート ルール レポート** ページで、使用可能なグラフとデータについては、次のセクションで説明します。
> [!NOTE]
> **Exchangeトランスポート ルール レポート** が EAC で使用できるようになりました。 詳細については、[新しい EAC のトランスポート ルール レポートExchangeを参照してください](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report)。

### <a name="chart-breakdown-by-direction"></a>方向別のグラフの内訳

:::image type="content" source="../../media/transport-rule-report-etr-direction-view.png" alt-text="Exchange トランスポート ルール レポートの Exchange トランスポート ルールの方向ビュー" lightbox="../../media/transport-rule-report-etr-direction-view.png":::

**[方向別のグラフの内訳**] を選択した場合は、次のグラフを使用できます。

- **Exchangeトランスポート ルールでデータを表示** する: メール フロー ルールの影響を受けた **受信** メッセージと **送信** メッセージの数。
- **DLP Exchange トランスポート ルールでデータを表示** する: データ損失防止 (DLP) メール フロー ルールの影響を受けた **受信** メッセージと **送信** メッセージの数。

グラフの下の詳細テーブルには、次の情報が表示されます。

- **Date**
- **DLP ポリシー** (**DLP Exchange トランスポート ルールのみでデータを表示**)
- **トランスポート ルール**
- **件名**
- **[送信者のアドレス]**
- **受信者の住所**
- **重大度**
- **方向**

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **日付 (UTC)** **開始日** と **終了日**。
- **方向**: **送信** と **受信**。
- **重大度**: **重大度が高い**、 **重大度が中程度**、 **重大度が低い**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**Exchangeトランスポート ルール レポート** ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="chart-breakdown-by-severity"></a>重大度別のグラフの内訳

:::image type="content" source="../../media/transport-rule-report-etr-severity-view.png" alt-text="Exchange トランスポート ルール レポートの Exchange トランスポート ルールの重大度ビュー" lightbox="../../media/transport-rule-report-etr-severity-view.png":::

**[重要度別のグラフの内訳**] を選択した場合は、次のグラフを使用できます。

- **Exchangeトランスポート ルールでデータを表示** する: **重大度が高い** メッセージ、**中重大度** メッセージ、**および重大度の低い** メッセージの数。 重大度レベルをルールのアクションとして設定します (重大度レベルまたは _SetAuditSeverity_ で **このルールを監査** します)。 詳細については、「[Exchange Onlineのメール フロー ルールアクション](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。

- **DLP Exchange トランスポート ルールでデータを表示** する: DLP メール フロー ルールの影響を受けた **重大度が高** い、重大度が **中程度**、**低の** メッセージの数。

グラフの下の詳細テーブルには、次の情報が表示されます。

- **Date**
- **DLP ポリシー** (**DLP Exchange トランスポート ルールのみでデータを表示**)
- **トランスポート ルール**
- **件名**
- **[送信者のアドレス]**
- **受信者の住所**
- **重大度**
- **方向**

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **日付 (UTC)** **開始日** と **終了日**
- **方向**: **送信** と **受信**
- **重大度**: **重大度が高い**、 **重大度が中程度**、 **重大度が低い**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**Exchangeトランスポート ルール レポート** ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

## <a name="forwarding-report"></a>転送レポート

> [!NOTE]
> このレポートは EAC で使用できるようになりました。 詳細については、 [新しい EAC の自動転送メッセージ レポートに関するページを参照してください](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。

## <a name="mailflow-status-report"></a>Mailflow 状態レポート

**Mailflow 状態レポート** は、送受信メール、スパム検出、マルウェア、"良い" と識別されたメール、エッジで許可またはブロックされた電子メールに関する情報を表示するスマート レポートです。 これは、エッジ保護情報を含む唯一のレポートであり、Exchange Online Protection (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量のみを示します。 メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされることを理解することが重要です。

Microsoft 365 Defender ポータルで<https://security.microsoft.com>レポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、[ **メールフローの状態の概要** ] を探し、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/mailflowStatusReport>。

:::image type="content" source="../../media/mail-flow-status-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [Mailflow 状態の概要] ウィジェット" lightbox="../../media/mail-flow-status-report-widget.png":::

### <a name="type-view-for-the-mailflow-status-report"></a>Mailflow 状態レポートの種類ビュー

:::image type="content" source="../../media/mail-flow-status-report-type-view.png" alt-text="Mailflow 状態レポートの [種類] ビュー" lightbox="../../media/mail-flow-status-report-type-view.png":::

**[メールフローの状態] レポート** ページの [**種類**] タブは既定で選択されています。 グラフには、指定した日付範囲に関する次の情報が表示されます。

- **適切なメール**: スパムでないと判断されたメール、またはユーザーまたは組織のポリシーで許可されている電子メール。
- **合計**
- **マルウェア**: さまざまなフィルターによってマルウェアとしてブロックされている電子メール。
- **フィッシングメール**: さまざまなフィルターによってフィッシングとしてブロックされている電子メール。
- **スパム**: さまざまなフィルターによってスパムとしてブロックされている電子メール。
- **エッジ保護**: EOP またはDefender for Office 365によって評価される前に、エッジ/境界で拒否された電子メール。
- **ルール メッセージ**: メール フロー ルールによって処理された電子メール メッセージ (トランスポート ルールとも呼ばれます)。

グラフの下の詳細テーブルは、次の情報を示しています。

- **方向**
- **Type**
- **24 時間**
- **3 日間**
- **7 日間**
- **15 日**
- **30 日間**

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **日付 (UTC)**: **開始日** と **終了日**。
- **メールの方向**: **受信** と **送信**。
- **型**:
  - **良いメール**
  - **マルウェア**
  - **スパム**
  - **エッジ保護**
  - **ルール メッセージ**
  - **フィッシング詐欺メール**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**メールフロー状態レポート** ページに戻り、詳細については [**カテゴリの選択**] をクリックすると、次の値から選択できます。

- **フィッシングメール**: この選択により [、脅威保護の状態レポートが表示](view-email-security-reports.md#threat-protection-status-report)されます。
- **電子メール内のマルウェア**: この選択を選択すると、 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)に移動します。
- **スパム検出**: この選択により、[ [スパム検出] レポートに移動します](view-email-security-reports.md#spam-detections-report)。
- **Edge ブロックされたスパム**: この選択を選択すると、[ [スパム検出] レポートに移動します](view-email-security-reports.md#spam-detections-report)。

**[メールフローの状態] レポート** ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュール](#schedule-report)** とエクスポートアイコンを ![作成します。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="direction-view-for-the-mailflow-status-report"></a>Mailflow 状態レポートの方向ビュー

:::image type="content" source="../../media/mail-flow-status-report-direction-view.png" alt-text="メールフロー状態レポートの [方向] ビュー" lightbox="../../media/mail-flow-status-report-direction-view.png":::

[ **方向** ] タブをクリックすると、指定した日付範囲の次の情報がグラフに表示されます。

- **受信**
- **送信**

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **日付 (UTC)**: **開始日** と **終了日**。
- **メールの方向**: **受信** と **送信**。
- **型**:
  - **良いメール**
  - **マルウェア**
  - **スパム**
  - **エッジ保護**
  - **ルール メッセージ**
  - **フィッシング詐欺メール**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**メールフロー状態レポート** ページに戻り、詳細については [**カテゴリの選択**] をクリックすると、次の値から選択できます。

- **フィッシングメール**: この選択により [、脅威保護の状態レポートが表示](view-email-security-reports.md#threat-protection-status-report)されます。
- **電子メール内のマルウェア**: この選択を選択すると、 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)に移動します。
- **スパム検出**: この選択により、[ [スパム検出] レポートに移動します](view-email-security-reports.md#spam-detections-report)。
- **Edge ブロックされたスパム**: この選択を選択すると、[ [スパム検出] レポートに移動します](view-email-security-reports.md#spam-detections-report)。

**[メールフローの状態] レポート** ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **スケジュール** とエクスポートアイコンを ![作成します。](../../media/m365-cc-sc-download-icon.png) **エクスポート** ボタンを使用できます。

### <a name="mailflow-view-for-the-mailflow-status-report"></a>Mailflow 状態レポートのメールフロー ビュー

**[メールフロー]** ビューには、Microsoft の電子メール脅威保護機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。 このビューでは、水平フロー図 ( _Sankey_ 図と呼ばれます) を使用して、電子メールの合計数と、構成された脅威保護機能 (エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策など) がどのようにこの数に影響するかを示します。

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view.png" alt-text="Mailflow 状態レポートの [メールフロー] ビュー" lightbox="../../media/mail-flow-status-report-mailflow-view.png":::

集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。

図の情報は、**EOP** または **Defender for Office 365** テクノロジによって色分けされています。

この図は、次の水平バンドに編成されています。

- **合計電子メール** バンド: この値は常に最初に表示されます。
- **エッジ ブロック** と **処理済み** バンド:
  - **エッジ ブロック: エッジ** でフィルター処理され、Edge Protection として識別されるメッセージ。
  - **処理済み**: フィルター処理スタックによって処理されるメッセージ。
- 結果バンド:
  - **ルール ブロック**: Exchangeメール フロー ルール (トランスポート ルール) によって処理されるメッセージ。
  - **マルウェア ブロック**: さまざまなフィルターによってマルウェアとして識別されるメッセージ。<sup>\*</sup>
  - **フィッシング ブロック**: さまざまなフィルターによって処理中にフィッシングとして識別されたメッセージ。<sup>\*</sup>
  - **スパム ブロック**: さまざまなフィルターによって処理中にスパムとして識別されたメッセージ。<sup>\*</sup>
  - **偽装ブロック**: Defender for Office 365でユーザー権限借用またはドメイン偽装として検出されたメッセージ。<sup>\*</sup>
  - **デトネーション ブロック**: セーフの添付ファイル ポリシーまたは Defender for Office 365のセーフ リンク ポリシーによって、ファイルまたは URL の起爆中に検出されたメッセージ。<sup>\*</sup>
  - **ZAP が削除されました**: ゼロ時間の自動消去 (ZAP) によって削除されたメッセージ。<sup>\*</sup>
  - **配信済み**: 許可が原因でユーザーに配信されたメッセージ。<sup>\*</sup>

図内の水平バンドにマウス ポインターを合わせると、関連するメッセージの数が表示されます。

<sup>\*</sup> この要素をクリックすると、ダイアグラムが展開され、詳細が表示されます。 展開されたノード内の各要素の説明については、「 [検出テクノロジ](/office/office-365-management-api/office-365-management-activity-api-schema#detection-technologies)」を参照してください。

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view-details.png" alt-text="Mailflow 状態レポートのメールフロー ビューのフィッシング ブロックの詳細" lightbox="../../media/mail-flow-status-report-mailflow-view-details.png":::

図の下の詳細テーブルは、次の情報を示しています。

- **Date**
- **メールの合計**
- **フィルター処理されたエッジ**
- **ルール メッセージ**
- **マルウェア対策エンジン、セーフ添付ファイル、フィルター処理されたルール**
- **DMARC 偽装、スプーフィング、フィッシング フィルター処理**
- **デトネーション検出**
- **フィルター処理されたスパム対策**
- **ZAP が削除されました**
- **脅威が検出されなかったメッセージ**

詳細テーブルで行を選択すると、表示される詳細ポップアップに電子メール数の詳細が表示されます。

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **日付 (UTC)** **開始日** と **終了日**。
- **方向**: **送信** と **受信**。

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[メールフローの状態] レポート** ページに戻り、[**傾向の表示**] をクリックすると、表示される **Mailflow** 傾向ポップアップに傾向グラフが表示されます。

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view-show-trends.png" alt-text="Mailflow 状態レポートの Mailflow ビューの Mailflow 傾向ポップアップ" lightbox="../../media/mail-flow-status-report-mailflow-view-show-trends.png":::

**[メールフローの状態] レポート** ページの [エクスポート] ![アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート]** ボタンを使用できます。

## <a name="malware-detections-report"></a>マルウェア検出レポート

> [!NOTE]
> このレポートは非推奨になりました。 [脅威保護の状態レポート](#threat-protection-status-report)でも、同じ情報を入手できます。

## <a name="mail-latency-report"></a>メール待機時間レポート

Defender for Office 365の **メール待機時間レポート** には、組織内で発生したメール配信と起爆の待機時間に関する情報が含まれています。 詳細については、「 [メール待機時間レポート](view-reports-for-mdo.md#mail-latency-report)」を参照してください。

## <a name="spam-detections-report"></a>スパム検出レポート

> [!NOTE]
> このレポートは非推奨になりました。 [脅威保護の状態レポート](#threat-protection-status-report)でも、同じ情報を入手できます。

## <a name="spoof-detections-report"></a>スプーフィング検出レポート

**スプーフィング検出レポートには、スプーフィン** グが原因でブロックまたは許可されたメッセージに関する情報が表示されます。 スプーフィングの詳細については、 [EOP でのスプーフィング対策の保護に関するページを](anti-spoofing-protection.md)参照してください。

レポートの集計ビューでは 90 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター処理のみが許可されます。

Microsoft 365 Defender ポータルでレポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、[ **スプーフィングの検出** ] を見つけて、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpoofMailReport>。

:::image type="content" source="../../media/spoof-detections-widget.png" alt-text="電子メール & コラボレーション レポート ページのスプーフィング検出ウィジェット" lightbox="../../media/spoof-detections-widget.png":::

グラフには、次の情報が表示されます。

- **渡す**
- **Fail/失敗**
- **SoftPass**
- **なし**
- **その他**

グラフで 1 日 (データ ポイント) をポイントすると、スプーフィングされたメッセージが検出された数とその理由を確認できます。

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **日付 (UTC)** **開始日** と **終了日**
- **結果**:
  - **渡す**
  - **Fail/失敗**
  - **SoftPass**
  - **なし**
  - **その他**
- **スプーフィングの種類**: **内部** と **外部**

:::image type="content" source="../../media/spoof-detections-report-page.png" alt-text="Microsoft 365 Defender ポータルの [スプーフィング メール] レポート ページ" lightbox="../../media/spoof-detections-report-page.png":::

グラフの下の詳細テーブルは、次の情報を示しています。

- **Date**
- **スプーフィングされたユーザー**
- **インフラストラクチャの送信**
- **スプーフィングの種類**
- **結果**
- **結果コード**
- **SPF**
- **DKIM**
- **DMARC**
- **メッセージ数**

複合認証結果コードの詳細については、[Microsoft 365のスパム対策メッセージ ヘッダーに](anti-spam-message-headers.md)関するページを参照してください。

[ **スプーフィングの検出** ] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

## <a name="submissions-report"></a>提出レポート

提出レポートには、管理者が分析のために Microsoft に報告したアイテムに関する情報が表示 **されます** 。 詳細については、「 [管理者申請を使用して、疑わしいスパム、フィッシング、URL、およびファイルを Microsoft に送信する」を参照してください](admin-submission.md)。

Microsoft 365 Defender ポータルで<https://security.microsoft.com>レポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、[ **申請] を** 探し、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/adminSubmissionReport>。 [Microsoft 365 Defender ポータルで管理者の申請に](admin-submission.md)移動するには、[**送信に移動**] をクリックします。 管理者は、過去 30 日間レポートを表示できます。

:::image type="content" source="../../media/submissions-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [申請] ウィジェット" lightbox="../../media/submissions-report-widget.png":::

グラフには、次の情報が表示されます。

- **Pending**
- **Completed**

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **報告された日付**: **開始時刻** と **終了時刻**
- **提出の種類**:
  - **電子メール**
  - **URL**
  - **ファイル**
- **申請 ID**
- **ネットワーク メッセージ ID**
- **Sender**
- **Name**
- **提出者**
- **送信の理由**:
  - **迷惑ではない**
  - **フィッシング**
  - **マルウェア**
  - **スパム**
- **再スキャン状態**:
  - **Pending**
  - **Completed**

グラフの下の詳細テーブルには、同じ情報が表示され、[**電子メール & コラボレーション**\>申請] の [**分析用に送信]** タブと同じ **[グループ**] または [**列のカスタマイズ**] オプションが **表示されます**。 詳細については、「 [Microsoft への管理者の提出を表示する」を参照してください](admin-submission.md#view-admin-submissions-to-microsoft)。

[ **申請] ページの** [ **[エクスポート](#export-report)** ] ボタンを使用できます。

:::image type="content" source="../../media/submissions-report-page.png" alt-text="Microsoft 365 Defender ポータルの [申請] レポート ページ" lightbox="../../media/submissions-report-page.png":::

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

**脅威の保護の状態** レポートは、EOP とDefender for Office 365の両方で使用できます。ただし、レポートには異なるデータが含まれています。 たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、[SharePoint、OneDrive、およびMicrosoft Teamsのセーフ添付ファイル](mdo-for-spo-odb-and-teams.md)によって検出された悪意のあるファイルに関する情報は表示できません。

このレポートには、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス (URL)、[ゼロ時間自動消去 (ZAP](zero-hour-auto-purge.md))、フィッシング対策ポリシーのセーフ [リンク](safe-links.md)、セーフ[添付ファイル](safe-attachments.md)、[偽装保護機能](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)などのDefender for Office 365機能など、悪意のあるコンテンツを含む電子メール メッセージの数が表示されます。 この情報を使用して、傾向を把握したり、組織のポリシーを調整する必要があるかどうかを判断することができます。

**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされることを理解することが重要です。

Microsoft 365 Defender ポータルでレポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、 **脅威の保護の状態** を確認し、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、次のいずれかの URL を開きます。

- Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP>
- EOP： <https://security.microsoft.com/reports/TPSAggregateReport>

:::image type="content" source="../../media/threat-protection-status-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [脅威保護の状態] ウィジェット" lightbox="../../media/threat-protection-status-report-widget.png":::

既定では、グラフには過去 7 日間のデータが表示されます。 **脅威保護の状態レポート** ページで **[フィルター**] をクリックすると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。 詳細テーブルでは、30 日間フィルター処理できます。

使用可能なビューについては、次のセクションで説明します。

### <a name="view-data-by-overview"></a>概要でデータを表示する

:::image type="content" source="../../media/threat-protection-status-report-overview-view.png" alt-text="脅威の保護状態レポートの [概要] ビュー" lightbox="../../media/threat-protection-status-report-overview-view.png":::

概要 **ビューでデータを表示** すると、次の検出情報がグラフに表示されます。

- **電子メール マルウェア**
- **メール フィッシング**
- **電子メールスパム**
- **コンテンツ マルウェア**

グラフの下に詳細テーブルはありません。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**。
- **検出**:
  - **電子メール マルウェア**
  - **メール フィッシング**
  - **電子メールスパム**
  - **コンテンツ マルウェア**
- **保護対象**: **MDO** (Defender for Office 365) と **EOP**。
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。 ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a>電子メール \> フィッシングとグラフの内訳でデータを検出テクノロジ別に表示する

:::image type="content" source="../../media/threat-protection-status-report-phishing-detection-tech-view.png" alt-text="脅威の保護状態レポートのフィッシングメールの検出テクノロジ ビュー" lightbox="../../media/threat-protection-status-report-phishing-detection-tech-view.png":::

> [!NOTE]
> 2021 年 5 月以降、フィッシング URL を含む **メッセージ添付ファイル** を含めるように、電子メールのフィッシング検出が更新されました。 この変更により、検出ボリュームの一部が [ **電子メール マルウェアによるデータの表示] ビューと [電子メール \> フィッシング** による **データ \> の表示]** ビューにシフトされる場合があります。 言い換えると、従来マルウェアとして識別されていたフィッシング URL を含むメッセージの添付ファイルは、代わりにフィッシングとして識別される可能性があります。

[ **検出テクノロジ別の電子メール \> フィッシング** と **グラフの内訳別** のデータの表示] ビューには、次の情報がグラフに表示されます。

- **URL 悪意のある評判**<sup>\*</sup>: 他のMicrosoft 365顧客のDefender for Office 365爆発から生成された悪意のある URL の評判。
- **高度なフィルター**: 機械学習に基づくフィッシングシグナル。
- **一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。
- **組織内スプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしています。
- **外部ドメインのスプーフィング**: 送信者が他のドメインをスプーフィングしようとしています。
- **DMARC のスプーフィング**: メッセージに対する DMARC 認証エラー。
- **偽装ブランド**: 送信者に基づく既知のブランドの偽装。
- **複合分析の検出**
- **ファイルの評価**
- **指紋の一致**
- **URL の起爆評価**<sup>\*</sup>
- **URL デトネーション**<sup>\*</sup>
- **偽装ユーザー**<sup>\*</sup>
- **偽装ドメイン**<sup>\*</sup>: 顧客が所有または定義するドメインの偽装。
- **メールボックス インテリジェンスの偽装**<sup>\*</sup>: 管理者によって定義された、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。
- **ファイルデトネーション**<sup>\*</sup>
- **ファイルデトネーションの評価**<sup>\*</sup>
- **キャンペーン**<sup>\*</sup>

<sup>\*</sup>Defender for Office 365のみ

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **検出**: グラフと同じ値。
- **保護対象**: **MDO** (Defender for Office 365) または **EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ)**: **すべて** または指定されたポリシー。
- **受信者**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[脅威の保護の状態**] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-email--spam-and-chart-breakdown-by-detection-technology"></a>電子メール \> スパムとグラフの内訳別のデータを検出テクノロジ別に表示する

:::image type="content" source="../../media/threat-protection-status-report-spam-detection-tech-view.png" alt-text="脅威保護の状態レポートのスパムの検出テクノロジ ビュー" lightbox="../../media/threat-protection-status-report-spam-detection-tech-view.png":::

[ **検出テクノロジ別の電子メール \> スパム** と **グラフの内訳別** のデータの表示] ビューで、次の情報がグラフに表示されます。

- **URL に悪意があるとする評価**
- **高度なフィルター**
- **一般的なフィルター**
- **混合分析検出**: 複数のフィルターがメッセージの判定に貢献しました。
- **指紋照合**: 以前のメッセージが原因で、メッセージが正しくないとマークされました。
- **ドメインの評判**: このメッセージは、送信者ドメインの評判に基づいてスパムと見なされました。
- **一括**: ユーザーの一括設定を超えると検出されたアイテム。
- **IP 評判**: メッセージは、送信 IP アドレスの評判に基づいてスパムと見なされました。

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **検出**: グラフと同じ値。
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ)**: **すべて** または指定されたポリシー。
- **受信者**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[脅威の保護の状態**] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a>電子メール \> マルウェアとグラフの内訳を検出テクノロジ別に表示する

:::image type="content" source="../../media/threat-protection-status-report-malware-detection-tech-view.png" alt-text="脅威保護の状態レポートのマルウェアの検出テクノロジ ビュー" lightbox="../../media/threat-protection-status-report-malware-detection-tech-view.png":::

> [!NOTE]
> 2021 年 5 月以降、メール内のマルウェア検出が更新され、メッセージの添付ファイルに **有害な URL が** 含まれています。 この変更により、検出ボリュームの一部が **[電子メール フィッシングによるデータの表示] ビューと [電子メール \>** **マルウェア別のデータ\>の表示]** ビューにシフトされる場合があります。 言い換えると、従来フィッシングとして識別されていたメッセージ添付ファイル内の有害な URL は、代わりにマルウェアとして識別される可能性があります。

[ **検出テクノロジ別の電子メール \> マルウェア** と **グラフの内訳別** のデータの表示] ビューで、グラフに次の情報が表示されます。

- **ファイルデトネーション**<sup>\*</sup>: セーフ添付ファイルによる検出。
- **ファイルデトネーションの評価**<sup>\*</sup>: Defender for Office 365デトネーションによって生成されるすべての悪意のあるファイルの評判。
- **ファイルの評価**
- **マルウェア対策エンジン**<sup>\*</sup>: マルウェア対策エンジンからの検出。
- **マルウェア対策ポリシー ファイルの種類ブロック**: これらは、メッセージ内で識別された悪意のあるファイルの種類のために除外された電子メール メッセージです。
- **URL 悪意のある評判**<sup>\*</sup>
- **URL デトネーション**<sup>\*</sup>
- **URL の起爆評価**<sup>\*</sup>
- **キャンペーン**<sup>\*</sup>

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **検出**: グラフと同じ値。
- **保護対象**: **MDO** (Defender for Office 365) または **EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ)**: **すべて** または指定されたポリシー。
- **受信者**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

[**Threat 保護の状態** ] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="chart-breakdown-by-policy-type"></a>ポリシーの種類別のグラフの内訳

:::image type="content" source="../../media/threat-protection-status-report-phishing-policy-type-view.png" alt-text="脅威の保護状態レポートのフィッシングメール、スパムメール、またはマルウェアメールのポリシーの種類ビュー" lightbox="../../media/threat-protection-status-report-phishing-policy-type-view.png":::

[**電子メール フィッシングによるデータの表示]、[電子メール \>****スパムによるデータの表示]、[電子メール \>****\> マルウェア別のデータの表示**] ビューで、[**ポリシーの種類別のグラフの内訳**] を選択すると、グラフに次の情報が表示されます。

- **マルウェア対策**
- **添付ファイルのセーフ**<sup>\*</sup>
- **フィッシング対策**
- **スパム対策**
- **メール フロー ルール** (トランスポート ルールとも呼ばれます)
- **Others**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **検出**:
  - **URL 悪意のある評判**<sup>\*</sup>: 他のMicrosoft 365顧客のDefender for Office 365爆発から生成された悪意のある URL の評判。
  - **高度なフィルター**: 機械学習に基づくフィッシングシグナル。
  - **一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。
  - **組織内スプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしています。
  - **外部ドメインのスプーフィング**: 送信者が他のドメインをスプーフィングしようとしています。
  - **DMARC のスプーフィング**: メッセージに対する DMARC 認証エラー。
  - **偽装ブランド**: 送信者に基づく既知のブランドの偽装。
  - **複合分析の検出**
  - **ファイルの評価**
  - **指紋の一致**
  - **URL の起爆評価**<sup>\*</sup>
  - **URL デトネーション**<sup>\*</sup>
  - **偽装ユーザー**<sup>\*</sup>
  - **偽装ドメイン**<sup>\*</sup>: 顧客が所有または定義するドメインの偽装。
  - **メールボックス インテリジェンスの偽装**<sup>\*</sup>: 管理者によって定義された、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。
  - **ファイルデトネーション**<sup>\*</sup>
  - **ファイルデトネーションの評価**<sup>\*</sup>
  - **キャンペーン**<sup>\*</sup>
- **保護対象**: **MDO** (Defender for Office 365) または **EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ)**: **すべて** または指定されたポリシー。
- **受信者**

<sup>\*</sup>Defender for Office 365のみ

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[脅威の保護の状態**] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="chart-breakdown-by-delivery-status"></a>配信状態別のグラフの内訳

:::image type="content" source="../../media/threat-protection-status-report-phishing-delivery-status-view.png" alt-text="脅威の保護状態レポートのフィッシングメールとマルウェアメールの配信状態ビュー" lightbox="../../media/threat-protection-status-report-phishing-delivery-status-view.png":::

**[メール フィッシングによるデータの表示]、[電子メール \>****スパム別のデータの表示]、[電子メール \>****\> マルウェア別のデータの表示**] ビューで、[**配信状態別のグラフの内訳**] を選択すると、グラフに次の情報が表示されます。

- **ホストされているメールボックス: 受信トレイ**
- **ホストされているメールボックス: 迷惑メール**
- **ホストされたメールボックス: カスタム フォルダー**
- **ホストされたメールボックス: 削除済みアイテム**
- **転送**
- **オンプレミス サーバー: 配信済み**
- **検疫**
- **配信に失敗しました**
- **削除**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **検出**:
  - **URL 悪意のある評判**<sup>\*</sup>: 他のMicrosoft 365顧客のDefender for Office 365爆発から生成された悪意のある URL の評判。
  - **高度なフィルター**: 機械学習に基づくフィッシングシグナル。
  - **一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。
  - **組織内スプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしています。
  - **外部ドメインのスプーフィング**: 送信者が他のドメインをスプーフィングしようとしています。
  - **DMARC のスプーフィング**: メッセージに対する DMARC 認証エラー。
  - **偽装ブランド**: 送信者に基づく既知のブランドの偽装。
  - **複合分析の検出**
  - **ファイルの評価**
  - **指紋の一致**
  - **URL の起爆評価**<sup>\*</sup>
  - **URL デトネーション**<sup>\*</sup>
  - **偽装ユーザー**<sup>\*</sup>
  - **偽装ドメイン**<sup>\*</sup>: 顧客が所有または定義するドメインの偽装。
  - **メールボックス インテリジェンスの偽装**<sup>\*</sup>: 管理者によって定義された、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。
  - **ファイルデトネーション**<sup>\*</sup>
  - **ファイルデトネーションの評価**<sup>\*</sup>
  - **キャンペーン**<sup>\*</sup>
- **保護対象**: **MDO** (Defender for Office 365) または **EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ)**: **すべて** または指定されたポリシー。
- **受信者**

<sup>\*</sup>Defender for Office 365のみ

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[脅威の保護の状態**] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-content--malware"></a>コンテンツ \> マルウェアによるデータの表示

:::image type="content" source="../../media/threat-protection-status-report-content-malware-view.png" alt-text="脅威の保護状態レポートの [コンテンツ マルウェア] ビュー" lightbox="../../media/threat-protection-status-report-content-malware-view.png":::

[**コンテンツ \> マルウェア別のデータの表示**] ビューでは、Microsoft Defender for Office 365組織のグラフに次の情報が表示されます。

- **マルウェア対策エンジン**: Microsoft 365の [組み込みのウイルス検出](virus-detection-in-spo.md)によって、SharePoint、OneDrive、およびMicrosoft Teamsで検出された悪意のあるファイル。
- **MDO デトネーション**: [SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイル](mdo-for-spo-odb-and-teams.md)によって検出された悪意のあるファイル。
- **ファイルの評価**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **日付 (UTC)**
- **添付ファイルの名前**
- **ワークロード**
- **検出テクノロジ**
- **ファイルのサイズ**
- **最終変更ユーザー**

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **検出**: **マルウェア対策エンジン**、 **MDO デトネーション**、 **ファイル デトネーション**
- **ワークロード**: **Teams**、**SharePoint**、**OneDrive**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[脅威の保護の状態**] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-system-override-and-chart-breakdown-by-reason"></a>システムのオーバーライドとグラフの内訳別のデータを理由別に表示する

:::image type="content" source="../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png" alt-text="脅威保護の状態レポートの [メッセージの上書き] ビューと [理由別グラフの内訳] ビュー" lightbox="../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png":::

**[システムオーバーライド別のデータの表示**] ビューと **[理由別グラフの内訳**] ビューでは、次のオーバーライド理由情報がグラフに表示されます。

- **オンプレミススキップ**
- **IP 許可**
- **Exchange トランスポート ルール** (メール フロー ルール)
- **組織で許可されている送信者**
- **組織で許可されているドメイン**
- **ZAP が有効になっていない**
- **ユーザー セーフ送信者**
- **ユーザー セーフ ドメイン**
- **フィッシング シミュレーション**: 詳細については、「 [サード パーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する方法を構成する」を](configure-advanced-delivery.md)参照してください。
- **サード パーティ製フィルター**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **システムオーバーライド**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **理由**: グラフと同じ値。
- **配信場所**: **迷惑メール フォルダーが有効になっていない** か **、SecOps メールボックス**。
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**: **すべて**
- **ポリシー名 (詳細テーブル ビューのみ)**: **すべて**
- **受信者**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[脅威の保護の状態**] ページの [エクスポート] ![アイコン。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート]](#export-report)** ボタンを使用できます。

### <a name="view-data-by-system-override-and-chart-breakdown-by-delivery-location"></a>配信場所別のシステム オーバーライドとグラフの内訳でデータを表示する

:::image type="content" source="../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png" alt-text="脅威の保護状態レポートの [配信場所別のメッセージの上書き] ビューと [グラフの内訳] ビュー" lightbox="../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png":::

[ **システムオーバーライド別のデータの表示** ] ビューと **[配信場所別のグラフの内訳** ] ビューでは、次のオーバーライド理由情報がグラフに表示されます。

- **迷惑メール フォルダーが有効になっていない**
- **SecOps メールボックス**: 詳細については、「 [サード パーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する方法を構成する」を](configure-advanced-delivery.md)参照してください。

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **システムオーバーライド**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

**[フィルター**] をクリックすると、次のフィルターを使用できます。

- **日付 (UTC)** **開始日** と **終了日**
- **理由**
  - **オンプレミススキップ**
  - **IP 許可**
  - **Exchange トランスポート ルール** (メール フロー ルール)
  - **組織で許可されている送信者**
  - **組織で許可されているドメイン**
  - **ZAP が有効になっていない**
  - **ユーザー セーフ送信者**
  - **ユーザー セーフ ドメイン**
  - **フィッシング シミュレーション**: 詳細については、「 [サード パーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する方法を構成する」を](configure-advanced-delivery.md)参照してください。
  - **サード パーティ製フィルター**
- **配信場所**: **迷惑メール フォルダーが有効になっていない** か **、SecOps メールボックス**。
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **すべて** または指定されたユーザー タグ (優先度アカウントを含む)。 ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。
- **ドメイン**: **すべて** または [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイルのセーフ**<sup>\*</sup>
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ)**: **すべて**
- **受信者**

<sup>\*</sup>Defender for Office 365のみ

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

**[脅威の保護の状態**] ページの [エクスポート] ![アイコン。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート]](#export-report)** ボタンを使用できます。

## <a name="top-malware-report"></a>上位マルウェア レポート

**[上位マルウェア**] レポートには、[EOP のマルウェア対策保護](anti-malware-protection.md)によって検出されたさまざまな種類のマルウェアが表示されます。

Microsoft 365 Defender ポータルでレポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、[ **上位マルウェア** ] を探し、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/TopMalware>。

:::image type="content" source="../../media/top-malware-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [上位マルウェア] ウィジェット" lightbox="../../media/top-malware-report-widget.png":::

円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが含まれていると検出されたメッセージの数が表示されます。

[ **上位マルウェア レポート** ] ページに、より大きなバージョンの円グラフが表示されます。 グラフの下の詳細テーブルは、次の情報を示しています。

- **上位マルウェア**
- **Count**

**[フィルター**] をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

[ **トップ マルウェア** ] ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュール](#schedule-report)** とエクスポートアイコンを ![作成します。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

:::image type="content" source="../../media/top-malware-report-view.png" alt-text="[上位マルウェア レポート] ビュー" lightbox="../../media/top-malware-report-view.png":::

## <a name="top-senders-and-recipients-report"></a>上位の送信者と受信者のレポート

**上位の送信者と受信者** のレポートは、EOP とDefender for Office 365の両方で使用できます。ただし、レポートには異なるデータが含まれています。 たとえば、EOP のお客様は、上位のマルウェア、スパム、フィッシング (スプーフィング) 受信者に関する情報を表示できますが、[偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)によって検出された[セーフ添付ファイル](safe-attachments.md)またはフィッシングによって検出されたマルウェアに関する情報は表示できません。

**上位の送信者と受信者** には、組織内の上位メッセージ送信者と、EOP およびDefender for Office 365保護機能によって検出されたメッセージの上位受信者が表示されます。 既定では、レポートには過去 1 週間のデータが表示されますが、データは過去 90 日間使用できます。

Microsoft 365 Defender ポータルで<https://security.microsoft.com>レポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、[ **上位の送信者と受信者] レポートを** 探し、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、次のいずれかの URL を開きます。

- Defender for Office 365:<https://security.microsoft.com/reports/TopSenderRecipientsATP>
- EOP： <https://security.microsoft.com/reports/TopSenderRecipient>

:::image type="content" source="../../media/top-senders-and-recipients-widget.png" alt-text="レポート ダッシュボードの上位送信者と受信者ウィジェット" lightbox="../../media/top-senders-and-recipients-widget.png":::

円グラフでくさびの上にマウス ポインターを置くと、送信者または受信者のメッセージの数が表示されます。

[ **上位の送信者と受信者]** ページに、より大きなバージョンの円グラフが表示されます。 次のグラフを使用できます。

- **上位のメール送信者のデータを表示する** (これは既定のビューです)
- **上位のメール受信者のデータを表示する**
- **上位スパム受信者のデータを表示する**
- **上位マルウェア受信者のデータを表示する** (EOP)
- **フィッシング詐欺の上位受信者のデータを表示する**
- **上位マルウェア受信者のデータを表示する (MDO)**
- **上位のフィッシング受信者 (MDO) のデータを表示する**

選択内容に基づいてデータが変更されます。

円グラフでくさびの上にマウス ポインターを置くと、その特定の送信者または受信者のメッセージ数が表示されます。

グラフの下の詳細テーブルは、選択したビューに基づいて送信者または受信者とメッセージ数を示しています。

[フィルター] をクリックし、[**開始日**] と [**終了日**] を選択すると、グラフと詳細テーブルの両方を **フィルター処理** できます。 ユーザーは、ユーザー タグでフィルター処理することもできます。 

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

[ **上位の送信者と受信者] ページの** [エクスポート] ![アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート]** ボタンを使用できます。

:::image type="content" source="../../media/top-senders-and-recipients-report-view.png" alt-text="[上位の送信者と受信者] レポートの [上位のメール送信者のデータを表示する] ビュー" lightbox="../../media/top-senders-and-recipients-report-view.png":::

## <a name="url-protection-report"></a>URL 保護レポート

**URL 保護レポート** は、Microsoft Defender for Office 365でのみ使用できます。 詳細については、「 [URL 保護レポート」を](view-reports-for-mdo.md#url-protection-report)参照してください。

## <a name="user-reported-messages-report"></a>ユーザーが報告したメッセージ レポート

> [!IMPORTANT]
> **ユーザーが報告したメッセージ** レポートを正しく機能させるには、Microsoft 365環境 **で監査ログを有効にする必要があります**。 これは通常、Exchange Onlineで監査ログ ロールが割り当てられているユーザーによって行われます。 詳細については、「[監査ログ検索Microsoft 365オンまたはオフにする」を](../../compliance/turn-audit-log-search-on-or-off.md)参照してください。

**ユーザーが報告したメッセージ** レポートには、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して、ユーザーが迷惑メール、フィッシング詐欺の試み、または適切なメールとして報告した電子メール [メッセージ](enable-the-report-message-add-in.md)に関 [する情報が](enable-the-report-phish-add-in.md)表示されます。

Microsoft 365 Defender ポータルでレポートを表示するには、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、[ **ユーザーから報告されたメッセージ]** を探し、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/userSubmissionReport>。 [Microsoft 365 Defender ポータルで管理者の申請に](admin-submission.md)移動するには、[**送信に移動**] をクリックします。

:::image type="content" source="../../media/user-reported-messages-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [ユーザーから報告されたメッセージ] ウィジェット" lightbox="../../media/user-reported-messages-widget.png":::

[フィルター] をクリックし、表示されるポップアップで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方を **フィルター** 処理できます。

- **報告された日付**: **開始時刻** と **終了時刻**
- [**レポート作成者**]
- **メールの件名**
- **メッセージ報告 ID**
- **ネットワーク メッセージ ID**
- **Sender**
- **報告された理由**
  - **迷惑ではない**
  - **フィッシング**
  - **スパム**
- **フィッシング シミュレーション**: **はい** または **いいえ**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

エントリをグループ化するには、[ **グループ化** ] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。

- **なし**
- **理由**
- **Sender**
- [**レポート作成者**]
- **結果を再スキャンする**
- **フィッシング シミュレーション**

:::image type="content" source="../../media/user-reported-messages-report.png" alt-text="ユーザーから報告されたメッセージ レポート" lightbox="../../media/user-reported-messages-report.png":::

グラフの下の詳細テーブルは、次の情報を示しています。

- **メールの件名**
- [**レポート作成者**]
- **報告日**
- **Sender**
- **報告された理由**
- **結果を再スキャンする**
- **タグ**: ユーザー タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

分析のために Microsoft にメッセージを送信するには、テーブルからメッセージ エントリを選択し、 **分析のために [Microsoft に送信]** をクリックし、ドロップダウン リストから次のいずれかの値を選択します。

- **クリーンなレポート**
- **フィッシングを報告する**
- **マルウェアを報告する**
- **スパムを報告する**'
- **トリガー調査** (Defender for Office 365)

[ **ユーザーから報告されたメッセージ]** ページの [エクスポート] ![アイコン。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート]](#export-report)** ボタンを使用できます。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するには、どのようなアクセス許可が必要ですか?

この記事で説明されているレポートを表示して使用するには、Microsoft 365 Defender ポータルで次のいずれかのロール グループのメンバーである必要があります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ閲覧者**
- **グローバル リーダー**

詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

**注**: Microsoft 365 管理センターの対応するAzure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可 _と_、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合はどうなりますか?

レポートにデータが表示されない場合は、使用しているフィルターを確認し、ポリシーが正しく設定されていることを再確認します。 詳細については、「 [脅威から保護する](protect-against-threats.md)」を参照してください。

## <a name="schedule-report"></a>スケジュール レポート

1. 特定のレポートのメイン ページで、[スケジュールの作成] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **スケジュールを作成します**。
2. **スケジュールされたレポートの作成** ウィザードが開きます。 [ **名前のスケジュールされたレポート]** ページで、[ **名前** ] の値を確認またはカスタマイズし、[ **次へ**] をクリックします。
3. [ **基本設定の設定] ページで** 、次の設定を構成します。
   - **頻度**: 次のいずれかの値を選択します。
     - **毎週** (既定値)
     - **毎月**
   - **開始日**: レポートの生成が開始されたとき。 既定値は現在です。
   - **有効期限**: レポートの生成が終了したとき。 既定値は、今日から 1 年間です。

   完了したら、**[次へ]** をクリックします。

4. [ **受信者] ページで** 、レポートの受信者を選択します。 既定値はメール アドレスですが、他のユーザーを追加できます。

   完了したら、**[次へ]** をクリックします。

5. [ **校閲** ] ページで、選択内容を確認します。 それぞれのセクションの [ **戻る** ] ボタンまたは **[編集]** リンクをクリックして変更を加えることができます。

   完了したら、**[送信]** をクリックします。

### <a name="managed-existing-scheduled-reports"></a>既存のスケジュールされたレポートを管理する

既に作成したスケジュールされたレポートを管理するには、次の手順に従います。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**レポート**\>] に移動し、[**電子メール &コラボレーション**\>] の [**スケジュールの管理**] を選択します。

   **[スケジュールの管理**] ページに直接移動するには、 <https://security.microsoft.com/ManageSubscription>.

2. [ **スケジュールの管理** ] ページには、スケジュールされたレポートごとに次の情報が表示されます。
   - **スケジュールの開始日**
   - **スケジュール名**
   - **レポートの種類**
   - **Frequency**
   - **最後に送信された**

   変更する既存のスケジュールされたレポートを見つけます。

3. スケジュールされたレポートを選択した後、開いた詳細ポップアップで次のいずれかの操作を行います。
   - **[名前の編集]:** このボタンをクリックし、表示されるポップアップ内のレポートの名前を変更して、[ **保存**] をクリックします。
   - **スケジュールの削除**: このボタンをクリックし、表示される警告を読み取り (以前のレポートはダウンロードできなくなります)、[ **保存**] をクリックします。
   - **[スケジュールの詳細** ] セクション: [ **設定の編集]** をクリックして、次の設定を変更します。
     - **頻度**: **毎週** または **毎月**
     - **開始日**
     - **有効 期限**

     完了したら、**[保存]** をクリックします。

   - **[受信者]** セクション: [ **受信者の編集]** をクリックして、スケジュールされたレポートの受信者を追加または削除します。 完了したら、[保存] をクリック **します**。

   完了したら、**[閉じる]** をクリックします。

## <a name="request-report"></a>レポートを要求する

1. 特定のレポートのメイン ページで、[レポートの要求] アイコンをクリックします ![。](../../media/m365-cc-sc-download-icon.png) **要求レポート**。
2. **オンデマンド レポートの作成** ウィザードが開きます。 [ **名前のオンデマンド レポート] ページで** 、[ **名前]** の値を確認またはカスタマイズし、[ **次へ**] をクリックします。
3. [ **基本設定の設定** ] ページで、次の設定を確認または構成します。
   - **開始日**: レポートの生成が開始されたとき。 既定値は 1 か月前です。
   - **有効期限**: レポートの生成が終了したとき。 既定値は現在です。

   完了したら、**[次へ]** をクリックします。

4. [ **受信者] ページで** 、レポートの受信者を選択します。 既定値はメール アドレスですが、他のユーザーを追加できます。

   完了したら、**[次へ]** をクリックします。

5. [ **校閲** ] ページで、選択内容を確認します。 それぞれのセクションの [ **戻る** ] ボタンまたは **[編集]** リンクをクリックして変更を加えることができます。

   完了したら、**[送信]** をクリックします。

6. レポートが正常に作成されると、[ **新しいオンデマンド レポートの作成** ] ページが表示され、[ **別のレポートの作成** ] または **[完了]** をクリックできます。

   レポートは、次のセクションで説明するように、[ **ダウンロード用のレポート]** ページでも使用できます。

### <a name="download-reports"></a>レポートのダウンロード

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**レポート**\>] に移動し、[**電子メール&コラボレーション**\>] を展開し、[**ダウンロード用のレポート]** を選択します。

   **[レポートのダウンロード**] ページに直接移動するには、次を使用します<https://security.microsoft.com/ReportsForDownload>。

2. **[ダウンロード用のレポート]** ページに、使用可能なレポートごとに次の情報が表示されます。
   - **開始日**
   - **Name**
   - **レポートの種類**
   - **最後に送信された**
   - **方向**

   ダウンロードするレポートを見つけて選択します。

## <a name="export-report"></a>レポートをエクスポートする

特定のレポートのメイン ページで、[エクスポート] アイコンをクリックします ![。](../../media/m365-cc-sc-download-icon.png) **エクスポート** (そのリンクが使用可能な場合)。 **次の設定を構成できるエクスポート条件** ポップアップが表示されます。

- **エクスポートするビューを選択** する: 次のいずれかの値を選択します。
  - **概要**: データは過去 90 日間使用できます。
  - **詳細**: データは過去 30 日間利用できます。
- **日付 (UTC)**: **開始日** と **終了日**。

フィルターの構成が完了したら、[ **エクスポート**] をクリックします。 開いたダイアログで、ファイルを開くか、ファイルを保存するか、選択内容を記憶するかを選択できます。

エクスポートされた.csv ファイルは、それぞれ 150,000 行に制限されています。 データに 150,000 行を超える行が含まれている場合は、複数の.csv ファイルが作成されます。

## <a name="related-topics"></a>関連項目

[EOP のスパム対策保護](anti-spam-protection.md)

[EOP のマルウェア対策保護](anti-malware-protection.md)

[Microsoft 365 Defender ポータルでのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[Microsoft 365 Defender ポータルでメール フロー レポートを表示する](view-mail-flow-reports.md)

[Defender for Office 365のレポートを表示する](view-reports-for-mdo.md)
