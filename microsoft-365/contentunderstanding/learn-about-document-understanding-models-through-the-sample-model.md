---
title: サンプル モデルを使用したドキュメント理解モデルについての詳細情報
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
description: サンプル モデルを使用したドキュメント理解モデルについての詳細情報
ms.openlocfilehash: f455e1ec854b4f9a6eea3fa6560ae5390892a640
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976413"
---
# <a name="learn-about-document-understanding-models-through-a-sample-model"></a><span data-ttu-id="a87df-103">サンプル モデルを通じてドキュメント理解モデルについて学ぶ</span><span class="sxs-lookup"><span data-stu-id="a87df-103">Learn about document understanding models through a sample model</span></span>

<span data-ttu-id="a87df-104">Microsoft SharePoint Syntex は、調査に使用できるサンプル モデルを提供し、独自のモデルを作成する方法をよりよく理解できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a87df-104">Microsoft SharePoint Syntex provides you a with a sample model you can use to examine, giving you a better understanding of how to create your own models.</span></span> <span data-ttu-id="a87df-105">サンプルモデルでは、分類子、抽出子、説明などのモデル コンポーネントを調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="a87df-105">The sample model also allows you to examine model components, such as its classifier, extractors, and explanations.</span></span> <span data-ttu-id="a87df-106">サンプル ファイルを使用して、モデルをトレーニングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a87df-106">You can also use the sample files to train the model.</span></span>

## <a name="import-the-sample-model"></a><span data-ttu-id="a87df-107">サンプルモ デルをインポートする</span><span class="sxs-lookup"><span data-stu-id="a87df-107">Import the sample model</span></span>

<span data-ttu-id="a87df-108">サンプルモデルにアクセスするには、最初にモデルをコンテンツ センターにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a87df-108">To access the sample model, you need to first import the model to your content center.</span></span>

1. <span data-ttu-id="a87df-109">コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="a87df-109">From the content center, select **Models** to see your models list.</span></span></br>
2. <span data-ttu-id="a87df-110">[**モデル**]ページで、[**サンプルモデルのインポート**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="a87df-110">On the **Models** page, select **Import sample model**.</span></span></br>

    ![サンプル モデルのインポート](../media/content-understanding/import-sample-model.png) </br>

3. <span data-ttu-id="a87df-112">インポートが完了すると、**BenefitsChangeNotice** モデルのホーム ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="a87df-112">When the import completes, the **BenefitsChangeNotice** model home page will open.</span></span> <span data-ttu-id="a87df-113">今後サンプル モデルを開く必要がある場合は、コンテンツ センターのモデル リストから開くことができます。</span><span class="sxs-lookup"><span data-stu-id="a87df-113">If you need to open the sample model in the future, you can do this from the models list in the content center.</span></span> </br>

     ![サンプル ホーム ページ](../media/content-understanding/sample-home-page.png)</br>

<span data-ttu-id="a87df-115">サンプル モデルを分析してモデルがどのように構築されているかをよりよく理解するだけでなく、作業モデルとしてさらに進んで、次のようなことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a87df-115">You can not only look through analyze the sample model to get a better understanding of how the model is constructed, but as a working model can go further and do things such as:</span></span>

- <span data-ttu-id="a87df-116">別の抽出子を追加します。</span><span class="sxs-lookup"><span data-stu-id="a87df-116">Add a another extractor.</span></span> <span data-ttu-id="a87df-117">たとえば、*割引料金* を抽出するものを追加します。</span><span class="sxs-lookup"><span data-stu-id="a87df-117">For example, add one that extracts the *discount fee*.</span></span>
- <span data-ttu-id="a87df-118">モデルをドキュメント ライブラリに適用し、トレーニング ファイルの一部をアップロードして、モデルがファイルを分類し、ファイルからデータを抽出する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="a87df-118">Apply the model to a document library, and upload some of the training files to it to see how the model classifies files and extracts data from them.</span></span>


## <a name="see-also"></a><span data-ttu-id="a87df-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a87df-119">See Also</span></span>
[<span data-ttu-id="a87df-120">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="a87df-120">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a87df-121">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="a87df-121">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a87df-122">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="a87df-122">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="a87df-123">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="a87df-123">Create a form processing model</span></span>](create-a-form-processing-model.md)  
