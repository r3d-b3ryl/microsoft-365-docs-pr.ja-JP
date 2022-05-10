---
title: Defender for Office 365 レポートを表示する
f1.keywords:
- CSH
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
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft 365 Defender ポータルで使用できるDefender for Office 365 レポートを検索して使用する方法について説明します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed83064d1686d1cf556e0b2dcca5766556c5fa3
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64970934"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでDefender for Office 365レポートを表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365組織 (Microsoft 365 E5 サブスクリプションやプラン 1 のMicrosoft Defender for Office 365など)Microsoft Defender for Office 365プラン 2 アドオン) には、さまざまなセキュリティ関連のレポートが含まれています。 [必要なアクセス許可](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)がある場合は、Microsoft 365 Defender ポータルでこれらのレポートを表示してダウンロードできます。

## <a name="view-and-download-reports"></a>レポートを表示してダウンロードする

### <a name="view-reports"></a>レポートの表示

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**レポート** \> **メール] &コラボレーション**\>メール **&コラボレーション レポート** に移動します。 **[電子メール & コラボレーション レポート**] ページに直接移動するには、<https://security.microsoft.com/emailandcollabreport>.

1. 表示するレポートを選択し、[ **詳細の表示**] を選択します。

### <a name="download-reports"></a>レポートのダウンロード

1. Microsoft 365 Defender ポータルで<https://security.microsoft.com>**、ReportsEmail** >  **& コラボレーション** \> **レポートに移動してダウンロードします**。 **[レポートのダウンロード**] ページに直接移動するには、次を使用します<https://security.microsoft.com/ReportsForDownload?viewid=custom>。

:::image type="content" source="../../media/email-collaboration-download-reports.png" alt-text="Microsoft 365 Defender ポータルの [電子メール & コラボレーション レポート] ページ" lightbox="../../media/email-collaboration-download-reports.png":::

> [!NOTE]
>
> Defender for Office 365を必要としない電子メール セキュリティ レポートについては、Microsoft 365 Defender [ポータルでの電子メール セキュリティ レポートの表示に関する](view-email-security-reports.md)説明を参照してください。
>
> メール フローに関連するレポートが、Exchange管理センター (EAC) に表示されるようになりました。 これらのレポートの詳細については、[新しいExchange管理センターのメール フロー レポートに関する](/exchange/monitoring/mail-flow-reports/mail-flow-reports)ページを参照してください。

## <a name="safe-attachments-file-types-report"></a>セーフ添付ファイルの種類レポート

