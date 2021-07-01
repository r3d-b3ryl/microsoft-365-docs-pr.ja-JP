---
title: 「SharePoint 分類計画」のためのSKOSフォーマットの詳細
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 「SharePoint 分類計画」のためのSKOSフォーマットの詳細
ms.openlocfilehash: 4c08073f453ef0b6a224829b7d4cb4034b74ed14
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228737"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="dc163-103">「SharePoint 分類計画」のためのSKOSフォーマットの詳細</span><span class="sxs-lookup"><span data-stu-id="dc163-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="dc163-104">この記事では、[SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) に使用される RDF ボキャブラリについて説明します。これは [SKOS](https://www.w3.org/TR/skos-primer/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="dc163-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="dc163-105">この RDF 構文のシリアル化には、RDF [タートル](https://www.w3.org/TR/turtle/)を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc163-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="dc163-106">次の表は、[SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) ボキャブラリに相当する [SKOS](https://www.w3.org/TR/skos-primer/) の説明です。</span><span class="sxs-lookup"><span data-stu-id="dc163-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="dc163-107">SharePoint は、SharePoint の分類に対応していない [SKOS](https://www.w3.org/TR/skos-primer/) 値をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="dc163-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="dc163-108">SharePoint 分類計画</span><span class="sxs-lookup"><span data-stu-id="dc163-108">SharePoint taxonomy</span></span>|<span data-ttu-id="dc163-109">SKOS同等物</span><span class="sxs-lookup"><span data-stu-id="dc163-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="dc163-110">sharepoint-taxonomy:用語</span><span class="sxs-lookup"><span data-stu-id="dc163-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="dc163-111">skos: 概念</span><span class="sxs-lookup"><span data-stu-id="dc163-111">skos:Concept</span></span>|
|<span data-ttu-id="dc163-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="dc163-113">skos: ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="dc163-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="dc163-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="dc163-115">skos: inScheme</span><span class="sxs-lookup"><span data-stu-id="dc163-115">skos:inScheme</span></span>|
|<span data-ttu-id="dc163-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="dc163-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="dc163-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="dc163-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="dc163-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="dc163-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="dc163-119">skos: topConceptOf</span><span class="sxs-lookup"><span data-stu-id="dc163-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="dc163-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="dc163-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-121">skos:prefLabel</span></span>|
|<span data-ttu-id="dc163-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="dc163-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="dc163-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-123">skos:prefLabel</span></span>|
|<span data-ttu-id="dc163-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="dc163-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="dc163-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-125">skos:prefLabel</span></span>|
|<span data-ttu-id="dc163-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="dc163-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-127">skos:altLabel</span></span>|
|<span data-ttu-id="dc163-128">sharepoint-taxonomy:説明</span><span class="sxs-lookup"><span data-stu-id="dc163-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="dc163-129">skos: 定義</span><span class="sxs-lookup"><span data-stu-id="dc163-129">skos:definition</span></span>|
|<span data-ttu-id="dc163-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="dc163-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="dc163-131">skos: より幅広い</span><span class="sxs-lookup"><span data-stu-id="dc163-131">skos:broader</span></span>|
|<span data-ttu-id="dc163-132">sharepoint-taxonomy:子供</span><span class="sxs-lookup"><span data-stu-id="dc163-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="dc163-133">skos: 狭い</span><span class="sxs-lookup"><span data-stu-id="dc163-133">skos:narrower</span></span>|

<span data-ttu-id="dc163-134">次の表に、 [OWL](https://www.w3.org/TR/owl2-primer/)から派生した、SharePoint 分類ボキャブラリのエンティティを示します。</span><span class="sxs-lookup"><span data-stu-id="dc163-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="dc163-135">SharePoint の分類ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="dc163-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="dc163-136">OWLから派生。</span><span class="sxs-lookup"><span data-stu-id="dc163-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="dc163-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="dc163-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="dc163-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="dc163-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="dc163-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="dc163-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="dc163-140">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="dc163-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="dc163-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="dc163-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="dc163-142">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="dc163-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="dc163-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="dc163-144">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="dc163-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="dc163-145">SharePoint の分類ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="dc163-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="dc163-p103">分類は、正式なクラス分けシステムです。分類により、何かを記述する単語、ラベル、および用語はグループ化され、それらのグループは 1 つの階層に配置されます。</span><span class="sxs-lookup"><span data-stu-id="dc163-p103">A taxonomy is a formal classification system. A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="dc163-148">**sharepoint-taxonomy:用語**</span><span class="sxs-lookup"><span data-stu-id="dc163-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="dc163-149">管理されたメタデータ階層内に用語またはキーワードを表します。</span><span class="sxs-lookup"><span data-stu-id="dc163-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="dc163-150">[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) は、SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の最小単位です。</span><span class="sxs-lookup"><span data-stu-id="dc163-150">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="dc163-151">各[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は[TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group)に属する [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) に属します。</span><span class="sxs-lookup"><span data-stu-id="dc163-151">Each [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span>

<span data-ttu-id="dc163-152">[項](/dotnet/api/microsoft.sharepoint.taxonomy.term) を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-152">The syntax to define a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="dc163-153">[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)内に[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) が絶対に存在しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dc163-153">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="dc163-154">DefaultLabel は、視覚的表現に表示された[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の名前です。</span><span class="sxs-lookup"><span data-stu-id="dc163-154">DefaultLabel is the name of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="dc163-155">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の定義には、次のようなフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="dc163-155">The required fields for defining a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="dc163-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="dc163-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="dc163-158">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)は次のことができます；</span><span class="sxs-lookup"><span data-stu-id="dc163-158">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="dc163-159">同じ [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) 両方が提供されている[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="dc163-159">Be hierarchically related to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="dc163-160">複数の子[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)を持っていますが、親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="dc163-160">Have multiple child [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="dc163-161">もしそれが[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)のtopLevelTermOfの場合、親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)が定義されていません。 </span><span class="sxs-lookup"><span data-stu-id="dc163-161">Not have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="dc163-162">[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語毎に1つの defaultLabel が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc163-162">Have one defaultLabel, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="dc163-163">親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)が含まれていないか、[TermSet ](/dotnet/api/microsoft.sharepoint.taxonomy.termset)のtopLevelTermOf でもない場合は、存在しません。</span><span class="sxs-lookup"><span data-stu-id="dc163-163">Not exist if it neither contains a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="dc163-164">同じ階層レベルで一意の defaultLabel のみを持ちます。</span><span class="sxs-lookup"><span data-stu-id="dc163-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="dc163-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="dc163-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="dc163-166">"TermSet" と呼ばれる、階層構造またはフラットな用語オブジェクトのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="dc163-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="dc163-167">名前が示しているように、TermSet は、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)のセットです。</span><span class="sxs-lookup"><span data-stu-id="dc163-167">As the name suggests, TermSet is a set of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="dc163-168">[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-168">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="dc163-169">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は独自に存在できません。</span><span class="sxs-lookup"><span data-stu-id="dc163-169">No [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span>

<span data-ttu-id="dc163-170">[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-170">The syntax to define a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="dc163-171">[Termsets](/dotnet/api/microsoft.sharepoint.taxonomy.termset)は、[TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group)内に論理的にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="dc163-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="dc163-172">[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) を定義するために必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-172">The required field for defining a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="dc163-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="dc163-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="dc163-174">与えられたtermSetName が[TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group)内でユニークではない場合、SharePointは名前の末尾に数字を追加して、termSetNameの独自性を維持します。</span><span class="sxs-lookup"><span data-stu-id="dc163-174">In the case of the termSetName provided is not unique within the [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="dc163-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="dc163-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="dc163-176">SharePoint では、このプロパティを使用して、[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)([TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)の[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) の階層へのエントリポイント) の最上位 の[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) がマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="dc163-176">SharePoint uses this property to map the top most [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="dc163-177">これは、sharepoint-taxonomy:topLevelTermOfの逆リレーションシップです。</span><span class="sxs-lookup"><span data-stu-id="dc163-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span>

<span data-ttu-id="dc163-178">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> <span data-ttu-id="dc163-179">親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の最上位の[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc163-179">You cannot define the top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="dc163-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="dc163-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="dc163-181">Sharepoint-taxonomy:topLevelTermOfは、sharepoint-taxonomy:hasTopLevelTermの逆です。</span><span class="sxs-lookup"><span data-stu-id="dc163-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="dc163-182">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="dc163-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="dc163-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="dc163-184">これを使用して、 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)を[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="dc163-184">Use this to map a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="dc163-185">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は、1つの[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="dc163-185">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="dc163-186">SharePointがこのプロパティを必要なのは、[用語](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)を定義する場合です。</span><span class="sxs-lookup"><span data-stu-id="dc163-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="dc163-187">必要なラベル</span><span class="sxs-lookup"><span data-stu-id="dc163-187">Required labels</span></span>

<span data-ttu-id="dc163-188">管理されたメタデータの使用を開始する前に、組織で慎重な計画が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="dc163-189">必要な計画のボリュームは、分類をどの程度フォーマルにするかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dc163-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="dc163-190">これは、メタデータに適用するコントロールのサイズによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="dc163-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="dc163-191">階層の各レベルで、用語または TermSet の必須ラベルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="dc163-p111">用語には、既定の言語では 1 つ以上のラベル、既定以外の言語では 0 個以上のラベルを含めることができます。用語に言語のラベルがある場合、ラベルの 1 つが既定のラベルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-p111">A Term can have one or more labels in the default language, and zero or more labels in the non-default language. If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="dc163-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="dc163-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="dc163-195">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の必須パラメーターである、この[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の既定の字句ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc163-195">Use this default lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="dc163-196">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)を視覚的に表現するために使用します。</span><span class="sxs-lookup"><span data-stu-id="dc163-196">Use to visually representing the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="dc163-197">DefaultLabel を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="dc163-198">DefaultLabel には、文字列と 言語タグという2つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="dc163-199">言語は、 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の作業言語のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-199">The language must be one of the [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="dc163-200">DefaultLabel は、同じ階層レベルにある同じ [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)内のすべての[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) に関して固有である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-200">The defaultLabel must be unique for all [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="dc163-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="dc163-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="dc163-202">現在の TermSet オブジェクトの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dc163-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="dc163-203">これが、[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の作業言語内の[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)の字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="dc163-203">This the lexical label for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="dc163-204">これは、[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に必須のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="dc163-204">This is a required parameter for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="dc163-205">[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)を視覚的に表現するために使用します。</span><span class="sxs-lookup"><span data-stu-id="dc163-205">Use to visually representing a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="dc163-206">TermSetName を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="dc163-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="dc163-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="dc163-208">現在の TermSet オブジェクトのプロパティ名を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dc163-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="dc163-209">これは、sharepoint-taxonomy:SharedCustomPropertyForTerm、sharepoint-taxonomy:LocalCustomPropertyForTerm および[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語内の working language.sharepoint-taxonomy:CustomPropertyForTermSet のTermSetの字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="dc163-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="dc163-210">The sharepoint-taxonomy:propertyNameは、CustomProperty のキーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="dc163-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="dc163-211">PropetyName を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="dc163-212">省略可能なラベル。</span><span class="sxs-lookup"><span data-stu-id="dc163-212">Optional labels</span></span>

<span data-ttu-id="dc163-213">また、任意のラベルを分類に追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc163-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="dc163-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="dc163-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="dc163-215">これは、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の別の字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="dc163-215">This is the alternate lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="dc163-216">ほかのラベルを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="dc163-217">セマンティックの関係</span><span class="sxs-lookup"><span data-stu-id="dc163-217">Semantic relationships</span></span>

<span data-ttu-id="dc163-218">分類は階層的で、場合によっては単純な "関連用語" に関連するリレーションシップですが、"意味的な関係" やユーザー設定のリレーションシップがあるものもあります。</span><span class="sxs-lookup"><span data-stu-id="dc163-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span>

<span data-ttu-id="dc163-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="dc163-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="dc163-220">これにより、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) が別の[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="dc163-220">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="dc163-221">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)は、[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)の最上位 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の場合もありますが、そうでない場合は親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc163-221">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="dc163-222">親を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="dc163-223">これは、TermA が親で、TermA が子であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dc163-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="dc163-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="dc163-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="dc163-225">このオブジェクトには、1つ以上の子 TermSet インスタンスが含まれています。これらは、TermSets プロパティからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dc163-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="dc163-226">このクラスには、新しい子 TermSet オブジェクトを作成するためのメソッドもあります。</span><span class="sxs-lookup"><span data-stu-id="dc163-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="dc163-227">子用語と TermSet インスタンスを編集するためのアクセス許可がグループに指定されています。</span><span class="sxs-lookup"><span data-stu-id="dc163-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span>

<span data-ttu-id="dc163-228">これにより、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) が別の[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="dc163-228">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="dc163-229">子を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="dc163-230">これは、TermA が親で、TermA が子であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dc163-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="dc163-231">ドキュメントメモ</span><span class="sxs-lookup"><span data-stu-id="dc163-231">Documentation notes</span></span>

<span data-ttu-id="dc163-232">ここでは、Microsoft.SharePoint.Taxonomy Namespaceに記載されている分類について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="dc163-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="dc163-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="dc163-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="dc163-234">ここでは、 [SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) の語彙のエンティティについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="dc163-234">This is a detailed explanation of any [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span>

<span data-ttu-id="dc163-235">説明を追加する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="dc163-236">カスタム プロパティ</span><span class="sxs-lookup"><span data-stu-id="dc163-236">Custom properties</span></span>

<span data-ttu-id="dc163-237">読み取り専用ディクショナリから、現在の用語オブジェクトのカスタムプロパティオブジェクトのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc163-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="dc163-238">カスタムプロパティは、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) または[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に対して定義できるキー値のペアです。また、 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) または [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)の詳細についても説明します。</span><span class="sxs-lookup"><span data-stu-id="dc163-238">Custom Properties are key-values pairs that can be defined for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="dc163-239">SharePoint では、propertyName を使用してカスタムプロパティのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc163-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="dc163-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="dc163-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="dc163-241">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="dc163-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="dc163-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="dc163-243">[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) のカスタムプロパティを[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)と共に使用する必要があり、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) を再使用している場合はSharedCustomPropertyForTerm を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-243">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="dc163-244">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="dc163-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="dc163-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="dc163-246">[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) のカスタムプロパティを [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)と共に使用する必要がなく、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) を再利用する場合は、LocalCustomPropertyForTermの下で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-246">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="dc163-247">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="dc163-248">データ プロパティ</span><span class="sxs-lookup"><span data-stu-id="dc163-248">Data properties</span></span>

<span data-ttu-id="dc163-249">階層の各レベルで、用語や TermSet に特定のデータプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="dc163-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="dc163-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="dc163-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="dc163-251">この機能を使用して、SharePoint のリストとライブラリで使用できる[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) または [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc163-251">Use this to specify if a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>

<span data-ttu-id="dc163-252">この構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc163-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="dc163-253">ドメインと範囲</span><span class="sxs-lookup"><span data-stu-id="dc163-253">Domain and range</span></span>

<span data-ttu-id="dc163-254">下の表は、SharePoint の分類ボキャブラリのドメインと範囲を示しています。</span><span class="sxs-lookup"><span data-stu-id="dc163-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="dc163-255">述語/動詞</span><span class="sxs-lookup"><span data-stu-id="dc163-255">Predicates/verb</span></span>|<span data-ttu-id="dc163-256">意味</span><span class="sxs-lookup"><span data-stu-id="dc163-256">Meaning</span></span>|<span data-ttu-id="dc163-257">ドメイン</span><span class="sxs-lookup"><span data-stu-id="dc163-257">Domain</span></span>|<span data-ttu-id="dc163-258">範囲</span><span class="sxs-lookup"><span data-stu-id="dc163-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="dc163-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-259">inTermSet</span></span>|<span data-ttu-id="dc163-260">用語セットで</span><span class="sxs-lookup"><span data-stu-id="dc163-260">In term set</span></span>|<span data-ttu-id="dc163-261">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-261">Term</span></span>|<span data-ttu-id="dc163-262">用語セット</span><span class="sxs-lookup"><span data-stu-id="dc163-262">Term Set</span></span>|
<span data-ttu-id="dc163-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="dc163-263">inTermGroup</span></span>|<span data-ttu-id="dc163-264">用語グループ</span><span class="sxs-lookup"><span data-stu-id="dc163-264">In term group</span></span>|<span data-ttu-id="dc163-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-265">TermSet</span></span>|<span data-ttu-id="dc163-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="dc163-266">TermGroup</span></span>|
<span data-ttu-id="dc163-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="dc163-267">topLevelTermOf</span></span>|<span data-ttu-id="dc163-268">は最上位の用語</span><span class="sxs-lookup"><span data-stu-id="dc163-268">Is Top Level Term Of</span></span>|<span data-ttu-id="dc163-269">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-269">Term</span></span>|<span data-ttu-id="dc163-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-270">TermSet</span></span>|
<span data-ttu-id="dc163-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="dc163-271">hasTopLevelTerm</span></span>|<span data-ttu-id="dc163-272">最上位の用語</span><span class="sxs-lookup"><span data-stu-id="dc163-272">Has top level term</span></span>|<span data-ttu-id="dc163-273">用語セット</span><span class="sxs-lookup"><span data-stu-id="dc163-273">Term Set</span></span>|<span data-ttu-id="dc163-274">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-274">Term</span></span>|
<span data-ttu-id="dc163-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="dc163-275">termSetName</span></span>|<span data-ttu-id="dc163-276">用語セットに名前がある</span><span class="sxs-lookup"><span data-stu-id="dc163-276">Term set has Name</span></span>|<span data-ttu-id="dc163-277">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-277">Term</span></span>|<span data-ttu-id="dc163-278">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="dc163-278">Plain literal</span></span>|
<span data-ttu-id="dc163-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-279">defaultLabel</span></span>|<span data-ttu-id="dc163-280">Term に既定のラベルがある</span><span class="sxs-lookup"><span data-stu-id="dc163-280">Term has default label</span></span>|<span data-ttu-id="dc163-281">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-281">Term</span></span>|<span data-ttu-id="dc163-282">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="dc163-282">Plain literal</span></span>|
<span data-ttu-id="dc163-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="dc163-283">otherLabel</span></span>|<span data-ttu-id="dc163-284">"その他" というラベル</span><span class="sxs-lookup"><span data-stu-id="dc163-284">Term has other label</span></span>|<span data-ttu-id="dc163-285">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-285">Term</span></span>|<span data-ttu-id="dc163-286">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="dc163-286">Plain literal</span></span>|
<span data-ttu-id="dc163-287">PropertyName</span><span class="sxs-lookup"><span data-stu-id="dc163-287">propertyName</span></span>|<span data-ttu-id="dc163-288">プロパティラベルあり</span><span class="sxs-lookup"><span data-stu-id="dc163-288">Has Property Label</span></span>|<span data-ttu-id="dc163-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="dc163-290">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="dc163-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="dc163-291">説明</span><span class="sxs-lookup"><span data-stu-id="dc163-291">description</span></span>|<span data-ttu-id="dc163-292">説明がある</span><span class="sxs-lookup"><span data-stu-id="dc163-292">Has Description</span></span>|<span data-ttu-id="dc163-293">すべて</span><span class="sxs-lookup"><span data-stu-id="dc163-293">All</span></span>|<span data-ttu-id="dc163-294">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="dc163-294">Plain literal</span></span>|
|<span data-ttu-id="dc163-295">親</span><span class="sxs-lookup"><span data-stu-id="dc163-295">parent</span></span>|<span data-ttu-id="dc163-296">親がある</span><span class="sxs-lookup"><span data-stu-id="dc163-296">Has parent</span></span>|<span data-ttu-id="dc163-297">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-297">Term</span></span>|<span data-ttu-id="dc163-298">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-298">Term</span></span>|
|<span data-ttu-id="dc163-299">子</span><span class="sxs-lookup"><span data-stu-id="dc163-299">child</span></span>|<span data-ttu-id="dc163-300">子がある</span><span class="sxs-lookup"><span data-stu-id="dc163-300">Has Child</span></span>|<span data-ttu-id="dc163-301">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-301">Term</span></span>|<span data-ttu-id="dc163-302">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-302">Term</span></span>|
|<span data-ttu-id="dc163-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="dc163-303">isAvailableForTagging</span></span>|<span data-ttu-id="dc163-304">タグ付けで使用可能</span><span class="sxs-lookup"><span data-stu-id="dc163-304">Is available for tagging</span></span>|<span data-ttu-id="dc163-305">用語、用語セット</span><span class="sxs-lookup"><span data-stu-id="dc163-305">Term, Term Set</span></span>|<span data-ttu-id="dc163-306">ブール値</span><span class="sxs-lookup"><span data-stu-id="dc163-306">Boolean</span></span>|
|<span data-ttu-id="dc163-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="dc163-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="dc163-308">共有カスタムプロパティがあります</span><span class="sxs-lookup"><span data-stu-id="dc163-308">Has shared custom property</span></span>|<span data-ttu-id="dc163-309">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-309">Term</span></span>|<span data-ttu-id="dc163-310">Boolean、string、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="dc163-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="dc163-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="dc163-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="dc163-312">ローカルのカスタムプロパティがあります</span><span class="sxs-lookup"><span data-stu-id="dc163-312">Has local custom property</span></span>|<span data-ttu-id="dc163-313">用語</span><span class="sxs-lookup"><span data-stu-id="dc163-313">Term</span></span>|<span data-ttu-id="dc163-314">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="dc163-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="dc163-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="dc163-316">Custom プロパティがある</span><span class="sxs-lookup"><span data-stu-id="dc163-316">Has Custom Property</span></span>|<span data-ttu-id="dc163-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="dc163-317">TermSet</span></span>|<span data-ttu-id="dc163-318">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="dc163-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="dc163-319">[SKOS](https://www.w3.org/TR/skos-primer/)これは[SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) が許可されていない有効なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="dc163-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="dc163-320">階層冗長化-[SKOS](https://www.w3.org/TR/skos-primer/) 概念が複数の階層の概念に同時に関連付けられている います。ただし、sharepoint の分類項目：用語は、1つの sharepoint 分類：親しか持てませんので、用語の循環的な依存関係になり、それは許可されません。</span><span class="sxs-lookup"><span data-stu-id="dc163-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="dc163-p118">孤立した用語は、SharePoint 分類では許可されていません。すべての sharepoint-taxonomy:Term には sharepoint-taxonomy:parent が必要です。または、TermSet の sharepoint-taxonomy:topLevelTermOf である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc163-p118">Orphaned terms are not allowed in SharePoint taxonomy. Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="dc163-323">SharePoint の分類は、関連する関係をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="dc163-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="dc163-324">SharePoint の分類では、2種類の階層関係 (sharepoint-taxonomy:親およびsharepoint-Taxonomy:子) のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="dc163-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span>
- <span data-ttu-id="dc163-325">[SKOS](https://www.w3.org/TR/skos-primer/)とは異なり、SharePoint 分類のボキャブラリの階層関係は、同じTermSet内の用語を使用して作成する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="dc163-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc163-326">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc163-326">See also</span></span>

[<span data-ttu-id="dc163-327">SKOS ベースの形式を使用して用語セットをインポートする</span><span class="sxs-lookup"><span data-stu-id="dc163-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)