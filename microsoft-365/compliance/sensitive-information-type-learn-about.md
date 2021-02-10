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
ms.openlocfilehash: 91366e8f255d277d4d40de4c4cd3330283da718c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166452"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="e9b63-102">機密情報の種類に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="e9b63-102">Learn about sensitive information types</span></span>

<span data-ttu-id="e9b63-103">組織の管理下にある機密性の高いアイテムの特定と分類は、情報保護の分野の最初 [のステップです](protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b63-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="e9b63-104">Microsoft 365 には、分類可能なアイテムを識別する 3 つの方法が提供されています。</span><span class="sxs-lookup"><span data-stu-id="e9b63-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="e9b63-105">ユーザーが手動で実行する</span><span class="sxs-lookup"><span data-stu-id="e9b63-105">manually by users</span></span>
- <span data-ttu-id="e9b63-106">機密情報の種類などの自動パターン認識</span><span class="sxs-lookup"><span data-stu-id="e9b63-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="e9b63-107">機械学習</span><span class="sxs-lookup"><span data-stu-id="e9b63-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="e9b63-108">機密情報の種類はパターン ベースの分類子です。</span><span class="sxs-lookup"><span data-stu-id="e9b63-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="e9b63-109">機密情報を識別するために、社会保障、クレジット カード、銀行口座番号などの機密情報を検出する場合は、「機密情報の種類」エンティティ定義 [を参照してください。](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="e9b63-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="e9b63-110">機密情報の種類は次の中で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="e9b63-111">データ損失防止ポリシー</span><span class="sxs-lookup"><span data-stu-id="e9b63-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="e9b63-112">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="e9b63-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="e9b63-113">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="e9b63-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="e9b63-114">通信コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="e9b63-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="e9b63-115">自動ラベル付けポリシー</span><span class="sxs-lookup"><span data-stu-id="e9b63-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="e9b63-116">機密情報の種類の基本的な部分</span><span class="sxs-lookup"><span data-stu-id="e9b63-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="e9b63-117">機密情報の種類のエンティティは、次のフィールドで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="e9b63-118">name: 機密情報の種類の参照方法</span><span class="sxs-lookup"><span data-stu-id="e9b63-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="e9b63-119">description: 機密情報の種類が探している内容を説明します</span><span class="sxs-lookup"><span data-stu-id="e9b63-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="e9b63-120">パターン: パターンは、機密情報の種類が検出する機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9b63-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="e9b63-121">次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-121">It consists of the following components</span></span>
    - <span data-ttu-id="e9b63-122">プライマリ要素 – 機密情報の種類が検索する主な要素。</span><span class="sxs-lookup"><span data-stu-id="e9b63-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="e9b63-123">正規表現 **には、チェックサム** 検証、キーワード リスト、キーワード ディクショナリ、または関数を指定 **できます**。</span><span class="sxs-lookup"><span data-stu-id="e9b63-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="e9b63-124">サポート要素 – マッチの信頼度を高める助けとして機能する要素。</span><span class="sxs-lookup"><span data-stu-id="e9b63-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="e9b63-125">たとえば、SSN 番号の近くにあるキーワード "SSN" です。</span><span class="sxs-lookup"><span data-stu-id="e9b63-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="e9b63-126">これは、チェックサム検証、キーワード リスト、キーワード ディクショナリを使用する場合と使用しない場合の正規表現です。</span><span class="sxs-lookup"><span data-stu-id="e9b63-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="e9b63-127">信頼度 - 信頼度 (高、中、低) は、主要素と共に検出された証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="e9b63-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="e9b63-128">アイテムに含まれる証拠が多いほど、一致するアイテムに必要な機密情報が含まれているという信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="e9b63-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="e9b63-129">近接性 – プライマリ要素とサポート要素の間の文字数</span><span class="sxs-lookup"><span data-stu-id="e9b63-129">Proximity – Number of characters between primary and supporting element</span></span>

![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="e9b63-131">信頼度の詳細については、このビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b63-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="e9b63-132">機密情報の種類の例</span><span class="sxs-lookup"><span data-stu-id="e9b63-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="e9b63-133">アルゼンチンの国民識別番号 (DNI)</span><span class="sxs-lookup"><span data-stu-id="e9b63-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="e9b63-134">フォーマット</span><span class="sxs-lookup"><span data-stu-id="e9b63-134">Format</span></span>

<span data-ttu-id="e9b63-135">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e9b63-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="e9b63-136">パターン</span><span class="sxs-lookup"><span data-stu-id="e9b63-136">Pattern</span></span>

<span data-ttu-id="e9b63-137">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="e9b63-137">Eight digits:</span></span>
- <span data-ttu-id="e9b63-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e9b63-138">two digits</span></span>
- <span data-ttu-id="e9b63-139">ピリオド</span><span class="sxs-lookup"><span data-stu-id="e9b63-139">a period</span></span>
- <span data-ttu-id="e9b63-140">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e9b63-140">three digits</span></span>
- <span data-ttu-id="e9b63-141">ピリオド</span><span class="sxs-lookup"><span data-stu-id="e9b63-141">a period</span></span>
- <span data-ttu-id="e9b63-142">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e9b63-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="e9b63-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e9b63-143">Checksum</span></span>

<span data-ttu-id="e9b63-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="e9b63-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="e9b63-145">定義</span><span class="sxs-lookup"><span data-stu-id="e9b63-145">Definition</span></span>

<span data-ttu-id="e9b63-146">DLP ポリシーは、約 300 文字以下の場合に、この種の機密情報が検出されたという中程度の信頼度を持っています。</span><span class="sxs-lookup"><span data-stu-id="e9b63-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="e9b63-147">パターンに一Regex_argentina_national_idコンテンツを検索する正規表現。</span><span class="sxs-lookup"><span data-stu-id="e9b63-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="e9b63-148">検索されたKeyword_argentina_national_id検索されます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b63-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="e9b63-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="e9b63-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="e9b63-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="e9b63-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="e9b63-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="e9b63-152">ID</span><span class="sxs-lookup"><span data-stu-id="e9b63-152">Identity</span></span> 
- <span data-ttu-id="e9b63-153">Id の国民識別カード</span><span class="sxs-lookup"><span data-stu-id="e9b63-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="e9b63-154">DNI</span><span class="sxs-lookup"><span data-stu-id="e9b63-154">DNI</span></span> 
- <span data-ttu-id="e9b63-155">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="e9b63-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="e9b63-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="e9b63-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="e9b63-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="e9b63-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="e9b63-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="e9b63-158">Identidad</span></span> 
- <span data-ttu-id="e9b63-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="e9b63-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="e9b63-160">信頼度の詳細</span><span class="sxs-lookup"><span data-stu-id="e9b63-160">More on confidence levels</span></span>

<span data-ttu-id="e9b63-161">機密情報の種類のエンティティ定義では、信頼度は、プライマリ要素に加えて検出されるサポート証拠の量を反映します。</span><span class="sxs-lookup"><span data-stu-id="e9b63-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="e9b63-162">アイテムに含まれる証拠が多いほど、一致するアイテムに必要な機密情報が含まれているという信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="e9b63-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="e9b63-163">たとえば、信頼度の高い一致では、主要素の近くに多くのサポート証拠が含まれるのに対し、信頼度の低い一致では、近くにはほとんど、または何もサポート証拠が含めずに一致します。</span><span class="sxs-lookup"><span data-stu-id="e9b63-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="e9b63-164">信頼度が高い場合は、最も少ない誤検知が返されますが、誤検知の数が多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="e9b63-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="e9b63-165">低または中程度の信頼度は、より多くの誤検知を返しますが、検出検出率はわずかからゼロまでです。</span><span class="sxs-lookup"><span data-stu-id="e9b63-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="e9b63-166">**低信頼** 度 : 値 65、一致したアイテムに含まれる検出検出は最も少なく、誤検知は最も少ない。</span><span class="sxs-lookup"><span data-stu-id="e9b63-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="e9b63-167">**中程度の** 信頼度 : 値 75、一致したアイテムには、平均量の誤検知と検出検出が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="e9b63-168">**高信頼** 度 : 値 85、一致したアイテムには、最も少ない誤検知が含まれますが、最も検出された検出は最も少ない。</span><span class="sxs-lookup"><span data-stu-id="e9b63-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="e9b63-169">高信頼度パターンは、低カウント (5 ~ 10) と高いカウントを持つ低信頼度パターン (20 以上) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b63-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="e9b63-170">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="e9b63-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="e9b63-171">次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="e9b63-172">**UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="e9b63-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="e9b63-173">この方法では、正規表現、キーワード、キーワード辞書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="e9b63-174">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b63-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="e9b63-175">**EDM を使用する** データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="e9b63-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="e9b63-176">この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="e9b63-177">詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b63-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="e9b63-178">**PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="e9b63-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="e9b63-179">この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e9b63-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="e9b63-180">詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b63-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="e9b63-181">信頼度の向上は、Microsoft 365 サービスのデータ損失防止、Microsoft 365 サービスの Microsoft Information Protection、通信コンプライアンス、情報ガバナンス、およびレコード管理ですぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-181">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="e9b63-182">Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e9b63-182">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="e9b63-183">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="e9b63-183">Chinese (simplified)</span></span>
> - <span data-ttu-id="e9b63-184">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="e9b63-184">Chinese (traditional)</span></span>
> - <span data-ttu-id="e9b63-185">韓国語</span><span class="sxs-lookup"><span data-stu-id="e9b63-185">Korean</span></span>
> - <span data-ttu-id="e9b63-186">日本語</span><span class="sxs-lookup"><span data-stu-id="e9b63-186">Japanese</span></span>

><span data-ttu-id="e9b63-187">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9b63-187">This support is available for sensitive information types.</span></span> <span data-ttu-id="e9b63-188">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b63-188">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="e9b63-189">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b63-189">For further information</span></span>
- [<span data-ttu-id="e9b63-190">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="e9b63-190">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="e9b63-191">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="e9b63-191">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="e9b63-192">PowerShell でカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="e9b63-192">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