> [!NOTE]
> このレポートは非推奨になりました。 [脅威保護の状態レポート](#threat-protection-status-report)でも、同じ情報を入手できます。

## <a name="safe-attachments-message-disposition-report"></a>セーフ 添付ファイル メッセージの処理レポート

> [!NOTE]
> このレポートは非推奨になりました。 [脅威保護の状態レポート](#threat-protection-status-report)でも、同じ情報を入手できます。

## <a name="mail-latency-report"></a>メール待機時間レポート

**[メール待機時間] レポート** には、組織内で発生したメール配信と起爆待機時間の集計ビューが表示されます。 サービス内のメール配信時間はさまざまな要因の影響を受け、絶対配信時間 (秒単位) は成功や問題を示す適切な指標ではないことがよくあります。 ある日の配信時間が遅い場合は、別の日の平均配送時間、またはその逆と見なされる場合があります。 これにより、他のメッセージの観察された配信時間に関する統計データに基づいて、メッセージ配信を修飾しようとします。

クライアント側とネットワークの待機時間は含まれません。

レポートを表示するには、Microsoft 365 Defender ポータル<https://security.microsoft.com>を開き、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 **[電子メール & コラボレーション レポート**] ページに直接移動するには、<https://security.microsoft.com/emailandcollabreport>.

[ **電子メール & コラボレーション レポート** ] ページで、[ **メール待機時間レポート** ] を探し、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、 <https://security.microsoft.com/mailLatencyReport>.

:::image type="content" source="../../media/mail-latency-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの [メール待機時間レポート] ウィジェット" lightbox="../../media/mail-latency-report-widget.png":::

**[メール待機時間] レポート** ページの [メール待機時間] レポート ページには、次のタブ **があります**。

- **50 パーセンタイル**: これは、メッセージ配信時間の中間です。 この値は、平均配信時間と見なすことができます。 このタブは既定で選択されています。
- **90 パーセンタイル**: これは、メッセージ配信の待機時間が長いことを示します。 メッセージの 10% だけが、この値を超えて配信に時間がかかりました。
- **99 パーセンタイル**: これは、メッセージ配信の待機時間が最も長いことを示します。

選択したタブに関係なく、グラフには次のカテゴリに分類されたメッセージが表示されます。

- **全体**
- **爆発**

グラフ内のカテゴリにマウス ポインターを合わせると、各カテゴリの待機時間の内訳が表示されます。

:::image type="content" source="../../media/mail-latency-report-50th-percentile-view.png" alt-text="メール待機時間レポートの 50 パーセンタイル ビュー" lightbox="../../media/mail-latency-report-50th-percentile-view.png":::

[ **フィルター]** をクリックすると、グラフと詳細テーブルの両方を次の値でフィルター処理できます。

- **日付 (UTC)**: **開始日** と **終了日**
- **メッセージ ビュー**: 次のいずれかの値。
  - **すべてのメッセージ**
  - **デトネーションされたメッセージ**: 次のいずれかの値。
    - **インラインデトネーション**: 配信前に完全にテストされたメッセージが含まれます。
    - **非同期起爆**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **日付 (UTC)**
- **遅延**
- **メッセージ数**
- **50 パーセンタイル**
- **90 パーセンタイル**
- **99 パーセンタイル**

メイン レポート ページの [エクスポート] ![アイコン。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート]](view-email-security-reports.md#export-report)** ボタンを使用できます。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

**脅威の保護状態** レポートは、[Exchange Online Protection (](exchange-online-protection-overview.md)EOP) とMicrosoft Defender for Office 365によって検出およびブロックされた悪意のあるコンテンツと悪意のある電子メールに関する情報をまとめた 1 つのビューです。 詳細については、 [脅威保護の状態レポートに関するページを](view-email-security-reports.md#threat-protection-status-report)参照してください。

## <a name="top-senders-and-recipients-report"></a>上位の送信者と受信者のレポート

**[上位の送信者と受信者] レポートには、** EOP とDefender for Office 365保護機能の上位受信者が表示されます。 詳細については、「 [上位の送信者と受信者のレポート](view-email-security-reports.md#top-senders-and-recipients-report)」を参照してください。

## <a name="url-protection-report"></a>URL 保護レポート

**URL 保護レポート** には、検出された脅威の概要と傾向のビューと、[セーフ リンク](safe-links.md)の一部として URL クリックに対して実行されたアクションが表示されます。 [ユーザークリックの追跡] オプションが選択されていない場合、セーフ リンク ポリシーが適用された **ユーザーからのクリック** データは、このレポートには表示されません。

レポートを表示するには、[Microsoft 365 Defender ポータル](https://security.microsoft.com)を開き、**レポート** \> **メール & コラボレーション** \> **メール & コラボレーション レポート** に移動します。 [ **電子メール & コラボレーション レポート** ] ページで、[ **URL 保護] ページ** を見つけて、[ **詳細の表示**] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/URLProtectionActionReport>。

:::image type="content" source="../../media/url-protection-report-widget.png" alt-text="[電子メール & コラボレーション レポート] ページの URL 保護レポート ウィジェット" lightbox="../../media/url-protection-report-widget.png":::

**URL 保護** レポート ページで使用可能なビューについては、次のセクションで説明します。

> [!NOTE]
> これは *保護傾向レポート* です。つまり、データは大規模なデータセットの傾向を表します。 その結果、グラフ内のデータはここでリアルタイムでは使用できませんが、詳細テーブルのデータが表示されるため、2 つのデータの間に若干の不一致が見られる場合があります。 グラフは 4 時間に 1 回更新され、過去 90 日間のデータが含まれます。

### <a name="view-data-by-url-click-protection-action"></a>URL クリック保護アクションでデータを表示する

:::image type="content" source="../../media/url-threat-protection-report-url-click-protection-action-view.png" alt-text="URL 保護レポートのビュー名 URL クリック保護アクション" lightbox="../../media/url-threat-protection-report-url-click-protection-action-view.png":::

**[URL クリック保護によるデータの表示] アクション** ビューには、組織内のユーザーによる URL クリックの数とクリックの結果が表示されます。

- **許可:** クリックが許可されます。
- **テナント管理者が許可** する: セーフ リンク ポリシーで許可されるクリック数。
- **ブロック**: [ブロック] をクリックします。
- **テナント管理者によってブロックされる**: セーフ リンク ポリシーでブロックされたクリック数。
- **ブロックとクリック: ユーザーがブロックされた** URL にクリックスルーするブロックされたクリック。
- **テナント管理者によってブロックされ、クリックされた** 場合: 管理者はリンクをブロックしましたが、ユーザーはクリックスルーしました。
- **スキャン中にクリックされた** 場合: ユーザーが保留中のスキャン ページをクリックして URL に移動する場所をクリックします。
- **保留中のスキャン: スキャン** の判定を保留中の URL をクリックします。

クリックは、ユーザーが悪意のある Web サイトのブロック ページをクリックしたことを示します (管理者は、セーフ リンク ポリシーでクリックを無効にすることができます)。

[ **フィルター**] をクリックすると、表示されるポップアップで次の値の 1 つ以上を選択して、レポートと詳細テーブルを変更できます。

- **日付 (UTC)**: **開始日** と **終了日**
- **アクション**:
  - **可**
  - **ブロック済み**
  - **テナント管理者が許可する**
  - **ブロックされ、クリックされた**
  - **テナント管理者によってブロックされ、クリックされた**
  - **スキャン中にクリックされた**
  - **保留中のスキャン**
- **ドメイン**: レポートの結果に表示される URL ドメイン。
- **受信者**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

グラフの下の詳細テーブルでは、組織内で過去 7 日間に発生したすべてのクリックをほぼリアルタイムで表示します。

- **クリック時間**
- **ユーザー**
- **URL**
- **操作**
- **アプリ**

メイン レポート ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](view-email-security-reports.md#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](view-email-security-reports.md#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](view-email-security-reports.md#export-report)** ボタンを使用できます。

### <a name="view-data-by-url-click-by-application"></a>アプリケーション別の URL クリックでデータを表示する

:::image type="content" source="../../media/url-threat-protection-report-url-click-by-application-view.png" alt-text="URL 保護レポートの URL クリック保護アクション ビュー" lightbox="../../media/url-threat-protection-report-url-click-by-application-view.png":::

**[アプリケーション別の URL クリック別のデータの表示]** ビューには、セーフリンクをサポートするアプリ別の URL クリック数が表示されます。

- **電子メール クライアント**
- **ドキュメントのOffice**
- **Teams**

[ **フィルター**] をクリックすると、表示されるポップアップで次の値の 1 つ以上を選択して、レポートと詳細テーブルを変更できます。

- **日付 (UTC)**: **開始日** と **終了日**
- **検出**: グラフから使用可能なアプリ。
- **ドメイン**: レポートの結果に表示される URL ドメイン。
- **受信者**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

グラフの下の詳細テーブルでは、組織内で過去 7 日間に発生したすべてのクリックをほぼリアルタイムで表示します。

- **クリック時間**
- **ユーザー**
- **URL**
- **操作**
- **アプリ**

メイン レポート ページの [スケジュールの作成] ![アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](view-email-security-reports.md#schedule-report)**、 ![レポートの要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[[要求レポート]](view-email-security-reports.md#request-report)**、[ ![エクスポート] アイコン。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](view-email-security-reports.md#export-report)** ボタンを使用できます。

## <a name="additional-reports-to-view"></a>表示するその他のレポート

この記事で説明されているレポートに加えて、次の表に示すように、他にもいくつかのレポートを使用できます。

|レポート|トピック|
|---|---|
|**エクスプローラー** (Microsoft Defender for Office 365 プラン 2) または **リアルタイム検出** (Microsoft Defender for Office 365 プラン 1)|[脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)|
|Defender for Office 365を必要としない電子メール セキュリティ レポート|[Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する](view-email-security-reports.md)|
|Exchange管理センター (EAC) のメール フロー レポート|[新しいExchange管理センターのメール フロー レポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|

PowerShell レポート コマンドレット:

|レポート|トピック|
|---|---|
|上位送信者および受信者|[Get-MailTrafficTopReport](/powershell/module/exchange/get-mailtraffictopreport) <p> [Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|上位マルウェア|[Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|メール トラフィック|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <p> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|安全なリンク|[Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <p> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|
|侵害されたユーザー|[Get-CompromisedUserAggregateReport](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [Get-CompromisedUserDetailReport](/powershell/module/exchange/get-compromiseduserdetailreport)|
|メール フローの状態|[Get-MailflowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|
|スプーフィングされたユーザー|[Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport)|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Defender for Office 365 レポートを表示するには、どのようなアクセス許可が必要ですか?

この記事で説明されているレポートを表示して使用するには、Microsoft 365 Defender ポータルで次のいずれかのロール グループのメンバーである必要があります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ閲覧者**
- **グローバル閲覧者**

詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

**注**: Microsoft 365 管理センターの対応するAzure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可 _と_、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合はどうなりますか?

Defender for Office 365 レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。 Defender for Office 365保護を実施するには、組織に[セーフリンク ポリシー](set-up-safe-links-policies.md)と[セーフ添付ファイル ポリシー](set-up-safe-attachments-policies.md)が定義されている必要があります。 [スパム対策とマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)も参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft 365 Defender ポータルでのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[組み込みロールをAzure ADする](/azure/active-directory/roles/permissions-reference)
