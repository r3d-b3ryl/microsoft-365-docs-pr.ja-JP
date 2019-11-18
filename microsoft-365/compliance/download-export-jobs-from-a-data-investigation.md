---
title: データ調査からエクスポートジョブをダウンロードする
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
ms.assetid: ''
description: データ調査で証拠からエクスポートされたドキュメントをダウンロードするには、Azure ストレージエクスプローラーをインストールして使用します。
ms.openlocfilehash: af71cb43f91c940e4c5edb8ca7be39f4bca9b3be
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686897"
---
# <a name="download-export-jobs"></a><span data-ttu-id="19429-103">エクスポート ジョブのダウンロード</span><span class="sxs-lookup"><span data-stu-id="19429-103">Download export jobs</span></span>

<span data-ttu-id="19429-104">データ調査の証拠からドキュメントをエクスポートすると、ドキュメントが Microsoft 提供の Azure ストレージの場所または組織によって管理される Azure ストレージの場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="19429-104">When you export documents from evidence in a data investigation, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="19429-105">使用される Azure ストレージの場所の種類は、ドキュメントのエクスポート時に選択されたオプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="19429-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span> 

<span data-ttu-id="19429-106">この記事では、Microsoft Azure ストレージエクスプローラーを使用して、エクスポートされたドキュメントを参照およびダウンロードするために Azure ストレージの場所に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19429-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="19429-107">Azure ストレージエクスプローラーの詳細については、「[クイックスタート: Azure ストレージエクスプローラーを使用する](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19429-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="19429-108">手順 1: Azure ストレージエクスプローラーをインストールする</span><span class="sxs-lookup"><span data-stu-id="19429-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="19429-109">最初の手順として、Azure ストレージエクスプローラーをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="19429-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="19429-110">手順については、「 [Azure ストレージエクスプローラーツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19429-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="19429-111">このツールを使用して、手順3でエクスポートされたドキュメントに接続し、ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="19429-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="19429-112">手順 2: エクスポートジョブから SAS URL を取得する</span><span class="sxs-lookup"><span data-stu-id="19429-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="19429-113">次の手順では、[レビューセットからドキュメントをエクスポート](export-documents-from-review-set.md)するエクスポートジョブを作成したときに生成される shared access SIGNATURE (SAS) URL を取得します。</span><span class="sxs-lookup"><span data-stu-id="19429-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="19429-114">Microsoft が提供する Azure ストレージの場所または組織によって管理される Azure ストレージの場所にアップロードされたドキュメントの SAS URL をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="19429-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="19429-115">どちらの場合も、手順3で、SAS URL を使用して Azure ストレージの場所に接続します。</span><span class="sxs-lookup"><span data-stu-id="19429-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="19429-116">[**データ調査**] ページで、調査に移動し、[**エクスポート**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-116">On the **Data investigations** page, go to the investigation, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="19429-117">[**エクスポート**] タブで、ダウンロードするエクスポートジョブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="19429-118">ポップアップページの [**場所**] で、表示されている SAS URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="19429-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="19429-119">必要に応じて、手順3でアクセスできるようにファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="19429-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![[場所] に表示されている SAS URL をコピーする](media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="19429-121">手順 3: Azure ストレージの場所に接続する</span><span class="sxs-lookup"><span data-stu-id="19429-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="19429-122">最後の手順として、Azure ストレージエクスプローラーと SAS URL を使用して Azure ストレージの場所に接続し、ローカルコンピューターにエクスポートしたドキュメントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="19429-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1.  <span data-ttu-id="19429-123">手順1でインストールした Azure ストレージエクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="19429-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="19429-124">[**アカウントの追加**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-124">Click the **Add account** icon.</span></span> <span data-ttu-id="19429-125">または、[**ストレージアカウント**] を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![[アカウントの追加] アイコンをクリックします。](media/AzureStorageConnect.png)

3.  <span data-ttu-id="19429-127">[ **Azure ストレージへの接続**] ページで、[**共有アクセス署名 (SAS) URI を使用**する] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![[共有アクセス署名 (SAS) URI を使用する] をクリックし、[次へ] をクリックします。](media/AzureStorageConnect2.png)

4.  <span data-ttu-id="19429-129">[ **SAS uri に接続**する] ページで、[uri] ボックスをクリックし、手順2で取得した SAS URL を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="19429-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![[URI] ボックスに SAS URL を貼り付けます。](media/AzureStorageConnect3.png)

    <span data-ttu-id="19429-131">SAS URL の一部が [**表示名**] ボックスに表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19429-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="19429-132">これは、保存場所に接続した後、**ストレージアカウント**の下に作成されるコンテナーの表示名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="19429-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="19429-133">この名前は、データの調査元の ID と一意の識別子で構成されます。</span><span class="sxs-lookup"><span data-stu-id="19429-133">This name consists of the ID of the data investigation is from and a unique identifier.</span></span> <span data-ttu-id="19429-134">既定の表示名をそのまま使用することも、それを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="19429-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="19429-135">この設定を変更する場合は、表示名を一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19429-135">If you change it, the display name must be unique.</span></span>

5.  <span data-ttu-id="19429-136">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-136">Click **Next**.</span></span>

    <span data-ttu-id="19429-137">[**接続の概要**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19429-137">The **Connection summary** page is displayed.</span></span>
   
    ![[接続の概要] ページの [接続] をクリックして、Azure ストレージの場所に接続します。](media/AzureStorageConnect4.png)

6. <span data-ttu-id="19429-139">[**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span> 

    <span data-ttu-id="19429-140">**Blob コンテナ**ノード (**ストレージアカウント** > **(接続されたコンテナー)** \>が開きます。</span><span class="sxs-lookup"><span data-stu-id="19429-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span> 

    ![Blob コンテナノードのジョブをエクスポートする](media/AzureStorageConnect5.png)

    <span data-ttu-id="19429-142">これには、手順4の表示名を持つという名前のコンテナーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19429-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="19429-143">このコンテナーには、作成した各エクスポートジョブのフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19429-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="19429-144">これらのフォルダーには、エクスポートジョブの ID に対応する ID を使用して名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="19429-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="19429-145">これらのエクスポート Id (およびエクスポートの名前) は、[**ジョブ**] タブに表示されている**エクスポートジョブのデータを準備**するためのフライアウトページの [**サポート情報**] にあります。</span><span class="sxs-lookup"><span data-stu-id="19429-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="19429-146">[エクスポートジョブ] フォルダーをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="19429-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="19429-147">フォルダーの一覧とレポートのエクスポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19429-147">A list of folders and export reports is displayed.</span></span>
   
    ![エクスポートフォルダーにはエクスポートファイルが含まれており、レポートをエクスポートする](media/AzureStorageConnect6.png)

   <span data-ttu-id="19429-149">[エクスポートジョブ] フォルダーには以下のアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19429-149">The export job folder contains the following items.</span></span> <span data-ttu-id="19429-150">エクスポートフォルダー内の実際のアイテムは、エクスポートジョブの作成時に構成されたエクスポートオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="19429-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="19429-151">詳細については、「[レビューセットからドキュメントをエクスポートする](export-documents-from-review-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19429-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="19429-152">Export_load_file csv: この CSV ファイルは、エクスポートされた各ドキュメントに関する情報を含む詳細エクスポートレポートです。</span><span class="sxs-lookup"><span data-stu-id="19429-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="19429-153">ファイルは、ドキュメントのメタデータプロパティごとに1つの列で構成されます。</span><span class="sxs-lookup"><span data-stu-id="19429-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="19429-154">このレポートに含まれているメタデータの一覧と説明については、「 [Advanced eDiscovery」の「ドキュメントメタデータフィールド](document-metadata-fields.md)の表」の「エクスポートされた**フィールド名**」列を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19429-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields.md).</span></span>
    
    - <span data-ttu-id="19429-155">Summary.txt: エクスポート統計情報を含むエクスポートの概要を含むテキストファイル。</span><span class="sxs-lookup"><span data-stu-id="19429-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="19429-156">Extracted_text_files: このフォルダーには、エクスポートされた各ドキュメントのテキストファイルバージョンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19429-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="19429-157">ファイル: このフォルダーには、エクスポートされた各ドキュメントのネイティブファイルバージョンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="19429-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="19429-158">Error_files: エクスポートジョブにエラーファイルが含まれている場合、このフォルダーには以下のアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19429-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="19429-159">ExtractionError csv: この CSV ファイルには、親アイテムから正しく抽出されなかったファイルに使用可能なメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19429-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="19429-160">ProcessingError: このフォルダーには、処理エラーが発生したドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19429-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="19429-161">このコンテンツはアイテムレベルで設定されています。これは、添付ファイルに処理エラーがあった場合に、添付ファイルを含むドキュメントがこのフォルダーにも含まれることを意味します。</span><span class="sxs-lookup"><span data-stu-id="19429-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="19429-162">エクスポートですべてのコンテンツをエクスポートするには、エクスポートフォルダーを選択し、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="19429-163">エクスポートされたファイルをダウンロードする場所を指定して、[**フォルダーの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19429-163">Specify the location where you want to download the exported files, and then click **Select folder**.</span></span>

    <span data-ttu-id="19429-164">Azure ストレージエクスプローラーがエクスポートプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="19429-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="19429-165">[**操作**] ウィンドウに、エクスポートされたアイテムのダウンロードの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19429-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="19429-166">ダウンロードが完了すると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19429-166">A message is displayed when the download is finished.</span></span>

    ![ダウンロードが完了すると、メッセージが表示されます。](media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="19429-168">エクスポートジョブ全体をダウンロードするのではなく、特定のアイテムを選択してダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="19429-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="19429-169">アイテムをダウンロードするのではなく、アイテムをダブルクリックして表示することができます。</span><span class="sxs-lookup"><span data-stu-id="19429-169">And instead of downloading items, you can double-click an item to view it.</span></span>

