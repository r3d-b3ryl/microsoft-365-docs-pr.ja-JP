---
title: 保持ラベルをドキュメント理解モデルに適用する
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
description: この記事では、保持ラベルをドキュメント理解モデルに適用する方法について説明します
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976557"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="000c1-103">保持ラベルをドキュメント理解モデルに適用する</span><span class="sxs-lookup"><span data-stu-id="000c1-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="000c1-104">Microsoft SharePoint Syntex のドキュメント理解モデルに[保持ラベル](https://docs.microsoft.com/microsoft-365/compliance/retention)を簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="000c1-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="000c1-105">保持ラベルを使用すると、ドキュメント理解モデルが識別するドキュメントに保持設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="000c1-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="000c1-106">たとえば、モデルで、ドキュメント ライブラリにアップロードされた *保険通知* ドキュメントを識別するだけでなく、*ビジネス* 保持タグを適用して、これらのドキュメントを指定された期間 ( たとえば、次の5か月) ドキュメント ライブラリから削除できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="000c1-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="000c1-107">モデルのホームページのモデル設定を使用して、既存の保持ラベルをドキュメント理解モデルに適用できます。</span><span class="sxs-lookup"><span data-stu-id="000c1-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="000c1-108">保持ラベルをコンテンツ理解モデルに適用できるようにするには、保持ラベルを[作成して Microsoft 365 コンプライアンス センターで公開する](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)必要があります。</span><span class="sxs-lookup"><span data-stu-id="000c1-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="000c1-109">保持ラベルをドキュメント理解モデルに追加する</span><span class="sxs-lookup"><span data-stu-id="000c1-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="000c1-110">モデルのホーム ページから、[**モデルの設定**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="000c1-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="000c1-111">[**モデルの設定**] の [**セキュリティとコンプライアンス**] セクションで、[**保持ラベル**] メニューを選択して、モデルに適用できる保持ラベルのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="000c1-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="000c1-112">![保持ラベル メニュー](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="000c1-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="000c1-113">モデルに適用する保持ラベルを選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="000c1-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="000c1-114">モデルに保持ラベルを適用した後、次のものに適用できます。</span><span class="sxs-lookup"><span data-stu-id="000c1-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="000c1-115">新しいドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="000c1-115">New document library</span></span>
- <span data-ttu-id="000c1-116">モデルがすでに適用されているドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="000c1-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="000c1-117">モデルがすでに適用されているドキュメント ライブラリに保持ラベルを適用します</span><span class="sxs-lookup"><span data-stu-id="000c1-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="000c1-118">ドキュメント理解モデルがすでにドキュメント ライブラリに適用されている場合は、次の手順を実行して、保持ラベルの更新を同期し、ドキュメント ライブラリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="000c1-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="000c1-119">モデルホームページの [**このモデルのあるライブラリ**] セクションで、保持ラベルの更新を適用するドキュメントライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="000c1-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="000c1-120">[**同期**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="000c1-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="000c1-121">![同期モデル](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="000c1-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="000c1-122">更新を適用してモデルに同期した後、次の手順を実行して、更新が適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="000c1-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="000c1-123">コンテンツ センターの [**このモデルのあるライブラリ**] セクションで、更新したモデルが適用されたライブラリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="000c1-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="000c1-124">ドキュメント ライブラリ ビューで、情報アイコンを選択してモデルのプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="000c1-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="000c1-125">[**アクティブモデル**] リストで、更新したモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="000c1-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="000c1-126">[**保持ラベル**] セクションに、適用された保持ラベルの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="000c1-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="000c1-127">ドキュメント ライブラリのモデルの表示ページに、新しい **保持ラベル** 列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="000c1-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="000c1-128">モデルがそのコンテンツ タイプに属するものとして識別したファイルを分類し、それらをライブラリ ビューに一覧表示すると、[保持ラベル]列には、モデルを通じてモデルに適用された保持ラベルの名前も表示されます。</span><span class="sxs-lookup"><span data-stu-id="000c1-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="000c1-129">たとえば、モデルが識別するすべての *保険通知* ドキュメントには、*ビジネス* 保持ラベルも適用され、ドキュメント ライブラリから5か月間削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="000c1-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="000c1-130">ドキュメント ライブラリからファイルを削除しようとすると、保持ラベルが適用されているため許可されていないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="000c1-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="000c1-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="000c1-131">See Also</span></span>
[<span data-ttu-id="000c1-132">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="000c1-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="000c1-133">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="000c1-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="000c1-134">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="000c1-134">Document Understanding overview</span></span>](document-understanding-overview.md)


