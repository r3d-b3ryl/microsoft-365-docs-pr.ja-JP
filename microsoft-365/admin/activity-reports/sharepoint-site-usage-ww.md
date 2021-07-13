---
title: Microsoft 365管理センターのレポート - SharePoint使用状況
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: ユーザーが SharePoint SharePoint サイトに保存するファイルの数、アクティブに使用されるファイルの数、および使用されたストレージの合計を確認するには、SharePoint サイト使用状況レポートを取得します。
ms.openlocfilehash: d2c549dbb5ab456dddedf0422cd8aebafab1987d
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393333"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a><span data-ttu-id="75f49-103">Microsoft 365管理センターのレポート - SharePoint使用状況</span><span class="sxs-lookup"><span data-stu-id="75f49-103">Microsoft 365 Reports in the admin center - SharePoint site usage</span></span>

<span data-ttu-id="75f49-104">管理者としてMicrosoft 365レポート **ダッシュボードには**、組織内のさまざまな製品のアクティビティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75f49-104">As a Microsoft 365 admin, the **Reports** dashboard shows you the activity overview across various products in your organization.</span></span> <span data-ttu-id="75f49-105">これにより、各製品に固有のアクティビティについてより詳しく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="75f49-105">It enables you to drill in to get more granular insight about the activities specific to each product.</span></span> <span data-ttu-id="75f49-106">たとえば、ユーザーが SharePoint サイトに保存するファイルの合計数、アクティブに使用されているファイルの数、およびこれらすべてのサイトにわたって使用される記憶域の観点から、SharePoint から得られる価値の概要をとらえることができます。</span><span class="sxs-lookup"><span data-stu-id="75f49-106">For example, you can get a high level view of the value you are getting from SharePoint in terms of the total number of files that users store in SharePoint sites, how many files are actively being used, and the storage consumed across all these sites.</span></span> <span data-ttu-id="75f49-107">その後、[SharePoint サイトの利用状況] レポートを詳細に確認して、すべてのサイトの傾向およびサイトごとのレベル詳細を把握できます。</span><span class="sxs-lookup"><span data-stu-id="75f49-107">Then, you can drill into the SharePoint site usage report to understand the trends and per site level details for all sites.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="75f49-108">レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="75f49-108">You must be a global administrator, global reader or reports reader in Microsoft 365 or an Exchange, SharePoint, Teams Service, Teams Communications, or Skype for Business administrator to see reports.</span></span>
<span data-ttu-id="75f49-109">Microsoft 365管理センターのレポートは、High テナントと DoD テナントGCCサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="75f49-109">Microsoft 365 Reports in the admin center is not supported for GCC High and DoD tenants.</span></span>
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a><span data-ttu-id="75f49-110">[SharePoint サイトの利用状況] レポートにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="75f49-110">How to get to the SharePoint site usage report</span></span>

1. <span data-ttu-id="75f49-111">管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="75f49-111">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
2. <span data-ttu-id="75f49-112">ダッシュボードのホームページで、カードの [その **他の表示**] SharePointクリックします。</span><span class="sxs-lookup"><span data-stu-id="75f49-112">From the dashboard homepage, click on the **View more** button on the SharePoint card.</span></span>
  
## <a name="interpret-the-sharepoint-site-usage-report"></a><span data-ttu-id="75f49-113">サイト利用状況SharePointレポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="75f49-113">Interpret the SharePoint site usage report</span></span>

<span data-ttu-id="75f49-114">[サイトの使用状況] タブを選択すると、SharePointレポートでサイトの使用状況 **を表示** できます。</span><span class="sxs-lookup"><span data-stu-id="75f49-114">You can view the site usage in the SharePoint report by choosing the **Site usage** tab.</span></span><br/><span data-ttu-id="75f49-115">![Microsoft 365レポート - Microsoft SharePoint利用状況レポート。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)</span><span class="sxs-lookup"><span data-stu-id="75f49-115">![Microsoft 365 reports - Microsoft SharePoint site usage report.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)</span></span>

<span data-ttu-id="75f49-116">[列 **の選択]** を選択して、レポートの列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="75f49-116">Select **Choose columns** to add or remove columns from the report.</span></span>  <br/> <span data-ttu-id="75f49-117">![SharePoint利用状況レポート - 列を選択する](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)</span><span class="sxs-lookup"><span data-stu-id="75f49-117">![SharePoint site usage report - choose columns](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)</span></span>

