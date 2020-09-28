---
title: SharePoint 分類の SKOS 形式リファレンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SharePoint 分類の SKOS 形式リファレンス
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296081"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="df2b8-103">SharePoint 分類の SKOS 形式リファレンス</span><span class="sxs-lookup"><span data-stu-id="df2b8-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="df2b8-104">この記事には、 [SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) を表すために使用される RDF ボキャブラリが含まれており、 [skos](https://www.w3.org/TR/skos-primer/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="df2b8-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="df2b8-105">この RDF 構文のシリアル化では、RDF [タートル](https://www.w3.org/TR/turtle/)を使用します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="df2b8-106">次の表は、 [SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)の語彙に相当する[skos](https://www.w3.org/TR/skos-primer/)を示しています。</span><span class="sxs-lookup"><span data-stu-id="df2b8-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="df2b8-107">SharePoint では、SharePoint 分類が対応していない [Skos](https://www.w3.org/TR/skos-primer/) 値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="df2b8-108">SharePoint 分類</span><span class="sxs-lookup"><span data-stu-id="df2b8-108">SharePoint taxonomy</span></span>|<span data-ttu-id="df2b8-109">SKOS の同等物</span><span class="sxs-lookup"><span data-stu-id="df2b8-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="df2b8-110">sharepoint-分類: 用語</span><span class="sxs-lookup"><span data-stu-id="df2b8-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="df2b8-111">skos: 概念</span><span class="sxs-lookup"><span data-stu-id="df2b8-111">skos:Concept</span></span>|
|<span data-ttu-id="df2b8-112">sharepoint-分類: 用語セット</span><span class="sxs-lookup"><span data-stu-id="df2b8-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="df2b8-113">skos: ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="df2b8-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="df2b8-114">sharepoint-分類: inTermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="df2b8-115">skos: inScheme</span><span class="sxs-lookup"><span data-stu-id="df2b8-115">skos:inScheme</span></span>|
|<span data-ttu-id="df2b8-116">sharepoint-分類: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="df2b8-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="df2b8-117">skos: hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="df2b8-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="df2b8-118">sharepoint-分類: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="df2b8-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="df2b8-119">skos: topConceptOf</span><span class="sxs-lookup"><span data-stu-id="df2b8-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="df2b8-120">sharepoint-分類: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="df2b8-121">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-121">skos:prefLabel</span></span>|
|<span data-ttu-id="df2b8-122">sharepoint-分類: termSetName</span><span class="sxs-lookup"><span data-stu-id="df2b8-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="df2b8-123">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-123">skos:prefLabel</span></span>|
|<span data-ttu-id="df2b8-124">sharepoint-分類: propertyName</span><span class="sxs-lookup"><span data-stu-id="df2b8-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="df2b8-125">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-125">skos:prefLabel</span></span>|
|<span data-ttu-id="df2b8-126">sharepoint-分類: otherLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="df2b8-127">skos: altLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-127">skos:altLabel</span></span>|
|<span data-ttu-id="df2b8-128">sharepoint-分類: 説明</span><span class="sxs-lookup"><span data-stu-id="df2b8-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="df2b8-129">skos: definition</span><span class="sxs-lookup"><span data-stu-id="df2b8-129">skos:definition</span></span>|
|<span data-ttu-id="df2b8-130">sharepoint-分類: 親</span><span class="sxs-lookup"><span data-stu-id="df2b8-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="df2b8-131">skos: より幅広い</span><span class="sxs-lookup"><span data-stu-id="df2b8-131">skos:broader</span></span>|
|<span data-ttu-id="df2b8-132">sharepoint-分類: 子</span><span class="sxs-lookup"><span data-stu-id="df2b8-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="df2b8-133">skos: 狭い</span><span class="sxs-lookup"><span data-stu-id="df2b8-133">skos:narrower</span></span>|

<span data-ttu-id="df2b8-134">次の表に、 [OWL](https://www.w3.org/TR/owl2-primer/)から派生した SharePoint 分類ボキャブラリのエンティティを示します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="df2b8-135">SharePoint 分類ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="df2b8-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="df2b8-136">OWL から派生したもの</span><span class="sxs-lookup"><span data-stu-id="df2b8-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="df2b8-137">sharepoint-分類: Is持ち Forタグ</span><span class="sxs-lookup"><span data-stu-id="df2b8-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="df2b8-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="df2b8-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="df2b8-139">sharepoint-分類: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="df2b8-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="df2b8-140">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="df2b8-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="df2b8-141">sharepoint-分類: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="df2b8-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="df2b8-142">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="df2b8-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="df2b8-143">sharepoint-分類: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="df2b8-144">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="df2b8-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="df2b8-145">SharePoint 分類ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="df2b8-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="df2b8-146">分類は、正式な分類システムです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="df2b8-147">分類は、何かを説明する単語、ラベル、用語をグループ化し、そのグループを階層に配置します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="df2b8-148">**sharepoint-分類: 用語**</span><span class="sxs-lookup"><span data-stu-id="df2b8-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="df2b8-149">管理メタデータ階層内の Term またはキーワードを表します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="df2b8-150">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は、SharePoint[用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の原子単位です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="df2b8-151">各[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は、 [Termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)に属する[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="df2b8-152">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="df2b8-153">[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内に Compulsorily と[いう用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が存在する。</span><span class="sxs-lookup"><span data-stu-id="df2b8-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="df2b8-154">DefaultLabel は、視覚的表現に表示される [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) の名前です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="df2b8-155">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を定義するために必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="df2b8-156">sharepoint-分類: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="df2b8-157">sharepoint-分類: inTermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="df2b8-158">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="df2b8-159">同じ[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属する[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が存在する別の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="df2b8-160">複数の子 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)がありますが、1つの親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="df2b8-161">親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) が定義されていない (TopLevelTermOf a [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の場合)。</span><span class="sxs-lookup"><span data-stu-id="df2b8-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="df2b8-162">[用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語ごとに1つの defaultlabel を用意します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="df2b8-163">親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が含まれていない場合、または TopLevelTermOf a [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)でない場合は、存在しません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="df2b8-164">同じ階層レベルに一意の defaultLabel のみを設定します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="df2b8-165">**sharepoint-分類: 用語セット**</span><span class="sxs-lookup"><span data-stu-id="df2b8-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="df2b8-166">"用語セット" と呼ばれる用語オブジェクトの階層構造またはフラットセットを表します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="df2b8-167">名前からわかるように、用語セットは一連の [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="df2b8-168">[用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)内の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は、[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="df2b8-169">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は単独では存在できません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="df2b8-170">[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="df2b8-171">[Termsets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) は、 [termsets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)に論理的にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="df2b8-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="df2b8-172">[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)を定義するために必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="df2b8-173">sharepoint-分類: termSetName</span><span class="sxs-lookup"><span data-stu-id="df2b8-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="df2b8-174">指定された termSetName が [Termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)内で一意ではない場合、sharepoint は、termSetName の一意性を維持するために、名前の末尾に数字を追加します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="df2b8-175">**sharepoint-分類: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="df2b8-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="df2b8-176">SharePoint では、このプロパティを使用して[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の最上位[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)をマップします。これは、[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の階層へのエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="df2b8-177">これは、sharepoint 分類: topLevelTermOf への逆の関係です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="df2b8-178">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="df2b8-179">親[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)のトップレベル[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="df2b8-180">**sharepoint-分類: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="df2b8-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="df2b8-181">Sharepoint-分類: topLevelTermOf は、hasTopLevelTerm の逆の方法です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="df2b8-182">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="df2b8-183">**sharepoint-分類: inTermSet**</span><span class="sxs-lookup"><span data-stu-id="df2b8-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="df2b8-184">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)にマップするのに使用します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="df2b8-185">1つの[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内にのみ存在する[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="df2b8-186">SharePoint [では、用語を定義](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)するときにこのプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="df2b8-187">必要なラベル</span><span class="sxs-lookup"><span data-stu-id="df2b8-187">Required labels</span></span>

<span data-ttu-id="df2b8-188">管理されたメタデータの使用を開始する前に、組織で慎重に計画する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="df2b8-189">必要な計画の量は、分類の正式な方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="df2b8-190">また、メタデータをどの程度制御するかによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="df2b8-191">階層の各レベルで、用語または用語セットに対して必要な lables を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="df2b8-192">用語には、既定の言語で1つ以上のラベルを含めることができます。また、既定以外の言語では、0個以上のラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="df2b8-193">用語に言語のラベルが含まれている場合、ラベルの1つは既定のラベルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="df2b8-194">**sharepoint-分類: defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="df2b8-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="df2b8-195">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の必須パラメーターである[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)には、この既定の字句ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="df2b8-196">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を視覚的に表すために使用します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="df2b8-197">DefaultLabel を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="df2b8-198">DefaultLabel には、文字列と言語タグの2つの部分が含まれています。</span><span class="sxs-lookup"><span data-stu-id="df2b8-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="df2b8-199">言語は、 [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 作業言語のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="df2b8-200">DefaultLabel は、同じ階層レベルで、同じ[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内のすべての[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="df2b8-201">**sharepoint-分類: termSetName**</span><span class="sxs-lookup"><span data-stu-id="df2b8-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="df2b8-202">現在の用語セットオブジェクトの名前を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="df2b8-203">これは、 [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の字句ラベルで、 [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の作業言語になります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="df2b8-204">これは、 [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の必須パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="df2b8-205">[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)を視覚的に表すために使用します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="df2b8-206">TermSetName を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="df2b8-207">**sharepoint-分類: propertyName**</span><span class="sxs-lookup"><span data-stu-id="df2b8-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="df2b8-208">現在の用語セットオブジェクトのプロパティ名を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="df2b8-209">これは、 [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 作業言語では、sharepoint 分類: sharedcustompropertyforterm、Sharepoint-CustomPropertyForTermSet: localcustompropertyforterm、および sharepoint-分類: の字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="df2b8-210">Sharepoint 分類: propertyName は、CustomProperty のキーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="df2b8-211">PropetyName を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="df2b8-212">オプションのラベル</span><span class="sxs-lookup"><span data-stu-id="df2b8-212">Optional labels</span></span>

<span data-ttu-id="df2b8-213">また、分類にオプションのラベルを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="df2b8-214">**sharepoint-分類: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="df2b8-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="df2b8-215">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の代替の字句ラベルです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="df2b8-216">OtherLabel を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="df2b8-217">セマンティック関係</span><span class="sxs-lookup"><span data-stu-id="df2b8-217">Semantic relationships</span></span>

<span data-ttu-id="df2b8-218">分類には階層型と単純な "関連用語" という関連性のある関係がありますが、"セマンティックリレーションシップ" またはカスタム作成されたリレーションシップを持つものがあります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="df2b8-219">**sharepoint-分類: 親**</span><span class="sxs-lookup"><span data-stu-id="df2b8-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="df2b8-220">これは、ある [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を別の [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="df2b8-221">[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)には、[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の最上位の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を指定することもできますが、その場合には、親の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="df2b8-222">親を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="df2b8-223">これは、TermA1 に親 TermA があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="df2b8-224">TermA1 は、TermA の子でもあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="df2b8-225">親子関係は inversible の関係です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="df2b8-226">**sharepoint-分類: 子**</span><span class="sxs-lookup"><span data-stu-id="df2b8-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="df2b8-227">オブジェクトには、1つ以上の子用語セットインスタンスが含まれています。これらには、TermSets プロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="df2b8-228">このクラスには、新しい子用語セットオブジェクトを作成するためのメソッドも用意されています。</span><span class="sxs-lookup"><span data-stu-id="df2b8-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="df2b8-229">子用語および用語セットインスタンスを編集するためのアクセス許可は、グループで指定されています。</span><span class="sxs-lookup"><span data-stu-id="df2b8-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="df2b8-230">これは、ある [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を別の [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="df2b8-231">子を定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="df2b8-232">これは、TermA に子 TermA1 があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="df2b8-233">また、TermA が TermA1 の親子関係の親であることも意味しています。 inversible の関係です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="df2b8-234">ドキュメントのメモ</span><span class="sxs-lookup"><span data-stu-id="df2b8-234">Documentation notes</span></span>

<span data-ttu-id="df2b8-235">このセクションでは、Microsoft SharePoint の分類の名前空間に詳細が記載されている分類について説明します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="df2b8-236">**sharepoint-分類: 説明**</span><span class="sxs-lookup"><span data-stu-id="df2b8-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="df2b8-237">これは、 [SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) ボキャブラリエンティティの詳細な説明です。</span><span class="sxs-lookup"><span data-stu-id="df2b8-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="df2b8-238">説明を追加するための構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="df2b8-239">カスタム プロパティ</span><span class="sxs-lookup"><span data-stu-id="df2b8-239">Custom properties</span></span>

<span data-ttu-id="df2b8-240">読み取り専用の辞書から、現在の用語オブジェクトのカスタムプロパティオブジェクトのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="df2b8-241">カスタムプロパティは、 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に対して定義できるキーと値の組み合わせであり、 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の説明にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="df2b8-242">SharePoint は、propertyName のヘルプを使用して、カスタムプロパティのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="df2b8-243">**sharepoint-分類: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="df2b8-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="df2b8-244">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="df2b8-245">**sharepoint-分類: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="df2b8-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="df2b8-246">用語のカスタムプロパティを[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)と一緒に再利用[する必要が](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)ある場合は、[その用語を別の場所に](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)再利用するときに、sharedcustompropertyforterm の下で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="df2b8-247">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="df2b8-248">**sharepoint-分類: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="df2b8-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="df2b8-249">[用語の](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)カスタムプロパティを[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)と一緒に再利用する必要がない場合は、その用語を別[の場所に](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)再利用するときに、localcustompropertyforterm の下に用語を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2b8-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="df2b8-250">これを定義する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="df2b8-251">データプロパティ</span><span class="sxs-lookup"><span data-stu-id="df2b8-251">Data properties</span></span>

<span data-ttu-id="df2b8-252">階層の各レベルで、用語または用語セットに特定のデータプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="df2b8-253">**sharepoint-分類: Is持ち Forタグ**</span><span class="sxs-lookup"><span data-stu-id="df2b8-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="df2b8-254">これを使用して、SharePoint リストとライブラリで使用可能な [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) を指定します。</span><span class="sxs-lookup"><span data-stu-id="df2b8-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="df2b8-255">この場合の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="df2b8-256">ドメインと範囲</span><span class="sxs-lookup"><span data-stu-id="df2b8-256">Domain and range</span></span>

<span data-ttu-id="df2b8-257">次の表は、SharePoint 分類の語彙のドメインと範囲を示しています。</span><span class="sxs-lookup"><span data-stu-id="df2b8-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="df2b8-258">述語/動詞</span><span class="sxs-lookup"><span data-stu-id="df2b8-258">Predicates/verb</span></span>|<span data-ttu-id="df2b8-259">意味</span><span class="sxs-lookup"><span data-stu-id="df2b8-259">Meaning</span></span>|<span data-ttu-id="df2b8-260">ドメイン</span><span class="sxs-lookup"><span data-stu-id="df2b8-260">Domain</span></span>|<span data-ttu-id="df2b8-261">範囲</span><span class="sxs-lookup"><span data-stu-id="df2b8-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="df2b8-262">inTermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-262">inTermSet</span></span>|<span data-ttu-id="df2b8-263">用語セット内</span><span class="sxs-lookup"><span data-stu-id="df2b8-263">In term set</span></span>|<span data-ttu-id="df2b8-264">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-264">Term</span></span>|<span data-ttu-id="df2b8-265">用語セット</span><span class="sxs-lookup"><span data-stu-id="df2b8-265">Term Set</span></span>|
<span data-ttu-id="df2b8-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="df2b8-266">inTermGroup</span></span>|<span data-ttu-id="df2b8-267">用語グループ</span><span class="sxs-lookup"><span data-stu-id="df2b8-267">In term group</span></span>|<span data-ttu-id="df2b8-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-268">TermSet</span></span>|<span data-ttu-id="df2b8-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="df2b8-269">TermGroup</span></span>|
<span data-ttu-id="df2b8-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="df2b8-270">topLevelTermOf</span></span>|<span data-ttu-id="df2b8-271">トップレベルの用語</span><span class="sxs-lookup"><span data-stu-id="df2b8-271">Is Top Level Term Of</span></span>|<span data-ttu-id="df2b8-272">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-272">Term</span></span>|<span data-ttu-id="df2b8-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-273">TermSet</span></span>|
<span data-ttu-id="df2b8-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="df2b8-274">hasTopLevelTerm</span></span>|<span data-ttu-id="df2b8-275">最上位レベルの用語</span><span class="sxs-lookup"><span data-stu-id="df2b8-275">Has top level term</span></span>|<span data-ttu-id="df2b8-276">用語セット</span><span class="sxs-lookup"><span data-stu-id="df2b8-276">Term Set</span></span>|<span data-ttu-id="df2b8-277">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-277">Term</span></span>|
<span data-ttu-id="df2b8-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="df2b8-278">termSetName</span></span>|<span data-ttu-id="df2b8-279">用語セットの名前</span><span class="sxs-lookup"><span data-stu-id="df2b8-279">Term set has Name</span></span>|<span data-ttu-id="df2b8-280">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-280">Term</span></span>|<span data-ttu-id="df2b8-281">プレーンなリテラル</span><span class="sxs-lookup"><span data-stu-id="df2b8-281">Plain literal</span></span>|
<span data-ttu-id="df2b8-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-282">defaultLabel</span></span>|<span data-ttu-id="df2b8-283">用語に既定のラベルがあります</span><span class="sxs-lookup"><span data-stu-id="df2b8-283">Term has default label</span></span>|<span data-ttu-id="df2b8-284">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-284">Term</span></span>|<span data-ttu-id="df2b8-285">プレーンなリテラル</span><span class="sxs-lookup"><span data-stu-id="df2b8-285">Plain literal</span></span>|
<span data-ttu-id="df2b8-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="df2b8-286">otherLabel</span></span>|<span data-ttu-id="df2b8-287">その他のラベルがある用語</span><span class="sxs-lookup"><span data-stu-id="df2b8-287">Term has other label</span></span>|<span data-ttu-id="df2b8-288">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-288">Term</span></span>|<span data-ttu-id="df2b8-289">プレーンなリテラル</span><span class="sxs-lookup"><span data-stu-id="df2b8-289">Plain literal</span></span>|
<span data-ttu-id="df2b8-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="df2b8-290">propertyName</span></span>|<span data-ttu-id="df2b8-291">プロパティラベルあり</span><span class="sxs-lookup"><span data-stu-id="df2b8-291">Has Property Label</span></span>|<span data-ttu-id="df2b8-292">SharedCustomPropertyForTerm、LocalCustomPropertyForTerm、CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="df2b8-293">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="df2b8-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="df2b8-294">説明</span><span class="sxs-lookup"><span data-stu-id="df2b8-294">description</span></span>|<span data-ttu-id="df2b8-295">説明あり</span><span class="sxs-lookup"><span data-stu-id="df2b8-295">Has Description</span></span>|<span data-ttu-id="df2b8-296">すべて</span><span class="sxs-lookup"><span data-stu-id="df2b8-296">All</span></span>|<span data-ttu-id="df2b8-297">プレーンなリテラル</span><span class="sxs-lookup"><span data-stu-id="df2b8-297">Plain literal</span></span>|
|<span data-ttu-id="df2b8-298">親</span><span class="sxs-lookup"><span data-stu-id="df2b8-298">parent</span></span>|<span data-ttu-id="df2b8-299">親がある</span><span class="sxs-lookup"><span data-stu-id="df2b8-299">Has parent</span></span>|<span data-ttu-id="df2b8-300">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-300">Term</span></span>|<span data-ttu-id="df2b8-301">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-301">Term</span></span>|
|<span data-ttu-id="df2b8-302">子供</span><span class="sxs-lookup"><span data-stu-id="df2b8-302">child</span></span>|<span data-ttu-id="df2b8-303">子がある</span><span class="sxs-lookup"><span data-stu-id="df2b8-303">Has Child</span></span>|<span data-ttu-id="df2b8-304">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-304">Term</span></span>|<span data-ttu-id="df2b8-305">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-305">Term</span></span>|
|<span data-ttu-id="df2b8-306">Is持ち Forタグ</span><span class="sxs-lookup"><span data-stu-id="df2b8-306">isAvailableForTagging</span></span>|<span data-ttu-id="df2b8-307">タグ付けに使用可能</span><span class="sxs-lookup"><span data-stu-id="df2b8-307">Is available for tagging</span></span>|<span data-ttu-id="df2b8-308">用語、用語セット</span><span class="sxs-lookup"><span data-stu-id="df2b8-308">Term, Term Set</span></span>|<span data-ttu-id="df2b8-309">Boolean</span><span class="sxs-lookup"><span data-stu-id="df2b8-309">Boolean</span></span>|
|<span data-ttu-id="df2b8-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="df2b8-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="df2b8-311">共有されたカスタムプロパティがある</span><span class="sxs-lookup"><span data-stu-id="df2b8-311">Has shared custom property</span></span>|<span data-ttu-id="df2b8-312">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-312">Term</span></span>|<span data-ttu-id="df2b8-313">Boolean、string、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="df2b8-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="df2b8-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="df2b8-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="df2b8-315">ローカルカスタムプロパティがある</span><span class="sxs-lookup"><span data-stu-id="df2b8-315">Has local custom property</span></span>|<span data-ttu-id="df2b8-316">Term</span><span class="sxs-lookup"><span data-stu-id="df2b8-316">Term</span></span>|<span data-ttu-id="df2b8-317">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="df2b8-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="df2b8-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="df2b8-319">カスタムプロパティあり</span><span class="sxs-lookup"><span data-stu-id="df2b8-319">Has Custom Property</span></span>|<span data-ttu-id="df2b8-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="df2b8-320">TermSet</span></span>|<span data-ttu-id="df2b8-321">Boolean、String、Integer、Decimal、Double</span><span class="sxs-lookup"><span data-stu-id="df2b8-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="df2b8-322">[SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)で許可されていない、 [skos](https://www.w3.org/TR/skos-primer/)の有効なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2b8-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="df2b8-323">階層的な冗長性- [Skos](https://www.w3.org/TR/skos-primer/) の概念は、複数のより広範な概念に同時にアタッチできますが、sharepoint の分類に含めることができるのは1つの sharepoint 分類だけであり、そのため、用語の循環依存関係も許可されません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="df2b8-324">孤立した用語は SharePoint 分類では許可されていません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="df2b8-325">すべての sharepoint 分類: 用語には、sharepoint の分類を設定する必要があります: 親であるか、sharepoint の分類である必要があります: topLevelTermOf a 用語セット。</span><span class="sxs-lookup"><span data-stu-id="df2b8-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="df2b8-326">SharePoint 分類は関連関係をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="df2b8-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="df2b8-327">SharePoint の分類では、2種類の階層関係のみが許可されます。 sharepoint 分類: 親と sharepoint の分類: 子。</span><span class="sxs-lookup"><span data-stu-id="df2b8-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="df2b8-328">[Skos](https://www.w3.org/TR/skos-primer/)とは異なり、SharePoint 分類語彙の階層関係は、同じ用語セット内の用語でのみ確立できます。</span><span class="sxs-lookup"><span data-stu-id="df2b8-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="df2b8-329">関連項目</span><span class="sxs-lookup"><span data-stu-id="df2b8-329">See also</span></span>

[<span data-ttu-id="df2b8-330">SKOS ベースの形式を使用して用語セットをインポートする</span><span class="sxs-lookup"><span data-stu-id="df2b8-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

