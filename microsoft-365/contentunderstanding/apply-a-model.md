---
title: ドキュメントライブラリに対するドキュメント理解モデルの適用
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: SharePoint ドキュメントライブラリに発行されたモデルを適用する方法について説明します。
ms.openlocfilehash: 8b7d6cf21f422ba54933c2d3ac29b4b34171059e
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322155"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f4f7a-103">Microsoft SharePoint Syntexのドキュメント理解モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="f4f7a-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="f4f7a-104">ドキュメント理解モデルを公開した後、、Microsoft 365 テナントの1つまたは複数の SharePoint ドキュメントライブラリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="f4f7a-105">ユーザーがアクセスできるドキュメントライブラリにのみモデルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="f4f7a-106">モデルをドキュメントライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-106">Apply your model to a document library.</span></span>

<span data-ttu-id="f4f7a-107">モデルをSharePointドキュメントライブラリに適用するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="f4f7a-108">モデルのホームページの [**ライブラリにモデルを適用する** ]タイルの [\*\*モデルの発行 \*\*]を選びます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="f4f7a-109">または、[**このモデルのあるライブラリ**]セクション の [**+ ライブラリの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![ライブラリにモデルを追加する](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="f4f7a-111">モデルを適用するドキュメントライブラリが含まれている SharePoint サイトを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="f4f7a-112">リストにサイトが表示されない場合は、検索ボックスを使用して検索します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![サイトの選択](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="f4f7a-114">モデルを適用しようとしているドキュメントライブラリへの*リスト管理*許可を持っているかまたは、*編集* 権限を持っていなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="f4f7a-115">サイトを選択した後、モデルを適用するドキュメントライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="f4f7a-116">このサンプルでは、*Contoso ケーストラッキング* サイトから*ドキュメント* ドキュメントライブラリ を選びます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![ドキュメントライブラリを選択する](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="f4f7a-118">モデルは、コンテンツタイプに関連付けられているため、ライブラリに適用すると、コンテンツタイプと、列として表示されている抽出したラベルのビューが追加されます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="f4f7a-119">このビューは既定ではライブラリの既定のビューですが、必要に応じて、[**詳細 設定**] を選択し、[**既定のビューとして設定**] 選択解除して、既定のビューから外すことができます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![ライブラリビュー](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="f4f7a-121">モデルをライブラリに適用するには、[ **追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="f4f7a-122">モデルのホームページの [**このモデルのある の ライブラリ**] セクションに、表示されている SharePoint サイトの URL を確認します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![選択したライブラリ](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="f4f7a-124">ドキュメントライブラリに移動し、モデルのドキュメントライブラリビューに移動していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="f4f7a-125">ドキュメントライブラリ名の横にある [情報] ボタンを選択すると、モデルがドキュメントライブラリに適用されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![情報表示](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="f4f7a-127">モデルをドキュメントライブラリに適用したら、サイトにドキュメントをアップロードし、結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="f4f7a-128">モデルは、モデルに関連付けられているすべてのファイルを特定し、ビューに表示します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="f4f7a-129">モデルにエクストラクターがある場合は、各ファイルから抽出したデータの列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="f4f7a-130">ドキュメントライブラリに既に存在するファイルにモデルを適用する</span><span class="sxs-lookup"><span data-stu-id="f4f7a-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="f4f7a-131">適用されたモデルが、ドキュメントライブラリにアップロードされたすべてのファイルを処理している場合は、次の操作を行って、モデルが適用される前に、ドキュメントライブラリ内に既に存在していたファイル上で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="f4f7a-132">ドキュメントライブラリで、モデルで処理するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="f4f7a-133">ファイルを選択すると、 [ドキュメントライブラリ] リボンに**分類および抽出** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="f4f7a-134">**分類および抽出**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="f4f7a-135">選択したファイルが処理されるキューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f4f7a-135">The files you selected will be added to the queue to be processed.</span></span>

      ![分類と抽出](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="f4f7a-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4f7a-137">See Also</span></span>
[<span data-ttu-id="f4f7a-138">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="f4f7a-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="f4f7a-139">エクストラクターを作成する</span><span class="sxs-lookup"><span data-stu-id="f4f7a-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f4f7a-140">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="f4f7a-140">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="f4f7a-141">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="f4f7a-141">Create a form processing model</span></span>](create-a-form-processing-model.md)  
