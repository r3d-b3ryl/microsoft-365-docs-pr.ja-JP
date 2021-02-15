---
title: ドキュメント理解の概要
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex でのドキュメント理解の概要を説明します。
ms.openlocfilehash: d2bf581468eeee008d09a242876bed5ad07ae01f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242412"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="99995-103">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="99995-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="99995-104">ドキュメント理解では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。</span><span class="sxs-lookup"><span data-stu-id="99995-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="99995-105">手紙や契約書などの非構造化ドキュメントで最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="99995-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="99995-106">これらのドキュメントには、フレーズやパターンに基づいて識別できるテキストが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99995-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="99995-107">識別されたテキストは、ファイルのタイプ (分類) および抽出するもの (抽出プログラム) の両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="99995-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="99995-108">ドキュメント理解シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99995-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="99995-109">ドキュメント理解モデルは、*コンテンツ センター* と呼ばれる一種の SharePoint サイトで作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="99995-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="99995-110">SharePoint ドキュメント ライブラリに適用した場合、モデルはコンテンツタイプに関連付けられ、抽出される情報を格納するための列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99995-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="99995-111">作成したコンテンツタイプは、SharePoint コンテンツタイプ ギャラリーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="99995-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="99995-112">既存のコンテンツ タイプを使用してスキーマを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="99995-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="99995-113">読み取り専用、またはシールされたコンテンツ タイプは更新できないため、モデルに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="99995-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="99995-114">*分類子* と *抽出子* をドキュメント理解モデルに追加して、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="99995-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="99995-115">分類子は、ドキュメント ライブラリにアップロードされたドキュメントを識別および分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="99995-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="99995-116">たとえば、分類子を "トレーニング" して、ライブラリにアップロードされているすべての契約 *更新ドキュメント* を識別させることができます。</span><span class="sxs-lookup"><span data-stu-id="99995-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="99995-117">契約更新コンテンツ タイプは、分類子を作成するときにユーザーが定義します。</span><span class="sxs-lookup"><span data-stu-id="99995-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="99995-118">抽出子は、これらのドキュメントから情報を引き出します。</span><span class="sxs-lookup"><span data-stu-id="99995-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="99995-119">たとえば、ドキュメント ライブラリで識別されたすべての契約更新ドキュメントについて、各契約更新ドキュメントの *サービス開始日* と *クライアント* を示す列がビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="99995-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="99995-120">サンプルファイルを使用して、モデル内の分類子と抽出子をトレーニングおよびテストできます。</span><span class="sxs-lookup"><span data-stu-id="99995-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="99995-121">サンプルファイルは、ファイルからデータを識別して抽出しようとするときに何を探すべきかについてのモデル例を提供します。</span><span class="sxs-lookup"><span data-stu-id="99995-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="99995-122">たとえば、会社が使用している契約更新ドキュメントの例を使用して、契約更新の分類子と抽出子をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="99995-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="99995-123">サンプルファイルを使用して、モデルの有効性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="99995-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="99995-124">モデルを公開したら、コンテンツセンターを使用して、アクセスできる SharePoint ドキュメントライブラリにモデルを適用します。</span><span class="sxs-lookup"><span data-stu-id="99995-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="99995-125">ファイルの制限事項</span><span class="sxs-lookup"><span data-stu-id="99995-125">File limitations</span></span>

<span data-ttu-id="99995-126">ドキュメント理解モデルは、光学式文字認識 (OCR) テクノロジーを使用して、PDF、画像、および TIFF ファイルをスキャンします。これは、サンプル ファイルを使用してモデルをトレーニングする場合と、ドキュメント ライブラリ内のファイルに対してモデルを実行する場合の両方です。</span><span class="sxs-lookup"><span data-stu-id="99995-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="99995-127">Microsoft Office のテキストベース ファイルと OCR スキャン ファイル (PDF、画像、または TIFF) に関して、次の違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="99995-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="99995-128">Office ファイル: 64K 文字を切り捨てます (トレーニング時およびドキュメント ライブラリ内のファイルに対して実行する場合)。</span><span class="sxs-lookup"><span data-stu-id="99995-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="99995-129">OCR スキャン ファイル: 20 ページの制限があります。</span><span class="sxs-lookup"><span data-stu-id="99995-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="99995-130">サポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="99995-130">Supported file types</span></span>

