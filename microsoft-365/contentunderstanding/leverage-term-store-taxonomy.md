---
title: 抽出器を作成するときに用語ストアの分類を活用する
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: ドキュメントに抽出器を作成するときに用語ストアの分類を活用する Microsoft SharePoint の同期 Tex のモデルを理解する。
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296013"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="d4372-103">抽出器を作成するときに用語ストアの分類を活用する</span><span class="sxs-lookup"><span data-stu-id="d4372-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="d4372-104">ドキュメント内で抽出器を作成する SharePoint の同期について理解すると、 [Managed Metadata service](https://docs.microsoft.com/sharepoint/managed-metadata#terms) の用語ストア分類を活用して、抽出するデータに適した用語を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d4372-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="d4372-105">例として、モデルは、ドキュメントライブラリにアップロードされたすべての **契約** ドキュメントを識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="d4372-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="d4372-106">さらに、このモデルでは、契約 **サービス** の値を各コントラクトから抽出し、ライブラリビューの列に表示します。</span><span class="sxs-lookup"><span data-stu-id="d4372-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="d4372-107">契約のさまざまな契約サービスの値の中には、会社で使用されなくなって名前が変更された古い値がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d4372-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="d4372-108">たとえば、[ *設計*]、[ *グラフィックス*]、または [ *地形* ] の各契約サービスへのすべての参照は、 *クリエイティブ*と呼ばれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d4372-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="d4372-109">モデルでは、契約ドキュメントから古くなった用語のいずれかを抽出するときに、ライブラリビューに現在の用語クリエイティブを表示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4372-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="d4372-110">次の例では、モデルを学習する際に、1つのサンプルドキュメントに、古い *設計*用語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4372-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![用語ストア](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="d4372-112">用語セットのシノニム</span><span class="sxs-lookup"><span data-stu-id="d4372-112">Term set synonyms</span></span> 

<span data-ttu-id="d4372-113">用語セットは、SharePoint 管理センターの Managed Metadata service 用語ストアで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d4372-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="d4372-114">次の例では、 *契約サービス*の [用語セット](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) が、 *クリエイティブ*を含むいくつかの用語を含むように構成されています。</span><span class="sxs-lookup"><span data-stu-id="d4372-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="d4372-115">この用語の詳細には、用語に3つの類義語 (*デザイン*、 *グラフィックス*、および *地形*) があり、類義語を *クリエイティブ*に変換する必要があることが示されています。</span><span class="sxs-lookup"><span data-stu-id="d4372-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![用語セット](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="d4372-117">これを説明する方法がわからない場合は、Mike <してください。</span><span class="sxs-lookup"><span data-stu-id="d4372-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="d4372-118">「Contract Services」列を抽出して表示する抽出器を作成すると、その列はクリエイティブサービスの管理メタデータ用語セットを使用するように "マークされています。" という処理をモデルに指示します。 ></span><span class="sxs-lookup"><span data-stu-id="d4372-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="d4372-119">管理されたメタデータフィールドのドキュメントライブラリサイト列を構成する</span><span class="sxs-lookup"><span data-stu-id="d4372-119">Configure your document library site column for a managed metadata field</span></span>


   ![管理されたメタデータを作成する](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="d4372-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4372-121">See Also</span></span>
[<span data-ttu-id="d4372-122">管理されたメタデータの概要</span><span class="sxs-lookup"><span data-stu-id="d4372-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="d4372-123">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="d4372-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="d4372-124">管理メタデータ列を作成する</span><span class="sxs-lookup"><span data-stu-id="d4372-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





