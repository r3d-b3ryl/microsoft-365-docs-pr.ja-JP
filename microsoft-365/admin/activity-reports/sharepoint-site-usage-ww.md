---
title: 管理センターの Microsoft 365 レポート-SharePoint サイトの使用状況
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Sharepoint サイトの利用状況レポートを取得して、ユーザーが SharePoint サイトに格納しているファイルの数、アクティブに使用されている数、および使用されている記憶域の合計量を把握します。
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649828"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a><span data-ttu-id="bf4ff-103">管理センターの Microsoft 365 レポート-SharePoint サイトの使用状況</span><span class="sxs-lookup"><span data-stu-id="bf4ff-103">Microsoft 365 Reports in the admin center - SharePoint site usage</span></span>

<span data-ttu-id="bf4ff-104">Microsoft 365 admin としての **レポート** ダッシュボードには、組織内のさまざまな製品におけるアクティビティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-104">As a Microsoft 365 admin, the **Reports** dashboard shows you the activity overview across various products in your organization.</span></span> <span data-ttu-id="bf4ff-105">これにより、各製品に固有のアクティビティについてより詳しく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-105">It enables you to drill in to get more granular insight about the activities specific to each product.</span></span> <span data-ttu-id="bf4ff-106">たとえば、ユーザーが SharePoint サイトに保存するファイルの合計数、アクティブに使用されているファイルの数、およびこれらすべてのサイトにわたって使用される記憶域の観点から、SharePoint から得られる価値の概要をとらえることができます。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-106">For example, you can get a high level view of the value you are getting from SharePoint in terms of the total number of files that users store in SharePoint sites, how many files are actively being used, and the storage consumed across all these sites.</span></span> <span data-ttu-id="bf4ff-107">その後、[SharePoint サイトの利用状況] レポートを詳細に確認して、すべてのサイトの傾向およびサイトごとのレベル詳細を把握できます。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-107">Then, you can drill into the SharePoint site usage report to understand the trends and per site level details for all sites.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bf4ff-108">レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-108">You must be a global administrator, global reader or reports reader in Microsoft 365 or an Exchange, SharePoint, Teams Service, Teams Communications, or Skype for Business administrator to see reports.</span></span>
<span data-ttu-id="bf4ff-109">管理センターの Microsoft 365 レポートは、GCC High および DoD テナントではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-109">Microsoft 365 Reports in the admin center is not supported for GCC High and DoD tenants.</span></span>
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a><span data-ttu-id="bf4ff-110">[SharePoint サイトの利用状況] レポートにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="bf4ff-110">How to get to the SharePoint site usage report</span></span>

