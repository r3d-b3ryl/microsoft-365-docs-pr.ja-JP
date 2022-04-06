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
description: 管理者は、ポータルで使用できる電子メール セキュリティ レポートを検索して使用する方法Microsoft 365 Defenderできます。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b6d085d2e3c1e9c1e032f468f56d67a393269fe1
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683057"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a>ポータルで電子メール セキュリティ レポートをMicrosoft 365 Defenderする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender ポータルでは、Microsoft 365 <https://security.microsoft.com> のスパム対策機能やマルウェア対策機能などの電子メール セキュリティ機能が組織を保護している方法を確認できます。 必要なアクセス許可 [がある場合は](#what-permissions-are-needed-to-view-these-reports)、この記事の説明に従って、これらのレポートを表示してダウンロードできます。

> [!NOTE]
>
> [電子メール] コラボレーション レポート ページの一 **部のレポート& Microsoft** Defender が必要です。Office 365。 これらのレポートの詳細については、「[View Defender for Office 365ポータル」をMicrosoft 365 Defenderしてください](view-reports-for-mdo.md)。
>
> メール フローに関連するレポートが管理センター Exchangeされます。 これらのレポートの詳細については、「新しい管理センターのメール フロー [レポートExchange参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。

## <a name="email-security-report-changes-in-the-microsoft-365-defender-portal"></a>電子メール セキュリティ レポートの変更点 (Microsoft 365 Defender ポータル)

置換Exchange Online Protection、移動、または廃止された Microsoft 365 Defender ポータルの Office 365 レポートのレポート (EOP) と Microsoft Defender について、次の表で説明します。

|非推奨のレポートとコマンドレット|新しいレポートとコマンドレット|メッセージ センター ID|日付|
|---|---|:---:|:---:|
|**URL 追跡** <p> Get-URLTrace|[URL 保護レポート](view-reports-for-mdo.md#url-protection-report) <p> [Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <br> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|MC239999|2021 年 6 月|
|**送信および受信した電子メール レポート** <p> Get-MailTrafficReport <br> Get-MailDetailReport|[脅威保護の状態レポート](#threat-protection-status-report) <br> [メールフローの状態レポート](#mailflow-status-report) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <br> [Get-MailFlowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|MC236025|2021 年 6 月|
|**転送レポート** <p> コマンドレットなし|[EAC の自動転送メッセージ レポート](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report) <p> コマンドレットなし|MC250533|2021 年 6 月|
|**セーフ添付ファイルの種類レポート** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[脅威保護の状態レポート: メール マルウェアによるデータの表示\>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250532|2021 年 6 月|
|**セーフ添付ファイル メッセージ廃棄レポート** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[脅威保護の状態レポート: メール マルウェアによるデータの表示\>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250531|2021 年 6 月|
|**電子メール レポートで検出されたマルウェア** <p> Get-MailTrafficReport <br> Get-MailDetailMalwareReport|[脅威保護の状態レポート: メール マルウェアによるデータの表示\>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250530|2021 年 6 月|
|**スパム検出レポート** <p> Get-MailTrafficReport <br> Get-MailDetailSpamReport|[脅威保護の状態レポート: メール スパムによるデータの \> 表示](#view-data-by-email--spam-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250529|2021 年 10 月|
|Get-AdvancedThreatProtectionDocumentReport <p> Get-AdvancedThreatProtectionDocumentDetail|[Get-ContentMalwareMdoAggregateReport](/powershell/module/exchange/get-contentmalwaremdoaggregatereport) <p> [Get-ContentMalwareMdoDetailReport](/powershell/module/exchange/get-contentmalwaremdodetailreport)|TBA|2022 年 5 月|
|**Exchangeルール レポート** <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|[Exchange EAC でトランスポート ルール レポートを作成する](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report) <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|MC316157|2022 年 4 月|
|Get-MailTrafficTopReport|[脅威保護の状態レポート: メール マルウェアによるデータの表示\>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <p> **注**: Get-MailTrafficTopReport の暗号化レポート機能に代わりはありません。|MC315742|2022 年 4 月|

## <a name="compromised-users-report"></a>侵害されたユーザー レポート

> [!NOTE]
> このレポートは、メールボックスを使用Microsoft 365組織Exchange Online使用できます。 スタンドアロン 組織 (EOP) ではExchange Online Protection使用できません。

[**侵害されたユーザー]** レポートには、過去 7 日間に [疑わしい] または  [制限付き] とマークされたユーザー アカウントの数が表示されます。 これらの状態のどちらかのアカウントは、問題が発生したり、侵害された場合もあります。 頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントのスパイクや傾向を見つけるのに使用できます。 侵害されたユーザーの詳細については、「侵害されたメール アカウントへの [応答」を参照してください](responding-to-a-compromised-email-account.md)。

![[電子メール] ページの [グループ&侵害されたユーザー] ウィジェット。](../../media/compromised-users-report-widget.png)

集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。

[レポート] ポータルでレポートMicrosoft 365 Defenderするには<https://security.microsoft.com>\>、[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [メール **] グループ&] ページで**、[侵害されたユーザー] を探し、[詳細の表示] **をクリックします**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/CompromisedUsers>。

[侵害された **ユーザー] ページ** で、指定した日付範囲の次の情報がグラフに表示されます。

- **制限**: ユーザー アカウントは、疑わしいパターンが多く、電子メールの送信が制限されています。
- **疑** わしい: ユーザー アカウントから不審なメールが送信され、電子メールの送信が制限される危険性があります。

グラフの下の詳細テーブルは、次の情報を示しています。

- **作成時間**
- **[ユーザー ID]**
- **操作**
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **日付 (UTC)**: **開始日と****終了日**。
- **アクティビティ**: **制限付き****または疑わしい**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[侵害された **ユーザー] ページ** で、[スケジュールの作成 ![] アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

![[侵害されたユーザー] レポートのレポート ビュー。](../../media/compromised-users-report-activity-view.png)

## <a name="exchange-transport-rule-report"></a>Exchangeルール レポート

> [!NOTE]
> EAC **Exchangeトランスポート ルール レポート** を使用できます。 詳細については、「新しい [EAC Exchangeトランスポート ルール レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report)。

### <a name="chart-breakdown-by-direction"></a>[方向] によるグラフの内訳

![トランスポート ルール レポートExchangeトランスポート ルールのExchange表示します。](../../media/transport-rule-report-etr-direction-view.png)

[方向によるグラフ **の内訳] を選択すると**、次のグラフを使用できます。

- **トランスポート ルール別Exchange表示** する: メール フロー ルールの影響を受けた受信メッセージと送信メッセージの数。
- **データを DLP Exchangeトランスポート** ルールで表示する: データ損失防止 (DLP) メール  フロー ルールの影響を受けた受信メッセージと送信メッセージの数。

次の情報は、グラフの下の詳細テーブルに示されています。

- **Date**
- **DLP ポリシー** (**DLP によるデータの表示Exchangeトランスポート ルールのみ**)
- **トランスポート ルール**
- **件名**
- **[送信者のアドレス]**
- **受信者の住所**
- **重大度**
- **方向**

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **日付 (UTC)** **開始日と****終了日**。
- **方向**: **送信と****受信**。
- **重大度:** **高重大度、** 中程度 **の重大度**、 **および低重大度**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[トランスポート **Exchangeレポート] ページで、[** スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="chart-breakdown-by-severity"></a>重大度別のグラフの内訳

![トランスポート ルール レポートExchangeトランスポート ルールのExchange表示されます。](../../media/transport-rule-report-etr-severity-view.png)

[重大度別の **グラフの内訳] を選択した** 場合は、次のグラフを使用できます。

- **トランスポート ルール別Exchange表示**: 重大度の高いメッセージ、中程度の重大度、および低重大度メッセージ **の** 数。 ルールのアクションとして重大度レベルを設定 **します (重大度** レベルまたは _SetAuditSeverity でこのルールを監査します_)。 詳細については、「メール フロー ルール[のアクション」を参照Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。

- **DLP メール フロー ルールExchange** でデータを表示する: DLP メール フロー ルールの影響を受けた重大度の高いメッセージ、中程度の重大度、および低重大度メッセージの数。

次の情報は、グラフの下の詳細テーブルに示されています。

- **Date**
- **DLP ポリシー** (**DLP によるデータの表示Exchangeトランスポート ルールのみ**)
- **トランスポート ルール**
- **件名**
- **[送信者のアドレス]**
- **受信者の住所**
- **重大度**
- **方向**

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **日付 (UTC)** **開始日と****終了日**
- **方向**: **送信と****受信**
- **重大度:** **高重大度、** 中程度 **の重大度**、 **および低重大度**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[トランスポート **Exchangeレポート] ページで、[** スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

## <a name="forwarding-report"></a>転送レポート

> [!NOTE]
> このレポートは EAC で利用できます。 詳細については、「新しい [EAC の自動転送メッセージ レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。

## <a name="mailflow-status-report"></a>メールフローの状態レポート

**Mailflow 状態** レポートは、受信および送信メール、スパム検出、マルウェア、"良い" と識別される電子メール、およびエッジで許可またはブロックされた電子メールに関する情報を示すスマート レポートです。 これは、エッジ保護情報を含む唯一のレポートであり、EOP (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量Exchange Online Protection示しています。 メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。

[レポート] ポータルでレポートMicrosoft 365 Defenderするには<https://security.microsoft.com>\>、[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [メール **の共有&] ページで** 、[ **メールフローの** 状態の概要] を探し、[詳細の表示] **をクリックします**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/mailflowStatusReport>。

![[メール] グループ作業レポート ページの [メールフロー&概要] ウィジェット。](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>メールフロー状態レポートの種類ビュー

![[メールフローの状態] レポートにビューを入力します。](../../media/mail-flow-status-report-type-view.png)

[メール **フローの状態] レポート ページで** 、[ **種類] タブ** が既定で選択されています。 グラフには、指定した日付範囲に関する次の情報が表示されます。

- **良いメール**: スパムではないと判断されたメール、またはユーザーまたは組織のポリシーによって許可されるメール。
- **合計**
- **マルウェア**: さまざまなフィルターによってマルウェアとしてブロックされたメール。
- **フィッシングメール**: さまざまなフィルターによってフィッシングとしてブロックされているメール。
- **スパム**: さまざまなフィルターによってスパムとしてブロックされているメール。
- **エッジ保護**: EOP または Defender によって評価される前に、エッジ/境界で拒否された電子メールOffice 365。
- **ルール メッセージ**: メール フロー ルール (トランスポート ルールとも呼ばれる) によって処理された電子メール メッセージ。

グラフの下の詳細テーブルは、次の情報を示しています。

- **方向**
- **Type**
- **24 時間**
- **3 日間**
- **7 日間**
- **15 日**
- **30 日間**

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **日付 (UTC)**: **開始日と****終了日**。
- **メールの方向**: **受信と****送信**。
- **タイプ**:
  - **良いメール**
  - **マルウェア**
  - **スパム**
  - **エッジ保護**
  - **ルール メッセージ**
  - **フィッシング詐欺メール**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[メールフローの **状態レポート] ページに戻** り、[詳細についてはカテゴリを選択する] をクリックすると、次の値から選択できます。

- **フィッシングメール**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。
- **電子メール内のマルウェア**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。
- **スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。
- **エッジブロックスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。

[ **メールフロー状態レポート] ページの** [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールとエクスポート](#schedule-report)** アイコン ![を作成します。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="direction-view-for-the-mailflow-status-report"></a>メールフロー状態レポートの方向ビュー

![メールフロー状態レポートの方向ビュー。](../../media/mail-flow-status-report-direction-view.png)

[方向] タブ **をクリック** すると、指定した日付範囲の次の情報がグラフに表示されます。

- **受信**
- **送信**

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **日付 (UTC)**: **開始日と****終了日**。
- **メールの方向**: **受信と****送信**。
- **タイプ**:
  - **良いメール**
  - **マルウェア**
  - **スパム**
  - **エッジ保護**
  - **ルール メッセージ**
  - **フィッシング詐欺メール**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[メールフローの **状態レポート] ページに戻** り、[詳細についてはカテゴリを選択する] をクリックすると、次の値から選択できます。

- **フィッシングメール**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。
- **電子メール内のマルウェア**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。
- **スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。
- **エッジブロックスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。

[ **メールフロー状態レポート] ページの** [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **スケジュールとエクスポート** アイコン ![を作成します。](../../media/m365-cc-sc-download-icon.png) **エクスポート** ボタンを使用できます。

### <a name="mailflow-view-for-the-mailflow-status-report"></a>メールフロー状態レポートのメールフロー ビュー

[ **メールフロー] ビュー** には、Microsoft の電子メール脅威保護機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。 このビューでは、水平方向のフロー図 ( _サン_ キー図と呼ばれる) を使用して、メールの総数の詳細と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策などの構成済みの脅威保護機能が、この数にどのような影響を与えるのかについて説明します。

![メールフロー状態レポートのメールフロー ビュー。](../../media/mail-flow-status-report-mailflow-view.png)

集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。

図の情報は、**EOP** または **Defender** によって色分けされた、Office 365されています。

図は、次の水平バンドに編成されています。

- **合計メール バンド** : この値は常に最初に表示されます。
- **エッジ ブロックと****処理されたバンド**:
  - **エッジ ブロック**: エッジでフィルター処理され、エッジ保護として識別されるメッセージ。
  - **処理:** フィルター スタックによって処理されるメッセージ。
- 結果バンド:
  - **ルール ブロック**: メール フロー ルール (トランスポート ルールExchangeによって処理されるメッセージ。
  - **マルウェア ブロック**: さまざまなフィルターによってマルウェアとして識別されるメッセージ。<sup>\*</sup>
  - **フィッシング ブロック**: さまざまなフィルターによる処理中にフィッシングとして識別されるメッセージ。<sup>\*</sup>
  - **スパム ブロック**: さまざまなフィルターによる処理中にスパムとして識別されるメッセージ。<sup>\*</sup>
  - **偽装ブロック**: Defender でユーザー偽装またはドメイン偽装として検出されたメッセージがOffice 365。<sup>\*</sup>
  - **[削除] ブロック**: セーフ 添付ファイル ポリシーまたは セーフ リンク ポリシーによってファイルまたは URL の削除中に検出されたメッセージ 。Office 365。<sup>\*</sup>
  - **ZAP が削除** されました: ゼロ時間自動削除 (ZAP) によって削除されるメッセージ。<sup>\*</sup>
  - **配信**: 許可が原因でユーザーに配信されるメッセージ。<sup>\*</sup>

図の水平方向のバンドにカーソルを合わせると、関連するメッセージの数が表示されます。

<sup>\*</sup> この要素をクリックすると、図が展開され、詳細が表示されます。 展開されたノード内の各要素の説明については、「検出テクノロジ」 [を参照してください](/office/office-365-management-api/office-365-management-activity-api-schema#detection-technologies)。

![メールフロー状態レポートの Mailflow ビューのフィッシング ブロックの詳細。](../../media/mail-flow-status-report-mailflow-view-details.png)

図の下の詳細テーブルは、次の情報を示しています。

- **Date**
- **メールの総数**
- **フィルター処理されたエッジ**
- **ルール メッセージ**
- **マルウェア対策エンジン、セーフ添付ファイル、フィルター処理されたルール**
- **DMARC 偽装、スプーフィング、フィッシング フィルター**
- **Detonation 検出**
- **フィルター処理されたスパム対策**
- **ZAP が削除されました**
- **脅威が検出されていないメッセージ**

詳細テーブルで行を選択すると、メール数の詳細が表示される詳細フライアウトに表示されます。

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **日付 (UTC)** **開始日と****終了日**。
- **方向**: **送信と****受信**。

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[メールフローの **状態レポート] ページに戻** って、[傾向の表示] をクリックすると、表示される **メール** フローの傾向のフライアウトに傾向グラフを表示できます。

![Mailflow 状態レポートの Mailflow ビューのメールフローの傾向フライアウト。](../../media/mail-flow-status-report-mailflow-view-show-trends.png)

[ **メールフローの状態レポート] ページで** 、[エクスポート] ![アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート** ] ボタンを使用できます。

## <a name="malware-detections-report"></a>マルウェア検出レポート

> [!NOTE]
> このレポートは廃止されました。 脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。

## <a name="mail-latency-report"></a>メール遅延レポート

Defender **for Office 365** のメール待機時間レポートには、組織内で発生したメール配信とデトレーションの待機時間に関する情報が含まれている。 詳細については、「メール遅延 [レポート」を参照してください](view-reports-for-mdo.md#mail-latency-report)。

## <a name="spam-detections-report"></a>スパム検出レポート

> [!NOTE]
> このレポートは廃止されました。 脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。

## <a name="spoof-detections-report"></a>スプーフィング検出レポート

ス **プーフィング検出レポート** には、スプーフィングによってブロックまたは許可されたメッセージに関する情報が表示されます。 スプーフィングの詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。

レポートの集計ビューでは 90 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター処理のみ可能です。

ポータルでレポートを表示するには \> Microsoft 365 Defender[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [メール **の送信&] ページで** 、[スプーフィングの検出] **を探** し、[詳細の表示] **をクリックします**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpoofMailReport>。

![[メール] グループ&スプーフィング検出ウィジェット。](../../media/spoof-detections-widget.png)

グラフには、次の情報が表示されます。

- **Pass**
- **Fail/失敗**
- **SoftPass**
- **なし**
- **その他**

グラフの 1 日 (データ ポイント) にカーソルを合わせると、スプーフィングされたメッセージの検出数と理由を確認できます。

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **日付 (UTC)** **開始日と****終了日**
- **結果**:
  - **Pass**
  - **Fail/失敗**
  - **SoftPass**
  - **なし**
  - **その他**
- **スプーフィングの****種類: 内部と****外部**

![[メール レポートのスプーフィング] ページ (Microsoft 365 Defenderポータル)。](../../media/spoof-detections-report-page.png)

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

複合認証結果コードの詳細については、「スパム対策メッセージ ヘッダー」を参照[Microsoft 365。](anti-spam-message-headers.md)

[スプー **フィングの検出] ページ** で、[スケジュールの作成 ![] アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

## <a name="submissions-report"></a>申請レポート

申請 **レポートには** 、管理者が分析のために Microsoft に報告したアイテムに関する情報が表示されます。 詳細については、「管理申請 [を使用して疑わしい](admin-submission.md)スパム、フィッシング、URL、ファイルを Microsoft に提出する」を参照してください。

[レポート] ポータルでレポートMicrosoft 365 Defenderするには<https://security.microsoft.com>\>、[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [コラボレーション **レポートのメール&] ページで** 、[申請] を探 **し** 、[詳細の表示] **をクリックします**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/adminSubmissionReport>。 ポータルで [管理者の申請に移動するにはMicrosoft 365 Defender送信](admin-submission.md)に移動 **] をクリックします**。 管理者は過去 30 日間レポートを表示できます。

![[電子メール] ページの [&] ウィジェット。](../../media/submissions-report-widget.png)

グラフには、次の情報が表示されます。

- **Pending**
- **Completed**

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **報告日**: **開始時刻** と **終了時刻**
- **申請の種類**:
  - **電子メール**
  - **URL**
  - **ファイル**
- **申請 ID**
- **ネットワーク メッセージ ID**
- **Sender**
- **名前**
- **提出者**
- **提出の理由**:
  - **迷惑メールではない**
  - **フィッシング**
  - **マルウェア**
  - **スパム**
- **再スキャンの状態**:
  - **Pending**
  - **Completed**

グラフの下の詳細テーブルは、同じ情報を示し、グループまたはカスタマイズの列のオプションは、[電子メール と共同作業の申請] の [分析用に送信済み] タブと同&**します** \> **。** 詳細については、「 [View admin submissions to Microsoft」を参照してください](admin-submission.md#view-admin-submissions-to-microsoft)。

[申請 **] ページで** 、[エクスポート] **[ボタン](#export-report)** を使用できます。

![ポータルの申請レポート ページMicrosoft 365 Defenderします。](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

脅威 **保護の状態** レポートは、EOP と Defender の両方Office 365使用できます。ただし、レポートには異なるデータが含まれる場合があります。 たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルに関する情報[は表示できません](mdo-for-spo-odb-and-teams.md)。

このレポートでは、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス [(URL](zero-hour-auto-purge.md))、[セーフ Links](safe-links.md)、[セーフ 添付](safe-attachments.md)ファイル、フィッシング対策ポリシーの偽装保護機能などの Office 365 機能に対する Defender などの悪意のあるコンテンツを含む電子メール メッセージの数を示します。[](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) この情報を使用して、傾向を特定したり、組織のポリシーで調整が必要かどうかを判断できます。

**注**: メッセージが 5 人の受信者に送信される場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。

ポータルでレポートを表示するには \> Microsoft 365 Defender[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [メール **の送信&] ページで** 、[脅威保護の状態] **を** 探し、[詳細の表示] **をクリックします**。 レポートに直接移動するには、次のいずれかの URL を開きます。

- Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP>
- EOP: <https://security.microsoft.com/reports/TPSAggregateReport>

![[メール] ページの [脅威&状態] ウィジェット。](../../media/threat-protection-status-report-widget.png)

既定では、グラフには過去 7 日間のデータが表示されます。 [脅威保護状態 **レポート]** **ページで** [フィルター] をクリックすると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。 詳細テーブルでは、30 日間のフィルター処理が可能です。

使用可能なビューについては、次のセクションで説明します。

### <a name="view-data-by-overview"></a>概要でデータを表示する

![脅威保護状態レポートの概要ビュー。](../../media/threat-protection-status-report-overview-view.png)

[概要で **データを表示]** ビューでは、次の検出情報がグラフに表示されます。

- **電子メール マルウェア**
- **メールフィッシング**
- **メールスパム**
- **コンテンツ マルウェア**

グラフの下に詳細テーブルはありません。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**。
- **検出**:
  - **電子メール マルウェア**
  - **メールフィッシング**
  - **メールスパム**
  - **コンテンツ マルウェア**
- **保護:** **MDO** (Defender for Office 365) **と EOP**。
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。 ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a>検出テクノロジによってメールフィッシングと \> グラフの内訳でデータを表示する

![脅威保護状態レポートのフィッシングメールの検出テクノロジ ビュー。](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

> [!NOTE]
> 2021 年 5 月から、メールのフィッシング検出が更新され、フィッシング URL を含むメッセージ添付ファイルが含まれています。 この変更により、検出ボリュームの **\>** 一部が [メール マルウェアによるデータの表示] ビューから [メールフィッシングによるデータの表示] ビュー **に移動する\>場合** があります。 つまり、従来はマルウェアとして識別されたフィッシング URL を含むメッセージ添付ファイルが、フィッシング詐欺として識別される可能性があります。

[ **メール フィッシングによるデータの表示 \> ] ビューと** **[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。

- **URL 悪意のある評判**<sup>\*</sup>: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザーのMicrosoft 365です。
- **高度なフィルター**: 機械学習に基づくフィッシングシグナル。
- **一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。
- **組織内のスプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしている。
- **外部ドメインのスプーフィング**: 送信者が他のドメインをスプーフィングしようとしている。
- **スプーフィング DMARC**: メッセージの DMARC 認証エラー。
- **偽装ブランド**: 送信者に基づく既知のブランドの偽装。
- **複合分析の検出**
- **ファイルの評価**
- **指紋の一致**
- **URL のデトレーション評価**<sup>\*</sup>
- **URL のデトナレーション**<sup>\*</sup>
- **偽装ユーザー**<sup>\*</sup>
- **偽装ドメイン**<sup>\*</sup>: 顧客が所有または定義するドメインの偽装。
- **メールボックス インテリジェンスの偽装**<sup>\*</sup>: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスによって学習されたユーザーの偽装。
- **ファイルのデトレーション**<sup>\*</sup>
- **ファイルのデトレーション評価**<sup>\*</sup>
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
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **検出**: グラフと同じ値。
- **保護:** **MDO** (Defender for Office 365) **または EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ):****すべてまたは** 指定したポリシー。
- **受信者**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[脅威保護 **の状態] ページ** で、[スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-email--spam-and-chart-breakdown-by-detection-technology"></a>検出テクノロジによってメール スパムと \> グラフの内訳でデータを表示する

![脅威保護状態レポートのスパムの検出テクノロジ ビュー。](../../media/threat-protection-status-report-spam-detection-tech-view.png)

[電子メール **スパムによるデータの\>****表示] ビュー** と [検出テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。

- **URL に悪意があるとする評価**
- **高度なフィルター**
- **一般的なフィルター**
- **混合分析の検出**: 複数のフィルターがメッセージの評決に貢献しました。
- **指紋照合**: 以前のメッセージが原因で、メッセージが不良としてマークされています。
- **ドメイン評価**: このメッセージは、送信者ドメイン評価に基づいてスパムと見なされます。
- **バルク**: ユーザーの一括設定を超えたと検出されたアイテム。
- **IP レピュ** テーション: メッセージは、送信 IP アドレス評価に基づいてスパムと見なされます。

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **検出**: グラフと同じ値。
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ):****すべてまたは** 指定したポリシー。
- **受信者**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[脅威保護 **の状態] ページ** で、[スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a>検出テクノロジによってメール マルウェアと \> グラフの内訳でデータを表示する

![脅威保護状態レポートのマルウェアの検出テクノロジ ビュー。](../../media/threat-protection-status-report-malware-detection-tech-view.png)

> [!NOTE]
> 2021 年 5 月から、メール内のマルウェア検出が更新され、有害 **な URL** がメッセージ添付ファイルに含まれる。 この変更により、検出ボリュームの **\>** 一部が [メールフィッシングによるデータの表示] ビューから [メール マルウェアによるデータの表示] ビュー **に移動する\>場合** があります。 つまり、従来はフィッシングとして識別されたメッセージ添付ファイル内の有害な URL が、マルウェアとして識別される可能性があります。

[電子メール **マルウェアによるデータの\>** 表示 **] ビューと** [検出テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。

- **ファイルの削除**<sup>\*</sup>: 添付ファイルセーフ検出。
- **ファイルの削除評価**<sup>\*</sup>: すべての悪意のあるファイルレピュテーションは、Defender によって生成され、Office 365されます。
- **ファイルの評価**
- **マルウェア対策エンジン:**<sup>\*</sup> マルウェア対策エンジンからの検出。
- **マルウェア対策ポリシー ファイルの種類** ブロック: これらは、メッセージで識別された悪意のあるファイルの種類が原因でフィルター処理された電子メール メッセージです。
- **URL 悪意のある評判**<sup>\*</sup>
- **URL のデトナレーション**<sup>\*</sup>
- **URL のデトレーション評価**<sup>\*</sup>
- **キャンペーン**<sup>\*</sup>

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **検出**: グラフと同じ値。
- **保護:** **MDO** (Defender for Office 365) **または EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ):****すべてまたは** 指定したポリシー。
- **受信者**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[**Threat 保護の状態] ページで** 、[スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="chart-breakdown-by-policy-type"></a>ポリシーの種類別のグラフの内訳

![脅威保護状態レポートのフィッシングメール、スパムメール、マルウェアメールのポリシーの種類の表示。](../../media/threat-protection-status-report-phishing-policy-type-view.png)

[**メール フィッシング\>****\>****\>** によるデータの表示]、[メール スパムによるデータの表示]、または [メール マルウェアによるデータの表示] ビューで、[ポリシーの種類別のグラフの内訳] を選択すると、グラフに次の情報が表示されます。

- **マルウェア対策**
- **セーフ添付ファイル**<sup>\*</sup>
- **フィッシング対策**
- **スパム対策**
- **メール フロー ルール** (トランスポート ルールとも呼ばれる)
- **Others**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **検出**:
  - **URL 悪意のある評判**<sup>\*</sup>: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザーのMicrosoft 365です。
  - **高度なフィルター**: 機械学習に基づくフィッシングシグナル。
  - **一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。
  - **組織内のスプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしている。
  - **外部ドメインのスプーフィング**: 送信者が他のドメインをスプーフィングしようとしている。
  - **スプーフィング DMARC**: メッセージの DMARC 認証エラー。
  - **偽装ブランド**: 送信者に基づく既知のブランドの偽装。
  - **複合分析の検出**
  - **ファイルの評価**
  - **指紋の一致**
  - **URL のデトレーション評価**<sup>\*</sup>
  - **URL のデトナレーション**<sup>\*</sup>
  - **偽装ユーザー**<sup>\*</sup>
  - **偽装ドメイン**<sup>\*</sup>: 顧客が所有または定義するドメインの偽装。
  - **メールボックス インテリジェンスの偽装**<sup>\*</sup>: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスによって学習されたユーザーの偽装。
  - **ファイルのデトレーション**<sup>\*</sup>
  - **ファイルのデトレーション評価**<sup>\*</sup>
  - **キャンペーン**<sup>\*</sup>
- **保護:** **MDO** (Defender for Office 365) **または EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ):****すべてまたは** 指定したポリシー。
- **受信者**

<sup>\*</sup>Defender for Office 365のみ

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[脅威保護 **の状態] ページ** で、[スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="chart-breakdown-by-delivery-status"></a>配信状態別のグラフの内訳

![脅威保護状態レポートのフィッシングメールとマルウェアメールの配信状態ビュー。](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

[**メール フィッシング\>****\>****\>** によるデータの表示]、[メール スパムによるデータの表示]、または [メール マルウェアによるデータの表示] ビューで、[配信状態別のグラフの内訳] を選択すると、グラフに次の情報が表示されます。

- **ホストされたメールボックス: 受信トレイ**
- **ホストされたメールボックス: 迷惑メール**
- **ホストされたメールボックス: カスタム フォルダー**
- **ホストされたメールボックス: 削除済みアイテム**
- **Forwarded**
- **オンプレミス サーバー: 配信**
- **検疫**
- **配信に失敗しました**
- **ドロップ**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **検出テクノロジ**
- **配信状態**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **検出**:
  - **URL 悪意のある評判**<sup>\*</sup>: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザーのMicrosoft 365です。
  - **高度なフィルター**: 機械学習に基づくフィッシングシグナル。
  - **一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。
  - **組織内のスプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしている。
  - **外部ドメインのスプーフィング**: 送信者が他のドメインをスプーフィングしようとしている。
  - **スプーフィング DMARC**: メッセージの DMARC 認証エラー。
  - **偽装ブランド**: 送信者に基づく既知のブランドの偽装。
  - **複合分析の検出**
  - **ファイルの評価**
  - **指紋の一致**
  - **URL のデトレーション評価**<sup>\*</sup>
  - **URL のデトナレーション**<sup>\*</sup>
  - **偽装ユーザー**<sup>\*</sup>
  - **偽装ドメイン**<sup>\*</sup>: 顧客が所有または定義するドメインの偽装。
  - **メールボックス インテリジェンスの偽装**<sup>\*</sup>: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスによって学習されたユーザーの偽装。
  - **ファイルのデトレーション**<sup>\*</sup>
  - **ファイルのデトレーション評価**<sup>\*</sup>
  - **キャンペーン**<sup>\*</sup>
- **保護:** **MDO** (Defender for Office 365) **または EOP**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **添付ファイル保護**
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ):****すべてまたは** 指定したポリシー。
- **受信者**

<sup>\*</sup>Defender for Office 365のみ

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[脅威保護 **の状態] ページ** で、[スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-content--malware"></a>コンテンツ マルウェアによるデータの \> 表示

![脅威保護状態レポートのコンテンツ マルウェア ビュー。](../../media/threat-protection-status-report-content-malware-view.png)

[コンテンツ **マルウェアによるデータの\>** 表示] ビューでは、組織の Microsoft Defender のグラフに次のOffice 365されます。

- **マルウェア対策エンジン**: SharePoint、OneDrive、Microsoft Teams で組み込みのウイルス検出によって検出された悪意のある [Microsoft 365](virus-detection-in-spo.md)。
- **MDO の削除**: 添付ファイルによって検出された悪意のあるファイルセーフ [、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)Microsoft Teams。
- **ファイルの評価**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **日付 (UTC)**
- **添付ファイルの名前**
- **ワークロード**
- **検出テクノロジ**
- **ファイル サイズ**
- **最後に変更したユーザー**

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **検出**: **マルウェア対策エンジン、****MDO のデトレーション**、**およびファイルのデトレーション**
- **ワークロード**: **Teams**、**SharePoint****、および** OneDrive

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[脅威保護 **の状態] ページ** で、[スケジュールの作成] ![アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

### <a name="view-data-by-system-override-and-chart-breakdown-by-reason"></a>システムオーバーライドと理由によるグラフの内訳でデータを表示する

![脅威保護状態レポートの [理由] ビューによるメッセージの上書きとグラフの内訳。](../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png)

[システムオーバーライド **によるデータの表示]** **ビューと** [理由別グラフの内訳] ビューでは、次のオーバーライド理由情報がグラフに表示されます。

- **オンプレミスのスキップ**
- **IP 許可**
- **Exchange トランスポート ルール** (メール フロー ルール)
- **組織で許可されている送信者**
- **組織で許可されているドメイン**
- **ZAP が有効になっていません**
- **ユーザー セーフ送信者**
- **ユーザー セーフ ドメイン**
- **フィッシング シミュレーション**: 詳細については、「ユーザーへのサード パーティフィッシング シミュレーションの配信の構成」および「SecOps メールボックスへのフィルター処理されていないメッセージの [構成」を参照してください](configure-advanced-delivery.md)。
- **サード パーティ製フィルター**

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **システムオーバーライド**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **理由**: グラフと同じ値。
- **配信場所**: **迷惑メール フォルダーが有効になっていないか****、または SecOps メールボックス。**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**: **すべて**
- **ポリシー名 (詳細テーブル ビューのみ)**: **All**
- **受信者**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[脅威保護 **の状態] ページ** で、[エクスポート] ![アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート](#export-report)** ] ボタンを使用できます。

### <a name="view-data-by-system-override-and-chart-breakdown-by-delivery-location"></a>配信場所別にシステムオーバーライドとグラフの内訳でデータを表示する

![脅威保護状態レポートの [メッセージの上書き] および [配信場所別グラフの内訳] ビュー。](../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png)

[システムの **上書きによるデータ** の表示 **] ビューと** [配信場所別のグラフの内訳] ビューでは、次のオーバーライド理由情報がグラフに表示されます。

- **迷惑メール フォルダーが有効になっていない**
- **SecOps メールボックス**: 詳細については、「ユーザーへのサード パーティフィッシング シミュレーションの配信の構成」および「SecOps メールボックスへのフィルター処理されていないメッセージの [構成」を参照してください](configure-advanced-delivery.md)。

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **Date**
- **件名**
- **送信者**
- **受信者**
- **システムオーバーライド**
- [**Sender IP (送信者の IP)**]
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

[フィルター] を **クリックすると**、次のフィルターを使用できます。

- **日付 (UTC)** **開始日と****終了日**
- **理由**
  - **オンプレミスのスキップ**
  - **IP 許可**
  - **Exchange トランスポート ルール** (メール フロー ルール)
  - **組織で許可されている送信者**
  - **組織で許可されているドメイン**
  - **ZAP が有効になっていません**
  - **ユーザー セーフ送信者**
  - **ユーザー セーフ ドメイン**
  - **フィッシング シミュレーション**: 詳細については、「ユーザーへのサード パーティフィッシング シミュレーションの配信の構成」および「SecOps メールボックスへのフィルター処理されていないメッセージの [構成」を参照してください](configure-advanced-delivery.md)。
  - **サード パーティ製フィルター**
- **配信場所**: **迷惑メール フォルダーが有効になっていないか****、または SecOps メールボックス。**
- **方向**:
  - **All**
  - **受信**
  - **送信**
- **タグ**: **All** または指定されたユーザー タグ (優先度アカウントを含む)。 ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。
- **ドメイン**: **すべて** または [受け入れ可能なドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **ポリシーの種類**:
  - **All**
  - **マルウェア対策**
  - **セーフ添付ファイル**<sup>\*</sup>
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルール)
  - **Others**
- **ポリシー名 (詳細テーブル ビューのみ)**: **All**
- **受信者**

<sup>\*</sup>Defender for Office 365のみ

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[脅威保護 **の状態] ページ** で、[エクスポート] ![アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート](#export-report)** ] ボタンを使用できます。

## <a name="top-malware-report"></a>トップ マルウェア レポート

[ **上位マルウェア]** レポートには、EOP のマルウェア対策保護によって検出されたさまざまな [種類のマルウェアが表示されます](anti-malware-protection.md)。

ポータルでレポートを表示するには \> Microsoft 365 Defender[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [メール **の作成と&] ページで** 、[トップ マルウェア] を探 **し** 、[詳細の表示] **をクリックします**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/TopMalware>。

![[メール] ページの [コラボレーション レポート] ページ&のトップ マルウェア ウィジェット。](../../media/top-malware-report-widget.png)

円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数を確認できます。

[上位 **マルウェア レポート] ページ** に、円グラフのより大きなバージョンが表示されます。 グラフの下の詳細テーブルは、次の情報を示しています。

- **トップ マルウェア**
- **Count**

[フィルター] **をクリック** すると、[開始日] と [終了日] で **日付範囲****を指定できます**。

[トップ **マルウェア] ページの** [スケジュールの作成 ![] アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールとエクスポート](#schedule-report)** アイコン ![を作成します。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](#export-report)** ボタンを使用できます。

![トップ マルウェア レポート ビュー。](../../media/top-malware-report-view.png)

## <a name="top-senders-and-recipients-report"></a>上位の送信者と受信者レポート

[**上位の送信者と** 受信者] レポートは、EOP と Defender の両方Office 365使用できます。ただし、レポートには異なるデータが含まれる場合があります。 [たとえば、EOP](safe-attachments.md) のお客様は、トップ マルウェア、スパム、フィッシング (スプーフィング) 受信者に関する情報を表示できますが、偽装保護によって検出された セーフ 添付ファイルやフィッシングによって検出されたマルウェアに[](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)関する情報は表示できません。

[**上位の送信者** と受信者] には、組織内の上位メッセージ送信者と、EOP および Defender によって検出されたメッセージの上位受信者が Office 365 保護機能で表示されます。 既定では、レポートには最後の 1 週間のデータが表示されますが、過去 90 日間はデータを使用できます。

[レポート] ポータルでレポートMicrosoft 365 Defenderするには<https://security.microsoft.com>\>、[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [メール **の送信&] ページ** で、[上位の送信者と受信者] レポートを検索し、[詳細の表示] **をクリックします**。 レポートに直接移動するには、次のいずれかの URL を開きます。

- Defender for Office 365:<https://security.microsoft.com/reports/TopSenderRecipientsATP>
- EOP: <https://security.microsoft.com/reports/TopSenderRecipient>

![レポート ダッシュボードの上位の送信者と受信者ウィジェット。](../../media/top-senders-and-recipients-widget.png)

円グラフのくさびの上にマウス ポインターを置くと、送信者または受信者のメッセージの数を確認できます。

[上位 **の送信者と受信者** ] ページに、より大きなバージョンの円グラフが表示されます。 次のグラフを使用できます。

- **上位メール送信者のデータを表示** する (これは既定のビューです)
- **上位メール受信者のデータを表示する**
- **上位のスパム受信者のデータを表示する**
- **上位マルウェア受信者 (** EOP) のデータを表示する
- **トップフィッシング受信者のデータを表示する**
- **上位マルウェア受信者のデータを表示する (MDO)**
- **上位のフィッシング受信者のデータを表示する (MDO)**

選択内容に基づいてデータが変更されます。

円グラフのくさびの上にマウス ポインターを置くと、その特定の送信者または受信者のメッセージ数を確認できます。

グラフの下の詳細テーブルには、選択したビューに基づいて送信者または受信者とメッセージ数が表示されます。

[フィルター] をクリックし、[開始日] と [終了日]  を選択すると、グラフと詳細テーブル **の両方を****フィルター処理できます**。

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

[上位 **の送信者と受信者] ページで** 、[エクスポート] ![アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート** ] ボタンを使用できます。

![[上位の送信者と受信者] レポートに [上位メール送信者] ビューのデータを表示します。](../../media/top-senders-and-recipients-report-view.png)

## <a name="url-protection-report"></a>URL 保護レポート

URL **保護レポートは、** Microsoft Defender でのみ使用できます。Office 365。 詳細については、「URL 保護 [レポート」を参照してください](view-reports-for-mdo.md#url-protection-report)。

## <a name="user-reported-messages-report"></a>ユーザーが報告したメッセージ レポート

> [!IMPORTANT]
> ユーザーが報告した **メッセージ レポート** が正しく動作するには、ユーザーの環境で監査ログを有効にするMicrosoft 365があります。 これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。 詳細については、「監査ログの[検索を有効またはMicrosoft 365を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

[**ユーザーレポート メッセージ**] レポートには、ユーザーが迷惑メール、フィッシング詐欺の試み、または良いメールとして報告した電子メール [](enable-the-report-message-add-in.md) メッセージに関する情報が、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して表示 [されます。](enable-the-report-phish-add-in.md)

ポータルでレポートを表示するには \> Microsoft 365 Defender[レポートの電子メール] &**[**\>グループ&**] に移動します**。 [コラボレーション **レポートのメール&] ページで**、[ユーザーが報告したメッセージ] を探し、[詳細の表示] **をクリックします**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/userSubmissionReport>。 ポータルで [管理者の申請に移動するにはMicrosoft 365 Defender送信](admin-submission.md)に移動 **] をクリックします**。

![ユーザーが報告したメッセージ ウィジェットは、[電子メール &] ページに表示されます。](../../media/user-reported-messages-widget.png)

[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **報告日**: **開始時刻** と **終了時刻**
- [**レポート作成者**]
- **メールの件名**
- **メッセージの報告 ID**
- **ネットワーク メッセージ ID**
- **Sender**
- **報告された理由**
  - **迷惑メールではない**
  - **フィッシング**
  - **スパム**
- **フィッシング シミュレーション**: **はいまたは****いいえ**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

エントリをグループ化するには、[グループ] を **クリック** し、ドロップダウン リストから次のいずれかの値を選択します。

- **なし**
- **理由**
- **Sender**
- [**レポート作成者**]
- **再スキャンの結果**
- **フィッシング シミュレーション**

![ユーザーが報告したメッセージ レポート。](../../media/user-reported-messages-report.png)

グラフの下の詳細テーブルは、次の情報を示しています。

- **メールの件名**
- [**レポート作成者**]
- **報告日**
- **Sender**
- **報告された理由**
- **再スキャンの結果**
- **タグ**: ユーザー タグの詳細については、「User [tags」を参照してください](user-tags.md)。

分析のために Microsoft にメッセージを送信するには、表からメッセージ エントリを選択し、[分析のために **Microsoft** に送信] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。

- **クリーンレポート**
- **フィッシングの報告**
- **マルウェアの報告**
- **[スパムの報告**]
- **トリガー調査** (Defender for Office 365)

[ユーザーが **報告したメッセージ] ページ** で、[エクスポート] ![アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート](#export-report)** ] ボタンを使用できます。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するために必要なアクセス許可

この記事で説明するレポートを表示して使用するには、ポータルで次のいずれかの役割グループのメンバーであるMicrosoft 365 Defenderがあります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ閲覧者**
- **グローバル リーダー**

詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

**注**: Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合は、

レポートにデータが表示されない場合は、使用しているフィルターを確認し、ポリシーが正しく設定されていることを再確認します。 詳細については、「脅威から [保護する」を参照してください](protect-against-threats.md)。

## <a name="schedule-report"></a>レポートをスケジュールする

1. 特定のレポートのメイン ページで、[スケジュールの作成] アイコン ![をクリックします。](../../media/m365-cc-sc-create-icon.png) **スケジュールを作成します**。
2. [スケジュール **されたレポートの作成] ウィザード** が開きます。 [スケジュール **されたレポートの名前] ページ** で、[名前] の値を確認 **またはカスタマイズし** 、[次へ] を **クリックします**。
3. [基本設定 **の設定] ページ** で、次の設定を構成します。
   - **頻度**: 次のいずれかの値を選択します。
     - **毎週** (既定)
     - **毎月**
   - **開始日:** レポートの生成が開始された場合。 既定値は今日です。
   - **有効期限:** レポートの生成が終了した場合。 既定値は今日から 1 年です。

   完了したら、**[次へ]** をクリックします。

4. [受信者 **] ページで** 、レポートの受信者を選択します。 既定値はメール アドレスですが、他のユーザーを追加できます。

   完了したら、**[次へ]** をクリックします。

5. [確認 **] ページ** で、選択内容を確認します。 各セクションの **[戻る** ] ボタンまたは **[編集** ] リンクをクリックして変更を加えます。

   完了したら、**[送信]** をクリックします。

### <a name="managed-existing-scheduled-reports"></a>既存のスケジュールされたレポートの管理

既に作成したスケジュールされたレポートを管理するには、次の手順を実行します。

1. [スケジュールの管理Microsoft 365 Defender] <https://security.microsoft.com>の [レポート] [電子 **メール**\>] を展開し、[&**の管理** \> **] を選択します**。

   [スケジュールの管理] ページ **に直接移動するには** 、 を使用します <https://security.microsoft.com/ManageSubscription>。

2. [スケジュール **の管理] ページ** に、スケジュールされたレポートごとに次の情報が表示されます。
   - **開始日をスケジュールする**
   - **スケジュール名**
   - **レポートの種類**
   - **Frequency**
   - **最終送信**

   変更する既存のスケジュールされたレポートを検索します。

3. スケジュールされたレポートを選択した後、開く詳細フライアウトで次の操作を実行します。
   - **名前の** 編集: このボタンをクリックし、表示されるフライアウトでレポートの名前を変更し、[保存] をクリック **します**。
   - **スケジュールの** 削除: このボタンをクリックし、表示される警告を読み取り (以前のレポートはダウンロードできなくなりました)、[保存] をクリック **します**。
   - **[スケジュールの詳細** ] セクション: [ **基本設定の編集] をクリックして** 、次の設定を変更します。
     - **頻度**: **週単位****または月単位**
     - **開始日**
     - **有効期限**

     完了したら、**[保存]** をクリックします。

   - **[受信者]** セクション: [受信者 **の編集] をクリック** して、スケジュールされたレポートの受信者を追加または削除します。 完了したら、[保存] を **クリックします。**

   完了したら、**[閉じる]** をクリックします。

## <a name="request-report"></a>要求レポート

1. 特定のレポートのメイン ページで、[レポートの要求] アイコン ![をクリックします。](../../media/m365-cc-sc-download-icon.png) **レポートを要求します**。
2. [ **オンデマンド レポートの作成] ウィザードが** 開きます。 [オンデマンド **レポートの名前] ページで**、[名前] の値を確認またはカスタマイズし、[次へ] をクリック **します**。
3. [基本設定 **の設定] ページ** で、次の設定を確認または構成します。
   - **開始日:** レポートの生成が開始された場合。 既定値は 1 か月前です。
   - **有効期限:** レポートの生成が終了した場合。 既定値は今日です。

   完了したら、**[次へ]** をクリックします。

4. [受信者 **] ページで** 、レポートの受信者を選択します。 既定値はメール アドレスですが、他のユーザーを追加できます。

   完了したら、**[次へ]** をクリックします。

5. [確認 **] ページ** で、選択内容を確認します。 各セクションの **[戻る** ] ボタンまたは **[編集** ] リンクをクリックして変更を加えます。

   完了したら、**[送信]** をクリックします。

6. レポートが正常に作成されると、[新しいオンデマンド レポート作成] ページが表示され、[別のレポートの作成] または [完了] **をクリック****できます**。

   レポートは、次のセクションで説明するように **、[** ダウンロード用のレポート] ページでも使用できます。

### <a name="download-reports"></a>レポートのダウンロード

1. [レポート] Microsoft 365 Defenderで<https://security.microsoft.com>\>、[レポート] [メール] を展開し、[&**]** \> を選択 **します**。

   [ダウンロード用のレポート] **ページに直接移動するには** 、 を使用します <https://security.microsoft.com/ReportsForDownload>。

2. [ダウンロード用 **のレポート] ページ** に、使用可能なレポートごとに次の情報が表示されます。
   - **開始日**
   - **名前**
   - **レポートの種類**
   - **最終送信**
   - **方向**

   ダウンロードするレポートを検索して選択します。

## <a name="export-report"></a>レポートのエクスポート

特定のレポートのメイン ページで、[エクスポート] アイコンを ![クリックします。](../../media/m365-cc-sc-download-icon.png) **エクスポート** (そのリンクが使用可能な場合)。 エクスポート **条件のフライ** アウトが表示され、次の設定を構成できます。

- **エクスポートするビューを選択する**: 次のいずれかの値を選択します。
  - **概要:** データは過去 90 日間利用できます。
  - **詳細**: データは過去 30 日間利用できます。
- **日付 (UTC)**: **開始日と****終了日**。

フィルターの構成が完了したら、[エクスポート] を **クリックします**。 開いたダイアログで、ファイルを開く、ファイルを保存する、または選択内容を記憶するを選択できます。

エクスポートされた.csvは、150,000 行に制限されます。 データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。

## <a name="related-topics"></a>関連項目

[EOP でのスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md)

[スマート レポートと分析情報 (Microsoft 365 Defender ポータル)](reports-and-insights-in-security-and-compliance.md)

[メール フロー レポートをポータルでMicrosoft 365 Defenderする](view-mail-flow-reports.md)

[Defender for Office 365](view-reports-for-mdo.md)
