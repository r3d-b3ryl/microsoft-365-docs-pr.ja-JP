---
title: フォーム処理の概要 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: プロジェクト Cortex でのフォーム処理について説明します。
ms.openlocfilehash: dbea06cdf2dbb232a7ea48c78d7ea968dd18b9c0
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612728"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="3335e-103">フォーム処理の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3335e-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="3335e-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="3335e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="3335e-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3335e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="3335e-106">プロジェクト Cortex は、Microsoft PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)フォーム処理を使用して、SharePoint ドキュメントライブラリ内にモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3335e-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="3335e-107">AI ビルダーフォーム処理を使用すると、機械学習技術を使用して、フォームや請求書などの構造化または半構造化されたドキュメントからキーと値のペアやテーブルデータを特定および抽出する AI モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3335e-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="3335e-108">多くの企業では、メール、fax、電子メール、ユーザーなど、さまざまなソースから請求書を受信しています。</span><span class="sxs-lookup"><span data-stu-id="3335e-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="3335e-109">これらのドキュメントを処理してデータベースに手動で入力するには、かなりの時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3335e-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="3335e-110">AI を使用して、ドキュメントからテキスト、キーと値のペア、およびテーブルを抽出することにより、フォーム処理によってこのプロセスが自動化されます。</span><span class="sxs-lookup"><span data-stu-id="3335e-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="3335e-111">たとえば、ドキュメントライブラリにアップロードされたすべての発注書ドキュメントを識別するフォーム処理モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3335e-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="3335e-112">また、各発注書から、 *PO 番号*、*日付*、*総コスト*など、自分にとって重要な特定のデータを抽出して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3335e-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="3335e-113">サンプルファイルを使用して、モデルを学習し、フォームから抽出する情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="3335e-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="3335e-114">ドキュメントのレイアウトは、モデルをトレーニングすることによって得られます。</span><span class="sxs-lookup"><span data-stu-id="3335e-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="3335e-115">開始するには5つのフォームドキュメントのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="3335e-115">You only need five form documents to get started.</span></span> <span data-ttu-id="3335e-116">AI ビルは、キーと値のペアのサンプルファイルを分析し、検出されなかった可能性があるものを手動で識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="3335e-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="3335e-117">AI ビルダーを使用すると、サンプルファイルのモデルの精度をテストできます。</span><span class="sxs-lookup"><span data-stu-id="3335e-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="3335e-118">モデルをトレーニングおよび発行した後、それを使用して、ファイルが SharePoint ドキュメントライブラリにアップロードされたときに実行され、モデルで識別されたデータを抽出する[電力自動化フロー](https://docs.microsoft.com/power-automate/getting-started)を作成します。</span><span class="sxs-lookup"><span data-stu-id="3335e-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="3335e-119">抽出したデータは、モデルのドキュメントライブラリビューの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3335e-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="3335e-120">Office 365 管理者は、SharePoint ドキュメントライブラリの[フォーム処理を有効](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding)にして、ユーザーが[フォーム処理モデルを作成](create-a-form-processing-model.md)できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3335e-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="3335e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3335e-121">See Also</span></span>
  
[<span data-ttu-id="3335e-122">電力の自動化に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="3335e-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="3335e-123">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="3335e-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="3335e-124">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="3335e-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="3335e-125">トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="3335e-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




