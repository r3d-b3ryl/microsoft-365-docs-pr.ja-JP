---
title: コンテンツ検索レポートのエクスポート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de27e25945f14f6a6119b4c1776eebca5e84d8ce
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358303"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="723a8-104">コンテンツ検索レポートのエクスポート</span><span class="sxs-lookup"><span data-stu-id="723a8-104">Export a Content Search report</span></span>

<span data-ttu-id="723a8-105">セキュリティ & コンプライアンスセンター (および電子情報開示ケースに関連付けられているコンテンツ検索) から完全な検索結果セットをエクスポートする代わりに、検索結果をエクスポートするときに生成されるものと同じレポートをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="723a8-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="723a8-106">レポートをエクスポートすると、コンテンツ検索と同じ名前のフォルダーにダウンロードされますが、これは *_ReportsOnly*に追加されます。</span><span class="sxs-lookup"><span data-stu-id="723a8-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="723a8-107">たとえば、コンテンツ検索に  *ContosoCase0815*という名前が付けられている場合、レポートは *ContosoCase0815_ReportsOnly*という名前のフォルダーにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="723a8-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="723a8-108">レポートに含まれるドキュメントの一覧については、「 [レポートに含まれるもの](#whats-included-in-the-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723a8-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="723a8-109">役割を割り当て、システム要件を確認する</span><span class="sxs-lookup"><span data-stu-id="723a8-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="723a8-110">コンテンツ検索レポートをエクスポートするには、セキュリティ & コンプライアンスセンターでコンプライアンス検索管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="723a8-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="723a8-111">この役割は、組み込みの電子情報開示マネージャーおよび組織の管理役割グループに既定で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="723a8-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="723a8-112">詳細については、「 [電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723a8-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="723a8-113">レポートをエクスポートすると、データがローカルコンピューターにダウンロードされる前に、Microsoft クラウド内の一意の Azure ストレージ領域に一時的に格納されます。</span><span class="sxs-lookup"><span data-stu-id="723a8-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="723a8-114">組織が Azure のエンドポイントに接続できることを確認し\*\* \* ます。 blob.core.windows.net\*\* (ワイルドカードは、エクスポートの一意識別子を表します)。</span><span class="sxs-lookup"><span data-stu-id="723a8-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="723a8-115">検索結果データは、作成後2週間後に Azure ストレージ領域から削除されます。</span><span class="sxs-lookup"><span data-stu-id="723a8-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="723a8-116">検索結果をエクスポートする際に使用するコンピューターは、次のシステム要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="723a8-116">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="723a8-117">32ビットまたは64ビット版の Windows 7 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="723a8-117">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="723a8-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="723a8-118">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="723a8-119">電子情報開示エクスポートツール<sup>1</sup>を実行するには、次のサポートされているブラウザーのいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="723a8-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="723a8-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="723a8-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="723a8-121">OR</span><span class="sxs-lookup"><span data-stu-id="723a8-121">OR</span></span>

  - <span data-ttu-id="723a8-122">Microsoft Internet Explorer 10 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="723a8-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="723a8-123"><sup>1</sup> Microsoft は、ClickOnce アプリケーション用のサードパーティ製の拡張機能またはアドオンを製造していません。</span><span class="sxs-lookup"><span data-stu-id="723a8-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="723a8-124">サポートされていないブラウザーを使用して、サードパーティの内線番号またはアドオンを使用して検索結果をエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="723a8-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="723a8-125"><sup>2</sup> Microsoft Edge に対する最近の変更の結果として、ClickOnce サポートは既定で有効になりません。</span><span class="sxs-lookup"><span data-stu-id="723a8-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="723a8-126">エッジで ClickOnce サポートを有効にする方法については、「 [Microsoft Edge で電子情報開示エクスポートツールを使用](configure-edge-to-export-search-results.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723a8-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="723a8-127">コンテンツ検索によって返された結果の推定合計サイズが 2 TB を超えている場合は、レポートをエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="723a8-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="723a8-128">レポートを正常にエクスポートするには、範囲を絞るようにして検索を再実行し、結果の推定サイズが 2 TB 未満になるようにします。</span><span class="sxs-lookup"><span data-stu-id="723a8-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="723a8-129">コンテンツ検索レポートのエクスポートは、同時に実行しているエクスポートの最大数と、1人のユーザーが実行できるエクスポートの最大数に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="723a8-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="723a8-130">エクスポート制限の詳細については、「 [コンテンツ検索の結果をエクスポート](export-search-results.md#export-limits)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723a8-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="723a8-131">コンテンツ検索レポートを生成してダウンロードする</span><span class="sxs-lookup"><span data-stu-id="723a8-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="723a8-132">コンテンツ検索レポートを生成してダウンロードする手順は、実際に検索結果をエクスポートした場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="723a8-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="723a8-133">手順 1: エクスポート用のレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="723a8-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="723a8-134">最初の手順として、コンピューターをエクスポートするためのレポートをダウンロードする準備をします。</span><span class="sxs-lookup"><span data-stu-id="723a8-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="723a8-135">レポートを作成すると、レポートドキュメントが Microsoft クラウドの Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="723a8-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="723a8-136">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="723a8-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="723a8-137">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="723a8-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="723a8-138">セキュリティ & コンプライアンスセンターの左側のウィンドウで、[ **検索** \> **コンテンツ検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="723a8-139">[ **コンテンツ検索** ] ページで、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="723a8-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="723a8-140">詳細ウィンドウの [ **レポートをコンピューターにエクスポートする**] で、[ **レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="723a8-141">検索の結果が 7 日よりも前の場合は、検索結果を更新するように求められます。</span><span class="sxs-lookup"><span data-stu-id="723a8-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="723a8-142">この問題が発生した場合は、エクスポートをキャンセルし、選択した検索の詳細ウィンドウで [ **検索結果の更新** ] をクリックしてから、結果が更新された後に再度レポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="723a8-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="723a8-143">[ **レポートのエクスポート** ] ページの [ **検索からこれらの項目を含める**] で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="723a8-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="723a8-144">インデックス付きのアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="723a8-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="723a8-145">インデックス付きのアイテムとインデックスのないアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="723a8-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="723a8-146">インデックスのないアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="723a8-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="723a8-147">インデックスのないアイテムの詳細については、「 [コンテンツ検索でインデックス](partially-indexed-items-in-content-search.md)が作成されたアイテム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723a8-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="723a8-148">SharePoint ドキュメントのすべてのバージョンの検索統計を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="723a8-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="723a8-149">このオプションは、検索のコンテンツソースに SharePoint または OneDrive for business サイトが含まれている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="723a8-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="723a8-150">[ **レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="723a8-151">検索結果レポートはダウンロード用に準備されています。つまり、レポートドキュメントが Microsoft クラウド内の Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="723a8-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="723a8-152">レポートがダウンロードできる状態になると、[レポートの **ダウンロード** ] リンクが [詳細] ウィンドウの [ **コンピューターにレポートをエクスポート** します] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="723a8-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="723a8-153">また、電子情報開示ケースに関連付けられているコンテンツ検索のレポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="723a8-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="723a8-154">これを行うには、[ **電子情報** \> **開示**] に移動し、ケースを選択して、[編集アイコンの **編集**] をクリックし ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="723a8-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="723a8-155">[検索 **] ページで** 、検索を選択し、[エクスポート] [検索結果 **のエクスポート** ![ ] アイコンをクリックして ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **レポートをエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="723a8-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="723a8-156">手順 2: レポートをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="723a8-156">Step 2: Download the report</span></span>

<span data-ttu-id="723a8-157">次の手順では、Azure ストレージ領域からローカルコンピューターにレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="723a8-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="723a8-158">レポートを生成した検索の詳細ウィンドウで、[ **レポートをコンピューターにエクスポート**する] で、[ **レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="723a8-159">[ **レポートのダウンロード** ] ページが表示され、コンピューターにダウンロードされたレポートに関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="723a8-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="723a8-160">ダウンロードされるアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="723a8-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="723a8-161">ダウンロードされるアイテムの推定合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="723a8-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="723a8-162">エクスポートされる内容にインデックスが付いているかどうか。</span><span class="sxs-lookup"><span data-stu-id="723a8-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="723a8-163">インデックスのないアイテムは、他の理由で、認識されている形式、暗号化されている、またはインデックスが作成されていないアイテムです。</span><span class="sxs-lookup"><span data-stu-id="723a8-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="723a8-164">SharePoint ドキュメントのバージョンをダウンロードするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="723a8-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="723a8-165">レポートエクスポートプロセスの状態。</span><span class="sxs-lookup"><span data-stu-id="723a8-165">The status of the report export process.</span></span> <span data-ttu-id="723a8-166">レポートの準備が完了していない場合でも、レポートのダウンロードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="723a8-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="723a8-167">**[エクスポート キー]** で、**[クリップボードにコピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="723a8-168">レポートをダウンロードするには、手順5でこのキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="723a8-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="723a8-169">すべてのユーザーが電子情報開示エクスポートツールをインストールして起動し、このキーを使用して検索レポートをダウンロードすることができるため、パスワードやその他のセキュリティ関連情報を保護するのと同じように、このキーを保護するための対策を必ず実行してください。</span><span class="sxs-lookup"><span data-stu-id="723a8-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="723a8-170">[ **レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="723a8-171">**電子情報開示エクスポートツール**をインストールするように求めるメッセージが表示されたら、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="723a8-172">**電子情報開示エクスポート ツール**で、手順 2 でコピーしたエクスポート キーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="723a8-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="723a8-173">[ **参照** ] をクリックして、レポートをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="723a8-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="723a8-174">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="723a8-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="723a8-175">**電子情報開示エクスポート ツール**には、ダウンロードする残りのアイテムの数とサイズの見積もりなど、エクスポート プロセスの状態に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="723a8-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="723a8-176">エクスポートプロセスが完了すると、ダウンロードされた場所にあるファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="723a8-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="723a8-177">電子情報開示ケースに関連付けられたコンテンツ検索のレポートをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="723a8-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="723a8-178">これを行うには、[ **電子情報** \> **開示**] に移動し、ケースを選択して、[編集アイコンの **編集**] をクリックし ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="723a8-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="723a8-179">[ **エクスポート** ] ページで、レポートのエクスポートを選択し、[詳細] ウィンドウの [ **レポートのダウンロード** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="723a8-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="723a8-180">レポートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="723a8-180">What's included in the report</span></span>

<span data-ttu-id="723a8-181">コンテンツ検索の結果に関するレポートを生成してエクスポートすると、次のドキュメントがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="723a8-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="723a8-182">**エクスポートの概要:** エクスポートの概要を含む Excel ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="723a8-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="723a8-183">これには、検索されたコンテンツソースの数、各コンテンツの場所からの検索結果の数、アイテムの推定数、エクスポートされるアイテムの実際の数、およびエクスポートされるアイテムの予想および実際のサイズなどの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="723a8-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="723a8-184">レポートをエクスポートするときに、インデックスのないアイテムを含めると、インデックスが作成されていないアイテムの数は、推定検索結果の合計数とダウンロードされた検索結果の合計数 (検索結果をエクスポートした場合) (エクスポートの概要レポートに表示された場合) に含まれます。</span><span class="sxs-lookup"><span data-stu-id="723a8-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="723a8-185">つまり、ダウンロードされるアイテムの合計数は、予想される結果の合計数と、インデックスが設定されていないアイテムの合計数と同じになります。</span><span class="sxs-lookup"><span data-stu-id="723a8-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="723a8-186">**マニフェスト:** 検索結果に含まれる各アイテムに関する情報を含むマニフェストファイル (XML 形式)。</span><span class="sxs-lookup"><span data-stu-id="723a8-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="723a8-187">**結果:** 検索結果と共にエクスポートされるインデックス化された各アイテムに関する情報を含む行を含む Excel ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="723a8-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="723a8-188">メールの場合、結果ログには、各メッセージに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="723a8-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="723a8-189">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="723a8-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="723a8-190">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="723a8-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="723a8-191">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="723a8-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="723a8-192">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="723a8-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="723a8-193">SharePoint および OneDrive for Business サイトのドキュメントの場合、結果ログには、各ドキュメントに関する以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="723a8-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="723a8-194">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="723a8-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="723a8-195">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="723a8-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="723a8-196">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="723a8-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="723a8-197">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="723a8-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="723a8-198">**結果**レポートの行数は、インデックスが設定されていない**アイテム**レポートに一覧表示されているアイテムの合計数を引いた数と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="723a8-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="723a8-199">**インデックスのないアイテム:** 検索結果に含まれるインデックスのないアイテムに関する情報を含む Excel ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="723a8-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="723a8-200">検索結果レポートを生成するときに、インデックスのないアイテムを含めない場合、このレポートは引き続きダウンロードされますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="723a8-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
