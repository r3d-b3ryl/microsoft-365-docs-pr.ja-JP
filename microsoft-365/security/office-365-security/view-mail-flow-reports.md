---
title: レポート ダッシュボードでメール フロー レポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ コンプライアンス センターのレポート ダッシュボードで使用可能なメール フロー レポートについて&できます。
ms.custom: ''
ms.openlocfilehash: 9e9249eab5d3519dac0e33acf40d600d471b7cb2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826459"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="7580e-103">レポート ダッシュボードのメール フロー レポートをセキュリティ コンプライアンス センター&表示する</span><span class="sxs-lookup"><span data-stu-id="7580e-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="7580e-104">セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで使用可能な [メール](mail-flow-insights-v2.md) フロー レポートに加えて、Microsoft 365 組織を監視できるように、レポート ダッシュボードでさまざまな追加のメール フロー レポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="7580e-105">必要なアクセス許可 [があは、](#what-permissions-are-needed-to-view-these-reports)セキュリティ センターでこれらの [レポートを表示するには、[レポート & ダッシュボード](https://office.protection.com) ] に **移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="7580e-106">レポート ダッシュボードに直接移動するには、開きます <https://office.protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="7580e-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![セキュリティ センター センターのレポート ダッシュボード& レポート](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="7580e-108">コネクタ レポート</span><span class="sxs-lookup"><span data-stu-id="7580e-108">Connector report</span></span>

<span data-ttu-id="7580e-109">コネクタ **レポートには** 、組織で構成されている [受信コネクタおよび送信コネクタ上の](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) メール フロー アクティビティが示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="7580e-110">レポートを表示するには、セキュリティ コンプライアンス センター [で&、[レポート](https://protection.office.com)ダッシュボード] に移動 **し** \> **、[コネクタ** レポート] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="7580e-111">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="7580e-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![レポート ダッシュボード内のコネクタ レポート ウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="7580e-113">コネクタ レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-113">Report view for the Connector report</span></span>

<span data-ttu-id="7580e-114">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="7580e-115">**データの表示方法: メール フロー**: 次の別の種類により構成される受信メッセージと送信メッセージ数が示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="7580e-116">**合計**</span><span class="sxs-lookup"><span data-stu-id="7580e-116">**Total**</span></span>
  - <span data-ttu-id="7580e-117">**コネクタなしでインターネットから**</span><span class="sxs-lookup"><span data-stu-id="7580e-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="7580e-118">**コネクタのないインターネットにアクセスする**</span><span class="sxs-lookup"><span data-stu-id="7580e-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="7580e-119">設定した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="7580e-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="7580e-120">グラフのデータを分離するには、[コントロールのデータを表示 **する] を** 使用して、これらのオプションまたは [すべてのメール フロー] **のいずれかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![コネクタ レポートでメール フロー別データを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="7580e-122">**データの表示元: TLS 使用**率: このグラフには、メール フローのトランスポート層セキュリティ (TLS) のバージョンの使用率が示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="7580e-123">グラフのデータを分離するには、コントロールの **[データを表示する] を使用** して、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7580e-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="7580e-124">**すべてのメール フロー**</span><span class="sxs-lookup"><span data-stu-id="7580e-124">**All mail flow**</span></span>
  - <span data-ttu-id="7580e-125">**コネクタなしでインターネットから**</span><span class="sxs-lookup"><span data-stu-id="7580e-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="7580e-126">**コネクタのないインターネットにアクセスする**</span><span class="sxs-lookup"><span data-stu-id="7580e-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="7580e-127">設定した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="7580e-127">A specific connector that you've configured.</span></span>

  ![コネクタ レポートで TLS 使用状況別のデータを表示する](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="7580e-129">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="7580e-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="7580e-130">コネクタ レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-130">Details table view for the Connector report</span></span>

<span data-ttu-id="7580e-131">レポート ビューで **詳細テーブルの表示** をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="7580e-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="7580e-132">**Date**</span></span>
- <span data-ttu-id="7580e-133">**コネクタの方向と名前**</span><span class="sxs-lookup"><span data-stu-id="7580e-133">**Connector direction and name**</span></span>
- <span data-ttu-id="7580e-134">**コネクタの種類**</span><span class="sxs-lookup"><span data-stu-id="7580e-134">**Connector type**</span></span>
- <span data-ttu-id="7580e-135">**TLS を適用しますか?:** 値 **は True または** False **です**。</span><span class="sxs-lookup"><span data-stu-id="7580e-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="7580e-136">**TLS なし** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="7580e-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="7580e-137">**TLS 1.0** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="7580e-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="7580e-138">**TLS 1.1** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="7580e-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="7580e-139">**TLS 1.2 (パー** センテージ)</span><span class="sxs-lookup"><span data-stu-id="7580e-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="7580e-140">**Volume:** The number of messages.</span><span class="sxs-lookup"><span data-stu-id="7580e-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="7580e-141">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="7580e-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="7580e-142">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7580e-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="7580e-143">Exchange トランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="7580e-143">Exchange transport rule report</span></span>

<span data-ttu-id="7580e-144">**Exchange トランスポート ルール レポートは**、組織内のメール フロー ルール (トランスポート ルールとも呼ばれる) の影響を、組織内の受信メッセージと送信メッセージに対して示します。</span><span class="sxs-lookup"><span data-stu-id="7580e-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="7580e-145">レポートを表示するには、セキュリティ コンプライアンス センター [&開き、[レポート](https://protection.office.com)ダッシュボード **] に** \> **移動して** Exchange トランスポート **ルールを選択します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="7580e-146">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="7580e-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![レポート ダッシュボードの Exchange トランスポート ルール ウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="7580e-148">Exchange トランスポート ルール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="7580e-149">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="7580e-150">**データの表示方法:Exchange トランスポート ルール** \>**方向の区切り.:** このグラフは、トランスポート ルール**によって**影響された**受信**メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="7580e-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="7580e-151">**データの表示方法:Exchange トランスポート ルール** \>**重大度: 重大度 :** この図は、**重**大度が高 **、中度**、および低い重大度**メッセージの数を示**します。</span><span class="sxs-lookup"><span data-stu-id="7580e-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="7580e-152">重大度レベルは、ルールのアクションとして設定します (**この**ルールを重大度レベルまたは_SetAuditSeverity で監査)。_</span><span class="sxs-lookup"><span data-stu-id="7580e-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="7580e-153">詳細については [、Exchange Online 内のメール フロー ルールのアクションを参照してください](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="7580e-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="7580e-154">**データの表示: DLP Exchange トランスポート ルール** \>**方向の区切り:この**グラフは、データ損**失**防止**Outbound**(DLP) トランスポート ルールによって影響された受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="7580e-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="7580e-155">次のオプションを選択して、グラフの絞り込みをさらに詳細にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7580e-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="7580e-156">**表示するデータ: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="7580e-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="7580e-157">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="7580e-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="7580e-158">**表示データ:低ボリュームのコンテンツを検出 - 米国のパトリアト法**</span><span class="sxs-lookup"><span data-stu-id="7580e-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="7580e-159">**データの表示: DLP Exchange トランスポート ルール** \>**[方向]: この**ビューには、重大度が**高\*\*\*\*、中程**度の重要度、および DLP**Low severity**トランスポート ルールの影響を受け取った重要度が低いメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="7580e-160">次のオプションを選択して、グラフの絞り込みをさらに詳細にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7580e-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="7580e-161">**表示するデータ: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="7580e-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="7580e-162">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="7580e-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="7580e-163">**表示データ:低ボリュームのコンテンツを検出 - 米国のパトリアト法**</span><span class="sxs-lookup"><span data-stu-id="7580e-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="7580e-164">レポート ビューで **[フィルター** ] をクリックした場合は、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="7580e-165">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="7580e-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="7580e-166">Direction の値</span><span class="sxs-lookup"><span data-stu-id="7580e-166">Direction values</span></span>
- <span data-ttu-id="7580e-167">重大度の値</span><span class="sxs-lookup"><span data-stu-id="7580e-167">Severity values</span></span>

![Exchange トランスポート ルール レポートのレポート ビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="7580e-169">Exchange トランスポート ルール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="7580e-170">[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。</span><span class="sxs-lookup"><span data-stu-id="7580e-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7580e-171">**データの表示方法: Exchange トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="7580e-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="7580e-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="7580e-172">**Date**</span></span>
  - <span data-ttu-id="7580e-173">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="7580e-173">**Transport rule**</span></span>
  - <span data-ttu-id="7580e-174">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="7580e-174">**Subject**</span></span>
  - <span data-ttu-id="7580e-175">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="7580e-175">**Sender address**</span></span>
  - <span data-ttu-id="7580e-176">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="7580e-176">**Recipient address**</span></span>
  - <span data-ttu-id="7580e-177">**重大度**</span><span class="sxs-lookup"><span data-stu-id="7580e-177">**Severity**</span></span>
  - <span data-ttu-id="7580e-178">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="7580e-178">**Direction**</span></span>

- <span data-ttu-id="7580e-179">**データの表示 : DLP Exchange トランスポート ルール**:</span><span class="sxs-lookup"><span data-stu-id="7580e-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="7580e-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="7580e-180">**Date**</span></span>
  - <span data-ttu-id="7580e-181">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="7580e-181">**DLP policy**</span></span>
  - <span data-ttu-id="7580e-182">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="7580e-182">**Transport rule**</span></span>
  - <span data-ttu-id="7580e-183">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="7580e-183">**Subject**</span></span>
  - <span data-ttu-id="7580e-184">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="7580e-184">**Sender address**</span></span>
  - <span data-ttu-id="7580e-185">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="7580e-185">**Recipient address**</span></span>
  - <span data-ttu-id="7580e-186">**重大度**</span><span class="sxs-lookup"><span data-stu-id="7580e-186">**Severity**</span></span>
  - <span data-ttu-id="7580e-187">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="7580e-187">**Direction**</span></span>

<span data-ttu-id="7580e-188">詳細テーブル ビュー **で [** フィルター] をクリックした場合、結果は次のフィルターを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="7580e-189">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="7580e-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="7580e-190">Direction の値</span><span class="sxs-lookup"><span data-stu-id="7580e-190">Direction values</span></span>
- <span data-ttu-id="7580e-191">重大度の値</span><span class="sxs-lookup"><span data-stu-id="7580e-191">Severity values</span></span>

<span data-ttu-id="7580e-192">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7580e-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="7580e-193">転送レポート</span><span class="sxs-lookup"><span data-stu-id="7580e-193">Forwarding report</span></span>

<span data-ttu-id="7580e-194">転送 **レポートは、** 組織が Exchange Online メールボックスから外部ドメインに自動的に転送されたメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="7580e-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="7580e-195">転送されたメッセージは、セキュリティやコンプライアンスリスクが発生する可能性があるため、侵害されたアカウントを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7580e-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="7580e-196">レポートを表示するには、セキュリティ センター コンプライアンス [センター&開き、[レポート](https://protection.office.com)ダッシュボード **] に** \> **移動し** 、[転送レポート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="7580e-197">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="7580e-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![レポート ダッシュボードの転送レポート ウィジェット](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="7580e-199">転送レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="7580e-200">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="7580e-201">**データの転送: 転送方法は次**のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7580e-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="7580e-202">**トランスポート ルール**: メール フロー ルール [とも呼ばれる](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="7580e-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="7580e-203">**メールボックス ルール**: 受信トレイ ルール [とも呼ばれる](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="7580e-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![転送レポートの転送方法ビュー](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="7580e-205">**[転送ドメイン] のデータを表示**: このビューには、転送先となってこかの受信者ドメインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![転送レポートの転送ドメイン ビュー](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="7580e-207">**次のデータを表示します。以下**の転送ワーカーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="7580e-208">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="7580e-208">**Transport rule**</span></span>
  - <span data-ttu-id="7580e-209">転送受信トレイ ルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="7580e-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![転送レポートの転送者ビュー](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="7580e-211">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="7580e-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="7580e-212">転送レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="7580e-213">レポート ビューで **詳細テーブルの表示** をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="7580e-214">**Forwarders**:トランスポート **ルールまたは転送** 受信トレイ ルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="7580e-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="7580e-215">**転送の種類**: 値の**メールボックス ルールまたは\*\*\*\*トランスポート ルール。**</span><span class="sxs-lookup"><span data-stu-id="7580e-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="7580e-216">**受信者名**</span><span class="sxs-lookup"><span data-stu-id="7580e-216">**Recipient name**</span></span>
- <span data-ttu-id="7580e-217">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="7580e-217">**Recipient domain**</span></span>
- <span data-ttu-id="7580e-218">**Details**: メール フロー ルールの GUID 値であるか、受信トレイ ルールの RuleIdentity 値です。</span><span class="sxs-lookup"><span data-stu-id="7580e-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="7580e-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="7580e-219">**Count**</span></span>
- <span data-ttu-id="7580e-220">**1 つ目の転送日**</span><span class="sxs-lookup"><span data-stu-id="7580e-220">**First forward date**</span></span>

<span data-ttu-id="7580e-221">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="7580e-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="7580e-222">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7580e-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="7580e-223">メール フロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="7580e-223">Mailflow status report</span></span>

<span data-ttu-id="7580e-224">メール **フロー状態レポートは送信** および受信メールの [レポートに似て、](#sent-and-received-email-report)エッジで電子メールの許可またはブロックに関する追加情報があります。</span><span class="sxs-lookup"><span data-stu-id="7580e-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="7580e-225">これは、エッジ保護情報を含むレポートのみで、Exchange Online Protection (EOP) による評価を行うためにサービスに組み込まれる前にブロックされるメールの数だけを示します。</span><span class="sxs-lookup"><span data-stu-id="7580e-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="7580e-226">メッセージを 5 人の受信者に送信した場合は、1 つのメッセージとしてのみ、5 つの異なるメッセージとしてカウントします。</span><span class="sxs-lookup"><span data-stu-id="7580e-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="7580e-227">レポートを表示するには、セキュリティ センターの [セキュリティ&開き、[](https://protection.office.com)レポート ダッシュボード **] に** \> **移動して** 、[メール フロー **ステータス レポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="7580e-228">メール フローの状態レポートに **直接進みるには、** 開きます <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="7580e-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![レポート ダッシュボードのメール フローステータス レポート ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="7580e-230">メールフロー ステータス レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="7580e-231">レポートを開くと、[種類] **タブ** が既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="7580e-232">既定では、このビューには、次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7580e-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="7580e-233">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="7580e-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="7580e-234">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="7580e-234">**Direction**:</span></span>

  - <span data-ttu-id="7580e-235">**受信**</span><span class="sxs-lookup"><span data-stu-id="7580e-235">**Inbound**</span></span>
  - <span data-ttu-id="7580e-236">**送信**</span><span class="sxs-lookup"><span data-stu-id="7580e-236">**Outbound**</span></span>
  - <span data-ttu-id="7580e-237">**Intra-org:** このカウントはテナント内のメッセージの数です</span><span class="sxs-lookup"><span data-stu-id="7580e-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="7580e-238">送信者abc@domain.com受信者が受信者への送信xyz@domain.com (受信/送信とは別**に含\*\*\*\*まれます**)</span><span class="sxs-lookup"><span data-stu-id="7580e-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="7580e-239">**型**:</span><span class="sxs-lookup"><span data-stu-id="7580e-239">**Type**:</span></span>

  - <span data-ttu-id="7580e-240">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="7580e-240">**Good mail**</span></span>
  - <span data-ttu-id="7580e-241">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="7580e-241">**Malware**</span></span>
  - <span data-ttu-id="7580e-242">**スパム**</span><span class="sxs-lookup"><span data-stu-id="7580e-242">**Spam**</span></span>
  - <span data-ttu-id="7580e-243">**エッジの保護**</span><span class="sxs-lookup"><span data-stu-id="7580e-243">**Edge protection**</span></span>
  - <span data-ttu-id="7580e-244">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="7580e-244">**Rule messages**</span></span>
  - <span data-ttu-id="7580e-245">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="7580e-245">**Phishing email**</span></span>

<span data-ttu-id="7580e-246">グラフは種類の値 **によって構成されています** 。</span><span class="sxs-lookup"><span data-stu-id="7580e-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="7580e-247">これらのフィルターは、[フィルター] をクリック **するか、グラフの** 凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="7580e-248">データ テーブルには次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7580e-248">The data table contains the following information:</span></span>

- <span data-ttu-id="7580e-249">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="7580e-249">**Direction**</span></span>
- <span data-ttu-id="7580e-250">**型**</span><span class="sxs-lookup"><span data-stu-id="7580e-250">**Type**</span></span>
- <span data-ttu-id="7580e-251">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="7580e-251">**24 hours**</span></span>
- <span data-ttu-id="7580e-252">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="7580e-252">**3 days**</span></span>
- <span data-ttu-id="7580e-253">**7 日**</span><span class="sxs-lookup"><span data-stu-id="7580e-253">**7 days**</span></span>
- <span data-ttu-id="7580e-254">**15 日**</span><span class="sxs-lookup"><span data-stu-id="7580e-254">**15 days**</span></span>
- <span data-ttu-id="7580e-255">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="7580e-255">**30 days**</span></span>

<span data-ttu-id="7580e-256">[詳細を使 **える] をクリックすると、** 次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="7580e-257">**フィッシング メール**: この選択を行すると、脅威保護 [状態レポートに移動します](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="7580e-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="7580e-258">**メール内のマルウェア**: この選択では、脅威保護状態 [レポートに移動します](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="7580e-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="7580e-259">**スパム検出**: この選択によって、スパム検出 [レポートに回されます](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="7580e-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="7580e-260">**エッジブロックされたスパム**: この選択によって、スパム検出 [レポートに使用されます](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="7580e-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="7580e-261">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="7580e-261">**Export**:</span></span>

<span data-ttu-id="7580e-262">詳細ビューの場合、エクスポートできるのは 1 日だけです。</span><span class="sxs-lookup"><span data-stu-id="7580e-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="7580e-263">そのため、7 日間データをエクスポートする場合、7 つの異なるエクスポート操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7580e-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="7580e-264">エクスポートされた各 .csv ファイルには、150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="7580e-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7580e-265">その日のデータに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="7580e-266">メールフロー ステータス レポートの種類のビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="7580e-267">メールフロー ステータス レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="7580e-268">[方向] タブを **クリック** すると、[種類] ビューの同じ既定 **フィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="7580e-269">グラフは方向の値によって **構成** されています。</span><span class="sxs-lookup"><span data-stu-id="7580e-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="7580e-270">これらのフィルターは、[フィルター] をクリック **するか、グラフの** 凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="7580e-271">種類ビューで使用するフィルター **と同** じフィルターが使われます。</span><span class="sxs-lookup"><span data-stu-id="7580e-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="7580e-272">データ テーブルには [種類] ビューと同じ情報 **が含** まれています。</span><span class="sxs-lookup"><span data-stu-id="7580e-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="7580e-273">[Choose **a category for more available** selections and behavior] は、[Type] ビューと同 **じ** です。</span><span class="sxs-lookup"><span data-stu-id="7580e-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="7580e-274">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="7580e-274">**Export**:</span></span>

<span data-ttu-id="7580e-275">詳細ビューの場合、エクスポートできるのは 1 日だけです。</span><span class="sxs-lookup"><span data-stu-id="7580e-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="7580e-276">そのため、7 日間データをエクスポートする場合、7 つの異なるエクスポート操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7580e-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="7580e-277">エクスポートされた各 .csv ファイルには、150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="7580e-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7580e-278">その日のデータに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="7580e-279">メールフロー ステータス レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="7580e-280">メール フローステータス レポートのファンネル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="7580e-281">[ **ファンネル] ビュー** には、組織内の Microsoft のメールの脅威保護機能により、受信および送信電子メールがどのようにフィルター処理されるかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="7580e-282">このレポートでは、メールの合計数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スパム対策、なりすみ保護がどのように影響するかなどの、構成されている脅威保護機能の影響に関する詳細が示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="7580e-283">[ファネ **ル] タブをクリックすると** 、既定では、このビューには、次のフィルターで構成されたグラフとデータ テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="7580e-284">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="7580e-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="7580e-285">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="7580e-285">**Direction**:</span></span>

  - <span data-ttu-id="7580e-286">**受信**</span><span class="sxs-lookup"><span data-stu-id="7580e-286">**Inbound**</span></span>
  - <span data-ttu-id="7580e-287">**送信**</span><span class="sxs-lookup"><span data-stu-id="7580e-287">**Outbound**</span></span>
  - <span data-ttu-id="7580e-288">**Intra-org:** このカウントはテナント内で送信されるメッセージの場合です。すなら、abc@domain.comは受信者に送信xyz@domain.com (受信と送信とは別に加算されます)。</span><span class="sxs-lookup"><span data-stu-id="7580e-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="7580e-289">集計ビューとデータ テーブル ビューでは 90 日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="7580e-290">[フィルター] を **クリック**した場合、グラフとデータ テーブルの両方にフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="7580e-291">このグラフには、以下の項目で整理されたメール数が示されています。</span><span class="sxs-lookup"><span data-stu-id="7580e-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="7580e-292">**電子メールの合計**</span><span class="sxs-lookup"><span data-stu-id="7580e-292">**Total email**</span></span>
- <span data-ttu-id="7580e-293">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="7580e-293">**Email after edge protection**</span></span>
- <span data-ttu-id="7580e-294">**マルウェア対策後の電子メール、ファイル評価、ファイルの種類のブロック**</span><span class="sxs-lookup"><span data-stu-id="7580e-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="7580e-295">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策のメール**</span><span class="sxs-lookup"><span data-stu-id="7580e-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="7580e-296">**スパム対策後のメール、バルク メール フィルター**</span><span class="sxs-lookup"><span data-stu-id="7580e-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="7580e-297">**ユーザーとドメイン偽装後の電子**<sup>メール 1</sup></span><span class="sxs-lookup"><span data-stu-id="7580e-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="7580e-298">**ファイルと URL に関する 1 つ後の**<sup>メール</sup></span><span class="sxs-lookup"><span data-stu-id="7580e-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="7580e-299">**配信後保護の後に開始されたメール (URL クリック タイム保護)**</span><span class="sxs-lookup"><span data-stu-id="7580e-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="7580e-300"><sup>1</sup> Office 365 ATP のみ</span><span class="sxs-lookup"><span data-stu-id="7580e-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="7580e-301">EOP または ATP でフィルター処理された電子メールを個別に表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7580e-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="7580e-302">データ テーブルには、次の情報が格納されます (日付の順番に示されています)。</span><span class="sxs-lookup"><span data-stu-id="7580e-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="7580e-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="7580e-303">**Date**</span></span>
- <span data-ttu-id="7580e-304">**電子メールの合計**</span><span class="sxs-lookup"><span data-stu-id="7580e-304">**Total email**</span></span>
- <span data-ttu-id="7580e-305">**エッジの保護**</span><span class="sxs-lookup"><span data-stu-id="7580e-305">**Edge protection**</span></span>
- <span data-ttu-id="7580e-306">**マルウェア対策、ファイルの評価、ファイルの種類のブロック**</span><span class="sxs-lookup"><span data-stu-id="7580e-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="7580e-307">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策**</span><span class="sxs-lookup"><span data-stu-id="7580e-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="7580e-308">**スパム対策、バルク メール フィルター**</span><span class="sxs-lookup"><span data-stu-id="7580e-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="7580e-309">**ユーザーとドメインの偽装 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="7580e-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="7580e-310">**ファイルと URL のデトネーション (ATP)**</span><span class="sxs-lookup"><span data-stu-id="7580e-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="7580e-311">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="7580e-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="7580e-312">データ テーブル内の行を選択すると、電子メールカウントのその他の詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="7580e-313">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="7580e-313">**Export**:</span></span>

<span data-ttu-id="7580e-314">[オプション] の **[エクスポート\*\*\*\*] を**クリックした後は、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="7580e-315">**概要 (最近 90 日間のデータを使用)**</span><span class="sxs-lookup"><span data-stu-id="7580e-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="7580e-316">**詳細 (最近 30 日間のデータ)**</span><span class="sxs-lookup"><span data-stu-id="7580e-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="7580e-317">日付 **で**範囲を選択し、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="7580e-318">現在のフィルターのデータは、.csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="7580e-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="7580e-319">エクスポートされた各 .csv ファイルには、150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="7580e-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7580e-320">データに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="7580e-321">メール フローステータス レポートのファンネル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="7580e-322">メールフロー ステータス レポートのテクニカル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="7580e-323">技術 **ビューは** 、ファネル **ビューと似** ており、構成されている脅威保護機能の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="7580e-324">この図では、脅威保護の各段階でのメッセージの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="7580e-325">[Tech **View] タブを** クリックすると、既定では、このビューには、次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7580e-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="7580e-326">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="7580e-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="7580e-327">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="7580e-327">**Direction**:</span></span>

  - <span data-ttu-id="7580e-328">**受信**</span><span class="sxs-lookup"><span data-stu-id="7580e-328">**Inbound**</span></span>
  - <span data-ttu-id="7580e-329">**送信**</span><span class="sxs-lookup"><span data-stu-id="7580e-329">**Outbound**</span></span>
  - <span data-ttu-id="7580e-330">**Intra-org:** このカウントはテナント内のメッセージの数です</span><span class="sxs-lookup"><span data-stu-id="7580e-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="7580e-331">送信者abc@domain.com送信者が受信者への送信xyz@domain.com (受信と送信とは別に含まれます)</span><span class="sxs-lookup"><span data-stu-id="7580e-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="7580e-332">集計ビューとデータ テーブル ビューでは 90 日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="7580e-333">[フィルター] を **クリック**した場合、グラフとデータ テーブルの両方にフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="7580e-334">このグラフには、次のカテゴリ分類に整理されたメッセージが示されています。</span><span class="sxs-lookup"><span data-stu-id="7580e-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="7580e-335">**電子メールの合計**</span><span class="sxs-lookup"><span data-stu-id="7580e-335">**Total email**</span></span>
- <span data-ttu-id="7580e-336">**エッジの許可、エッジフィルター**</span><span class="sxs-lookup"><span data-stu-id="7580e-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="7580e-337">**マルウェア、安全な添付ファイルの検出 (ATP)、マルウェア対策エンジンの検出、ルール ブロック**</span><span class="sxs-lookup"><span data-stu-id="7580e-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="7580e-338">**フィッシング、DMARC 障害、偽装検出、なりすみ検出、フィッシング検出**</span><span class="sxs-lookup"><span data-stu-id="7580e-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="7580e-339">**URL のデトン留トによる検出なし、URL デトネーション検出 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="7580e-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="7580e-340">**スパム未使用、スパム**</span><span class="sxs-lookup"><span data-stu-id="7580e-340">**Not spam, spam**</span></span>
- <span data-ttu-id="7580e-341">**悪意のある非悪意のあるメール、安全なリンクの検出 (ATP)、ZAP**</span><span class="sxs-lookup"><span data-stu-id="7580e-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="7580e-342">グラフ内の各カテゴリにユーザーを重とすると、そのカテゴリのメッセージ数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="7580e-343">データ テーブルには、次の情報が格納されます (日付の順番に示されています)。</span><span class="sxs-lookup"><span data-stu-id="7580e-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="7580e-344">**Date**</span><span class="sxs-lookup"><span data-stu-id="7580e-344">**Date**</span></span>
- <span data-ttu-id="7580e-345">**電子メールの合計**</span><span class="sxs-lookup"><span data-stu-id="7580e-345">**Total email**</span></span>
- <span data-ttu-id="7580e-346">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="7580e-346">**Edge filtered**</span></span>
- <span data-ttu-id="7580e-347">**マルウェア対策エンジン、安全な添付ファイル、ルールのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="7580e-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="7580e-348">**DMARC、偽装、スプーフィング、フィッシング フィルター処理**</span><span class="sxs-lookup"><span data-stu-id="7580e-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="7580e-349">**URL の特定検出**</span><span class="sxs-lookup"><span data-stu-id="7580e-349">**URL detonation detection**</span></span>
- <span data-ttu-id="7580e-350">**スパム対策フィルター処理**</span><span class="sxs-lookup"><span data-stu-id="7580e-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="7580e-351">**ZAP の削除**</span><span class="sxs-lookup"><span data-stu-id="7580e-351">**ZAP removed**</span></span>
- <span data-ttu-id="7580e-352">**安全なリンクによる検出**</span><span class="sxs-lookup"><span data-stu-id="7580e-352">**Detection by safe links**</span></span>

<span data-ttu-id="7580e-353">データ テーブル内の行を選択すると、電子メールカウントのその他の詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="7580e-354">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="7580e-354">**Export**:</span></span>

<span data-ttu-id="7580e-355">[エクスポート] **の**[オプション **] にある** [エクスポート] をクリックすると、次の値のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="7580e-356">**概要 (最近 90 日間のデータを使用)**</span><span class="sxs-lookup"><span data-stu-id="7580e-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="7580e-357">**詳細 (最近 30 日間のデータ)**</span><span class="sxs-lookup"><span data-stu-id="7580e-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="7580e-358">日付 **で**範囲を選択し、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="7580e-359">現在のフィルターのデータは、.csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="7580e-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="7580e-360">エクスポートされた各 .csv ファイルには、150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="7580e-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7580e-361">データに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="7580e-362">メールフロー ステータス レポートのテクニカル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="7580e-363">送受信メール レポート</span><span class="sxs-lookup"><span data-stu-id="7580e-363">Sent and received email report</span></span>

<span data-ttu-id="7580e-364">送信 **および受信メール レポート** は、"good" と識別されるスパムの検出、マルウェア、メールなど、送受信メールに関する情報を表示するスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="7580e-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="7580e-365">このレポートとメール フロー ステータス レポートの [違い](#mailflow-status-report) は、このレポートにはエッジ保護によってブロックされたメッセージに関するデータが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7580e-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="7580e-366">集計ビューとレポートの詳細ビューでは、90 日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="7580e-367">レポートを表示するには、セキュリティ コンプライアンス センター [でセキュリティ&開き、[レポート](https://protection.office.com)ダッシュボード **]** に \> **移動し、[** 送信済み **および受信メール] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="7580e-368">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="7580e-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![レポート ダッシュボードで送受信したメール ウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="7580e-370">送信済みおよび受信した電子メール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="7580e-371">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="7580e-372">**[種類] :[種類]:** グラフには、利用可能なすべてのカテゴリが示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="7580e-373">**合計**</span><span class="sxs-lookup"><span data-stu-id="7580e-373">**Total**</span></span>
  - <span data-ttu-id="7580e-374">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="7580e-374">**Good mail**</span></span>
  - <span data-ttu-id="7580e-375">**マルウェア (マルウェア対策)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="7580e-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="7580e-376">**スパム検出**</span><span class="sxs-lookup"><span data-stu-id="7580e-376">**Spam detections**</span></span>
  - <span data-ttu-id="7580e-377">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="7580e-377">**Rule messages**</span></span>
  - <span data-ttu-id="7580e-378">**高度なマルウェア** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="7580e-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="7580e-379">グラフで 1 日 (データ ポイント) にポインターを移動すると、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送受信した電子メール レポートの種類ビュー](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="7580e-381">**下向き: グラフには**集**計、受信\*\*\*\*、および送信**データ**が示**されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="7580e-382">グラフで 1 日 (データ ポイント) にポインターを移動すると、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信済みおよび受信したメール レポートでの方向ビュー](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="7580e-384">**ドリルダウン** \>**マルウェア (マルウェア対策)**: この選択では、電子メール レポート[内のマルウェア検出に対して使用できます](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="7580e-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="7580e-385">**ドリルダウン** \>**スパムの検出数)**: この選択によって、スパム検出[レポートに回されます](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="7580e-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="7580e-386">レポート ビューで **[フィルター** ] をクリックした場合は、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="7580e-387">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="7580e-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="7580e-388">Direction の値</span><span class="sxs-lookup"><span data-stu-id="7580e-388">Direction values</span></span>
- <span data-ttu-id="7580e-389">型の値</span><span class="sxs-lookup"><span data-stu-id="7580e-389">Type values</span></span>

<span data-ttu-id="7580e-390">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7580e-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="7580e-391">送信済みおよび受信したメール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="7580e-392">[方法] **方向または下方向への割** り **当ての各ビューで [** 詳細の **表示]** テーブルをクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="7580e-393">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="7580e-393">**Date (UTC)**</span></span>
- <span data-ttu-id="7580e-394">**型**</span><span class="sxs-lookup"><span data-stu-id="7580e-394">**Type**</span></span>
- <span data-ttu-id="7580e-395">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="7580e-395">**Direction**</span></span>
- <span data-ttu-id="7580e-396">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="7580e-396">**Message count**</span></span>

<span data-ttu-id="7580e-397">詳細テーブル ビュー **で [** フィルター] をクリックした場合、結果は次のフィルターを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="7580e-398">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="7580e-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="7580e-399">Direction の値</span><span class="sxs-lookup"><span data-stu-id="7580e-399">Direction values</span></span>
- <span data-ttu-id="7580e-400">型の値</span><span class="sxs-lookup"><span data-stu-id="7580e-400">Type values</span></span>

<span data-ttu-id="7580e-401">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7580e-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="7580e-402">上位送信者と受信者レポート</span><span class="sxs-lookup"><span data-stu-id="7580e-402">Top senders and recipients report</span></span>

<span data-ttu-id="7580e-403">上 **位送信者と受信者のレポート** は、上位のメールの送信者と受信者を示すパースグラフです。</span><span class="sxs-lookup"><span data-stu-id="7580e-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="7580e-404">レポートを表示するには、セキュリティ センターの [セキュリティ &開き、[](https://protection.office.com)レポート ダッシュボード **]** に \> **移動して** [上 **位送信者と受信者] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7580e-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="7580e-405">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="7580e-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![レポート ダッシュボードの上位送信者と受信者ウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="7580e-407">上位送信者と受信者レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="7580e-408">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7580e-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="7580e-409">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="7580e-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="7580e-410">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="7580e-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="7580e-411">**上位のスパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="7580e-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="7580e-412">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="7580e-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="7580e-413">**データの表示 \> 上位マルウェア受信者 (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="7580e-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="7580e-414">円グラフの合(合関) は、これらの選択内容に基づいて変化します。</span><span class="sxs-lookup"><span data-stu-id="7580e-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="7580e-415">円グラフのウェイプの上にポイントすると、送信または受信したメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7580e-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="7580e-416">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="7580e-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![上位送信者と受信者レポートのレポート ビューにある円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="7580e-418">上位送信者と受信者レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="7580e-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="7580e-419">[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。</span><span class="sxs-lookup"><span data-stu-id="7580e-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7580e-420">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="7580e-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="7580e-421">**上位のメール送信者**</span><span class="sxs-lookup"><span data-stu-id="7580e-421">**Top mail senders**</span></span>
  - <span data-ttu-id="7580e-422">**Count**</span><span class="sxs-lookup"><span data-stu-id="7580e-422">**Count**</span></span>

- <span data-ttu-id="7580e-423">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="7580e-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="7580e-424">**[上位メール受信者]**</span><span class="sxs-lookup"><span data-stu-id="7580e-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="7580e-425">**Count**</span><span class="sxs-lookup"><span data-stu-id="7580e-425">**Count**</span></span>

- <span data-ttu-id="7580e-426">**上位のスパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="7580e-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="7580e-427">**スパムの上位受信者**</span><span class="sxs-lookup"><span data-stu-id="7580e-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="7580e-428">**Count**</span><span class="sxs-lookup"><span data-stu-id="7580e-428">**Count**</span></span>

- <span data-ttu-id="7580e-429">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="7580e-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="7580e-430">**[上位マルウェア受信者]**</span><span class="sxs-lookup"><span data-stu-id="7580e-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="7580e-431">**Count**</span><span class="sxs-lookup"><span data-stu-id="7580e-431">**Count**</span></span>

- <span data-ttu-id="7580e-432">**データの表示 \> 上位マルウェア受信者 (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="7580e-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="7580e-433">**上位マルウェア受信者 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="7580e-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="7580e-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="7580e-434">**Count**</span></span>

<span data-ttu-id="7580e-435">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="7580e-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="7580e-436">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7580e-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="7580e-437">これらのレポートを表示するにはどのようなアクセス許可が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="7580e-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="7580e-438">レポートを表示して使用するには、セキュリティ保護センターおよび Exchange Online で指定された &役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="7580e-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="7580e-439">コンプライアンス センターで&役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7580e-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="7580e-440">-組織の管理 - セキュリティ管理者 [(Azure Active Directory](https://aad.portal.azure.com) 管理センター -Security Reader でも実行できます)</span><span class="sxs-lookup"><span data-stu-id="7580e-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="7580e-441">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7580e-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="7580e-442">Exchange Online で、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7580e-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="7580e-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span><span class="sxs-lookup"><span data-stu-id="7580e-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="7580e-444">詳細については、「Exchange [Online のアクセス許可」と「Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) [の役割グループの管理」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="7580e-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7580e-445">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7580e-445">Related topics</span></span>

[<span data-ttu-id="7580e-446">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="7580e-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="7580e-447">セキュリティとコンプライアンス センターのメッセージ追跡の分析情報</span><span class="sxs-lookup"><span data-stu-id="7580e-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="7580e-448">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="7580e-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="7580e-449">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="7580e-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
