---
title: フォーム処理の概要
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint Syntex でのフォーム処理について学ぶ
ms.openlocfilehash: 9b5b9b1c54220037e1c10f2722a641b526592f84
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338615"
---
# <a name="form-processing-overview"></a><span data-ttu-id="560e5-103">フォーム処理の概要</span><span class="sxs-lookup"><span data-stu-id="560e5-103">Form processing overview</span></span>

 ![AI ビルダー](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="560e5-105">Microsoft SharePoint Syntex は、Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) フォーム処理を使用して、SharePoint ドキュメントライブラリ内にモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="560e5-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="560e5-106">AI Builder フォーム処理を使用して、機械学習テクノロジーを使用する AI モデルを作成し、フォームや請求書などの構造化または半構造化文書からキーと値のペアとテーブルデータを識別し、抽出できます。</span><span class="sxs-lookup"><span data-stu-id="560e5-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="560e5-107">組織は、メール、ファックス、電子メールなどのさまざまなソースから大量の請求書を受け取ることがよくあります。これらの文書を処理してデータベースに手動で入力するには、かなりの時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="560e5-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="560e5-108">AI を使用してドキュメントからテキスト、キーと値のペア、およびテーブルを抽出することにより、フォーム処理はこのプロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="560e5-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="560e5-109">フォーム処理シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="560e5-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="560e5-110">たとえば、ドキュメント ライブラリにアップロードされたすべての発注書ドキュメントを識別するフォーム処理モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="560e5-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="560e5-111">次に、各発注書から、*PO番号*、*日付*、*総コスト*など、重要な特定のデータを抽出して表示できます。</span><span class="sxs-lookup"><span data-stu-id="560e5-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![ドキュメント ライブラリ ビュー](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="560e5-113">サンプルファイルを使用してモデルをトレーニングし、フォームから抽出する情報を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="560e5-113">You can also use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="560e5-114">ドキュメントのレイアウトは、モデルをトレーニングすることで学習されます。また、フォーム内の同様の場所からデータを抽出することも学習します。これは、ドキュメントのレイアウトが類似しているためです。</span><span class="sxs-lookup"><span data-stu-id="560e5-114">The layout of your document is learned by training your model, and it learns to extract your data from similar locations in your forms since they have a similar structured layout.</span></span> 

<span data-ttu-id="560e5-115">開始するには、少なくとも5つのフォームドキュメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="560e5-115">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="560e5-116">AI ビルディングは、サンプルファイルでキーと値のペアを分析し、検出されなかった可能性のあるファイルを手動で識別します。</span><span class="sxs-lookup"><span data-stu-id="560e5-116">AI building analyzes your example files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="560e5-117">AI ビルダーを使用すると、サンプルファイルでモデルの精度をテストできます。</span><span class="sxs-lookup"><span data-stu-id="560e5-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="560e5-118">モデルをトレーニングして公開したら、それを使用して、ファイルが SharePoint ドキュメントライブラリにアップロードされた後に実行される [Power Automate フロー](https://docs.microsoft.com/power-automate/getting-started)を作成します。</span><span class="sxs-lookup"><span data-stu-id="560e5-118">After you train and publish your model, use it to create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that runs after a file is uploaded to the SharePoint document library.</span></span> <span data-ttu-id="560e5-119">次に、モデルで識別されたデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="560e5-119">It then extracts data that has been identified in the model.</span></span> <span data-ttu-id="560e5-120">抽出されたデータは、モデルのドキュメント ライブラリ ビューの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="560e5-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="560e5-121">サンプルファイルを使用してモデルをトレーニングし、フォームから抽出する情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="560e5-121">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="560e5-122">文書のレイアウトは、モデルをトレーニングすることで学習されます。</span><span class="sxs-lookup"><span data-stu-id="560e5-122">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="560e5-123">開始するのに必要なフォーム ドキュメントは5つだけです。</span><span class="sxs-lookup"><span data-stu-id="560e5-123">You only need five form documents to get started.</span></span> <span data-ttu-id="560e5-124">AI Builderは、サンプル ファイルを分析してキーと値のペアを探します。また、検出されなかった可能性のあるファイルを手動で特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="560e5-124">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="560e5-125">AI ビルダーを使用すると、サンプルファイルでモデルの精度をテストできます。</span><span class="sxs-lookup"><span data-stu-id="560e5-125">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="560e5-126">モデルをトレーニングして公開すると、モデルは [Power Automate フロー](https://docs.microsoft.com/power-automate/getting-started)を作成します。</span><span class="sxs-lookup"><span data-stu-id="560e5-126">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="560e5-127">フローは、ファイルが SharePoint ドキュメントライブラリにアップロードされたときに実行され、モデルで識別されたデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="560e5-127">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="560e5-128">抽出されたデータは、モデルのドキュメント ライブラリ ビューの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="560e5-128">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="560e5-129">Office 365 管理者 は、ユーザーが SharePoint ドキュメント ライブラリで[フォーム処理モデルを作成](create-a-form-processing-model.md)できるように、SharePoint ドキュメント ライブラリの[フォーム処理を有効にする](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding)必要があります。</span><span class="sxs-lookup"><span data-stu-id="560e5-129">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="560e5-130">セットアップ中、またはセットアップ後に管理設定でサイトを選択できます。</span><span class="sxs-lookup"><span data-stu-id="560e5-130">You can select the sites during setup, or after setup in your management settings.</span></span>



## <a name="see-also"></a><span data-ttu-id="560e5-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="560e5-131">See Also</span></span>
  
[<span data-ttu-id="560e5-132">Power Automate ドキュメント</span><span class="sxs-lookup"><span data-stu-id="560e5-132">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="560e5-133">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="560e5-133">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="560e5-134">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="560e5-134">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="560e5-135">トレーニング: AI ビルダーを使用してビジネスの実績を高める</span><span class="sxs-lookup"><span data-stu-id="560e5-135">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
