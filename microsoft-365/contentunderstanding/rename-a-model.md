---
title: Microsoft SharePoint Syntex の文書理解モデルの名前を変更する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex でモデルの名前を変更する方法と理由について説明します。
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446002"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="40546-103">Microsoft SharePoint Syntex の文書理解モデルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="40546-103">Rename a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="40546-104">ある時点で、文書理解モデルの名前を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="40546-104">At some point, you might want to rename a document understanding model.</span></span> <span data-ttu-id="40546-105">一般的な例として、モデルの最初の下書きを作成するときに、最終的な名前について深く考えていない場合があります (たとえば、「AlexWilburModel1」 という名前を付けてしまうかもしれません)。</span><span class="sxs-lookup"><span data-stu-id="40546-105">A common example is when you create an initial draft of a model, you might not have given a lot of thought as to the final name (for example, you might have named it “AlexWilburModel1”).</span></span> <span data-ttu-id="40546-106">モデルの最終処理が近くなり使用の調整に入るると、より適切な名前は「Contract Renewals (契約更新)」であると気付き、名前を変更しようとする場合があります。</span><span class="sxs-lookup"><span data-stu-id="40546-106">As you come closer to finalizing the model and putting it to use, you realize that a more proper name would be “Contract Renewals,” and you want to rename it.</span></span>  

<span data-ttu-id="40546-107">別の例として、プロセスやドキュメントの種類を別の名前で参照するよう決定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="40546-107">Another example is when your organization makes a decision to refer to a process or document type by a different name.</span></span> <span data-ttu-id="40546-108">たとえば、モデルを作成し、それを適用する準備が整うと、すべての「Contract (契約)」が正式に「Agreement (契約)」と呼ばれるよう命じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40546-108">For example, after you create your model and are ready to apply it, your organization might mandate that all “Contracts” will now formally be referred to as “Agreements.”</span></span> <span data-ttu-id="40546-109">必要に応じて、モデルの名前を「Contract Renewals (契約の更新)」 から「Agreement Renewals (契約の更新)」に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="40546-109">If needed, you can choose to rename your model from “Contract Renewals” to “Agreement Renewals.”</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40546-110">ドキュメント ライブラリに適用されていない文書理解モデルの名前のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="40546-110">You can only rename a document understanding model if it has not been applied to a document library.</span></span> 

<span data-ttu-id="40546-111">モデルの名前を変更すると、モデルに関連づけられる[コンテンツ タイプ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)の名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="40546-111">Renaming a model also renames the [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that is associated with the model.</span></span>

## <a name="rename-a-model"></a><span data-ttu-id="40546-112">モデルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="40546-112">Rename a model</span></span>

<span data-ttu-id="40546-113">文書理解モデルの名前を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="40546-113">Follow these steps to rename a document understanding model.</span></span>

1. <span data-ttu-id="40546-114">コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="40546-114">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="40546-115">**モデル** ページで、名前を変更するモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="40546-115">On the **Models** page, select the model you want to rename.</span></span>

3. <span data-ttu-id="40546-116">リボンまたは [**アクションの表示**] ボタン (モデル名の横) を使用して、[**名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40546-116">By using either the ribbon or the **Show actions** button (next to the model name), select **Rename**.</span></span> </br>

    ![[名前の変更] オプションが強調表示された状態で選択されたモデルを示す [モデル] ページのスクリーンショット。](../media/content-understanding/select-model-rename-both.png) </br>

4. <span data-ttu-id="40546-118">[**モデルの名前を変更する**] パネル上で: </span><span class="sxs-lookup"><span data-stu-id="40546-118">On the **Rename model** panel:</span></span>

   <span data-ttu-id="40546-119">a.</span><span class="sxs-lookup"><span data-stu-id="40546-119">a.</span></span> <span data-ttu-id="40546-120">[**新しい名前**]の下に、名前を変更するモデルの新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="40546-120">Under **New name**, enter the new name of the model that you want to rename.</span></span></br>

    ![[名前の変更] パネルを示すスクリーンショット。](../media/content-understanding/rename-model-panel.png) </br>

   <span data-ttu-id="40546-122">b.</span><span class="sxs-lookup"><span data-stu-id="40546-122">b.</span></span> <span data-ttu-id="40546-123">(省略可能)[**詳細設定**] で、既存の[コンテンツ タイプ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)を関連付けるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="40546-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span> <span data-ttu-id="40546-124">[**既存のコンテンツ タイプを使用する**] を選択すると、選択されたコンテンツ タイプに合わせてモデルの名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="40546-124">If you choose **Use an existing content type**, the model will be renamed to match the selected content type.</span></span>

5. <span data-ttu-id="40546-125">[**名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40546-125">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="40546-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="40546-126">See Also</span></span>
[<span data-ttu-id="40546-127">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="40546-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="40546-128">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="40546-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="40546-129">抽出子の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="40546-129">Rename an extractor</span></span>](rename-an-extractor.md)

[<span data-ttu-id="40546-130">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="40546-130">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="40546-131">説明の種類</span><span class="sxs-lookup"><span data-stu-id="40546-131">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="40546-132">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="40546-132">Apply a model</span></span>](apply-a-model.md) 
