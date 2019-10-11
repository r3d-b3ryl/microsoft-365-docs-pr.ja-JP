---
title: コンテンツ検索レポートのエクスポート
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Office 365 のセキュリティ & コンプライアンスセンターでコンテンツ検索の実際の結果をエクスポートする代わりに、検索結果レポートをエクスポートすることができます。 レポートには、検索結果の概要と、エクスポートされる各アイテムの詳細情報を含むドキュメントが含まれます。
ms.openlocfilehash: 9fe006ba595920f938a4d070eb87987137d73f7e
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437787"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="8f8d5-104">コンテンツ検索レポートのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8f8d5-104">Export a Content Search report</span></span>

<span data-ttu-id="8f8d5-105">セキュリティ & コンプライアンスセンター (および電子情報開示ケースに関連付けられているコンテンツ検索) から完全な検索結果セットをエクスポートする代わりに、検索結果をエクスポートするときに生成されるものと同じレポートをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="8f8d5-106">レポートをエクスポートすると、コンテンツ検索と同じ名前のフォルダーにダウンロードされますが、そのレポートには [レポート]*のみ*が追加されます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="8f8d5-107">たとえば、コンテンツ検索に*ContosoCase0815*という名前が付けられている場合、レポートは*ContosoCase0815_ReportsOnly*という名前のフォルダーにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="8f8d5-108">レポートに含まれるドキュメントの一覧については、「[レポートに含まれるもの](#whats-included-in-the-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8f8d5-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="8f8d5-109">Before you begin</span></span>

- <span data-ttu-id="8f8d5-110">コンテンツ検索レポートをエクスポートするには、セキュリティ & コンプライアンスセンターでコンプライアンス検索管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="8f8d5-111">この役割は、組み込みの電子情報開示マネージャーと組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="8f8d5-112">既定では、Organization Management 役割グループには割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="8f8d5-113">詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="8f8d5-114">レポートをエクスポートすると、データがローカルコンピューターにダウンロードされる前に、Microsoft クラウド内の一意の Azure ストレージ領域に一時的に格納されます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-114">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="8f8d5-115">組織が Azure のエンドポイントに接続できることを確認し\*\* \*ます。 blob.core.windows.net\*\* (ワイルドカードは、エクスポートの一意識別子を表します)。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-115">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="8f8d5-116">検索結果データは、作成後2週間後に Azure ストレージ領域から削除されます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-116">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="8f8d5-117">検索結果をエクスポートする際に使用するコンピューターは、次のシステム要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="8f8d5-118">32ビットまたは64ビット版の Windows 7 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8f8d5-118">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="8f8d5-119">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8f8d5-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="8f8d5-120">サポートされているブラウザー:</span><span class="sxs-lookup"><span data-stu-id="8f8d5-120">A supported browser:</span></span>
    
    - <span data-ttu-id="8f8d5-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8f8d5-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="8f8d5-122">または</span><span class="sxs-lookup"><span data-stu-id="8f8d5-122">or</span></span>
    
    - <span data-ttu-id="8f8d5-123">Microsoft Internet Explorer 10 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8f8d5-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="8f8d5-124">**注:** Microsoft は、ClickOnce アプリケーションのサードパーティの拡張機能またはアドオンを製造していません。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-124">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="8f8d5-125">サポートされていないブラウザーを使用して、サードパーティの内線番号またはアドオンを使用して検索結果をエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="8f8d5-126">コンテンツ検索によって返された結果の推定合計サイズが 2 TB を超えている場合は、レポートをエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-126">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="8f8d5-127">レポートを正常にエクスポートするには、範囲を絞るようにして検索を再実行し、結果の推定サイズが 2 TB 未満になるようにします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-127">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="8f8d5-128">コンテンツ検索レポートのエクスポートは、同時に実行しているエクスポートの最大数と、1人のユーザーが実行できるエクスポートの最大数に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-128">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="8f8d5-129">エクスポート制限の詳細については、「[コンテンツ検索の結果をエクスポート](export-search-results.md#export-limits)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-129">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="8f8d5-130">コンテンツ検索レポートを生成してダウンロードする</span><span class="sxs-lookup"><span data-stu-id="8f8d5-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="8f8d5-131">コンテンツ検索レポートを生成してダウンロードする手順は、実際に検索結果をエクスポートした場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-131">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="8f8d5-132">手順 1: エクスポート用のレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="8f8d5-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="8f8d5-133">最初の手順として、コンピューターをエクスポートするためのレポートをダウンロードする準備をします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-133">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="8f8d5-134">レポートを作成すると、レポートドキュメントが Microsoft クラウドの Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-134">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="8f8d5-135">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8f8d5-136">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="8f8d5-137">セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**検索** \> **コンテンツ検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-137">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="8f8d5-138">[**コンテンツ検索**] ページで、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="8f8d5-139">詳細ウィンドウの [**レポートをコンピューターにエクスポートする**] で、[**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8f8d5-140">検索の結果が 7 日よりも前の場合は、検索結果を更新するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-140">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="8f8d5-141">この問題が発生した場合は、エクスポートをキャンセルし、選択した検索の詳細ウィンドウで [**検索結果の更新**] をクリックしてから、結果が更新された後に再度レポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-141">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="8f8d5-142">[**レポートのエクスポート**] ページの [**検索からこれらの項目を含める**] で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="8f8d5-143">インデックス付きのアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8f8d5-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="8f8d5-144">インデックス付きのアイテムとインデックスのないアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8f8d5-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="8f8d5-145">インデックスのないアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8f8d5-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="8f8d5-146">インデックスのないアイテムの詳細については、「[コンテンツ検索でインデックス](partially-indexed-items-in-content-search.md)が作成されたアイテム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="8f8d5-147">SharePoint ドキュメントのすべてのバージョンの検索統計を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-147">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="8f8d5-148">このオプションは、検索のコンテンツソースに SharePoint または OneDrive for business サイトが含まれている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-148">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="8f8d5-149">[**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="8f8d5-150">検索結果レポートはダウンロード用に準備されています。つまり、レポートドキュメントが Microsoft クラウド内の Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-150">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="8f8d5-151">レポートがダウンロードできる状態になると、[レポートの**ダウンロード**] リンクが [詳細] ウィンドウの [**コンピューターにレポートをエクスポート**します] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-151">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8f8d5-152">また、電子情報開示ケースに関連付けられているコンテンツ検索のレポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-152">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="8f8d5-153">これを行うには、 **[電子情報** \> **開示**] に移動し、ケースを選択](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)して、[編集アイコンの**編集** ![] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-153">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="8f8d5-154">[検索 **] ページで**、検索を選択し、[エクスポート] [検索結果](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **のエクスポート]** ![アイコンをクリックして**レポートをエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-154">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="8f8d5-155">手順 2: レポートをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="8f8d5-155">Step 2: Download the report</span></span>

<span data-ttu-id="8f8d5-156">次の手順では、Azure ストレージ領域からローカルコンピューターにレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-156">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="8f8d5-157">レポートを生成した検索の詳細ウィンドウで、[**レポートをコンピューターにエクスポート**する] で、[**レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="8f8d5-158">[**レポートのダウンロード**] ページが表示され、コンピューターにダウンロードされたレポートに関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-158">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="8f8d5-159">ダウンロードされるアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="8f8d5-160">ダウンロードされるアイテムの推定合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="8f8d5-161">エクスポートされる内容にインデックスが付いているかどうか。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-161">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="8f8d5-162">インデックスのないアイテムは、他の理由で、認識されている形式、暗号化されている、またはインデックスが作成されていないアイテムです。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-162">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="8f8d5-163">SharePoint ドキュメントのバージョンをダウンロードするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-163">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="8f8d5-164">レポートエクスポートプロセスの状態。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-164">The status of the report export process.</span></span> <span data-ttu-id="8f8d5-165">レポートの準備が完了していない場合でも、レポートのダウンロードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-165">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="8f8d5-166">**[エクスポート キー]** で、**[クリップボードにコピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-166">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="8f8d5-167">レポートをダウンロードするには、手順5でこのキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-167">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8f8d5-168">すべてのユーザーが電子情報開示エクスポートツールをインストールして起動し、このキーを使用して検索レポートをダウンロードすることができるため、パスワードやその他のセキュリティ関連情報を保護するのと同じように、このキーを保護するための対策を必ず実行してください。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="8f8d5-169">[**レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="8f8d5-170">**MicrosoftOffice 365 電子情報開示エクスポートツール**をインストールするように求めるメッセージが表示されたら、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="8f8d5-171">**電子情報開示エクスポート ツール**で、手順 2 でコピーしたエクスポート キーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="8f8d5-172">[**参照**] をクリックして、レポートをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="8f8d5-173">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="8f8d5-174">**電子情報開示エクスポート ツール**には、ダウンロードする残りのアイテムの数とサイズの見積もりなど、エクスポート プロセスの状態に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-174">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="8f8d5-175">エクスポートプロセスが完了すると、ダウンロードされた場所にあるファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-175">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8f8d5-176">電子情報開示ケースに関連付けられたコンテンツ検索のレポートをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-176">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="8f8d5-177">これを行うには、 **[電子情報** \> **開示**] に移動し、ケースを選択](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)して、[編集アイコンの**編集** ![] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-177">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="8f8d5-178">[**エクスポート**] ページで、レポートのエクスポートを選択し、[詳細] ウィンドウの [**レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-178">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="8f8d5-179">レポートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="8f8d5-179">What's included in the report</span></span>

<span data-ttu-id="8f8d5-180">コンテンツ検索の結果に関するレポートを生成してエクスポートすると、次のドキュメントがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="8f8d5-181">**エクスポートの概要:** エクスポートの概要を含む Excel ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-181">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="8f8d5-182">これには、検索されたコンテンツソースの数、各コンテンツの場所からの検索結果の数、アイテムの推定数、エクスポートされるアイテムの実際の数、およびアイテムの予想および実際のサイズなどの情報が含まれます。エクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-182">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8f8d5-183">レポートをエクスポートするときにインデックスのないアイテムを含めると、インデックスが作成されていないアイテムの数が、予想される検索結果の合計数とダウンロードした検索結果の合計数に含まれます (検索結果をエクスポートした場合)。概要レポートをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-183">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="8f8d5-184">つまり、ダウンロードされるアイテムの合計数は、予想される結果の合計数と、インデックスが設定されていないアイテムの合計数と同じになります。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-184">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="8f8d5-185">**マニフェスト:** 検索結果に含まれる各アイテムに関する情報を含むマニフェストファイル (XML 形式)。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-185">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="8f8d5-186">**結果:** 検索結果と共にエクスポートされるインデックス化された各アイテムに関する情報を含む行を含む Excel ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="8f8d5-187">メールの場合、結果ログには、各メッセージに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-187">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="8f8d5-188">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="8f8d5-189">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="8f8d5-190">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="8f8d5-191">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="8f8d5-192">SharePoint および OneDrive for Business サイトのドキュメントの場合、結果ログには、各ドキュメントに関する以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="8f8d5-193">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="8f8d5-194">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="8f8d5-195">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="8f8d5-196">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8f8d5-197">**結果**レポートの行数は、インデックスが設定されていない**アイテム**レポートに一覧表示されているアイテムの合計数を引いた数と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="8f8d5-198">**インデックスのないアイテム:** 検索結果に含まれるインデックスのないアイテムに関する情報を含む Excel ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-198">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="8f8d5-199">検索結果レポートを生成するときに、インデックスのないアイテムを含めない場合、このレポートは引き続きダウンロードされますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="8f8d5-199">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