<span data-ttu-id="75f49-118">また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="75f49-118">You can also export the report data into an Excel .csv file by selecting the **Export** link.</span></span> <span data-ttu-id="75f49-119">これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。</span><span class="sxs-lookup"><span data-stu-id="75f49-119">This exports data of all users and enables you to do simple sorting and filtering for further analysis.</span></span> <span data-ttu-id="75f49-120">ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="75f49-120">If you have less than 2000 users, you can sort and filter within the table in the report itself.</span></span> <span data-ttu-id="75f49-121">ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75f49-121">If you have more than 2000 users, in order to filter and sort, you will need to export the data.</span></span> 
  
|<span data-ttu-id="75f49-122">項目</span><span class="sxs-lookup"><span data-stu-id="75f49-122">Item</span></span>|<span data-ttu-id="75f49-123">説明</span><span class="sxs-lookup"><span data-stu-id="75f49-123">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="75f49-124">**測定基準**</span><span class="sxs-lookup"><span data-stu-id="75f49-124">**Metric**</span></span>|<span data-ttu-id="75f49-125">**定義**</span><span class="sxs-lookup"><span data-stu-id="75f49-125">**Definition**</span></span>|
|<span data-ttu-id="75f49-126">サイトの URL</span><span class="sxs-lookup"><span data-stu-id="75f49-126">Site URL</span></span>  <br/> |<span data-ttu-id="75f49-127">サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="75f49-127">The full URL of the site.</span></span> <br/> |
|<span data-ttu-id="75f49-128">Deleted</span><span class="sxs-lookup"><span data-stu-id="75f49-128">Deleted</span></span>  <br/> |<span data-ttu-id="75f49-129">サイトの削除状態。</span><span class="sxs-lookup"><span data-stu-id="75f49-129">The deletion status of the site.</span></span> <span data-ttu-id="75f49-130">サイトを削除済みとしてマークするには、少なくとも 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="75f49-130">It takes at least 7 days for sites to be marked as deleted.</span></span>  <br/> |
|<span data-ttu-id="75f49-131">サイト所有者</span><span class="sxs-lookup"><span data-stu-id="75f49-131">Site owner</span></span>  <br/> |<span data-ttu-id="75f49-132">サイトのプライマリ所有者のユーザー名。</span><span class="sxs-lookup"><span data-stu-id="75f49-132">The username of the primary owner of the site.</span></span>   <br/> |
|<span data-ttu-id="75f49-133">サイト所有者プリンシパル名</span><span class="sxs-lookup"><span data-stu-id="75f49-133">Site owner principal name</span></span>  <br/> |<span data-ttu-id="75f49-134">サイトの所有者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="75f49-134">The email address of the owner of the site.</span></span> <br/> |
|<span data-ttu-id="75f49-135">最終アクティビティ日 (UTC)</span><span class="sxs-lookup"><span data-stu-id="75f49-135">Last activity date (UTC)</span></span>  <br/> | <span data-ttu-id="75f49-136">ファイルアクティビティが最後に検出された日付、またはサイトでページが表示された日付。</span><span class="sxs-lookup"><span data-stu-id="75f49-136">The date of the last time file activity was detected or a page was viewed on the site.</span></span>  <br/> |
|<span data-ttu-id="75f49-137">サイトの感度ラベル ID</span><span class="sxs-lookup"><span data-stu-id="75f49-137">Site sensitivity label id</span></span>  <br/> | <span data-ttu-id="75f49-138">サイトの感度ラベル。</span><span class="sxs-lookup"><span data-stu-id="75f49-138">The sensitivity label on the site.</span></span>  <br/> |
|<span data-ttu-id="75f49-139">外部共有</span><span class="sxs-lookup"><span data-stu-id="75f49-139">External sharing</span></span>  <br/> | <span data-ttu-id="75f49-140">サイトの外部のsharable設定。</span><span class="sxs-lookup"><span data-stu-id="75f49-140">The external sharable settings on the site.</span></span>  <br/> |
|<span data-ttu-id="75f49-141">管理されていないデバイス ポリシー</span><span class="sxs-lookup"><span data-stu-id="75f49-141">Unmanaged device policy</span></span>  <br/> | <span data-ttu-id="75f49-142">管理されていないデバイスのサイト アクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="75f49-142">The site access policy for unmanaged devices.</span></span>  <br/> |
|<span data-ttu-id="75f49-143">地域の場所</span><span class="sxs-lookup"><span data-stu-id="75f49-143">Geo location</span></span>  <br/> | <span data-ttu-id="75f49-144">サイトの地理的な場所。</span><span class="sxs-lookup"><span data-stu-id="75f49-144">The Geo location of the site.</span></span>  <br/> |
|<span data-ttu-id="75f49-145">ファイル</span><span class="sxs-lookup"><span data-stu-id="75f49-145">Files</span></span>  <br/> |<span data-ttu-id="75f49-146">サイト上のファイルの数。</span><span class="sxs-lookup"><span data-stu-id="75f49-146">The number of files on the site.</span></span> <br/>|
|<span data-ttu-id="75f49-147">アクティブ ファイル</span><span class="sxs-lookup"><span data-stu-id="75f49-147">Active files</span></span>  <br/> | <span data-ttu-id="75f49-148">サイト上のアクティブ なファイルの数。</span><span class="sxs-lookup"><span data-stu-id="75f49-148">The number of active files on the site.</span></span><br/> <span data-ttu-id="75f49-149">注: レポートの指定された期間中にファイルが削除された場合、レポートに表示されるアクティブ なファイルの数は、サイト上の現在のファイル数よりも多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="75f49-149">NOTE: If files were removed during the specified time period for the report, the number of active files shown in the report may be larger than the current number of files on the site.</span></span>  <br/> |
|<span data-ttu-id="75f49-150">Storage使用 (MB)</span><span class="sxs-lookup"><span data-stu-id="75f49-150">Storage used (MB)</span></span>  <br/> |<span data-ttu-id="75f49-151">サイトで現在使用されている記憶域の量。</span><span class="sxs-lookup"><span data-stu-id="75f49-151">The amount of storage currently being used on the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-152">Storage済み (MB)</span><span class="sxs-lookup"><span data-stu-id="75f49-152">Storage allocated (MB)</span></span>  <br/> |<span data-ttu-id="75f49-153">サイトに割り当てられた記憶域の最大量。</span><span class="sxs-lookup"><span data-stu-id="75f49-153">The maximum amount of storage allocated for the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-154">ページ ビュー</span><span class="sxs-lookup"><span data-stu-id="75f49-154">Page views</span></span>  <br/> |<span data-ttu-id="75f49-155">サイトでページが表示された回数。</span><span class="sxs-lookup"><span data-stu-id="75f49-155">The number of times pages were viewed on the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-156">アクセスしたページ</span><span class="sxs-lookup"><span data-stu-id="75f49-156">Pages visited</span></span>  <br/> |<span data-ttu-id="75f49-157">サイトにアクセスした一意のページの数。</span><span class="sxs-lookup"><span data-stu-id="75f49-157">The number of unique pages that were visited on the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-158">匿名リンク数</span><span class="sxs-lookup"><span data-stu-id="75f49-158">Anonymous link count</span></span>  <br/> |<span data-ttu-id="75f49-159">サイト上の [リンクを持つすべてのユーザー] を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="75f49-159">The number of times documents or folders are shared using "Anyone with the link" on the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-160">会社のリンク数</span><span class="sxs-lookup"><span data-stu-id="75f49-160">Company link count</span></span>  <br/> |<span data-ttu-id="75f49-161">サイト上の "リンクを持つ組織のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="75f49-161">The number of times documents or folders are shared using "People in org with the link" on the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-162">ゲスト数のセキュリティで保護されたリンク</span><span class="sxs-lookup"><span data-stu-id="75f49-162">Secure link for guest count</span></span>  <br/> |<span data-ttu-id="75f49-163">サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="75f49-163">The number of times documents or folders are shared using "specific people" on the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-164">メンバー数のセキュリティで保護されたリンク</span><span class="sxs-lookup"><span data-stu-id="75f49-164">Secure link for member count</span></span>  <br/> |<span data-ttu-id="75f49-165">サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。</span><span class="sxs-lookup"><span data-stu-id="75f49-165">The number of times documents or folders are shared using "specific people" on the site.</span></span>  <br/>|
|<span data-ttu-id="75f49-166">ルート Web テンプレート</span><span class="sxs-lookup"><span data-stu-id="75f49-166">Root Web Template</span></span>  <br/> |<span data-ttu-id="75f49-167">サイトの作成に使用するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="75f49-167">The template used for creating the site.</span></span>  <br/> <span data-ttu-id="75f49-168">注: 異なるサイトの種類でデータをフィルター処理する場合は、データをエクスポートし、[ルート Web テンプレート] 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="75f49-168">NOTE: If you want to filter the data by different site types, then export the data and use the Root Web Template column.</span></span> |
|||