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
description: プレゼンテーションまたは外部レビュー用のレビュー セットからコンテンツを選択およびエクスポートする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423648"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="3cf0e-103">Advanced eDiscovery のレビュー セットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="3cf0e-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="3cf0e-104">エクスポートを使用すると、ユーザーはダウンロード パッケージに含まれるコンテンツをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="3cf0e-105">エクスポート ツールには、次の設定を含む構成ページがあります。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-105">The Export tool provides a configuration page with the following settings:</span></span>

![レビュー セットからアイテムをエクスポートするためのオプション](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="3cf0e-107">エクスポート オプション</span><span class="sxs-lookup"><span data-stu-id="3cf0e-107">Export options</span></span>

- <span data-ttu-id="3cf0e-108">エクスポート名: エクスポート ジョブの名前。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="3cf0e-109">説明: 説明を追加するフリー テキスト フィールド。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="3cf0e-110">次のドキュメントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-110">Export these documents:</span></span>

  - <span data-ttu-id="3cf0e-111">選択したドキュメントのみ - 現在選択されているドキュメントのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="3cf0e-112">レビュー セット内のすべてのドキュメント - レビュー セット内のすべてのドキュメントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="3cf0e-113">Metadata</span><span class="sxs-lookup"><span data-stu-id="3cf0e-113">Metadata</span></span>
  
  - <span data-ttu-id="3cf0e-114">ファイルの読み込み - このファイルには、各ファイルのメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="3cf0e-115">含まれるフィールドの詳細については、「Advanced [eDiscovery のドキュメント メタデータ フィールド」を参照してください](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="3cf0e-116">このファイルは、通常、サードパーティの電子情報開示ツールによって取り込まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="3cf0e-117">タグ - 選択すると、タグ付け情報が読み込みファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="3cf0e-118">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3cf0e-118">Content</span></span>
  
  - <span data-ttu-id="3cf0e-119">ネイティブ ファイル - ネイティブ ファイルを含める場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="3cf0e-120">会話のオプション</span><span class="sxs-lookup"><span data-stu-id="3cf0e-120">Conversation options</span></span>
    
    - <span data-ttu-id="3cf0e-121">会話ファイル - 再構築されたチャット メッセージをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="3cf0e-122">この形式は、ユーザーがネイティブ アプリケーションで見たものに似た形式の会話を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="3cf0e-123">個々のチャット メッセージ - Microsoft 365 に保存されている元の会話ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="3cf0e-124">オプション</span><span class="sxs-lookup"><span data-stu-id="3cf0e-124">Options</span></span>

  - <span data-ttu-id="3cf0e-125">テキスト ファイル - 抽出されたテキスト バージョンのネイティブ ファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="3cf0e-126">編集されたネイティブを変換された PDF に置き換える - レビュー中に編集された PDF ファイルが生成された場合、これらのファイルはエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="3cf0e-127">(このオプションを選択しない場合) やり直されたネイティブ ファイルのみをエクスポートするか、実際のやり直しを含む PDF ファイルをエクスポートするには、このオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="3cf0e-128">出力オプション (エクスポートされたコンテンツは、Web ブラウザーから直接ダウンロードするか、Azure Storage アカウントに送信できます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="3cf0e-129">最初の 2 つのオプションは、直接ダウンロードを有効にします)。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="3cf0e-130">ルーズ ファイルと PST (電子メールは可能な場合は PST に追加されます) - ファイルは、ネイティブ アプリケーションのユーザーが見た元のディレクトリ構造に似た形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="3cf0e-131">詳細については、「ルーズ ファイルと [PST エクスポート構造」セクションを参照](#loose-files-and-pst-export-structure) してください。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="3cf0e-132">圧縮ディレクトリ構造 - ファイルがエクスポートされ、ダウンロードに含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="3cf0e-133">Azure Storage アカウントにエクスポートされた圧縮ディレクトリ構造 - ファイルは組織の Azure Storage アカウントにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="3cf0e-134">ルーズ ファイルと PST エクスポート構造</span><span class="sxs-lookup"><span data-stu-id="3cf0e-134">Loose files and PST export structure</span></span>

<span data-ttu-id="3cf0e-135">このエクスポート オプションを選択すると、エクスポートされたコンテンツは次の構造で整理されます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="3cf0e-136">ルート フォルダー – 名前付きフォルダー内のこのExportName.zip</span><span class="sxs-lookup"><span data-stu-id="3cf0e-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="3cf0e-137">Export_load_file.csv - メタデータ ファイル。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="3cf0e-138">Summary.csv - エクスポート統計も含むサマリー ファイル。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="3cf0e-139">Exchange - このフォルダーには、Exchange のすべてのコンテンツがネイティブ ファイル形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="3cf0e-140">[変更されたネイティブを変換された PDF に置き換える] オプションを選択した場合、ネイティブ ファイルは編集 **された PDF に置き換** えられる。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="3cf0e-141">SharePoint = このフォルダーには、SharePoint のすべてのネイティブ コンテンツがネイティブ ファイル形式で含まれる。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="3cf0e-142">[変更されたネイティブを変換された PDF に置き換える] オプションを選択した場合、ネイティブ ファイルは編集 **された PDF に置き換** えられる。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="3cf0e-143">ディレクトリ構造の要約</span><span class="sxs-lookup"><span data-stu-id="3cf0e-143">Condensed directory structure</span></span>

- <span data-ttu-id="3cf0e-144">ルート フォルダー - このフォルダーの名前は、ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="3cf0e-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="3cf0e-145">Export_load_file.csv - メタデータ ファイル。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="3cf0e-146">Summary.txt - エクスポート統計も含むサマリー ファイル。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="3cf0e-147">Input_or_native_files - このフォルダーには、エクスポートされたネイティブ ファイルすべてが含まれる。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="3cf0e-148">編集した PDF ファイルをエクスポートした場合、PST ファイルには保存されません。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="3cf0e-149">代わりに、分離されたフォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="3cf0e-150">Error_files - エクスポートに含まれている場合、このフォルダーには次のエラー ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="3cf0e-151">ExtractionError。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-151">ExtractionError.</span></span> <span data-ttu-id="3cf0e-152">親ファイルから適切に抽出されていないファイルの使用可能なメタデータを含む CSV ファイル。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="3cf0e-153">ProcessingError – このファイルには、処理エラーのあるドキュメントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="3cf0e-154">このコンテンツはアイテム レベルです。つまり、添付ファイルが処理エラーの原因である場合、添付ファイルを含む電子メール メッセージがこのフォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="3cf0e-155">Extracted_text_files - このフォルダーには、処理時に生成された抽出されたテキスト ファイルすべてが格納されます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="3cf0e-156">エクスポート ジョブは、ケースの一生保持されます。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="3cf0e-157">ただし、エクスポート ジョブが完了した後、30 日以内にエクスポート ジョブからコンテンツをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf0e-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
