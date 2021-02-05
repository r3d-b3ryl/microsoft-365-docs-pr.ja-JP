---
title: Microsoft のトピックの検出を管理するトピック
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: トピック検出を管理する方法については、「Microsoft のトピック」を参照してください。
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107761"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="0ef93-103">Microsoft のトピックの検出を管理するトピック</span><span class="sxs-lookup"><span data-stu-id="0ef93-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="0ef93-104">トピック検出の設定は [、Microsoft 365 管理センターで管理できます](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="0ef93-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="0ef93-105">これらのタスクを実行するには、全体管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ef93-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="0ef93-106">トピックの管理設定にアクセスするには:</span><span class="sxs-lookup"><span data-stu-id="0ef93-106">To access topics management settings:</span></span>

1. <span data-ttu-id="0ef93-107">Microsoft 365 管理センターで、[設定] をクリックし、[組織の設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ef93-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="0ef93-108">[サービス] **タブで** 、[トピックエクスペリエンス] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ef93-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![ユーザーを知識に接続する](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="0ef93-110">[トピックの **検出] タブを選択** します。各設定の詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ef93-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="0ef93-112">SharePoint トピック ソースの選択</span><span class="sxs-lookup"><span data-stu-id="0ef93-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="0ef93-113">トピックをクロールする組織内の SharePoint サイトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="0ef93-114">サイトの特定のリストを含める、または除外する場合は、次の .csv テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="0ef93-115">サイト ピッカーを使用してサイトを追加すると、既存のサイト一覧に追加され、追加または除外されます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="0ef93-116">.csv ファイルをアップロードすると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="0ef93-117">以前に特定のサイトを含めるか除外した場合は、リストを .csv ファイルとしてダウンロードし、変更を加え、新しいリストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0ef93-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="0ef93-118">トピック検出用のサイトを選択するには</span><span class="sxs-lookup"><span data-stu-id="0ef93-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="0ef93-119">[トピックの **検出]** タブの **[SharePoint** トピック ソースの選択] で、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0ef93-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="0ef93-120">**[SharePoint トピック ソース** の選択] ページで、検出時にトピックのソースとしてクロールする SharePoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ef93-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="0ef93-121">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-121">This includes:</span></span>
    - <span data-ttu-id="0ef93-122">**すべてのサイト**: テナント内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="0ef93-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="0ef93-123">これにより、現在および将来のサイトがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="0ef93-124">**すべて (選択したサイトを** 除く): 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ef93-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="0ef93-125">検出からオプトアウトするサイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="0ef93-126">今後作成されるサイトは、トピック検出のソースとして含まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="0ef93-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="0ef93-127">**選択したサイト** のみ: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ef93-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="0ef93-128">サイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-128">You can also upload a list of sites.</span></span> <span data-ttu-id="0ef93-129">将来作成されるサイトは、トピック検出のソースとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="0ef93-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="0ef93-130">**サイトなし**: トピックは SharePoint コンテンツで自動的に生成または更新されません。</span><span class="sxs-lookup"><span data-stu-id="0ef93-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="0ef93-131">既存のトピックはトピック センターに残ります。</span><span class="sxs-lookup"><span data-stu-id="0ef93-131">Existing topics remain in the topic center.</span></span>

    ![SharePoint トピック ソースのユーザー インターフェイスのスクリーンショット](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="0ef93-133">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ef93-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="0ef93-134">名前でトピックを除外する</span><span class="sxs-lookup"><span data-stu-id="0ef93-134">Exclude topics by name</span></span>

<span data-ttu-id="0ef93-135">.csv ファイルを使用してリストをアップロードすることで、検出からトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="0ef93-136">トピックを以前に除外した場合は、.csv をダウンロードし、変更を加え、もう一度アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="0ef93-137">[トピックの **検出] タブの** [除外] **トピックで**、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0ef93-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="0ef93-138">[名前 **でトピックを除外する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ef93-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="0ef93-139">リストを作成する必要がある場合は、.csv テンプレートをダウンロードし、除外するトピックを追加します (以下の *.csv* テンプレートの操作を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0ef93-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="0ef93-140">ファイルの準備ができたら、[参照] をクリック **して** ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0ef93-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="0ef93-141">既存のリストがある場合は、リストを含む .csv をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="0ef93-142">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ef93-142">Click **Save**.</span></span>

    ![除外トピックのユーザー インターフェイスのスクリーンショット](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="0ef93-144">.csv テンプレートを操作する</span><span class="sxs-lookup"><span data-stu-id="0ef93-144">Working with the .csv template</span></span>

<span data-ttu-id="0ef93-145">csv テンプレートは、次の場所にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="0ef93-146">CSV テンプレートで、除外するトピックに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ef93-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="0ef93-147">**[名前**]: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ef93-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="0ef93-148">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0ef93-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="0ef93-149">完全一致: 正確な名前または頭字語 *(Contoso* や ATL など) *を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="0ef93-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="0ef93-150">部分一致: 特定の単語を含むすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="0ef93-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="0ef93-151">たとえば、円弧 *には*、円弧、円弧の円弧、トレーニング用の円弧など、その中に円弧を含むすべてのトピック *が除外されます*。 Architecture など、単語の一部としてテキストが含まれるトピックは除外されない点に注意 *してください*。</span><span class="sxs-lookup"><span data-stu-id="0ef93-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="0ef93-152">**略語 (省略可能)**: 頭字語を除外する場合は、略語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ef93-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="0ef93-153">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="0ef93-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![CSV テンプレートでトピックを除外する](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="0ef93-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ef93-155">See also</span></span>

[<span data-ttu-id="0ef93-156">Microsoft 365 でトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="0ef93-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="0ef93-157">Microsoft 365 でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="0ef93-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="0ef93-158">Microsoft 365 のトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="0ef93-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
