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
description: ''
ms.openlocfilehash: 9a732258e787de3407731f0fdfc98ed07653df71
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074360"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="631d7-102">レビュー セットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="631d7-102">Export documents from a review set</span></span>

<span data-ttu-id="631d7-103">次のいずれかの方法で、プレゼンテーションまたは外部レビューのコンテンツをレビューセットからエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="631d7-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="631d7-104">ドキュメントのダウンロード</span><span class="sxs-lookup"><span data-stu-id="631d7-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="631d7-105">ドキュメントのエクスポート</span><span class="sxs-lookup"><span data-stu-id="631d7-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="631d7-106">校閲セットからドキュメントをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="631d7-106">Download documents from a review set</span></span>

<span data-ttu-id="631d7-107">ダウンロードは、ネイティブ形式のレビューセットからコンテンツをダウンロードする簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="631d7-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="631d7-108">ブラウザーのデータ転送機能を利用して、ダウンロードが完了するとブラウザーのプロンプトが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="631d7-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="631d7-109">このメソッドを使用してダウンロードしたファイルは、コンテナーファイルに圧縮され、アイテムレベルのファイルになります。</span><span class="sxs-lookup"><span data-stu-id="631d7-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="631d7-110">これは、添付ファイルを選択すると、添付ファイルが含まれている電子メールを自動的に受信することを意味します。</span><span class="sxs-lookup"><span data-stu-id="631d7-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="631d7-111">同様に、word 文書に埋め込まれた excel スプレッドシートを選択すると、excel スプレッドシートが埋め込まれた word 文書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="631d7-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="631d7-112">ダウンロードされたアイテムは、ファイルプロパティとして表示できる最終変更日を保持します。</span><span class="sxs-lookup"><span data-stu-id="631d7-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="631d7-113">レビューセットからコンテンツをダウンロードするには、ダウンロードするファイルを選択してから、[操作] メニューの [ダウンロード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="631d7-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![コンピューターの説明のスクリーンショットが自動的に生成される](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="631d7-115">レビュー セットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="631d7-115">Export documents from a review set</span></span>

<span data-ttu-id="631d7-116">[エクスポートすると、ユーザーはダウンロードパッケージに含まれるコンテンツをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="631d7-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="631d7-117">構成ページには、次の設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="631d7-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="631d7-118">メタデータファイル</span><span class="sxs-lookup"><span data-stu-id="631d7-118">Metadata file</span></span>

<span data-ttu-id="631d7-119">これは、エクスポートするファイルに関連付けられたメタデータを含む "load file" と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="631d7-119">This can be considered your "load file" that contains metadata associated with the files you export.</span></span> <span data-ttu-id="631d7-120">メタデータファイルで使用できるエクスポートフィールドの一覧については、「 [Advanced 電子情報開示のドキュメントメタデータフィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="631d7-120">For a list of exported fields available in the metadata file, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="631d7-121">このファイルは、通常、サードパーティ製のツールによって取り込まれたできます。</span><span class="sxs-lookup"><span data-stu-id="631d7-121">This file can typically be ingested by third-party tools.</span></span>

### <a name="tag-data"></a><span data-ttu-id="631d7-122">タグデータ</span><span class="sxs-lookup"><span data-stu-id="631d7-122">Tag data</span></span>

<span data-ttu-id="631d7-123">このコンテンツは、メタデータファイルのフィールドとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="631d7-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="631d7-124">これには、校閲セットに適用されるすべてのタグ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="631d7-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="631d7-125">テキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="631d7-125">Text files</span></span>

<span data-ttu-id="631d7-126">レビューセットからエクスポートされたファイルごとに、テキストファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="631d7-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="631d7-127">これらのファイルは、多くの場合、サービスパートナーが取り込むデータの一部としてサードパーティ製ツールに必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="631d7-127">Often times these files are required by service partners as part of ingesting data into third-party tools.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="631d7-128">がファイル</span><span class="sxs-lookup"><span data-stu-id="631d7-128">Redacted files</span></span>

<span data-ttu-id="631d7-129">レビュー中にが PDF ファイルが生成された場合、これらのファイルはエクスポート中に利用できます。</span><span class="sxs-lookup"><span data-stu-id="631d7-129">If redacted PDF files are generated during review, these files are available during export.</span></span> <span data-ttu-id="631d7-130">ネイティブファイルのみをエクスポートするか、または校正を必要とするネイティブファイルを、実際の redactions を含む PDF ファイルに置き換えるかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="631d7-130">You can decide whether to export native files only or to replace the native files that required redaction with the PDF files that contain the actual redactions.</span></span>

### <a name="export-location"></a><span data-ttu-id="631d7-131">エクスポート場所</span><span class="sxs-lookup"><span data-stu-id="631d7-131">Export location</span></span>

<span data-ttu-id="631d7-132">エクスポートされたコンテンツは、Microsoft が提供する Azure blob またはお客様の blob のいずれかに配信されます。詳細については、export で提供されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="631d7-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="631d7-133">エクスポート構造</span><span class="sxs-lookup"><span data-stu-id="631d7-133">Export structure</span></span>

<span data-ttu-id="631d7-134">コンテンツが校閲セットからエクスポートされると、コンテンツは次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="631d7-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="631d7-135">ルートフォルダー–ダウンロード ID</span><span class="sxs-lookup"><span data-stu-id="631d7-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="631d7-136">Load\_\_ファイル .csv = メタデータファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="631d7-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="631d7-137">Summary.txt = エクスポート統計情報を含む要約ファイル</span><span class="sxs-lookup"><span data-stu-id="631d7-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="631d7-138">入力\_ファイルまた\_はネイティブファイル = すべてのネイティブファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="631d7-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="631d7-139">エラー\_ファイル = エクスポートに含まれているエラーファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="631d7-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="631d7-140">ExtractionError –親ファイルから正しく抽出されなかったファイルの利用可能なメタデータを含む csv。</span><span class="sxs-lookup"><span data-stu-id="631d7-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="631d7-141">ProcessingError-処理エラーがあるコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="631d7-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="631d7-142">このコンテンツはアイテムレベルを意味する。添付ファイルに処理エラーが発生した場合、添付ファイルを含む電子メールはこのフォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="631d7-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="631d7-143">抽出\_さ\_れたテキストファイル = 処理時に生成されたすべての抽出済みテキストファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="631d7-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>
