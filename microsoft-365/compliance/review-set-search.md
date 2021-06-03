---
title: レビュー セット内のコンテンツをクエリする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: レビュー セットでクエリを作成して実行し、コンテンツを整理して、より効率的なレビューを行う方法についてAdvanced eDiscoveryします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736419"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="5779d-103">レビュー セット内のコンテンツのクエリとフィルター</span><span class="sxs-lookup"><span data-stu-id="5779d-103">Query and filter content in a review set</span></span>

<span data-ttu-id="5779d-104">ほとんどの場合、レビュー セット内のコンテンツを深く掘り下げ、より効率的なレビューを容易にするために整理すると便利です。</span><span class="sxs-lookup"><span data-stu-id="5779d-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="5779d-105">レビュー セットでフィルターとクエリを使用すると、レビューの条件を満たすドキュメントのサブセットに焦点を当てるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5779d-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="5779d-106">既定のフィルター</span><span class="sxs-lookup"><span data-stu-id="5779d-106">Default filters</span></span>

<span data-ttu-id="5779d-107">レビュー セットには、レビュー セットに事前に読み込まれる 5 つの既定のフィルターがあります。</span><span class="sxs-lookup"><span data-stu-id="5779d-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="5779d-108">キーワード</span><span class="sxs-lookup"><span data-stu-id="5779d-108">Keywords</span></span>
- <span data-ttu-id="5779d-109">日付</span><span class="sxs-lookup"><span data-stu-id="5779d-109">Date</span></span>
- <span data-ttu-id="5779d-110">送信者/作成者</span><span class="sxs-lookup"><span data-stu-id="5779d-110">Sender/Author</span></span>
- <span data-ttu-id="5779d-111">件名/タイトル</span><span class="sxs-lookup"><span data-stu-id="5779d-111">Subject/Title</span></span>
- <span data-ttu-id="5779d-112">タグ</span><span class="sxs-lookup"><span data-stu-id="5779d-112">Tags</span></span>

![既定のフィルターの種類](../media/DefaultFilterTypes.png)

<span data-ttu-id="5779d-114">各フィルターをクリックして展開し、値を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="5779d-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="5779d-115">フィルターの外側をクリックすると、自動的にレビュー セットにフィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="5779d-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="5779d-116">次のスクリーンショットは、日付範囲内のドキュメントを表示するように構成された日付フィルターを示しています。</span><span class="sxs-lookup"><span data-stu-id="5779d-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![既定のフィルターが展開されました](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="5779d-118">フィルターの追加または削除</span><span class="sxs-lookup"><span data-stu-id="5779d-118">Add or remove filters</span></span>

<span data-ttu-id="5779d-119">レビュー セットに表示されるフィルターを追加または削除するには、[フィルター  ] を選択して、フライアウト ページに表示されるフィルター パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5779d-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![[フィルター] パネル](../media/FilterPanel.png)

<span data-ttu-id="5779d-121">使用可能なフィルターは、次の 4 つのセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5779d-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="5779d-122">**検索**: さまざまな検索機能を提供するフィルター。</span><span class="sxs-lookup"><span data-stu-id="5779d-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="5779d-123">**Analytics &予測** コーディング: ドキュメント の電子メール分析ジョブを実行するか、予測コーディング モデル **を** 使用するときに&追加されたプロパティのフィルター。</span><span class="sxs-lookup"><span data-stu-id="5779d-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="5779d-124">**ID :** ドキュメントのすべての ID プロパティのフィルター。</span><span class="sxs-lookup"><span data-stu-id="5779d-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="5779d-125">**アイテムのプロパティ**: ドキュメントプロパティのフィルター。</span><span class="sxs-lookup"><span data-stu-id="5779d-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="5779d-126">各セクションを展開し、フィルターを選択または選択解除して、フィルター セットでフィルターを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="5779d-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="5779d-127">フィルターを追加すると、フィルター セットに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5779d-127">When you add a filter, it's displayed in the filter set.</span></span> 

