---
title: フォーム処理の概要
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint の同期 Tex でのフォーム処理について
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295178"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="ce008-103">フォーム処理の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ce008-103">Form Processing overview (Preview)</span></span>

<span data-ttu-id="ce008-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="ce008-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="ce008-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce008-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="ce008-106">プロジェクト Cortex は、Microsoft PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview) フォーム処理を使用して、SharePoint ドキュメントライブラリ内にモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce008-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="ce008-107">AI ビルダーフォーム処理を使用すると、機械学習技術を使用して、フォームや請求書などの構造化ドキュメントまたは半構造化ドキュメントからキーと値のペアおよびテーブルデータを抽出および抽出する AI モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce008-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="ce008-108">AI ビルダーフォーム処理を使用して、機械学習 (ML) テクノロジを利用して、構造化または半構造化されたドキュメント (フォーム、請求書など) からキーと値のペアおよびテーブルデータを抽出して抽出する AI モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce008-108">Use AI Builder form processing to create AI models that utilize machine learning (ML) technology to identify and extract key-value pairs and table data from structured or semi-structured documents, such as form and invoices.</span></span>

<span data-ttu-id="ce008-109">多くの場合、組織はメール、fax、電子メールなどのさまざまなソースから大量の請求書を受け取ります。これらのドキュメントを処理してデータベースに手動で入力するには、かなりの時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ce008-109">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="ce008-110">AI を使用して、テキスト、キーと値のペア、およびテーブルをドキュメントから抽出することにより、フォーム処理がこのプロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="ce008-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

<span data-ttu-id="ce008-111">たとえば、ドキュメントライブラリにアップロードされたすべての発注書ドキュメントを識別するフォーム処理モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce008-111">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="ce008-112">各発注書から、 *PO 番号*、 *日付*、 *総コスト*など、自分にとって重要な特定のデータを抽出して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ce008-112">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="ce008-113">サンプルファイルを使用してモデルを学習し、フォームから抽出する情報を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce008-113">You can also use sample files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="ce008-114">ドキュメントのレイアウトは、モデルをトレーニングすることによって得られます。</span><span class="sxs-lookup"><span data-stu-id="ce008-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="ce008-115">開始するには、少なくとも5つのフォームドキュメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce008-115">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="ce008-116">AI ビルは、キーと値のペアのサンプルファイルを分析し、検出されなかった可能性があるものを手動で識別します。</span><span class="sxs-lookup"><span data-stu-id="ce008-116">AI building analyzes your sample files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="ce008-117">AI ビルダーを使用すると、サンプルファイルのモデルの精度をテストできます。</span><span class="sxs-lookup"><span data-stu-id="ce008-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="ce008-118">モデルをトレーニングして発行した後、それを使用して、ファイルが SharePoint ドキュメントライブラリにアップロードされた後に実行する [電力自動化フロー](https://docs.microsoft.com/power-automate/getting-started) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ce008-118">After you train and publish your model, use it to create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that runs after a file is uploaded to the SharePoint document library.</span></span> <span data-ttu-id="ce008-119">その後、モデルで識別されたデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="ce008-119">It then extracts data that has been identified in the model.</span></span> <span data-ttu-id="ce008-120">抽出したデータは、モデルのドキュメントライブラリビューの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce008-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="ce008-121">サンプルファイルを使用して、モデルを学習し、フォームから抽出する情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="ce008-121">You use sample files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="ce008-122">ドキュメントのレイアウトは、モデルをトレーニングすることによって得られます。</span><span class="sxs-lookup"><span data-stu-id="ce008-122">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="ce008-123">開始するには5つのフォームドキュメントのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce008-123">You only need five form documents to get started.</span></span> <span data-ttu-id="ce008-124">AI ビルダーは、キーと値のペアのサンプルファイルを分析し、検出されなかった可能性があるものを手動で識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce008-124">AI Builder will analyze your sample files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="ce008-125">AI ビルダーを使用すると、サンプルファイルのモデルの精度をテストできます。</span><span class="sxs-lookup"><span data-stu-id="ce008-125">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="ce008-126">モデルをトレーニングして発行した後、それを使用して [Power オートメーションフロー](https://docs.microsoft.com/power-automate/getting-started)を作成します。</span><span class="sxs-lookup"><span data-stu-id="ce008-126">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="ce008-127">このフローは、ファイルが SharePoint ドキュメントライブラリにアップロードされるときに実行され、モデルで識別されたデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="ce008-127">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="ce008-128">抽出したデータは、モデルのドキュメントライブラリビューの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce008-128">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="ce008-129">Office 365 管理者は、SharePoint ドキュメントライブラリの [フォーム処理を有効](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) にして、ユーザーが [フォーム処理モデルを作成](create-a-form-processing-model.md) できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce008-129">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce008-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce008-130">See Also</span></span>
  
[<span data-ttu-id="ce008-131">電力の自動化に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="ce008-131">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="ce008-132">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="ce008-132">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="ce008-133">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="ce008-133">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="ce008-134">トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="ce008-134">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
