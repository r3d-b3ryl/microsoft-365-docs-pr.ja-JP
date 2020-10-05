---
title: ドキュメント理解の概要
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint Syntex でのドキュメント理解の概要を説明します。
ms.openlocfilehash: 1265dfa06db323e23d63a044a1a95a6b67c525cf
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333560"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="cdd93-103">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="cdd93-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="cdd93-104">ドキュメント理解では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="cdd93-105">手紙や契約書などの非構造化ドキュメントで最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="cdd93-106">これらのドキュメントには、フレーズやパターンに基づいて識別できるテキストが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd93-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="cdd93-107">識別されたテキストは、ファイルのタイプ (分類) および抽出するもの (抽出プログラム) の両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="cdd93-108">ドキュメント理解シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd93-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="cdd93-109">ドキュメント理解モデルは、*コンテンツ センター*と呼ばれる一種の SharePoint サイトで作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="cdd93-110">SharePoint ドキュメント ライブラリに適用した場合、モデルはコンテンツタイプに関連付けられ、抽出される情報を格納するための列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="cdd93-111">作成したコンテンツタイプは、SharePoint コンテンツタイプ ギャラリーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="cdd93-112">既存のコンテンツ タイプを使用してスキーマを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-112">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="cdd93-113">*分類子*と*抽出子*をドキュメント理解モデルに追加して、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-113">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="cdd93-114">分類子は、ドキュメント ライブラリにアップロードされたドキュメントを識別および分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-114">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="cdd93-115">たとえば、分類子を "トレーニング" して、ライブラリにアップロードされているすべての契約*更新ドキュメント*を識別させることができます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-115">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="cdd93-116">契約更新コンテンツ タイプは、分類子を作成するときにユーザーが定義します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-116">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="cdd93-117">抽出子は、これらのドキュメントから情報を引き出します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-117">Extractors pull information from these documents.</span></span> <span data-ttu-id="cdd93-118">たとえば、ドキュメント ライブラリで識別されたすべての契約更新ドキュメントについて、各契約更新ドキュメントの*サービス開始日*と*クライアント*を示す列がビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-118">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="cdd93-119">サンプルファイルを使用して、モデル内の分類子と抽出子をトレーニングおよびテストできます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-119">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="cdd93-120">サンプルファイルは、ファイルからデータを識別して抽出しようとするときに何を探すべきかについてのモデル例を提供します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-120">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="cdd93-121">たとえば、会社が使用している契約更新ドキュメントの例を使用して、契約更新の分類子と抽出子をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="cdd93-121">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="cdd93-122">サンプルファイルを使用して、モデルの有効性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cdd93-122">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="cdd93-123">モデルを公開したら、コンテンツセンターを使用して、アクセスできる SharePoint ドキュメントライブラリにモデルを適用します。</span><span class="sxs-lookup"><span data-stu-id="cdd93-123">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  



## <a name="see-also"></a><span data-ttu-id="cdd93-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdd93-124">See Also</span></span>
[<span data-ttu-id="cdd93-125">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="cdd93-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="cdd93-126">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="cdd93-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="cdd93-127">コンテンツ センターを作成する</span><span class="sxs-lookup"><span data-stu-id="cdd93-127">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="cdd93-128">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="cdd93-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="cdd93-129">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="cdd93-129">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="cdd93-130">ドキュメント理解とフォーム処理モデルの違い</span><span class="sxs-lookup"><span data-stu-id="cdd93-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="cdd93-131">フォーム処理の概要</span><span class="sxs-lookup"><span data-stu-id="cdd93-131">Form processing overview</span></span>](form-processing-overview.md)
