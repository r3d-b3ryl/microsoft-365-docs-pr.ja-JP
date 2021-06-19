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
description: 管理者は、セキュリティ コンプライアンス センターの [レポート] ダッシュボードで使用できるメール フロー レポート&できます。
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029478"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="720fa-103">セキュリティ コンプライアンス センターの [レポート] ダッシュボードでメール フロー レポート&表示する</span><span class="sxs-lookup"><span data-stu-id="720fa-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="720fa-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="720fa-104">**Applies to**</span></span>
- [<span data-ttu-id="720fa-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="720fa-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="720fa-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="720fa-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="720fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="720fa-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="720fa-108">このトピックで説明するレポートの大部分は、Exchange 管理センター (EAC) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="720fa-109">詳細については、「新しい [Exchange 管理センターのメール フロー レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="720fa-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="720fa-110">[Exchange トランスポート ルール レポートは](view-email-security-reports.md#exchange-transport-rule-report)、Microsoft 365 Defender ポータルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="720fa-111">セキュリティ & コンプライアンス センターのメール フロー[](mail-flow-insights-v2.md)ダッシュボードで使用できるメール フロー レポートに加えて、Microsoft 365 組織の監視に役立つさまざまなメール フロー レポートをレポート ダッシュボードで利用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="720fa-112">必要なアクセス許可 [がある](#what-permissions-are-needed-to-view-these-reports)場合は、[レポート ダッシュボード] に移動して、セキュリティ & [コンプライアンス](https://protection.office.com) センターでこれらのレポート **を表示** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="720fa-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="720fa-113">レポート ダッシュボードに直接移動するには、を開きます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="720fa-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ 管理コンプライアンス センター&ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="720fa-115">コネクタ レポート</span><span class="sxs-lookup"><span data-stu-id="720fa-115">Connector report</span></span>

<span data-ttu-id="720fa-116">コネクタ **レポートには**、組織用に構成 [](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)されている受信コネクタと送信コネクタのメール フロー アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="720fa-117">レポートを表示するには、コンプライアンス センターのセキュリティ &[開き、[](https://protection.office.com)レポート **ダッシュボード]** に移動し、[コネクタ \> レポート]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="720fa-118">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="720fa-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![レポート ダッシュボードのコネクタ レポート ウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="720fa-120">コネクタ レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-120">Report view for the Connector report</span></span>

<span data-ttu-id="720fa-121">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="720fa-122">**データの表示方法: メール フロー**: このグラフは、次の方法で編成された受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="720fa-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="720fa-123">**合計**</span><span class="sxs-lookup"><span data-stu-id="720fa-123">**Total**</span></span>
  - <span data-ttu-id="720fa-124">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="720fa-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="720fa-125">**コネクタのないインターネットへ**</span><span class="sxs-lookup"><span data-stu-id="720fa-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="720fa-126">構成した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="720fa-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="720fa-127">グラフ内のデータを分離するには、[データの表示] コントロールを使用して、これらのオプションのいずれかを選択するか、[すべてのメール フロー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![コネクタ レポートでメール フロー別にデータを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="720fa-129">**データの表示方法: TLS の使用状況**: このグラフは、メール フローのトランスポート層セキュリティ (TLS) バージョンの使用状況の割合を示しています。</span><span class="sxs-lookup"><span data-stu-id="720fa-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="720fa-130">グラフ内のデータを分離するには、[データの表示] コントロールを使用 **して** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="720fa-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="720fa-131">**すべてのメール フロー**</span><span class="sxs-lookup"><span data-stu-id="720fa-131">**All mail flow**</span></span>
  - <span data-ttu-id="720fa-132">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="720fa-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="720fa-133">**コネクタのないインターネットへ**</span><span class="sxs-lookup"><span data-stu-id="720fa-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="720fa-134">構成した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="720fa-134">A specific connector that you've configured.</span></span>

  ![コネクタ レポートで TLS 使用状況別にデータを表示する](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="720fa-136">レポート ビューで **[フィルター]** をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="720fa-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="720fa-137">コネクタ レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-137">Details table view for the Connector report</span></span>

<span data-ttu-id="720fa-138">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="720fa-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="720fa-139">**Date**</span></span>
- <span data-ttu-id="720fa-140">**コネクタの方向と名前**</span><span class="sxs-lookup"><span data-stu-id="720fa-140">**Connector direction and name**</span></span>
- <span data-ttu-id="720fa-141">**コネクタの種類**</span><span class="sxs-lookup"><span data-stu-id="720fa-141">**Connector type**</span></span>
- <span data-ttu-id="720fa-142">**強制 TLS?**: True **または** False の **値を指定します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="720fa-143">**TLS なし** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="720fa-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="720fa-144">**TLS 1.0** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="720fa-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="720fa-145">**TLS 1.1** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="720fa-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="720fa-146">**TLS 1.2** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="720fa-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="720fa-147">**ボリューム**: メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="720fa-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="720fa-148">詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="720fa-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="720fa-149">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="720fa-150">Exchange トランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="720fa-150">Exchange transport rule report</span></span>

<span data-ttu-id="720fa-151">**Exchange トランスポート ルール レポートには**、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="720fa-152">レポートを表示するには、コンプライアンス センターのセキュリティ & [開](https://protection.office.com)き、[レポート **ダッシュボード]** に移動し \> 、[Exchange **トランスポート** ルール **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="720fa-153">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="720fa-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![レポート ダッシュボードの Exchange トランスポート ルール ウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="720fa-155">Exchange トランスポート ルール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="720fa-156">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="720fa-157">**データの表示方法: Exchange トランスポート ルール** \>**[ブレークダウン]: [方向]**: このグラフには、トランスポート ルールの影響を受けた受信メッセージと送信メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="720fa-158">**データの表示方法: Exchange トランスポート ルール** \>**[分類]: [重大度]**: このグラフには、重大度の高いメッセージと中程度の重大度メッセージ、および **低重大度メッセージの数が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="720fa-159">重大度レベルは、ルールのアクションとして設定します **(重大度** レベルまたは _SetAuditSeverity_ でこのルールを監査します)。</span><span class="sxs-lookup"><span data-stu-id="720fa-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="720fa-160">詳細については [、「Exchange Online のメール フロー ルールアクション」を参照してください](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="720fa-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="720fa-161">**データの表示方法: DLP Exchange トランスポート ルール** \>**[ブレークダウン]: [方向]**: このグラフは、データ損失防止 (DLP) トランスポート ルールの影響を受けた受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="720fa-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="720fa-162">次のオプションをオンにすることで、グラフをさらに絞り込みできます。</span><span class="sxs-lookup"><span data-stu-id="720fa-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="720fa-163">**データの表示: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="720fa-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="720fa-164">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="720fa-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="720fa-165">**データの表示: 検出されたコンテンツの量が少ない米国愛国者法**</span><span class="sxs-lookup"><span data-stu-id="720fa-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="720fa-166">**データの表示方法: DLP Exchange トランスポート ルール** \>**[分類: 方向]**: このビューには、DLP トランスポートルールの影響を受けた重大度の高いメッセージと中程度の重大度メッセージの数が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="720fa-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="720fa-167">次のオプションをオンにすることで、グラフをさらに絞り込みできます。</span><span class="sxs-lookup"><span data-stu-id="720fa-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="720fa-168">**データの表示: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="720fa-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="720fa-169">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="720fa-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="720fa-170">**データの表示: 検出されたコンテンツの量が少ない米国愛国者法**</span><span class="sxs-lookup"><span data-stu-id="720fa-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="720fa-171">レポート ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="720fa-172">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="720fa-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="720fa-173">方向の値</span><span class="sxs-lookup"><span data-stu-id="720fa-173">Direction values</span></span>
- <span data-ttu-id="720fa-174">重大度の値</span><span class="sxs-lookup"><span data-stu-id="720fa-174">Severity values</span></span>

![Exchange トランスポート ルール レポートのレポート ビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="720fa-176">Exchange トランスポート ルール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="720fa-177">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="720fa-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="720fa-178">**データの表示方法: Exchange トランスポート ルール**:</span><span class="sxs-lookup"><span data-stu-id="720fa-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="720fa-179">**Date**</span><span class="sxs-lookup"><span data-stu-id="720fa-179">**Date**</span></span>
  - <span data-ttu-id="720fa-180">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="720fa-180">**Transport rule**</span></span>
  - <span data-ttu-id="720fa-181">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="720fa-181">**Subject**</span></span>
  - <span data-ttu-id="720fa-182">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="720fa-182">**Sender address**</span></span>
  - <span data-ttu-id="720fa-183">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="720fa-183">**Recipient address**</span></span>
  - <span data-ttu-id="720fa-184">**重大度**</span><span class="sxs-lookup"><span data-stu-id="720fa-184">**Severity**</span></span>
  - <span data-ttu-id="720fa-185">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="720fa-185">**Direction**</span></span>

- <span data-ttu-id="720fa-186">**データの表示方法: DLP Exchange トランスポート ルール**:</span><span class="sxs-lookup"><span data-stu-id="720fa-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="720fa-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="720fa-187">**Date**</span></span>
  - <span data-ttu-id="720fa-188">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="720fa-188">**DLP policy**</span></span>
  - <span data-ttu-id="720fa-189">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="720fa-189">**Transport rule**</span></span>
  - <span data-ttu-id="720fa-190">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="720fa-190">**Subject**</span></span>
  - <span data-ttu-id="720fa-191">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="720fa-191">**Sender address**</span></span>
  - <span data-ttu-id="720fa-192">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="720fa-192">**Recipient address**</span></span>
  - <span data-ttu-id="720fa-193">**重大度**</span><span class="sxs-lookup"><span data-stu-id="720fa-193">**Severity**</span></span>
  - <span data-ttu-id="720fa-194">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="720fa-194">**Direction**</span></span>

<span data-ttu-id="720fa-195">詳細テーブル ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="720fa-196">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="720fa-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="720fa-197">方向の値</span><span class="sxs-lookup"><span data-stu-id="720fa-197">Direction values</span></span>
- <span data-ttu-id="720fa-198">重大度の値</span><span class="sxs-lookup"><span data-stu-id="720fa-198">Severity values</span></span>

<span data-ttu-id="720fa-199">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="720fa-200">転送レポート</span><span class="sxs-lookup"><span data-stu-id="720fa-200">Forwarding report</span></span>

<span data-ttu-id="720fa-201">転送 **レポートには**、組織の自動的に転送されたメッセージが、組織のメールボックスから外部ドメインExchange Onlineされます。</span><span class="sxs-lookup"><span data-stu-id="720fa-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="720fa-202">転送されたメッセージは、セキュリティまたはコンプライアンスリスクを引き起し、アカウントの侵害を示す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="720fa-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="720fa-203">レポートを表示するには、コンプライアンス センターのセキュリティ &[開](https://protection.office.com)き、[レポート **ダッシュボード]** に移動し、[レポートの転送] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="720fa-204">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="720fa-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![レポート ダッシュボードのレポート ウィジェットの転送](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="720fa-206">転送レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="720fa-207">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="720fa-208">**データの表示: 転送方法**: 次のメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="720fa-209">**トランスポート ルール**: メール フロー ルール [とも呼ばれる](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="720fa-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="720fa-210">**メールボックス ルール**: 受信トレイ ルール [とも呼ばれる](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="720fa-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![転送レポートの [転送方法] ビュー](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="720fa-212">**[データの表示: 転送ドメイン**] : このビューには、転送先である受信者ドメインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![転送レポートの [転送ドメイン] ビュー](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="720fa-214">**データを表示する: Forwarders**: 次の転送者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="720fa-215">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="720fa-215">**Transport rule**</span></span>
  - <span data-ttu-id="720fa-216">転送受信トレイ ルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="720fa-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![転送レポートのフォワーダー ビュー](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="720fa-218">レポート ビューで **[フィルター]** をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="720fa-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="720fa-219">転送レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="720fa-220">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="720fa-221">**フォワーダー**: トランスポート **ルールまたは** 転送受信トレイ ルールを含むメールボックスの値。</span><span class="sxs-lookup"><span data-stu-id="720fa-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="720fa-222">**転送の種類**: メールボックス ルール **またはトランスポート ルール\*\*\*\*の値** です。</span><span class="sxs-lookup"><span data-stu-id="720fa-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="720fa-223">**受信者名**</span><span class="sxs-lookup"><span data-stu-id="720fa-223">**Recipient name**</span></span>
- <span data-ttu-id="720fa-224">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="720fa-224">**Recipient domain**</span></span>
- <span data-ttu-id="720fa-225">**詳細**: これは、メール フロー ルールの GUID 値、または受信トレイ ルールの RuleIdentity 値です。</span><span class="sxs-lookup"><span data-stu-id="720fa-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="720fa-226">**Count**</span><span class="sxs-lookup"><span data-stu-id="720fa-226">**Count**</span></span>
- <span data-ttu-id="720fa-227">**最初の転送日**</span><span class="sxs-lookup"><span data-stu-id="720fa-227">**First forward date**</span></span>

<span data-ttu-id="720fa-228">詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="720fa-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="720fa-229">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="720fa-230">メールフローの状態レポート</span><span class="sxs-lookup"><span data-stu-id="720fa-230">Mailflow status report</span></span>

<span data-ttu-id="720fa-231">Mailflow **状態レポートは**、送信済 [](#sent-and-received-email-report)みおよび受信済みメール レポートに似ています。エッジで許可またはブロックされた電子メールに関する追加情報を含む。</span><span class="sxs-lookup"><span data-stu-id="720fa-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="720fa-232">これは、エッジ保護情報を含む唯一のレポートであり、EOP (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量を示Exchange Online Protectionです。</span><span class="sxs-lookup"><span data-stu-id="720fa-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="720fa-233">メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="720fa-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="720fa-234">レポートを表示するには、コンプライアンス センターでセキュリティ &[を](https://protection.office.com)開き、[レポート **ダッシュボード]** に移動し、[メールフローの状態レポート \> ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="720fa-235">メール フローの状態レポートに **直接移動するには、** 開きます <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="720fa-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![レポート ダッシュボードのメールフロー状態レポート ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="720fa-237">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="720fa-238">レポートを開いた場合、[種類] **タブ** が既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="720fa-239">既定では、このビューにはグラフと、次のフィルターで構成されたデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="720fa-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="720fa-240">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="720fa-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="720fa-241">**方向**:</span><span class="sxs-lookup"><span data-stu-id="720fa-241">**Direction**:</span></span>

  - <span data-ttu-id="720fa-242">**受信**</span><span class="sxs-lookup"><span data-stu-id="720fa-242">**Inbound**</span></span>
  - <span data-ttu-id="720fa-243">**送信**</span><span class="sxs-lookup"><span data-stu-id="720fa-243">**Outbound**</span></span>
  - <span data-ttu-id="720fa-244">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="720fa-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="720fa-245">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別 **に\*\*\*\*カウント)**</span><span class="sxs-lookup"><span data-stu-id="720fa-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="720fa-246">**種類**:</span><span class="sxs-lookup"><span data-stu-id="720fa-246">**Type**:</span></span>

  - <span data-ttu-id="720fa-247">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="720fa-247">**Good mail**</span></span>
  - <span data-ttu-id="720fa-248">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="720fa-248">**Malware**</span></span>
  - <span data-ttu-id="720fa-249">**スパム**</span><span class="sxs-lookup"><span data-stu-id="720fa-249">**Spam**</span></span>
  - <span data-ttu-id="720fa-250">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="720fa-250">**Edge protection**</span></span>
  - <span data-ttu-id="720fa-251">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="720fa-251">**Rule messages**</span></span>
  - <span data-ttu-id="720fa-252">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="720fa-252">**Phishing email**</span></span>

<span data-ttu-id="720fa-253">グラフは、Type 値によって **整理** されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="720fa-254">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="720fa-255">データ テーブルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="720fa-255">The data table contains the following information:</span></span>

- <span data-ttu-id="720fa-256">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="720fa-256">**Direction**</span></span>
- <span data-ttu-id="720fa-257">**種類**</span><span class="sxs-lookup"><span data-stu-id="720fa-257">**Type**</span></span>
- <span data-ttu-id="720fa-258">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="720fa-258">**24 hours**</span></span>
- <span data-ttu-id="720fa-259">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="720fa-259">**3 days**</span></span>
- <span data-ttu-id="720fa-260">**7 日間**</span><span class="sxs-lookup"><span data-stu-id="720fa-260">**7 days**</span></span>
- <span data-ttu-id="720fa-261">**15 日**</span><span class="sxs-lookup"><span data-stu-id="720fa-261">**15 days**</span></span>
- <span data-ttu-id="720fa-262">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="720fa-262">**30 days**</span></span>

<span data-ttu-id="720fa-263">詳細については、[ **カテゴリの選択] をクリックすると**、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="720fa-264">**フィッシングメール**: この選択によって、脅威保護の [状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="720fa-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="720fa-265">**電子メール内のマルウェア**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="720fa-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="720fa-266">**スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="720fa-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="720fa-267">**エッジブロックスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="720fa-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="720fa-268">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="720fa-268">**Export**:</span></span>

<span data-ttu-id="720fa-269">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="720fa-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="720fa-270">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="720fa-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="720fa-271">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="720fa-272">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフローの状態レポートにビューを入力する](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="720fa-274">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="720fa-275">[方向] タブ **をクリックすると** 、[種類] ビューの同じ既定 **のフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="720fa-276">グラフは、方向の値 **によって整理** されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="720fa-277">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="720fa-278">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="720fa-279">データ テーブルには、Type ビューの同じ情報 **が含** まれている。</span><span class="sxs-lookup"><span data-stu-id="720fa-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="720fa-280">[ **使用可能な選択と動作** の詳細については、カテゴリを選択する] は、[種類] ビューと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="720fa-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="720fa-281">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="720fa-281">**Export**:</span></span>

<span data-ttu-id="720fa-282">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="720fa-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="720fa-283">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="720fa-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="720fa-284">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="720fa-285">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートの方向ビュー](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="720fa-287">メールフロー状態レポートのファネル ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="720fa-288">[ **ファネル** ] ビューには、Microsoft の電子メール脅威防止機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="720fa-289">電子メールの総数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策などの構成済みの脅威保護機能が、この数に与える影響の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="720fa-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="720fa-290">[ファネル] タブ **を** クリックすると、既定では、次のフィルターで構成されたグラフとデータ テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="720fa-291">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="720fa-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="720fa-292">**方向**:</span><span class="sxs-lookup"><span data-stu-id="720fa-292">**Direction**:</span></span>

  - <span data-ttu-id="720fa-293">**受信**</span><span class="sxs-lookup"><span data-stu-id="720fa-293">**Inbound**</span></span>
  - <span data-ttu-id="720fa-294">**送信**</span><span class="sxs-lookup"><span data-stu-id="720fa-294">**Outbound**</span></span>
  - <span data-ttu-id="720fa-295">**組織内**: この数は、テナント内で送信されるメッセージを示します。つまり、送信者は abc@domain.com に送信 xyz@domain.com (受信と送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="720fa-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="720fa-296">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="720fa-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="720fa-297">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="720fa-298">このグラフは、次の方法で整理されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="720fa-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="720fa-299">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="720fa-299">**Total email**</span></span>
- <span data-ttu-id="720fa-300">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="720fa-300">**Email after edge protection**</span></span>
- <span data-ttu-id="720fa-301">**マルウェア対策、ファイル評価、ファイルの種類ブロック後のメール**</span><span class="sxs-lookup"><span data-stu-id="720fa-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="720fa-302">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策の後のメール**</span><span class="sxs-lookup"><span data-stu-id="720fa-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="720fa-303">**スパム対策、バルク メール フィルター処理後のメール**</span><span class="sxs-lookup"><span data-stu-id="720fa-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="720fa-304">**ユーザーとドメインの偽装後のメール**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="720fa-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="720fa-305">**ファイルと URL の削除後の** メール <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="720fa-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="720fa-306">**配信後の保護後に良性として検出された電子メール (URL クリック時間保護)**</span><span class="sxs-lookup"><span data-stu-id="720fa-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="720fa-307"><sup>1</sup> Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="720fa-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="720fa-308">EOP または Defender でフィルター処理されたメールを個別Office 365表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="720fa-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="720fa-309">データ テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="720fa-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="720fa-310">**Date**</span><span class="sxs-lookup"><span data-stu-id="720fa-310">**Date**</span></span>
- <span data-ttu-id="720fa-311">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="720fa-311">**Total email**</span></span>
- <span data-ttu-id="720fa-312">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="720fa-312">**Edge protection**</span></span>
- <span data-ttu-id="720fa-313">**マルウェア対策、ファイル評価、ファイルの種類ブロック**:</span><span class="sxs-lookup"><span data-stu-id="720fa-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="720fa-314">**ファイル評価**: 他の Microsoft のお客様が添付ファイルを識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="720fa-315">**ファイルの種類のブロック**: メッセージで識別された悪意のあるファイルの種類によってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="720fa-316">**フィッシング対策、URL レピュテーション、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="720fa-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="720fa-317">**URL レピュ** テーション : 他の Microsoft のお客様による URL の識別のためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="720fa-318">**ブランド偽装**: よく知られているブランド偽装送信者からのメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="720fa-319">**スプーフィング** 対策: 受信者が属するドメイン、またはメッセージ送信者が所有していないドメインをスプーフィングしようとするメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="720fa-320">**スパム対策、バルク メール フィルター**:</span><span class="sxs-lookup"><span data-stu-id="720fa-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="720fa-321">**バルク メール フィルター :** 受信者にバルク メールを配信しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="720fa-322">**ユーザーとドメインの偽装 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="720fa-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="720fa-323">**ユーザー偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているユーザー (メッセージ送信者) を偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="720fa-324">**ドメイン偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているドメインを偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="720fa-325">**ファイルと URL のデトレーション (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="720fa-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="720fa-326">**ファイルの削除**: 添付ファイル ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="720fa-327">**URL の削除**: リンク ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="720fa-328">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**: ZAP は 0 時間の自動削除を示します。</span><span class="sxs-lookup"><span data-stu-id="720fa-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="720fa-329">データ テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="720fa-330">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="720fa-330">**Export**:</span></span>

<span data-ttu-id="720fa-331">[オプション] で **[エクスポート]** **をクリック** すると、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="720fa-332">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="720fa-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="720fa-333">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="720fa-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="720fa-334">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="720fa-335">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="720fa-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="720fa-336">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="720fa-337">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![メールフロー状態レポートのファネル ビュー](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="720fa-339">メールフローの状態レポートの技術ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="720fa-340">Tech **ビューは、** ファネル **ビューに** 似ています。構成済みの脅威保護機能の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="720fa-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="720fa-341">グラフから、脅威保護の異なる段階でメッセージがどのように分類されるのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="720fa-342">[Tech view] **タブを** クリックすると、既定では、このビューにはグラフと、次のフィルターで構成されたデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="720fa-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="720fa-343">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="720fa-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="720fa-344">**方向**:</span><span class="sxs-lookup"><span data-stu-id="720fa-344">**Direction**:</span></span>

  - <span data-ttu-id="720fa-345">**受信**</span><span class="sxs-lookup"><span data-stu-id="720fa-345">**Inbound**</span></span>
  - <span data-ttu-id="720fa-346">**送信**</span><span class="sxs-lookup"><span data-stu-id="720fa-346">**Outbound**</span></span>
  - <span data-ttu-id="720fa-347">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="720fa-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="720fa-348">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="720fa-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="720fa-349">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="720fa-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="720fa-350">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="720fa-351">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="720fa-352">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="720fa-352">**Total email**</span></span>
- <span data-ttu-id="720fa-353">**エッジ許可** と **フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="720fa-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="720fa-354">**マルウェアではない\*\*\*\*、セーフ添付ファイルの検出、** <sup>\*</sup> **マルウェア対策エンジンの検出**、**およびルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="720fa-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="720fa-355">**フィッシング** **、DMARC 障害、\*\*\*\*偽装検出、ス** プーフィング **検出**、**およびフィッシングの検出を行う**</span><span class="sxs-lookup"><span data-stu-id="720fa-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="720fa-356">**URL のデトレーションと URL の** デトレーション **検出による検出なし**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="720fa-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="720fa-357">**スパムとスパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="720fa-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="720fa-358">**悪意のあるメール以外の電子\*\*\*\*メール、セーフリンクの検出** <sup>\*</sup> 、**および ZAP**</span><span class="sxs-lookup"><span data-stu-id="720fa-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="720fa-359"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="720fa-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="720fa-360">グラフ内のカテゴリにカーソルを合わせると、そのカテゴリ内のメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="720fa-361">データ テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="720fa-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="720fa-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="720fa-362">**Date**</span></span>
- <span data-ttu-id="720fa-363">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="720fa-363">**Total email**</span></span>
- <span data-ttu-id="720fa-364">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="720fa-364">**Edge filtered**</span></span>
- <span data-ttu-id="720fa-365">**マルウェア対策エンジン、セーフ添付ファイル、フィルター処理されたルール**:</span><span class="sxs-lookup"><span data-stu-id="720fa-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="720fa-366">**フィルター処理されたルール**: メール フロー ルール (トランスポート ルールとも呼ばれる) が原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="720fa-367">**DMARC、偽装、スプーフィング、フィッシング フィルター**:</span><span class="sxs-lookup"><span data-stu-id="720fa-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="720fa-368">**DMARC**: DMARC 認証チェックに失敗したメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="720fa-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="720fa-369">**URL のデトレーション検出**</span><span class="sxs-lookup"><span data-stu-id="720fa-369">**URL detonation detection**</span></span>
- <span data-ttu-id="720fa-370">**フィルター処理されたスパム対策**</span><span class="sxs-lookup"><span data-stu-id="720fa-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="720fa-371">**ZAP が削除されました**</span><span class="sxs-lookup"><span data-stu-id="720fa-371">**ZAP removed**</span></span>
- <span data-ttu-id="720fa-372">**リンクによるセーフ検出**</span><span class="sxs-lookup"><span data-stu-id="720fa-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="720fa-373">データ テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="720fa-374">**エクスポート**:</span><span class="sxs-lookup"><span data-stu-id="720fa-374">**Export**:</span></span>

<span data-ttu-id="720fa-375">[エクスポート] **をクリックすると**、[ **オプション] で** 、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="720fa-376">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="720fa-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="720fa-377">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="720fa-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="720fa-378">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="720fa-379">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="720fa-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="720fa-380">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="720fa-381">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![メールフロー状態レポートの技術ビュー](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="720fa-383">送信および受信した電子メール レポート</span><span class="sxs-lookup"><span data-stu-id="720fa-383">Sent and received email report</span></span>

<span data-ttu-id="720fa-384">送信 **および受信電子** メール レポートは、スパム検出、マルウェア、および "良い" と識別された電子メールを含む、受信および送信メールに関する情報を示すスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="720fa-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="720fa-385">このレポートと [Mailflow](#mailflow-status-report) 状態レポートの違いは、このレポートにエッジ保護によってブロックされたメッセージに関するデータは含まれておりない点です。</span><span class="sxs-lookup"><span data-stu-id="720fa-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="720fa-386">**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="720fa-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="720fa-387">レポートの集計ビューと詳細ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="720fa-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="720fa-388">レポートを表示するには、セキュリティ & コンプライアンス センターを [開](https://protection.office.com)き、[レポートダッシュボード] に移動し、[送信メールと受信メール \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="720fa-389">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="720fa-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![レポート ダッシュボードの送信および受信メール ウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="720fa-391">送信および受信電子メール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="720fa-392">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="720fa-393">**分類: タイプ : グラフ** には、使用可能なすべてのカテゴリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="720fa-394">**合計**</span><span class="sxs-lookup"><span data-stu-id="720fa-394">**Total**</span></span>
  - <span data-ttu-id="720fa-395">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="720fa-395">**Good mail**</span></span>
  - <span data-ttu-id="720fa-396">**マルウェア (マルウェア対策)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="720fa-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="720fa-397">**スパム検出**</span><span class="sxs-lookup"><span data-stu-id="720fa-397">**Spam detections**</span></span>
  - <span data-ttu-id="720fa-398">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="720fa-398">**Rule messages**</span></span>
  - <span data-ttu-id="720fa-399">**高度なマルウェア**(Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="720fa-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="720fa-400">グラフで 1 日 (データ ポイント) にカーソルを合わせると、その日の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信および受信電子メール レポートにビューを入力する](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="720fa-402">**[ブレークダウン]: [方向]**: グラフには、 **合計** データ、 **受信** データ、および **送信データが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="720fa-403">グラフで 1 日 (データ ポイント) にカーソルを合わせると、その日の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![送信および受信電子メール レポートの方向ビュー](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="720fa-405">**ドリルダウン** \>**マルウェア (マルウェア対策)**: この選択により、マルウェア検出 [レポートが表示されます](view-email-security-reports.md#malware-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="720fa-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="720fa-406">**ドリルダウン** \>**スパム検出)**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="720fa-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="720fa-407">レポート ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="720fa-408">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="720fa-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="720fa-409">方向の値</span><span class="sxs-lookup"><span data-stu-id="720fa-409">Direction values</span></span>
- <span data-ttu-id="720fa-410">型の値</span><span class="sxs-lookup"><span data-stu-id="720fa-410">Type values</span></span>

<span data-ttu-id="720fa-411">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="720fa-412">送信および受信電子メール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="720fa-413">[別の **方向] または [** 方向] の [方向 **]** ビューで [詳細テーブルの表示] をクリック **すると** 、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="720fa-414">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="720fa-414">**Date (UTC)**</span></span>
- <span data-ttu-id="720fa-415">**種類**</span><span class="sxs-lookup"><span data-stu-id="720fa-415">**Type**</span></span>
- <span data-ttu-id="720fa-416">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="720fa-416">**Direction**</span></span>
- <span data-ttu-id="720fa-417">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="720fa-417">**Message count**</span></span>

<span data-ttu-id="720fa-418">詳細テーブル ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="720fa-419">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="720fa-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="720fa-420">方向の値</span><span class="sxs-lookup"><span data-stu-id="720fa-420">Direction values</span></span>
- <span data-ttu-id="720fa-421">型の値</span><span class="sxs-lookup"><span data-stu-id="720fa-421">Type values</span></span>

<span data-ttu-id="720fa-422">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="720fa-423">上位の送信者と受信者レポート</span><span class="sxs-lookup"><span data-stu-id="720fa-423">Top senders and recipients report</span></span>

<span data-ttu-id="720fa-424">[ **上位の送信者と受信者]** レポートは、上位のメール送信者と受信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="720fa-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="720fa-425">レポートを表示するには、セキュリティ & コンプライアンス センターを [開き、[](https://protection.office.com)レポートダッシュボード] に移動し、[上位の送信者と受信者] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="720fa-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="720fa-426">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="720fa-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![レポート ダッシュボードの上位の送信者と受信者ウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="720fa-428">上位の送信者と受信者レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="720fa-429">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="720fa-430">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="720fa-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="720fa-431">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="720fa-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="720fa-432">**上位のスパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="720fa-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="720fa-433">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="720fa-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="720fa-434">**上位マルウェア受信者 \> のデータを表示する (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="720fa-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="720fa-435">円グラフの構成は、これらの選択内容に基づいて変更されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="720fa-436">円グラフのくさびの上にマウス ポインターを置くと、送信または受信されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="720fa-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="720fa-437">レポート ビューで **[フィルター]** をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="720fa-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![上位の送信者と受信者レポートのレポート ビューの円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="720fa-439">上位の送信者と受信者レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="720fa-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="720fa-440">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="720fa-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="720fa-441">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="720fa-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="720fa-442">**上位のメール送信者**</span><span class="sxs-lookup"><span data-stu-id="720fa-442">**Top mail senders**</span></span>
  - <span data-ttu-id="720fa-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="720fa-443">**Count**</span></span>

- <span data-ttu-id="720fa-444">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="720fa-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="720fa-445">**上位のメール受信者**</span><span class="sxs-lookup"><span data-stu-id="720fa-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="720fa-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="720fa-446">**Count**</span></span>

- <span data-ttu-id="720fa-447">**上位のスパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="720fa-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="720fa-448">**上位のスパム受信者**</span><span class="sxs-lookup"><span data-stu-id="720fa-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="720fa-449">**Count**</span><span class="sxs-lookup"><span data-stu-id="720fa-449">**Count**</span></span>

- <span data-ttu-id="720fa-450">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="720fa-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="720fa-451">**上位のマルウェア受信者**</span><span class="sxs-lookup"><span data-stu-id="720fa-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="720fa-452">**Count**</span><span class="sxs-lookup"><span data-stu-id="720fa-452">**Count**</span></span>

- <span data-ttu-id="720fa-453">**上位マルウェア受信者 \> のデータを表示する (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="720fa-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="720fa-454">**上位のマルウェア受信者 (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="720fa-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="720fa-455">**Count**</span><span class="sxs-lookup"><span data-stu-id="720fa-455">**Count**</span></span>

<span data-ttu-id="720fa-456">詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="720fa-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="720fa-457">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="720fa-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="720fa-458">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="720fa-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="720fa-459">この記事で説明するレポートを表示および使用するには、セキュリティ コンプライアンス センターで次のいずれかの役割グループの&必要があります。</span><span class="sxs-lookup"><span data-stu-id="720fa-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="720fa-460">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="720fa-460">**Organization Management**</span></span>
- <span data-ttu-id="720fa-461">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="720fa-461">**Security Administrator**</span></span>
- <span data-ttu-id="720fa-462">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="720fa-462">**Security Reader**</span></span>
- <span data-ttu-id="720fa-463">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="720fa-463">**Global Reader**</span></span>

<span data-ttu-id="720fa-464">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="720fa-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="720fa-465">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="720fa-466">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="720fa-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="720fa-467">関連項目</span><span class="sxs-lookup"><span data-stu-id="720fa-467">Related topics</span></span>

[<span data-ttu-id="720fa-468">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="720fa-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="720fa-469">セキュリティとコンプライアンス センターのメッセージ追跡の分析情報</span><span class="sxs-lookup"><span data-stu-id="720fa-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="720fa-470">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="720fa-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="720fa-471">Microsoft Defender for microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="720fa-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