![フィルター パネルのフィルター セクションとプロパティの一覧](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="5779d-129">フィルター パネルでセクションを展開すると、既定のフィルターの種類が選択されています。</span><span class="sxs-lookup"><span data-stu-id="5779d-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="5779d-130">これらを選択したままにするか、選択を解除し、フィルター セットから削除できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="5779d-131">フィルターの種類</span><span class="sxs-lookup"><span data-stu-id="5779d-131">Filter types</span></span>

<span data-ttu-id="5779d-132">レビュー セット内のすべての検索可能なフィールドには、特定のフィールドに基づくフィルター アイテムに使用できる対応するフィルターがあります。</span><span class="sxs-lookup"><span data-stu-id="5779d-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="5779d-133">フィルターには複数の種類があります。</span><span class="sxs-lookup"><span data-stu-id="5779d-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="5779d-134">**Freetext**: フリーテキスト フィルターは、"Subject" などのテキスト フィールドに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5779d-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="5779d-135">複数の検索用語をコンマで区切って一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="5779d-136">**日付**: 日付フィルターは、"最終変更日" などの日付フィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5779d-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="5779d-137">**検索オプション**: 検索オプション フィルターは、レビュー内の特定のフィールドに対して、可能な値の一覧を提供します (各値には、選択できるチェック ボックスが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="5779d-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="5779d-138">このフィルターは、レビュー セットに指定できる値の数が有限である "Sender" などのフィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5779d-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="5779d-139">**キーワード**: キーワード条件は、用語の検索に使用できるフリーテキスト条件の特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="5779d-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="5779d-140">この種類のフィルターでは、KQL のようなクエリ言語を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5779d-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="5779d-141">詳細については、このトピックの「クエリ言語」および「高度なクエリ ビルダー」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5779d-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="5779d-142">フィルター関係を含める/除外する</span><span class="sxs-lookup"><span data-stu-id="5779d-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="5779d-143">特定のフィルターの include リレーションシップと exclude リレーションシップを変更するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5779d-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="5779d-144">たとえば、タグ フィルターで、ドロップダウン フィルターで [等しくない] を選択すると、特定のタグでタグ付けされたアイテムを除外できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![タグ フィルターを除外する](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="5779d-146">フィルターをクエリとして保存する</span><span class="sxs-lookup"><span data-stu-id="5779d-146">Save filters as queries</span></span>

<span data-ttu-id="5779d-147">フィルターに満足したら、フィルターの組み合わせをフィルター クエリとして保存できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="5779d-148">これにより、将来のレビュー セッションでフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="5779d-149">フィルターを保存するには、[クエリの **保存] を選択し** 、名前を付けて指定します。</span><span class="sxs-lookup"><span data-stu-id="5779d-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="5779d-150">ユーザーまたは他のレビュー担当者は、[保存済みフィルター クエリ] ドロップダウンを選択し、設定されたドキュメントを確認するために適用するフィルター クエリを選択することで、以前に保存したフィルター クエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![フィルター クエリを保存する](../media/SaveFilterQuery.png)

<span data-ttu-id="5779d-152">フィルター クエリを削除するには、フィルター パネルを開き、クエリの横にあるゴミ箱アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5779d-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![フィルター クエリを削除する](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="5779d-154">クエリ言語</span><span class="sxs-lookup"><span data-stu-id="5779d-154">Query language</span></span>

<span data-ttu-id="5779d-155">フィルターの使用に加えて、キーワード フィルターで KQL のようなクエリ言語を使用して、レビュー セット検索クエリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5779d-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="5779d-156">レビュー セット クエリのクエリ言語は **、AND、OR、NOT、NEAR** などの標準ブール演算子を **サポートします**。 </span><span class="sxs-lookup"><span data-stu-id="5779d-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="5779d-157">また、1 文字のワイルドカード (?) と複数文字のワイルドカード (\*) もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5779d-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="5779d-158">高度なクエリ ビルダー</span><span class="sxs-lookup"><span data-stu-id="5779d-158">Advanced query builder</span></span>

<span data-ttu-id="5779d-159">さらに高度なクエリを作成して、レビュー セット内のドキュメントを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="5779d-160">フィルター パネルを開き、[フィルター] **を選択** し、[検索] セクション **を展開** します。</span><span class="sxs-lookup"><span data-stu-id="5779d-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![KQL フィルターの追加](../media/AddKQLFilter.png)

2. <span data-ttu-id="5779d-162">**KQL フィルターを選択し、[** クエリ ビルダーを **開く] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5779d-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="5779d-163">このパネルでは、クエリ ビルダーを使用して複雑な KQL クエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5779d-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="5779d-164">AND または OR リレーションシップによって論理的に接続されている複数の条件で構成される条件グループを追加したり、**条件グループ\*\*\*\*を** 追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5779d-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![クエリ ビルダーを使用して複雑なフィルター クエリを構成する](../media/ComplexQuery.png)
