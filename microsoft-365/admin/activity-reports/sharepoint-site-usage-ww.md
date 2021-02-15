---
title: 管理センターでの Microsoft 365 レポート - SharePoint サイトの使用状況
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
description: SharePoint サイト利用状況レポートを取得して、ユーザーが SharePoint サイトに保存するファイルの数、アクティブに使用されているファイルの数、消費された記憶域の合計を確認します。
ms.openlocfilehash: 403ebfd75fca5ba5777832140155bb09734db3c7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233510"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a><span data-ttu-id="3d077-103">管理センターでの Microsoft 365 レポート - SharePoint サイトの使用状況</span><span class="sxs-lookup"><span data-stu-id="3d077-103">Microsoft 365 Reports in the admin center - SharePoint site usage</span></span>

<span data-ttu-id="3d077-104">Microsoft 365 管理者の **レポート** ダッシュボードには、組織内のさまざまな製品のアクティビティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d077-104">As a Microsoft 365 admin, the **Reports** dashboard shows you the activity overview across various products in your organization.</span></span> <span data-ttu-id="3d077-105">これにより、各製品に固有のアクティビティについてより詳しく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="3d077-105">It enables you to drill in to get more granular insight about the activities specific to each product.</span></span> <span data-ttu-id="3d077-106">たとえば、ユーザーが SharePoint サイトに保存するファイルの合計数、アクティブに使用されているファイルの数、およびこれらすべてのサイトにわたって使用される記憶域の観点から、SharePoint から得られる価値の概要をとらえることができます。</span><span class="sxs-lookup"><span data-stu-id="3d077-106">For example, you can get a high level view of the value you are getting from SharePoint in terms of the total number of files that users store in SharePoint sites, how many files are actively being used, and the storage consumed across all these sites.</span></span> <span data-ttu-id="3d077-107">その後、[SharePoint サイトの利用状況] レポートを詳細に確認して、すべてのサイトの傾向およびサイトごとのレベル詳細を把握できます。</span><span class="sxs-lookup"><span data-stu-id="3d077-107">Then, you can drill into the SharePoint site usage report to understand the trends and per site level details for all sites.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3d077-108">レポートを表示するには、グローバル管理者、Microsoft 365 のグローバル閲覧者またはレポート閲覧者、または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d077-108">You must be a global administrator, global reader or reports reader in Microsoft 365 or an Exchange, SharePoint, Teams Service, Teams Communications, or Skype for Business administrator to see reports.</span></span>
<span data-ttu-id="3d077-109">管理センターの Microsoft 365 レポートは、GCC High テナントと DoD テナントではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3d077-109">Microsoft 365 Reports in the admin center is not supported for GCC High and DoD tenants.</span></span>
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a><span data-ttu-id="3d077-110">[SharePoint サイトの利用状況] レポートにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="3d077-110">How to get to the SharePoint site usage report</span></span>

1. <span data-ttu-id="3d077-111">管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3d077-111">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
2. <span data-ttu-id="3d077-112">ダッシュボード ホームページで、SharePoint **カードの** [その他の表示] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d077-112">From the dashboard homepage, click on the **View more** button on the SharePoint card.</span></span>
  
## <a name="interpret-the-sharepoint-site-usage-report"></a><span data-ttu-id="3d077-113">SharePoint サイトの利用状況レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="3d077-113">Interpret the SharePoint site usage report</span></span>

<span data-ttu-id="3d077-114">[サイトの利用状況] タブを選択すると、SharePoint レポートでサイトの **利用状況を表示** できます。</span><span class="sxs-lookup"><span data-stu-id="3d077-114">You can view the site usage in the SharePoint report by choosing the **Site usage** tab.</span></span><br/><span data-ttu-id="3d077-115">![Microsoft 365 レポート - Microsoft SharePoint サイト利用状況レポート。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)</span><span class="sxs-lookup"><span data-stu-id="3d077-115">![Microsoft 365 reports - Microsoft SharePoint site usage report.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)</span></span>

<span data-ttu-id="3d077-116">[列 **の選択] を** 選択して、レポートに列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="3d077-116">Select **Choose columns** to add or remove columns from the report.</span></span>  <br/> <span data-ttu-id="3d077-117">![SharePoint サイト利用状況レポート - 列の選択](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)</span><span class="sxs-lookup"><span data-stu-id="3d077-117">![SharePoint site usage report - choose columns](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)</span></span>

