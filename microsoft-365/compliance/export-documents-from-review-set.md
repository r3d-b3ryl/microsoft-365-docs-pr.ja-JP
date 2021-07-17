---
title: レビュー セットからドキュメントをエクスポートする
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
ms.assetid: ''
description: プレゼンテーションまたは外部レビューのレビュー セットAdvanced eDiscoveryコンテンツを選択してエクスポートする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461401"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="513d0-103">[ドキュメント] のレビュー セットからドキュメントをエクスポートAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="513d0-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="513d0-104">エクスポートを使用すると、ユーザーは、ドキュメントをダウンロード パッケージのレビュー セットからエクスポートするときに、ダウンロード パッケージに含まれるコンテンツをカスタマイズAdvanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="513d0-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="513d0-105">レビュー セットからドキュメントをエクスポートするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="513d0-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="513d0-106">次のMicrosoft 365 コンプライアンス センターケースを開Advanced eDiscovery、[レビュー セット] タブを選択し、エクスポートするレビュー セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="513d0-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="513d0-107">レビュー セットで、[アクションのエクスポート]**を**  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="513d0-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="513d0-108">[エクスポート] ツールは、エクスポートを構成する設定を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="513d0-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="513d0-109">一部のオプションは既定で選択されますが、これらを変更できます。</span><span class="sxs-lookup"><span data-stu-id="513d0-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="513d0-110">構成できるエクスポート オプションの説明については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="513d0-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![レビュー セットからアイテムをエクスポートするための構成オプション](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="513d0-112">エクスポートを構成した後、[エクスポート] **をクリックして** エクスポート プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="513d0-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="513d0-113">[出力オプション] セクションで選択したオプションに応じて、直接ダウンロードするか、組織のアカウントでエクスポート ファイルにAzure Storageできます。</span><span class="sxs-lookup"><span data-stu-id="513d0-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="513d0-114">エクスポート ジョブは、ケースの一生保持されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="513d0-115">ただし、エクスポート ジョブが完了した後、30 日以内にエクスポート ジョブからコンテンツをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="513d0-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="513d0-116">エクスポート オプション</span><span class="sxs-lookup"><span data-stu-id="513d0-116">Export options</span></span>

