---
title: 機密情報の種類に関する詳細情報
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 90b545f60c68ac6b76509e14daf1258df66e1c63
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741534"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="d1a5f-102">機密情報の種類に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="d1a5f-102">Learn about sensitive information types</span></span>

<span data-ttu-id="d1a5f-103">組織の管理下にある機密性の高いアイテムを識別および分類する方法は、情報保護の分野の最初の [ステップです](protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="d1a5f-104">Microsoft 365 には、分類できるアイテムを識別する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="d1a5f-105">ユーザーが手動で行う</span><span class="sxs-lookup"><span data-stu-id="d1a5f-105">manually by users</span></span>
- <span data-ttu-id="d1a5f-106">機密情報の種類などの自動パターン認識</span><span class="sxs-lookup"><span data-stu-id="d1a5f-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="d1a5f-107">機械学習</span><span class="sxs-lookup"><span data-stu-id="d1a5f-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="d1a5f-108">機密情報の種類は、パターン ベースの分類子です。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="d1a5f-109">機密アイテムを識別するために、社会保障、クレジット カード、銀行口座番号などの機密情報を検出する場合は、「機密情報の種類エンティティ定義」 [を参照してください。](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="d1a5f-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="d1a5f-110">機密情報の種類は、</span><span class="sxs-lookup"><span data-stu-id="d1a5f-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="d1a5f-111">データ損失防止ポリシー</span><span class="sxs-lookup"><span data-stu-id="d1a5f-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="d1a5f-112">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="d1a5f-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="d1a5f-113">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="d1a5f-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="d1a5f-114">通信コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="d1a5f-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="d1a5f-115">自動ラベル付けポリシー</span><span class="sxs-lookup"><span data-stu-id="d1a5f-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="d1a5f-116">機密情報の種類の基本的な部分</span><span class="sxs-lookup"><span data-stu-id="d1a5f-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="d1a5f-117">すべての機密情報の種類エンティティは、次のフィールドで定義されます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="d1a5f-118">name: 機密情報の種類の参照方法</span><span class="sxs-lookup"><span data-stu-id="d1a5f-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="d1a5f-119">description: 機密情報の種類が何を探しているのかを説明します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="d1a5f-120">pattern: パターンは、機密情報の種類が検出する情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="d1a5f-121">このコンポーネントは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-121">It consists of the following components</span></span>
    - <span data-ttu-id="d1a5f-122">Primary 要素 – 機密情報の種類が探している主な要素。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="d1a5f-123">これは、チェックサム検証 **、** キーワード リスト、キーワード 辞書、または関数を含む正規表現と指定 **できます**。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="d1a5f-124">サポート要素 – 一致の信頼度を高めるのに役立つ証拠として機能する要素。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="d1a5f-125">たとえば、SSN 番号の近接にあるキーワード "SSN" です。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="d1a5f-126">これは、チェックサム検証、キーワード リスト、キーワード 辞書の付いた正規表現と指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="d1a5f-127">信頼度レベル - 信頼度レベル (高、中、低) は、主要素と共に検出された証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="d1a5f-128">アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="d1a5f-129">近接 – プライマリ要素とサポート要素の間の文字数</span><span class="sxs-lookup"><span data-stu-id="d1a5f-129">Proximity – Number of characters between primary and supporting element</span></span>

![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="d1a5f-131">このビデオの信頼度の詳細</span><span class="sxs-lookup"><span data-stu-id="d1a5f-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="d1a5f-132">機密情報の種類の例</span><span class="sxs-lookup"><span data-stu-id="d1a5f-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="d1a5f-133">アルゼンチンの国民 ID (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="d1a5f-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="d1a5f-134">フォーマット</span><span class="sxs-lookup"><span data-stu-id="d1a5f-134">Format</span></span>

<span data-ttu-id="d1a5f-135">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d1a5f-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="d1a5f-136">パターン</span><span class="sxs-lookup"><span data-stu-id="d1a5f-136">Pattern</span></span>

<span data-ttu-id="d1a5f-137">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="d1a5f-137">Eight digits:</span></span>
- <span data-ttu-id="d1a5f-138">2 桁</span><span class="sxs-lookup"><span data-stu-id="d1a5f-138">two digits</span></span>
- <span data-ttu-id="d1a5f-139">ピリオド</span><span class="sxs-lookup"><span data-stu-id="d1a5f-139">a period</span></span>
- <span data-ttu-id="d1a5f-140">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d1a5f-140">three digits</span></span>
- <span data-ttu-id="d1a5f-141">ピリオド</span><span class="sxs-lookup"><span data-stu-id="d1a5f-141">a period</span></span>
- <span data-ttu-id="d1a5f-142">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d1a5f-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d1a5f-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d1a5f-143">Checksum</span></span>

<span data-ttu-id="d1a5f-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="d1a5f-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="d1a5f-145">定義</span><span class="sxs-lookup"><span data-stu-id="d1a5f-145">Definition</span></span>

<span data-ttu-id="d1a5f-146">DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d1a5f-147">正規表現は、Regex_argentina_national_id一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d1a5f-148">このページのKeyword_argentina_national_idが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d1a5f-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="d1a5f-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="d1a5f-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="d1a5f-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="d1a5f-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="d1a5f-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="d1a5f-152">ID</span><span class="sxs-lookup"><span data-stu-id="d1a5f-152">Identity</span></span> 
- <span data-ttu-id="d1a5f-153">ID 国の ID カード</span><span class="sxs-lookup"><span data-stu-id="d1a5f-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="d1a5f-154">DNI</span><span class="sxs-lookup"><span data-stu-id="d1a5f-154">DNI</span></span> 
- <span data-ttu-id="d1a5f-155">NIC の国民登録</span><span class="sxs-lookup"><span data-stu-id="d1a5f-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="d1a5f-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="d1a5f-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="d1a5f-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="d1a5f-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="d1a5f-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="d1a5f-158">Identidad</span></span> 
- <span data-ttu-id="d1a5f-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="d1a5f-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="d1a5f-160">信頼度の詳細</span><span class="sxs-lookup"><span data-stu-id="d1a5f-160">More on confidence levels</span></span>

<span data-ttu-id="d1a5f-161">機密情報の種類のエンティティ定義では、信頼度 **は** 、主要素に加えて検出される証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="d1a5f-162">アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="d1a5f-163">たとえば、信頼度が高い一致には、主要要素の近接性に関するより多くの証拠が含まれるのに対し、信頼度が低い一致には、近接する証拠はほとんど含めず、サポート証拠もほとんど含めずになります。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="d1a5f-164">高信頼度は、最も少ない誤検知を返しますが、より多くの誤検知が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="d1a5f-165">低または中程度の信頼度は、より多くの誤検知を返しますが、偽陰性を返す値は少なから 0 です。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="d1a5f-166">**低信頼** 度 : 値が 65 の場合、一致するアイテムには最も少ない偽陰性が含まれますが、最も誤検知が発生します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-166">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="d1a5f-167">低信頼度は、すべての低、中、および高信頼度の一致を返します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-167">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="d1a5f-168">**中程度の** 信頼度 : 値が 75 の場合、一致するアイテムには平均的な量の誤検知と偽陰性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-168">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="d1a5f-169">中程度の信頼度は、すべての中程度と高信頼度の一致を返します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-169">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="d1a5f-170">**高信頼**: 値が 85 の場合、一致するアイテムには、最も少ない誤検知が含まれますが、最も誤った負の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-170">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="d1a5f-171">高信頼は、高信頼度の一致のみを返します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-171">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="d1a5f-172">高信頼度レベルのパターンは、5 ~ 10 と低い信頼度パターンと、20 以上の高信頼度パターンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-172">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="d1a5f-173">数値ベースの信頼レベル (精度も知っている) を使用して定義されている既存のポリシーまたはカスタム機密情報の種類 (SIT) がある場合は、3 つの個別の信頼レベルに自動的にマップされます。セキュリティ @ コンプライアンス センター UI 全体で、低信頼性、中程度の信頼、および高い信頼性。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-173">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="d1a5f-174">76 ~ 100 の信頼レベルを持つ最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、高信頼度にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-174">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="d1a5f-175">66 ~ 75 の信頼レベルを持つ最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、中程度の信頼度にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-175">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="d1a5f-176">信頼度レベルが 65 以下の最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、低信頼度にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-176">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 
## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="d1a5f-177">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="d1a5f-177">Creating custom sensitive information types</span></span>

<span data-ttu-id="d1a5f-178">次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-178">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="d1a5f-179">**UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-179">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="d1a5f-180">この方法では、正規表現、キーワード、キーワード辞書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-180">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="d1a5f-181">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-181">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="d1a5f-182">**EDM を使用する** データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-182">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="d1a5f-183">この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-183">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="d1a5f-184">詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-184">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="d1a5f-185">**PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-185">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="d1a5f-186">この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-186">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="d1a5f-187">詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-187">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="d1a5f-188">Microsoft 365 サービスのデータ損失防止、Microsoft 365 サービスの Microsoft Information Protection、コミュニケーション コンプライアンス、情報ガバナンス、およびレコード管理内で、信頼性レベルの向上がすぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-188">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="d1a5f-189">Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-189">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="d1a5f-190">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="d1a5f-190">Chinese (simplified)</span></span>
> - <span data-ttu-id="d1a5f-191">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="d1a5f-191">Chinese (traditional)</span></span>
> - <span data-ttu-id="d1a5f-192">韓国語</span><span class="sxs-lookup"><span data-stu-id="d1a5f-192">Korean</span></span>
> - <span data-ttu-id="d1a5f-193">日本語</span><span class="sxs-lookup"><span data-stu-id="d1a5f-193">Japanese</span></span>

><span data-ttu-id="d1a5f-194">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-194">This support is available for sensitive information types.</span></span> <span data-ttu-id="d1a5f-195">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-195">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="d1a5f-196">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-196">For further information</span></span>
- [<span data-ttu-id="d1a5f-197">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="d1a5f-197">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="d1a5f-198">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="d1a5f-198">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="d1a5f-199">PowerShell でカスタム機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="d1a5f-199">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
