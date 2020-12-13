---
title: Advanced eDiscovery でプロセス モジュールを実行する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Advanced eDiscovery を使用して分析するデータのケース ファイルを準備するためのガイドラインについて説明します。
ms.openlocfilehash: 3773833d9d0af993b4ccb35bcd18276800c4081f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662812"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="03ca4-103">Advanced eDiscovery (クラシック) でプロセス モジュールを実行する</span><span class="sxs-lookup"><span data-stu-id="03ca4-103">Run the Process module in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="03ca4-104">ケース ファイルは、準備プロセス中に Advanced eDiscovery **に読み込** \> **まれます**。</span><span class="sxs-lookup"><span data-stu-id="03ca4-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="03ca4-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="03ca4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="03ca4-107">ガイドライン: Advanced eDiscovery 用のデータの準備</span><span class="sxs-lookup"><span data-stu-id="03ca4-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="03ca4-108">**品質**: ケースに関連するケース ファイルの母集団を明確に識別します。</span><span class="sxs-lookup"><span data-stu-id="03ca4-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="03ca4-109">**読** み込み: Advanced eDiscovery にアクセスできる場所にファイルを読み込む。</span><span class="sxs-lookup"><span data-stu-id="03ca4-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="03ca4-110">**ファイル ID**: Advanced eDiscovery の一意のファイル識別子。</span><span class="sxs-lookup"><span data-stu-id="03ca4-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="03ca4-111">インポートされたファイル識別子がない場合、Advanced eDiscovery は自動的に ID を生成します。</span><span class="sxs-lookup"><span data-stu-id="03ca4-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="03ca4-112">後続のプロセス読み込みで ID をマップし、最初のプロセスの読み込みとは異なるパスをマップする場合、Advanced eDiscovery はパスを置き換える (新しいファイル エントリを追加する代わりに)。</span><span class="sxs-lookup"><span data-stu-id="03ca4-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="03ca4-113">この ID は、エクスポート プロセスの参照として使用できます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="03ca4-114">ID 値を "-1" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03ca4-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="03ca4-115">**MD5**: この署名は、ファイルを区別するために使用されます (同じ MD5 を持たない限り、2 つのファイルは完全に重複すると見なされません)。</span><span class="sxs-lookup"><span data-stu-id="03ca4-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="03ca4-116">既定では、Advanced eDiscovery はファイルの MD5 を計算します。</span><span class="sxs-lookup"><span data-stu-id="03ca4-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="03ca4-117">読み込まれたファイルがテキスト ファイルの場合は、Advanced eDiscovery で計算するのではなく、元の MD5 値を読み込み、マップしてください。</span><span class="sxs-lookup"><span data-stu-id="03ca4-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="03ca4-118">**ファイルの種類と名前**:</span><span class="sxs-lookup"><span data-stu-id="03ca4-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="03ca4-119">Advanced eDiscovery では、さまざまな形式のファイルを処理し、読み込まれたネイティブ ファイルを標準形式 (次のように) に抽出できます \* 。TXT、HTML、または .XML。</span><span class="sxs-lookup"><span data-stu-id="03ca4-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="03ca4-120">テキスト ファイルの処理は、ネイティブ ファイルよりも高速です。</span><span class="sxs-lookup"><span data-stu-id="03ca4-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="03ca4-121">抽出されたテキスト ファイルは、ケース フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="03ca4-122">抽出できないファイル (システム ファイルやグラフィック イメージなど) は読み込めない。</span><span class="sxs-lookup"><span data-stu-id="03ca4-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="03ca4-123">これらのファイルは処理を遅らせる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03ca4-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="03ca4-124">ファイル名が大幅に名前が付けられているか、パスが正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="03ca4-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="03ca4-125">**ファイル パス**: Advanced eDiscovery は、パスの長さが最大 400 文字のファイルを読み込めます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="03ca4-126">**テキスト** 抽出 : ネイティブ ファイルからテキストを抽出する場合、通常のテキストに加えて、隠しテキスト (Excel および .doc)、非表示列 (Excel)、変更の追跡 (.doc)、スピーカー ノート (.ppt)、埋め込みオブジェクト (.ppt 内の Excel オブジェクトなど) も抽出されます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="03ca4-127">これらはテキスト エディターで表示できます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="03ca4-128">**テキストを無視**: このオプション機能は、プロセスの実行後および分析前に定義されます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="03ca4-129">使用するとファイル分析のパフォーマンスが低下する可能性があります。テキストを無視する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="03ca4-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="03ca4-130">**多言語テキスト**: Advanced eDiscovery は現在、タグ、カストディアン、および問題の多言語名を処理していない。</span><span class="sxs-lookup"><span data-stu-id="03ca4-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="03ca4-131">**メタデータ**: 将来の参照のためにケース データベースに保存するメタデータ (日付範囲、ファイル サイズ、ファイルの種類、保管担当者、件名など) が含まれるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="03ca4-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="03ca4-132">メタデータは、インベントリを再実行したり、再処理のオーバーヘッドを追加したりすることなく、ファイルが既に読み込まれた後に読み込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03ca4-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="03ca4-133">ファイルが最初にパスによって読み込まれた場合は、後でメタデータをインポートするときにパス列をマップします。</span><span class="sxs-lookup"><span data-stu-id="03ca4-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="03ca4-134">ファイルを ID で参照し、別のパスをマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="03ca4-135">これは、ファイル パスが変更される場合に便利なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="03ca4-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="03ca4-136">ファイルが最初にファイル ID によって読み込まれた場合は、メタデータの読み込み時に ID 列をマップします。</span><span class="sxs-lookup"><span data-stu-id="03ca4-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="03ca4-137">(ID ではなく) パスでファイルを参照すると、ファイルは別の ID で再読み込みされます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="03ca4-138">Advanced eDiscovery は、既存のファイルのメタデータを読み込むファイルのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="03ca4-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="03ca4-139">**家族**: 親 (家族の親) なしではファミリを読み込めずに済む。</span><span class="sxs-lookup"><span data-stu-id="03ca4-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="03ca4-140">**ファイル サイズ**: Advanced eDiscovery に読み込まれるファイルのサイズに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="03ca4-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="03ca4-141">分析 (分析、関連性など) の場合、抽出されたテキストの文字数は 5,242,880 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="03ca4-142">大きなファイルは無視されます (たとえば、関連度では、ファイルは関連性トレーニング プロセスに参加し、バッチ計算後に関連性スコアを受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="03ca4-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="03ca4-143">**ファイル数**: 1 つのケースで処理できるファイルの数に対して推奨される制限はありません。</span><span class="sxs-lookup"><span data-stu-id="03ca4-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="03ca4-144">パフォーマンスはシステムのリソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="03ca4-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="03ca4-145">ファイルのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="03ca4-145">Filtering files</span></span>

<span data-ttu-id="03ca4-146">ユーザー定義ラベルを一連のファイルに関連付け、プロセスや他のタスクから除外できます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="03ca4-147">各プロセス セッションは、バッチ ID に関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="03ca4-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="03ca4-148">バッチ ID は、関連性の専門家には表示されませんが、現在のバッチのフィルターを追加し、適切なすべてのファイルにユーザー定義ラベルをタグ付けすることで、検索ユーティリティを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="03ca4-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="03ca4-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="03ca4-149">See also</span></span>

[<span data-ttu-id="03ca4-150">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="03ca4-150">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="03ca4-151">プロセス モジュールの実行とデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="03ca4-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="03ca4-152">プロセス モジュールの結果の表示</span><span class="sxs-lookup"><span data-stu-id="03ca4-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

