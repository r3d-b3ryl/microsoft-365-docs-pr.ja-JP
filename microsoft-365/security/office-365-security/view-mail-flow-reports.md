---
title: セキュリティ & コンプライアンスセンターでメールフローレポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 組織のメールフローセキュリティレポートを検索して使用する方法について説明します。 メールフローレポートは、セキュリティ & コンプライアンスセンターで利用できます。
ms.custom: ''
ms.openlocfilehash: 70c96bb4f43edb80f98fdc98aa173fed9e54e7d7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937261"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="acc2c-104">セキュリティ & コンプライアンスセンターでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="acc2c-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="acc2c-105">セキュリティ & コンプライアンスセンターで利用できる[メールフローの洞察](mail-flow-insights-v2.md)に加えて、さまざまなメールフローレポートを使用して、Microsoft 365 組織の監視に役立てることもできます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="acc2c-106">[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、 <https://office.protection.com> **レポート**ダッシュボードにアクセスすることで、これらのレポートをセキュリティ & コンプライアンスセンターで表示でき \> **Dashboard**ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="acc2c-107">レポートダッシュボードに直接移動するには、を開き <https://office.protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="acc2c-109">コネクタレポート</span><span class="sxs-lookup"><span data-stu-id="acc2c-109">Connector report</span></span>

<span data-ttu-id="acc2c-110">**コネクタレポート**には、組織に対して構成されている[受信コネクタと送信コネクタ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)のメールフローアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="acc2c-111">レポートを表示するには、[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] を開き、[**レポート** \> **ダッシュボード**] に移動して、[**コネクタレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="acc2c-112">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ConnectorReport> ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![レポートダッシュボードのコネクタレポートウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="acc2c-114">コネクタレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-114">Report view for the Connector report</span></span>

<span data-ttu-id="acc2c-115">次のグラフはレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="acc2c-116">**データの表示: メールフロー**: このグラフは、次の方法で開催される受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="acc2c-117">**合計**</span><span class="sxs-lookup"><span data-stu-id="acc2c-117">**Total**</span></span>
  - <span data-ttu-id="acc2c-118">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="acc2c-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="acc2c-119">**コネクタを使用せずにインターネットに接続する**</span><span class="sxs-lookup"><span data-stu-id="acc2c-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="acc2c-120">構成済みの特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="acc2c-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="acc2c-121">グラフのデータを分離するには、[**データの表示**] コントロールを使用して、これらのオプションのいずれかまたは**すべてのメールフロー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![コネクタレポートでメールフロー別にデータを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="acc2c-123">**データの表示方法: tls 使用法**: このグラフは、メールフローのトランスポート層セキュリティ (TLS) バージョンの使用率を示しています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="acc2c-124">グラフのデータを分離するには、[**データの表示**] コントロールを使用して、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="acc2c-125">**すべてのメールフロー**</span><span class="sxs-lookup"><span data-stu-id="acc2c-125">**All mail flow**</span></span>
  - <span data-ttu-id="acc2c-126">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="acc2c-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="acc2c-127">**コネクタを使用せずにインターネットに接続する**</span><span class="sxs-lookup"><span data-stu-id="acc2c-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="acc2c-128">構成済みの特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="acc2c-128">A specific connector that you've configured.</span></span>

  ![コネクタレポートでの TLS 使用法によるデータの表示](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="acc2c-130">レポートビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="acc2c-131">コネクタレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-131">Details table view for the Connector report</span></span>

<span data-ttu-id="acc2c-132">レポートビューで [**詳細テーブルの表示**] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="acc2c-133">**Date**</span><span class="sxs-lookup"><span data-stu-id="acc2c-133">**Date**</span></span>
- <span data-ttu-id="acc2c-134">**コネクタの方向と名前**</span><span class="sxs-lookup"><span data-stu-id="acc2c-134">**Connector direction and name**</span></span>
- <span data-ttu-id="acc2c-135">**コネクタの種類**</span><span class="sxs-lookup"><span data-stu-id="acc2c-135">**Connector type**</span></span>
- <span data-ttu-id="acc2c-136">**FORCED TLS?**: 値**True**または**False**。</span><span class="sxs-lookup"><span data-stu-id="acc2c-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="acc2c-137">**TLS なし**(パーセント)</span><span class="sxs-lookup"><span data-stu-id="acc2c-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="acc2c-138">**TLS 1.0** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="acc2c-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="acc2c-139">**TLS 1.1** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="acc2c-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="acc2c-140">**TLS 1.2** (パーセント)</span><span class="sxs-lookup"><span data-stu-id="acc2c-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="acc2c-141">**Volume**: メッセージ数。</span><span class="sxs-lookup"><span data-stu-id="acc2c-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="acc2c-142">詳細テーブルビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="acc2c-143">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="acc2c-144">Exchange トランスポートルールレポート</span><span class="sxs-lookup"><span data-stu-id="acc2c-144">Exchange transport rule report</span></span>

<span data-ttu-id="acc2c-145">**Exchange トランスポートルールレポート**は、組織内の受信メッセージと送信メッセージに対するメールフロールール (トランスポートルールとも呼ばれます) の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="acc2c-146">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して、[ **Exchange トランスポートルール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="acc2c-147">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ETRRuleReport> ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![レポートダッシュボードの Exchange トランスポートルールウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="acc2c-149">Exchange トランスポートルールレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="acc2c-150">次のグラフはレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="acc2c-151">**データの表示方法: Exchange トランスポートルール** \>**分割ダウン: 方向**: このグラフは、トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="acc2c-152">**データの表示方法: Exchange トランスポートルール** \>**下に移動: 重要**度: このグラフは、重要**High severity**度が高い**ものと重要度が**低いもの、**重大度が低い**メッセージの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="acc2c-153">重要度レベルをルールのアクションとして設定します (**このルールを重要度レベル**または_Setauditseverity_で監査します)。</span><span class="sxs-lookup"><span data-stu-id="acc2c-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="acc2c-154">詳細については、「 [Exchange Online のメールフロールールのアクション](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc2c-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="acc2c-155">**データの表示方法: DLP Exchange トランスポートルール** \>**分解ダウン: Direction**: このグラフは、データ損失防止 (DLP) トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="acc2c-156">次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="acc2c-157">**データの表示: すべての DLP トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="acc2c-158">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="acc2c-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="acc2c-159">**データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="acc2c-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="acc2c-160">**データの表示方法: DLP Exchange トランスポートルール** \>**下に移動: 方向**: このビューには、重要度が**高**で、**中程度**、および DLP トランスポートルールの影響を受けた**重要度の低い**メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="acc2c-161">次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="acc2c-162">**データの表示: すべての DLP トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="acc2c-163">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="acc2c-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="acc2c-164">**データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="acc2c-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="acc2c-165">レポートビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="acc2c-166">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="acc2c-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="acc2c-167">Direction 値</span><span class="sxs-lookup"><span data-stu-id="acc2c-167">Direction values</span></span>
- <span data-ttu-id="acc2c-168">重要度の値</span><span class="sxs-lookup"><span data-stu-id="acc2c-168">Severity values</span></span>

![Exchange トランスポートルールレポートのレポートビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="acc2c-170">Exchange トランスポートルールレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="acc2c-171">[**詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="acc2c-172">**データの表示方法: Exchange トランスポートルール**:</span><span class="sxs-lookup"><span data-stu-id="acc2c-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="acc2c-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="acc2c-173">**Date**</span></span>
  - <span data-ttu-id="acc2c-174">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-174">**Transport rule**</span></span>
  - <span data-ttu-id="acc2c-175">**件名**</span><span class="sxs-lookup"><span data-stu-id="acc2c-175">**Subject**</span></span>
  - <span data-ttu-id="acc2c-176">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="acc2c-176">**Sender address**</span></span>
  - <span data-ttu-id="acc2c-177">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="acc2c-177">**Recipient address**</span></span>
  - <span data-ttu-id="acc2c-178">**重大度**</span><span class="sxs-lookup"><span data-stu-id="acc2c-178">**Severity**</span></span>
  - <span data-ttu-id="acc2c-179">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="acc2c-179">**Direction**</span></span>

- <span data-ttu-id="acc2c-180">**データの表示方法: DLP Exchange トランスポートルール**:</span><span class="sxs-lookup"><span data-stu-id="acc2c-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="acc2c-181">**Date**</span><span class="sxs-lookup"><span data-stu-id="acc2c-181">**Date**</span></span>
  - <span data-ttu-id="acc2c-182">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="acc2c-182">**DLP policy**</span></span>
  - <span data-ttu-id="acc2c-183">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-183">**Transport rule**</span></span>
  - <span data-ttu-id="acc2c-184">**件名**</span><span class="sxs-lookup"><span data-stu-id="acc2c-184">**Subject**</span></span>
  - <span data-ttu-id="acc2c-185">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="acc2c-185">**Sender address**</span></span>
  - <span data-ttu-id="acc2c-186">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="acc2c-186">**Recipient address**</span></span>
  - <span data-ttu-id="acc2c-187">**重大度**</span><span class="sxs-lookup"><span data-stu-id="acc2c-187">**Severity**</span></span>
  - <span data-ttu-id="acc2c-188">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="acc2c-188">**Direction**</span></span>

<span data-ttu-id="acc2c-189">詳細テーブルビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="acc2c-190">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="acc2c-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="acc2c-191">Direction 値</span><span class="sxs-lookup"><span data-stu-id="acc2c-191">Direction values</span></span>
- <span data-ttu-id="acc2c-192">重要度の値</span><span class="sxs-lookup"><span data-stu-id="acc2c-192">Severity values</span></span>

<span data-ttu-id="acc2c-193">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="acc2c-194">転送レポート</span><span class="sxs-lookup"><span data-stu-id="acc2c-194">Forwarding report</span></span>

<span data-ttu-id="acc2c-195">**転送レポート**には、組織が Exchange Online メールボックスから外部ドメインにメッセージを自動的に転送したことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="acc2c-196">転送されたメッセージは、セキュリティまたはコンプライアンスリスクを引き起こす可能性があり、侵害されたアカウントを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="acc2c-197">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [レポートの**転送**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="acc2c-198">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MailFlowForwarding> ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![レポートダッシュボードでレポートウィジェットを転送する](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="acc2c-200">転送レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="acc2c-201">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="acc2c-202">**データの表示: 転送方法**: 次のメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="acc2c-203">**トランスポートルール**:[メールフロールール](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="acc2c-204">**メールボックスルール**:[受信トレイルール](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![転送レポートでの転送方法の表示](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="acc2c-206">**データの表示: 転送ドメイン**: このビューには、転送先の受信者ドメインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![転送レポートでのドメインの転送ビュー](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="acc2c-208">**データの表示: フォワーダー**: 次のフォワーダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="acc2c-209">**トランスポートルール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-209">**Transport rule**</span></span>
  - <span data-ttu-id="acc2c-210">転送の受信トレイルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="acc2c-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![転送レポートのフォワーダービュー](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="acc2c-212">レポートビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="acc2c-213">転送レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="acc2c-214">レポートビューで [**詳細テーブルの表示**] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="acc2c-215">**フォワーダー**: 転送の受信トレイルールを含む値**トランスポートルール**またはメールボックス。</span><span class="sxs-lookup"><span data-stu-id="acc2c-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="acc2c-216">**転送の種類**: 値**メールボックスルール**または**トランスポートルール**。</span><span class="sxs-lookup"><span data-stu-id="acc2c-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="acc2c-217">**受信者名**</span><span class="sxs-lookup"><span data-stu-id="acc2c-217">**Recipient name**</span></span>
- <span data-ttu-id="acc2c-218">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="acc2c-218">**Recipient domain**</span></span>
- <span data-ttu-id="acc2c-219">**詳細**: これは、メールフロールールの GUID 値、または受信トレイルールの RuleIdentity 値です。</span><span class="sxs-lookup"><span data-stu-id="acc2c-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="acc2c-220">**Count**</span><span class="sxs-lookup"><span data-stu-id="acc2c-220">**Count**</span></span>
- <span data-ttu-id="acc2c-221">**最初の繰越日付**</span><span class="sxs-lookup"><span data-stu-id="acc2c-221">**First forward date**</span></span>

<span data-ttu-id="acc2c-222">詳細テーブルビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="acc2c-223">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="acc2c-224">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="acc2c-224">Mailflow status report</span></span>

<span data-ttu-id="acc2c-225">**メールフローの状態レポート**は、[送信および受信](#sent-and-received-email-report)した電子メールレポートに似ていますが、エッジで許可またはブロックされる電子メールに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="acc2c-226">これは、エッジ保護情報が含まれている唯一のレポートで、Exchange Online Protection (EOP) による評価のためにサービスに許可されるまでにブロックされる電子メールの量のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="acc2c-227">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、**メールフローの状態レポート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="acc2c-228">**メールフロー状態レポート**に直接移動するには、を開き <https://protection.office.com/mailflowStatusReport> ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![レポートダッシュボードのメールフロー status レポートウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="acc2c-230">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="acc2c-231">レポートを開くと、既定で [**種類**] タブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="acc2c-232">既定では、このビューには、次のフィルターを使用して構成されたグラフとデータテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="acc2c-233">**日付**: 過去7日間。</span><span class="sxs-lookup"><span data-stu-id="acc2c-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="acc2c-234">**方向**:</span><span class="sxs-lookup"><span data-stu-id="acc2c-234">**Direction**:</span></span>

  - <span data-ttu-id="acc2c-235">**受信**</span><span class="sxs-lookup"><span data-stu-id="acc2c-235">**Inbound**</span></span>
  - <span data-ttu-id="acc2c-236">**向き**</span><span class="sxs-lookup"><span data-stu-id="acc2c-236">**Outbound**</span></span>
  - <span data-ttu-id="acc2c-237">**組織内**(**受信**および**送信**とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="acc2c-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="acc2c-238">**型**:</span><span class="sxs-lookup"><span data-stu-id="acc2c-238">**Type**:</span></span>

  - <span data-ttu-id="acc2c-239">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-239">**Good mail**</span></span>
  - <span data-ttu-id="acc2c-240">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="acc2c-240">**Malware**</span></span>
  - <span data-ttu-id="acc2c-241">**スパム**</span><span class="sxs-lookup"><span data-stu-id="acc2c-241">**Spam**</span></span>
  - <span data-ttu-id="acc2c-242">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="acc2c-242">**Edge protection**</span></span>
  - <span data-ttu-id="acc2c-243">**ルールメッセージ**</span><span class="sxs-lookup"><span data-stu-id="acc2c-243">**Rule messages**</span></span>
  - <span data-ttu-id="acc2c-244">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-244">**Phishing email**</span></span>

<span data-ttu-id="acc2c-245">グラフは、 **Type**の値で構成されています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="acc2c-246">これらのフィルターを変更するには、[**フィルター** ] をクリックするか、グラフの凡例で値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="acc2c-247">データテーブルには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-247">The data table contains the following information:</span></span>

- <span data-ttu-id="acc2c-248">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="acc2c-248">**Direction**</span></span>
- <span data-ttu-id="acc2c-249">**型**</span><span class="sxs-lookup"><span data-stu-id="acc2c-249">**Type**</span></span>
- <span data-ttu-id="acc2c-250">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="acc2c-250">**24 hours**</span></span>
- <span data-ttu-id="acc2c-251">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="acc2c-251">**3 days**</span></span>
- <span data-ttu-id="acc2c-252">**7日**</span><span class="sxs-lookup"><span data-stu-id="acc2c-252">**7 days**</span></span>
- <span data-ttu-id="acc2c-253">**15 日**</span><span class="sxs-lookup"><span data-stu-id="acc2c-253">**15 days**</span></span>
- <span data-ttu-id="acc2c-254">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="acc2c-254">**30 days**</span></span>

<span data-ttu-id="acc2c-255">[カテゴリの選択] をクリックし**て詳細**を確認する場合は、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="acc2c-256">**フィッシング電子メール**: この選択によって、[脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="acc2c-257">**メール内のマルウェア**: この選択によって、[脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="acc2c-258">**スパム検出**: この選択を行うと、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="acc2c-259">**エッジブロック**されたスパム: これを選択すると、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)に移動します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="acc2c-260">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="acc2c-260">**Export**:</span></span>

<span data-ttu-id="acc2c-261">詳細ビューでは、1日分のデータしかエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="acc2c-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="acc2c-262">そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="acc2c-263">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="acc2c-264">その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="acc2c-265">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="acc2c-266">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="acc2c-267">[**方向**] タブをクリックすると、[**種類**] ビューの同じ既定のフィルターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="acc2c-268">グラフは**方向**の値によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="acc2c-269">これらのフィルターを変更するには、[**フィルター** ] をクリックするか、グラフの凡例で値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="acc2c-270">[**種類**の表示と同じフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="acc2c-271">データテーブルには、**種類**ビューと同じ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="acc2c-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="acc2c-272">[詳細を表示する**カテゴリを選択**してください] の選択肢と動作は、[**種類**] ビューと同じです。</span><span class="sxs-lookup"><span data-stu-id="acc2c-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="acc2c-273">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="acc2c-273">**Export**:</span></span>

<span data-ttu-id="acc2c-274">詳細ビューでは、1日分のデータしかエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="acc2c-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="acc2c-275">そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="acc2c-276">エクスポートされた各 .csv ファイルは、15万行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="acc2c-277">その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="acc2c-278">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="acc2c-279">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="acc2c-279">Sent and received email report</span></span>

<span data-ttu-id="acc2c-280">**送信および受信**した電子メールレポートは、スパム検出、マルウェア、および "good" と識別された電子メールを含む、受信および送信電子メールに関する情報を示すスマートレポートです。</span><span class="sxs-lookup"><span data-stu-id="acc2c-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="acc2c-281">このレポートと[メールフロー状態レポート](#mailflow-status-report)の違いは次のとおりです。このレポートには、エッジ保護によってブロックされたメッセージに関するデータは含まれません。</span><span class="sxs-lookup"><span data-stu-id="acc2c-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="acc2c-282">レポートの集計ビューと詳細ビューでは、90日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="acc2c-283">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [**送信済みおよび受信した電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="acc2c-284">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![レポートダッシュボードで送信および受信した電子メールウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="acc2c-286">送信および受信した電子メールレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="acc2c-287">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="acc2c-288">**分割ダウン: 種類**: 使用可能なすべてのカテゴリをグラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="acc2c-289">**合計**</span><span class="sxs-lookup"><span data-stu-id="acc2c-289">**Total**</span></span>
  - <span data-ttu-id="acc2c-290">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="acc2c-290">**Good mail**</span></span>
  - <span data-ttu-id="acc2c-291">**マルウェア (マルウェア対策)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="acc2c-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="acc2c-292">**スパム検出**</span><span class="sxs-lookup"><span data-stu-id="acc2c-292">**Spam detections**</span></span>
  - <span data-ttu-id="acc2c-293">**ルールメッセージ**</span><span class="sxs-lookup"><span data-stu-id="acc2c-293">**Rule messages**</span></span>
  - <span data-ttu-id="acc2c-294">**高度なマルウェア**(OFFICE 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="acc2c-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="acc2c-295">グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信済みおよび受信した電子メールレポートの種類ビュー](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="acc2c-297">**分割ダウン: 方向**: グラフには、**合計**、**受信**、および**送信**データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="acc2c-298">グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信および受信した電子メールレポートの方向ビュー](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="acc2c-300">**ドリルダウン** \> する方法**マルウェア (マルウェア対策)**: これを選択すると、[電子メールレポートのマルウェアの検出](view-email-security-reports.md#malware-detection-in-email-report)に移動します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detection in email report](view-email-security-reports.md#malware-detection-in-email-report).</span></span>

- <span data-ttu-id="acc2c-301">**ドリルダウン** \> する方法**スパム検出)**: この選択によって、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="acc2c-302">レポートビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="acc2c-303">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="acc2c-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="acc2c-304">Direction 値</span><span class="sxs-lookup"><span data-stu-id="acc2c-304">Direction values</span></span>
- <span data-ttu-id="acc2c-305">型の値</span><span class="sxs-lookup"><span data-stu-id="acc2c-305">Type values</span></span>

<span data-ttu-id="acc2c-306">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="acc2c-307">送信および受信した電子メールレポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="acc2c-308">[次の方法で**詳細テーブルを表示**] をクリックすると、 **[方向] または**[**下に移動: 方向**] が表示され、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="acc2c-309">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="acc2c-309">**Date (UTC)**</span></span>
- <span data-ttu-id="acc2c-310">**型**</span><span class="sxs-lookup"><span data-stu-id="acc2c-310">**Type**</span></span>
- <span data-ttu-id="acc2c-311">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="acc2c-311">**Direction**</span></span>
- <span data-ttu-id="acc2c-312">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="acc2c-312">**Message count**</span></span>

<span data-ttu-id="acc2c-313">詳細テーブルビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="acc2c-314">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="acc2c-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="acc2c-315">Direction 値</span><span class="sxs-lookup"><span data-stu-id="acc2c-315">Direction values</span></span>
- <span data-ttu-id="acc2c-316">型の値</span><span class="sxs-lookup"><span data-stu-id="acc2c-316">Type values</span></span>

<span data-ttu-id="acc2c-317">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="acc2c-318">[上位送信者および受信者] レポート</span><span class="sxs-lookup"><span data-stu-id="acc2c-318">Top senders and recipients report</span></span>

<span data-ttu-id="acc2c-319">[**上位の送信者と受信者**] レポートは、上位の電子メール送信者と受信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="acc2c-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="acc2c-320">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して [**上位の送信者と受信者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc2c-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="acc2c-321">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> ます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![レポートダッシュボードの [上位送信者および受信者] ウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="acc2c-323">上位送信者および受信者レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="acc2c-324">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="acc2c-325">**上位メール送信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="acc2c-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="acc2c-326">**\>最上位のメール受信者のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="acc2c-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="acc2c-327">**上位スパム受信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="acc2c-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="acc2c-328">**データの \> 表示上位マルウェア受信者**(EOP)</span><span class="sxs-lookup"><span data-stu-id="acc2c-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="acc2c-329">**データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)</span><span class="sxs-lookup"><span data-stu-id="acc2c-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="acc2c-330">これらの選択に基づいて、円グラフの構成が変更されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="acc2c-331">円グラフのくさび形の上にポインターを移動すると、送信または受信したメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="acc2c-332">レポートビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![上位の送信者と受信者レポートのレポートビューに表示された円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="acc2c-334">上位送信者および受信者レポートの詳細テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="acc2c-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="acc2c-335">[**詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="acc2c-336">**上位メール送信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="acc2c-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="acc2c-337">**上位メール送信者**</span><span class="sxs-lookup"><span data-stu-id="acc2c-337">**Top mail senders**</span></span>
  - <span data-ttu-id="acc2c-338">**Count**</span><span class="sxs-lookup"><span data-stu-id="acc2c-338">**Count**</span></span>

- <span data-ttu-id="acc2c-339">**\>最上位のメール受信者のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="acc2c-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="acc2c-340">**上位メール受信者**</span><span class="sxs-lookup"><span data-stu-id="acc2c-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="acc2c-341">**Count**</span><span class="sxs-lookup"><span data-stu-id="acc2c-341">**Count**</span></span>

- <span data-ttu-id="acc2c-342">**上位スパム受信者のデータを表示する \>**</span><span class="sxs-lookup"><span data-stu-id="acc2c-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="acc2c-343">**上位スパム受信者**</span><span class="sxs-lookup"><span data-stu-id="acc2c-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="acc2c-344">**Count**</span><span class="sxs-lookup"><span data-stu-id="acc2c-344">**Count**</span></span>

- <span data-ttu-id="acc2c-345">**データの \> 表示上位マルウェア受信者**(EOP)</span><span class="sxs-lookup"><span data-stu-id="acc2c-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="acc2c-346">**上位マルウェア受信者**</span><span class="sxs-lookup"><span data-stu-id="acc2c-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="acc2c-347">**Count**</span><span class="sxs-lookup"><span data-stu-id="acc2c-347">**Count**</span></span>

- <span data-ttu-id="acc2c-348">**データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)</span><span class="sxs-lookup"><span data-stu-id="acc2c-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="acc2c-349">**上位マルウェア受信者 (ATP)**</span><span class="sxs-lookup"><span data-stu-id="acc2c-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="acc2c-350">**Count**</span><span class="sxs-lookup"><span data-stu-id="acc2c-350">**Count**</span></span>

<span data-ttu-id="acc2c-351">詳細テーブルビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acc2c-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="acc2c-352">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc2c-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="acc2c-353">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="acc2c-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="acc2c-354">レポートを表示して使用するには、セキュリティ & コンプライアンスセンター**および**Exchange Online で、指定された役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="acc2c-355">セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="acc2c-356">-組織の管理</span><span class="sxs-lookup"><span data-stu-id="acc2c-356">-Organization Management</span></span>

  <span data-ttu-id="acc2c-357">-セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)</span><span class="sxs-lookup"><span data-stu-id="acc2c-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="acc2c-358">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc2c-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="acc2c-359">Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc2c-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="acc2c-360">-組織の管理</span><span class="sxs-lookup"><span data-stu-id="acc2c-360">-Organization Management</span></span>

  <span data-ttu-id="acc2c-361">-表示のみの組織管理</span><span class="sxs-lookup"><span data-stu-id="acc2c-361">-View-only Organization Management</span></span>

  <span data-ttu-id="acc2c-362">-表示のみの受信者</span><span class="sxs-lookup"><span data-stu-id="acc2c-362">-View-Only Recipients</span></span>

  <span data-ttu-id="acc2c-363">-コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="acc2c-363">-Compliance Management</span></span>

<span data-ttu-id="acc2c-364">詳細については、「exchange online の[アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc2c-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="acc2c-365">関連トピック</span><span class="sxs-lookup"><span data-stu-id="acc2c-365">Related topics</span></span>

[<span data-ttu-id="acc2c-366">セキュリティとコンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="acc2c-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="acc2c-367">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="acc2c-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
