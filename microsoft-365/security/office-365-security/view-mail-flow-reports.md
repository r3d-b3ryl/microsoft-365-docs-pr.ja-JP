---
title: レポートダッシュボードのメールフローレポートを表示する
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
description: 管理者は、セキュリティ & コンプライアンスセンターのレポートダッシュボードで使用できるメールフローレポートについて説明しています。
ms.custom: ''
ms.openlocfilehash: 3db9130083565d77bb84b4b31ec63eee5cc7a7c9
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171400"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="f9a7b-103">セキュリティ & コンプライアンスセンターのレポートダッシュボードでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f9a7b-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="f9a7b-104">セキュリティ & コンプライアンスセンターの [メールフローダッシュボード](mail-flow-insights-v2.md) で使用できるメールフローレポートに加えて、Microsoft 365 組織を監視するのに役立つさまざまな追加のメールフローレポートがレポートダッシュボードに用意されています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="f9a7b-105">[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、**レポート**ダッシュボードにアクセスすることによって、[セキュリティ & コンプライアンスセンター](https://office.protection.com)でこれらのレポートを表示でき \> **Dashboard**ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="f9a7b-106">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="f9a7b-108">コネクタレポート</span><span class="sxs-lookup"><span data-stu-id="f9a7b-108">Connector report</span></span>

