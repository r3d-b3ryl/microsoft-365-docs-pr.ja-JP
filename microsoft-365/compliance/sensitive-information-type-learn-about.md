---
title: 機密情報の種類の詳細
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
ms.openlocfilehash: 896a529d67faddb45b2672ca077f5a8e3b19827e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933083"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="2ed79-102">機密情報の種類の詳細</span><span class="sxs-lookup"><span data-stu-id="2ed79-102">Learn about sensitive information types</span></span>

<span data-ttu-id="2ed79-103">組織の管理下にある機密性の高いアイテムの特定と分類は、情報保護の分野の最初 [のステップです](protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="2ed79-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="2ed79-104">Microsoft 365 には、分類可能なアイテムを識別する 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2ed79-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="2ed79-105">ユーザーが手動で行う</span><span class="sxs-lookup"><span data-stu-id="2ed79-105">manually by users</span></span>
- <span data-ttu-id="2ed79-106">機密情報の種類などの自動パターン認識</span><span class="sxs-lookup"><span data-stu-id="2ed79-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="2ed79-107">機械学習</span><span class="sxs-lookup"><span data-stu-id="2ed79-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="2ed79-108">機密情報の種類はパターン ベースの分類子です。</span><span class="sxs-lookup"><span data-stu-id="2ed79-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="2ed79-109">機密情報を識別するために、社会保障、クレジット カード、銀行口座番号などの機密情報を検出する場合は、「機密情報の種類」エンティティ定義 [を参照してください。](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="2ed79-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="2ed79-110">機密情報の種類は次の中で使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="2ed79-111">データ損失防止ポリシー</span><span class="sxs-lookup"><span data-stu-id="2ed79-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="2ed79-112">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="2ed79-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2ed79-113">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="2ed79-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="2ed79-114">通信コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2ed79-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="2ed79-115">自動ラベル付けポリシー</span><span class="sxs-lookup"><span data-stu-id="2ed79-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="2ed79-116">機密情報の種類の基本的な部分</span><span class="sxs-lookup"><span data-stu-id="2ed79-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="2ed79-117">機密情報の種類のエンティティは、次のフィールドで定義されます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="2ed79-118">name: 機密情報の種類の参照方法</span><span class="sxs-lookup"><span data-stu-id="2ed79-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="2ed79-119">description: 機密情報の種類が何を探しているのかを説明します</span><span class="sxs-lookup"><span data-stu-id="2ed79-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="2ed79-120">パターン: パターンは、機密情報の種類が検出する情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="2ed79-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="2ed79-121">次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-121">It consists of the following components</span></span>
    - <span data-ttu-id="2ed79-122">プライマリ要素 – 機密情報の種類が検索している主な要素。</span><span class="sxs-lookup"><span data-stu-id="2ed79-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="2ed79-123">正規表現 **には、チェックサム** 検証、キーワード リスト、キーワード ディクショナリ、または関数を使用 **できます**。</span><span class="sxs-lookup"><span data-stu-id="2ed79-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="2ed79-124">サポート要素 – マッチの信頼度を高めるのに役立つサポート 証拠として機能する要素。</span><span class="sxs-lookup"><span data-stu-id="2ed79-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="2ed79-125">たとえば、SSN 番号の近くにあるキーワード "SSN" です。</span><span class="sxs-lookup"><span data-stu-id="2ed79-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="2ed79-126">これは、チェックサム検証、キーワード リスト、キーワード ディクショナリを使用する場合と使用しない場合の正規表現です。</span><span class="sxs-lookup"><span data-stu-id="2ed79-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="2ed79-127">信頼度 - 信頼度 (高、中、低) は、プライマリ要素と共に検出されたサポート証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="2ed79-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="2ed79-128">アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="2ed79-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="2ed79-129">近接性 – プライマリ要素とサポート要素の間の文字数</span><span class="sxs-lookup"><span data-stu-id="2ed79-129">Proximity – Number of characters between primary and supporting element</span></span>

![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="2ed79-131">信頼度の詳細については、このビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed79-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="2ed79-132">機密情報の種類の例</span><span class="sxs-lookup"><span data-stu-id="2ed79-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="2ed79-133">アルゼンチンの国民識別番号 (DNI)</span><span class="sxs-lookup"><span data-stu-id="2ed79-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="2ed79-134">フォーマット</span><span class="sxs-lookup"><span data-stu-id="2ed79-134">Format</span></span>

<span data-ttu-id="2ed79-135">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2ed79-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2ed79-136">パターン</span><span class="sxs-lookup"><span data-stu-id="2ed79-136">Pattern</span></span>

<span data-ttu-id="2ed79-137">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2ed79-137">Eight digits:</span></span>
- <span data-ttu-id="2ed79-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2ed79-138">two digits</span></span>
- <span data-ttu-id="2ed79-139">ピリオド</span><span class="sxs-lookup"><span data-stu-id="2ed79-139">a period</span></span>
- <span data-ttu-id="2ed79-140">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2ed79-140">three digits</span></span>
- <span data-ttu-id="2ed79-141">ピリオド</span><span class="sxs-lookup"><span data-stu-id="2ed79-141">a period</span></span>
- <span data-ttu-id="2ed79-142">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2ed79-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2ed79-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2ed79-143">Checksum</span></span>

<span data-ttu-id="2ed79-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="2ed79-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="2ed79-145">定義</span><span class="sxs-lookup"><span data-stu-id="2ed79-145">Definition</span></span>

<span data-ttu-id="2ed79-146">DLP ポリシーは、約 300 文字以下の場合にこの種の機密情報が検出されたという中程度の信頼度を持っています。</span><span class="sxs-lookup"><span data-stu-id="2ed79-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2ed79-147">パターンに一Regex_argentina_national_idコンテンツを検索する正規表現。</span><span class="sxs-lookup"><span data-stu-id="2ed79-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2ed79-148">検索されたKeyword_argentina_national_id検索されます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ed79-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="2ed79-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="2ed79-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="2ed79-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="2ed79-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="2ed79-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="2ed79-152">ID</span><span class="sxs-lookup"><span data-stu-id="2ed79-152">Identity</span></span> 
- <span data-ttu-id="2ed79-153">Id の国民識別カード</span><span class="sxs-lookup"><span data-stu-id="2ed79-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="2ed79-154">DNI</span><span class="sxs-lookup"><span data-stu-id="2ed79-154">DNI</span></span> 
- <span data-ttu-id="2ed79-155">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="2ed79-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="2ed79-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="2ed79-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="2ed79-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="2ed79-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="2ed79-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="2ed79-158">Identidad</span></span> 
- <span data-ttu-id="2ed79-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="2ed79-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="2ed79-160">信頼度の詳細</span><span class="sxs-lookup"><span data-stu-id="2ed79-160">More on confidence levels</span></span>

<span data-ttu-id="2ed79-161">機密情報の種類のエンティティ定義では、信頼度は、プライマリ要素に加えて検出されるサポート証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="2ed79-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="2ed79-162">アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="2ed79-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="2ed79-163">たとえば、信頼度の高い一致では、主要素の近くに多くのサポート証拠が含まれるのに対し、信頼度の低い一致には近接する証拠はほとんど含めず、何も含めずに最も近い証拠が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ed79-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="2ed79-164">信頼度が高い場合は、最も少ない誤検知が返されますが、誤検知の数が多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ed79-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="2ed79-165">低または中程度の信頼度は、より多くの誤検知を返しますが、検出検出は少なからゼロです。</span><span class="sxs-lookup"><span data-stu-id="2ed79-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="2ed79-166">**低信頼** 度 : 値 65、一致したアイテムに含まれる検出検出は最も少なく、誤検知は最も少ない。</span><span class="sxs-lookup"><span data-stu-id="2ed79-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="2ed79-167">**中程度の** 信頼度 : 値 75、一致したアイテムには、平均的な誤検知と検出検出の量が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="2ed79-168">**高信頼** 度 : 値 85、一致したアイテムには、最も少ない誤検知が含まれますが、最も検出検出が多い。</span><span class="sxs-lookup"><span data-stu-id="2ed79-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="2ed79-169">高信頼度パターンは、低カウント (5 ~ 10) と高いカウント (20 以上) の低信頼度パターンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed79-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="2ed79-170">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="2ed79-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="2ed79-171">次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="2ed79-172">**UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="2ed79-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="2ed79-173">この方法では、正規表現、キーワード、キーワード辞書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="2ed79-174">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed79-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="2ed79-175">**EDM を使用する** データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="2ed79-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="2ed79-176">この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="2ed79-177">詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed79-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="2ed79-178">**PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="2ed79-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="2ed79-179">この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2ed79-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="2ed79-180">詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed79-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="2ed79-181">Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2ed79-181">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="2ed79-182">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="2ed79-182">Chinese (simplified)</span></span>
> - <span data-ttu-id="2ed79-183">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="2ed79-183">Chinese (traditional)</span></span>
> - <span data-ttu-id="2ed79-184">韓国語</span><span class="sxs-lookup"><span data-stu-id="2ed79-184">Korean</span></span>
> - <span data-ttu-id="2ed79-185">日本語</span><span class="sxs-lookup"><span data-stu-id="2ed79-185">Japanese</span></span>

><span data-ttu-id="2ed79-186">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ed79-186">This support is available for sensitive information types.</span></span> <span data-ttu-id="2ed79-187">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed79-187">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="2ed79-188">詳しくは、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ed79-188">For further information</span></span>
- [<span data-ttu-id="2ed79-189">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="2ed79-189">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="2ed79-190">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="2ed79-190">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="2ed79-191">PowerShell でカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="2ed79-191">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->