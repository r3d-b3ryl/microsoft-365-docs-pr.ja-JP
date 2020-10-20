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
ms.openlocfilehash: 801463877db2e022ab84c3187367587c61f71090
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600594"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="45894-103">セキュリティ & コンプライアンスセンターのレポートダッシュボードでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="45894-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="45894-104">セキュリティ & コンプライアンスセンターの [メールフローダッシュボード](mail-flow-insights-v2.md) で使用できるメールフローレポートに加えて、Microsoft 365 組織を監視するのに役立つさまざまな追加のメールフローレポートがレポートダッシュボードに用意されています。</span><span class="sxs-lookup"><span data-stu-id="45894-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="45894-105">[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、**レポート**ダッシュボードにアクセスすることによって、[セキュリティ & コンプライアンスセンター](https://office.protection.com)でこれらのレポートを表示でき \> **Dashboard**ます。</span><span class="sxs-lookup"><span data-stu-id="45894-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="45894-106">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="45894-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="45894-108">コネクタレポート</span><span class="sxs-lookup"><span data-stu-id="45894-108">Connector report</span></span>

<span data-ttu-id="45894-109">**コネクタレポート**には、組織に対して構成されている[受信コネクタと送信コネクタ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)のメールフローアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="45894-110">レポートを表示するには、[ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **コネクタレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="45894-111">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ConnectorReport> ます。</span><span class="sxs-lookup"><span data-stu-id="45894-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![レポートダッシュボードのコネクタレポートウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="45894-113">コネクタレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="45894-113">Report view for the Connector report</span></span>

<span data-ttu-id="45894-114">次のグラフはレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="45894-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="45894-115">**データの表示: メールフロー**: このグラフは、次の方法で開催される受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="45894-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="45894-116">**合計**</span><span class="sxs-lookup"><span data-stu-id="45894-116">**Total**</span></span>
  - <span data-ttu-id="45894-117">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="45894-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="45894-118">**コネクタを使用せずにインターネットに接続する**</span><span class="sxs-lookup"><span data-stu-id="45894-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="45894-119">構成済みの特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="45894-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="45894-120">グラフのデータを分離するには、[ **データの表示** ] コントロールを使用して、これらのオプションのいずれかまたは **すべてのメールフロー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![コネクタレポートでメールフロー別にデータを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="45894-122">**データの表示方法: tls 使用法**: このグラフは、メールフローのトランスポート層セキュリティ (TLS) バージョンの使用率を示しています。</span><span class="sxs-lookup"><span data-stu-id="45894-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="45894-123">グラフのデータを分離するには、[ **データの表示** ] コントロールを使用して、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="45894-124">**すべてのメールフロー**</span><span class="sxs-lookup"><span data-stu-id="45894-124">**All mail flow**</span></span>
  - <span data-ttu-id="45894-125">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="45894-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="45894-126">**コネクタを使用せずにインターネットに接続する**</span><span class="sxs-lookup"><span data-stu-id="45894-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="45894-127">構成済みの特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="45894-127">A specific connector that you've configured.</span></span>

  ![コネクタレポートでの TLS 使用法によるデータの表示](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="45894-129">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45894-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="45894-130">コネクタレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-130">Details table view for the Connector report</span></span>

<span data-ttu-id="45894-131">レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="45894-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="45894-132">**Date**</span></span>
- <span data-ttu-id="45894-133">**コネクタの方向と名前**</span><span class="sxs-lookup"><span data-stu-id="45894-133">**Connector direction and name**</span></span>
- <span data-ttu-id="45894-134">**コネクタの種類**</span><span class="sxs-lookup"><span data-stu-id="45894-134">**Connector type**</span></span>
- <span data-ttu-id="45894-135">**FORCED TLS?**: 値 **True** または **False**。</span><span class="sxs-lookup"><span data-stu-id="45894-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="45894-136">**TLS なし** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="45894-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="45894-137">**TLS 1.0** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="45894-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="45894-138">**TLS 1.1** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="45894-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="45894-139">**TLS 1.2** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="45894-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="45894-140">**Volume**: メッセージ数。</span><span class="sxs-lookup"><span data-stu-id="45894-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="45894-141">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45894-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="45894-142">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="45894-143">Exchange トランスポートルールレポート</span><span class="sxs-lookup"><span data-stu-id="45894-143">Exchange transport rule report</span></span>

<span data-ttu-id="45894-144">**Exchange トランスポートルールレポート**は、組織内の受信メッセージと送信メッセージに対するメールフロールール (トランスポートルールとも呼ばれます) の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="45894-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="45894-145">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **Exchange トランスポートルール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="45894-146">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ETRRuleReport> ます。</span><span class="sxs-lookup"><span data-stu-id="45894-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![レポートダッシュボードの Exchange トランスポートルールウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="45894-148">Exchange トランスポートルールレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="45894-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="45894-149">次のグラフはレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="45894-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="45894-150">**データの表示方法: Exchange トランスポートルール** \>**分割ダウン: 方向**: このグラフは、トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="45894-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="45894-151">**データの表示方法: Exchange トランスポートルール** \>**下に移動: 重要**度: このグラフは、重要**High severity**度が高い**ものと重要度が**低いもの、**重大度が低い**メッセージの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="45894-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="45894-152">重要度レベルをルールのアクションとして設定します (**このルールを重要度レベル** または _Setauditseverity_で監査します)。</span><span class="sxs-lookup"><span data-stu-id="45894-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="45894-153">詳細については、「 [Exchange Online のメールフロールールのアクション](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45894-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="45894-154">**データの表示方法: DLP Exchange トランスポートルール** \>**分解ダウン: Direction**: このグラフは、データ損失防止 (DLP) トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="45894-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="45894-155">次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="45894-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="45894-156">**データの表示: すべての DLP トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="45894-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="45894-157">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="45894-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="45894-158">**データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="45894-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="45894-159">**データの表示方法: DLP Exchange トランスポートルール** \>**下に移動: 方向**: このビューには、重要度が**高**で、**中程度**、および DLP トランスポートルールの影響を受けた**重要度の低い**メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="45894-160">次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="45894-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="45894-161">**データの表示: すべての DLP トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="45894-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="45894-162">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="45894-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="45894-163">**データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="45894-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="45894-164">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="45894-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="45894-165">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="45894-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="45894-166">Direction 値</span><span class="sxs-lookup"><span data-stu-id="45894-166">Direction values</span></span>
- <span data-ttu-id="45894-167">重要度の値</span><span class="sxs-lookup"><span data-stu-id="45894-167">Severity values</span></span>

![Exchange トランスポートルールレポートのレポートビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="45894-169">Exchange トランスポートルールレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="45894-170">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="45894-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="45894-171">**データの表示方法: Exchange トランスポートルール**:</span><span class="sxs-lookup"><span data-stu-id="45894-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="45894-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="45894-172">**Date**</span></span>
  - <span data-ttu-id="45894-173">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="45894-173">**Transport rule**</span></span>
  - <span data-ttu-id="45894-174">**Subject**</span><span class="sxs-lookup"><span data-stu-id="45894-174">**Subject**</span></span>
  - <span data-ttu-id="45894-175">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="45894-175">**Sender address**</span></span>
  - <span data-ttu-id="45894-176">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="45894-176">**Recipient address**</span></span>
  - <span data-ttu-id="45894-177">**重大度**</span><span class="sxs-lookup"><span data-stu-id="45894-177">**Severity**</span></span>
  - <span data-ttu-id="45894-178">**Direction**</span><span class="sxs-lookup"><span data-stu-id="45894-178">**Direction**</span></span>

- <span data-ttu-id="45894-179">**データの表示方法: DLP Exchange トランスポートルール**:</span><span class="sxs-lookup"><span data-stu-id="45894-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="45894-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="45894-180">**Date**</span></span>
  - <span data-ttu-id="45894-181">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="45894-181">**DLP policy**</span></span>
  - <span data-ttu-id="45894-182">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="45894-182">**Transport rule**</span></span>
  - <span data-ttu-id="45894-183">**Subject**</span><span class="sxs-lookup"><span data-stu-id="45894-183">**Subject**</span></span>
  - <span data-ttu-id="45894-184">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="45894-184">**Sender address**</span></span>
  - <span data-ttu-id="45894-185">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="45894-185">**Recipient address**</span></span>
  - <span data-ttu-id="45894-186">**重大度**</span><span class="sxs-lookup"><span data-stu-id="45894-186">**Severity**</span></span>
  - <span data-ttu-id="45894-187">**Direction**</span><span class="sxs-lookup"><span data-stu-id="45894-187">**Direction**</span></span>

<span data-ttu-id="45894-188">詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="45894-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="45894-189">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="45894-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="45894-190">Direction 値</span><span class="sxs-lookup"><span data-stu-id="45894-190">Direction values</span></span>
- <span data-ttu-id="45894-191">重要度の値</span><span class="sxs-lookup"><span data-stu-id="45894-191">Severity values</span></span>

<span data-ttu-id="45894-192">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="45894-193">転送レポート</span><span class="sxs-lookup"><span data-stu-id="45894-193">Forwarding report</span></span>

<span data-ttu-id="45894-194">**転送レポート**には、組織が Exchange Online メールボックスから外部ドメインにメッセージを自動的に転送したことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="45894-195">転送されたメッセージは、セキュリティまたはコンプライアンスリスクを引き起こす可能性があり、侵害されたアカウントを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="45894-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="45894-196">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [レポートの**転送**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="45894-197">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MailFlowForwarding> ます。</span><span class="sxs-lookup"><span data-stu-id="45894-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![レポートダッシュボードでレポートウィジェットを転送する](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="45894-199">転送レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="45894-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="45894-200">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="45894-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="45894-201">**データの表示: 転送方法**: 次のメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="45894-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="45894-202">**トランスポートルール**: [メールフロールール](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="45894-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="45894-203">**メールボックスルール**: [受信トレイルール](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="45894-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![転送レポートでの転送方法の表示](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="45894-205">**データの表示: 転送ドメイン**: このビューには、転送先の受信者ドメインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![転送レポートでのドメインの転送ビュー](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="45894-207">**データの表示: フォワーダー**: 次のフォワーダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="45894-208">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="45894-208">**Transport rule**</span></span>
  - <span data-ttu-id="45894-209">転送の受信トレイルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="45894-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![転送レポートのフォワーダービュー](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="45894-211">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45894-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="45894-212">転送レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="45894-213">レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="45894-214">**フォワーダー**: 転送の受信トレイルールを含む値 **トランスポートルール** またはメールボックス。</span><span class="sxs-lookup"><span data-stu-id="45894-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="45894-215">**転送の種類**: 値 **メールボックスルール** または **トランスポートルール**。</span><span class="sxs-lookup"><span data-stu-id="45894-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="45894-216">**受信者名**</span><span class="sxs-lookup"><span data-stu-id="45894-216">**Recipient name**</span></span>
- <span data-ttu-id="45894-217">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="45894-217">**Recipient domain**</span></span>
- <span data-ttu-id="45894-218">**詳細**: これは、メールフロールールの GUID 値、または受信トレイルールの RuleIdentity 値です。</span><span class="sxs-lookup"><span data-stu-id="45894-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="45894-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="45894-219">**Count**</span></span>
- <span data-ttu-id="45894-220">**最初の繰越日付**</span><span class="sxs-lookup"><span data-stu-id="45894-220">**First forward date**</span></span>

<span data-ttu-id="45894-221">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45894-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="45894-222">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="45894-223">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="45894-223">Mailflow status report</span></span>

<span data-ttu-id="45894-224">**メールフローの状態レポート**は、[送信および受信](#sent-and-received-email-report)した電子メールレポートに似ていますが、エッジで許可またはブロックされる電子メールに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45894-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="45894-225">これは、エッジ保護情報が含まれている唯一のレポートで、Exchange Online Protection (EOP) による評価のためにサービスに許可されるまでにブロックされる電子メールの量のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="45894-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="45894-226">メッセージが5人の受信者に送信される場合は、メッセージを5つの異なるメッセージとしてカウントし、1つのメッセージではないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="45894-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="45894-227">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、**メールフローの状態レポート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="45894-228">**メールフロー状態レポート**に直接移動するには、を開き <https://protection.office.com/mailflowStatusReport> ます。</span><span class="sxs-lookup"><span data-stu-id="45894-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![レポートダッシュボードのメールフロー status レポートウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="45894-230">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="45894-231">レポートを開くと、既定で [ **種類** ] タブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="45894-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="45894-232">既定では、このビューには、次のフィルターを使用して構成されたグラフとデータテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="45894-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="45894-233">**日付**: 過去7日間。</span><span class="sxs-lookup"><span data-stu-id="45894-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="45894-234">**方向**:</span><span class="sxs-lookup"><span data-stu-id="45894-234">**Direction**:</span></span>

  - <span data-ttu-id="45894-235">**受信**</span><span class="sxs-lookup"><span data-stu-id="45894-235">**Inbound**</span></span>
  - <span data-ttu-id="45894-236">**向き**</span><span class="sxs-lookup"><span data-stu-id="45894-236">**Outbound**</span></span>
  - <span data-ttu-id="45894-237">**組織内**: この数は、テナント内のメッセージに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="45894-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="45894-238">sender abc@domain.com が受信者 xyz@domain.com に送信される ( **受信** および **送信**とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="45894-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="45894-239">**型**:</span><span class="sxs-lookup"><span data-stu-id="45894-239">**Type**:</span></span>

  - <span data-ttu-id="45894-240">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="45894-240">**Good mail**</span></span>
  - <span data-ttu-id="45894-241">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="45894-241">**Malware**</span></span>
  - <span data-ttu-id="45894-242">**スパム**</span><span class="sxs-lookup"><span data-stu-id="45894-242">**Spam**</span></span>
  - <span data-ttu-id="45894-243">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="45894-243">**Edge protection**</span></span>
  - <span data-ttu-id="45894-244">**ルールメッセージ**</span><span class="sxs-lookup"><span data-stu-id="45894-244">**Rule messages**</span></span>
  - <span data-ttu-id="45894-245">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="45894-245">**Phishing email**</span></span>

<span data-ttu-id="45894-246">グラフは、 **Type** の値で構成されています。</span><span class="sxs-lookup"><span data-stu-id="45894-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="45894-247">これらのフィルターを変更するには、[ **フィルター** ] をクリックするか、グラフの凡例で値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="45894-248">データテーブルには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45894-248">The data table contains the following information:</span></span>

- <span data-ttu-id="45894-249">**Direction**</span><span class="sxs-lookup"><span data-stu-id="45894-249">**Direction**</span></span>
- <span data-ttu-id="45894-250">**型**</span><span class="sxs-lookup"><span data-stu-id="45894-250">**Type**</span></span>
- <span data-ttu-id="45894-251">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="45894-251">**24 hours**</span></span>
- <span data-ttu-id="45894-252">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="45894-252">**3 days**</span></span>
- <span data-ttu-id="45894-253">**7日**</span><span class="sxs-lookup"><span data-stu-id="45894-253">**7 days**</span></span>
- <span data-ttu-id="45894-254">**15 日**</span><span class="sxs-lookup"><span data-stu-id="45894-254">**15 days**</span></span>
- <span data-ttu-id="45894-255">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="45894-255">**30 days**</span></span>

<span data-ttu-id="45894-256">[カテゴリの選択] をクリックし **て詳細**を確認する場合は、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="45894-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="45894-257">**フィッシング電子メール**: この選択によって、 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="45894-258">**メール内のマルウェア**: この選択によって、 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="45894-259">**スパム検出**: この選択を行うと、 [スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="45894-260">**エッジブロック**されたスパム: これを選択すると、 [スパム検出レポート](view-email-security-reports.md#spam-detections-report)に移動します。</span><span class="sxs-lookup"><span data-stu-id="45894-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="45894-261">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="45894-261">**Export**:</span></span>

<span data-ttu-id="45894-262">詳細ビューでは、1日分のデータしかエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="45894-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="45894-263">そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="45894-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="45894-264">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="45894-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="45894-265">その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="45894-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="45894-266">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="45894-267">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="45894-268">[ **方向** ] タブをクリックすると、[ **種類** ] ビューの同じ既定のフィルターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="45894-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="45894-269">グラフは **方向** の値によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="45894-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="45894-270">これらのフィルターを変更するには、[ **フィルター** ] をクリックするか、グラフの凡例で値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="45894-271">[ **種類** の表示と同じフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="45894-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="45894-272">データテーブルには、 **種類** ビューと同じ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45894-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="45894-273">[詳細を表示する **カテゴリを選択** してください] の選択肢と動作は、[ **種類** ] ビューと同じです。</span><span class="sxs-lookup"><span data-stu-id="45894-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="45894-274">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="45894-274">**Export**:</span></span>

<span data-ttu-id="45894-275">詳細ビューでは、1日分のデータしかエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="45894-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="45894-276">そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="45894-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="45894-277">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="45894-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="45894-278">その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="45894-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="45894-279">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="45894-280">メールフロー状態レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="45894-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="45894-281">**じょうご**ビューには、Microsoft の電子メール脅威保護機能が組織内の受信および送信電子メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="45894-282">この例では、電子メール数の合計と、構成された脅威保護機能 (エッジ保護、マルウェア対策、フィッシング詐欺対策、スパム対策、スプーフィング対策など) がこの数に影響を与える方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="45894-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="45894-283">[ **じょうご** ] タブをクリックした場合、既定では、このビューには、次のフィルターで構成されたグラフとデータテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="45894-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="45894-284">**日付**: 過去7日間。</span><span class="sxs-lookup"><span data-stu-id="45894-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="45894-285">**方向**:</span><span class="sxs-lookup"><span data-stu-id="45894-285">**Direction**:</span></span>

  - <span data-ttu-id="45894-286">**受信**</span><span class="sxs-lookup"><span data-stu-id="45894-286">**Inbound**</span></span>
  - <span data-ttu-id="45894-287">**向き**</span><span class="sxs-lookup"><span data-stu-id="45894-287">**Outbound**</span></span>
  - <span data-ttu-id="45894-288">**組織内**: この数は、テナント内で送信されたメッセージに対して使用されます。つまり、sender abc@domain.com は受信者 xyz@domain.com に送信されます (受信および送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="45894-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="45894-289">集計ビューとデータテーブルビューでは、90日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="45894-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="45894-290">[ **フィルター**] をクリックすると、グラフとデータテーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="45894-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="45894-291">この図は、次のように分類されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="45894-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="45894-292">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="45894-292">**Total email**</span></span>
- <span data-ttu-id="45894-293">**エッジ保護後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="45894-293">**Email after edge protection**</span></span>
- <span data-ttu-id="45894-294">**マルウェア対策、ファイル評価、ファイルの種類ブロックの後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="45894-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="45894-295">**フィッシング、URL 評価、ブランド偽装、スプーフィング対策の後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="45894-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="45894-296">**スパム対策、バルクメールフィルタリングの後の電子メール**</span><span class="sxs-lookup"><span data-stu-id="45894-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="45894-297">**ユーザーとドメインの偽装1の後の電子メール**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="45894-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="45894-298">**[ファイルと URL の後に電子メールを送信分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="45894-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="45894-299">**配信後の保護 (URL のクリック時保護) 後に、電子メールが害ありませんでした。**</span><span class="sxs-lookup"><span data-stu-id="45894-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="45894-300"><sup>1</sup> OFFICE 365 ATP のみ</span><span class="sxs-lookup"><span data-stu-id="45894-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="45894-301">EOP または ATP によってフィルター処理された電子メールを個別に表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="45894-302">データテーブルには、次の情報が含まれています (日付の順序は降順)。</span><span class="sxs-lookup"><span data-stu-id="45894-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="45894-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="45894-303">**Date**</span></span>
- <span data-ttu-id="45894-304">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="45894-304">**Total email**</span></span>
- <span data-ttu-id="45894-305">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="45894-305">**Edge protection**</span></span> 
- <span data-ttu-id="45894-306">**マルウェア対策、ファイルの評価、ファイルの種類のブロック**:</span><span class="sxs-lookup"><span data-stu-id="45894-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="45894-307">**ファイル評価**: 他の Microsoft のお客様が添付ファイルを識別したためにフィルター処理されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="45894-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="45894-308">**ファイルの種類のブロック**: メッセージで識別された悪意のあるファイルの種類によってフィルター処理されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="45894-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>      
- <span data-ttu-id="45894-309">**フィッシング、URL 評価、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="45894-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="45894-310">**Url 評価**: 他の Microsoft のお客様からの url の識別により、メッセージがフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="45894-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="45894-311">**ブランドの偽装**: 既知のブランドの公開送信者からのメッセージによってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="45894-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="45894-312">**スプーフィング**: 受信者が属しているドメインをスプーフィングしようとしたメッセージによってフィルター処理されたメッセージ、またはメッセージ送信者が所有していないドメイン。</span><span class="sxs-lookup"><span data-stu-id="45894-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>  
- <span data-ttu-id="45894-313">**スパム対策、一括メールフィルター**:</span><span class="sxs-lookup"><span data-stu-id="45894-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="45894-314">**バルクメールフィルター**: 受信者に一括メールを配信しようとしたためにフィルター処理されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="45894-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span> 
- <span data-ttu-id="45894-315">**ユーザーおよびドメインの偽装 (ATP)**:</span><span class="sxs-lookup"><span data-stu-id="45894-315">**User and domain impersonation (ATP)**:</span></span>
  - <span data-ttu-id="45894-316">**ユーザー偽装**: フィッシング対策ポリシーの偽造保護設定で定義されたユーザー (メッセージ送信者) を偽装しようとしたため、メッセージがフィルター処理されました。</span><span class="sxs-lookup"><span data-stu-id="45894-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="45894-317">**ドメイン偽装**: フィッシング対策ポリシーの偽造保護設定で定義されているドメインを偽装しようとしたため、メッセージがフィルター処理されました。</span><span class="sxs-lookup"><span data-stu-id="45894-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span> 
- <span data-ttu-id="45894-318">**File および URL 分析 (ATP)**:</span><span class="sxs-lookup"><span data-stu-id="45894-318">**File and URL detonation (ATP)**:</span></span>
  - <span data-ttu-id="45894-319">**ファイル分析**: 安全な添付ファイルポリシーによってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="45894-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="45894-320">**URL 分析**: 「安全なリンク」ポリシーによってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="45894-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>  
- <span data-ttu-id="45894-321">**配信後の保護と zap (ATP)、または zap (EOP): zap は、** ゼロ時間の自動削除を示します。</span><span class="sxs-lookup"><span data-stu-id="45894-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="45894-322">データテーブル内の行を選択すると、そのメール数の詳細がポップアップスライドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="45894-323">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="45894-323">**Export**:</span></span>

<span data-ttu-id="45894-324">[**オプション**] の [**エクスポート**] をクリックした後、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="45894-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="45894-325">**概要 (過去90日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="45894-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="45894-326">**詳細 (過去30日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="45894-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="45894-327">[ **日付**] で範囲を選択し、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="45894-328">現在のフィルターのデータは .csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="45894-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="45894-329">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="45894-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="45894-330">データに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="45894-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="45894-331">メールフロー状態レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="45894-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="45894-332">メールフロー状態レポートの Tech ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="45894-333">[ **技術] ビュー** は、構成された脅威の保護機能についてより詳細な情報を提供する、 **じょうご** ビューに似ています。</span><span class="sxs-lookup"><span data-stu-id="45894-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="45894-334">グラフから、脅威保護のさまざまな段階でメッセージがどのように分類されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="45894-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="45894-335">既定では、[ **技術表示** ] タブをクリックすると、このビューには、次のフィルターで構成されたグラフとデータテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="45894-336">**日付**: 過去7日間。</span><span class="sxs-lookup"><span data-stu-id="45894-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="45894-337">**方向**:</span><span class="sxs-lookup"><span data-stu-id="45894-337">**Direction**:</span></span>

  - <span data-ttu-id="45894-338">**受信**</span><span class="sxs-lookup"><span data-stu-id="45894-338">**Inbound**</span></span>
  - <span data-ttu-id="45894-339">**向き**</span><span class="sxs-lookup"><span data-stu-id="45894-339">**Outbound**</span></span>
  - <span data-ttu-id="45894-340">**組織内**: この数は、テナント内のメッセージに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="45894-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="45894-341">sender abc@domain.com が受信者 xyz@domain.com に送信される (受信および送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="45894-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="45894-342">集計ビューとデータテーブルビューでは、90日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="45894-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="45894-343">[ **フィルター**] をクリックすると、グラフとデータテーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="45894-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="45894-344">この図は、次のカテゴリに分類されるメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="45894-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="45894-345">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="45894-345">**Total email**</span></span>
- <span data-ttu-id="45894-346">**エッジの許可、エッジのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="45894-346">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="45894-347">**マルウェア、安全な添付ファイルの検出 (ATP)、マルウェア対策エンジンの検出、ルールブロック**</span><span class="sxs-lookup"><span data-stu-id="45894-347">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="45894-348">**Not フィッシング、DMARC failure、impersonation detection、スプーフィング検出、フィッシング検出**</span><span class="sxs-lookup"><span data-stu-id="45894-348">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="45894-349">**URL 分析、URL 分析検出 (ATP) を使用した検出なし**</span><span class="sxs-lookup"><span data-stu-id="45894-349">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="45894-350">**スパムではない、スパム**</span><span class="sxs-lookup"><span data-stu-id="45894-350">**Not spam, spam**</span></span>
- <span data-ttu-id="45894-351">**非悪意のある電子メール、安全なリンクの検出 (ATP)、ZAP**</span><span class="sxs-lookup"><span data-stu-id="45894-351">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="45894-352">グラフのカテゴリの上にマウスカーソルを移動すると、そのカテゴリのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-352">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="45894-353">データテーブルには、次の情報が含まれています (日付の順序は降順)。</span><span class="sxs-lookup"><span data-stu-id="45894-353">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="45894-354">**Date**</span><span class="sxs-lookup"><span data-stu-id="45894-354">**Date**</span></span>
- <span data-ttu-id="45894-355">**合計メール数**</span><span class="sxs-lookup"><span data-stu-id="45894-355">**Total email**</span></span>
- <span data-ttu-id="45894-356">**エッジのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="45894-356">**Edge filtered**</span></span>
- <span data-ttu-id="45894-357">**マルウェア対策エンジン、安全な添付ファイル、フィルター処理**されたルール:</span><span class="sxs-lookup"><span data-stu-id="45894-357">**Anti-malware engine, safe attachments, rule filtered**:</span></span>
  - <span data-ttu-id="45894-358">**ルールフィルター**: メールフロールール (トランスポートルールとも呼ばれる) によってフィルター処理されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="45894-358">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="45894-359">**DMARC、impersonation、スプーフ、フィッシング filtered**:</span><span class="sxs-lookup"><span data-stu-id="45894-359">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="45894-360">**DMARC**: メッセージが DMARC 認証チェックに失敗したためにフィルター処理されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="45894-360">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span> 
- <span data-ttu-id="45894-361">**URL 分析の検出**</span><span class="sxs-lookup"><span data-stu-id="45894-361">**URL detonation detection**</span></span>
- <span data-ttu-id="45894-362">**迷惑メール対策フィルター**</span><span class="sxs-lookup"><span data-stu-id="45894-362">**Anti-spam filtered**</span></span>
- <span data-ttu-id="45894-363">**ZAP 削除**</span><span class="sxs-lookup"><span data-stu-id="45894-363">**ZAP removed**</span></span>
- <span data-ttu-id="45894-364">**安全なリンクによる検出**</span><span class="sxs-lookup"><span data-stu-id="45894-364">**Detection by safe links**</span></span>

<span data-ttu-id="45894-365">データテーブル内の行を選択すると、そのメール数の詳細がポップアップスライドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-365">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="45894-366">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="45894-366">**Export**:</span></span>

<span data-ttu-id="45894-367">[ **エクスポート**] をクリックし、[ **オプション** ] で、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="45894-367">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="45894-368">**概要 (過去90日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="45894-368">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="45894-369">**詳細 (過去30日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="45894-369">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="45894-370">[ **日付**] で範囲を選択し、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-370">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="45894-371">現在のフィルターのデータは .csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="45894-371">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="45894-372">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="45894-372">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="45894-373">データに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="45894-373">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="45894-374">メールフロー状態レポートの Tech ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-374">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="45894-375">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="45894-375">Sent and received email report</span></span>

<span data-ttu-id="45894-376">**送信および受信**した電子メールレポートは、スパム検出、マルウェア、および "good" と識別された電子メールを含む、受信および送信電子メールに関する情報を示すスマートレポートです。</span><span class="sxs-lookup"><span data-stu-id="45894-376">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="45894-377">このレポートと [メールフロー状態レポート](#mailflow-status-report) の違いは次のとおりです。このレポートには、エッジ保護によってブロックされたメッセージに関するデータは含まれません。メッセージが5人の受信者に送信されると、1つのメッセージとして数えられることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="45894-377">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="45894-378">レポートの集計ビューと詳細ビューでは、90日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="45894-378">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="45894-379">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [**送信済みおよび受信した電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-379">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="45894-380">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> ます。</span><span class="sxs-lookup"><span data-stu-id="45894-380">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![レポートダッシュボードで送信および受信した電子メールウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="45894-382">送信および受信した電子メールレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="45894-382">Report view for the Sent and received email report</span></span>

<span data-ttu-id="45894-383">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="45894-383">The following charts are available in the report view:</span></span>

- <span data-ttu-id="45894-384">**分割ダウン: 種類**: 使用可能なすべてのカテゴリをグラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="45894-384">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="45894-385">**合計**</span><span class="sxs-lookup"><span data-stu-id="45894-385">**Total**</span></span>
  - <span data-ttu-id="45894-386">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="45894-386">**Good mail**</span></span>
  - <span data-ttu-id="45894-387">**マルウェア (マルウェア対策)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="45894-387">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="45894-388">**スパム検出**</span><span class="sxs-lookup"><span data-stu-id="45894-388">**Spam detections**</span></span>
  - <span data-ttu-id="45894-389">**ルールメッセージ**</span><span class="sxs-lookup"><span data-stu-id="45894-389">**Rule messages**</span></span>
  - <span data-ttu-id="45894-390">**高度なマルウェア** (OFFICE 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="45894-390">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="45894-391">グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-391">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信済みおよび受信した電子メールレポートの種類ビュー](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="45894-393">**分割ダウン: 方向**: グラフには、 **合計**、 **受信**、および **送信** データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-393">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="45894-394">グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-394">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信および受信した電子メールレポートの方向ビュー](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="45894-396">**ドリルダウン** \> する方法 **マルウェア (マルウェア対策)**: この選択を行うと、 [電子メールレポートにあるマルウェアの検出](view-email-security-reports.md#malware-detections-in-email-report)が行われます。</span><span class="sxs-lookup"><span data-stu-id="45894-396">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="45894-397">**ドリルダウン** \> する方法 **スパム検出)**: この選択によって、 [スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-397">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="45894-398">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="45894-398">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="45894-399">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="45894-399">**Start date** and **End date**</span></span>
- <span data-ttu-id="45894-400">Direction 値</span><span class="sxs-lookup"><span data-stu-id="45894-400">Direction values</span></span>
- <span data-ttu-id="45894-401">型の値</span><span class="sxs-lookup"><span data-stu-id="45894-401">Type values</span></span>

<span data-ttu-id="45894-402">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-402">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="45894-403">送信および受信した電子メールレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="45894-403">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="45894-404">[次の方法で **詳細テーブルを表示** ] をクリックすると、 **[方向] または** [ **下に移動: 方向** ] が表示され、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-404">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="45894-405">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="45894-405">**Date (UTC)**</span></span>
- <span data-ttu-id="45894-406">**型**</span><span class="sxs-lookup"><span data-stu-id="45894-406">**Type**</span></span>
- <span data-ttu-id="45894-407">**Direction**</span><span class="sxs-lookup"><span data-stu-id="45894-407">**Direction**</span></span>
- <span data-ttu-id="45894-408">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="45894-408">**Message count**</span></span>

<span data-ttu-id="45894-409">詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="45894-409">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="45894-410">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="45894-410">**Start date** and **End date**</span></span>
- <span data-ttu-id="45894-411">Direction 値</span><span class="sxs-lookup"><span data-stu-id="45894-411">Direction values</span></span>
- <span data-ttu-id="45894-412">型の値</span><span class="sxs-lookup"><span data-stu-id="45894-412">Type values</span></span>

<span data-ttu-id="45894-413">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-413">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="45894-414">[上位送信者および受信者] レポート</span><span class="sxs-lookup"><span data-stu-id="45894-414">Top senders and recipients report</span></span>

<span data-ttu-id="45894-415">[ **上位の送信者と受信者** ] レポートは、上位の電子メール送信者と受信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="45894-415">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="45894-416">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して [ **上位の送信者と受信者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45894-416">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="45894-417">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> ます。</span><span class="sxs-lookup"><span data-stu-id="45894-417">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![レポートダッシュボードの [上位送信者および受信者] ウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="45894-419">上位送信者および受信者レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="45894-419">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="45894-420">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="45894-420">The following charts are available in the report view:</span></span>

- <span data-ttu-id="45894-421">**上位メール送信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="45894-421">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="45894-422">**\>最上位のメール受信者のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="45894-422">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="45894-423">**上位スパム受信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="45894-423">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="45894-424">**データの \> 表示上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="45894-424">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="45894-425">**データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)</span><span class="sxs-lookup"><span data-stu-id="45894-425">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="45894-426">これらの選択に基づいて、円グラフの構成が変更されます。</span><span class="sxs-lookup"><span data-stu-id="45894-426">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="45894-427">円グラフのくさび形の上にポインターを移動すると、送信または受信したメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45894-427">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="45894-428">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45894-428">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![上位の送信者と受信者レポートのレポートビューに表示された円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="45894-430">上位送信者および受信者レポートの詳細テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="45894-430">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="45894-431">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="45894-431">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="45894-432">**上位メール送信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="45894-432">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="45894-433">**上位メール送信者**</span><span class="sxs-lookup"><span data-stu-id="45894-433">**Top mail senders**</span></span>
  - <span data-ttu-id="45894-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="45894-434">**Count**</span></span>

- <span data-ttu-id="45894-435">**\>最上位のメール受信者のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="45894-435">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="45894-436">**上位メール受信者**</span><span class="sxs-lookup"><span data-stu-id="45894-436">**Top mail recipients**</span></span>
  - <span data-ttu-id="45894-437">**Count**</span><span class="sxs-lookup"><span data-stu-id="45894-437">**Count**</span></span>

- <span data-ttu-id="45894-438">**上位スパム受信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="45894-438">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="45894-439">**上位スパム受信者**</span><span class="sxs-lookup"><span data-stu-id="45894-439">**Top spam recipients**</span></span>
  - <span data-ttu-id="45894-440">**Count**</span><span class="sxs-lookup"><span data-stu-id="45894-440">**Count**</span></span>

- <span data-ttu-id="45894-441">**データの \> 表示上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="45894-441">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="45894-442">**上位マルウェア受信者**</span><span class="sxs-lookup"><span data-stu-id="45894-442">**Top malware recipients**</span></span>
  - <span data-ttu-id="45894-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="45894-443">**Count**</span></span>

- <span data-ttu-id="45894-444">**データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)</span><span class="sxs-lookup"><span data-stu-id="45894-444">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="45894-445">**上位マルウェア受信者 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="45894-445">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="45894-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="45894-446">**Count**</span></span>

<span data-ttu-id="45894-447">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45894-447">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="45894-448">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45894-448">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="45894-449">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="45894-449">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="45894-450">レポートを表示して使用するには、セキュリティ & コンプライアンスセンター **および** Exchange Online で、指定された役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="45894-450">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="45894-451">セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="45894-451">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="45894-452">-組織の管理-セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)</span><span class="sxs-lookup"><span data-stu-id="45894-452">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="45894-453">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45894-453">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="45894-454">Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="45894-454">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="45894-455">-組織の管理-表示のみの組織の管理-表示のみの受信者-コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="45894-455">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="45894-456">詳細については、「exchange online の [アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45894-456">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="45894-457">関連項目</span><span class="sxs-lookup"><span data-stu-id="45894-457">Related topics</span></span>

[<span data-ttu-id="45894-458">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="45894-458">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="45894-459">セキュリティとコンプライアンス センターのメッセージ追跡の分析情報</span><span class="sxs-lookup"><span data-stu-id="45894-459">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="45894-460">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="45894-460">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="45894-461">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="45894-461">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