<span data-ttu-id="99995-131">ドキュメント理解モデルでは、次のファイルの種類がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="99995-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="99995-132">doc</span><span class="sxs-lookup"><span data-stu-id="99995-132">doc</span></span>
- <span data-ttu-id="99995-133">docx</span><span class="sxs-lookup"><span data-stu-id="99995-133">docx</span></span>
- <span data-ttu-id="99995-134">eml</span><span class="sxs-lookup"><span data-stu-id="99995-134">eml</span></span>
- <span data-ttu-id="99995-135">heic</span><span class="sxs-lookup"><span data-stu-id="99995-135">heic</span></span>
- <span data-ttu-id="99995-136">heic</span><span class="sxs-lookup"><span data-stu-id="99995-136">heif</span></span>
- <span data-ttu-id="99995-137">htm</span><span class="sxs-lookup"><span data-stu-id="99995-137">htm</span></span>
- <span data-ttu-id="99995-138">html</span><span class="sxs-lookup"><span data-stu-id="99995-138">html</span></span>
- <span data-ttu-id="99995-139">jpeg</span><span class="sxs-lookup"><span data-stu-id="99995-139">jpeg</span></span>
- <span data-ttu-id="99995-140">jpg</span><span class="sxs-lookup"><span data-stu-id="99995-140">jpg</span></span>
- <span data-ttu-id="99995-141">markdown</span><span class="sxs-lookup"><span data-stu-id="99995-141">markdown</span></span>
- <span data-ttu-id="99995-142">md</span><span class="sxs-lookup"><span data-stu-id="99995-142">md</span></span>
- <span data-ttu-id="99995-143">msg</span><span class="sxs-lookup"><span data-stu-id="99995-143">msg</span></span>
- <span data-ttu-id="99995-144">pdf</span><span class="sxs-lookup"><span data-stu-id="99995-144">pdf</span></span>
- <span data-ttu-id="99995-145">png</span><span class="sxs-lookup"><span data-stu-id="99995-145">png</span></span>
- <span data-ttu-id="99995-146">ppt</span><span class="sxs-lookup"><span data-stu-id="99995-146">ppt</span></span>
- <span data-ttu-id="99995-147">pptx</span><span class="sxs-lookup"><span data-stu-id="99995-147">pptx</span></span>
- <span data-ttu-id="99995-148">rtf</span><span class="sxs-lookup"><span data-stu-id="99995-148">rtf</span></span>
- <span data-ttu-id="99995-149">tif</span><span class="sxs-lookup"><span data-stu-id="99995-149">tif</span></span>
- <span data-ttu-id="99995-150">tiff</span><span class="sxs-lookup"><span data-stu-id="99995-150">tiff</span></span>
- <span data-ttu-id="99995-151">txt</span><span class="sxs-lookup"><span data-stu-id="99995-151">txt</span></span>
- <span data-ttu-id="99995-152">xls</span><span class="sxs-lookup"><span data-stu-id="99995-152">xls</span></span>
- <span data-ttu-id="99995-153">xlsx</span><span class="sxs-lookup"><span data-stu-id="99995-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="99995-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="99995-154">See Also</span></span>
[<span data-ttu-id="99995-155">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="99995-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="99995-156">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="99995-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="99995-157">コンテンツ センターを作成する</span><span class="sxs-lookup"><span data-stu-id="99995-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="99995-158">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="99995-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="99995-159">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="99995-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="99995-160">ドキュメント理解とフォーム処理モデルの違い</span><span class="sxs-lookup"><span data-stu-id="99995-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="99995-161">フォーム処理の概要</span><span class="sxs-lookup"><span data-stu-id="99995-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="99995-162">SharePoint Syntex アクセシビリティ モード</span><span class="sxs-lookup"><span data-stu-id="99995-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
