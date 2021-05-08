---
title: 手順 1. Syntex SharePointを使用してコントラクト ファイルを識別し、データを抽出する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Syntex を使用して、SharePoint ソリューションを使用してコントラクト ファイルを識別し、データを抽出するMicrosoft 365します。
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281211"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="b591d-104">手順 1.</span><span class="sxs-lookup"><span data-stu-id="b591d-104">Step 1.</span></span> <span data-ttu-id="b591d-105">Syntex SharePointを使用してコントラクト ファイルを識別し、データを抽出する</span><span class="sxs-lookup"><span data-stu-id="b591d-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="b591d-106">組織では、受信した多数のファイルからすべての契約ドキュメントを識別して分類する方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="b591d-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="b591d-107">また、特定された各コントラクト ファイル内のいくつかの重要な要素 (クライアント、契約者、手数料金額など)をすばやく *表示できます*。</span><span class="sxs-lookup"><span data-stu-id="b591d-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="b591d-108">これを行うには[、Syntex](index.md) SharePointを使用してドキュメント理解モデルを作成し、それをドキュメント ライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="b591d-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

<span data-ttu-id="b591d-109">[ドキュメントの理解](document-understanding-overview.md) では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。</span><span class="sxs-lookup"><span data-stu-id="b591d-109">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="b591d-110">ドキュメント理解モデルは、必要な情報がテーブルやフォーム (コントラクトなど) に含まれている必要のない非構造化ドキュメントや半構造化ドキュメントから情報を抽出する場合にも最適です。</span><span class="sxs-lookup"><span data-stu-id="b591d-110">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="b591d-111">最初に、モデルを "トレーニング" して、識別しようとしているコンテンツ タイプ (契約) に固有の特性を検索するために使用できる少なくとも 5 つのサンプル ファイルを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b591d-111">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="b591d-112">Syntex SharePoint使用して、新しいドキュメント理解モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b591d-112">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="b591d-113">サンプル ファイルを使用して、分類子 [を作成する必要があります](create-a-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="b591d-113">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="b591d-114">サンプル ファイルを使用して分類子をトレーニングすると、会社の契約に表示される特性に固有の特性を検索できます。</span><span class="sxs-lookup"><span data-stu-id="b591d-114">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="b591d-115">たとえば、サービス契約、契約条件、報酬など、契約内の特定の文字列を検索する "説明 ["](create-a-classifier.md#create-an-explanation)を作成 *します*。</span><span class="sxs-lookup"><span data-stu-id="b591d-115">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="b591d-116">説明をトレーニングして、ドキュメントの特定のセクションでこれらの文字列を探したり、他の文字列の横に位置したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b591d-116">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="b591d-117">分類子に必要な情報をトレーニングしたと思う場合は、サンプル ファイルのサンプル セットでモデルをテストして、その効率を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b591d-117">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="b591d-118">テスト後、必要に応じて説明を変更して、より効率的に行えます。</span><span class="sxs-lookup"><span data-stu-id="b591d-118">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="b591d-119">モデルでは、抽出プログラム [を作成して](create-an-extractor.md) 、各コントラクトから特定のデータを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="b591d-119">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="b591d-120">たとえば、契約ごとに、最も懸念される情報は、クライアントが誰か、契約者の名前、および総コストです。</span><span class="sxs-lookup"><span data-stu-id="b591d-120">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="b591d-121">モデルを正常に作成したら、そのモデルを[ドキュメント ライブラリSharePoint適用します](apply-a-model.md)。</span><span class="sxs-lookup"><span data-stu-id="b591d-121">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="b591d-122">ドキュメントをドキュメント ライブラリにアップロードすると、ドキュメント理解モデルが実行され、モデルで定義したコントラクト コンテンツ タイプに一致するファイルすべてが識別され、分類されます。</span><span class="sxs-lookup"><span data-stu-id="b591d-122">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="b591d-123">コントラクトとして分類されたファイルはすべて、カスタム ライブラリ ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b591d-123">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="b591d-124">ファイルには、抽出プログラムで定義した各コントラクトの値も表示されます。</span><span class="sxs-lookup"><span data-stu-id="b591d-124">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![ドキュメント ライブラリ内のコントラクト](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="b591d-126">さらに、契約の保持要件がある場合は、モデルを使用して保持ラベルを適用して、指定[](apply-a-retention-label-to-a-model.md)した期間契約が削除されるのを防ぐ方法もあります。</span><span class="sxs-lookup"><span data-stu-id="b591d-126">Additionally, if you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="next-step"></a><span data-ttu-id="b591d-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="b591d-127">Next step</span></span>

[<span data-ttu-id="b591d-128">手順 2.契約Microsoft Teamsチャネルを作成するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="b591d-128">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)