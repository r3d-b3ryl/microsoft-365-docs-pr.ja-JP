---
title: フォーム処理の概要
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
description: Microsoft SharePoint Syntex でのフォーム処理について学ぶ
ms.openlocfilehash: 1dba8828a158a5163017ee5f37735f44e974274c
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515162"
---
# <a name="form-processing-overview"></a><span data-ttu-id="b5ec4-103">フォーム処理の概要</span><span class="sxs-lookup"><span data-stu-id="b5ec4-103">Form processing overview</span></span>

 ![AI ビルダー](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="b5ec4-105">Microsoft SharePoint Syntex は、Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) フォーム処理を使用して、SharePoint ドキュメントライブラリ内にモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="b5ec4-106">AI Builder フォーム処理を使用して、機械学習テクノロジーを使用する AI モデルを作成し、フォームや請求書などの構造化または半構造化文書からキーと値のペアとテーブルデータを識別し、抽出できます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="b5ec4-107">組織は、メール、ファックス、電子メールなどのさまざまなソースから大量の請求書を受け取ることがよくあります。これらの文書を処理してデータベースに手動で入力するには、かなりの時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="b5ec4-108">AI を使用してドキュメントからテキスト、キーと値のペア、およびテーブルを抽出することにより、フォーム処理はこのプロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5ec4-109">フォーム処理シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="b5ec4-110">たとえば、ドキュメント ライブラリにアップロードされたすべての発注書ドキュメントを識別するフォーム処理モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="b5ec4-111">次に、各発注書から、*PO番号*、*日付*、*総コスト* など、重要な特定のデータを抽出して表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![ドキュメント ライブラリ ビュー](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="b5ec4-113">サンプルファイルを使用してモデルをトレーニングし、フォームから抽出する情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="b5ec4-114">文書のレイアウトは、モデルをトレーニングすることで学習されます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="b5ec4-115">開始するのに必要なフォーム ドキュメントは5つだけです。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-115">You only need five form documents to get started.</span></span> <span data-ttu-id="b5ec4-116">AI Builderは、サンプル ファイルを分析してキーと値のペアを探します。また、検出されなかった可能性のあるファイルを手動で特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="b5ec4-117">AI ビルダーを使用すると、サンプルファイルでモデルの精度をテストできます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="b5ec4-118">モデルをトレーニングして公開すると、モデルは [Power Automate フロー](https://docs.microsoft.com/power-automate/getting-started)を作成します。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-118">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="b5ec4-119">フローは、ファイルが SharePoint ドキュメントライブラリにアップロードされたときに実行され、モデルで識別されたデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="b5ec4-120">抽出されたデータは、モデルのドキュメント ライブラリ ビューの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="b5ec4-121">Office 365 管理者 は、ユーザーが SharePoint ドキュメント ライブラリで[フォーム処理モデルを作成](create-a-form-processing-model.md)できるように、SharePoint ドキュメント ライブラリの[フォーム処理を有効にする](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding)必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="b5ec4-122">セットアップ中、またはセットアップ後に管理設定でサイトを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="b5ec4-123">ファイルの制限事項</span><span class="sxs-lookup"><span data-stu-id="b5ec4-123">File limitations</span></span>

<span data-ttu-id="b5ec4-124">フォーム処理モデルを使用する場合は、[ファイルの使用に関する必要条件と制限事項](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-124">When using form processing models, make sure to note the [requirements and limitations for file usage](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="b5ec4-125">Multi-Geo 環境</span><span class="sxs-lookup"><span data-stu-id="b5ec4-125">Multi-Geo environments</span></span>

<span data-ttu-id="b5ec4-126">[Microsoft 365 Multi-Geo 環境](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo)で SharePoint Syntex をセットアップする場合、中央の場所でフォーム処理を使用するように構成することしかできません。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="b5ec4-127">サテライトの場所でフォーム処理を使用する場合は、Microsoft サポートに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="b5ec4-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="b5ec4-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5ec4-128">See Also</span></span>
  
[<span data-ttu-id="b5ec4-129">Power Automate ドキュメント</span><span class="sxs-lookup"><span data-stu-id="b5ec4-129">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="b5ec4-130">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="b5ec4-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="b5ec4-131">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="b5ec4-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="b5ec4-132">トレーニング: AI ビルダーを使用してビジネスの実績を高める</span><span class="sxs-lookup"><span data-stu-id="b5ec4-132">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
