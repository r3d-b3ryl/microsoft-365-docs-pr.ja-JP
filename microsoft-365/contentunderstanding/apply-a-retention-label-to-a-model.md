---
title: ドキュメントへの保持ラベルの適用モデルについて
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: この記事では、ドキュメントに保持ラベルを適用する方法について説明します。モデルを理解する
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294925"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="8e2ac-103">ドキュメントへの保持ラベルの適用モデルについて</span><span class="sxs-lookup"><span data-stu-id="8e2ac-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="8e2ac-104">[保持ラベル](https://docs.microsoft.com/microsoft-365/compliance/retention)は、Microsoft SharePoint の同期のモデルを理解するドキュメントに簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="8e2ac-105">保持ラベルを使用すると、ドキュメントが識別するドキュメントに保持設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="8e2ac-106">たとえば、ドキュメントライブラリにアップロードされる *保険通知* ドキュメントを特定するだけでなく、指定された期間 (たとえば、次の5か月) にこれらのドキュメントをドキュメントライブラリから削除できないようにするために、モデルに *ビジネス* 保持タグを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="8e2ac-107">既存の保持ラベルをドキュメントに適用するには、モデルのホームページのモデル設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="8e2ac-108">コンテンツについて理解するために保持ラベルを使用できるようにするには、 [Microsoft 365 コンプライアンスセンターで作成および発行](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="8e2ac-109">ドキュメントに保持ラベルを追加するにはモデルを理解する</span><span class="sxs-lookup"><span data-stu-id="8e2ac-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="8e2ac-110">モデルのホームページで、[ **モデルの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="8e2ac-111">[ **モデル設定**] の [ **セキュリティとコンプライアンス** ] セクションで、[ **保持ラベル** ] メニューを選択して、モデルに適用するために使用できる保持ラベルのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="8e2ac-112">![保持ラベルメニュー](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="8e2ac-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="8e2ac-113">モデルに適用する保持ラベルを選択し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="8e2ac-114">保持ラベルをモデルに適用した後、それをモデルに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="8e2ac-115">新しいドキュメントライブラリ</span><span class="sxs-lookup"><span data-stu-id="8e2ac-115">New document library</span></span>
- <span data-ttu-id="8e2ac-116">モデルが既に適用されているドキュメントライブラリ</span><span class="sxs-lookup"><span data-stu-id="8e2ac-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="8e2ac-117">モデルが既に適用されているドキュメントライブラリに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="8e2ac-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="8e2ac-118">ドキュメントがドキュメントライブラリに既に適用されている場合、ドキュメントライブラリに適用するために保持ラベルの更新を同期するには、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="8e2ac-119">モデルのホームページの [ **このモデルを持つライブラリ** ] セクションで、保持ラベルの更新を適用するドキュメントライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="8e2ac-120">[ **同期**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="8e2ac-121">![同期モデル](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="8e2ac-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="8e2ac-122">更新を適用してモデルに同期した後、次の操作を実行して、更新が適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="8e2ac-123">コンテンツセンターの [ **このモデルを持つライブラリ** ] セクションで、更新したモデルが適用されたライブラリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="8e2ac-124">ドキュメントライブラリビューで、[情報] アイコンを選択してモデルプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="8e2ac-125">[ **アクティブなモデル** ] の一覧で、更新したモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="8e2ac-126">[ **保持ラベル** ] セクションに、適用される保持ラベルの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="8e2ac-127">ドキュメントライブラリのモデルの表示ページで、新しい [ **保持ラベル** ] 列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="8e2ac-128">モデルは、そのコンテンツタイプに属すると識別されるファイルを分類し、それらをライブラリビューで一覧表示します。また、[保持ラベル] 列には、モデルによって適用された保持ラベルの名前も表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="8e2ac-129">たとえば、モデルによって識別されるすべての *保険通知* ドキュメントにも、 *ビジネス* 保持ラベルが適用されるため、5か月間ドキュメントライブラリから削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="8e2ac-130">ドキュメントライブラリからファイルを削除しようとすると、適用された保持ラベルが原因で許可されていないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e2ac-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e2ac-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e2ac-131">See Also</span></span>
[<span data-ttu-id="8e2ac-132">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="8e2ac-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="8e2ac-133">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="8e2ac-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="8e2ac-134">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="8e2ac-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="8e2ac-135">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="8e2ac-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
