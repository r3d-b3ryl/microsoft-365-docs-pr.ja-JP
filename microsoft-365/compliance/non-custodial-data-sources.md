---
title: 保管されていないデータ ソースを Advanced eDiscovery ケースに追加する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 保管されていないデータ ソースを Advanced eDiscovery ケースに追加し、データ ソースを保留にできます。 保管されていないデータ ソースは再インデックス化されます。そのため、部分的にインデックスが付いているとマークされたコンテンツは再処理され、完全かつ迅速に検索可能になります。
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740354"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="597ad-104">保管されていないデータ ソースを Advanced eDiscovery ケースに追加する</span><span class="sxs-lookup"><span data-stu-id="597ad-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="597ad-105">Advanced eDiscovery のケースでは、Microsoft 365 データ ソースをケースの保管担当者に関連付ける必要が常に満たされるとは限らない。</span><span class="sxs-lookup"><span data-stu-id="597ad-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="597ad-106">ただし、そのデータをケースに関連付け、検索、レビュー セットへの追加、分析とレビューを行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="597ad-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="597ad-107">Advanced eDiscovery の機能は、保管されていないデータ ソースと呼ばれる機能であり、データを保管担当者に関連付けなくてもケースに追加できます。</span><span class="sxs-lookup"><span data-stu-id="597ad-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="597ad-108">また、保管担当者に関連付けられたデータに使用できる保管されていないデータにも、同じ Advanced eDiscovery 機能が適用されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="597ad-109">保管されていないデータに適用できる最も有用なものの 2 つが、保管データを保留にし、 [高度](indexing-custodian-data.md)なインデックス作成を使用して処理することです。</span><span class="sxs-lookup"><span data-stu-id="597ad-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="597ad-110">保管されていないデータ ソースを追加する</span><span class="sxs-lookup"><span data-stu-id="597ad-110">Add a non-custodial data source</span></span>

<span data-ttu-id="597ad-111">Advanced eDiscovery ケースで保管されていないデータ ソースを追加および管理するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="597ad-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="597ad-112">Advanced **eDiscovery ホーム ページ** で、データを追加するケースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="597ad-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="597ad-113">[データ ソース **] タブをクリックし**、[データ ソースの **追加]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="597ad-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="597ad-114">[ **保管されていないデータの場所** の新規] フライアウト ページで、ケースに追加するデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="597ad-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="597ad-115">複数のメールボックスとサイトを追加するには **、SharePoint** または **Exchange** のセクションを展開し、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="597ad-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![SharePoint サイトと Exchange メールボックスを保管されていないデータ ソースとして追加する](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="597ad-117">**SharePoint** - [編集] **をクリック** してサイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="597ad-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="597ad-118">一覧からサイトを選択するか、検索バーにサイトの URL を入力してサイトを検索できます。</span><span class="sxs-lookup"><span data-stu-id="597ad-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="597ad-119">保管担当者以外のデータ ソースとして追加するサイトを選択し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="597ad-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="597ad-120">**Exchange** - [編集 **] をクリック** してメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="597ad-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="597ad-121">メールボックスまたは配布グループの検索ボックスに名前またはエイリアス (3 文字以上) を入力します。</span><span class="sxs-lookup"><span data-stu-id="597ad-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="597ad-122">保管担当者以外のデータ ソースとして追加するメールボックスを選択し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="597ad-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="597ad-123">**SharePoint** セクションと **Exchange** セクションを使用して、チームまたはグループに関連付けられているサイトとメールボックスを、保管Yammerデータ ソースとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="597ad-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="597ad-124">チームまたはグループに関連付けられているメールボックスとサイトを個別に追加Yammerがあります。</span><span class="sxs-lookup"><span data-stu-id="597ad-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="597ad-125">保管されていないデータ ソースを追加した後は、それらの場所を保留にするかしないかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="597ad-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="597ad-126">データ ソースの横にある [ **保留** ] チェック ボックスをオンまたはオフにして、保留にします。</span><span class="sxs-lookup"><span data-stu-id="597ad-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="597ad-127">[**保管されていない** データの場所の新規] フライアウト ページの下部にある [追加] をクリックして、データ ソースをケースに追加します。</span><span class="sxs-lookup"><span data-stu-id="597ad-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="597ad-128">追加した保管されていない各データ ソースは、[データ ソース **] ページに一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="597ad-129">保管されていないデータ ソースは、[ソースの種類] 列の **[データの** 場所] **の値によって識別** されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![[データ ソース] タブの非保管データ ソース](../media/NonCustodialDataSources2.png)

<span data-ttu-id="597ad-131">保管されていないデータ ソースをケースに追加すると、保管データ *の* インデックス再作成という名前のジョブが作成され、ケースの [ジョブ]タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="597ad-132">ジョブが作成されると、開始された高度なインデックス処理とデータ ソースのインデックスが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="597ad-133">保管されていないデータ ソースの保留を管理する</span><span class="sxs-lookup"><span data-stu-id="597ad-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="597ad-134">保管されていないデータ ソースを保留にした後、ケースの保管されていないデータ ソースを含む保留ポリシーが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="597ad-135">保管されていない他のデータ ソースを保留にした場合、そのデータ ソースは、この保持ポリシーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="597ad-136">Advanced eDiscovery ケースを開き、[保留] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="597ad-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="597ad-137">**[NCDSHold- \<GUID\> ]** をクリックします。ここで、GUID 値はケースに固有です。</span><span class="sxs-lookup"><span data-stu-id="597ad-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="597ad-138">このフライアウト ページには、保管中でないデータ ソースに関する情報と統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![保管されていないデータ ソース保持のフライアウト ページには統計情報が表示されます](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="597ad-140">[ **保留の編集]** をクリックして、保留にされている保管されていないデータ ソースを表示し、次の管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="597ad-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="597ad-141">[ **場所] ページ** では、保留リストから削除することで、保管されていないデータ ソースを解放できます。</span><span class="sxs-lookup"><span data-stu-id="597ad-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="597ad-142">データ ソースを解放しても、ケースから保管されていないデータ ソースは削除されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="597ad-143">データ ソースに設定された保留リストだけが削除されます。</span><span class="sxs-lookup"><span data-stu-id="597ad-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="597ad-144">[クエリ **]** ページで、保留リストを編集して、ケース内のすべての非保管データ ソースに適用されるクエリ ベースの保留リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="597ad-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
