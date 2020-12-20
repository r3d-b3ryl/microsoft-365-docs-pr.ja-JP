---
title: 抽出子の作成時に用語ストアの分類を活用する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Microsoft SharePoint Syntex のドキュメント理解モデルで抽出子を作成するときに、用語ストアの分類法を活用します。
ms.openlocfilehash: cf396d14a497981389cc336c5efd121f36392181
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709550"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="d96ee-103">抽出子の作成時に用語ストアの分類を活用する</span><span class="sxs-lookup"><span data-stu-id="d96ee-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="d96ee-104">SharePoint Syntex を使用してドキュメント理解モデルで抽出子を作成する場合、[用語ストア](https://docs.microsoft.com/sharepoint/managed-metadata)のグローバル用語セットを利用して、抽出するデータの優先用語を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d96ee-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](https://docs.microsoft.com/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="d96ee-105">例として、モデルは、ドキュメント ライブラリにアップロードされているすべての **契約** ドキュメントを識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="d96ee-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="d96ee-106">さらに、モデルは各契約から **契約サービス** 値も抽出し、ライブラリ ビューの列に表示します。</span><span class="sxs-lookup"><span data-stu-id="d96ee-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="d96ee-107">契約内のさまざまな契約サービス値の中には、会社が使用しなくなって名前が変更された古い値がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d96ee-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="d96ee-108">たとえば、契約サービスでの *Design*、*Graphics*、*Topography* という用語への参照はすべて、*Creative* と呼ばれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96ee-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="d96ee-109">モデルが契約ドキュメントから過去の条件の 1 つを抽出するときは必ず、ライブラリ ビューに現在の条件 (Creative) を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96ee-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="d96ee-110">以下の例では、モデルのトレーニング中に、1 つのサンプル ドキュメントに古い用語である *Design* が含まれていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d96ee-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![用語ストア](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="d96ee-112">抽出子で管理されたメタデータ列を使用する</span><span class="sxs-lookup"><span data-stu-id="d96ee-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="d96ee-113">用語セットは、SharePoint 管理センターの 管理されたメタデータ サービス (MMS) 用語ストアで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d96ee-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="d96ee-114">以下の例では、*契約サービス* の [用語セット](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)は、*Creative* などのいくつかの用語を含むように構成されています。</span><span class="sxs-lookup"><span data-stu-id="d96ee-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="d96ee-115">詳細は、この用語に 3 つの同義語 (*Design*、*Graphics*、*Topography*) があり、これらの同義語を *Creative* に翻訳する必要があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d96ee-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![用語セット](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="d96ee-117">用語セットで同義語を使用する理由はいくつか考えられます。</span><span class="sxs-lookup"><span data-stu-id="d96ee-117">There could be a number of reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="d96ee-118">たとえば、古い用語、名前が変更された用語、または名前付けに関する組織部門間のバリエーションがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d96ee-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="d96ee-119">モデルで抽出子を作成するときに管理メタデータ フィールドを選択できるようにするには、それを[管理メタデータ サイト列として追加する](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96ee-119">To make the managed metadata field available for you to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="d96ee-120">サイト列を追加すると、モデルの抽出子を作成するときに選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d96ee-120">After you add the site column, it will be available for you to select when you create the extractor for your model.</span></span>

   ![契約サービス](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="d96ee-122">モデルをドキュメント ライブラリに適用した後、ドキュメントがライブラリにアップロードされると、抽出子が同義語の値 (*Design*、*Graphics*、*Topography*) のいずれかを検出すると、*Creative Services* 列に優先用語 (*Creative*) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d96ee-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![契約サービス列](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="d96ee-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d96ee-124">See Also</span></span>
[<span data-ttu-id="d96ee-125">管理されたメタデータの概要</span><span class="sxs-lookup"><span data-stu-id="d96ee-125">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="d96ee-126">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="d96ee-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d96ee-127">管理メタデータ列を作成する</span><span class="sxs-lookup"><span data-stu-id="d96ee-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





