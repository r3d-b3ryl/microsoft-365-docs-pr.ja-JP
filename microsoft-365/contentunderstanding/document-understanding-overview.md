---
title: ドキュメント理解の概要
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint の同期に関するドキュメントの概要について説明します。
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294762"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="f0841-103">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="f0841-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="f0841-104">ドキュメントの概要は、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。</span><span class="sxs-lookup"><span data-stu-id="f0841-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="f0841-105">これは、文字や契約書などの非構造化ドキュメントに最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="f0841-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="f0841-106">これらのドキュメントには、語句やパターンに基づいて識別できるテキストが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0841-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="f0841-107">識別されたテキストは、そのファイルの種類 (分類) と抽出するもの (抽出器) の両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0841-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="f0841-108">ドキュメントのモデルについては、 *コンテンツセンター*と呼ばれる種類の SharePoint サイトで作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="f0841-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="f0841-109">SharePoint ドキュメントライブラリに適用されると、モデルには、抽出される情報を格納する列があるコンテンツタイプに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="f0841-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="f0841-110">作成したコンテンツタイプは、SharePoint コンテンツタイプギャラリーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f0841-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="f0841-111">既存のコンテンツタイプを使用してスキーマを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0841-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="f0841-112">*分類子*と抽出器をドキュメントに追加する次の操作を実行するモデルについて*説明します*。</span><span class="sxs-lookup"><span data-stu-id="f0841-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="f0841-113">分類子は、ドキュメントライブラリにアップロードされたドキュメントを識別して分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0841-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="f0841-114">たとえば、分類子は、ライブラリにアップロードされたすべての *契約更新* ドキュメントを識別するために、"トレーニング済み" にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0841-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="f0841-115">契約更新コンテンツタイプは、分類子を作成するときに定義されます。</span><span class="sxs-lookup"><span data-stu-id="f0841-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="f0841-116">これらのドキュメントからの抽出情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="f0841-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="f0841-117">たとえば、ドキュメントライブラリで特定されたすべての契約書の更新ドキュメントについては、ビューに列が表示されます。このドキュメントには、 *サービスの開始日* と  *クライアント* も表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0841-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="f0841-118">サンプルファイルを使用すると、モデルで分類子と抽出器をトレーニングし、テストすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0841-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="f0841-119">サンプルファイルには、ファイルのデータを特定して抽出しようとしたときに検索する内容のモデル例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f0841-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="f0841-120">たとえば、会社で作業している契約更新文書のサンプルを使用して、契約の更新分類子と抽出器をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="f0841-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="f0841-121">サンプルファイルを使用して、モデルの有効性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f0841-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="f0841-122">モデルを公開した後、コンテンツセンターを使用して、アクセスできる任意の SharePoint ドキュメントライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="f0841-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="f0841-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0841-123">See Also</span></span>
[<span data-ttu-id="f0841-124">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="f0841-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="f0841-125">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="f0841-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="f0841-126">[コンテンツセンター](create-a-content-center.md) 
 を作成する[フォーム処理モデルを作成する](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="f0841-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="f0841-127">[モデルを適用する](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="f0841-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="f0841-128">ドキュメントの理解とフォーム処理モデルの違い</span><span class="sxs-lookup"><span data-stu-id="f0841-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="f0841-129">フォーム処理の概要</span><span class="sxs-lookup"><span data-stu-id="f0841-129">Form processing overview</span></span>](form-processing-overview.md)
