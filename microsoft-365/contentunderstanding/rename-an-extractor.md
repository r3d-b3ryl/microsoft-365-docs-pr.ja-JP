---
title: Microsoft SharePoint Syntex で抽出子の名前を変更する
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
description: Microsoft SharePoint Syntex で抽出子の名前を変更する方法および理由について説明します。
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445994"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f29fc-103">Microsoft SharePoint Syntex で抽出子の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="f29fc-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="f29fc-104">抽出されたデータ フィールドを別の名前で参照する場合、ある時点で抽出子の名前を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f29fc-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="f29fc-105">たとえば、組織が契約文書を変更し、文書内で 「顧客」を「クライアント」と呼ぶことにする場合などです。</span><span class="sxs-lookup"><span data-stu-id="f29fc-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="f29fc-106">モデル内で [顧客] フィールドを抽出する場合、[クライアント] に名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f29fc-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="f29fc-107">更新されたモデルを SharePoint ドキュメント ライブラリと同期すると、ドキュメント ライブラリ ビューに新しい [クライアント] 列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f29fc-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="f29fc-108">ビューでは過去のアクティビティの [顧客] 列が保持されますが、モデルによって処理されるすべての新しいドキュメントの新しい [クライアント] 列が更新されます。</span><span class="sxs-lookup"><span data-stu-id="f29fc-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="f29fc-109">更新したモデルを以前に適用したドキュメント ライブラリと同期して新しい列名を表示してください。</span><span class="sxs-lookup"><span data-stu-id="f29fc-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="f29fc-110">抽出子の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="f29fc-110">Rename an extractor</span></span>

<span data-ttu-id="f29fc-111">エンティティ抽出の名前を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f29fc-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="f29fc-112">コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="f29fc-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="f29fc-113">[**モデル**] ページの [**名前**] 列で、抽出子の名前を変更するモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f29fc-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="f29fc-114">[**エンティティ抽出**] で、名前を変更する抽出子の名前を選択し、[**名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f29fc-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![[名前の変更] オプションが強調表示された状態で選択された抽出子を示す [エンティティ抽出] セクションのスクリーンショット。](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="f29fc-116">[**エンティティ抽出の名前の変更**] パネル上で: </span><span class="sxs-lookup"><span data-stu-id="f29fc-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="f29fc-117">a.</span><span class="sxs-lookup"><span data-stu-id="f29fc-117">a.</span></span> <span data-ttu-id="f29fc-118">[**新しい名前**] で抽出子の新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f29fc-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![[エンティティ抽出] パネルを示すスクリーンショット。](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="f29fc-120">b.</span><span class="sxs-lookup"><span data-stu-id="f29fc-120">b.</span></span> <span data-ttu-id="f29fc-121">(省略可能)[**詳細設定**] で、既存のサイト列を関連付けるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f29fc-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="f29fc-122">[**名前の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f29fc-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f29fc-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f29fc-123">See Also</span></span>
[<span data-ttu-id="f29fc-124">エクストラクターを作成する</span><span class="sxs-lookup"><span data-stu-id="f29fc-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f29fc-125">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="f29fc-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="f29fc-126">モデルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="f29fc-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="f29fc-127">説明の種類</span><span class="sxs-lookup"><span data-stu-id="f29fc-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="f29fc-128">エクストラクターの作成時に用語ストアの分類を活用する</span><span class="sxs-lookup"><span data-stu-id="f29fc-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="f29fc-129">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="f29fc-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="f29fc-130">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="f29fc-130">Apply a model</span></span>](apply-a-model.md) 
