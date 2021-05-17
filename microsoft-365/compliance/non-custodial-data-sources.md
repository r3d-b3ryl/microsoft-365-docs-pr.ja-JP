---
title: 非保管データ ソースをサポートケースにAdvanced eDiscoveryする
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
description: 保管されていないデータ ソースをケースにAdvanced eDiscoveryし、データ ソースに保留を設定できます。 保管されていないデータ ソースはインデックスが再作成され、部分的にインデックスとしてマークされたコンテンツは再処理され、完全かつ迅速に検索できます。
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740354"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="33dd3-104">非保管データ ソースをサポートケースにAdvanced eDiscoveryする</span><span class="sxs-lookup"><span data-stu-id="33dd3-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="33dd3-105">このようなAdvanced eDiscovery場合、ケース内のデータ ソースにデータ ソースを関連付けるMicrosoft 365満たすとは限らない場合があります。</span><span class="sxs-lookup"><span data-stu-id="33dd3-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="33dd3-106">ただし、そのデータをケースに関連付け、検索し、レビュー セットに追加し、分析して確認する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="33dd3-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="33dd3-107">この機能Advanced eDiscovery非保管データ ソースと呼ばれるので、データを保管担当者に関連付けなくてもケースにデータを追加できます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="33dd3-108">また、保管担当者に関連Advanced eDiscoveryデータで使用できる非保管データにも、同じ機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="33dd3-109">保管されていないデータに適用できる最も便利な点の 2 つが、それを保留にし [、Advanced indexing](indexing-custodian-data.md)を使用して処理することです。</span><span class="sxs-lookup"><span data-stu-id="33dd3-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="33dd3-110">保管されていないデータ ソースを追加する</span><span class="sxs-lookup"><span data-stu-id="33dd3-110">Add a non-custodial data source</span></span>

<span data-ttu-id="33dd3-111">次の手順に従って、非保管データ ソースを追加および管理します。Advanced eDiscoveryします。</span><span class="sxs-lookup"><span data-stu-id="33dd3-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="33dd3-112">[ホーム **Advanced eDiscovery]** で、データを追加するケースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="33dd3-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="33dd3-113">[データ ソース **] タブをクリック** し、[データ ソースの追加]  >  **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="33dd3-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="33dd3-114">[保管 **されていないデータの場所の新** しい場所] フライアウト ページで、ケースに追加するデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="33dd3-115">複数のメールボックスとサイトを追加するには、[フォルダー] セクションまたは [SharePoint] セクションExchange [編集] をクリック **します**。  </span><span class="sxs-lookup"><span data-stu-id="33dd3-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![管理SharePointおよびメールボックスExchange非保管データ ソースとして追加する](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="33dd3-117">**SharePoint** - [編集]**をクリックして** サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="33dd3-118">リストでサイトを選択するか、検索バーにサイトの URL を入力してサイトを検索できます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="33dd3-119">非保管データ ソースとして追加するサイトを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="33dd3-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="33dd3-120">**Exchange** - [編集 **] をクリック** してメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="33dd3-121">メールボックスまたは配布グループの検索ボックスに、名前またはエイリアス (最低 3 文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="33dd3-122">保管担当者以外のデータ ソースとして追加するメールボックスを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="33dd3-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33dd3-123">[管理] **SharePoint** セクションと[Exchange] セクションを使用して、チームまたはグループに関連付けられたサイトとメールボックスを非保管データ ソースYammer追加できます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="33dd3-124">チームまたはグループに関連付けられているメールボックスとサイトを個別に追加Yammerがあります。</span><span class="sxs-lookup"><span data-stu-id="33dd3-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="33dd3-125">保管されていないデータ ソースを追加した後、それらの場所を保留にするかしないかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="33dd3-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="33dd3-126">データ ソースの横にある **[保持** ] チェック ボックスをオンまたはオフにして、データ ソースを保留にします。</span><span class="sxs-lookup"><span data-stu-id="33dd3-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="33dd3-127">[ **新しい** 保管以外のデータ **の場所** ] フライアウト ページの下部にある [追加] をクリックして、データ ソースをケースに追加します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="33dd3-128">追加した保管されていない各データ ソースは、[データ ソース] **ページに一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="33dd3-129">保管されていないデータ ソースは、[ソースの種類] 列の **[データの** 場所] の値 **によって識別** されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![[データ ソース] タブの非保管データ ソース](../media/NonCustodialDataSources2.png)

<span data-ttu-id="33dd3-131">ケースに非保管データ ソースを追加すると、保管されていないデータのインデックスを再作成するという名前のジョブが作成され、ケースの [**ジョブ**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="33dd3-132">ジョブが作成されると、開始された高度なインデックス処理とデータ ソースのインデックスが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="33dd3-133">保管されていないデータ ソースの保留を管理する</span><span class="sxs-lookup"><span data-stu-id="33dd3-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="33dd3-134">保管されていないデータ ソースに保留を設定すると、ケースの非保管データ ソースを含む保留ポリシーが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="33dd3-135">他の非保管データ ソースを保留にした場合、そのデータ ソースは、この保留ポリシーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="33dd3-136">ケースを開Advanced eDiscoveryし、[保持] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="33dd3-137">**[NCDSHold-] \<GUID\>** をクリックします。GUID 値はケースに固有です。</span><span class="sxs-lookup"><span data-stu-id="33dd3-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="33dd3-138">フライアウト ページには、保留の非保管データ ソースに関する情報と統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![非保管データ ソースのフライアウト ページには、統計情報が表示されます](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="33dd3-140">[ **保持の編集]** をクリックして保留にされている非保管データ ソースを表示し、次の管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="33dd3-141">[場所 **] ページ** で、保留リストからデータ ソースを削除することで、保管されていないデータ ソースを解放できます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="33dd3-142">データ ソースを解放しても、ケースから非保管データ ソースは削除されます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="33dd3-143">データ ソースに配置された保留リストのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="33dd3-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="33dd3-144">[クエリ **] ページ** で、ホールドを編集して、ケース内のすべての非保管データ ソースに適用されるクエリ ベースのホールドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="33dd3-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