1. <span data-ttu-id="bf4ff-111">管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-111">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
2. <span data-ttu-id="bf4ff-112">ダッシュボードのホームページから、SharePoint カードの [ **詳細を表示** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-112">From the dashboard homepage, click on the **View more** button on the SharePoint card.</span></span>
  
## <a name="interpret-the-sharepoint-site-usage-report"></a><span data-ttu-id="bf4ff-113">SharePoint サイトの利用状況レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="bf4ff-113">Interpret the SharePoint site usage report</span></span>

<span data-ttu-id="bf4ff-114">SharePoint レポートでサイトの利用状況を表示するには、[ **サイトの利用状況** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-114">You can view the site usage in the SharePoint report by choosing the **Site usage** tab.</span></span><br/><span data-ttu-id="bf4ff-115">![Microsoft 365 レポート-Microsoft SharePoint サイトの利用状況レポート。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)</span><span class="sxs-lookup"><span data-stu-id="bf4ff-115">![Microsoft 365 reports - Microsoft SharePoint site usage report.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)</span></span>

<span data-ttu-id="bf4ff-116">レポートに列を追加または削除するには、[ **列の選択** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-116">Select **Choose columns** to add or remove columns from the report.</span></span>  <br/> <span data-ttu-id="bf4ff-117">![SharePoint サイトの利用状況レポート-列の選択](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)</span><span class="sxs-lookup"><span data-stu-id="bf4ff-117">![SharePoint site usage report - choose columns](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)</span></span>

<span data-ttu-id="bf4ff-118">また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-118">You can also export the report data into an Excel .csv file by selecting the **Export** link.</span></span> <span data-ttu-id="bf4ff-119">これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-119">This exports data of all users and enables you to do simple sorting and filtering for further analysis.</span></span> <span data-ttu-id="bf4ff-120">ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-120">If you have less than 2000 users, you can sort and filter within the table in the report itself.</span></span> <span data-ttu-id="bf4ff-121">ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-121">If you have more than 2000 users, in order to filter and sort, you will need to export the data.</span></span> 
  
|<span data-ttu-id="bf4ff-122">アイテム</span><span class="sxs-lookup"><span data-stu-id="bf4ff-122">Item</span></span>|<span data-ttu-id="bf4ff-123">説明</span><span class="sxs-lookup"><span data-stu-id="bf4ff-123">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf4ff-124">**測定基準**</span><span class="sxs-lookup"><span data-stu-id="bf4ff-124">**Metric**</span></span>|<span data-ttu-id="bf4ff-125">**定義**</span><span class="sxs-lookup"><span data-stu-id="bf4ff-125">**Definition**</span></span>|
|<span data-ttu-id="bf4ff-126">サイトの URL</span><span class="sxs-lookup"><span data-stu-id="bf4ff-126">Site URL</span></span>  <br/> |<span data-ttu-id="bf4ff-127">サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-127">The full URL of the site.</span></span> <br/> |
|<span data-ttu-id="bf4ff-128">Deleted</span><span class="sxs-lookup"><span data-stu-id="bf4ff-128">Deleted</span></span>  <br/> |<span data-ttu-id="bf4ff-129">サイトの削除状態。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-129">The deletion status of the site.</span></span> <span data-ttu-id="bf4ff-130">サイトを削除済みとしてマークするには、少なくとも 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-130">It takes at least 7 days for sites to be marked as deleted.</span></span>  <br/> |
|<span data-ttu-id="bf4ff-131">サイト所有者</span><span class="sxs-lookup"><span data-stu-id="bf4ff-131">Site owner</span></span>  <br/> |<span data-ttu-id="bf4ff-132">サイトのプライマリ所有者のユーザー名。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-132">The username of the primary owner of the site.</span></span>   <br/> |
|<span data-ttu-id="bf4ff-133">サイト所有者のプリンシパル名</span><span class="sxs-lookup"><span data-stu-id="bf4ff-133">Site owner principal name</span></span>  <br/> |<span data-ttu-id="bf4ff-134">サイトの所有者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-134">The email address of the owner of the site.</span></span> <br/> |
|<span data-ttu-id="bf4ff-135">最後のアクティビティの日付 (UTC)</span><span class="sxs-lookup"><span data-stu-id="bf4ff-135">Last activity date (UTC)</span></span>  <br/> | <span data-ttu-id="bf4ff-136">ファイルアクティビティが最後に検出された日付、またはサイトでページが表示された日付。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-136">The date of the last time file activity was detected or a page was viewed on the site.</span></span>  <br/> |
|<span data-ttu-id="bf4ff-137">ファイル</span><span class="sxs-lookup"><span data-stu-id="bf4ff-137">Files</span></span>  <br/> |<span data-ttu-id="bf4ff-138">サイト上のファイルの数。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-138">The number of files on the site.</span></span> <br/>|
|<span data-ttu-id="bf4ff-139">作業中のファイル</span><span class="sxs-lookup"><span data-stu-id="bf4ff-139">Active files</span></span>  <br/> | <span data-ttu-id="bf4ff-140">サイト上のアクティブなファイルの数。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-140">The number of active files on the site.</span></span><br/> <span data-ttu-id="bf4ff-141">注: レポートに指定された期間中にファイルが削除された場合、レポートに表示されるアクティブなファイルの数が、サイト上の現在のファイル数を超えることがあります。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-141">NOTE: If files were removed during the specified time period for the report, the number of active files shown in the report may be larger than the current number of files on the site.</span></span>  <br/> |
|<span data-ttu-id="bf4ff-142">使用済み記憶域 (MB)</span><span class="sxs-lookup"><span data-stu-id="bf4ff-142">Storage used (MB)</span></span>  <br/> |<span data-ttu-id="bf4ff-143">サイトで現在使用されている記憶域の容量。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-143">The amount of storage currently being used on the site.</span></span>  <br/>|
|<span data-ttu-id="bf4ff-144">割り当て済み記憶域 (MB)</span><span class="sxs-lookup"><span data-stu-id="bf4ff-144">Storage allocated (MB)</span></span>  <br/> |<span data-ttu-id="bf4ff-145">サイトに割り当てられている記憶域の最大容量。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-145">The maximum amount of storage allocated for the site.</span></span>  <br/>|
|<span data-ttu-id="bf4ff-146">ページビュー</span><span class="sxs-lookup"><span data-stu-id="bf4ff-146">Page views</span></span>  <br/> |<span data-ttu-id="bf4ff-147">サイトでページが表示された回数。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-147">The number of times pages were viewed on the site.</span></span>  <br/>|
|<span data-ttu-id="bf4ff-148">アクセスしたページ</span><span class="sxs-lookup"><span data-stu-id="bf4ff-148">Pages visited</span></span>  <br/> |<span data-ttu-id="bf4ff-149">サイト上でアクセスされた一意のページの数。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-149">The number of unique pages that were visited on the site.</span></span>  <br/>|
|<span data-ttu-id="bf4ff-150">ルート Web テンプレート</span><span class="sxs-lookup"><span data-stu-id="bf4ff-150">Root Web Template</span></span>  <br/> |<span data-ttu-id="bf4ff-151">サイトの作成に使用するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-151">The template used for creating the site.</span></span>  <br/> <span data-ttu-id="bf4ff-152">注: 異なるサイトの種類でデータをフィルター処理する場合は、データをエクスポートし、[ルート Web テンプレート] 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf4ff-152">NOTE: If you want to filter the data by different site types, then export the data and use the Root Web Template column.</span></span> |
|||