<span data-ttu-id="513d0-117">エクスポートを構成するには、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="513d0-117">Use the following options to configure the export.</span></span> <span data-ttu-id="513d0-118">一部の出力オプションでは、特に、テキスト ファイルと編集された PDF のエクスポートが PST 形式にエクスポートされる場合、一部のオプションが使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="513d0-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="513d0-119">**エクスポート名**: エクスポート ジョブの名前。</span><span class="sxs-lookup"><span data-stu-id="513d0-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="513d0-120">これは、ダウンロードされる ZIP ファイルに名前を付けるのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="513d0-121">**説明**: 説明を追加するフリー テキスト フィールド。</span><span class="sxs-lookup"><span data-stu-id="513d0-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="513d0-122">**これらのドキュメントをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="513d0-122">**Export these documents**</span></span>

  - <span data-ttu-id="513d0-123">選択したドキュメントのみ: このオプションは、現在選択されているドキュメントのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="513d0-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="513d0-124">このオプションは、レビュー セットでアイテムが選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="513d0-124">This option is only available when items are selected in a review set.</span></span>
  
  - <span data-ttu-id="513d0-125">すべてのフィルター処理されたドキュメント: このオプションは、アクティブなフィルター内のドキュメントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="513d0-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="513d0-126">このオプションは、レビュー セットにフィルターが適用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="513d0-126">This option is only available when a filter is applied to the review set.</span></span>
  
  - <span data-ttu-id="513d0-127">レビュー セット内のすべてのドキュメント: このオプションは、レビュー セット内のすべてのドキュメントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="513d0-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="513d0-128">**出力オプション**: エクスポートされたコンテンツは、Web ブラウザーを介して直接ダウンロードするか、またはアカウントにAzure Storageできます。</span><span class="sxs-lookup"><span data-stu-id="513d0-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="513d0-129">最初の 2 つのオプションは、直接ダウンロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="513d0-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="513d0-130">レポートのみ: サマリー ファイルと読み込みファイルだけが作成されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-130">Reports only: Only the summary and load file are created.</span></span>
  
  - <span data-ttu-id="513d0-131">ルーズ ファイルと PST (電子メールは可能な場合は PST に追加されます): ファイルは、ネイティブ アプリケーションのユーザーが見た元のディレクトリ構造に似た形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="513d0-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="513d0-132">詳細については、「ルーズ ファイルと [PST エクスポート構造」セクションを参照](#loose-files-and-pst-export-structure) してください。</span><span class="sxs-lookup"><span data-stu-id="513d0-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="513d0-133">圧縮ディレクトリ構造: ファイルはエクスポートされ、ダウンロードに含まれます。</span><span class="sxs-lookup"><span data-stu-id="513d0-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="513d0-134">サーバー アカウントにエクスポートされたAzure Storage構造: ファイルは、組織のアカウントにAzure Storageされます。</span><span class="sxs-lookup"><span data-stu-id="513d0-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="513d0-135">このオプションでは、ファイルのエクスポート先として、Azure Storageの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="513d0-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="513d0-136">また、ユーザーアカウントに共有アクセス署名 (SAS) トークンをAzure Storageがあります。</span><span class="sxs-lookup"><span data-stu-id="513d0-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="513d0-137">詳細については、「レビュー セット[内のドキュメントをアカウントにエクスポートする」をAzure Storageしてください](download-export-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="513d0-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="513d0-138">**Include**</span><span class="sxs-lookup"><span data-stu-id="513d0-138">**Include**</span></span>
  
  - <span data-ttu-id="513d0-139">タグ: 選択すると、タグ付け情報が読み込みファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="513d0-139">Tags: When selected, tagging information is included in the load file.</span></span>
  
  - <span data-ttu-id="513d0-140">テキスト ファイル: このオプションには、エクスポートに抽出されたテキスト バージョンのネイティブ ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="513d0-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="513d0-141">編集されたネイティブを変換された PDF に置き換える: レビュー中に編集された PDF ファイルが生成された場合、これらのファイルはエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="513d0-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="513d0-142">(このオプションを選択しない場合) やり直されたネイティブ ファイルのみをエクスポートするか、実際のやり直しを含む PDF ファイルをエクスポートするには、このオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="513d0-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

<span data-ttu-id="513d0-143">次のセクションでは、緩いファイルと圧縮ディレクトリ構造オプションのフォルダー構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="513d0-143">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span> <span data-ttu-id="513d0-144">エクスポートは、圧縮されていないコンテンツの最大サイズが 75 GB の ZIP ファイルに分割されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="513d0-145">エクスポート サイズが 75 GB 未満の場合、エクスポートはサマリー ファイルと 1 つの ZIP ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="513d0-146">75 GB を超える圧縮されていないデータをエクスポートする場合は、複数の ZIP ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-146">For exports larger than 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="513d0-147">ダウンロード後、ZIP ファイルを 1 つの場所に圧縮解除して、完全なエクスポートを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="513d0-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="513d0-148">ルーズ ファイルと PST エクスポート構造</span><span class="sxs-lookup"><span data-stu-id="513d0-148">Loose files and PST export structure</span></span>

<span data-ttu-id="513d0-149">このエクスポート オプションを選択すると、エクスポートされたコンテンツは次の構造で整理されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="513d0-150">Summary.csv: レビュー セットからエクスポートされたコンテンツの概要を含む</span><span class="sxs-lookup"><span data-stu-id="513d0-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="513d0-151">ルート フォルダー: [Export Name] x という名前のこのフォルダーは、z.zip ZIP ファイル パーティションごとに繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="513d0-152">Export_load_file_xのz.csv: メタデータ ファイル。</span><span class="sxs-lookup"><span data-stu-id="513d0-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="513d0-153">警告とエラー x z.csv: このファイルには、レビュー セットからエクスポートしようとするときに発生したエラーに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="513d0-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  
  - <span data-ttu-id="513d0-154">Exchange: このフォルダーには、PST ファイルにExchangeファイルからのすべてのコンテンツが含まれる。</span><span class="sxs-lookup"><span data-stu-id="513d0-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="513d0-155">このオプションには、編集された PDF ファイルを含めません。</span><span class="sxs-lookup"><span data-stu-id="513d0-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="513d0-156">レビュー セットで添付ファイルが選択されている場合、親メールは添付ファイルと一緒にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="513d0-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  
  - <span data-ttu-id="513d0-157">SharePoint: このフォルダーには、すべてのネイティブ コンテンツがSharePointファイル形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="513d0-158">このオプションには、編集された PDF ファイルを含めません。</span><span class="sxs-lookup"><span data-stu-id="513d0-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="513d0-159">ディレクトリ構造の要約</span><span class="sxs-lookup"><span data-stu-id="513d0-159">Condensed directory structure</span></span>

- <span data-ttu-id="513d0-160">Summary.csv: レビュー セットからエクスポートされたコンテンツの概要を含む</span><span class="sxs-lookup"><span data-stu-id="513d0-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="513d0-161">ルート フォルダー: [Export Name] x という名前のこのフォルダーは、z.zip ZIP ファイル パーティションごとに繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="513d0-162">Export_load_file_xのz.csv: メタデータ ファイルと、ZIP ファイルに格納されている各ファイルの場所も含まれます。</span><span class="sxs-lookup"><span data-stu-id="513d0-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  
  - <span data-ttu-id="513d0-163">警告とエラー x z.csv: このファイルには、レビュー セットからエクスポートしようとするときに発生したエラーに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="513d0-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>

  - <span data-ttu-id="513d0-164">NativeFiles: このフォルダーには、エクスポートされたネイティブ ファイルすべてが含まれる。</span><span class="sxs-lookup"><span data-stu-id="513d0-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="513d0-165">[変更されたネイティブを変換された PDF に置き換える] オプションを選択した場合、ネイティブ ファイルは編集 *された PDF に置き換* えられる。</span><span class="sxs-lookup"><span data-stu-id="513d0-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  
  - <span data-ttu-id="513d0-166">Error_files: このフォルダーには、抽出エラーまたは他の処理エラーが発生したファイルが含まれる。</span><span class="sxs-lookup"><span data-stu-id="513d0-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="513d0-167">ファイルは、ExtractionError または ProcessingError のいずれかの個別のフォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="513d0-168">これらのファイルは、読み込みファイルに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-168">These files are listed in the load file.</span></span>

  - <span data-ttu-id="513d0-169">Extracted_text_files: このフォルダーには、処理時に生成された抽出されたテキスト ファイルすべてが含まれる。</span><span class="sxs-lookup"><span data-stu-id="513d0-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="513d0-170">アカウントにエクスポートされたディレクトリ構造をAzure Storageする</span><span class="sxs-lookup"><span data-stu-id="513d0-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="513d0-171">このオプションは、*圧縮* ディレクトリ構造と同じ一般的な構造を使用しますが、コンテンツは圧縮されません。データはユーザーのアカウントAzure Storageされます。</span><span class="sxs-lookup"><span data-stu-id="513d0-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="513d0-172">このオプションは、通常、サードパーティの電子情報開示プロバイダーを操作するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="513d0-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="513d0-173">このオプションの使い方の詳細については、「レビュー セット内のドキュメントを別のアカウントにエクスポート[する」をAzure Storageしてください](download-export-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="513d0-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