<span data-ttu-id="f9a7b-109">**コネクタレポート**には、組織に対して構成されている[受信コネクタと送信コネクタ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)のメールフローアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="f9a7b-110">レポートを表示するには、[ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **コネクタレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="f9a7b-111">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ConnectorReport> ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![レポートダッシュボードのコネクタレポートウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="f9a7b-113">コネクタレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-113">Report view for the Connector report</span></span>

<span data-ttu-id="f9a7b-114">次のグラフはレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="f9a7b-115">**データの表示: メールフロー**: このグラフは、次の方法で開催される受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="f9a7b-116">**合計**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-116">**Total**</span></span>
  - <span data-ttu-id="f9a7b-117">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f9a7b-118">**コネクタを使用せずにインターネットに接続する**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f9a7b-119">構成済みの特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="f9a7b-120">グラフのデータを分離するには、[ **データの表示** ] コントロールを使用して、これらのオプションのいずれかまたは **すべてのメールフロー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![コネクタレポートでメールフロー別にデータを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="f9a7b-122">**データの表示方法: tls 使用法**: このグラフは、メールフローのトランスポート層セキュリティ (TLS) バージョンの使用率を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="f9a7b-123">グラフのデータを分離するには、[ **データの表示** ] コントロールを使用して、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="f9a7b-124">**すべてのメールフロー**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-124">**All mail flow**</span></span>
  - <span data-ttu-id="f9a7b-125">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f9a7b-126">**コネクタを使用せずにインターネットに接続する**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f9a7b-127">構成済みの特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-127">A specific connector that you've configured.</span></span>

  ![コネクタレポートでの TLS 使用法によるデータの表示](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="f9a7b-129">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="f9a7b-130">コネクタレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-130">Details table view for the Connector report</span></span>

<span data-ttu-id="f9a7b-131">レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f9a7b-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-132">**Date**</span></span>
- <span data-ttu-id="f9a7b-133">**コネクタの方向と名前**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-133">**Connector direction and name**</span></span>
- <span data-ttu-id="f9a7b-134">**コネクタの種類**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-134">**Connector type**</span></span>
- <span data-ttu-id="f9a7b-135">**FORCED TLS?**: 値 **True** または **False**。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="f9a7b-136">**TLS なし** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="f9a7b-137">**TLS 1.0** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="f9a7b-138">**TLS 1.1** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="f9a7b-139">**TLS 1.2** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="f9a7b-140">**Volume**: メッセージ数。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="f9a7b-141">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9a7b-142">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="f9a7b-143">Exchange トランスポートルールレポート</span><span class="sxs-lookup"><span data-stu-id="f9a7b-143">Exchange transport rule report</span></span>

<span data-ttu-id="f9a7b-144">**Exchange トランスポートルールレポート**は、組織内の受信メッセージと送信メッセージに対するメールフロールール (トランスポートルールとも呼ばれます) の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="f9a7b-145">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **Exchange トランスポートルール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="f9a7b-146">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ETRRuleReport> ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![レポートダッシュボードの Exchange トランスポートルールウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f9a7b-148">Exchange トランスポートルールレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="f9a7b-149">次のグラフはレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="f9a7b-150">**データの表示方法: Exchange トランスポートルール** \>**分割ダウン: 方向**: このグラフは、トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="f9a7b-151">**データの表示方法: Exchange トランスポートルール** \>**下に移動: 重要**度: このグラフは、重要**High severity**度が高い**ものと重要度が**低いもの、**重大度が低い**メッセージの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="f9a7b-152">重要度レベルをルールのアクションとして設定します (**このルールを重要度レベル** または _Setauditseverity_で監査します)。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="f9a7b-153">詳細については、「 [Exchange Online のメールフロールールのアクション](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="f9a7b-154">**データの表示方法: DLP Exchange トランスポートルール** \>**分解ダウン: Direction**: このグラフは、データ損失防止 (DLP) トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="f9a7b-155">次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f9a7b-156">**データの表示: すべての DLP トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f9a7b-157">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f9a7b-158">**データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="f9a7b-159">**データの表示方法: DLP Exchange トランスポートルール** \>**下に移動: 方向**: このビューには、重要度が**高**で、**中程度**、および DLP トランスポートルールの影響を受けた**重要度の低い**メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="f9a7b-160">次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f9a7b-161">**データの表示: すべての DLP トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f9a7b-162">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f9a7b-163">**データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="f9a7b-164">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="f9a7b-165">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9a7b-166">Direction 値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-166">Direction values</span></span>
- <span data-ttu-id="f9a7b-167">重要度の値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-167">Severity values</span></span>

![Exchange トランスポートルールレポートのレポートビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f9a7b-169">Exchange トランスポートルールレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="f9a7b-170">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9a7b-171">**データの表示方法: Exchange トランスポートルール**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="f9a7b-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-172">**Date**</span></span>
  - <span data-ttu-id="f9a7b-173">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-173">**Transport rule**</span></span>
  - <span data-ttu-id="f9a7b-174">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-174">**Subject**</span></span>
  - <span data-ttu-id="f9a7b-175">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-175">**Sender address**</span></span>
  - <span data-ttu-id="f9a7b-176">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-176">**Recipient address**</span></span>
  - <span data-ttu-id="f9a7b-177">**重大度**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-177">**Severity**</span></span>
  - <span data-ttu-id="f9a7b-178">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-178">**Direction**</span></span>

- <span data-ttu-id="f9a7b-179">**データの表示方法: DLP Exchange トランスポートルール**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="f9a7b-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-180">**Date**</span></span>
  - <span data-ttu-id="f9a7b-181">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-181">**DLP policy**</span></span>
  - <span data-ttu-id="f9a7b-182">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-182">**Transport rule**</span></span>
  - <span data-ttu-id="f9a7b-183">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-183">**Subject**</span></span>
  - <span data-ttu-id="f9a7b-184">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-184">**Sender address**</span></span>
  - <span data-ttu-id="f9a7b-185">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-185">**Recipient address**</span></span>
  - <span data-ttu-id="f9a7b-186">**重大度**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-186">**Severity**</span></span>
  - <span data-ttu-id="f9a7b-187">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-187">**Direction**</span></span>

<span data-ttu-id="f9a7b-188">詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9a7b-189">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9a7b-190">Direction 値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-190">Direction values</span></span>
- <span data-ttu-id="f9a7b-191">重要度の値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-191">Severity values</span></span>

<span data-ttu-id="f9a7b-192">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="f9a7b-193">転送レポート</span><span class="sxs-lookup"><span data-stu-id="f9a7b-193">Forwarding report</span></span>

<span data-ttu-id="f9a7b-194">**転送レポート**には、組織が Exchange Online メールボックスから外部ドメインにメッセージを自動的に転送したことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="f9a7b-195">転送されたメッセージは、セキュリティまたはコンプライアンスリスクを引き起こす可能性があり、侵害されたアカウントを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="f9a7b-196">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [レポートの**転送**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="f9a7b-197">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MailFlowForwarding> ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![レポートダッシュボードでレポートウィジェットを転送する](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="f9a7b-199">転送レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="f9a7b-200">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9a7b-201">**データの表示: 転送方法**: 次のメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="f9a7b-202">**トランスポートルール**: [メールフロールール](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="f9a7b-203">**メールボックスルール**: [受信トレイルール](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![転送レポートでの転送方法の表示](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="f9a7b-205">**データの表示: 転送ドメイン**: このビューには、転送先の受信者ドメインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![転送レポートでのドメインの転送ビュー](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="f9a7b-207">**データの表示: フォワーダー**: 次のフォワーダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="f9a7b-208">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-208">**Transport rule**</span></span>
  - <span data-ttu-id="f9a7b-209">転送の受信トレイルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![転送レポートのフォワーダービュー](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="f9a7b-211">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="f9a7b-212">転送レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="f9a7b-213">レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f9a7b-214">**フォワーダー**: 転送の受信トレイルールを含む値 **トランスポートルール** またはメールボックス。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="f9a7b-215">**転送の種類**: 値 **メールボックスルール** または **トランスポートルール**。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="f9a7b-216">**受信者名**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-216">**Recipient name**</span></span>
- <span data-ttu-id="f9a7b-217">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-217">**Recipient domain**</span></span>
- <span data-ttu-id="f9a7b-218">**詳細**: これは、メールフロールールの GUID 値、または受信トレイルールの RuleIdentity 値です。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="f9a7b-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-219">**Count**</span></span>
- <span data-ttu-id="f9a7b-220">**最初の繰越日付**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-220">**First forward date**</span></span>

<span data-ttu-id="f9a7b-221">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9a7b-222">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f9a7b-223">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="f9a7b-223">Mailflow status report</span></span>

<span data-ttu-id="f9a7b-224">**メールフローの状態レポート**は、[送信および受信](#sent-and-received-email-report)した電子メールレポートに似ていますが、エッジで許可またはブロックされる電子メールに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="f9a7b-225">これは、エッジ保護情報が含まれている唯一のレポートで、Exchange Online Protection (EOP) による評価のためにサービスに許可されるまでにブロックされる電子メールの量のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f9a7b-226">メッセージが5人の受信者に送信される場合は、メッセージを5つの異なるメッセージとしてカウントし、1つのメッセージではないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="f9a7b-227">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、**メールフローの状態レポート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="f9a7b-228">**メールフロー状態レポート**に直接移動するには、を開き <https://protection.office.com/mailflowStatusReport> ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![レポートダッシュボードのメールフロー status レポートウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9a7b-230">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="f9a7b-231">レポートを開くと、既定で [ **種類** ] タブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="f9a7b-232">既定では、このビューには、次のフィルターを使用して構成されたグラフとデータテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f9a7b-233">**日付**: 過去7日間。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="f9a7b-234">**方向**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-234">**Direction**:</span></span>

  - <span data-ttu-id="f9a7b-235">**受信**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-235">**Inbound**</span></span>
  - <span data-ttu-id="f9a7b-236">**向き**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-236">**Outbound**</span></span>
  - <span data-ttu-id="f9a7b-237">**組織内**: この数は、テナント内のメッセージに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f9a7b-238">sender abc@domain.com が受信者 xyz@domain.com に送信される ( **受信** および **送信**とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="f9a7b-239">**型**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-239">**Type**:</span></span>

  - <span data-ttu-id="f9a7b-240">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-240">**Good mail**</span></span>
  - <span data-ttu-id="f9a7b-241">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-241">**Malware**</span></span>
  - <span data-ttu-id="f9a7b-242">**スパム**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-242">**Spam**</span></span>
  - <span data-ttu-id="f9a7b-243">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-243">**Edge protection**</span></span>
  - <span data-ttu-id="f9a7b-244">**ルールメッセージ**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-244">**Rule messages**</span></span>
  - <span data-ttu-id="f9a7b-245">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-245">**Phishing email**</span></span>

<span data-ttu-id="f9a7b-246">グラフは、 **Type** の値で構成されています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="f9a7b-247">これらのフィルターを変更するには、[ **フィルター** ] をクリックするか、グラフの凡例で値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="f9a7b-248">データテーブルには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-248">The data table contains the following information:</span></span>

- <span data-ttu-id="f9a7b-249">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-249">**Direction**</span></span>
- <span data-ttu-id="f9a7b-250">**型**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-250">**Type**</span></span>
- <span data-ttu-id="f9a7b-251">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-251">**24 hours**</span></span>
- <span data-ttu-id="f9a7b-252">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-252">**3 days**</span></span>
- <span data-ttu-id="f9a7b-253">**7日**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-253">**7 days**</span></span>
- <span data-ttu-id="f9a7b-254">**15 日**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-254">**15 days**</span></span>
- <span data-ttu-id="f9a7b-255">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-255">**30 days**</span></span>

<span data-ttu-id="f9a7b-256">[カテゴリの選択] をクリックし **て詳細**を確認する場合は、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="f9a7b-257">**フィッシング電子メール**: この選択によって、 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f9a7b-258">**メール内のマルウェア**: この選択によって、 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f9a7b-259">**スパム検出**: この選択を行うと、 [スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="f9a7b-260">**エッジブロック**されたスパム: これを選択すると、 [スパム検出レポート](view-email-security-reports.md#spam-detections-report)に移動します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f9a7b-261">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-261">**Export**:</span></span>

<span data-ttu-id="f9a7b-262">詳細ビューでは、1日分のデータしかエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f9a7b-263">そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f9a7b-264">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9a7b-265">その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f9a7b-266">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9a7b-267">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="f9a7b-268">[ **方向** ] タブをクリックすると、[ **種類** ] ビューの同じ既定のフィルターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="f9a7b-269">グラフは **方向** の値によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="f9a7b-270">これらのフィルターを変更するには、[ **フィルター** ] をクリックするか、グラフの凡例で値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="f9a7b-271">[ **種類** の表示と同じフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f9a7b-272">データテーブルには、 **種類** ビューと同じ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="f9a7b-273">[詳細を表示する **カテゴリを選択** してください] の選択肢と動作は、[ **種類** ] ビューと同じです。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="f9a7b-274">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-274">**Export**:</span></span>

<span data-ttu-id="f9a7b-275">詳細ビューでは、1日分のデータしかエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f9a7b-276">そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f9a7b-277">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9a7b-278">その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f9a7b-279">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9a7b-280">メールフロー状態レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="f9a7b-281">**じょうご**ビューには、Microsoft の電子メール脅威保護機能が組織内の受信および送信電子メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="f9a7b-282">この例では、電子メール数の合計と、構成された脅威保護機能 (エッジ保護、マルウェア対策、フィッシング詐欺対策、スパム対策、スプーフィング対策など) がこの数に影響を与える方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="f9a7b-283">[ **じょうご** ] タブをクリックした場合、既定では、このビューには、次のフィルターで構成されたグラフとデータテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f9a7b-284">**日付**: 過去7日間。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f9a7b-285">**方向**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-285">**Direction**:</span></span>

  - <span data-ttu-id="f9a7b-286">**受信**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-286">**Inbound**</span></span>
  - <span data-ttu-id="f9a7b-287">**向き**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-287">**Outbound**</span></span>
  - <span data-ttu-id="f9a7b-288">**組織内**: この数は、テナント内で送信されたメッセージに対して使用されます。つまり、sender abc@domain.com は受信者 xyz@domain.com に送信されます (受信および送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="f9a7b-289">集計ビューとデータテーブルビューでは、90日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f9a7b-290">[ **フィルター**] をクリックすると、グラフとデータテーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f9a7b-291">この図は、次のように分類されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="f9a7b-292">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-292">**Total email**</span></span>
- <span data-ttu-id="f9a7b-293">**エッジ保護後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-293">**Email after edge protection**</span></span>
- <span data-ttu-id="f9a7b-294">**マルウェア対策、ファイル評価、ファイルの種類ブロックの後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="f9a7b-295">**フィッシング、URL 評価、ブランド偽装、スプーフィング対策の後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="f9a7b-296">**スパム対策、バルクメールフィルタリングの後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="f9a7b-297">**ユーザーとドメインの偽装1の後の電子メール**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f9a7b-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="f9a7b-298">**[ファイルと URL の後に電子メールを送信分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f9a7b-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="f9a7b-299">**配信後の保護 (URL のクリック時保護) 後に、電子メールが害ありませんでした。**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="f9a7b-300"><sup>1</sup> OFFICE 365 ATP のみ</span><span class="sxs-lookup"><span data-stu-id="f9a7b-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="f9a7b-301">EOP または ATP によってフィルター処理された電子メールを個別に表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="f9a7b-302">データテーブルには、次の情報が含まれています (日付の順序は降順)。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f9a7b-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-303">**Date**</span></span>
- <span data-ttu-id="f9a7b-304">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-304">**Total email**</span></span>
- <span data-ttu-id="f9a7b-305">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-305">**Edge protection**</span></span>
- <span data-ttu-id="f9a7b-306">**マルウェア対策、ファイル評価、ファイルの種類ブロック**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="f9a7b-307">**フィッシング、URL 評価、ブランド偽装、スプーフィング対策**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="f9a7b-308">**スパム対策、一括メールフィルター**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="f9a7b-309">**ユーザーおよびドメインの偽装 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="f9a7b-310">**File および URL 分析 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="f9a7b-311">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="f9a7b-312">データテーブル内の行を選択すると、そのメール数の詳細がポップアップスライドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f9a7b-313">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-313">**Export**:</span></span>

<span data-ttu-id="f9a7b-314">[**オプション**] の [**エクスポート**] をクリックした後、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="f9a7b-315">**概要 (過去90日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f9a7b-316">**詳細 (過去30日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f9a7b-317">[ **日付**] で範囲を選択し、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f9a7b-318">現在のフィルターのデータは .csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f9a7b-319">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9a7b-320">データに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="f9a7b-321">メールフロー状態レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9a7b-322">メールフロー状態レポートの Tech ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="f9a7b-323">[ **技術] ビュー** は、構成された脅威の保護機能についてより詳細な情報を提供する、 **じょうご** ビューに似ています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="f9a7b-324">グラフから、脅威保護のさまざまな段階でメッセージがどのように分類されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="f9a7b-325">既定では、[ **技術表示** ] タブをクリックすると、このビューには、次のフィルターで構成されたグラフとデータテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f9a7b-326">**日付**: 過去7日間。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f9a7b-327">**方向**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-327">**Direction**:</span></span>

  - <span data-ttu-id="f9a7b-328">**受信**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-328">**Inbound**</span></span>
  - <span data-ttu-id="f9a7b-329">**向き**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-329">**Outbound**</span></span>
  - <span data-ttu-id="f9a7b-330">**組織内**: この数は、テナント内のメッセージに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f9a7b-331">sender abc@domain.com が受信者 xyz@domain.com に送信される (受信および送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="f9a7b-332">集計ビューとデータテーブルビューでは、90日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f9a7b-333">[ **フィルター**] をクリックすると、グラフとデータテーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f9a7b-334">この図は、次のカテゴリに分類されるメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f9a7b-335">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-335">**Total email**</span></span>
- <span data-ttu-id="f9a7b-336">**エッジの許可、エッジのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="f9a7b-337">**マルウェア、安全な添付ファイルの検出 (ATP)、マルウェア対策エンジンの検出、ルールブロック**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="f9a7b-338">**Not フィッシング、DMARC failure、impersonation detection、スプーフィング検出、フィッシング検出**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="f9a7b-339">**URL 分析、URL 分析検出 (ATP) を使用した検出なし**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="f9a7b-340">**スパムではない、スパム**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-340">**Not spam, spam**</span></span>
- <span data-ttu-id="f9a7b-341">**非悪意のある電子メール、安全なリンクの検出 (ATP)、ZAP**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="f9a7b-342">グラフのカテゴリの上にマウスカーソルを移動すると、そのカテゴリのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="f9a7b-343">データテーブルには、次の情報が含まれています (日付の順序は降順)。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f9a7b-344">**Date**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-344">**Date**</span></span>
- <span data-ttu-id="f9a7b-345">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-345">**Total email**</span></span>
- <span data-ttu-id="f9a7b-346">**エッジのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-346">**Edge filtered**</span></span>
- <span data-ttu-id="f9a7b-347">**マルウェア対策エンジン、安全な添付ファイル、およびフィルター処理されたルール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="f9a7b-348">**DMARC、impersonation、スプーフ、フィッシング filtered**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="f9a7b-349">**URL 分析の検出**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-349">**URL detonation detection**</span></span>
- <span data-ttu-id="f9a7b-350">**迷惑メール対策フィルター**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="f9a7b-351">**ZAP 削除**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-351">**ZAP removed**</span></span>
- <span data-ttu-id="f9a7b-352">**安全なリンクによる検出**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-352">**Detection by safe links**</span></span>

<span data-ttu-id="f9a7b-353">データテーブル内の行を選択すると、そのメール数の詳細がポップアップスライドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f9a7b-354">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="f9a7b-354">**Export**:</span></span>

<span data-ttu-id="f9a7b-355">[ **エクスポート**] をクリックし、[ **オプション** ] で、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="f9a7b-356">**概要 (過去90日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f9a7b-357">**詳細 (過去30日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f9a7b-358">[ **日付**] で範囲を選択し、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f9a7b-359">現在のフィルターのデータは .csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f9a7b-360">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9a7b-361">データに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="f9a7b-362">メールフロー状態レポートの Tech ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="f9a7b-363">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="f9a7b-363">Sent and received email report</span></span>

<span data-ttu-id="f9a7b-364">**送信および受信**した電子メールレポートは、スパム検出、マルウェア、および "good" と識別された電子メールを含む、受信および送信電子メールに関する情報を示すスマートレポートです。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="f9a7b-365">このレポートと [メールフロー状態レポート](#mailflow-status-report) の違いは次のとおりです。このレポートには、エッジ保護によってブロックされたメッセージに関するデータは含まれません。メッセージが5人の受信者に送信されると、1つのメッセージとして数えられることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="f9a7b-366">レポートの集計ビューと詳細ビューでは、90日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="f9a7b-367">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [**送信済みおよび受信した電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="f9a7b-368">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![レポートダッシュボードで送信および受信した電子メールウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f9a7b-370">送信および受信した電子メールレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="f9a7b-371">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9a7b-372">**分割ダウン: 種類**: 使用可能なすべてのカテゴリをグラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="f9a7b-373">**合計**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-373">**Total**</span></span>
  - <span data-ttu-id="f9a7b-374">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-374">**Good mail**</span></span>
  - <span data-ttu-id="f9a7b-375">**マルウェア (マルウェア対策)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="f9a7b-376">**スパム検出**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-376">**Spam detections**</span></span>
  - <span data-ttu-id="f9a7b-377">**ルールメッセージ**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-377">**Rule messages**</span></span>
  - <span data-ttu-id="f9a7b-378">**高度なマルウェア** (OFFICE 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="f9a7b-379">グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信済みおよび受信した電子メールレポートの種類ビュー](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="f9a7b-381">**分割ダウン: 方向**: グラフには、 **合計**、 **受信**、および **送信** データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="f9a7b-382">グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信および受信した電子メールレポートの方向ビュー](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="f9a7b-384">**ドリルダウン** \> する方法 **マルウェア (マルウェア対策)**: この選択を行うと、 [電子メールレポートにあるマルウェアの検出](view-email-security-reports.md#malware-detections-in-email-report)が行われます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="f9a7b-385">**ドリルダウン** \> する方法 **スパム検出)**: この選択によって、 [スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f9a7b-386">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9a7b-387">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9a7b-388">Direction 値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-388">Direction values</span></span>
- <span data-ttu-id="f9a7b-389">型の値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-389">Type values</span></span>

<span data-ttu-id="f9a7b-390">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f9a7b-391">送信および受信した電子メールレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="f9a7b-392">[次の方法で **詳細テーブルを表示** ] をクリックすると、 **[方向] または** [ **下に移動: 方向** ] が表示され、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="f9a7b-393">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-393">**Date (UTC)**</span></span>
- <span data-ttu-id="f9a7b-394">**型**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-394">**Type**</span></span>
- <span data-ttu-id="f9a7b-395">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-395">**Direction**</span></span>
- <span data-ttu-id="f9a7b-396">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-396">**Message count**</span></span>

<span data-ttu-id="f9a7b-397">詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9a7b-398">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9a7b-399">Direction 値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-399">Direction values</span></span>
- <span data-ttu-id="f9a7b-400">型の値</span><span class="sxs-lookup"><span data-stu-id="f9a7b-400">Type values</span></span>

<span data-ttu-id="f9a7b-401">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="f9a7b-402">[上位送信者および受信者] レポート</span><span class="sxs-lookup"><span data-stu-id="f9a7b-402">Top senders and recipients report</span></span>

<span data-ttu-id="f9a7b-403">[ **上位の送信者と受信者** ] レポートは、上位の電子メール送信者と受信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="f9a7b-404">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して [ **上位の送信者と受信者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="f9a7b-405">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> ます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![レポートダッシュボードの [上位送信者および受信者] ウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f9a7b-407">上位送信者および受信者レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="f9a7b-408">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9a7b-409">**上位メール送信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="f9a7b-410">**\>最上位のメール受信者のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="f9a7b-411">**上位スパム受信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="f9a7b-412">**データの \> 表示上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="f9a7b-413">**データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="f9a7b-414">これらの選択に基づいて、円グラフの構成が変更されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="f9a7b-415">円グラフのくさび形の上にポインターを移動すると、送信または受信したメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="f9a7b-416">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![上位の送信者と受信者レポートのレポートビューに表示された円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f9a7b-418">上位送信者および受信者レポートの詳細テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="f9a7b-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="f9a7b-419">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9a7b-420">**上位メール送信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="f9a7b-421">**上位メール送信者**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-421">**Top mail senders**</span></span>
  - <span data-ttu-id="f9a7b-422">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-422">**Count**</span></span>

- <span data-ttu-id="f9a7b-423">**\>最上位のメール受信者のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="f9a7b-424">**上位メール受信者**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="f9a7b-425">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-425">**Count**</span></span>

- <span data-ttu-id="f9a7b-426">**上位スパム受信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="f9a7b-427">**上位スパム受信者**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="f9a7b-428">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-428">**Count**</span></span>

- <span data-ttu-id="f9a7b-429">**データの \> 表示上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="f9a7b-430">**上位マルウェア受信者**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="f9a7b-431">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-431">**Count**</span></span>

- <span data-ttu-id="f9a7b-432">**データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="f9a7b-433">**上位マルウェア受信者 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="f9a7b-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="f9a7b-434">**Count**</span></span>

<span data-ttu-id="f9a7b-435">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9a7b-436">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f9a7b-437">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f9a7b-438">レポートを表示して使用するには、セキュリティ & コンプライアンスセンター **および** Exchange Online で、指定された役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="f9a7b-439">セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="f9a7b-440">-組織の管理-セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)</span><span class="sxs-lookup"><span data-stu-id="f9a7b-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="f9a7b-441">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="f9a7b-442">Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="f9a7b-443">-組織の管理-表示のみの組織の管理-表示のみの受信者-コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="f9a7b-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="f9a7b-444">詳細については、「exchange online の [アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9a7b-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9a7b-445">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9a7b-445">Related topics</span></span>

[<span data-ttu-id="f9a7b-446">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="f9a7b-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f9a7b-447">セキュリティとコンプライアンス センターのメッセージ追跡の分析情報</span><span class="sxs-lookup"><span data-stu-id="f9a7b-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="f9a7b-448">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f9a7b-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="f9a7b-449">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f9a7b-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
