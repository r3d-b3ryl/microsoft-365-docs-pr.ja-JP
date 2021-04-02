---
title: Microsoft SharePoint Syntex でモデルを複製する
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
description: Microsoft SharePoint Syntex でモデルを複製する方法と理由について説明します。
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446038"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="6b70d-103">Microsoft SharePoint Syntex でモデルを複製する</span><span class="sxs-lookup"><span data-stu-id="6b70d-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="6b70d-104">文書理解モデルを複製すると、新しいモデルを作成する必要がある場合に時間や労力を節約できます。また、既存モデルが必要なモデルと非常に似ていることを把握します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="6b70d-105">たとえば、「Contracts」という名前の既存モデルでは、作業する必要がある同じファイルが分類されます。</span><span class="sxs-lookup"><span data-stu-id="6b70d-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="6b70d-106">新しいモデルは既存のデータの一部を抽出しますが、一部の追加データを抽出するには更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b70d-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="6b70d-107">新しいモデルを一から作成してトレーニングする代わりに、複製モデル機能を使用して契約モデルのコピーを作成することができます。これにより、サンプル ファイルやエンティティ抽出など、関連するトレーニング アイテムもすべてコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6b70d-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="6b70d-108">モデルを複製すると、名前を変更した後 (たとえば「Contract Renewals (契約書の更新)」に)、モデルを更新できます。</span><span class="sxs-lookup"><span data-stu-id="6b70d-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="6b70d-109">たとえば、必要ない既存の抽出フィールドの一部を削除し、モデルをトレーニングして新しいフィールド (たとえば、「更新日」) を抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="6b70d-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="6b70d-110">モデルを複製する</span><span class="sxs-lookup"><span data-stu-id="6b70d-110">Duplicate a model</span></span>

<span data-ttu-id="6b70d-111">文書理解モデルを複製するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="6b70d-112">コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="6b70d-113">**モデル** ページで、複製するモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="6b70d-114">リボンまたは [**アクションの表示**] ボタン (モデル名の横) を使用して、[**複製する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![[複製] オプションが強調表示された状態で選択されたモデルを示す [モデル] ページのスクリーンショット。](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="6b70d-116">[**モデルの複製**] パネル上で: </span><span class="sxs-lookup"><span data-stu-id="6b70d-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="6b70d-117">a.</span><span class="sxs-lookup"><span data-stu-id="6b70d-117">a.</span></span> <span data-ttu-id="6b70d-118">[**名前**]の下に、複製するモデルの新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![[モデルの複製] パネルを示すスクリーンショット。](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="6b70d-120">b.</span><span class="sxs-lookup"><span data-stu-id="6b70d-120">b.</span></span> <span data-ttu-id="6b70d-121">[**説明**]下で、新しいモデルの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="6b70d-122">c.</span><span class="sxs-lookup"><span data-stu-id="6b70d-122">c.</span></span> <span data-ttu-id="6b70d-123">(省略可能)[**詳細設定**] で、既存の[コンテンツ タイプ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)を関連付けるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="6b70d-124">[**複製する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b70d-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b70d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b70d-125">See Also</span></span>
[<span data-ttu-id="6b70d-126">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="6b70d-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="6b70d-127">モデルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="6b70d-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="6b70d-128">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="6b70d-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="6b70d-129">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="6b70d-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="6b70d-130">説明の種類</span><span class="sxs-lookup"><span data-stu-id="6b70d-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="6b70d-131">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="6b70d-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="6b70d-132">SharePoint Syntex アクセシビリティ モード</span><span class="sxs-lookup"><span data-stu-id="6b70d-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)