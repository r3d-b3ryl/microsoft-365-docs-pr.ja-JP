---
title: ドキュメントライブラリにドキュメントを適用する (プレビュー)
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
description: SharePoint ドキュメントライブラリに発行されたモデルを適用する方法について説明します。
ms.openlocfilehash: 7e5f3f02c2679769515b27026918a15c901c896e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537616"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="d232b-103">ドキュメントを適用するモデルについて (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d232b-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d232b-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="d232b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d232b-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d232b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="d232b-106">ドキュメントを公開した後、モデルを理解した後、Microsoft 365 テナントの SharePoint ドキュメントライブラリに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d232b-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="d232b-107">アクセスできるドキュメントライブラリに対してのみ、モデルを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d232b-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="d232b-108">モデルをドキュメントライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="d232b-108">Apply your model to a document library.</span></span>

<span data-ttu-id="d232b-109">モデルを SharePoint ドキュメントライブラリに適用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d232b-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="d232b-110">モデルのホームページで、[**ライブラリにモデルを適用**] タイルで、[**モデルの発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d232b-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="d232b-111">または、[**このモデルを使用してライブラリ**内の**ライブラリを追加**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="d232b-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![ライブラリにモデルを追加する](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="d232b-113">その後、モデルを適用するドキュメントライブラリを含む SharePoint サイトを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d232b-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="d232b-114">サイトが一覧に表示されない場合は、検索ボックスを使用して検索します。</span><span class="sxs-lookup"><span data-stu-id="d232b-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![サイトの選択](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="d232b-116">リストのアクセス許可を*管理*するか、モデルを適用するドキュメントライブラリに対する*編集*権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d232b-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="d232b-117">サイトを選択した後、モデルを適用するドキュメントライブラリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d232b-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="d232b-118">この例では、 *Contoso 社のケーストラッキング*サイトから*ドキュメント*ドキュメントライブラリを選択しています。</span><span class="sxs-lookup"><span data-stu-id="d232b-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![ドキュメントライブラリを選択する](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="d232b-120">モデルはコンテンツタイプに関連付けられているため、ライブラリに適用すると、抽出したラベルが列として表示されるコンテンツタイプのビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d232b-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="d232b-121">このビューは既定ではライブラリの既定のビューになりますが、オプションで [**詳細設定**] を選択し、[**この新しいビューを既定として設定**する] を選択解除して、既定のビューにしないように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="d232b-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![ライブラリビュー](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="d232b-123">[**追加**] を選択してモデルをライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="d232b-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="d232b-124">モデルのホームページの [**このモデルを持つライブラリ**] セクションに、SharePoint サイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d232b-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![ライブラリビュー](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="d232b-126">ドキュメントライブラリに移動し、モデルのドキュメントライブラリビューを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d232b-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="d232b-127">ドキュメントライブラリ名の横にある [情報] ボタンを選択すると、モデルがドキュメントライブラリに適用されていることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d232b-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![ライブラリビュー](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="d232b-129">ドキュメントライブラリにモデルを適用した後で、サイトへのドキュメントのアップロードを開始し、結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d232b-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="d232b-130">モデルは、モデルに関連付けられたコンテンツタイプを持つファイルを識別し、ビューにそのファイルをリストします。</span><span class="sxs-lookup"><span data-stu-id="d232b-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="d232b-131">モデルに抽出器がある場合、各ファイルから抽出するデータの列がビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d232b-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="d232b-132">ドキュメントライブラリに既に存在するファイルにモデルを適用する</span><span class="sxs-lookup"><span data-stu-id="d232b-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="d232b-133">適用したモデルでは、適用後にドキュメントライブラリにアップロードされたすべてのファイルが処理されますが、次の操作を実行して、モデルを適用する前にドキュメントライブラリに既に存在していたファイルに対してモデルを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d232b-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="d232b-134">ドキュメントライブラリで、モデルで処理するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d232b-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="d232b-135">ファイルを選択すると、[ドキュメントライブラリ] リボンに**分類と抽出**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d232b-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="d232b-136">[**分類と抽出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d232b-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="d232b-137">選択したファイルが処理されるキューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d232b-137">The files you selected will be added to the queue to be processed.</span></span>

      ![分類と抽出](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="d232b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="d232b-139">See Also</span></span>
[<span data-ttu-id="d232b-140">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="d232b-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="d232b-141">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="d232b-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="d232b-142">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="d232b-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="d232b-143">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="d232b-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




