---
title: ラベル分析によるラベル使用状況の表示
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 最もよく使用される保持ラベルと機密ラベルはどれか、どこに適用されているかをすばやく確認する方法について説明します。
ms.openlocfilehash: 89ccdce54b0d7e6146260037b8dcb085631b408e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817506"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="f3ccf-103">ラベル分析によるラベル使用状況の表示</span><span class="sxs-lookup"><span data-stu-id="f3ccf-103">View label usage with label analytics</span></span>

<span data-ttu-id="f3ccf-104">保持ラベルと機密ラベルを作成した後に、テナント全体でどのように使用されているかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-104">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="f3ccf-105">Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのラベル分析で、どのラベルが最もよく使われているか、どこで適用されているかを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-105">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="f3ccf-106">たとえば、ラベル分析で次を確認できます:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-106">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="f3ccf-107">コンテンツに適用された保持ラベルと機密ラベルの合計数。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-107">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="f3ccf-108">上位のラベルと各ラベルの適用回数。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-108">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="f3ccf-109">ラベルの適用場所と、各場所での適用回数。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-109">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="f3ccf-110">保持レベルが変更または削除されたファイルとフォルダーの数。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-110">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="f3ccf-111">ラベル分析は、[[Microsoft 365 コンプライアンス センター]](https://compliance.microsoft.com/labelanalytics) または [[Microsoft 365 セキュリティ センター]](https://security.microsoft.com/labelanalytics)  >  **[分類]**  >  **[ラベル分析]** で確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-111">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![ラベル分析のページ](../media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="f3ccf-113">機密ラベルの使用状況</span><span class="sxs-lookup"><span data-stu-id="f3ccf-113">Sensitivity label usage</span></span>

<span data-ttu-id="f3ccf-114">機密ラベルの使用状況のデータは、Azure Information Protection のレポートから取得します。詳細については、「[Azure Information Protection の集中レポート](https://docs.microsoft.com/azure/information-protection/reports-aip)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-114">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="f3ccf-115">Azure Information Protection のレポートは、Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティセンターの機密ラベルに対するラベル分析にも適用される[前提条件](/azure/information-protection/reports-aip#prerequisites)があるのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-115">Note that the Azure Information Protection reports have [prerequisites](/azure/information-protection/reports-aip#prerequisites) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="f3ccf-116">たとえば、これらのレポートは Azure Information Protection のクライアントとスキャン プログラムから Azure Log Analytics サービスに基づいて集中管理された場所に情報保護の監視イベントを送信した結果なので、Log Analytics を含む Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-116">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="f3ccf-117">機密ラベルの使用状況は:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-117">For sensitivity label usage:</span></span>

- <span data-ttu-id="f3ccf-118">データの待機時間はありません。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-118">There is no latency in the data.</span></span> <span data-ttu-id="f3ccf-119">リアルタイムのレポートです。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-119">This is a real-time report.</span></span>
- <span data-ttu-id="f3ccf-120">上位の各ラベルの数を確認するには、棒グラフをポイントすると表示されるツール ヒントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-120">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="f3ccf-121">レポートでは、アプリごとに機密ラベルがどこに適用されているかを示します (保持ラベルは場所ごとに示されます)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-121">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![機密ラベルの使用状況レポート](../media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="f3ccf-123">保持ラベルの使用状況</span><span class="sxs-lookup"><span data-stu-id="f3ccf-123">Retention label usage</span></span>

<span data-ttu-id="f3ccf-124">このレポートでは、上位のラベルとそれがどこで適用されているかについてクイック ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-124">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="f3ccf-125">SharePoint や OneDrive のコンテンツがどのようにラベル付けされているかについての詳細は、「[ドキュメントのラベル アクティビティを表示する](view-label-activity-for-documents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-125">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="f3ccf-126">保持ラベルの使用状況は:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-126">For retention label usage:</span></span>

- <span data-ttu-id="f3ccf-127">データは、週ごとに集計されるため、データがレポートに表示されるまで最大 7 日間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-127">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="f3ccf-128">上位の各ラベルの数を確認するには、棒グラフをポイントすると表示されるツール ヒントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-128">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="f3ccf-129">レポートでは、場所ごとに保持ラベルがどこに適用されているかを示します (機密ラベルはアプリごとに示されます)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-129">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="f3ccf-130">保持レベルは、テナントの全期間のデータの概要で、特定の日付範囲にフィルター処理はされません。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-130">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="f3ccf-131">これに対し、[ラベル アクティビティ エクスプローラー](view-label-activity-for-documents.md)は、過去 30 日間のみのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-131">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![保持ラベルの使用状況レポート](../media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="f3ccf-133">特定の保持ラベルが付いたコンテンツをすべて表示する</span><span class="sxs-lookup"><span data-stu-id="f3ccf-133">View all content with a specific retention label</span></span>

<span data-ttu-id="f3ccf-134">保持ラベルの使用状況レポートから、そのラベルが適用されたすべてのコンテンツを簡単に参照することができます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-134">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="f3ccf-135">(この機能については、現在作業中のためすべてのラベル付けされたコンテンツを見るにはいくつかの手順が必要になります。)</span><span class="sxs-lookup"><span data-stu-id="f3ccf-135">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="f3ccf-136">最初に、レポートの下部にある **[詳細の表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-136">First, choose **View Details** at the bottom of the report.</span></span>

![保持ラベルの使用状況レポートの下部にある [詳細の表示] オプション](../media/retention-label-usage-view-details.png)

<span data-ttu-id="f3ccf-138">次に、保持ラベル > **右側のウィンドウの [アイテムを参照する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-138">Then choose a retention label > **Explore items** in the right pane.</span></span>

![右側のウィンドウの [アイテムを参照する] オプション](../media/retention-label-usage-explore-items.png)

<span data-ttu-id="f3ccf-140">そのラベルで、**[アクティビティ]** タブを選択すると、そのラベルの場所ごとのアイテム数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-140">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![保持ラベルの [アクティビティ] タブ](../media/retention-label-usage-activity-tab.png)

<span data-ttu-id="f3ccf-142">**[このラベルを含むアイテム]** タブも選択できます。それから、特定の場所について確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-142">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="f3ccf-143">Exchange Online では、メールボックスの一覧とメールボックスごとにラベルが付いたアイテムの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-143">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="f3ccf-144">SharePoint Online と OneDrive for Business では、サイト コレクションの一覧と、OneDrive アカウントをそれぞれの場所のラベル付けされたアイテムの数と合わせて確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-144">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="f3ccf-145">メールボックスまたはサイト コレクションを選択すると、その場所の保持ラベルを含むアイテムの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-145">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![[このラベルを含むアイテム] タブでその保持ラベルを持つすべてのアイテムを表示](../media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="f3ccf-147">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3ccf-147">Permissions</span></span>

<span data-ttu-id="f3ccf-148">ラベル分析を確認するには、Azure Active Directory で次のいずれかの役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-148">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="f3ccf-149">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="f3ccf-149">Global administrator</span></span>
- <span data-ttu-id="f3ccf-150">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="f3ccf-150">Compliance administrator</span></span>
- <span data-ttu-id="f3ccf-151">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="f3ccf-151">Security administrator</span></span>
- <span data-ttu-id="f3ccf-152">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="f3ccf-152">Security reader</span></span>

<span data-ttu-id="f3ccf-153">さらに、これらのレポートでは、Azure Monitor を使用して、組織が所有する Log Analytics ワークスペースにデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-153">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="f3ccf-154">そのため、データが格納されている Azure Monitor のワークスペースの閲覧者としてユーザーを追加しておく必要があります。詳細については、「[Azure Information Protection の分析に必要なアクセス許可](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-154">Therefore, the user should be added as a reader to the Azure Monitoring workspace that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>

