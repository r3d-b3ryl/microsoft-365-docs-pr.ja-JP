---
title: サンプルモデルを使用したドキュメント理解モデルについて
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
description: サンプルモデルを使用したドキュメント理解モデルについて
ms.openlocfilehash: c27d50df69c2555b1720e3e919f786076ab1e3fb
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296117"
---
# <a name="learn-about-document-understanding-models-through-a-sample-model"></a><span data-ttu-id="19e21-103">サンプルモデルを使用したドキュメントの理解モデルについて</span><span class="sxs-lookup"><span data-stu-id="19e21-103">Learn about document understanding models through a sample model</span></span>

<span data-ttu-id="19e21-104">Microsoft SharePoint の Syntex では、サンプルモデルを使用して、独自のモデルの作成方法をより深く理解することができます。</span><span class="sxs-lookup"><span data-stu-id="19e21-104">Microsoft SharePoint Syntex provides you a with a sample model you can use to examine, giving you a better understanding of how to create your own models.</span></span> <span data-ttu-id="19e21-105">サンプルモデルを使用すると、モデルコンポーネント (分類子、抽出器、説明など) を調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="19e21-105">The sample model also allows you to examine model components, such as its classifier, extractors, and explanations.</span></span> <span data-ttu-id="19e21-106">サンプルファイルを使用してモデルを学習することもできます。</span><span class="sxs-lookup"><span data-stu-id="19e21-106">You can also use the sample files to train the model.</span></span>

## <a name="import-the-sample-model"></a><span data-ttu-id="19e21-107">サンプルモデルをインポートする</span><span class="sxs-lookup"><span data-stu-id="19e21-107">Import the sample model</span></span>

<span data-ttu-id="19e21-108">サンプルモデルにアクセスするには、まず、コンテンツセンターにモデルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e21-108">To access the sample model, you need to first import the model to your content center.</span></span>

1. <span data-ttu-id="19e21-109">コンテンツセンターで、[ **モデル** ] を選択してモデルリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="19e21-109">From the content center, select **Models** to see your models list.</span></span></br>
2. <span data-ttu-id="19e21-110">[ **モデル** ] ページで、[ **サンプルモデルのインポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19e21-110">On the **Models** page, select **Import sample model**.</span></span></br>

    ![サンプルモデルのインポート](../media/content-understanding/import-sample-model.png) </br>

3. <span data-ttu-id="19e21-112">[モデル] リストに表示される *BenefitsChangeNotice* という名前のサンプルモデルを探します。</span><span class="sxs-lookup"><span data-stu-id="19e21-112">Look for the sample model titled *BenefitsChangeNotice.classifier* that appears in your models list.</span></span></br>

    ![サンプルモデル](../media/content-understanding/sample-model.png) </br>

4. <span data-ttu-id="19e21-114">*BenefitsChangeNotice*を選択して、モデルのホームページを開きます。</span><span class="sxs-lookup"><span data-stu-id="19e21-114">Select the *BenefitsChangeNotice.classifier*, to open the model's home page.</span></span></br>
  
     ![サンプルホームページ](../media/content-understanding/sample-home-page.png)

5. <span data-ttu-id="19e21-116">モデルのホームページで、モデルがどのように作成されたかを詳しく調べてください。</span><span class="sxs-lookup"><span data-stu-id="19e21-116">From the model home page, examine the model more closely to see how it was created.</span></span>
 
- <span data-ttu-id="19e21-117">モデルの学習に使用されるサンプルファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="19e21-117">View the sample files used to train the model.</span></span>
- <span data-ttu-id="19e21-118">モデルのエンティティ抽出機能を詳しく調べて、サンプルモデルが説明を構成した方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="19e21-118">Examine the model's entity extractors more closely to see how the sample model configured the explanations.</span></span>

   ![サンプルモデルエクストラクター](../media/content-understanding/entity-extractors.png)  

## <a name="see-also"></a><span data-ttu-id="19e21-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="19e21-120">See Also</span></span>
[<span data-ttu-id="19e21-121">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="19e21-121">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="19e21-122">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="19e21-122">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="19e21-123">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="19e21-123">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="19e21-124">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="19e21-124">Create a form processing model</span></span>](create-a-form-processing-model.md)  
