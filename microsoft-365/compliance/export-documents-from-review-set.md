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
description: プレゼンテーションまたは外部レビューのために、校閲セットからコンテンツを選択してエクスポートする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285363"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="2f79e-103">高度な電子情報開示のレビューセットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="2f79e-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="2f79e-104">[エクスポートすると、ユーザーはダウンロードパッケージに含まれるコンテンツをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="2f79e-105">エクスポートツールでは、次の設定の構成ページが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-105">The Export tool provides a configuration page with the following settings:</span></span>

![レビューセットからアイテムをエクスポートするためのオプション](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="2f79e-107">エクスポート オプション</span><span class="sxs-lookup"><span data-stu-id="2f79e-107">Export options</span></span>

- <span data-ttu-id="2f79e-108">[エクスポート名: エクスポートジョブの名前。</span><span class="sxs-lookup"><span data-stu-id="2f79e-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="2f79e-109">Description: 説明を追加するための自由テキストフィールド。</span><span class="sxs-lookup"><span data-stu-id="2f79e-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="2f79e-110">エクスポートするドキュメント:</span><span class="sxs-lookup"><span data-stu-id="2f79e-110">Export these documents:</span></span>

  - <span data-ttu-id="2f79e-111">[選択したドキュメントのみ-現在選択されているドキュメントのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2f79e-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="2f79e-112">レビューのすべてのドキュメント-レビューセット内のすべてのドキュメントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2f79e-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="2f79e-113">のメタデータ</span><span class="sxs-lookup"><span data-stu-id="2f79e-113">Metadata</span></span>
  
  - <span data-ttu-id="2f79e-114">Load file-このファイルには、各ファイルのメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f79e-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="2f79e-115">含まれるフィールドの詳細については、「 [Advanced 電子情報開示のドキュメントメタデータフィールド](document-metadata-fields-in-Advanced-eDiscovery.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f79e-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="2f79e-116">このファイルは、通常、サードパーティの電子情報開示ツールによって取り込まれたできます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="2f79e-117">Tags-選択されている場合、タグ付け情報はロードファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="2f79e-118">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="2f79e-118">Content</span></span>
  
  - <span data-ttu-id="2f79e-119">ネイティブファイル-ネイティブファイルを含める場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2f79e-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="2f79e-120">会話オプション</span><span class="sxs-lookup"><span data-stu-id="2f79e-120">Conversation options</span></span>
    
    - <span data-ttu-id="2f79e-121">会話ファイル-再構築したチャットメッセージをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2f79e-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="2f79e-122">この形式では、ネイティブアプリケーションでユーザーに表示されるものと同じような形式で会話が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="2f79e-123">個別のチャットメッセージ-Microsoft 365 に格納されているとおりに、元の会話ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2f79e-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="2f79e-124">Options</span><span class="sxs-lookup"><span data-stu-id="2f79e-124">Options</span></span>

  - <span data-ttu-id="2f79e-125">テキストファイル-展開されたテキストバージョンのネイティブファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="2f79e-126">が natives を変換された Pdf に置換する-レビュー中にが PDF ファイルが生成された場合、これらのファイルはエクスポートに使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="2f79e-127">このオプションを選択しないことで、がされていたネイティブファイルのみをエクスポートすることを選択することも、このオプションを選択して、実際の redactions を含む PDF ファイルをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="2f79e-128">出力オプション (エクスポートされたコンテンツは、web ブラウザーを使用して直接ダウンロードすることも、Azure ストレージアカウントに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="2f79e-129">最初の2つのオプションは、直接ダウンロードを有効にします。)</span><span class="sxs-lookup"><span data-stu-id="2f79e-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="2f79e-130">圧縮されていないファイルおよび Pst (可能な場合はメールが Pst に追加されます)-ファイルは、ユーザーがネイティブアプリケーションで表示する元のディレクトリ構造に似た形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="2f79e-131">詳細については、「圧縮されていない [ファイルおよび PST のエクスポート構造](#loose-files-and-pst-export-structure) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f79e-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="2f79e-132">圧縮されたディレクトリ構造-ファイルがエクスポートされ、ダウンロードに含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="2f79e-133">圧縮されたディレクトリ構造を Azure Storage account にエクスポートします。ファイルは、組織の Azure Storage accouunt にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="2f79e-134">ルースファイルおよび PST エクスポート構造</span><span class="sxs-lookup"><span data-stu-id="2f79e-134">Loose files and PST export structure</span></span>

<span data-ttu-id="2f79e-135">このエクスポートオプションを選択した場合、エクスポートされたコンテンツは次の構造で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="2f79e-136">ルートフォルダー–名前付き ExportName.zip のこのフォルダー</span><span class="sxs-lookup"><span data-stu-id="2f79e-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="2f79e-137">Export_load_file.csv メタデータファイル。</span><span class="sxs-lookup"><span data-stu-id="2f79e-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="2f79e-138">Summary.csv-エクスポート統計情報も含む要約ファイル。</span><span class="sxs-lookup"><span data-stu-id="2f79e-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="2f79e-139">Exchange-このフォルダーには、Exchange からのすべてのコンテンツがネイティブファイル形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="2f79e-140">[ **変換した pdf を使用してが Natives を置換** する] オプションを選択した場合、Natives ファイルはが pdf に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="2f79e-141">SharePoint = このフォルダーには、ネイティブファイル形式で SharePoint からのすべてのネイティブコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f79e-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="2f79e-142">[ **変換した pdf を使用してが Natives を置換** する] オプションを選択した場合、Natives ファイルはが pdf に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="2f79e-143">圧縮ディレクトリ構造</span><span class="sxs-lookup"><span data-stu-id="2f79e-143">Condensed directory structure</span></span>

- <span data-ttu-id="2f79e-144">ルートフォルダー-このフォルダーには ExportName.zip という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="2f79e-145">Export_load_file.csv メタデータファイル。</span><span class="sxs-lookup"><span data-stu-id="2f79e-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="2f79e-146">Summary.txt-エクスポート統計情報も含む要約ファイル。</span><span class="sxs-lookup"><span data-stu-id="2f79e-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="2f79e-147">Input_or_native_files-このフォルダーには、エクスポートされたすべてのネイティブファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f79e-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="2f79e-148">が PDF ファイルをエクスポートする場合、それらのファイルは PST ファイルには配置されません。</span><span class="sxs-lookup"><span data-stu-id="2f79e-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="2f79e-149">代わりに、それらのフォルダーは個別のフォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="2f79e-150">Error_files-このフォルダーには、次のエラーファイルが含まれています (エクスポートに含まれている場合)。</span><span class="sxs-lookup"><span data-stu-id="2f79e-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="2f79e-151">ExtractionError。</span><span class="sxs-lookup"><span data-stu-id="2f79e-151">ExtractionError.</span></span> <span data-ttu-id="2f79e-152">親ファイルから正しく抽出されなかったファイルの利用可能なメタデータを含む CSV ファイル。</span><span class="sxs-lookup"><span data-stu-id="2f79e-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="2f79e-153">ProcessingError-このファイルには、処理エラーが発生したドキュメントの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f79e-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="2f79e-154">このコンテンツはアイテムレベルです。つまり、添付ファイルの結果として処理エラーが発生した場合、添付ファイルを含む電子メールメッセージがこのフォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="2f79e-155">Extracted_text_files-このフォルダーには、処理で生成されたすべての抽出済みテキストファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f79e-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="2f79e-156">エクスポートジョブは、ケースの期間中は保持され、そのケースが削除されていない限り、ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2f79e-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
