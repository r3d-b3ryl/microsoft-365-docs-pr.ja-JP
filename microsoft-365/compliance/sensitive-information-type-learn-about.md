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
description: この記事では、機密情報の種類の概要と、機密情報 (社会保障、クレジット カード、銀行口座番号など) を検出して機密情報を識別する方法について説明します。
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453623"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="8b562-103">機密情報の種類に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="8b562-103">Learn about sensitive information types</span></span>

<span data-ttu-id="8b562-104">組織の管理下にある機密性の高いアイテムを識別および分類する方法は、情報保護の分野の最初の [ステップです](./information-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8b562-104">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="8b562-105">Microsoft 365には、分類可能なアイテムを識別する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8b562-105">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="8b562-106">ユーザーが手動で行う</span><span class="sxs-lookup"><span data-stu-id="8b562-106">manually by users</span></span>
- <span data-ttu-id="8b562-107">機密情報の種類などの自動パターン認識</span><span class="sxs-lookup"><span data-stu-id="8b562-107">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="8b562-108">機械学習</span><span class="sxs-lookup"><span data-stu-id="8b562-108">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="8b562-109">機密情報の種類は、パターン ベースの分類子です。</span><span class="sxs-lookup"><span data-stu-id="8b562-109">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="8b562-110">機密アイテムを識別するために、社会保障、クレジット カード、銀行口座番号などの機密情報を検出する場合は、「機密情報の種類エンティティ定義」 [を参照してください。](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="8b562-110">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="8b562-111">機密情報の種類は、</span><span class="sxs-lookup"><span data-stu-id="8b562-111">Sensitive information types are used in</span></span>

- [<span data-ttu-id="8b562-112">データ損失防止ポリシー</span><span class="sxs-lookup"><span data-stu-id="8b562-112">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="8b562-113">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="8b562-113">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="8b562-114">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="8b562-114">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="8b562-115">インサイダー リスクの管理</span><span class="sxs-lookup"><span data-stu-id="8b562-115">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="8b562-116">通信コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="8b562-116">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="8b562-117">自動ラベル付けポリシー</span><span class="sxs-lookup"><span data-stu-id="8b562-117">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [<span data-ttu-id="8b562-118">プライバシー管理 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8b562-118">Privacy management (preview)</span></span>](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="8b562-119">機密情報の種類の基本的な部分</span><span class="sxs-lookup"><span data-stu-id="8b562-119">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="8b562-120">すべての機密情報の種類エンティティは、次のフィールドで定義されます。</span><span class="sxs-lookup"><span data-stu-id="8b562-120">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="8b562-121">name: 機密情報の種類の参照方法</span><span class="sxs-lookup"><span data-stu-id="8b562-121">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="8b562-122">description: 機密情報の種類が何を探しているのかを説明します。</span><span class="sxs-lookup"><span data-stu-id="8b562-122">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="8b562-123">pattern: パターンは、機密情報の種類が検出する情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b562-123">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="8b562-124">このコンポーネントは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8b562-124">It consists of the following components</span></span>
    - <span data-ttu-id="8b562-125">Primary 要素 – 機密情報の種類が探している主な要素。</span><span class="sxs-lookup"><span data-stu-id="8b562-125">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="8b562-126">これは、チェックサム検証 **、** キーワード リスト、キーワード 辞書、または関数を含む正規表現と指定 **できます**。</span><span class="sxs-lookup"><span data-stu-id="8b562-126">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="8b562-127">サポート要素 – 一致の信頼度を高めるのに役立つ証拠として機能する要素。</span><span class="sxs-lookup"><span data-stu-id="8b562-127">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="8b562-128">たとえば、SSN 番号の近接にあるキーワード "SSN" です。</span><span class="sxs-lookup"><span data-stu-id="8b562-128">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="8b562-129">これは、チェックサム検証、キーワード リスト、キーワード 辞書の付いた正規表現と指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b562-129">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="8b562-130">信頼度レベル - 信頼度レベル (高、中、低) は、主要素と共に検出された証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="8b562-130">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="8b562-131">アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="8b562-131">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="8b562-132">近接 – プライマリ要素とサポート要素の間の文字数</span><span class="sxs-lookup"><span data-stu-id="8b562-132">Proximity – Number of characters between primary and supporting element</span></span>

![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="8b562-134">このビデオの信頼度の詳細</span><span class="sxs-lookup"><span data-stu-id="8b562-134">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="8b562-135">機密情報の種類の例</span><span class="sxs-lookup"><span data-stu-id="8b562-135">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="8b562-136">アルゼンチンの国民 ID (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="8b562-136">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="8b562-137">フォーマット</span><span class="sxs-lookup"><span data-stu-id="8b562-137">Format</span></span>

<span data-ttu-id="8b562-138">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8b562-138">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="8b562-139">パターン</span><span class="sxs-lookup"><span data-stu-id="8b562-139">Pattern</span></span>

<span data-ttu-id="8b562-140">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8b562-140">Eight digits:</span></span>
- <span data-ttu-id="8b562-141">2 桁</span><span class="sxs-lookup"><span data-stu-id="8b562-141">two digits</span></span>
- <span data-ttu-id="8b562-142">ピリオド</span><span class="sxs-lookup"><span data-stu-id="8b562-142">a period</span></span>
- <span data-ttu-id="8b562-143">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8b562-143">three digits</span></span>
- <span data-ttu-id="8b562-144">ピリオド</span><span class="sxs-lookup"><span data-stu-id="8b562-144">a period</span></span>
- <span data-ttu-id="8b562-145">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8b562-145">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8b562-146">チェックサム</span><span class="sxs-lookup"><span data-stu-id="8b562-146">Checksum</span></span>

<span data-ttu-id="8b562-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="8b562-147">No</span></span>

### <a name="definition"></a><span data-ttu-id="8b562-148">定義</span><span class="sxs-lookup"><span data-stu-id="8b562-148">Definition</span></span>

<span data-ttu-id="8b562-149">DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。</span><span class="sxs-lookup"><span data-stu-id="8b562-149">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8b562-150">正規表現は、Regex_argentina_national_id一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8b562-150">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8b562-151">このページのKeyword_argentina_national_idが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8b562-151">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b562-152">キーワード</span><span class="sxs-lookup"><span data-stu-id="8b562-152">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="8b562-153">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="8b562-153">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="8b562-154">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="8b562-154">Argentina National Identity number</span></span> 
- <span data-ttu-id="8b562-155">ID</span><span class="sxs-lookup"><span data-stu-id="8b562-155">Identity</span></span> 
- <span data-ttu-id="8b562-156">ID 国の ID カード</span><span class="sxs-lookup"><span data-stu-id="8b562-156">Identification National Identity Card</span></span> 
- <span data-ttu-id="8b562-157">DNI</span><span class="sxs-lookup"><span data-stu-id="8b562-157">DNI</span></span> 
- <span data-ttu-id="8b562-158">NIC の国民登録</span><span class="sxs-lookup"><span data-stu-id="8b562-158">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="8b562-159">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="8b562-159">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="8b562-160">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="8b562-160">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="8b562-161">Identidad</span><span class="sxs-lookup"><span data-stu-id="8b562-161">Identidad</span></span> 
- <span data-ttu-id="8b562-162">Identificación</span><span class="sxs-lookup"><span data-stu-id="8b562-162">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="8b562-163">信頼度の詳細</span><span class="sxs-lookup"><span data-stu-id="8b562-163">More on confidence levels</span></span>

<span data-ttu-id="8b562-164">機密情報の種類のエンティティ定義では、信頼度 **は** 、主要素に加えて検出される証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="8b562-164">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="8b562-165">アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="8b562-165">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="8b562-166">たとえば、信頼度が高い一致には、主要要素の近接性に関するより多くの証拠が含まれるのに対し、信頼度が低い一致には、近接する証拠はほとんど含めず、サポート証拠もほとんど含めずになります。</span><span class="sxs-lookup"><span data-stu-id="8b562-166">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="8b562-167">高信頼度は、最も少ない誤検知を返しますが、より多くの誤検知が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b562-167">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="8b562-168">低または中程度の信頼度は、より多くの誤検知を返しますが、偽陰性を返す値は少なから 0 です。</span><span class="sxs-lookup"><span data-stu-id="8b562-168">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="8b562-169">**低信頼** 度 : 値が 65 の場合、一致するアイテムには最も少ない偽陰性が含まれますが、最も誤検知が発生します。</span><span class="sxs-lookup"><span data-stu-id="8b562-169">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="8b562-170">低信頼度は、すべての低、中、および高信頼度の一致を返します。</span><span class="sxs-lookup"><span data-stu-id="8b562-170">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="8b562-171">**中程度の** 信頼度 : 値が 75 の場合、一致するアイテムには平均的な量の誤検知と偽陰性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b562-171">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="8b562-172">中程度の信頼度は、すべての中程度と高信頼度の一致を返します。</span><span class="sxs-lookup"><span data-stu-id="8b562-172">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="8b562-173">**高信頼**: 値が 85 の場合、一致するアイテムには、最も少ない誤検知が含まれますが、最も誤った負の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b562-173">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="8b562-174">高信頼は、高信頼度の一致のみを返します。</span><span class="sxs-lookup"><span data-stu-id="8b562-174">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="8b562-175">高信頼度レベルのパターンは、5 ~ 10 と低い信頼度パターンと、20 以上の高信頼度パターンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b562-175">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="8b562-176">数値ベースの信頼レベル (精度も知っている) を使用して定義されている既存のポリシーまたはカスタム機密情報の種類 (SIT) がある場合は、3 つの個別の信頼レベルに自動的にマップされます。セキュリティ @ コンプライアンス センター UI 全体で、低信頼性、中程度の信頼、および高い信頼性。</span><span class="sxs-lookup"><span data-stu-id="8b562-176">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="8b562-177">76 ~ 100 の信頼レベルを持つ最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、高信頼度にマップされます。</span><span class="sxs-lookup"><span data-stu-id="8b562-177">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="8b562-178">66 ~ 75 の信頼レベルを持つ最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、中程度の信頼度にマップされます。</span><span class="sxs-lookup"><span data-stu-id="8b562-178">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="8b562-179">信頼度レベルが 65 以下の最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、低信頼度にマップされます。</span><span class="sxs-lookup"><span data-stu-id="8b562-179">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="8b562-180">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8b562-180">Creating custom sensitive information types</span></span>

<span data-ttu-id="8b562-181">次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8b562-181">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="8b562-182">**UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="8b562-182">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="8b562-183">この方法では、正規表現、キーワード、キーワード辞書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8b562-183">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="8b562-184">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b562-184">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="8b562-185">**EDM を使用する** データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="8b562-185">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="8b562-186">この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8b562-186">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="8b562-187">詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b562-187">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="8b562-188">**PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="8b562-188">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="8b562-189">この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8b562-189">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="8b562-190">詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b562-190">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="8b562-191">Microsoft 365 サービス、Microsoft 365 サービスの Microsoft Information Protection、コミュニケーション コンプライアンス、情報ガバナンス、レコード管理のデータ損失防止内ですぐに使用できる信頼性レベルの向上。</span><span class="sxs-lookup"><span data-stu-id="8b562-191">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="8b562-192">Microsoft 365Information Protection では、次の 2 バイト文字セット言語がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b562-192">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="8b562-193">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="8b562-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="8b562-194">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="8b562-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="8b562-195">韓国語</span><span class="sxs-lookup"><span data-stu-id="8b562-195">Korean</span></span>
> - <span data-ttu-id="8b562-196">日本語</span><span class="sxs-lookup"><span data-stu-id="8b562-196">Japanese</span></span>
> 
> <span data-ttu-id="8b562-197">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b562-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="8b562-198">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b562-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="8b562-199">中国語/日本語の文字と 1 バイト文字を含むパターンを検出する、または中国語/日本語と英語を含むパターンを検出するには、キーワードまたは正規表現の 2 つのバリエーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b562-199">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="8b562-200">たとえば、「机密的ドキュメント」のようなキーワードを検出するには、キーワードの 2 つのバリエーションを使用します。 1 つは日本語と英語のテキストの間にスペースがあり、もう 1 つは日本語と英語のテキストの間にスペースがありません。</span><span class="sxs-lookup"><span data-stu-id="8b562-200">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="8b562-201">したがって、SITに追加するキーワードは、"机密的 document" と "机密的document" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b562-201">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="8b562-202">同様に、"東京オリンピック2020" というフレーズを検出するには、"東京オリンピック 2020" と "東京オリンピック2020" の 2 つのバリエーションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b562-202">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="8b562-p118">2 バイトのハイフンまたは 2 バイトのピリオドを使用して正規表現を作成するときは、正規表現のハイフンまたはピリオドをエスケープするように、必ず両方の文字をエスケープしてください。参考までに、サンプルの正規表現を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8b562-p118">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="8b562-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="8b562-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="8b562-206">キーワード リストで単語一致の代わりに文字列一致を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8b562-206">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="8b562-207">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b562-207">For further information</span></span>
- [<span data-ttu-id="8b562-208">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="8b562-208">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="8b562-209">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8b562-209">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="8b562-210">PowerShell でカスタム機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8b562-210">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="8b562-211">機密情報の種類を使用してデータプライバシー規制に準拠する方法については、「データ[](../solutions/information-protection-deploy.md)プライバシー規制に関する情報保護を展開する (Microsoft 365 (aka.ms/m365dataprivacy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b562-211">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
