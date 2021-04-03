---
title: 組織の Azure Storage アカウントにドキュメントをエクスポートする
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
ms.custom: seo-marvel-mar2020
description: レビュー セット内のドキュメントを Azure Storage アカウントにエクスポートし、Azure Storage Explorer を使用してローカル コンピューターにダウンロードします。
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574729"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="df2e3-103">レビュー セット内のドキュメントを Azure Storage アカウントにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="df2e3-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="df2e3-104">Advanced eDiscovery ケースのレビュー セットからドキュメントをエクスポートする場合は、組織が管理する Azure Storage アカウントにドキュメントをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="df2e3-105">このオプションを使用した場合、ドキュメントは Azure Storage の場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-105">If you used this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="df2e3-106">ドキュメントがエクスポートされた後は、Azure Storage Explorer を使用してドキュメントにアクセス (およびローカル コンピューターまたは他の場所にダウンロード) できます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="df2e3-107">この記事では、ドキュメントを Azure Storage アカウントにエクスポートする方法と、Azure Storage Explorer を使用して Azure Storage の場所に接続してエクスポートされたドキュメントをダウンロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="df2e3-108">Azure Storage Explorer の詳細については、「Use Azure Storage [Explorer」を参照してください](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。</span><span class="sxs-lookup"><span data-stu-id="df2e3-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="df2e3-109">レビュー セットからドキュメントをエクスポートする前に</span><span class="sxs-lookup"><span data-stu-id="df2e3-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="df2e3-110">レビュー セットからドキュメントをエクスポートするには、Azure Storage アカウントの共有アクセス署名 (SAS) トークンと、ストレージ アカウント内の特定のコンテナーの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2e3-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="df2e3-111">手順 2 を実行する際は、必ず手に (たとえば、テキスト ファイルにコピーする) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2e3-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="df2e3-112">**SAS トークン**: SAS トークンを取得するには、Azure Storage アカウント用 (コンテナー用ではなく) を取得してください。</span><span class="sxs-lookup"><span data-stu-id="df2e3-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="df2e3-113">Azure Storage でアカウントの SAS トークンを生成できます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="df2e3-114">これを行うには、Azure Storage アカウントに移動し、[ストレージ アカウント]ブレードの [設定] で [アクセス署名の共有] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="df2e3-115">SAS トークンを生成するときに、既定の設定を使用し、すべてのリソースの種類を許可します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="df2e3-116">**コンテナー URL**: レビュー セットドキュメントをアップロードするコンテナーを作成し、そのコンテナーの URL のコピーを取得する必要があります。たとえば、 `https://ediscoverydata.blob.core.windows.net/exportdata` .</span><span class="sxs-lookup"><span data-stu-id="df2e3-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="df2e3-117">URL を取得するには、Azure Storage のコンテナーに移動し、コンテナーブレードの [設定] セクションの [プロパティ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="df2e3-118">Azure Storage Explorer をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="df2e3-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="df2e3-119">手順については [、「Azure Storage Explorer ツール」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="df2e3-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="df2e3-120">このツールを使用して、Azure Storage アカウントのコンテナーに接続し、手順 1 でエクスポートしたドキュメントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="df2e3-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="df2e3-121">手順 1: レビュー セットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="df2e3-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="df2e3-122">最初の手順は、レビュー セットからドキュメントをエクスポートするエクスポート ジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="df2e3-123">すべてのエクスポート オプションの詳細な手順については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="df2e3-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="df2e3-124">次の手順では、組織の Azure Storage アカウントにドキュメントをエクスポートする設定を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="df2e3-125">Microsoft 365 コンプライアンス センターで、高度な電子情報開示ケースを開き、[レビュー セット] タブを選択し、エクスポートするレビュー セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="df2e3-126">レビュー セットで、[アクションのエクスポート]**を**  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="df2e3-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="df2e3-127">[エクスポート **オプション] フライ** アウト ページで、エクスポートの名前 (必須) と説明 (オプション) を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="df2e3-128">ドキュメント、メタデータ、コンテンツ、およびオプションセクションの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="df2e3-129">これらの設定の詳細については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="df2e3-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="df2e3-130">[出力 **オプション] セクション** で **、[Azure Storage アカウント** にエクスポートされた圧縮ディレクトリ構造] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="df2e3-131">対応するフィールドにストレージ アカウントのコンテナー URL と SAS トークンを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![接続 URL と SAS トークンを対応するフィールドに貼り付ける](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="df2e3-133">[エクスポート **] を** クリックしてエクスポート ジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="df2e3-134">手順 2: エクスポート ジョブから SAS URL を取得する</span><span class="sxs-lookup"><span data-stu-id="df2e3-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="df2e3-135">次の手順では、手順 1 でエクスポート ジョブを作成した後に生成される SAS URL を取得します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="df2e3-136">SAS URL を使用して、レビュー セット ドキュメントをエクスポートした Azure Storage アカウントのコンテナーに接続します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="df2e3-137">[高度 **な電子情報開示] ページ** で、ケースに移動し、[エクスポート] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="df2e3-138">[**エクスポート**]タブで、ダウンロードするエクスポートジョブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2e3-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="df2e3-139">これは、手順 1 で作成したエクスポート ジョブです。</span><span class="sxs-lookup"><span data-stu-id="df2e3-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="df2e3-140">[フライアウト] ページの [場所] **で**、表示される SAS URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="df2e3-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="df2e3-141">必要に応じて、テキスト ファイルに保存して、手順 3 でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![[場所] の下に表示される SAS URL をコピーする](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="df2e3-143">エクスポート ジョブに表示される SAS URL は、コンテナー URL と Azure Storage アカウントの SAS トークンの連結です。</span><span class="sxs-lookup"><span data-stu-id="df2e3-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="df2e3-144">エクスポート ジョブからコピーするか、URL と SAS トークンを組み合わせて作成できます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="df2e3-145">手順 3: Azure Storage コンテナーに接続する</span><span class="sxs-lookup"><span data-stu-id="df2e3-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="df2e3-146">最後に、Azure Storage Explorer と SAS URL を使用して Azure Storage アカウントのコンテナーに接続し、エクスポートされたドキュメントをローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="df2e3-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="df2e3-147">ダウンロードしてインストールした Azure Storage Explorer を起動します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="df2e3-148">[接続ダイアログ **を開く] アイコンを** クリックします。</span><span class="sxs-lookup"><span data-stu-id="df2e3-148">Click the **Open Connect Dialog** icon.</span></span>

   ![[アカウントの追加] アイコンをクリックします。](../media/AzureStorageConnect.png)

3. <span data-ttu-id="df2e3-150">[Azure **ストレージへの接続] ページで、[BLOB** コンテナー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="df2e3-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="df2e3-151">[認証方法 **の選択] ページ** で、[共有アクセス署名 **(SAS)** ] オプションを選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="df2e3-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="df2e3-152">[接続 **情報の入力]** ページで、[BLOB コンテナーの SAS URL] ボックスに SAS URL (手順 2 のエクスポート ジョブで取得した) **を貼り付** けます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![[URI] ボックスに SAS URL を貼り付ける](../media/AzureStorageConnect3.png)

    <span data-ttu-id="df2e3-154">コンテナー名が [表示名] ボックス **に表示されます** 。</span><span class="sxs-lookup"><span data-stu-id="df2e3-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="df2e3-155">この名前は編集できます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-155">You can edit this name.</span></span>

6. <span data-ttu-id="df2e3-156">[ **次へ]** をクリックして **概要ページを表示** し、[接続] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="df2e3-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="df2e3-157">[Blob **コンテナー]** ノード **([ストレージ アカウント**  >  **] (接続されたコンテナー) が** \> 開きます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Blobs コンテナー ノードのジョブのエクスポート](../media/AzureStorageConnect5.png)

    <span data-ttu-id="df2e3-159">手順 5 の表示名を持つコンテナーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="df2e3-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="df2e3-160">このコンテナーには、Azure Storage アカウントのコンテナーにダウンロードしたエクスポート ジョブごとにフォルダーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="df2e3-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="df2e3-161">これらのフォルダーの名前は、エクスポート ジョブの ID に対応する ID です。</span><span class="sxs-lookup"><span data-stu-id="df2e3-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="df2e3-162">これらのエクスポートの ID (およびエクスポートの名前) は、[高度な電子情報開示] ケースの [ジョブ] タブに一覧表示されているエクスポートジョブの各準備データのフライアウト ページの [サポート情報] にあります。 </span><span class="sxs-lookup"><span data-stu-id="df2e3-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="df2e3-163">エクスポート ジョブ フォルダーをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="df2e3-164">フォルダーとエクスポート レポートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-164">A list of folders and export reports is displayed.</span></span>

    ![エクスポート フォルダーには、エクスポートされたファイルとエクスポート レポートが含まれる](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="df2e3-166">エクスポート ジョブからすべてのコンテンツをエクスポートするには、上矢印をクリックしてエクスポート ジョブ フォルダーに戻り、[ダウンロード] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="df2e3-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="df2e3-167">エクスポートしたファイルをダウンロードする場所を指定して、[フォルダを選択]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2e3-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="df2e3-168">Azure Storage Explorer は、ダウンロード プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="df2e3-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="df2e3-169">エクスポートしたアイテムのダウンロードの状態が [アクティビティ] ウィンドウ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="df2e3-170">ダウンロードが完了すると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="df2e3-171">Azure Storage Explorer でエクスポート ジョブ全体をダウンロードする代わりに、ダウンロードして表示する特定のアイテムを選択できます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="df2e3-172">詳細情報</span><span class="sxs-lookup"><span data-stu-id="df2e3-172">More information</span></span>

- <span data-ttu-id="df2e3-173">エクスポート ジョブ フォルダーには、次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-173">The export job folder contains the following items.</span></span> <span data-ttu-id="df2e3-174">エクスポート フォルダー内の実際のアイテムは、エクスポート ジョブの作成時に構成されたエクスポート オプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="df2e3-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="df2e3-175">これらのオプションの詳細については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="df2e3-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="df2e3-176">Export_load_file.csv: この CSV ファイルは、エクスポートされた各ドキュメントに関する情報を含む詳細エクスポート レポートです。</span><span class="sxs-lookup"><span data-stu-id="df2e3-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="df2e3-177">ファイルは、ドキュメントの各メタデータ プロパティの列で構成されます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="df2e3-178">このレポートに含まれるメタデータの一覧と説明については、「Advanced eDiscoveryのドキュメント メタデータ フィールド」の表の「エクスポートされたフィールド名」[列を参照してください](document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="df2e3-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="df2e3-179">Summary.txt: エクスポート統計を含むエクスポートの概要を含むテキスト ファイル。</span><span class="sxs-lookup"><span data-stu-id="df2e3-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="df2e3-180">Extracted_text_files: このフォルダーには、エクスポートされた各ドキュメントのテキスト ファイル バージョンが含まれる。</span><span class="sxs-lookup"><span data-stu-id="df2e3-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="df2e3-181">NativeFiles: このフォルダーには、エクスポートされた各ドキュメントのネイティブ ファイル バージョンが含まれる。</span><span class="sxs-lookup"><span data-stu-id="df2e3-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="df2e3-182">Error_files: エクスポート ジョブにエラー ファイルが含まれている場合、このフォルダーには次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="df2e3-183">ExtractionError.csv: この CSV ファイルには、親アイテムから適切に抽出されていないファイルに使用可能なメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df2e3-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="df2e3-184">ProcessingError: このフォルダーには、処理エラーのあるドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df2e3-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="df2e3-185">このコンテンツはアイテム レベルです。つまり、添付ファイルに処理エラーが発生した場合、添付ファイルを含むドキュメントもこのフォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="df2e3-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
