---
title: ドキュメント理解の概要 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex におけるドキュメントの理解の概要について説明します。
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537402"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="80658-103">ドキュメント理解の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="80658-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="80658-104">Project Cortex は現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="80658-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="80658-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80658-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="80658-106">ドキュメントの概要 AI モデルを使用して、ファイルの分類と情報の抽出を自動化します。</span><span class="sxs-lookup"><span data-stu-id="80658-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="80658-107">これは、文字や契約書などの非構造化ドキュメントに最適です。</span><span class="sxs-lookup"><span data-stu-id="80658-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="80658-108">ドキュメントには、語句またはパターンに基づいて識別できるテキストが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80658-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="80658-109">識別されたテキストでは、ファイルの種類 (分類) と抽出するもの (抽出器) の両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="80658-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="80658-110">ドキュメントのモデルについては、コンテンツセンターと呼ばれる種類の SharePoint サイトで作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="80658-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="80658-111">SharePoint ドキュメントライブラリに適用されると、モデルは、抽出された情報を格納する列を持つコンテンツタイプに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="80658-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="80658-112">作成したコンテンツタイプは、SharePoint コンテンツタイプギャラリーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="80658-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="80658-113">スキーマを使用するために、既存のコンテンツタイプを使用するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="80658-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="80658-114">*分類子\*\*と抽出器をドキュメント*に追加するには、次の操作を実行するモデルを理解します。</span><span class="sxs-lookup"><span data-stu-id="80658-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="80658-115">分類子は、ドキュメントライブラリにアップロードされたドキュメントを識別して分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="80658-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="80658-116">たとえば、分類子は、ライブラリにアップロードされたすべての*契約更新*ドキュメントを識別するために、"トレーニング済み" にすることができます。</span><span class="sxs-lookup"><span data-stu-id="80658-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="80658-117">契約更新コンテンツタイプは、分類子を作成するときに定義されます。</span><span class="sxs-lookup"><span data-stu-id="80658-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="80658-118">これらのドキュメントからの抽出情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="80658-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="80658-119">たとえば、ドキュメントライブラリで特定されたすべての契約書更新ドキュメントに対して、列がビューに表示され、各契約更新ドキュメントの*サービス開始日*と*クライアント*も表示されます。</span><span class="sxs-lookup"><span data-stu-id="80658-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="80658-120">サンプルファイルを使用して、モデルで分類子と抽出器をトレーニングおよびテストします。</span><span class="sxs-lookup"><span data-stu-id="80658-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="80658-121">ファイルの例は、ファイルのデータを特定して抽出しようとしたときにどのような意味があるかをモデルの例で示しています。</span><span class="sxs-lookup"><span data-stu-id="80658-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="80658-122">たとえば、会社で作業している契約更新ドキュメントの例を使用して、契約の更新分類子と抽出器をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="80658-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="80658-123">また、サンプルファイルを使用して、モデルの有効性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="80658-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="80658-124">モデルを公開した後、コンテンツセンターを使用して、アクセスできる任意の SharePoint ドキュメントライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="80658-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="80658-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="80658-125">See Also</span></span>
[<span data-ttu-id="80658-126">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="80658-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="80658-127">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="80658-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="80658-128">[コンテンツセンター](create-a-content-center.md) 
 を作成する[フォーム処理モデルを作成する](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="80658-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="80658-129">[モデルを適用する](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="80658-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="80658-130">ドキュメントの理解とフォーム処理モデルの違い</span><span class="sxs-lookup"><span data-stu-id="80658-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="80658-131">フォーム処理の概要</span><span class="sxs-lookup"><span data-stu-id="80658-131">Form processing overview</span></span>](form-processing-overview.md)




