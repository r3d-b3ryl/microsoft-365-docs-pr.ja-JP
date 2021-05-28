---
title: ドキュメント理解の概要
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex でのドキュメント理解の概要を説明します。
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683825"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="7b152-103">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="7b152-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="7b152-104">ドキュメント理解では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。</span><span class="sxs-lookup"><span data-stu-id="7b152-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="7b152-105">手紙や契約書などの非構造化ドキュメントで最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="7b152-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="7b152-106">これらのドキュメントには、フレーズやパターンに基づいて識別できるテキストが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="7b152-107">識別されたテキストは、ファイルのタイプ (分類) および抽出するもの (抽出プログラム) の両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b152-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="7b152-108">ドキュメント理解シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](./adoption-getstarted.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b152-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="7b152-109">ドキュメント理解モデルは、*コンテンツ センター* と呼ばれる一種の SharePoint サイトで作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="7b152-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="7b152-110">SharePoint ドキュメント ライブラリに適用した場合、モデルはコンテンツタイプに関連付けられ、抽出される情報を格納するための列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b152-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="7b152-111">作成したコンテンツタイプは、SharePoint コンテンツタイプ ギャラリーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="7b152-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="7b152-112">既存のコンテンツ タイプを使用してスキーマを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b152-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="7b152-113">読み取り専用、またはシールされたコンテンツ タイプは更新できないため、モデルに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b152-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="7b152-114">*分類子* と *抽出子* をドキュメント理解モデルに追加して、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="7b152-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="7b152-115">分類子は、ドキュメント ライブラリにアップロードされたドキュメントを識別および分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b152-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="7b152-116">たとえば、分類子を "トレーニング" して、ライブラリにアップロードされているすべての契約 *更新ドキュメント* を識別させることができます。</span><span class="sxs-lookup"><span data-stu-id="7b152-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="7b152-117">契約更新コンテンツ タイプは、分類子を作成するときにユーザーが定義します。</span><span class="sxs-lookup"><span data-stu-id="7b152-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="7b152-118">抽出子は、これらのドキュメントから情報を引き出します。</span><span class="sxs-lookup"><span data-stu-id="7b152-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="7b152-119">たとえば、ドキュメント ライブラリで識別されたすべての契約更新ドキュメントについて、各契約更新ドキュメントの *サービス開始日* と *クライアント* を示す列がビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b152-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="7b152-120">サンプルファイルを使用して、モデル内の分類子と抽出子をトレーニングおよびテストできます。</span><span class="sxs-lookup"><span data-stu-id="7b152-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="7b152-121">サンプルファイルは、ファイルからデータを識別して抽出しようとするときに何を探すべきかについてのモデル例を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b152-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="7b152-122">たとえば、会社が使用している契約更新ドキュメントの例を使用して、契約更新の分類子と抽出子をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="7b152-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="7b152-123">サンプルファイルを使用して、モデルの有効性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b152-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="7b152-124">モデルを公開したら、コンテンツセンターを使用して、アクセスできる SharePoint ドキュメントライブラリにモデルを適用します。</span><span class="sxs-lookup"><span data-stu-id="7b152-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="7b152-125">ファイルの制限事項</span><span class="sxs-lookup"><span data-stu-id="7b152-125">File limitations</span></span>

<span data-ttu-id="7b152-126">ドキュメント理解モデルは、光学式文字認識 (OCR) テクノロジーを使用して、PDF、画像、および TIFF ファイルをスキャンします。これは、サンプル ファイルを使用してモデルをトレーニングする場合と、ドキュメント ライブラリ内のファイルに対してモデルを実行する場合の両方です。</span><span class="sxs-lookup"><span data-stu-id="7b152-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="7b152-127">Microsoft Office のテキストベース ファイルと OCR スキャン ファイル (PDF、画像、または TIFF) に関して、次の違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7b152-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="7b152-128">Office ファイル: 64,000 文字を切り捨てます (トレーニング時およびドキュメント ライブラリ内のファイルに対して実行する場合)。</span><span class="sxs-lookup"><span data-stu-id="7b152-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="7b152-129">OCR スキャン ファイル: 20 ページの制限があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="7b152-130">要件</span><span class="sxs-lookup"><span data-stu-id="7b152-130">Requirements</span></span>

<span data-ttu-id="7b152-131">OCR 処理は、次の要件を満たすドキュメントで最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="7b152-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="7b152-132">JPG、PNG、または PDF 形式 (テキストまたはスキャン)。</span><span class="sxs-lookup"><span data-stu-id="7b152-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="7b152-133">文字の抽出と場所にエラーが発生しないため、テキストが埋め込まれた PDF の方が優れています。</span><span class="sxs-lookup"><span data-stu-id="7b152-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="7b152-134">PDF がパスワードでロックされている場合は、送信する前にロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="7b152-135">コレクションごとのトレーニングに使用されるドキュメントの合計ファイル サイズは 50 MB を超えてはならず、PDF ドキュメントは 500 ページを超えてはなりません。</span><span class="sxs-lookup"><span data-stu-id="7b152-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="7b152-136">画像の場合、サイズは 50×50 ピクセルと 10,000×10,000 ピクセルの間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="7b152-137">非常に幅が広い画像やサイズが奇数の画像 (平面図など) は、OCR プロセスで切り捨てられ、精度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="7b152-138">PDF ファイルの場合、サイズは最大 17 x 17 インチで、リーガルまたは A3 の用紙サイズ以下に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="7b152-139">紙の文書からスキャンする場合、スキャンは高品質の画像である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="7b152-140">ラテン アルファベット (英語の文字) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b152-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="7b152-141">AI ビルダーは現在、次の種類のフォーム処理入力データをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7b152-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="7b152-142">- チェック ボックスまたはラジオ ボタン</span><span class="sxs-lookup"><span data-stu-id="7b152-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="7b152-143">- 署名</span><span class="sxs-lookup"><span data-stu-id="7b152-143">- Signatures</span></span><br><span data-ttu-id="7b152-144">- 入力可能な PDF</span><span class="sxs-lookup"><span data-stu-id="7b152-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="7b152-145">サポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="7b152-145">Supported file types</span></span>

<span data-ttu-id="7b152-146">ドキュメント理解モデルでは、次のファイルの種類がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7b152-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="7b152-147">doc</span><span class="sxs-lookup"><span data-stu-id="7b152-147">doc</span></span>
- <span data-ttu-id="7b152-148">docx</span><span class="sxs-lookup"><span data-stu-id="7b152-148">docx</span></span>
- <span data-ttu-id="7b152-149">eml</span><span class="sxs-lookup"><span data-stu-id="7b152-149">eml</span></span>
- <span data-ttu-id="7b152-150">heic</span><span class="sxs-lookup"><span data-stu-id="7b152-150">heic</span></span>
- <span data-ttu-id="7b152-151">heic</span><span class="sxs-lookup"><span data-stu-id="7b152-151">heif</span></span>
- <span data-ttu-id="7b152-152">htm</span><span class="sxs-lookup"><span data-stu-id="7b152-152">htm</span></span>
- <span data-ttu-id="7b152-153">html</span><span class="sxs-lookup"><span data-stu-id="7b152-153">html</span></span>
- <span data-ttu-id="7b152-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="7b152-154">jpeg</span></span>
- <span data-ttu-id="7b152-155">jpg</span><span class="sxs-lookup"><span data-stu-id="7b152-155">jpg</span></span>
- <span data-ttu-id="7b152-156">markdown</span><span class="sxs-lookup"><span data-stu-id="7b152-156">markdown</span></span>
- <span data-ttu-id="7b152-157">md</span><span class="sxs-lookup"><span data-stu-id="7b152-157">md</span></span>
- <span data-ttu-id="7b152-158">msg</span><span class="sxs-lookup"><span data-stu-id="7b152-158">msg</span></span>
- <span data-ttu-id="7b152-159">pdf</span><span class="sxs-lookup"><span data-stu-id="7b152-159">pdf</span></span>
- <span data-ttu-id="7b152-160">png</span><span class="sxs-lookup"><span data-stu-id="7b152-160">png</span></span>
- <span data-ttu-id="7b152-161">ppt</span><span class="sxs-lookup"><span data-stu-id="7b152-161">ppt</span></span>
- <span data-ttu-id="7b152-162">pptx</span><span class="sxs-lookup"><span data-stu-id="7b152-162">pptx</span></span>
- <span data-ttu-id="7b152-163">rtf</span><span class="sxs-lookup"><span data-stu-id="7b152-163">rtf</span></span>
- <span data-ttu-id="7b152-164">tif</span><span class="sxs-lookup"><span data-stu-id="7b152-164">tif</span></span>
- <span data-ttu-id="7b152-165">tiff</span><span class="sxs-lookup"><span data-stu-id="7b152-165">tiff</span></span>
- <span data-ttu-id="7b152-166">txt</span><span class="sxs-lookup"><span data-stu-id="7b152-166">txt</span></span>
- <span data-ttu-id="7b152-167">xls</span><span class="sxs-lookup"><span data-stu-id="7b152-167">xls</span></span>
- <span data-ttu-id="7b152-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="7b152-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="7b152-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b152-169">See Also</span></span>
[<span data-ttu-id="7b152-170">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="7b152-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="7b152-171">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="7b152-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="7b152-172">コンテンツ センターを作成する</span><span class="sxs-lookup"><span data-stu-id="7b152-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="7b152-173">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="7b152-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="7b152-174">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="7b152-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="7b152-175">ドキュメント理解とフォーム処理モデルの違い</span><span class="sxs-lookup"><span data-stu-id="7b152-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="7b152-176">フォーム処理の概要</span><span class="sxs-lookup"><span data-stu-id="7b152-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="7b152-177">SharePoint Syntex アクセシビリティ モード</span><span class="sxs-lookup"><span data-stu-id="7b152-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)