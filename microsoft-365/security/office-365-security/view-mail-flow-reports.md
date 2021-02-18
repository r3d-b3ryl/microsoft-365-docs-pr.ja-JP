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
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286719"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="e25f0-103">セキュリティ/コンプライアンス センターの [レポート] ダッシュボードでメール フロー &表示する</span><span class="sxs-lookup"><span data-stu-id="e25f0-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e25f0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e25f0-104">**Applies to**</span></span>
- [<span data-ttu-id="e25f0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e25f0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e25f0-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e25f0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e25f0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e25f0-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e25f0-108">セキュリティ & コンプライアンス センターのメール フロー[](mail-flow-insights-v2.md)ダッシュボードで使用できるメール フロー レポートに加えて、Microsoft 365 組織の監視に役立つさまざまな追加のメール フロー レポートをレポート ダッシュボードで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="e25f0-109">必要なアクセス許可 [がある](#what-permissions-are-needed-to-view-these-reports)場合は、レポート ダッシュボードに移動して、[](https://protection.office.com)セキュリティ/コンプライアンス センター&レポート **を表示** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e25f0-110">レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="e25f0-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ/コンプライアンス センター&ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="e25f0-112">コネクタ レポート</span><span class="sxs-lookup"><span data-stu-id="e25f0-112">Connector report</span></span>

<span data-ttu-id="e25f0-113">コネクタ **レポートには**、組織用に構成 [](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)されている受信コネクタと送信コネクタでのメール フロー アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="e25f0-114">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&レポート ダッシュボード **に移動し**、[コネクタ] \> レポート **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="e25f0-115">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="e25f0-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![レポート ダッシュボードのコネクタ レポート ウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="e25f0-117">コネクタ レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-117">Report view for the Connector report</span></span>

<span data-ttu-id="e25f0-118">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="e25f0-119">**データの表示方法: [メール フロー**]: このグラフは、次の方法で編成された受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="e25f0-120">**合計**</span><span class="sxs-lookup"><span data-stu-id="e25f0-120">**Total**</span></span>
  - <span data-ttu-id="e25f0-121">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="e25f0-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e25f0-122">**コネクタのないインターネットへ**</span><span class="sxs-lookup"><span data-stu-id="e25f0-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e25f0-123">構成した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="e25f0-124">グラフ内のデータを分離するには、コントロールのデータの表示を使用して、これらのオプションまたはすべてのメール フロー **のいずれかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![コネクタ レポートでメール フロー別にデータを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="e25f0-126">**データの表示:TLS 使用状況**: このグラフは、メール フローでのトランスポート層セキュリティ (TLS) バージョンの使用状況の割合を示しています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="e25f0-127">グラフ内のデータを分離するには、コントロールの [ **データ** の表示] を使用して、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="e25f0-128">**すべてのメール フロー**</span><span class="sxs-lookup"><span data-stu-id="e25f0-128">**All mail flow**</span></span>
  - <span data-ttu-id="e25f0-129">**コネクタのないインターネットから**</span><span class="sxs-lookup"><span data-stu-id="e25f0-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e25f0-130">**コネクタのないインターネットへ**</span><span class="sxs-lookup"><span data-stu-id="e25f0-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e25f0-131">構成した特定のコネクタ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-131">A specific connector that you've configured.</span></span>

  ![コネクタ レポートで TLS 使用法別にデータを表示する](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="e25f0-133">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="e25f0-134">コネクタ レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-134">Details table view for the Connector report</span></span>

<span data-ttu-id="e25f0-135">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e25f0-136">**日付**</span><span class="sxs-lookup"><span data-stu-id="e25f0-136">**Date**</span></span>
- <span data-ttu-id="e25f0-137">**コネクタの方向と名前**</span><span class="sxs-lookup"><span data-stu-id="e25f0-137">**Connector direction and name**</span></span>
- <span data-ttu-id="e25f0-138">**コネクタの種類**</span><span class="sxs-lookup"><span data-stu-id="e25f0-138">**Connector type**</span></span>
- <span data-ttu-id="e25f0-139">**強制 TLS?**: 値 **は True** または **False です**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="e25f0-140">**TLS なし** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="e25f0-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="e25f0-141">**TLS 1.0** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="e25f0-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="e25f0-142">**TLS 1.1** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="e25f0-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="e25f0-143">**TLS 1.2** (パーセンテージ)</span><span class="sxs-lookup"><span data-stu-id="e25f0-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="e25f0-144">**Volume**: メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="e25f0-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="e25f0-145">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e25f0-146">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="e25f0-147">Exchange トランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="e25f0-147">Exchange transport rule report</span></span>

<span data-ttu-id="e25f0-148">**Exchange トランスポート ルール レポートは**、組織内の受信および送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="e25f0-149">レポートを表示するには、セキュリティ/[](https://protection.office.com)コンプライアンス センター&開き、[**レポート** ダッシュボード] に移動し \> 、[Exchange トランスポート ルール **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="e25f0-150">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="e25f0-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![レポート ダッシュボードの Exchange トランスポート ルール ウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e25f0-152">Exchange トランスポート ルール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="e25f0-153">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="e25f0-154">**データの表示方法: Exchange トランスポート ルール** \>**[Break down by: Direction]**(方向):このグラフには、トランスポート ルールの影響を受けた受信メッセージと送信メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="e25f0-155">**データの表示方法: Exchange トランスポート ルール** \>**分類: 重大度 :** このグラフには、重大度の高と中の重大度、および重要度の低の **メッセージの数が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="e25f0-156">ルールのアクションとして重大度レベルを設定します **(この** ルールを重大度レベルまたは _SetAuditSeverity で監査します_)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="e25f0-157">詳細については [、「Exchange Online でのメール フロー ルールのアクション」を参照してください](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-157">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="e25f0-158">**データの表示方法: DLP Exchange トランスポート ルール** \>**[ブレークダウンバイ: 方向**]: このグラフは、データ損失防止 (DLP) トランスポート ルールの影響を受けた受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="e25f0-159">次のオプションをオンにすることで、グラフをさらに調整できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e25f0-160">**データの表示: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e25f0-161">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="e25f0-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e25f0-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e25f0-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="e25f0-163">**データの表示方法: DLP Exchange トランスポート ルール** \>**[Break down by: Direction**]  (方向): このビューには、DLPトランスポート ルールの影響を受けた重大度の高いメッセージと中程度の重大度のメッセージの数が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="e25f0-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="e25f0-164">次のオプションをオンにすることで、グラフをさらに調整できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e25f0-165">**データの表示: すべての DLP トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e25f0-166">**データの表示: 侵害されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="e25f0-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e25f0-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e25f0-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="e25f0-168">レポート ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="e25f0-169">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="e25f0-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="e25f0-170">方向の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-170">Direction values</span></span>
- <span data-ttu-id="e25f0-171">重要度の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-171">Severity values</span></span>

![Exchange トランスポート ルール レポートのレポート ビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e25f0-173">Exchange トランスポート ルール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="e25f0-174">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e25f0-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e25f0-175">**データの表示方法: Exchange トランスポート ルール**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="e25f0-176">**日付**</span><span class="sxs-lookup"><span data-stu-id="e25f0-176">**Date**</span></span>
  - <span data-ttu-id="e25f0-177">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-177">**Transport rule**</span></span>
  - <span data-ttu-id="e25f0-178">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-178">**Subject**</span></span>
  - <span data-ttu-id="e25f0-179">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-179">**Sender address**</span></span>
  - <span data-ttu-id="e25f0-180">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="e25f0-180">**Recipient address**</span></span>
  - <span data-ttu-id="e25f0-181">**重大度**</span><span class="sxs-lookup"><span data-stu-id="e25f0-181">**Severity**</span></span>
  - <span data-ttu-id="e25f0-182">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-182">**Direction**</span></span>

- <span data-ttu-id="e25f0-183">**データの表示方法: DLP Exchange トランスポート ルール**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="e25f0-184">**日付**</span><span class="sxs-lookup"><span data-stu-id="e25f0-184">**Date**</span></span>
  - <span data-ttu-id="e25f0-185">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="e25f0-185">**DLP policy**</span></span>
  - <span data-ttu-id="e25f0-186">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-186">**Transport rule**</span></span>
  - <span data-ttu-id="e25f0-187">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-187">**Subject**</span></span>
  - <span data-ttu-id="e25f0-188">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-188">**Sender address**</span></span>
  - <span data-ttu-id="e25f0-189">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="e25f0-189">**Recipient address**</span></span>
  - <span data-ttu-id="e25f0-190">**重大度**</span><span class="sxs-lookup"><span data-stu-id="e25f0-190">**Severity**</span></span>
  - <span data-ttu-id="e25f0-191">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-191">**Direction**</span></span>

<span data-ttu-id="e25f0-192">詳細テーブル ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e25f0-193">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="e25f0-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="e25f0-194">方向の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-194">Direction values</span></span>
- <span data-ttu-id="e25f0-195">重要度の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-195">Severity values</span></span>

<span data-ttu-id="e25f0-196">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="e25f0-197">転送レポート</span><span class="sxs-lookup"><span data-stu-id="e25f0-197">Forwarding report</span></span>

<span data-ttu-id="e25f0-198">転送 **レポートには、Exchange** Online メールボックスから外部ドメインに組織が自動的に転送したメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="e25f0-199">転送されたメッセージは、セキュリティまたはコンプライアンスのリスクを引き起し、アカウントが侵害された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e25f0-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="e25f0-200">レポートを表示するには、セキュリティ/コンプライアンス センターを [&レポート](https://protection.office.com)ダッシュボードに移動し、[転送 \> ] レポート **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="e25f0-201">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="e25f0-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![レポート ダッシュボードの転送レポート ウィジェット](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="e25f0-203">転送レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="e25f0-204">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e25f0-205">**転送方法のデータを表示する**: 次のメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="e25f0-206">**トランスポート ルール**: メール フロー ルール [とも呼ばれる](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-206">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="e25f0-207">**メールボックス ルール**: 受信トレイ ルール [とも呼ばれる](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![転送レポートの転送方法ビュー](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="e25f0-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span><span class="sxs-lookup"><span data-stu-id="e25f0-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![転送レポートの [ドメインの転送] ビュー](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="e25f0-211">**Show data for: Forwarders**: The following forwarders are shown:</span><span class="sxs-lookup"><span data-stu-id="e25f0-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="e25f0-212">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-212">**Transport rule**</span></span>
  - <span data-ttu-id="e25f0-213">転送受信トレイ ルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="e25f0-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![転送レポートのフォワーダー ビュー](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="e25f0-215">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="e25f0-216">転送レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="e25f0-217">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e25f0-218">**フォワーダー**: トランスポート ルール **の値、** または転送受信トレイ ルールを含むメールボックス。</span><span class="sxs-lookup"><span data-stu-id="e25f0-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="e25f0-219">**転送の種類**: メールボックス ルール **またはトランスポート ルール\*\*\*\*の値**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="e25f0-220">**受信者名**</span><span class="sxs-lookup"><span data-stu-id="e25f0-220">**Recipient name**</span></span>
- <span data-ttu-id="e25f0-221">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="e25f0-221">**Recipient domain**</span></span>
- <span data-ttu-id="e25f0-222">**詳細**: これは、メール フロー ルールの GUID 値、または受信トレイ ルールの RuleIdentity 値です。</span><span class="sxs-lookup"><span data-stu-id="e25f0-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="e25f0-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="e25f0-223">**Count**</span></span>
- <span data-ttu-id="e25f0-224">**最初の転送日**</span><span class="sxs-lookup"><span data-stu-id="e25f0-224">**First forward date**</span></span>

<span data-ttu-id="e25f0-225">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e25f0-226">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e25f0-227">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="e25f0-227">Mailflow status report</span></span>

<span data-ttu-id="e25f0-228">Mailflow **ステータス レポートは**、送信 [](#sent-and-received-email-report)済みおよび受信した電子メール レポートに似ていますが、エッジで許可またはブロックされた電子メールに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="e25f0-229">これは、エッジ保護情報を含む唯一のレポートであり、Exchange Online Protection (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量のみを示します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e25f0-230">メッセージが 5 人の受信者に送信された場合、1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされるという点を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e25f0-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="e25f0-231">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&ダッシュボードに移動し、[ \> **メールフロー] ステータス レポートを選択します**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="e25f0-232">メール フローの状態レポートに **直接移動するには、開** きます <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="e25f0-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![レポート ダッシュボードのメールフロー状態レポート ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="e25f0-234">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="e25f0-235">レポートを開いた場合、既定 **では [種類** ] タブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="e25f0-236">既定では、このビューには、次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e25f0-237">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="e25f0-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="e25f0-238">**方向**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-238">**Direction**:</span></span>

  - <span data-ttu-id="e25f0-239">**受信**</span><span class="sxs-lookup"><span data-stu-id="e25f0-239">**Inbound**</span></span>
  - <span data-ttu-id="e25f0-240">**送信**</span><span class="sxs-lookup"><span data-stu-id="e25f0-240">**Outbound**</span></span>
  - <span data-ttu-id="e25f0-241">**組織内**: この数は、テナント内のメッセージ (つまり、</span><span class="sxs-lookup"><span data-stu-id="e25f0-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e25f0-242">送信者abc@domain.com受信者に送信xyz@domain.com (受信および送信 **とは別に\*\*\*\*カウントされます**)</span><span class="sxs-lookup"><span data-stu-id="e25f0-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="e25f0-243">**型**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-243">**Type**:</span></span>

  - <span data-ttu-id="e25f0-244">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-244">**Good mail**</span></span>
  - <span data-ttu-id="e25f0-245">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="e25f0-245">**Malware**</span></span>
  - <span data-ttu-id="e25f0-246">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-246">**Spam**</span></span>
  - <span data-ttu-id="e25f0-247">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="e25f0-247">**Edge protection**</span></span>
  - <span data-ttu-id="e25f0-248">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="e25f0-248">**Rule messages**</span></span>
  - <span data-ttu-id="e25f0-249">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-249">**Phishing email**</span></span>

<span data-ttu-id="e25f0-250">グラフは Type 値で **構成** されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="e25f0-251">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="e25f0-252">データ テーブルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-252">The data table contains the following information:</span></span>

- <span data-ttu-id="e25f0-253">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-253">**Direction**</span></span>
- <span data-ttu-id="e25f0-254">**型**</span><span class="sxs-lookup"><span data-stu-id="e25f0-254">**Type**</span></span>
- <span data-ttu-id="e25f0-255">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="e25f0-255">**24 hours**</span></span>
- <span data-ttu-id="e25f0-256">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="e25f0-256">**3 days**</span></span>
- <span data-ttu-id="e25f0-257">**7 日**</span><span class="sxs-lookup"><span data-stu-id="e25f0-257">**7 days**</span></span>
- <span data-ttu-id="e25f0-258">**15 日**</span><span class="sxs-lookup"><span data-stu-id="e25f0-258">**15 days**</span></span>
- <span data-ttu-id="e25f0-259">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="e25f0-259">**30 days**</span></span>

<span data-ttu-id="e25f0-260">[カテゴリの **選択] をクリックして詳細を表示する** 場合は、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="e25f0-261">**フィッシング メール**: この選択によって、脅威保護の [状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e25f0-262">**電子メール内の** マルウェア : この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e25f0-263">**スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="e25f0-264">**エッジでブロックされたスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e25f0-265">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-265">**Export**:</span></span>

<span data-ttu-id="e25f0-266">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e25f0-267">したがって、データを 7 日間エクスポートする場合は、7 つの異なるエクスポート操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e25f0-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e25f0-268">エクスポートされる .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e25f0-269">その日のデータに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e25f0-270">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="e25f0-271">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="e25f0-272">[方向] タブ **をクリックすると** 、[種類] ビューの同じ **既定のフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="e25f0-273">グラフは方向の値で **構成** されています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="e25f0-274">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="e25f0-275">Type ビューの同 **じフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="e25f0-276">データ テーブルには、型ビューと同じ情報 **が含** まれる。</span><span class="sxs-lookup"><span data-stu-id="e25f0-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="e25f0-277">[ **カテゴリの選択] で使用可能な選択と** 動作の詳細については、[種類] ビューと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="e25f0-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="e25f0-278">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-278">**Export**:</span></span>

<span data-ttu-id="e25f0-279">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e25f0-280">したがって、データを 7 日間エクスポートする場合は、7 つの異なるエクスポート操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e25f0-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e25f0-281">エクスポートされる .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e25f0-282">その日のデータに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e25f0-283">メールフローステータス レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="e25f0-284">メールフローステータス レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="e25f0-285">じょう **ごビュー** には、Microsoft のメール脅威防止機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="e25f0-286">この記事では、メールの総数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策など、構成された脅威保護機能が、このカウントにどのような影響を与えるのかについて詳しく知っています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="e25f0-287">[ **じょう** ご] タブをクリックすると、既定では、このビューには次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e25f0-288">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="e25f0-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e25f0-289">**方向**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-289">**Direction**:</span></span>

  - <span data-ttu-id="e25f0-290">**受信**</span><span class="sxs-lookup"><span data-stu-id="e25f0-290">**Inbound**</span></span>
  - <span data-ttu-id="e25f0-291">**送信**</span><span class="sxs-lookup"><span data-stu-id="e25f0-291">**Outbound**</span></span>
  - <span data-ttu-id="e25f0-292">**組織内**: このカウントは、テナント内で送信されたメッセージに対して行います。つまり、送信者はabc@domain.com受信者に送信xyz@domain.com (受信と送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="e25f0-293">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="e25f0-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e25f0-294">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e25f0-295">このグラフは、次の方法で整理されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="e25f0-296">**Total email**</span><span class="sxs-lookup"><span data-stu-id="e25f0-296">**Total email**</span></span>
- <span data-ttu-id="e25f0-297">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-297">**Email after edge protection**</span></span>
- <span data-ttu-id="e25f0-298">**マルウェア対策、ファイル評価、ファイルの種類ブロック後のメール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="e25f0-299">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策の後のメール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="e25f0-300">**スパム対策、バルク メール フィルター後のメール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="e25f0-301">**ユーザーとドメインの偽装後の電子メール**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e25f0-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="e25f0-302">**ファイルおよび URL 分析後の**<sup>電子メール 1</sup></span><span class="sxs-lookup"><span data-stu-id="e25f0-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="e25f0-303">**配信後の保護後に良性として検出された電子メール (URL クリック時間保護)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="e25f0-304"><sup>365</sup> の場合のみ 1 Office Defender</span><span class="sxs-lookup"><span data-stu-id="e25f0-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="e25f0-305">EOP または Defender でフィルター処理された Office 365 を個別に表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e25f0-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="e25f0-306">データ テーブルには、降順で示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e25f0-307">**日付**</span><span class="sxs-lookup"><span data-stu-id="e25f0-307">**Date**</span></span>
- <span data-ttu-id="e25f0-308">**Total email**</span><span class="sxs-lookup"><span data-stu-id="e25f0-308">**Total email**</span></span>
- <span data-ttu-id="e25f0-309">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="e25f0-309">**Edge protection**</span></span>
- <span data-ttu-id="e25f0-310">**マルウェア対策、ファイル評価、ファイルの種類のブロック**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="e25f0-311">**ファイル評価**: 他の Microsoft ユーザーが添付ファイルを識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="e25f0-312">**ファイルの種類の** ブロック : メッセージで識別された悪意のあるファイルの種類のためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="e25f0-313">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="e25f0-314">**URL 評価**: 他の Microsoft ユーザーが URL を識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="e25f0-315">**ブランド偽装**: 既知のブランド偽装送信者からのメッセージのためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="e25f0-316">**スプーフィン** グ対策 : 受信者が属するドメインを偽装しようとするメッセージ、またはメッセージ送信者が所有していないドメインが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="e25f0-317">**スパム対策、バルク メール フィルター:**</span><span class="sxs-lookup"><span data-stu-id="e25f0-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="e25f0-318">**バルク メール フィルター**: 受信者にバルク メールを配信しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="e25f0-319">**ユーザーとドメインの偽装 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e25f0-320">**ユーザー偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているユーザー (メッセージ送信者) を偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="e25f0-321">**ドメイン偽装**: フィッシング詐欺対策ポリシーの偽装保護設定で定義されているドメインを偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="e25f0-322">**ファイルと URL の分析 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e25f0-323">**ファイル分析**: 安全な添付ファイル ポリシーによってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="e25f0-324">**URL デトレーション**: 安全なリンク ポリシーによってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="e25f0-325">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**: ZAP はゼロアワー自動消去を示します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="e25f0-326">データ テーブル内の行を選択すると、メールカウントの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e25f0-327">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-327">**Export**:</span></span>

<span data-ttu-id="e25f0-328">[オプション] で **[エクスポート\*\*\*\*] をクリック** すると、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="e25f0-329">**概要 (最大 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e25f0-330">**詳細 (最大 30 日間のデータ)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e25f0-331">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e25f0-332">現在のフィルターのデータが .csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e25f0-333">エクスポートされる .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e25f0-334">データに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e25f0-335">メールフローステータス レポートのじょうごビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="e25f0-336">メールフローの状態レポートのテクニカル ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="e25f0-337">Tech **ビューは** じょうごビューに **似ています。** 構成済みの脅威保護機能に関するより詳細な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="e25f0-338">グラフから、脅威保護の異なる段階でのメッセージの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="e25f0-339">[技術表示]タブをクリックすると、既定では、このビューには次のフィルターで構成されたグラフとデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e25f0-340">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="e25f0-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e25f0-341">**方向**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-341">**Direction**:</span></span>

  - <span data-ttu-id="e25f0-342">**受信**</span><span class="sxs-lookup"><span data-stu-id="e25f0-342">**Inbound**</span></span>
  - <span data-ttu-id="e25f0-343">**送信**</span><span class="sxs-lookup"><span data-stu-id="e25f0-343">**Outbound**</span></span>
  - <span data-ttu-id="e25f0-344">**組織内**: この数は、テナント内のメッセージ (つまり、</span><span class="sxs-lookup"><span data-stu-id="e25f0-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e25f0-345">送信者abc@domain.com受信者に送信するxyz@domain.com (受信と送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="e25f0-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="e25f0-346">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="e25f0-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e25f0-347">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e25f0-348">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="e25f0-349">**Total email**</span><span class="sxs-lookup"><span data-stu-id="e25f0-349">**Total email**</span></span>
- <span data-ttu-id="e25f0-350">**エッジの許可** と **フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="e25f0-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="e25f0-351">**マルウェアではない、\*\*\*\*安全な添付ファイルの検出** <sup>\*</sup> 、**マルウェア対策エンジンの検出**、**およびルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="e25f0-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="e25f0-352">**Not phish**, **DMARC failure**, **Impersonation detection**, Spoof **detection**, and **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="e25f0-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="e25f0-353">**URL デトレーションと URL デトレーション** 検出 **による検出なし**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e25f0-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="e25f0-354">**スパムおよびスパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="e25f0-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="e25f0-355">**悪意のあるメール以外、\*\*\*\*安全なリンクの検出** <sup>\*</sup> **、ZAP**</span><span class="sxs-lookup"><span data-stu-id="e25f0-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="e25f0-356"><sup>\*</sup> Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e25f0-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="e25f0-357">グラフのカテゴリにカーソルを合わせると、そのカテゴリ内のメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="e25f0-358">データ テーブルには、降順で示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e25f0-359">**日付**</span><span class="sxs-lookup"><span data-stu-id="e25f0-359">**Date**</span></span>
- <span data-ttu-id="e25f0-360">**Total email**</span><span class="sxs-lookup"><span data-stu-id="e25f0-360">**Total email**</span></span>
- <span data-ttu-id="e25f0-361">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="e25f0-361">**Edge filtered**</span></span>
- <span data-ttu-id="e25f0-362">**マルウェア対策エンジン、安全な添付ファイル、フィルター処理されたルール**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="e25f0-363">**フィルター処理されたルール**: メール フロー ルール (トランスポート ルールとも呼ばれる) が原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="e25f0-364">**DMARC, 偽装, スプーフィング, フィッシング フィルター:**</span><span class="sxs-lookup"><span data-stu-id="e25f0-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="e25f0-365">**DMARC**: メッセージが DMARC 認証チェックに失敗した場合にフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e25f0-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="e25f0-366">**URL デトレーション検出**</span><span class="sxs-lookup"><span data-stu-id="e25f0-366">**URL detonation detection**</span></span>
- <span data-ttu-id="e25f0-367">**フィルター処理されたスパム対策**</span><span class="sxs-lookup"><span data-stu-id="e25f0-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="e25f0-368">**ZAP の削除**</span><span class="sxs-lookup"><span data-stu-id="e25f0-368">**ZAP removed**</span></span>
- <span data-ttu-id="e25f0-369">**安全なリンクによる検出**</span><span class="sxs-lookup"><span data-stu-id="e25f0-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="e25f0-370">データ テーブル内の行を選択すると、メールカウントの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e25f0-371">**Export**:</span><span class="sxs-lookup"><span data-stu-id="e25f0-371">**Export**:</span></span>

<span data-ttu-id="e25f0-372">[エクスポート] **をクリック** すると、[オプション] **で** 次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="e25f0-373">**概要 (最大 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e25f0-374">**詳細 (最大 30 日間のデータ)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e25f0-375">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e25f0-376">現在のフィルターのデータが .csv ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e25f0-377">エクスポートされる .csv ファイルは、それぞれ 150,000 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="e25f0-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e25f0-378">データに 150,000 行を超える行が含まれる場合は、複数の .csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e25f0-379">メールフローの状態レポートのテクニカル ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e25f0-380">送信および受信メール レポート</span><span class="sxs-lookup"><span data-stu-id="e25f0-380">Sent and received email report</span></span>

<span data-ttu-id="e25f0-381">送信 **メール レポートと** 受信メール レポートは、スパム検出、マルウェア、"良好" と識別された電子メールなど、受信および送信電子メールに関する情報を表示するスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="e25f0-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="e25f0-382">このレポートとメールフローステータス[](#mailflow-status-report)レポートの違いは、エッジ保護によってブロックされるメッセージに関するデータが含まれるという点です。メッセージが 5 人の受信者に送信された場合、1 つのメッセージとしてカウントされるという点を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e25f0-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="e25f0-383">レポートの集計ビューと詳細ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="e25f0-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="e25f0-384">レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを&レポート ダッシュボードに移動し、[送信メールと受信メール \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="e25f0-385">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="e25f0-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![レポート ダッシュボードで送信および受信した電子メール ウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e25f0-387">送信および受信メール レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="e25f0-388">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e25f0-389">**分類: 種類 :** グラフには、利用可能なすべてのカテゴリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="e25f0-390">**合計**</span><span class="sxs-lookup"><span data-stu-id="e25f0-390">**Total**</span></span>
  - <span data-ttu-id="e25f0-391">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="e25f0-391">**Good mail**</span></span>
  - <span data-ttu-id="e25f0-392">**マルウェア (マルウェア対策)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e25f0-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="e25f0-393">**スパム検出**</span><span class="sxs-lookup"><span data-stu-id="e25f0-393">**Spam detections**</span></span>
  - <span data-ttu-id="e25f0-394">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="e25f0-394">**Rule messages**</span></span>
  - <span data-ttu-id="e25f0-395">**高度なマルウェア** (Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="e25f0-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="e25f0-396">グラフ内の 1 日 (データ ポイント) の上にマウス ポインターを移動すると、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![[送信メールと受信メール] レポートの種類ビュー](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="e25f0-398">**次の方法でブレーク ダウンします。方向**: グラフには、 **合計**、受信 **、** および **送信データが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="e25f0-399">グラフ内の 1 日 (データ ポイント) の上にマウス ポインターを移動すると、その日の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![[送信メールと受信メール] レポートの [方向] ビュー](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="e25f0-401">**ドリルダウン** \>**マルウェア (マルウェア対策)**: この選択により、メール レポートの [マルウェア検出にアクセスします](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="e25f0-402">**ドリルダウン** \>**スパム検出)**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="e25f0-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e25f0-403">レポート ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e25f0-404">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="e25f0-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="e25f0-405">方向の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-405">Direction values</span></span>
- <span data-ttu-id="e25f0-406">型の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-406">Type values</span></span>

<span data-ttu-id="e25f0-407">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e25f0-408">送信および受信メール レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="e25f0-409">[Break **down by:** Direction] (方向)**ビューまたは** **[Break down by: Direction]** (方向) ビューで [詳細の表示] テーブルをクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="e25f0-410">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-410">**Date (UTC)**</span></span>
- <span data-ttu-id="e25f0-411">**型**</span><span class="sxs-lookup"><span data-stu-id="e25f0-411">**Type**</span></span>
- <span data-ttu-id="e25f0-412">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="e25f0-412">**Direction**</span></span>
- <span data-ttu-id="e25f0-413">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="e25f0-413">**Message count**</span></span>

<span data-ttu-id="e25f0-414">詳細テーブル ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e25f0-415">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="e25f0-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="e25f0-416">方向の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-416">Direction values</span></span>
- <span data-ttu-id="e25f0-417">型の値</span><span class="sxs-lookup"><span data-stu-id="e25f0-417">Type values</span></span>

<span data-ttu-id="e25f0-418">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="e25f0-419">上位の送信者と受信者のレポート</span><span class="sxs-lookup"><span data-stu-id="e25f0-419">Top senders and recipients report</span></span>

<span data-ttu-id="e25f0-420">[ **上位の送信者と受信者** ] レポートは、上位のメールの送信者と受信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="e25f0-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="e25f0-421">レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを&レポート ダッシュボードに移動し、[上位の送信者と受信者 \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="e25f0-422">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="e25f0-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![レポート ダッシュボードの上位の送信者と受信者のウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e25f0-424">上位送信者と受信者レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="e25f0-425">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e25f0-426">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="e25f0-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="e25f0-427">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="e25f0-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="e25f0-428">**上位スパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="e25f0-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="e25f0-429">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e25f0-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="e25f0-430">**上位マルウェア受信者 \> のデータを表示する (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="e25f0-431">円グラフの構成は、これらの選択内容に基づいて変化します。</span><span class="sxs-lookup"><span data-stu-id="e25f0-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="e25f0-432">円グラフでくさびをポイントすると、送信または受信したメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="e25f0-433">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![上位の送信者と受信者レポートのレポート ビューの円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e25f0-435">上位送信者と受信者レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="e25f0-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="e25f0-436">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e25f0-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e25f0-437">**上位メール送信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="e25f0-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="e25f0-438">**上位メール送信者**</span><span class="sxs-lookup"><span data-stu-id="e25f0-438">**Top mail senders**</span></span>
  - <span data-ttu-id="e25f0-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="e25f0-439">**Count**</span></span>

- <span data-ttu-id="e25f0-440">**上位メール受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="e25f0-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="e25f0-441">**上位メール受信者**</span><span class="sxs-lookup"><span data-stu-id="e25f0-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="e25f0-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="e25f0-442">**Count**</span></span>

- <span data-ttu-id="e25f0-443">**上位スパム受信者 \> のデータを表示する**</span><span class="sxs-lookup"><span data-stu-id="e25f0-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="e25f0-444">**スパムの上位受信者**</span><span class="sxs-lookup"><span data-stu-id="e25f0-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="e25f0-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="e25f0-445">**Count**</span></span>

- <span data-ttu-id="e25f0-446">**データの表示 \> 上位マルウェア受信者** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e25f0-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="e25f0-447">**上位マルウェア受信者**</span><span class="sxs-lookup"><span data-stu-id="e25f0-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="e25f0-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="e25f0-448">**Count**</span></span>

- <span data-ttu-id="e25f0-449">**上位マルウェア受信者 \> のデータを表示する (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="e25f0-450">**上位マルウェア受信者 (Defender for Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e25f0-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="e25f0-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="e25f0-451">**Count**</span></span>

<span data-ttu-id="e25f0-452">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e25f0-453">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e25f0-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e25f0-454">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e25f0-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e25f0-455">この記事で説明されているレポートを表示して使用するには、セキュリティ/コンプライアンス センターの次のいずれかの役割グループのメンバー&があります。</span><span class="sxs-lookup"><span data-stu-id="e25f0-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e25f0-456">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="e25f0-456">**Organization Management**</span></span>
- <span data-ttu-id="e25f0-457">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="e25f0-457">**Security Administrator**</span></span>
- <span data-ttu-id="e25f0-458">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="e25f0-458">**Security Reader**</span></span>
- <span data-ttu-id="e25f0-459">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="e25f0-459">**Global Reader**</span></span>

<span data-ttu-id="e25f0-460">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25f0-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e25f0-461">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e25f0-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e25f0-462">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25f0-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e25f0-463">関連項目</span><span class="sxs-lookup"><span data-stu-id="e25f0-463">Related topics</span></span>

[<span data-ttu-id="e25f0-464">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="e25f0-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e25f0-465">セキュリティとコンプライアンス センターのメッセージ追跡の分析情報</span><span class="sxs-lookup"><span data-stu-id="e25f0-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="e25f0-466">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="e25f0-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="e25f0-467">Microsoft Defender for Office 365 のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="e25f0-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
