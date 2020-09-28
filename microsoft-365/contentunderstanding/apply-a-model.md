---
title: ドキュメントライブラリにドキュメントを適用する
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
description: SharePoint ドキュメントライブラリに発行されたモデルを適用する方法について説明します。
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295492"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="de0ee-103">ドキュメントを適用する Microsoft SharePoint の同期のモデルを理解する</span><span class="sxs-lookup"><span data-stu-id="de0ee-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="de0ee-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="de0ee-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="de0ee-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de0ee-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="de0ee-106">ドキュメントを公開した後、モデルを理解した後、Microsoft 365 テナントの SharePoint ドキュメントライブラリに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="de0ee-107">アクセスできるドキュメントライブラリにのみモデルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="de0ee-108">モデルをドキュメントライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-108">Apply your model to a document library.</span></span>

<span data-ttu-id="de0ee-109">モデルを SharePoint ドキュメントライブラリに適用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="de0ee-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="de0ee-110">モデルのホームページで、[ **ライブラリにモデルを適用** ] タイルの [ **発行モデル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="de0ee-111">または、[**このモデルを使用してライブラリ**内の**ライブラリを追加**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![ライブラリにモデルを追加する](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="de0ee-113">モデルを適用するドキュメントライブラリが含まれている SharePoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="de0ee-114">サイトが一覧に表示されない場合は、検索ボックスを使用して検索します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![サイトの選択](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="de0ee-116">リストのアクセス許可を *管理* するか、モデルを適用するドキュメントライブラリに対する *編集* 権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="de0ee-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="de0ee-117">サイトを選択してから、モデルを適用するドキュメントライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="de0ee-118">サンプルでは、 *Contoso 社のケーストラッキング*サイトから*ドキュメント*ドキュメントライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![ドキュメントライブラリを選択する](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="de0ee-120">モデルはコンテンツタイプに関連付けられているため、ライブラリに適用すると、抽出したラベルが列として表示されるコンテンツタイプのビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="de0ee-121">このビューは既定ではライブラリの既定のビューですが、オプションで **[詳細設定** ] を選択し、[ **この新しいビューを既定として設定**する] をオフにして、既定のビューにしないように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![ライブラリビュー](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="de0ee-123">[ **追加** ] を選択してモデルをライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="de0ee-124">モデルのホームページの [ **このモデルを持つライブラリ** ] セクションに、表示されている SharePoint サイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![選択されたライブラリ](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="de0ee-126">ドキュメントライブラリに移動し、モデルのドキュメントライブラリビューを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="de0ee-127">ドキュメントライブラリ名の横にある [情報] ボタンを選択すると、モデルがドキュメントライブラリに適用されたことを示すメッセージが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="de0ee-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![情報ビュー](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="de0ee-129">ドキュメントライブラリにモデルを適用した後で、サイトへのドキュメントのアップロードを開始し、結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="de0ee-130">モデルは、モデルに関連付けられたコンテンツタイプのすべてのファイルを識別し、ビューにリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="de0ee-131">モデルに抽出器がある場合、ビューには各ファイルから抽出するデータの列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="de0ee-132">ドキュメントライブラリに既に存在するファイルにモデルを適用する</span><span class="sxs-lookup"><span data-stu-id="de0ee-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="de0ee-133">適用されたモデルは、適用された後にドキュメントライブラリにアップロードされたすべてのファイルを処理しますが、次の操作を行って、モデルを適用する前に、ドキュメントライブラリに既に存在するファイルに対してモデルを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="de0ee-134">ドキュメントライブラリで、モデルで処理するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="de0ee-135">ファイルを選択すると、[ドキュメントライブラリ] リボンに **分類と抽出** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="de0ee-136">[ **分類と抽出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de0ee-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="de0ee-137">選択したファイルが処理されるキューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="de0ee-137">The files you selected will be added to the queue to be processed.</span></span>

      ![分類と抽出](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="de0ee-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="de0ee-139">See Also</span></span>
[<span data-ttu-id="de0ee-140">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="de0ee-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="de0ee-141">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="de0ee-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="de0ee-142">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="de0ee-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="de0ee-143">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="de0ee-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
