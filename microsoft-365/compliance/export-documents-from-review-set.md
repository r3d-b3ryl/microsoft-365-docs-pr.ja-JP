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
description: プレゼンテーションまたは外部レビュー用の高度な電子情報開示レビュー セットからコンテンツを選択してエクスポートする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581027"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="a1eb0-103">Advanced eDiscovery のレビュー セットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a1eb0-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="a1eb0-104">エクスポートを使用すると、Advanced eDiscovery のレビュー セットからドキュメントをエクスポートするときに、ダウンロード パッケージに含まれるコンテンツをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="a1eb0-105">レビュー セットからドキュメントをエクスポートするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="a1eb0-106">Microsoft 365 コンプライアンス センターで、高度な電子情報開示ケースを開き、[レビュー セット] タブを選択し、エクスポートするレビュー セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="a1eb0-107">レビュー セットで、[アクションのエクスポート]**を**  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="a1eb0-108">[エクスポート] ツールは、エクスポートを構成する設定を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="a1eb0-109">一部のオプションは既定で選択されますが、これらを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="a1eb0-110">構成できるエクスポート オプションの説明については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![レビュー セットからアイテムをエクスポートするための構成オプション](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="a1eb0-112">エクスポートを構成した後、[エクスポート] **をクリックして** エクスポート プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="a1eb0-113">[出力オプション] セクションで選択したオプションに応じて、直接ダウンロードするか、組織の Azure Storage アカウントでエクスポート ファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="a1eb0-114">エクスポート ジョブは、ケースの一生保持されます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="a1eb0-115">ただし、エクスポート ジョブが完了した後、30 日以内にエクスポート ジョブからコンテンツをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="a1eb0-116">エクスポート オプション</span><span class="sxs-lookup"><span data-stu-id="a1eb0-116">Export options</span></span>