<span data-ttu-id="3d077-118">また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3d077-118">You can also export the report data into an Excel .csv file by selecting the **Export** link.</span></span> <span data-ttu-id="3d077-119">これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。</span><span class="sxs-lookup"><span data-stu-id="3d077-119">This exports data of all users and enables you to do simple sorting and filtering for further analysis.</span></span> <span data-ttu-id="3d077-120">ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3d077-120">If you have less than 2000 users, you can sort and filter within the table in the report itself.</span></span> <span data-ttu-id="3d077-121">ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d077-121">If you have more than 2000 users, in order to filter and sort, you will need to export the data.</span></span> 
  
|<span data-ttu-id="3d077-122">アイテム</span><span class="sxs-lookup"><span data-stu-id="3d077-122">Item</span></span>|<span data-ttu-id="3d077-123">説明</span><span class="sxs-lookup"><span data-stu-id="3d077-123">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="3d077-124">**測定基準**</span><span class="sxs-lookup"><span data-stu-id="3d077-124">**Metric**</span></span>|<span data-ttu-id="3d077-125">**定義**</span><span class="sxs-lookup"><span data-stu-id="3d077-125">**Definition**</span></span>|
|<span data-ttu-id="3d077-126">サイトの URL</span><span class="sxs-lookup"><span data-stu-id="3d077-126">Site URL</span></span>  <br/> |<span data-ttu-id="3d077-127">サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="3d077-127">The full URL of the site.</span></span> <br/> |
|<span data-ttu-id="3d077-128">Deleted</span><span class="sxs-lookup"><span data-stu-id="3d077-128">Deleted</span></span>  <br/> |<span data-ttu-id="3d077-129">サイトの削除状態。</span><span class="sxs-lookup"><span data-stu-id="3d077-129">The deletion status of the site.</span></span> <span data-ttu-id="3d077-130">サイトを削除済みとしてマークするには、少なくとも 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="3d077-130">It takes at least 7 days for sites to be marked as deleted.</span></span>  <br/> |
|<span data-ttu-id="3d077-131">サイト所有者</span><span class="sxs-lookup"><span data-stu-id="3d077-131">Site owner</span></span>  <br/> |<span data-ttu-id="3d077-132">サイトのプライマリ所有者のユーザー名。</span><span class="sxs-lookup"><span data-stu-id="3d077-132">The username of the primary owner of the site.</span></span>   <br/> |
|<span data-ttu-id="3d077-133">サイト所有者のプリンシパル名</span><span class="sxs-lookup"><span data-stu-id="3d077-133">Site owner principal name</span></span>  <br/> |<span data-ttu-id="3d077-134">サイトの所有者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="3d077-134">The email address of the owner of the site.</span></span> <br/> |
|<span data-ttu-id="3d077-135">最後のアクティビティの日付 (UTC)</span><span class="sxs-lookup"><span data-stu-id="3d077-135">Last activity date (UTC)</span></span>  <br/> | <span data-ttu-id="3d077-136">ファイル アクティビティが最後に検出された日付、またはサイトでページが表示された日付。</span><span class="sxs-lookup"><span data-stu-id="3d077-136">The date of the last time file activity was detected or a page was viewed on the site.</span></span>  <br/> |
|<span data-ttu-id="3d077-137">サイトの感度ラベル ID</span><span class="sxs-lookup"><span data-stu-id="3d077-137">Site sensitivity label id</span></span>  <br/> | <span data-ttu-id="3d077-138">サイトの感度ラベル。</span><span class="sxs-lookup"><span data-stu-id="3d077-138">The sensitivity label on the site.</span></span>  <br/> |
|<span data-ttu-id="3d077-139">外部共有</span><span class="sxs-lookup"><span data-stu-id="3d077-139">External sharing</span></span>  <br/> | <span data-ttu-id="3d077-140">サイト上の外部のファイルの移動可能な設定。</span><span class="sxs-lookup"><span data-stu-id="3d077-140">The external sharable settings on the site.</span></span>  <br/> |
|<span data-ttu-id="3d077-141">非管理対象デバイス ポリシー</span><span class="sxs-lookup"><span data-stu-id="3d077-141">Unmanaged device policy</span></span>  <br/> | <span data-ttu-id="3d077-142">非管理対象デバイスのサイト アクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3d077-142">The site access policy for unmanaged devices.</span></span>  <br/> |
|<span data-ttu-id="3d077-143">地域の場所</span><span class="sxs-lookup"><span data-stu-id="3d077-143">Geo location</span></span>  <br/> | <span data-ttu-id="3d077-144">サイトの地理的位置。</span><span class="sxs-lookup"><span data-stu-id="3d077-144">The Geo location of the site.</span></span>  <br/> |
|<span data-ttu-id="3d077-145">ファイル</span><span class="sxs-lookup"><span data-stu-id="3d077-145">Files</span></span>  <br/> |<span data-ttu-id="3d077-146">サイト上のファイルの数。</span><span class="sxs-lookup"><span data-stu-id="3d077-146">The number of files on the site.</span></span> <br/>|
|<span data-ttu-id="3d077-147">アクティブなファイル</span><span class="sxs-lookup"><span data-stu-id="3d077-147">Active files</span></span>  <br/> | <span data-ttu-id="3d077-148">サイト上のアクティブなファイルの数。</span><span class="sxs-lookup"><span data-stu-id="3d077-148">The number of active files on the site.</span></span><br/> <span data-ttu-id="3d077-149">注: レポートの指定した期間中にファイルが削除された場合、レポートに表示されるアクティブなファイルの数は、サイト上の現在のファイル数よりも多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d077-149">NOTE: If files were removed during the specified time period for the report, the number of active files shown in the report may be larger than the current number of files on the site.</span></span>  <br/> |
|<span data-ttu-id="3d077-150">使用ストレージ (MB)</span><span class="sxs-lookup"><span data-stu-id="3d077-150">Storage used (MB)</span></span>  <br/> |<span data-ttu-id="3d077-151">サイトで現在使用されている記憶域の容量。</span><span class="sxs-lookup"><span data-stu-id="3d077-151">The amount of storage currently being used on the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-152">割り当てられた記憶域 (MB)</span><span class="sxs-lookup"><span data-stu-id="3d077-152">Storage allocated (MB)</span></span>  <br/> |<span data-ttu-id="3d077-153">サイトに割り当てられる記憶域の最大容量。</span><span class="sxs-lookup"><span data-stu-id="3d077-153">The maximum amount of storage allocated for the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-154">ページ ビュー</span><span class="sxs-lookup"><span data-stu-id="3d077-154">Page views</span></span>  <br/> |<span data-ttu-id="3d077-155">サイトでページが表示された回数。</span><span class="sxs-lookup"><span data-stu-id="3d077-155">The number of times pages were viewed on the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-156">アクセスされたページ</span><span class="sxs-lookup"><span data-stu-id="3d077-156">Pages visited</span></span>  <br/> |<span data-ttu-id="3d077-157">サイトでアクセスされた一意のページの数。</span><span class="sxs-lookup"><span data-stu-id="3d077-157">The number of unique pages that were visited on the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-158">匿名リンク数</span><span class="sxs-lookup"><span data-stu-id="3d077-158">Anonymous link count</span></span>  <br/> |<span data-ttu-id="3d077-159">サイトで [リンクを持つすべてのユーザー] を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="3d077-159">The number of times documents or folders are shared using "Anyone with the link" on the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-160">会社のリンク数</span><span class="sxs-lookup"><span data-stu-id="3d077-160">Company link count</span></span>  <br/> |<span data-ttu-id="3d077-161">サイトで "リンクを含む組織のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="3d077-161">The number of times documents or folders are shared using "People in org with the link" on the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-162">ゲスト数のセキュリティで保護されたリンク</span><span class="sxs-lookup"><span data-stu-id="3d077-162">Secure link for guest count</span></span>  <br/> |<span data-ttu-id="3d077-163">サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="3d077-163">The number of times documents or folders are shared using "specific people" on the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-164">メンバー数のセキュリティで保護されたリンク</span><span class="sxs-lookup"><span data-stu-id="3d077-164">Secure link for member count</span></span>  <br/> |<span data-ttu-id="3d077-165">サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="3d077-165">The number of times documents or folders are shared using "specific people" on the site.</span></span>  <br/>|
|<span data-ttu-id="3d077-166">ルート Web テンプレート</span><span class="sxs-lookup"><span data-stu-id="3d077-166">Root Web Template</span></span>  <br/> |<span data-ttu-id="3d077-167">サイトの作成に使用するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="3d077-167">The template used for creating the site.</span></span>  <br/> <span data-ttu-id="3d077-168">注: 異なるサイトの種類でデータをフィルター処理する場合は、データをエクスポートし、[ルート Web テンプレート] 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d077-168">NOTE: If you want to filter the data by different site types, then export the data and use the Root Web Template column.</span></span> |
|||