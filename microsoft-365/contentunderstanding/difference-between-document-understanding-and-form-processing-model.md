---
title: ドキュメントの理解とフォーム処理モデルの相違点 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: ドキュメント理解とフォーム処理モデルの主要な違いについて説明します。
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537435"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="60615-103">ドキュメントの理解とフォーム処理モデルの相違点 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="60615-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="60615-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="60615-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="60615-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60615-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="60615-106">「Project Cortex」では、SharePoint ドキュメントライブラリにアップロードされたドキュメントを識別して分類し、各ファイルから関連情報を抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="60615-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="60615-107">たとえば、ファイルが SharePoint ドキュメントライブラリにアップロードされると、注文*書*として識別されたすべてのファイルは、そのように分類され、表示されるカスタムのドキュメントライブラリビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="60615-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="60615-108">さらに、各ファイル ( *PO 番号*や*合計*など) から特定の情報を取得し、ドキュメントライブラリビューの列に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="60615-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="60615-109">コンテンツを理解することで、必要な情報を特定して抽出するための*モデル*を作成できます。</span><span class="sxs-lookup"><span data-stu-id="60615-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="60615-110">使用できるモデルには、次の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="60615-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="60615-111">ドキュメントのモデルについて</span><span class="sxs-lookup"><span data-stu-id="60615-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="60615-112">フォーム処理モデル</span><span class="sxs-lookup"><span data-stu-id="60615-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="60615-113">両方のモデルは一般的に同じ目的で使用されていますが、どちらを使用するかに影響する主な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="60615-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="60615-114">構造化コンテンツと非構造化コンテンツおよび半構造化されたコンテンツ</span><span class="sxs-lookup"><span data-stu-id="60615-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="60615-115">ドキュメントについてのモデルを使用して、文字や契約書などの非構造化ドキュメントからデータを特定して抽出します。抽出するテキストエンティティは、ドキュメントのセンテンスまたは特定の領域に格納します。</span><span class="sxs-lookup"><span data-stu-id="60615-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="60615-116">たとえば、構造化されていないドキュメントは、さまざまな方法で記述できる契約更新レターの場合があります。</span><span class="sxs-lookup"><span data-stu-id="60615-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="60615-117">ただし、各契約更新文書の本文に一貫した情報があります。たとえば、テキスト文字列「サービスの開始日」の後に実際の日付が続きます。</span><span class="sxs-lookup"><span data-stu-id="60615-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="60615-118">フォーム処理モデルを使用して、ファイルを特定し、構造化または半構造化されたドキュメント (たとえば、*日付: 10/1/2020*) \* またはテーブルデータなど、キーと値のペアが明確であるフォームや請求書からデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="60615-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="60615-119">例として、フォーム処理の候補として、*名前*、*電話番号*、*総コスト*など、ドキュメントレイアウトの同じ領域にある特定のフィールドについて、クライアントが情報を提供する必要がある会社の注文要求フォームが挙げられます。 構造化されたドキュメントの例として、税フォームがあります。</span><span class="sxs-lookup"><span data-stu-id="60615-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="60615-120">作成された場所</span><span class="sxs-lookup"><span data-stu-id="60615-120">Where they are created</span></span>

<span data-ttu-id="60615-121">ドキュメントのモデルについては、SharePoint コンテンツセンターサイトで作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="60615-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="60615-122">ドキュメントを認識するモデルを作成したり、SharePoint ドキュメントライブラリに適用したりするには、コンテンツセンターサイトにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="60615-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="60615-123">ドキュメントを理解するには、SharePoint コンテンツタイプギャラリーに保存される新しい[sharepoint コンテンツタイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)を作成します。</span><span class="sxs-lookup"><span data-stu-id="60615-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="60615-124">必要に応じて、既存のコンテンツタイプを使用してモデルを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="60615-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="60615-125">フォーム処理モデルは PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)で作成されますが、作成は SharePoint ドキュメントライブラリから直接開始されます。</span><span class="sxs-lookup"><span data-stu-id="60615-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="60615-126">ユーザーがフォーム処理モデルを作成できるようにするには、ドキュメントライブラリでフォーム処理モデルの作成が有効になっている必要があります。管理者は、これをコンテンツの管理設定について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60615-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="60615-127">フォーム処理モデルは、PowerAutomate フローを使用して、ファイルをドキュメントライブラリにアップロードするときに処理します。</span><span class="sxs-lookup"><span data-stu-id="60615-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="60615-128">フォーム処理モデルでも、sharepoint コンテンツタイプギャラリーに格納されている新しい[sharepoint コンテンツタイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)を作成します。</span><span class="sxs-lookup"><span data-stu-id="60615-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="60615-129">適用可能な場所</span><span class="sxs-lookup"><span data-stu-id="60615-129">Where they can be applied</span></span>

<span data-ttu-id="60615-130">ドキュメントのモデルについては、アクセスできるさまざまな SharePoint ドキュメントライブラリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="60615-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="60615-131">コンテンツセンターを使用して、ドキュメントを理解するだけでなく、別のドキュメントライブラリに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="60615-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="60615-132">コンテンツセンターでは、コンテンツセンターにロールアップする必要があるので、ドキュメントを理解するモデルをどのように使用し、どのように適用するかについて、より集中管理できます。</span><span class="sxs-lookup"><span data-stu-id="60615-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="60615-133">現在、フォーム処理モデルは、作成元の SharePoint ドキュメントライブラリにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="60615-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="60615-134">これにより、サイトにアクセスできる任意のライセンスユーザーがフォーム処理モデルを作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="60615-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="60615-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="60615-135">See Also</span></span>
[<span data-ttu-id="60615-136">トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="60615-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="60615-137">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="60615-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="60615-138">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="60615-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="60615-139">ドキュメントを適用するモデルを理解する</span><span class="sxs-lookup"><span data-stu-id="60615-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="60615-140">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="60615-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



