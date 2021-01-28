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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ/コンプライアンス センターのレポート ダッシュボードで利用できるメール フロー レポート&確認できます。
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e69085d1fad845ab519f2590b0527316463373a7
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029800"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="2b2ea-103">セキュリティ/コンプライアンス センターの [レポート] ダッシュボードでメール フロー &表示する</span><span class="sxs-lookup"><span data-stu-id="2b2ea-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2b2ea-104">セキュリティ & コンプライアンス センターのメール フロー[](mail-flow-insights-v2.md)ダッシュボードで使用できるメール フロー レポートに加えて、Microsoft 365 組織の監視に役立つさまざまな追加のメール フロー レポートをレポート ダッシュボードで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="2b2ea-105">必要なアクセス許可 [がある](#what-permissions-are-needed-to-view-these-reports)場合は、レポート ダッシュボードに移動して、[](https://protection.office.com)セキュリティ/コンプライアンス センター&レポート **を表示** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="2b2ea-106">レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ/コンプライアンス センター&ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="2b2ea-108">コネクタ レポート</span><span class="sxs-lookup"><span data-stu-id="2b2ea-108">Connector report</span></span>

<span data-ttu-id="2b2ea-109">コネクタ **レポートには**、組織用に構成 [](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)されている受信コネクタと送信コネクタでのメール フロー アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="2b2ea-110">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&レポート ダッシュボード **に移動し**、[コネクタ] \> レポート **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="2b2ea-111">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![レポート ダッシュボードのコネクタ レポート ウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="2b2ea-113">コネクタ レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-113">Report view for the Connector report</span></span>

<span data-ttu-id="2b2ea-114">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="2b2ea-115">**データの表示方法: [メール フロー**]: このグラフは、次の方法で編成された受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="2b2ea-116">**合計**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-116">**Total**</span></span>
  - <span data-ttu-id="2b2ea-117">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="2b2ea-118">**コネクタのないインターネットへ**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="2b2ea-119">構成した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="2b2ea-120">グラフ内のデータを分離するには、コントロールのデータの表示を使用して、これらのオプションまたはすべてのメール フロー **のいずれかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![コネクタ レポートでメール フロー別にデータを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="2b2ea-122">**データの表示:TLS 使用状況**: このグラフは、メール フローでのトランスポート層セキュリティ (TLS) バージョンの使用状況の割合を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="2b2ea-123">グラフ内のデータを分離するには、コントロールの [ **データ** の表示] を使用して、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="2b2ea-124">**すべてのメール フロー**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-124">**All mail flow**</span></span>
  - <span data-ttu-id="2b2ea-125">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="2b2ea-126">**コネクタのないインターネットへ**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="2b2ea-127">構成した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-127">A specific connector that you've configured.</span></span>

  ![コネクタ レポートで TLS 使用法別にデータを表示する](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="2b2ea-129">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="2b2ea-130">コネクタ レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-130">Details table view for the Connector report</span></span>

<span data-ttu-id="2b2ea-131">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="2b2ea-132">**日付**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-132">**Date**</span></span>
- <span data-ttu-id="2b2ea-133">**コネクタの方向と名前**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-133">**Connector direction and name**</span></span>
- <span data-ttu-id="2b2ea-134">**コネクタの種類**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-134">**Connector type**</span></span>
- <span data-ttu-id="2b2ea-135">**強制 TLS?**: 値 **は True** または **False です**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="2b2ea-136">**TLS なし** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="2b2ea-137">**TLS 1.0** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="2b2ea-138">**TLS 1.1** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="2b2ea-139">**TLS 1.2** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="2b2ea-140">**Volume**: メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="2b2ea-141">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2b2ea-142">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="2b2ea-143">Exchange トランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="2b2ea-143">Exchange transport rule report</span></span>

<span data-ttu-id="2b2ea-144">**Exchange トランスポート ルール レポートは**、組織内の受信および送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="2b2ea-145">レポートを表示するには、セキュリティ/[](https://protection.office.com)コンプライアンス センター&開き、[**レポート** ダッシュボード] に移動し \> 、[Exchange トランスポート ルール **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="2b2ea-146">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![レポート ダッシュボードの Exchange トランスポート ルール ウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="2b2ea-148">Exchange トランスポート ルール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="2b2ea-149">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="2b2ea-150">**データの表示方法: Exchange トランスポート ルール** \>**[Break down by: Direction]**(方向):このグラフには、トランスポート ルールの影響を受けた受信メッセージと送信メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="2b2ea-151">**データの表示方法: Exchange トランスポート ルール** \>**分類: 重大度 :** このグラフには、重大度の高と中の重大度、および重要度の低の **メッセージの数が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="2b2ea-152">ルールのアクションとして重大度レベルを設定します **(この** ルールを重大度レベルまたは _SetAuditSeverity で監査します_)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="2b2ea-153">詳細については [、「Exchange Online でのメール フロー ルールのアクション」を参照してください](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="2b2ea-154">**データの表示方法: DLP Exchange トランスポート ルール** \>**[ブレークダウンバイ: 方向**]: このグラフは、データ損失防止 (DLP) トランスポート ルールの影響を受けた受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="2b2ea-155">次のオプションをオンにすることで、グラフをさらに調整できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="2b2ea-156">**データの表示: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="2b2ea-157">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="2b2ea-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="2b2ea-159">**データの表示方法: DLP Exchange トランスポート ルール** \>**[Break down by: Direction**]  (方向): このビューには、DLPトランスポート ルールの影響を受けた重大度の高いメッセージと中程度の重大度のメッセージの数が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="2b2ea-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="2b2ea-160">次のオプションをオンにすることで、グラフをさらに調整できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="2b2ea-161">**データの表示: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="2b2ea-162">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="2b2ea-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="2b2ea-164">レポート ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="2b2ea-165">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="2b2ea-166">方向の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-166">Direction values</span></span>
- <span data-ttu-id="2b2ea-167">重要度の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-167">Severity values</span></span>

![Exchange トランスポート ルール レポートのレポート ビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="2b2ea-169">Exchange トランスポート ルール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="2b2ea-170">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2b2ea-171">**データの表示方法: Exchange トランスポート ルール**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="2b2ea-172">**日付**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-172">**Date**</span></span>
  - <span data-ttu-id="2b2ea-173">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-173">**Transport rule**</span></span>
  - <span data-ttu-id="2b2ea-174">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-174">**Subject**</span></span>
  - <span data-ttu-id="2b2ea-175">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-175">**Sender address**</span></span>
  - <span data-ttu-id="2b2ea-176">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-176">**Recipient address**</span></span>
  - <span data-ttu-id="2b2ea-177">**重大度**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-177">**Severity**</span></span>
  - <span data-ttu-id="2b2ea-178">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-178">**Direction**</span></span>

- <span data-ttu-id="2b2ea-179">**データの表示方法: DLP Exchange トランスポート ルール**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="2b2ea-180">**日付**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-180">**Date**</span></span>
  - <span data-ttu-id="2b2ea-181">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-181">**DLP policy**</span></span>
  - <span data-ttu-id="2b2ea-182">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-182">**Transport rule**</span></span>
  - <span data-ttu-id="2b2ea-183">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-183">**Subject**</span></span>
  - <span data-ttu-id="2b2ea-184">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-184">**Sender address**</span></span>
  - <span data-ttu-id="2b2ea-185">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-185">**Recipient address**</span></span>
  - <span data-ttu-id="2b2ea-186">**重大度**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-186">**Severity**</span></span>
  - <span data-ttu-id="2b2ea-187">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-187">**Direction**</span></span>

<span data-ttu-id="2b2ea-188">詳細テーブル ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2b2ea-189">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="2b2ea-190">方向の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-190">Direction values</span></span>
- <span data-ttu-id="2b2ea-191">重要度の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-191">Severity values</span></span>

<span data-ttu-id="2b2ea-192">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="2b2ea-193">転送レポート</span><span class="sxs-lookup"><span data-stu-id="2b2ea-193">Forwarding report</span></span>

<span data-ttu-id="2b2ea-194">転送 **レポートには、Exchange** Online メールボックスから外部ドメインに組織が自動的に転送したメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="2b2ea-195">転送されたメッセージは、セキュリティまたはコンプライアンスのリスクを引き起し、アカウントが侵害された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="2b2ea-196">レポートを表示するには、セキュリティ/コンプライアンス センターを [&レポート](https://protection.office.com)ダッシュボードに移動し、[転送 \> ] レポート **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="2b2ea-197">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![レポート ダッシュボードの転送レポート ウィジェット](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="2b2ea-199">転送レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="2b2ea-200">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2b2ea-201">**転送方法のデータを表示する**: 次のメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="2b2ea-202">**トランスポート ルール**: メール フロー ルール [とも呼ばれる](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="2b2ea-203">**メールボックス ルール**: 受信トレイ ルール [とも呼ばれる](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![転送レポートの転送方法ビュー](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="2b2ea-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span><span class="sxs-lookup"><span data-stu-id="2b2ea-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![転送レポートの [ドメインの転送] ビュー](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="2b2ea-207">**Show data for: Forwarders**: The following forwarders are shown:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="2b2ea-208">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-208">**Transport rule**</span></span>
  - <span data-ttu-id="2b2ea-209">転送受信トレイ ルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![転送レポートのフォワーダー ビュー](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="2b2ea-211">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="2b2ea-212">転送レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="2b2ea-213">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="2b2ea-214">**フォワーダー**: トランスポート ルール **の値、** または転送受信トレイ ルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="2b2ea-215">**転送の種類**: メールボックス ルール **またはトランスポート ルール\*\*\*\*の値**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="2b2ea-216">**受信者名**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-216">**Recipient name**</span></span>
- <span data-ttu-id="2b2ea-217">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-217">**Recipient domain**</span></span>
- <span data-ttu-id="2b2ea-218">**詳細**: これは、メール フロー ルールの GUID 値、または受信トレイ ルールの RuleIdentity 値です。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="2b2ea-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-219">**Count**</span></span>
- <span data-ttu-id="2b2ea-220">**最初の転送日**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-220">**First forward date**</span></span>

<span data-ttu-id="2b2ea-221">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2b2ea-222">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="2b2ea-223">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="2b2ea-223">Mailflow status report</span></span>

<span data-ttu-id="2b2ea-224">Mailflow **ステータス レポートは**、送信 [](#sent-and-received-email-report)済みおよび受信した電子メール レポートに似ていますが、エッジで許可またはブロックされた電子メールに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="2b2ea-225">これは、エッジ保護情報を含む唯一のレポートであり、Exchange Online Protection (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量のみを示します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="2b2ea-226">メッセージが 5 人の受信者に送信された場合、1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされるという点を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="2b2ea-227">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&ダッシュボードに移動し、[ \> **メールフロー] ステータス レポートを選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="2b2ea-228">メール フローの状態レポートに **直接移動するには、開** きます <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![レポート ダッシュボードのメールフロー状態レポート ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="2b2ea-230">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="2b2ea-231">レポートを開いた場合、既定 **では [種類** ] タブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="2b2ea-232">既定では、このビューには、次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2b2ea-233">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="2b2ea-234">**方向**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-234">**Direction**:</span></span>

  - <span data-ttu-id="2b2ea-235">**受信**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-235">**Inbound**</span></span>
  - <span data-ttu-id="2b2ea-236">**送信**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-236">**Outbound**</span></span>
  - <span data-ttu-id="2b2ea-237">**組織内**: この数は、テナント内のメッセージ (つまり、</span><span class="sxs-lookup"><span data-stu-id="2b2ea-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2b2ea-238">送信者abc@domain.com受信者に送信xyz@domain.com (受信および送信 **とは別に\*\*\*\*カウントされます**)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="2b2ea-239">**型**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-239">**Type**:</span></span>

  - <span data-ttu-id="2b2ea-240">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-240">**Good mail**</span></span>
  - <span data-ttu-id="2b2ea-241">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-241">**Malware**</span></span>
  - <span data-ttu-id="2b2ea-242">**スパム**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-242">**Spam**</span></span>
  - <span data-ttu-id="2b2ea-243">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-243">**Edge protection**</span></span>
  - <span data-ttu-id="2b2ea-244">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-244">**Rule messages**</span></span>
  - <span data-ttu-id="2b2ea-245">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-245">**Phishing email**</span></span>

<span data-ttu-id="2b2ea-246">グラフは Type 値で **構成** されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="2b2ea-247">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="2b2ea-248">データ テーブルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-248">The data table contains the following information:</span></span>

- <span data-ttu-id="2b2ea-249">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-249">**Direction**</span></span>
- <span data-ttu-id="2b2ea-250">**型**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-250">**Type**</span></span>
- <span data-ttu-id="2b2ea-251">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-251">**24 hours**</span></span>
- <span data-ttu-id="2b2ea-252">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-252">**3 days**</span></span>
- <span data-ttu-id="2b2ea-253">**7 日**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-253">**7 days**</span></span>
- <span data-ttu-id="2b2ea-254">**15 日**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-254">**15 days**</span></span>
- <span data-ttu-id="2b2ea-255">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-255">**30 days**</span></span>

<span data-ttu-id="2b2ea-256">[カテゴリの **選択] をクリックして詳細を表示する** 場合は、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="2b2ea-257">**フィッシング メール**: この選択によって、脅威保護の [状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2b2ea-258">**電子メール内の** マルウェア : この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2b2ea-259">**スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="2b2ea-260">**エッジでブロックされたスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="2b2ea-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-261">**Export**:</span></span>

<span data-ttu-id="2b2ea-262">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2b2ea-263">したがって、データを 7 日間エクスポートする場合は、7 つの異なるエクスポート操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2b2ea-264">エクスポートされる .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2b2ea-265">その日のデータに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="2b2ea-266">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="2b2ea-267">Mailflow ステータス レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="2b2ea-268">[方向] タブ **をクリックすると** 、[種類] ビューの同じ **既定のフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="2b2ea-269">グラフは方向の値で **構成** されています。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="2b2ea-270">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="2b2ea-271">Type ビューの同 **じフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="2b2ea-272">データ テーブルには、型ビューと同じ情報 **が含** まれる。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="2b2ea-273">[ **カテゴリの選択] で使用可能な選択と** 動作の詳細については、[種類] ビューと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="2b2ea-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-274">**Export**:</span></span>

<span data-ttu-id="2b2ea-275">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2b2ea-276">したがって、データを 7 日間エクスポートする場合は、7 つの異なるエクスポート操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2b2ea-277">エクスポートする .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2b2ea-278">その日のデータに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="2b2ea-279">メールフローステータス レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="2b2ea-280">メールフローステータス レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="2b2ea-281">じょう **ごビュー** には、Microsoft のメール脅威防止機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="2b2ea-282">この記事では、メールの総数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策などの構成済みの脅威保護機能が、このカウントにどのような影響を与えるのかについて詳しく情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="2b2ea-283">[ **じょう** ご] タブをクリックすると、既定では、このビューには次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2b2ea-284">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2b2ea-285">**方向**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-285">**Direction**:</span></span>

  - <span data-ttu-id="2b2ea-286">**受信**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-286">**Inbound**</span></span>
  - <span data-ttu-id="2b2ea-287">**送信**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-287">**Outbound**</span></span>
  - <span data-ttu-id="2b2ea-288">**組織内**: このカウントは、テナント内で送信されたメッセージに対して行います。つまり、送信者はabc@domain.com受信者に送信xyz@domain.com (受信と送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="2b2ea-289">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2b2ea-290">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2b2ea-291">このグラフは、次の方法で整理されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="2b2ea-292">**Total email**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-292">**Total email**</span></span>
- <span data-ttu-id="2b2ea-293">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-293">**Email after edge protection**</span></span>
- <span data-ttu-id="2b2ea-294">**マルウェア対策、ファイル評価、ファイルの種類ブロック後のメール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="2b2ea-295">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策の後のメール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="2b2ea-296">**スパム対策、バルク メール フィルター後のメール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="2b2ea-297">**ユーザーとドメインの偽装後の電子メール**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2b2ea-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="2b2ea-298">**ファイルおよび URL 分析後の**<sup>電子メール 1</sup></span><span class="sxs-lookup"><span data-stu-id="2b2ea-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="2b2ea-299">**配信後の保護後に良性として検出された電子メール (URL クリック時間保護)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="2b2ea-300"><sup>365</sup> の場合のみ 1 Office Defender</span><span class="sxs-lookup"><span data-stu-id="2b2ea-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="2b2ea-301">EOP または Defender でフィルター処理された Office 365 を個別に表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="2b2ea-302">データ テーブルには、降順で示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2b2ea-303">**日付**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-303">**Date**</span></span>
- <span data-ttu-id="2b2ea-304">**Total email**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-304">**Total email**</span></span>
- <span data-ttu-id="2b2ea-305">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-305">**Edge protection**</span></span>
- <span data-ttu-id="2b2ea-306">**マルウェア対策、ファイル評価、ファイルの種類のブロック**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="2b2ea-307">**ファイル評価**: 他の Microsoft ユーザーが添付ファイルを識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="2b2ea-308">**ファイルの種類の** ブロック : メッセージで識別された悪意のあるファイルの種類のためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="2b2ea-309">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="2b2ea-310">**URL 評価**: 他の Microsoft ユーザーが URL を識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="2b2ea-311">**ブランド偽装**: 既知のブランド偽装送信者からのメッセージのためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="2b2ea-312">**スプーフィン** グ対策 : 受信者が属するドメインを偽装しようとするメッセージ、またはメッセージ送信者が所有していないドメインが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="2b2ea-313">**スパム対策、バルク メール フィルター:**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="2b2ea-314">**バルク メール フィルター**: 受信者にバルク メールを配信しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="2b2ea-315">**ユーザーとドメインの偽装 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2b2ea-316">**ユーザー偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているユーザー (メッセージ送信者) を偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="2b2ea-317">**ドメイン偽装**: フィッシング詐欺対策ポリシーの偽装保護設定で定義されているドメインを偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="2b2ea-318">**ファイルと URL の分析 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2b2ea-319">**ファイル分析**: 安全な添付ファイル ポリシーによってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="2b2ea-320">**URL デトレーション**: 安全なリンク ポリシーによってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="2b2ea-321">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**: ZAP はゼロアワー自動消去を示します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="2b2ea-322">データ テーブル内の行を選択すると、メールカウントの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="2b2ea-323">**Export**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-323">**Export**:</span></span>

<span data-ttu-id="2b2ea-324">[オプション] で **[エクスポート\*\*\*\*] をクリック** すると、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="2b2ea-325">**概要 (最大 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2b2ea-326">**詳細 (最大 30 日間のデータ)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2b2ea-327">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2b2ea-328">現在のフィルターのデータが .csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2b2ea-329">エクスポートされる .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2b2ea-330">データに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="2b2ea-331">メールフローステータス レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="2b2ea-332">メールフローの状態レポートのテクニカル ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="2b2ea-333">Tech **ビューは** じょうごビューに **似ています。** 構成済みの脅威保護機能に関するより詳細な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="2b2ea-334">グラフから、脅威保護の異なる段階でのメッセージの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="2b2ea-335">[技術表示]タブをクリックすると、既定では、このビューには次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2b2ea-336">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2b2ea-337">**方向**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-337">**Direction**:</span></span>

  - <span data-ttu-id="2b2ea-338">**受信**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-338">**Inbound**</span></span>
  - <span data-ttu-id="2b2ea-339">**送信**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-339">**Outbound**</span></span>
  - <span data-ttu-id="2b2ea-340">**組織内**: この数は、テナント内のメッセージ (つまり、</span><span class="sxs-lookup"><span data-stu-id="2b2ea-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2b2ea-341">送信者abc@domain.com受信者に送信するxyz@domain.com (受信と送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="2b2ea-342">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2b2ea-343">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2b2ea-344">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="2b2ea-345">**Total email**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-345">**Total email**</span></span>
- <span data-ttu-id="2b2ea-346">**エッジの許可** と **フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="2b2ea-347">**マルウェアではない、\*\*\*\*安全な添付ファイルの検出**、 <sup>\*</sup> **マルウェア対策エンジンの検出**、**およびルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="2b2ea-348">**Not phish**, **DMARC failure**, **Impersonation detection**, Spoof **detection**, and **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="2b2ea-349">**URL デトレーションと URL デトレーション** 検出 **による検出なし**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2b2ea-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="2b2ea-350">**スパムおよびスパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="2b2ea-351">**悪意のあるメール以外、\*\*\*\*安全なリンクの検出** <sup>\*</sup> **、ZAP**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="2b2ea-352"><sup>\*</sup> Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2b2ea-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="2b2ea-353">グラフのカテゴリにカーソルを合わせると、そのカテゴリ内のメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="2b2ea-354">データ テーブルには、降順で示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2b2ea-355">**日付**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-355">**Date**</span></span>
- <span data-ttu-id="2b2ea-356">**Total email**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-356">**Total email**</span></span>
- <span data-ttu-id="2b2ea-357">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-357">**Edge filtered**</span></span>
- <span data-ttu-id="2b2ea-358">**マルウェア対策エンジン、安全な添付ファイル、フィルター処理されたルール**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="2b2ea-359">**フィルター処理されたルール**: メール フロー ルール (トランスポート ルールとも呼ばれる) が原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="2b2ea-360">**DMARC, 偽装, スプーフィング, フィッシング フィルター:**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="2b2ea-361">**DMARC**: メッセージが DMARC 認証チェックに失敗した場合にフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="2b2ea-362">**URL デトレーション検出**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-362">**URL detonation detection**</span></span>
- <span data-ttu-id="2b2ea-363">**フィルター処理されたスパム対策**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="2b2ea-364">**ZAP の削除**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-364">**ZAP removed**</span></span>
- <span data-ttu-id="2b2ea-365">**安全なリンクによる検出**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="2b2ea-366">データ テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="2b2ea-367">**Export**:</span><span class="sxs-lookup"><span data-stu-id="2b2ea-367">**Export**:</span></span>

<span data-ttu-id="2b2ea-368">[エクスポート] **をクリック** すると、[オプション] **で** 次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="2b2ea-369">**概要 (最大 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2b2ea-370">**詳細 (最大 30 日間のデータ)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2b2ea-371">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2b2ea-372">現在のフィルターのデータは、.csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2b2ea-373">エクスポートする .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2b2ea-374">データに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="2b2ea-375">メールフローの状態レポートのテクニカル ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="2b2ea-376">送信および受信メール レポート</span><span class="sxs-lookup"><span data-stu-id="2b2ea-376">Sent and received email report</span></span>

<span data-ttu-id="2b2ea-377">送信 **メール レポートと** 受信メール レポートは、スパム検出、マルウェア、"良好" と識別された電子メールなど、受信および送信電子メールに関する情報を表示するスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="2b2ea-378">このレポートとメールフローステータス[](#mailflow-status-report)レポートの違いは、エッジ保護によってブロックされるメッセージに関するデータが含まれるという点です。メッセージが 5 人の受信者に送信された場合、1 つのメッセージとしてカウントされるという点を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="2b2ea-379">レポートの集計ビューと詳細ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="2b2ea-380">レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを&レポート ダッシュボードに移動し、[送信メールと受信メール \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="2b2ea-381">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![レポート ダッシュボードの送信メールウィジェットと受信メール ウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="2b2ea-383">送信および受信メール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="2b2ea-384">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2b2ea-385">**分類: 種類 :** グラフには、利用可能なすべてのカテゴリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="2b2ea-386">**合計**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-386">**Total**</span></span>
  - <span data-ttu-id="2b2ea-387">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-387">**Good mail**</span></span>
  - <span data-ttu-id="2b2ea-388">**マルウェア (マルウェア対策)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="2b2ea-389">**スパム検出**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-389">**Spam detections**</span></span>
  - <span data-ttu-id="2b2ea-390">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-390">**Rule messages**</span></span>
  - <span data-ttu-id="2b2ea-391">**高度なマルウェア** (Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="2b2ea-392">グラフ内の 1 日 (データ ポイント) の上にマウス ポインターを移動すると、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![[送信メールと受信メール] レポートの種類ビュー](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="2b2ea-394">**次の方法でブレーク ダウンします。方向**: グラフには、 **合計**、受信 **、** および **送信データが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="2b2ea-395">グラフ内の 1 日 (データ ポイント) の上にマウス ポインターを移動すると、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![[送信メールと受信メール] レポートの [方向] ビュー](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="2b2ea-397">**ドリルダウン** \>**マルウェア (マルウェア対策)**: この選択により、メール レポートの [マルウェア検出にアクセスします](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="2b2ea-398">**ドリルダウン** \>**スパム検出)**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="2b2ea-399">レポート ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2b2ea-400">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="2b2ea-401">方向の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-401">Direction values</span></span>
- <span data-ttu-id="2b2ea-402">型の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-402">Type values</span></span>

<span data-ttu-id="2b2ea-403">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="2b2ea-404">送信および受信メール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="2b2ea-405">[Break **down by:** Direction] (方向)**ビューまたは** **[Break down by: Direction]** (方向) ビューで [詳細の表示] テーブルをクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="2b2ea-406">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-406">**Date (UTC)**</span></span>
- <span data-ttu-id="2b2ea-407">**型**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-407">**Type**</span></span>
- <span data-ttu-id="2b2ea-408">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-408">**Direction**</span></span>
- <span data-ttu-id="2b2ea-409">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-409">**Message count**</span></span>

<span data-ttu-id="2b2ea-410">詳細テーブル ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2b2ea-411">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="2b2ea-412">方向の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-412">Direction values</span></span>
- <span data-ttu-id="2b2ea-413">型の値</span><span class="sxs-lookup"><span data-stu-id="2b2ea-413">Type values</span></span>

<span data-ttu-id="2b2ea-414">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="2b2ea-415">上位の送信者と受信者のレポート</span><span class="sxs-lookup"><span data-stu-id="2b2ea-415">Top senders and recipients report</span></span>

<span data-ttu-id="2b2ea-416">[ **上位の送信者と受信者** ] レポートは、上位のメールの送信者と受信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="2b2ea-417">レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを&レポート ダッシュボードに移動し、[上位の送信者と受信者 \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="2b2ea-418">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![レポート ダッシュボードの上位の送信者と受信者のウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="2b2ea-420">上位送信者と受信者レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="2b2ea-421">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2b2ea-422">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="2b2ea-423">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="2b2ea-424">**上位スパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="2b2ea-425">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="2b2ea-426">**上位マルウェア受信者 \> のデータを表示する (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="2b2ea-427">円グラフの構成は、これらの選択内容に基づいて変化します。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="2b2ea-428">円グラフでくさびの上にカーソルを合わせると、送信または受信したメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="2b2ea-429">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![上位の送信者と受信者レポートのレポート ビューの円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="2b2ea-431">上位送信者と受信者レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="2b2ea-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="2b2ea-432">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2b2ea-433">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="2b2ea-434">**上位メール送信者**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-434">**Top mail senders**</span></span>
  - <span data-ttu-id="2b2ea-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-435">**Count**</span></span>

- <span data-ttu-id="2b2ea-436">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="2b2ea-437">**上位メール受信者**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="2b2ea-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-438">**Count**</span></span>

- <span data-ttu-id="2b2ea-439">**上位スパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="2b2ea-440">**スパムの上位受信者**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="2b2ea-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-441">**Count**</span></span>

- <span data-ttu-id="2b2ea-442">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="2b2ea-443">**上位マルウェア受信者**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="2b2ea-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-444">**Count**</span></span>

- <span data-ttu-id="2b2ea-445">**上位マルウェア受信者 \> のデータを表示する (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="2b2ea-446">**上位マルウェア受信者 (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="2b2ea-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-447">**Count**</span></span>

<span data-ttu-id="2b2ea-448">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2b2ea-449">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="2b2ea-450">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2b2ea-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="2b2ea-451">この記事で説明されているレポートを表示して使用するには、セキュリティ/コンプライアンス センターの次のいずれかの役割グループのメンバー&があります。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2b2ea-452">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-452">**Organization Management**</span></span>
- <span data-ttu-id="2b2ea-453">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-453">**Security Administrator**</span></span>
- <span data-ttu-id="2b2ea-454">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-454">**Security Reader**</span></span>
- <span data-ttu-id="2b2ea-455">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-455">**Global Reader**</span></span>

<span data-ttu-id="2b2ea-456">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2b2ea-457">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-457">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2b2ea-458">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2b2ea-459">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b2ea-459">Related topics</span></span>

[<span data-ttu-id="2b2ea-460">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="2b2ea-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="2b2ea-461">セキュリティとコンプライアンス センターのメッセージ追跡の分析情報</span><span class="sxs-lookup"><span data-stu-id="2b2ea-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="2b2ea-462">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="2b2ea-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="2b2ea-463">Microsoft Defender for Office 365 のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="2b2ea-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
