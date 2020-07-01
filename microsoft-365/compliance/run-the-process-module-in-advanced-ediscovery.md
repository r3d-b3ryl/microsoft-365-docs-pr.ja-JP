---
title: Advanced eDiscovery で Process モジュールを実行する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 高度な電子情報開示を使用して、分析用のデータのケースファイルを準備するためのガイドラインについて説明します。
ms.openlocfilehash: 5130bea7da8922fd7e98d07696ffde3930d2ce41
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936200"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="388ee-103">Advanced eDiscovery でプロセスモジュールを実行する (クラシック)</span><span class="sxs-lookup"><span data-stu-id="388ee-103">Run the Process module in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="388ee-104">ケースファイルは、**準備**プロセス中に Advanced eDiscovery にロードされ \> **Process**ます。</span><span class="sxs-lookup"><span data-stu-id="388ee-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="388ee-105">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="388ee-105">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="388ee-106">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="388ee-106">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="388ee-107">ガイドライン: 高度な電子情報開示用のデータを準備する</span><span class="sxs-lookup"><span data-stu-id="388ee-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="388ee-108">**品質**: ケースに関連するケースファイルの作成を明確に特定します。</span><span class="sxs-lookup"><span data-stu-id="388ee-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="388ee-109">Load: Advanced eDiscovery にアクセスできる場所にファイルを**読み込みます。**</span><span class="sxs-lookup"><span data-stu-id="388ee-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="388ee-110">**ファイル ID**: Advanced 電子情報開示の一意のファイル識別子。</span><span class="sxs-lookup"><span data-stu-id="388ee-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="388ee-111">ファイル識別子がインポートされていない場合は、アドバンスト eDiscovery によって ID が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="388ee-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="388ee-112">その後のプロセス負荷で ID をマップし、初期プロセス負荷では別のパスをマップした場合、Advanced eDiscovery は (新しいファイルエントリを追加するのではなく) パスを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="388ee-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="388ee-113">この ID は、エクスポートプロセスで参照として使用できます。</span><span class="sxs-lookup"><span data-stu-id="388ee-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="388ee-114">ID 値を "-1" にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="388ee-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="388ee-115">**MD5**: このシグネチャはファイルを区別するために使用されます (2 つのファイルは、同じ MD5 でない限り、完全に重複しているとは見なされません)。</span><span class="sxs-lookup"><span data-stu-id="388ee-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="388ee-116">既定では、Advanced eDiscovery はファイルの MD5 を計算します。</span><span class="sxs-lookup"><span data-stu-id="388ee-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="388ee-117">読み込まれたファイルがテキストファイルの場合は、Advanced eDiscovery で計算するのではなく、元の MD5 値を読み込んでマップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="388ee-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="388ee-118">**ファイルの種類と名前**:</span><span class="sxs-lookup"><span data-stu-id="388ee-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="388ee-119">高度な電子情報開示では、さまざまな形式のファイルを処理し、に読み込まれたネイティブファイルを、などの標準形式で抽出でき \* ます。TXT、HTML、またはです。XML-RPC.</span><span class="sxs-lookup"><span data-stu-id="388ee-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="388ee-120">テキストファイルの処理は、ネイティブファイルよりも高速です。</span><span class="sxs-lookup"><span data-stu-id="388ee-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="388ee-121">抽出したテキストファイルは、case フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="388ee-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="388ee-122">抽出できないファイル (システムファイルやグラフィックスイメージなど) を読み込まないようにします。</span><span class="sxs-lookup"><span data-stu-id="388ee-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="388ee-123">これらのファイルは処理を遅らせている場合があります。</span><span class="sxs-lookup"><span data-stu-id="388ee-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="388ee-124">ファイル名に大きな名前が付けられ、パスが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="388ee-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="388ee-125">**ファイルパス**: 上級電子情報開示では、パスの長さが400文字までのファイルを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="388ee-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="388ee-126">**テキストの抽出**: ネイティブファイルからテキストを抽出する場合、通常のテキストに加えて、隠しテキスト (excel および .doc)、非表示の列 (excel)、変更履歴 (.doc)、発表者のノート (.ppt)、埋め込みオブジェクト (たとえば、.Ppt の Excel オブジェクト) が抽出されます。</span><span class="sxs-lookup"><span data-stu-id="388ee-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="388ee-127">これらはテキストエディターで表示できます。</span><span class="sxs-lookup"><span data-stu-id="388ee-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="388ee-128">**テキストを無視**する: このオプションの機能は、プロセスが実行された後、Analyze が実行される前に定義されます。</span><span class="sxs-lookup"><span data-stu-id="388ee-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="388ee-129">テキストを無視するには、使用するとファイル分析のパフォーマンスが低下する可能性があるため、注意して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="388ee-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="388ee-130">**多言語テキスト**: Advanced eDiscovery は、現在、タグ、保管担当者、および問題の多言語名を処理しません。</span><span class="sxs-lookup"><span data-stu-id="388ee-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="388ee-131">**メタデータ**: 将来の参照のためにケースデータベースに保存するメタデータがあるかどうかを確認します (日付範囲、ファイルサイズ、ファイルの種類、保管担当者、件名など)。</span><span class="sxs-lookup"><span data-stu-id="388ee-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="388ee-132">メタデータは、インベントリを再実行したり、再処理オーバーヘッドを追加したりしなくても、ファイルが既に読み込まれた後でロードできます。</span><span class="sxs-lookup"><span data-stu-id="388ee-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="388ee-133">ファイルが最初にパスで読み込まれていた場合は、後でメタデータをインポートするときに [パス] 列をマップします。</span><span class="sxs-lookup"><span data-stu-id="388ee-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="388ee-134">ID でファイルを参照し、別のパスをマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="388ee-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="388ee-135">これは、ファイルパスが変更された場合に便利なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="388ee-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="388ee-136">ファイルが最初にファイル ID で読み込まれたものである場合は、メタデータの読み込み時に ID 列をマップします。</span><span class="sxs-lookup"><span data-stu-id="388ee-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="388ee-137">(ID ではなく) パスでファイルを参照すると、別の ID でファイルが再度読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="388ee-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="388ee-138">Advanced eDiscovery は、既存のファイルのメタデータを読み込む代わりに、ファイルのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="388ee-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="388ee-139">**ファミリ: 親**を持たないファミリー (ファミリーの head) を読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="388ee-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="388ee-140">**ファイルサイズ**: Advanced eDiscovery に読み込まれるファイルのサイズに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="388ee-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="388ee-141">Analysis (分析、関連性など) では、抽出されたテキストの5242880文字に制限があります。</span><span class="sxs-lookup"><span data-stu-id="388ee-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="388ee-142">大きなファイルは無視されます (たとえば、関連性がある場合、ファイルは関連性トレーニングプロセスに参加せず、バッチ計算後に関連性スコアを受け取ることはありません)。</span><span class="sxs-lookup"><span data-stu-id="388ee-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="388ee-143">**ファイルの数量**: 単一のケースで処理できるファイル数に関して推奨される制限はありません。</span><span class="sxs-lookup"><span data-stu-id="388ee-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="388ee-144">パフォーマンスはシステムのリソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="388ee-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="388ee-145">ファイルのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="388ee-145">Filtering files</span></span>

<span data-ttu-id="388ee-146">ユーザー定義のラベルは、プロセスまたは他のタスクから除外するファイルのセットに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="388ee-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="388ee-147">各プロセスセッションは、バッチ ID に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="388ee-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="388ee-148">関連性の専門家にはバッチ ID が表示されませんが、これは検索ユーティリティを使用して実行できます。これは、現在のバッチのフィルターを追加して、すべての適切なファイルにユーザー定義のラベルを付けることによって行います。</span><span class="sxs-lookup"><span data-stu-id="388ee-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="388ee-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="388ee-149">See also</span></span>

[<span data-ttu-id="388ee-150">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="388ee-150">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="388ee-151">プロセスモジュールの実行とデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="388ee-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="388ee-152">プロセスモジュールの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="388ee-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

