---
title: Advanced eDiscovery ケースのエクスポート ジョブをダウンロードする
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Azure Storage Explorer をインストールして使用して、Advanced eDiscovery のレビュー セットからエクスポートされたドキュメントをダウンロードします。
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751294"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="8e089-103">Advanced eDiscovery ケースでエクスポート ジョブをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="8e089-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="8e089-104">Advanced eDiscovery ケースのレビュー セットからドキュメントをエクスポートすると、ドキュメントは Microsoft が提供する Azure Storage の場所、または組織が管理する Azure Storage の場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="8e089-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="8e089-105">使用される Azure Storage の場所の種類は、ドキュメントのエクスポート時に選択されたオプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8e089-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="8e089-106">この記事では、Microsoft Azure Storage Explorer を使用して Azure Storage の場所に接続し、エクスポートされたドキュメントを参照してダウンロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e089-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="8e089-107">Azure Storage Explorer の詳細については、「クイック スタート: Azure Storage Explorer を使用する [」を参照してください](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。</span><span class="sxs-lookup"><span data-stu-id="8e089-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="8e089-108">手順 1: Azure Storage Explorer をインストールする</span><span class="sxs-lookup"><span data-stu-id="8e089-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="8e089-109">最初の手順は、Azure Storage Explorer をダウンロードしてインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="8e089-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="8e089-110">手順については [、Azure Storage Explorer ツールを参照してください](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="8e089-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="8e089-111">このツールを使用して、手順 3 でエクスポートしたドキュメントに接続してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8e089-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="8e089-112">手順 2: エクスポート ジョブから SAS URL を取得する</span><span class="sxs-lookup"><span data-stu-id="8e089-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="8e089-113">次の手順では、レビュー セットからドキュメントをエクスポートするエクスポート ジョブを作成するときに生成される共有アクセス署名 (SAS) URL [を取得します](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="8e089-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="8e089-114">Microsoft 提供の Azure Storage の場所または組織で管理されている Azure Storage の場所にアップロードされたドキュメントの SAS URL をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="8e089-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="8e089-115">どちらの場合も、SAS URL を使用して手順 3 で Azure Storage の場所に接続します。</span><span class="sxs-lookup"><span data-stu-id="8e089-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="8e089-116">[Advanced **eDiscovery] ページ** でケースに移動し、[エクスポート] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="8e089-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="8e089-117">[**エクスポート**]タブで、ダウンロードするエクスポートジョブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e089-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="8e089-118">フライアウト ページの [ **場所] で、** 表示される SAS URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8e089-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="8e089-119">必要に応じて、手順 3 でアクセスできるよう、ファイルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="8e089-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![[場所] の下に表示される SAS URL をコピーする](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="8e089-121">手順 3: Azure Storage の場所に接続する</span><span class="sxs-lookup"><span data-stu-id="8e089-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="8e089-122">最後の手順では、Azure Storage Explorer と SAS URL を使用して Azure Storage の場所に接続し、ローカル コンピューターにエクスポートしたドキュメントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8e089-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="8e089-123">手順 1 でインストールした Azure Storage Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="8e089-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="8e089-124">[アカウントの **追加] アイコンをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="8e089-124">Click the **Add account** icon.</span></span> <span data-ttu-id="8e089-125">または、[ストレージ アカウント] を右 **クリックすることもできます**。</span><span class="sxs-lookup"><span data-stu-id="8e089-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![[アカウントの追加] アイコンをクリックします。](../media/AzureStorageConnect.png)

3. <span data-ttu-id="8e089-127">[Azure **Storage への接続** ] ページで、[共有アクセス署名 **(SAS) URI** を使用する] をクリックし、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8e089-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![[共有アクセス署名 (SAS) URI を使用する] をクリックし、[次へ] をクリックします。](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="8e089-129">[SAS URI にアタッチ] ページで **、[URI]** ボックスをクリックし、手順 2 で取得した SAS URL を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8e089-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![[URI] ボックスに SAS URL を貼り付ける](../media/AzureStorageConnect3.png)

    <span data-ttu-id="8e089-131">SAS URL の一部が [表示名] ボックスに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="8e089-132">これは、ストレージの場所に接続した後にストレージ アカウントの下に作成されるコンテナーの表示名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="8e089-133">この名前は、Advanced eDiscovery ケースの ID と一意の識別子で構成されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="8e089-134">デフォルトの表示名をそのまま使用することも、変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e089-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="8e089-135">変更する場合、表示名は一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8e089-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="8e089-136">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e089-136">Click **Next**.</span></span>

    <span data-ttu-id="8e089-137">[ **接続の概要]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-137">The **Connection summary** page is displayed.</span></span>

    ![Azure Storage の場所に接続するには、[接続の概要] ページで [接続] をクリックします。](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="8e089-139">[接続 **の概要] ページ** で、接続情報を確認し、[接続] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8e089-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="8e089-140">Blob **コンテナー ノード**([**ストレージ** アカウント]  >  **(添付コンテナー) の下)** \> が開きます。</span><span class="sxs-lookup"><span data-stu-id="8e089-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![BLOB コンテナー ノード内のジョブをエクスポートする](../media/AzureStorageConnect5.png)

    <span data-ttu-id="8e089-142">手順 4 の表示名を持つコンテナーが含まれている。</span><span class="sxs-lookup"><span data-stu-id="8e089-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="8e089-143">このコンテナーには、作成した各エクスポート ジョブのフォルダーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="8e089-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="8e089-144">これらのフォルダーの名前は、エクスポート ジョブの ID に対応する ID です。</span><span class="sxs-lookup"><span data-stu-id="8e089-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="8e089-145">これらのエクスポート ID (およびエクスポートの名前) は、[ジョブ] タブに表示されるエクスポート ジョブの準備データごとに、フライアウト ページの[サポート情報] にあります。 </span><span class="sxs-lookup"><span data-stu-id="8e089-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="8e089-146">エクスポート ジョブ フォルダーをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="8e089-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="8e089-147">フォルダーとエクスポート レポートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-147">A list of folders and export reports is displayed.</span></span>
   
    ![エクスポート フォルダーには、エクスポートされたファイルとエクスポート レポートが含まれている](../media/AzureStorageConnect6.png)

   <span data-ttu-id="8e089-149">エクスポート ジョブ フォルダーには、次のアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e089-149">The export job folder contains the following items.</span></span> <span data-ttu-id="8e089-150">エクスポート フォルダー内の実際のアイテムは、エクスポート ジョブの作成時に構成されたエクスポート オプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="8e089-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="8e089-151">詳細については、「レビュー セット [からドキュメントをエクスポートする」を参照してください](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="8e089-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="8e089-152">Export_load_file.csv: この CSV ファイルは、エクスポートされた各ドキュメントに関する情報を含む詳細エクスポート レポートです。</span><span class="sxs-lookup"><span data-stu-id="8e089-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="8e089-153">ファイルは、ドキュメントの各メタデータ プロパティの列で構成されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="8e089-154">このレポートに含まれるメタデータの一覧と説明については[、Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md)のドキュメント メタデータ フィールドの表の 「エクスポートされたフィールド名」列を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e089-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="8e089-155">Summary.txt: エクスポート統計を含むエクスポートの概要を含むテキスト ファイル。</span><span class="sxs-lookup"><span data-stu-id="8e089-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="8e089-156">Extracted_text_files: このフォルダーには、エクスポートされた各ドキュメントのテキスト ファイル バージョンが含まれる。</span><span class="sxs-lookup"><span data-stu-id="8e089-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="8e089-157">NativeFiles: このフォルダーには、エクスポートされた各ドキュメントのネイティブ ファイル バージョンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="8e089-158">Error_files: エクスポート ジョブにエラー ファイルが含まれている場合、このフォルダーには次のアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e089-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="8e089-159">ExtractionError.csv: この CSV ファイルには、親アイテムから適切に抽出されていないファイルに使用可能なメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e089-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="8e089-160">ProcessingError: このフォルダーには、処理エラーのあるドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e089-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="8e089-161">このコンテンツはアイテム レベルです。つまり、添付ファイルで処理エラーが発生した場合、添付ファイルを含むドキュメントもこのフォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e089-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="8e089-162">エクスポート内のすべてのコンテンツをエクスポートするには、エクスポートフォルダーを選択し、[**ダウンロード**]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e089-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="8e089-163">エクスポートしたファイルをダウンロードする場所を指定して、[フォルダを選択]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e089-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="8e089-164">Azure Storage Explorer がエクスポート プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8e089-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="8e089-165">エクスポートしたアイテムのダウンロードの状態が [アクティビティ] ウィンドウに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="8e089-166">ダウンロードが完了すると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e089-166">A message is displayed when the download is finished.</span></span>

    ![ダウンロードが完了するとメッセージが表示される](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="8e089-168">エクスポートジョブ全体をダウンロードする代わりに、ダウンロードする特定のアイテムを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8e089-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="8e089-169">また、アイテムをダウンロードする代わりに、アイテムをダブルクリックして表示できます。</span><span class="sxs-lookup"><span data-stu-id="8e089-169">And instead of downloading items, you can double-click an item to view it.</span></span>
