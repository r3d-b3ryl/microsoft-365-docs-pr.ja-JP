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
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087283"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="2d60a-103">「SharePoint 分類計画」のためのSKOSフォーマットの詳細</span><span class="sxs-lookup"><span data-stu-id="2d60a-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="2d60a-104">この記事では、[SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) に使用される RDF ボキャブラリについて説明します。これは [SKOS](https://www.w3.org/TR/skos-primer/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="2d60a-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="2d60a-105">この RDF 構文のシリアル化には、RDF [タートル](https://www.w3.org/TR/turtle/)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="2d60a-106">次の表は、[SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) ボキャブラリに相当する [SKOS](https://www.w3.org/TR/skos-primer/) の説明です。</span><span class="sxs-lookup"><span data-stu-id="2d60a-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="2d60a-107">SharePoint は、SharePoint の分類に対応していない [SKOS](https://www.w3.org/TR/skos-primer/) 値をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="2d60a-108">SharePoint 分類計画</span><span class="sxs-lookup"><span data-stu-id="2d60a-108">SharePoint taxonomy</span></span>|<span data-ttu-id="2d60a-109">SKOS同等物</span><span class="sxs-lookup"><span data-stu-id="2d60a-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="2d60a-110">sharepoint-taxonomy:用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="2d60a-111">skos: 概念</span><span class="sxs-lookup"><span data-stu-id="2d60a-111">skos:Concept</span></span>|
|<span data-ttu-id="2d60a-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="2d60a-113">skos: ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="2d60a-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="2d60a-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="2d60a-115">skos: inScheme</span><span class="sxs-lookup"><span data-stu-id="2d60a-115">skos:inScheme</span></span>|
|<span data-ttu-id="2d60a-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="2d60a-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="2d60a-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="2d60a-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="2d60a-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="2d60a-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="2d60a-119">skos: topConceptOf</span><span class="sxs-lookup"><span data-stu-id="2d60a-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="2d60a-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="2d60a-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-121">skos:prefLabel</span></span>|
|<span data-ttu-id="2d60a-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="2d60a-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="2d60a-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-123">skos:prefLabel</span></span>|
|<span data-ttu-id="2d60a-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="2d60a-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="2d60a-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-125">skos:prefLabel</span></span>|
|<span data-ttu-id="2d60a-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="2d60a-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-127">skos:altLabel</span></span>|
|<span data-ttu-id="2d60a-128">sharepoint-taxonomy:説明</span><span class="sxs-lookup"><span data-stu-id="2d60a-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="2d60a-129">skos: 定義</span><span class="sxs-lookup"><span data-stu-id="2d60a-129">skos:definition</span></span>|
|<span data-ttu-id="2d60a-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="2d60a-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="2d60a-131">skos: より幅広い</span><span class="sxs-lookup"><span data-stu-id="2d60a-131">skos:broader</span></span>|
|<span data-ttu-id="2d60a-132">sharepoint-taxonomy:子供</span><span class="sxs-lookup"><span data-stu-id="2d60a-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="2d60a-133">skos: 狭い</span><span class="sxs-lookup"><span data-stu-id="2d60a-133">skos:narrower</span></span>|

<span data-ttu-id="2d60a-134">次の表に、 [OWL](https://www.w3.org/TR/owl2-primer/)から派生した、SharePoint 分類ボキャブラリのエンティティを示します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="2d60a-135">SharePoint の分類ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="2d60a-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="2d60a-136">OWLから派生。</span><span class="sxs-lookup"><span data-stu-id="2d60a-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="2d60a-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="2d60a-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="2d60a-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="2d60a-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="2d60a-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="2d60a-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="2d60a-140">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="2d60a-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="2d60a-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="2d60a-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="2d60a-142">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="2d60a-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="2d60a-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="2d60a-144">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="2d60a-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="2d60a-145">SharePoint の分類ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="2d60a-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="2d60a-146">分類は、正式な分類システムです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="2d60a-147">分類により、何かを記述する単語、ラベル、および用語はグループ化され、それらのグループは 1 つの階層として配置されます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="2d60a-148">**sharepoint-taxonomy:用語**</span><span class="sxs-lookup"><span data-stu-id="2d60a-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="2d60a-149">管理されたメタデータ階層内に用語またはキーワードを表します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="2d60a-150">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) は、SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の最小単位です。</span><span class="sxs-lookup"><span data-stu-id="2d60a-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="2d60a-151">各[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) は[TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)に属する [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) に属します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="2d60a-152">[項](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="2d60a-153">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内に[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) が絶対に存在しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="2d60a-154">DefaultLabel は、視覚的表現に表示された[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の名前です。</span><span class="sxs-lookup"><span data-stu-id="2d60a-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="2d60a-155">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の定義には、次のようなフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="2d60a-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="2d60a-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="2d60a-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="2d60a-158">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は次のことができます；</span><span class="sxs-lookup"><span data-stu-id="2d60a-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="2d60a-159">同じ [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 両方が提供されている[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="2d60a-160">複数の子[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を持っていますが、親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="2d60a-161">もしそれが[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)のtopLevelTermOfの場合、親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が定義されていません。 </span><span class="sxs-lookup"><span data-stu-id="2d60a-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="2d60a-162">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語毎に1つの defaultLabel が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2d60a-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="2d60a-163">親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が含まれていないか、[TermSet ](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)のtopLevelTermOf でもない場合は、存在しません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="2d60a-164">同じ階層レベルで一意の defaultLabel のみを持ちます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="2d60a-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="2d60a-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="2d60a-166">"TermSet" と呼ばれる、階層構造またはフラットな用語オブジェクトのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="2d60a-167">名前が示しているように、TermSet は、[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)のセットです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="2d60a-168">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) は [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="2d60a-169">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) は独自に存在できません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="2d60a-170">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="2d60a-171">[Termsets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)は、[TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)内に論理的にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="2d60a-172">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) を定義するために必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="2d60a-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="2d60a-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="2d60a-174">与えられたtermSetName が[TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)内でユニークではない場合、SharePointは名前の末尾に数字を追加して、termSetNameの独自性を維持します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="2d60a-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="2d60a-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="2d60a-176">SharePoint では、このプロパティを使用して、[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)([TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) の階層へのエントリポイント) の最上位 の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) がマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="2d60a-177">これは、sharepoint-taxonomy:topLevelTermOfの逆リレーションシップです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="2d60a-178">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="2d60a-179">親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の最上位の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="2d60a-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="2d60a-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="2d60a-181">Sharepoint-taxonomy:topLevelTermOfは、sharepoint-taxonomy:hasTopLevelTermの逆です。</span><span class="sxs-lookup"><span data-stu-id="2d60a-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="2d60a-182">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="2d60a-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="2d60a-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="2d60a-184">これを使用して、 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="2d60a-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="2d60a-185">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) は、1つの[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="2d60a-186">SharePointがこのプロパティを必要なのは、[用語](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)を定義する場合です。</span><span class="sxs-lookup"><span data-stu-id="2d60a-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="2d60a-187">必要なラベル</span><span class="sxs-lookup"><span data-stu-id="2d60a-187">Required labels</span></span>

<span data-ttu-id="2d60a-188">管理されたメタデータの使用を開始する前に、組織で慎重な計画が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="2d60a-189">必要な計画のボリュームは、分類をどの程度フォーマルにするかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="2d60a-190">これは、メタデータに適用するコントロールのサイズによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="2d60a-191">階層の各レベルで、用語または TermSet の必須ラベルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="2d60a-192">1つの用語には、既定の言語で1つまたは複数のラベルを含めることができます。また、既定以外の言語には0以上のラベルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="2d60a-193">用語に言語のラベルが含まれている場合は、ラベルの1つは既定のラベルにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="2d60a-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="2d60a-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="2d60a-195">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の必須パラメーターである、この[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の既定の字句ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="2d60a-196">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を視覚的に表現するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="2d60a-197">DefaultLabel を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="2d60a-198">DefaultLabel には、文字列と 言語タグという2つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="2d60a-199">言語は、 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の作業言語のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="2d60a-200">DefaultLabel は、同じ階層レベルにある同じ [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内のすべての[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) に関して固有である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="2d60a-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="2d60a-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="2d60a-202">現在の TermSet オブジェクトの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="2d60a-203">これが、[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の作業言語内の[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="2d60a-204">これは、[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に必須のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="2d60a-205">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)を視覚的に表現するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="2d60a-206">TermSetName を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="2d60a-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="2d60a-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="2d60a-208">現在の TermSet オブジェクトのプロパティ名を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="2d60a-209">これは、sharepoint-taxonomy:SharedCustomPropertyForTerm、sharepoint-taxonomy:LocalCustomPropertyForTerm および[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語内の working language.sharepoint-taxonomy:CustomPropertyForTermSet のTermSetの字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="2d60a-210">The sharepoint-taxonomy:propertyNameは、CustomProperty のキーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="2d60a-211">PropetyName を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="2d60a-212">省略可能なラベル。</span><span class="sxs-lookup"><span data-stu-id="2d60a-212">Optional labels</span></span>

<span data-ttu-id="2d60a-213">また、任意のラベルを分類に追加できます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="2d60a-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="2d60a-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="2d60a-215">これは、[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の別の字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="2d60a-216">ほかのラベルを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="2d60a-217">セマンティックの関係</span><span class="sxs-lookup"><span data-stu-id="2d60a-217">Semantic relationships</span></span>

<span data-ttu-id="2d60a-218">分類は階層的で、場合によっては単純な "関連用語" に関連するリレーションシップですが、"意味的な関係" やユーザー設定のリレーションシップがあるものもあります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="2d60a-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="2d60a-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="2d60a-220">これにより、[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) が別の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="2d60a-221">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は、[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の最上位 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の場合もありますが、そうでない場合は親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d60a-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="2d60a-222">親を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="2d60a-223">これは、TermA が親で、TermA が子であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="2d60a-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="2d60a-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="2d60a-225">このオブジェクトには、1つ以上の子 TermSet インスタンスが含まれています。これらは、TermSets プロパティからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="2d60a-226">このクラスには、新しい子 TermSet オブジェクトを作成するためのメソッドもあります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="2d60a-227">子用語と TermSet インスタンスを編集するためのアクセス許可がグループに指定されています。</span><span class="sxs-lookup"><span data-stu-id="2d60a-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="2d60a-228">これにより、[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) が別の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="2d60a-229">子を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="2d60a-230">これは、TermA が親で、TermA が子であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="2d60a-231">ドキュメントメモ</span><span class="sxs-lookup"><span data-stu-id="2d60a-231">Documentation notes</span></span>

<span data-ttu-id="2d60a-232">ここでは、Microsoft.SharePoint.Taxonomy Namespaceに記載されている分類について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="2d60a-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="2d60a-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="2d60a-234">ここでは、 [SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) の語彙のエンティティについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="2d60a-235">説明を追加する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="2d60a-236">カスタム プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d60a-236">Custom properties</span></span>

<span data-ttu-id="2d60a-237">読み取り専用ディクショナリから、現在の用語オブジェクトのカスタムプロパティオブジェクトのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="2d60a-238">カスタムプロパティは、[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に対して定義できるキー値のペアです。また、 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の詳細についても説明します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="2d60a-239">SharePoint では、propertyName を使用してカスタムプロパティのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="2d60a-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="2d60a-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="2d60a-241">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="2d60a-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="2d60a-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="2d60a-243">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) のカスタムプロパティを[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)と共に使用する必要があり、[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を再使用している場合はSharedCustomPropertyForTerm を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="2d60a-244">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="2d60a-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="2d60a-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="2d60a-246">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) のカスタムプロパティを [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)と共に使用する必要がなく、[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を再利用する場合は、LocalCustomPropertyForTermの下で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="2d60a-247">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="2d60a-248">データ プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d60a-248">Data properties</span></span>

<span data-ttu-id="2d60a-249">階層の各レベルで、用語や TermSet に特定のデータプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="2d60a-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="2d60a-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="2d60a-251">この機能を使用して、SharePoint のリストとライブラリで使用できる[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d60a-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="2d60a-252">この構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d60a-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="2d60a-253">ドメインと範囲</span><span class="sxs-lookup"><span data-stu-id="2d60a-253">Domain and range</span></span>

<span data-ttu-id="2d60a-254">下の表は、SharePoint の分類ボキャブラリのドメインと範囲を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d60a-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="2d60a-255">述語/動詞</span><span class="sxs-lookup"><span data-stu-id="2d60a-255">Predicates/verb</span></span>|<span data-ttu-id="2d60a-256">意味</span><span class="sxs-lookup"><span data-stu-id="2d60a-256">Meaning</span></span>|<span data-ttu-id="2d60a-257">ドメイン</span><span class="sxs-lookup"><span data-stu-id="2d60a-257">Domain</span></span>|<span data-ttu-id="2d60a-258">範囲</span><span class="sxs-lookup"><span data-stu-id="2d60a-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="2d60a-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-259">inTermSet</span></span>|<span data-ttu-id="2d60a-260">用語セットで</span><span class="sxs-lookup"><span data-stu-id="2d60a-260">In term set</span></span>|<span data-ttu-id="2d60a-261">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-261">Term</span></span>|<span data-ttu-id="2d60a-262">用語セット</span><span class="sxs-lookup"><span data-stu-id="2d60a-262">Term Set</span></span>|
<span data-ttu-id="2d60a-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="2d60a-263">inTermGroup</span></span>|<span data-ttu-id="2d60a-264">用語グループ</span><span class="sxs-lookup"><span data-stu-id="2d60a-264">In term group</span></span>|<span data-ttu-id="2d60a-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-265">TermSet</span></span>|<span data-ttu-id="2d60a-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="2d60a-266">TermGroup</span></span>|
<span data-ttu-id="2d60a-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="2d60a-267">topLevelTermOf</span></span>|<span data-ttu-id="2d60a-268">は最上位の用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-268">Is Top Level Term Of</span></span>|<span data-ttu-id="2d60a-269">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-269">Term</span></span>|<span data-ttu-id="2d60a-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-270">TermSet</span></span>|
<span data-ttu-id="2d60a-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="2d60a-271">hasTopLevelTerm</span></span>|<span data-ttu-id="2d60a-272">最上位の用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-272">Has top level term</span></span>|<span data-ttu-id="2d60a-273">用語セット</span><span class="sxs-lookup"><span data-stu-id="2d60a-273">Term Set</span></span>|<span data-ttu-id="2d60a-274">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-274">Term</span></span>|
<span data-ttu-id="2d60a-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="2d60a-275">termSetName</span></span>|<span data-ttu-id="2d60a-276">用語セットに名前がある</span><span class="sxs-lookup"><span data-stu-id="2d60a-276">Term set has Name</span></span>|<span data-ttu-id="2d60a-277">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-277">Term</span></span>|<span data-ttu-id="2d60a-278">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="2d60a-278">Plain literal</span></span>|
<span data-ttu-id="2d60a-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-279">defaultLabel</span></span>|<span data-ttu-id="2d60a-280">Term に既定のラベルがある</span><span class="sxs-lookup"><span data-stu-id="2d60a-280">Term has default label</span></span>|<span data-ttu-id="2d60a-281">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-281">Term</span></span>|<span data-ttu-id="2d60a-282">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="2d60a-282">Plain literal</span></span>|
<span data-ttu-id="2d60a-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="2d60a-283">otherLabel</span></span>|<span data-ttu-id="2d60a-284">"その他" というラベル</span><span class="sxs-lookup"><span data-stu-id="2d60a-284">Term has other label</span></span>|<span data-ttu-id="2d60a-285">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-285">Term</span></span>|<span data-ttu-id="2d60a-286">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="2d60a-286">Plain literal</span></span>|
<span data-ttu-id="2d60a-287">PropertyName</span><span class="sxs-lookup"><span data-stu-id="2d60a-287">propertyName</span></span>|<span data-ttu-id="2d60a-288">プロパティラベルあり</span><span class="sxs-lookup"><span data-stu-id="2d60a-288">Has Property Label</span></span>|<span data-ttu-id="2d60a-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="2d60a-290">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="2d60a-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="2d60a-291">説明</span><span class="sxs-lookup"><span data-stu-id="2d60a-291">description</span></span>|<span data-ttu-id="2d60a-292">説明がある</span><span class="sxs-lookup"><span data-stu-id="2d60a-292">Has Description</span></span>|<span data-ttu-id="2d60a-293">すべて</span><span class="sxs-lookup"><span data-stu-id="2d60a-293">All</span></span>|<span data-ttu-id="2d60a-294">プレーンリテラル</span><span class="sxs-lookup"><span data-stu-id="2d60a-294">Plain literal</span></span>|
|<span data-ttu-id="2d60a-295">親</span><span class="sxs-lookup"><span data-stu-id="2d60a-295">parent</span></span>|<span data-ttu-id="2d60a-296">親がある</span><span class="sxs-lookup"><span data-stu-id="2d60a-296">Has parent</span></span>|<span data-ttu-id="2d60a-297">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-297">Term</span></span>|<span data-ttu-id="2d60a-298">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-298">Term</span></span>|
|<span data-ttu-id="2d60a-299">子</span><span class="sxs-lookup"><span data-stu-id="2d60a-299">child</span></span>|<span data-ttu-id="2d60a-300">子がある</span><span class="sxs-lookup"><span data-stu-id="2d60a-300">Has Child</span></span>|<span data-ttu-id="2d60a-301">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-301">Term</span></span>|<span data-ttu-id="2d60a-302">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-302">Term</span></span>|
|<span data-ttu-id="2d60a-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="2d60a-303">isAvailableForTagging</span></span>|<span data-ttu-id="2d60a-304">タグ付けで使用可能</span><span class="sxs-lookup"><span data-stu-id="2d60a-304">Is available for tagging</span></span>|<span data-ttu-id="2d60a-305">用語、用語セット</span><span class="sxs-lookup"><span data-stu-id="2d60a-305">Term, Term Set</span></span>|<span data-ttu-id="2d60a-306">ブール値</span><span class="sxs-lookup"><span data-stu-id="2d60a-306">Boolean</span></span>|
|<span data-ttu-id="2d60a-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="2d60a-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="2d60a-308">共有カスタムプロパティがあります</span><span class="sxs-lookup"><span data-stu-id="2d60a-308">Has shared custom property</span></span>|<span data-ttu-id="2d60a-309">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-309">Term</span></span>|<span data-ttu-id="2d60a-310">Boolean、string、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="2d60a-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="2d60a-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="2d60a-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="2d60a-312">ローカルのカスタムプロパティがあります</span><span class="sxs-lookup"><span data-stu-id="2d60a-312">Has local custom property</span></span>|<span data-ttu-id="2d60a-313">用語</span><span class="sxs-lookup"><span data-stu-id="2d60a-313">Term</span></span>|<span data-ttu-id="2d60a-314">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="2d60a-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="2d60a-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="2d60a-316">Custom プロパティがある</span><span class="sxs-lookup"><span data-stu-id="2d60a-316">Has Custom Property</span></span>|<span data-ttu-id="2d60a-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="2d60a-317">TermSet</span></span>|<span data-ttu-id="2d60a-318">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="2d60a-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="2d60a-319">[SKOS](https://www.w3.org/TR/skos-primer/)これは[SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) が許可されていない有効なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="2d60a-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="2d60a-320">階層冗長化-[SKOS](https://www.w3.org/TR/skos-primer/) 概念が複数の階層の概念に同時に関連付けられている います。ただし、sharepoint の分類項目：用語は、1つの sharepoint 分類：親しか持てませんので、用語の循環的な依存関係になり、それは許可されません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="2d60a-321">孤立した用語は、SharePoint の分類では許可されません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="2d60a-322">すべての sharepoint-taxonomy: 用語には、sharepoint-taxonomy:親を持つか、あるいはTermSetのsharepoint-taxonomy:topLevelTermOfである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d60a-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="2d60a-323">SharePoint の分類は、関連する関係をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2d60a-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="2d60a-324">SharePoint の分類では、2種類の階層関係 (sharepoint-taxonomy:親およびsharepoint-Taxonomy:子) のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="2d60a-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="2d60a-325">[SKOS](https://www.w3.org/TR/skos-primer/)とは異なり、SharePoint 分類のボキャブラリの階層関係は、同じTermSet内の用語を使用して作成する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="2d60a-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d60a-326">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d60a-326">See also</span></span>

[<span data-ttu-id="2d60a-327">SKOS ベースの形式を使用して用語セットをインポートする</span><span class="sxs-lookup"><span data-stu-id="2d60a-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