<span data-ttu-id="a1eb0-117">エクスポートを構成するには、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="a1eb0-118">**エクスポート名**: エクスポート ジョブの名前。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="a1eb0-119">**説明**: 説明を追加するフリー テキスト フィールド。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="a1eb0-120">**これらのドキュメントをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="a1eb0-120">**Export these documents**</span></span>

  - <span data-ttu-id="a1eb0-121">**選択したドキュメントのみ**: このオプションは、現在選択されているドキュメントのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="a1eb0-122">**レビュー セット内のすべてのドキュメント**: このオプションは、レビュー セット内のすべてのドキュメントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="a1eb0-123">**メタデータ**</span><span class="sxs-lookup"><span data-stu-id="a1eb0-123">**Metadata**</span></span>
  
  - <span data-ttu-id="a1eb0-124">**ファイルの読** み込み: このファイルには、各ファイルのメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="a1eb0-125">このファイルは、通常、サードパーティの電子情報開示ツールによって取り込まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="a1eb0-126">含まれるフィールドの詳細については、「Advanced [eDiscovery のドキュメント メタデータ フィールド」を参照してください](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="a1eb0-127">**タグ**: 選択すると、タグ付け情報が読み込みファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="a1eb0-128">**Content**</span><span class="sxs-lookup"><span data-stu-id="a1eb0-128">**Content**</span></span>
  
  - <span data-ttu-id="a1eb0-129">**ネイティブ ファイル**: レビュー セットにドキュメントのネイティブ ファイルを含める場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="a1eb0-130">ネイティブ ファイルのエクスポートを選択した場合は、チャット会話のエクスポート方法に関する次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="a1eb0-131">**会話のオプション**</span><span class="sxs-lookup"><span data-stu-id="a1eb0-131">**Conversation options**</span></span>

    - <span data-ttu-id="a1eb0-132">**会話ファイル**: このオプションは、再構成されたチャット会話をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="a1eb0-133">この形式は、ユーザーがネイティブ アプリケーションで見たものに似た形式の会話を表示します。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="a1eb0-134">**個々のチャット メッセージ**: このオプションは、Microsoft 365 に保存されている元の会話ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="a1eb0-135">**オプション**</span><span class="sxs-lookup"><span data-stu-id="a1eb0-135">**Options**</span></span>

  - <span data-ttu-id="a1eb0-136">**テキスト ファイル**: - このオプションには、抽出されたテキスト バージョンのネイティブ ファイルがエクスポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="a1eb0-137">**編集されたネイティブを変換** された PDF に置き換える : レビュー中に編集された PDF ファイルが生成された場合、これらのファイルはエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="a1eb0-138">(このオプションを選択しない場合) やり直されたネイティブ ファイルのみをエクスポートするか、実際のやり直しを含む PDF ファイルをエクスポートするには、このオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="a1eb0-139">**出力オプション**: エクスポートされたコンテンツは、Web ブラウザーを介して直接ダウンロードするか、Azure Storage アカウントに送信できます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="a1eb0-140">最初の 2 つのオプションは、直接ダウンロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="a1eb0-141">**ルーズ ファイルと PST (** 電子メールは可能な場合は PST に追加されます) : ファイルは、ネイティブ アプリケーションのユーザーが見た元のディレクトリ構造に似た形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="a1eb0-142">詳細については、「ルーズ ファイルと [PST エクスポート構造」セクションを参照](#loose-files-and-pst-export-structure) してください。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="a1eb0-143">**圧縮ディレクトリ構造**: ファイルはエクスポートされ、ダウンロードに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="a1eb0-144">**Azure Storage アカウントにエクスポートされた** 凝縮ディレクトリ構造 : ファイルは組織の Azure Storage アカウントにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="a1eb0-145">このオプションでは、ファイルをエクスポートする Azure Storage アカウントのコンテナーの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="a1eb0-146">また、Azure Storage アカウントの共有アクセス署名 (SAS) トークンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="a1eb0-147">詳細については、「レビュー セット [内のドキュメントを Azure Storage アカウントにエクスポートする」を参照してください](download-export-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="a1eb0-148">次のセクションでは、緩いファイルと圧縮ディレクトリ構造オプションのフォルダー構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="a1eb0-149">ルーズ ファイルと PST エクスポート構造</span><span class="sxs-lookup"><span data-stu-id="a1eb0-149">Loose files and PST export structure</span></span>

<span data-ttu-id="a1eb0-150">このエクスポート オプションを選択すると、エクスポートされたコンテンツは次の構造で整理されます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="a1eb0-151">ルート フォルダー: 名前付きフォルダー内のこのExportName.zip</span><span class="sxs-lookup"><span data-stu-id="a1eb0-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="a1eb0-152">Export_load_file.csv: メタデータ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="a1eb0-153">Summary.csv: エクスポート統計も含むサマリー ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="a1eb0-154">Exchange: このフォルダーには、Exchange のすべてのコンテンツがネイティブ ファイル形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="a1eb0-155">[変更されたネイティブを変換された PDF に置き換える] オプションを選択した場合、ネイティブ ファイルは編集 **された PDF に置き換** えられる。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="a1eb0-156">SharePoint: このフォルダーには、SharePoint のすべてのネイティブ コンテンツがネイティブ ファイル形式で含まれる。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="a1eb0-157">[変更されたネイティブを変換された PDF に置き換える] オプションを選択した場合、ネイティブ ファイルは編集 **された PDF に置き換** えられる。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="a1eb0-158">ディレクトリ構造の要約</span><span class="sxs-lookup"><span data-stu-id="a1eb0-158">Condensed directory structure</span></span>

- <span data-ttu-id="a1eb0-159">ルート フォルダー: このフォルダーの名前は ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="a1eb0-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="a1eb0-160">Export_load_file.csv: メタデータ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="a1eb0-161">Summary.txt: エクスポート統計も含むサマリー ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="a1eb0-162">NativeFiles: このフォルダーには、エクスポートされたネイティブ ファイルすべてが含まれる。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="a1eb0-163">編集した PDF ファイルをエクスポートした場合、PST ファイルには保存されません。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="a1eb0-164">代わりに、分離されたフォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="a1eb0-165">Error_files: エクスポートに含まれている場合、このフォルダーには次のエラー ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="a1eb0-166">ExtractError: 親ファイルから適切に抽出されていないファイルの使用可能なメタデータを含む CSV ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="a1eb0-167">ProcessingError: このファイルには、処理エラーのあるドキュメントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="a1eb0-168">このコンテンツはアイテム レベルです。つまり、添付ファイルが処理エラーの原因である場合、添付ファイルを含む電子メール メッセージがこのフォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="a1eb0-169">Extracted_text_files: このフォルダーには、処理時に生成された抽出されたテキスト ファイルすべてが含まれる。</span><span class="sxs-lookup"><span data-stu-id="a1eb0-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
