---
title: 機密情報の種類の検索基準：
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できる状態で、80の機密情報の種類が含まれています。 このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。
ms.openlocfilehash: 517ff6ae711d61b783e837aebeeb991dfaa53daa
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084336"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="16023-104">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="16023-104">What the sensitive information types look for</span></span>

<span data-ttu-id="16023-105">Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できるさまざまな機密情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="16023-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="16023-106">このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="16023-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="16023-107">機密情報の種類はパターンで定義され、正規表現または関数で識別できます。</span><span class="sxs-lookup"><span data-stu-id="16023-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="16023-108">機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="16023-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="16023-109">信頼レベルと近接も、評価プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="16023-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="16023-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="16023-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-111">Format</span><span class="sxs-lookup"><span data-stu-id="16023-111">Format</span></span>

<span data-ttu-id="16023-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-113">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-113">Pattern</span></span>

<span data-ttu-id="16023-114">さ</span><span class="sxs-lookup"><span data-stu-id="16023-114">Formatted:</span></span>
- <span data-ttu-id="16023-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="16023-116">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-116">A hyphen</span></span>
- <span data-ttu-id="16023-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-117">Four digits</span></span>
- <span data-ttu-id="16023-118">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-118">A hyphen</span></span>
- <span data-ttu-id="16023-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-119">A digit</span></span>

<span data-ttu-id="16023-120">書式なし: 0、1、2、3、6、7、または8で始まる9桁の連続した数字</span><span class="sxs-lookup"><span data-stu-id="16023-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="16023-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-121">Checksum</span></span>

<span data-ttu-id="16023-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-123">定義</span><span class="sxs-lookup"><span data-stu-id="16023-123">Definition</span></span>

<span data-ttu-id="16023-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="16023-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="16023-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="16023-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="16023-129">aba</span><span class="sxs-lookup"><span data-stu-id="16023-129">aba</span></span>
- <span data-ttu-id="16023-130">aba #</span><span class="sxs-lookup"><span data-stu-id="16023-130">aba #</span></span>
- <span data-ttu-id="16023-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="16023-131">aba routing #</span></span>
- <span data-ttu-id="16023-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="16023-132">aba routing number</span></span>
- <span data-ttu-id="16023-133">aba#</span><span class="sxs-lookup"><span data-stu-id="16023-133">aba#</span></span>
- <span data-ttu-id="16023-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="16023-134">abarouting#</span></span>
- <span data-ttu-id="16023-135">aba number</span><span class="sxs-lookup"><span data-stu-id="16023-135">aba number</span></span>
- <span data-ttu-id="16023-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16023-136">abaroutingnumber</span></span>
- <span data-ttu-id="16023-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="16023-137">american bank association routing #</span></span>
- <span data-ttu-id="16023-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="16023-138">american bank association routing number</span></span>
- <span data-ttu-id="16023-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="16023-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="16023-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16023-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="16023-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="16023-141">bank routing number</span></span>
- <span data-ttu-id="16023-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="16023-142">bankrouting#</span></span>
- <span data-ttu-id="16023-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16023-143">bankroutingnumber</span></span>
- <span data-ttu-id="16023-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="16023-144">routing transit number</span></span>
- <span data-ttu-id="16023-145">RTN</span><span class="sxs-lookup"><span data-stu-id="16023-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="16023-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-147">Format</span><span class="sxs-lookup"><span data-stu-id="16023-147">Format</span></span>

<span data-ttu-id="16023-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-149">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-149">Pattern</span></span>

<span data-ttu-id="16023-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-150">Eight digits:</span></span>
- <span data-ttu-id="16023-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-151">Two digits</span></span>
- <span data-ttu-id="16023-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-152">A period</span></span>
- <span data-ttu-id="16023-153">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-153">Three digits</span></span>
- <span data-ttu-id="16023-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-154">A period</span></span>
- <span data-ttu-id="16023-155">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-156">Checksum</span></span>

<span data-ttu-id="16023-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-158">定義</span><span class="sxs-lookup"><span data-stu-id="16023-158">Definition</span></span>

<span data-ttu-id="16023-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-160">正規表現 Regex_argentina_national_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-161">Keyword_argentina_national_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="16023-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="16023-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="16023-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="16023-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="16023-165">ID</span><span class="sxs-lookup"><span data-stu-id="16023-165">Identity</span></span> 
- <span data-ttu-id="16023-166">識別国の Id カード</span><span class="sxs-lookup"><span data-stu-id="16023-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="16023-167">DNI</span><span class="sxs-lookup"><span data-stu-id="16023-167">DNI</span></span> 
- <span data-ttu-id="16023-168">個人の NIC National レジストリ</span><span class="sxs-lookup"><span data-stu-id="16023-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="16023-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="16023-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="16023-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="16023-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="16023-171">Dad の識別子</span><span class="sxs-lookup"><span data-stu-id="16023-171">Identidad</span></span> 
- <span data-ttu-id="16023-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="16023-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="16023-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-174">Format</span><span class="sxs-lookup"><span data-stu-id="16023-174">Format</span></span>

<span data-ttu-id="16023-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-176">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-176">Pattern</span></span>

<span data-ttu-id="16023-177">口座番号は 6 ～ 10 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="16023-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="16023-178">オーストラリアの銀行の州支店番号:</span><span class="sxs-lookup"><span data-stu-id="16023-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="16023-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-179">Three digits</span></span> 
- <span data-ttu-id="16023-180">ハイフン</span><span class="sxs-lookup"><span data-stu-id="16023-180">A hyphen</span></span> 
- <span data-ttu-id="16023-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-182">Checksum</span></span>

<span data-ttu-id="16023-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-184">定義</span><span class="sxs-lookup"><span data-stu-id="16023-184">Definition</span></span>

<span data-ttu-id="16023-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="16023-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="16023-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="16023-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="16023-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="16023-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="16023-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="16023-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="16023-194">swift bank code</span></span>
- <span data-ttu-id="16023-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="16023-195">correspondent bank</span></span>
- <span data-ttu-id="16023-196">base currency</span><span class="sxs-lookup"><span data-stu-id="16023-196">base currency</span></span>
- <span data-ttu-id="16023-197">usa account</span><span class="sxs-lookup"><span data-stu-id="16023-197">usa account</span></span>
- <span data-ttu-id="16023-198">holder address</span><span class="sxs-lookup"><span data-stu-id="16023-198">holder address</span></span>
- <span data-ttu-id="16023-199">bank address</span><span class="sxs-lookup"><span data-stu-id="16023-199">bank address</span></span>
- <span data-ttu-id="16023-200">information account</span><span class="sxs-lookup"><span data-stu-id="16023-200">information account</span></span>
- <span data-ttu-id="16023-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="16023-201">fund transfers</span></span>
- <span data-ttu-id="16023-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="16023-202">bank charges</span></span>
- <span data-ttu-id="16023-203">bank details</span><span class="sxs-lookup"><span data-stu-id="16023-203">bank details</span></span>
- <span data-ttu-id="16023-204">banking information</span><span class="sxs-lookup"><span data-stu-id="16023-204">banking information</span></span>
- <span data-ttu-id="16023-205">full names</span><span class="sxs-lookup"><span data-stu-id="16023-205">full names</span></span>
- <span data-ttu-id="16023-206">iaea</span><span class="sxs-lookup"><span data-stu-id="16023-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="16023-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-208">Format</span><span class="sxs-lookup"><span data-stu-id="16023-208">Format</span></span>

<span data-ttu-id="16023-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="16023-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-210">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-210">Pattern</span></span>

<span data-ttu-id="16023-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="16023-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="16023-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="16023-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="16023-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-213">Two digits</span></span> 
- <span data-ttu-id="16023-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="16023-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="16023-215">または</span><span class="sxs-lookup"><span data-stu-id="16023-215">OR</span></span>

- <span data-ttu-id="16023-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="16023-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-217">4-9 digits</span></span>

<span data-ttu-id="16023-218">または</span><span class="sxs-lookup"><span data-stu-id="16023-218">OR</span></span>

- <span data-ttu-id="16023-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="16023-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-220">Checksum</span></span>

<span data-ttu-id="16023-221">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-222">定義</span><span class="sxs-lookup"><span data-stu-id="16023-222">Definition</span></span>

<span data-ttu-id="16023-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="16023-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="16023-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="16023-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16023-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="16023-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="16023-229">international driving permits</span></span>
- <span data-ttu-id="16023-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="16023-230">australian automobile association</span></span>
- <span data-ttu-id="16023-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="16023-231">international driving permit</span></span>
- <span data-ttu-id="16023-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="16023-232">DriverLicence</span></span>
- <span data-ttu-id="16023-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="16023-233">DriverLicences</span></span>
- <span data-ttu-id="16023-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="16023-234">Driver Lic</span></span>
- <span data-ttu-id="16023-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="16023-235">Driver Licence</span></span>
- <span data-ttu-id="16023-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="16023-236">Driver Licences</span></span>
- <span data-ttu-id="16023-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="16023-237">DriversLic</span></span>
- <span data-ttu-id="16023-238">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-238">DriversLicence</span></span>
- <span data-ttu-id="16023-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="16023-239">DriversLicences</span></span>
- <span data-ttu-id="16023-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16023-240">Drivers Lic</span></span>
- <span data-ttu-id="16023-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="16023-241">Drivers Lics</span></span>
- <span data-ttu-id="16023-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="16023-242">Drivers Licence</span></span>
- <span data-ttu-id="16023-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="16023-243">Drivers Licences</span></span>
- <span data-ttu-id="16023-244">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16023-244">Driver'Lic</span></span>
- <span data-ttu-id="16023-245">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16023-245">Driver'Lics</span></span>
- <span data-ttu-id="16023-246">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-246">Driver'Licence</span></span>
- <span data-ttu-id="16023-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="16023-247">Driver'Licences</span></span>
- <span data-ttu-id="16023-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16023-248">Driver' Lic</span></span>
- <span data-ttu-id="16023-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16023-249">Driver' Lics</span></span>
- <span data-ttu-id="16023-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="16023-250">Driver' Licence</span></span>
- <span data-ttu-id="16023-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="16023-251">Driver' Licences</span></span>
- <span data-ttu-id="16023-252">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="16023-252">Driver'sLic</span></span>
- <span data-ttu-id="16023-253">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="16023-253">Driver'sLics</span></span>
- <span data-ttu-id="16023-254">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="16023-254">Driver'sLicence</span></span>
- <span data-ttu-id="16023-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="16023-255">Driver'sLicences</span></span>
- <span data-ttu-id="16023-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16023-256">Driver's Lic</span></span>
- <span data-ttu-id="16023-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="16023-257">Driver's Lics</span></span>
- <span data-ttu-id="16023-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="16023-258">Driver's Licence</span></span>
- <span data-ttu-id="16023-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="16023-259">Driver's Licences</span></span>
- <span data-ttu-id="16023-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="16023-260">DriverLic#</span></span>
- <span data-ttu-id="16023-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="16023-261">DriverLics#</span></span>
- <span data-ttu-id="16023-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="16023-262">DriverLicence#</span></span>
- <span data-ttu-id="16023-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="16023-263">DriverLicences#</span></span>
- <span data-ttu-id="16023-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-264">Driver Lic#</span></span>
- <span data-ttu-id="16023-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-265">Driver Lics#</span></span>
- <span data-ttu-id="16023-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="16023-266">Driver Licence#</span></span>
- <span data-ttu-id="16023-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-267">Driver Licences#</span></span>
- <span data-ttu-id="16023-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="16023-268">DriversLic#</span></span>
- <span data-ttu-id="16023-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="16023-269">DriversLics#</span></span>
- <span data-ttu-id="16023-270">その他のライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-270">DriversLicence#</span></span>
- <span data-ttu-id="16023-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="16023-271">DriversLicences#</span></span>
- <span data-ttu-id="16023-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-272">Drivers Lic#</span></span>
- <span data-ttu-id="16023-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-273">Drivers Lics#</span></span>
- <span data-ttu-id="16023-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="16023-274">Drivers Licence#</span></span>
- <span data-ttu-id="16023-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-275">Drivers Licences#</span></span>
- <span data-ttu-id="16023-276">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-276">Driver'Lic#</span></span>
- <span data-ttu-id="16023-277">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-277">Driver'Lics#</span></span>
- <span data-ttu-id="16023-278">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-278">Driver'Licence#</span></span>
- <span data-ttu-id="16023-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-279">Driver'Licences#</span></span>
- <span data-ttu-id="16023-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-280">Driver' Lic#</span></span>
- <span data-ttu-id="16023-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-281">Driver' Lics#</span></span>
- <span data-ttu-id="16023-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="16023-282">Driver' Licence#</span></span>
- <span data-ttu-id="16023-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-283">Driver' Licences#</span></span>
- <span data-ttu-id="16023-284">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="16023-284">Driver'sLic#</span></span>
- <span data-ttu-id="16023-285">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="16023-285">Driver'sLics#</span></span>
- <span data-ttu-id="16023-286">ドライバ ' スライスの持続性#</span><span class="sxs-lookup"><span data-stu-id="16023-286">Driver'sLicence#</span></span>
- <span data-ttu-id="16023-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="16023-287">Driver'sLicences#</span></span>
- <span data-ttu-id="16023-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-288">Driver's Lic#</span></span>
- <span data-ttu-id="16023-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-289">Driver's Lics#</span></span>
- <span data-ttu-id="16023-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="16023-290">Driver's Licence#</span></span>
- <span data-ttu-id="16023-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="16023-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="16023-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="16023-293">aaa</span><span class="sxs-lookup"><span data-stu-id="16023-293">aaa</span></span>
- <span data-ttu-id="16023-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="16023-294">DriverLicense</span></span>
- <span data-ttu-id="16023-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="16023-295">DriverLicenses</span></span>
- <span data-ttu-id="16023-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="16023-296">Driver License</span></span>
- <span data-ttu-id="16023-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-297">Driver Licenses</span></span>
- <span data-ttu-id="16023-298">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="16023-298">DriversLicense</span></span>
- <span data-ttu-id="16023-299">このライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-299">DriversLicenses</span></span>
- <span data-ttu-id="16023-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16023-300">Drivers License</span></span>
- <span data-ttu-id="16023-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-301">Drivers Licenses</span></span>
- <span data-ttu-id="16023-302">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-302">Driver'License</span></span>
- <span data-ttu-id="16023-303">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-303">Driver'Licenses</span></span>
- <span data-ttu-id="16023-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="16023-304">Driver' License</span></span>
- <span data-ttu-id="16023-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-305">Driver' Licenses</span></span>
- <span data-ttu-id="16023-306">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-306">Driver'sLicense</span></span>
- <span data-ttu-id="16023-307">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-307">Driver'sLicenses</span></span>
- <span data-ttu-id="16023-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16023-308">Driver's License</span></span>
- <span data-ttu-id="16023-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-309">Driver's Licenses</span></span>
- <span data-ttu-id="16023-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="16023-310">DriverLicense#</span></span>
- <span data-ttu-id="16023-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="16023-311">DriverLicenses#</span></span>
- <span data-ttu-id="16023-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16023-312">Driver License#</span></span>
- <span data-ttu-id="16023-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-313">Driver Licenses#</span></span>
- <span data-ttu-id="16023-314">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="16023-314">DriversLicense#</span></span>
- <span data-ttu-id="16023-315">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-315">DriversLicenses#</span></span>
- <span data-ttu-id="16023-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="16023-316">Drivers License#</span></span>
- <span data-ttu-id="16023-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-317">Drivers Licenses#</span></span>
- <span data-ttu-id="16023-318">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-318">Driver'License#</span></span>
- <span data-ttu-id="16023-319">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-319">Driver'Licenses#</span></span>
- <span data-ttu-id="16023-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="16023-320">Driver' License#</span></span>
- <span data-ttu-id="16023-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-321">Driver' Licenses#</span></span>
- <span data-ttu-id="16023-322">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-322">Driver'sLicense#</span></span>
- <span data-ttu-id="16023-323">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="16023-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="16023-324">Driver's License#</span></span>
- <span data-ttu-id="16023-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="16023-326">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-327">Format</span><span class="sxs-lookup"><span data-stu-id="16023-327">Format</span></span>

<span data-ttu-id="16023-328">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-329">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-329">Pattern</span></span>

<span data-ttu-id="16023-330">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-330">10-11 digits:</span></span>
- <span data-ttu-id="16023-331">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="16023-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="16023-332">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="16023-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="16023-333">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="16023-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="16023-334">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="16023-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-335">Checksum</span></span>

<span data-ttu-id="16023-336">はい</span><span class="sxs-lookup"><span data-stu-id="16023-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-337">定義</span><span class="sxs-lookup"><span data-stu-id="16023-337">Definition</span></span>

<span data-ttu-id="16023-338">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-339">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-340">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="16023-341">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-341">The checksum passes.</span></span>

<span data-ttu-id="16023-342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-343">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-344">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-345">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="16023-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="16023-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="16023-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="16023-347">bank account details</span></span>
- <span data-ttu-id="16023-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="16023-348">medicare payments</span></span>
- <span data-ttu-id="16023-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="16023-349">mortgage account</span></span>
- <span data-ttu-id="16023-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="16023-350">bank payments</span></span>
- <span data-ttu-id="16023-351">information branch</span><span class="sxs-lookup"><span data-stu-id="16023-351">information branch</span></span>
- <span data-ttu-id="16023-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="16023-352">credit card loan</span></span>
- <span data-ttu-id="16023-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="16023-353">department of human services</span></span>
- <span data-ttu-id="16023-354">local service</span><span class="sxs-lookup"><span data-stu-id="16023-354">local service</span></span>
- <span data-ttu-id="16023-355">medicare</span><span class="sxs-lookup"><span data-stu-id="16023-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="16023-356">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-357">Format</span><span class="sxs-lookup"><span data-stu-id="16023-357">Format</span></span>

<span data-ttu-id="16023-358">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-359">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-359">Pattern</span></span>

<span data-ttu-id="16023-360">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-361">Checksum</span></span>

<span data-ttu-id="16023-362">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-363">定義</span><span class="sxs-lookup"><span data-stu-id="16023-363">Definition</span></span>

<span data-ttu-id="16023-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-365">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-366">Keyword_passport または Keyword_australia_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="16023-367">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="16023-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16023-368">Keyword_passport</span></span>

- <span data-ttu-id="16023-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16023-369">Passport Number</span></span>
- <span data-ttu-id="16023-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="16023-370">Passport No</span></span>
- <span data-ttu-id="16023-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="16023-371">Passport #</span></span>
- <span data-ttu-id="16023-372">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="16023-372">Passport#</span></span>
- <span data-ttu-id="16023-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="16023-373">PassportID</span></span>
- <span data-ttu-id="16023-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="16023-374">Passportno</span></span>
- <span data-ttu-id="16023-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16023-375">passportnumber</span></span>
- <span data-ttu-id="16023-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="16023-376">パスポート</span></span>
- <span data-ttu-id="16023-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-377">パスポート番号</span></span>
- <span data-ttu-id="16023-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16023-378">パスポートのNum</span></span>
- <span data-ttu-id="16023-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="16023-379">パスポート ＃</span></span> 
- <span data-ttu-id="16023-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16023-380">Numéro de passeport</span></span>
- <span data-ttu-id="16023-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16023-381">Passeport n °</span></span>
- <span data-ttu-id="16023-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16023-382">Passeport Non</span></span>
- <span data-ttu-id="16023-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16023-383">Passeport #</span></span>
- <span data-ttu-id="16023-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="16023-384">Passeport#</span></span>
- <span data-ttu-id="16023-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16023-385">PasseportNon</span></span>
- <span data-ttu-id="16023-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16023-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="16023-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="16023-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="16023-388">サインアウト</span><span class="sxs-lookup"><span data-stu-id="16023-388">passport</span></span>
- <span data-ttu-id="16023-389">passport details</span><span class="sxs-lookup"><span data-stu-id="16023-389">passport details</span></span>
- <span data-ttu-id="16023-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="16023-390">immigration and citizenship</span></span>
- <span data-ttu-id="16023-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="16023-391">commonwealth of australia</span></span>
- <span data-ttu-id="16023-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="16023-392">department of immigration</span></span>
- <span data-ttu-id="16023-393">residential address</span><span class="sxs-lookup"><span data-stu-id="16023-393">residential address</span></span>
- <span data-ttu-id="16023-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="16023-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="16023-395">visa</span><span class="sxs-lookup"><span data-stu-id="16023-395">visa</span></span>
- <span data-ttu-id="16023-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="16023-396">national identity card</span></span>
- <span data-ttu-id="16023-397">passport number</span><span class="sxs-lookup"><span data-stu-id="16023-397">passport number</span></span>
- <span data-ttu-id="16023-398">travel document</span><span class="sxs-lookup"><span data-stu-id="16023-398">travel document</span></span>
- <span data-ttu-id="16023-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="16023-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="16023-400">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="16023-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-401">Format</span><span class="sxs-lookup"><span data-stu-id="16023-401">Format</span></span>

<span data-ttu-id="16023-402">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-403">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-403">Pattern</span></span>

<span data-ttu-id="16023-404">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16023-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="16023-405">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-405">Three digits</span></span> 
- <span data-ttu-id="16023-406">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="16023-406">An optional space</span></span> 
- <span data-ttu-id="16023-407">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-407">Three digits</span></span> 
- <span data-ttu-id="16023-408">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="16023-408">An optional space</span></span> 
- <span data-ttu-id="16023-409">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="16023-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-410">Checksum</span></span>

<span data-ttu-id="16023-411">はい</span><span class="sxs-lookup"><span data-stu-id="16023-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-412">定義</span><span class="sxs-lookup"><span data-stu-id="16023-412">Definition</span></span>

<span data-ttu-id="16023-413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-414">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-415">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="16023-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="16023-416">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="16023-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="16023-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="16023-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="16023-419">australian business number</span></span>
- <span data-ttu-id="16023-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="16023-420">marginal tax rate</span></span>
- <span data-ttu-id="16023-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="16023-421">medicare levy</span></span>
- <span data-ttu-id="16023-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="16023-422">portfolio number</span></span>
- <span data-ttu-id="16023-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="16023-423">service veterans</span></span>
- <span data-ttu-id="16023-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="16023-424">withholding tax</span></span>
- <span data-ttu-id="16023-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="16023-425">individual tax return</span></span>
- <span data-ttu-id="16023-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="16023-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="16023-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="16023-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="16023-428">00000000</span><span class="sxs-lookup"><span data-stu-id="16023-428">00000000</span></span>
- <span data-ttu-id="16023-429">11111111</span><span class="sxs-lookup"><span data-stu-id="16023-429">11111111</span></span>
- <span data-ttu-id="16023-430">22222222</span><span class="sxs-lookup"><span data-stu-id="16023-430">22222222</span></span>
- <span data-ttu-id="16023-431">33333333</span><span class="sxs-lookup"><span data-stu-id="16023-431">33333333</span></span>
- <span data-ttu-id="16023-432">44444444</span><span class="sxs-lookup"><span data-stu-id="16023-432">44444444</span></span>
- <span data-ttu-id="16023-433">55555555</span><span class="sxs-lookup"><span data-stu-id="16023-433">55555555</span></span>
- <span data-ttu-id="16023-434">66666666</span><span class="sxs-lookup"><span data-stu-id="16023-434">66666666</span></span>
- <span data-ttu-id="16023-435">77777777</span><span class="sxs-lookup"><span data-stu-id="16023-435">77777777</span></span>
- <span data-ttu-id="16023-436">88888888</span><span class="sxs-lookup"><span data-stu-id="16023-436">88888888</span></span>
- <span data-ttu-id="16023-437">99999999</span><span class="sxs-lookup"><span data-stu-id="16023-437">99999999</span></span>
- <span data-ttu-id="16023-438">000000000</span><span class="sxs-lookup"><span data-stu-id="16023-438">000000000</span></span>
- <span data-ttu-id="16023-439">111111111</span><span class="sxs-lookup"><span data-stu-id="16023-439">111111111</span></span>
- <span data-ttu-id="16023-440">222222222</span><span class="sxs-lookup"><span data-stu-id="16023-440">222222222</span></span>
- <span data-ttu-id="16023-441">333333333</span><span class="sxs-lookup"><span data-stu-id="16023-441">333333333</span></span>
- <span data-ttu-id="16023-442">444444444</span><span class="sxs-lookup"><span data-stu-id="16023-442">444444444</span></span>
- <span data-ttu-id="16023-443">555555555</span><span class="sxs-lookup"><span data-stu-id="16023-443">555555555</span></span>
- <span data-ttu-id="16023-444">666666666</span><span class="sxs-lookup"><span data-stu-id="16023-444">666666666</span></span>
- <span data-ttu-id="16023-445">777777777</span><span class="sxs-lookup"><span data-stu-id="16023-445">777777777</span></span>
- <span data-ttu-id="16023-446">888888888</span><span class="sxs-lookup"><span data-stu-id="16023-446">888888888</span></span>
- <span data-ttu-id="16023-447">999999999</span><span class="sxs-lookup"><span data-stu-id="16023-447">999999999</span></span>
- <span data-ttu-id="16023-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="16023-448">0000000000</span></span>
- <span data-ttu-id="16023-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="16023-449">1111111111</span></span>
- <span data-ttu-id="16023-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="16023-450">2222222222</span></span>
- <span data-ttu-id="16023-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="16023-451">3333333333</span></span>
- <span data-ttu-id="16023-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="16023-452">4444444444</span></span>
- <span data-ttu-id="16023-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="16023-453">5555555555</span></span>
- <span data-ttu-id="16023-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="16023-454">6666666666</span></span>
- <span data-ttu-id="16023-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="16023-455">7777777777</span></span>
- <span data-ttu-id="16023-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="16023-456">8888888888</span></span>
- <span data-ttu-id="16023-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="16023-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="16023-458">Azure DocumentDB 認証キー</span><span class="sxs-lookup"><span data-stu-id="16023-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="16023-459">Format</span><span class="sxs-lookup"><span data-stu-id="16023-459">Format</span></span>

<span data-ttu-id="16023-460">文字列 "DocumentDb" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="16023-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-461">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-461">Pattern</span></span>

- <span data-ttu-id="16023-462">文字列 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="16023-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="16023-463">3-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-464">より大きい記号 (>)、等号 (=)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="16023-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="16023-465">86の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16023-466">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-467">Checksum</span></span>

<span data-ttu-id="16023-468">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-469">定義</span><span class="sxs-lookup"><span data-stu-id="16023-469">Definition</span></span>

<span data-ttu-id="16023-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-471">正規表現 CEP_Regex_AzureDocumentDBAuthKey は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-472">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-473">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-475">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-476">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-476">contoso</span></span>
- <span data-ttu-id="16023-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-477">fabrikam</span></span>
- <span data-ttu-id="16023-478">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-478">northwind</span></span>
- <span data-ttu-id="16023-479">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-479">sandbox</span></span>
- <span data-ttu-id="16023-480">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-480">onebox</span></span>
- <span data-ttu-id="16023-481">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-481">localhost</span></span>
- <span data-ttu-id="16023-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-482">127.0.0.1</span></span>
- <span data-ttu-id="16023-483">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-484">com</span><span class="sxs-lookup"><span data-stu-id="16023-484">com</span></span>
- <span data-ttu-id="16023-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-486">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="16023-487">Azure IAAS データベースの接続文字列と Azure SQL 接続文字列</span><span class="sxs-lookup"><span data-stu-id="16023-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16023-488">Format</span><span class="sxs-lookup"><span data-stu-id="16023-488">Format</span></span>

<span data-ttu-id="16023-489">文字列 "Server"、"server"、または "data source" の後に、次のパターンで概説されている文字と文字列を指定します (文字列 "cloudapp" を含む)。</span><span class="sxs-lookup"><span data-stu-id="16023-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="16023-490">com または "cloudapp azure。</span><span class="sxs-lookup"><span data-stu-id="16023-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="16023-491">net "または" database "です。</span><span class="sxs-lookup"><span data-stu-id="16023-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="16023-492">net "、および" Password "または" pwd "という文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="16023-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-493">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-493">Pattern</span></span>

- <span data-ttu-id="16023-494">文字列 "Server"、"server"、または "data source"</span><span class="sxs-lookup"><span data-stu-id="16023-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="16023-495">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-496">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-496">An equal sign (=)</span></span>
- <span data-ttu-id="16023-497">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-498">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-499">文字列 "cloudapp。</span><span class="sxs-lookup"><span data-stu-id="16023-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="16023-500">com "," cloudapp。</span><span class="sxs-lookup"><span data-stu-id="16023-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="16023-501">net "、または" database "です。</span><span class="sxs-lookup"><span data-stu-id="16023-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="16023-502">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-502">net"</span></span>
- <span data-ttu-id="16023-503">1-300 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-504">文字列 "Password"、"password"、または "pwd"</span><span class="sxs-lookup"><span data-stu-id="16023-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="16023-505">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-506">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-506">An equal sign (=)</span></span>
- <span data-ttu-id="16023-507">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-508">セミコロンではない1つ以上の文字 (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="16023-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="16023-509">セミコロン (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="16023-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-510">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-510">Checksum</span></span>

<span data-ttu-id="16023-511">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-512">定義</span><span class="sxs-lookup"><span data-stu-id="16023-512">Definition</span></span>

<span data-ttu-id="16023-513">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-514">正規表現 CEP_Regex_AzureConnectionString は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-515">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-516">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-518">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-519">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-519">contoso</span></span>
- <span data-ttu-id="16023-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-520">fabrikam</span></span>
- <span data-ttu-id="16023-521">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-521">northwind</span></span>
- <span data-ttu-id="16023-522">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-522">sandbox</span></span>
- <span data-ttu-id="16023-523">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-523">onebox</span></span>
- <span data-ttu-id="16023-524">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-524">localhost</span></span>
- <span data-ttu-id="16023-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-525">127.0.0.1</span></span>
- <span data-ttu-id="16023-526">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-527">com</span><span class="sxs-lookup"><span data-stu-id="16023-527">com</span></span>
- <span data-ttu-id="16023-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-529">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="16023-530">Azure IoT 接続文字列</span><span class="sxs-lookup"><span data-stu-id="16023-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16023-531">Format</span><span class="sxs-lookup"><span data-stu-id="16023-531">Format</span></span>

<span data-ttu-id="16023-532">文字列 "HostName" の後に、次のパターンで概説されている文字と文字列 ("azure デバイス" を含む)。</span><span class="sxs-lookup"><span data-stu-id="16023-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="16023-533">net "および" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="16023-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-534">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-534">Pattern</span></span>

- <span data-ttu-id="16023-535">文字列 "HostName"</span><span class="sxs-lookup"><span data-stu-id="16023-535">The string "HostName"</span></span>
- <span data-ttu-id="16023-536">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-537">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-537">An equal sign (=)</span></span>
- <span data-ttu-id="16023-538">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-539">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-540">文字列 "azure デバイス。</span><span class="sxs-lookup"><span data-stu-id="16023-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="16023-541">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-541">net"</span></span>
- <span data-ttu-id="16023-542">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-543">文字列 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="16023-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="16023-544">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-545">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-545">An equal sign (=)</span></span>
- <span data-ttu-id="16023-546">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-547">43の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16023-548">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-549">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-549">Checksum</span></span>

<span data-ttu-id="16023-550">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-551">定義</span><span class="sxs-lookup"><span data-stu-id="16023-551">Definition</span></span>

<span data-ttu-id="16023-552">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-553">正規表現 CEP_Regex_AzureIoTConnectionString は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-554">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-555">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-557">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-558">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-558">contoso</span></span>
- <span data-ttu-id="16023-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-559">fabrikam</span></span>
- <span data-ttu-id="16023-560">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-560">northwind</span></span>
- <span data-ttu-id="16023-561">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-561">sandbox</span></span>
- <span data-ttu-id="16023-562">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-562">onebox</span></span>
- <span data-ttu-id="16023-563">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-563">localhost</span></span>
- <span data-ttu-id="16023-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-564">127.0.0.1</span></span>
- <span data-ttu-id="16023-565">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-566">com</span><span class="sxs-lookup"><span data-stu-id="16023-566">com</span></span>
- <span data-ttu-id="16023-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-568">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="16023-569">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="16023-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="16023-570">Format</span><span class="sxs-lookup"><span data-stu-id="16023-570">Format</span></span>

<span data-ttu-id="16023-571">文字列 "userpwd =" に続けて英数字の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="16023-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-572">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-572">Pattern</span></span>

- <span data-ttu-id="16023-573">文字列 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="16023-573">The string "userpwd="</span></span>
- <span data-ttu-id="16023-574">60小文字または数字の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="16023-575">二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="16023-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-576">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-576">Checksum</span></span>

<span data-ttu-id="16023-577">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-578">定義</span><span class="sxs-lookup"><span data-stu-id="16023-578">Definition</span></span>

<span data-ttu-id="16023-579">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-580">正規表現 CEP_Regex_AzurePublishSettingPasswords は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-581">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-582">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-584">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-585">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-585">contoso</span></span>
- <span data-ttu-id="16023-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-586">fabrikam</span></span>
- <span data-ttu-id="16023-587">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-587">northwind</span></span>
- <span data-ttu-id="16023-588">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-588">sandbox</span></span>
- <span data-ttu-id="16023-589">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-589">onebox</span></span>
- <span data-ttu-id="16023-590">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-590">localhost</span></span>
- <span data-ttu-id="16023-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-591">127.0.0.1</span></span>
- <span data-ttu-id="16023-592">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-593">com</span><span class="sxs-lookup"><span data-stu-id="16023-593">com</span></span>
- <span data-ttu-id="16023-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-595">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="16023-596">Azure Redis Cache 接続文字列</span><span class="sxs-lookup"><span data-stu-id="16023-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16023-597">Format</span><span class="sxs-lookup"><span data-stu-id="16023-597">Format</span></span>

<span data-ttu-id="16023-598">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="16023-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="16023-599">net "の後に、次のパターンで概説されている文字と文字列を指定します。文字列" password "または" pwd "が含まれます。</span><span class="sxs-lookup"><span data-stu-id="16023-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-600">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-600">Pattern</span></span>

- <span data-ttu-id="16023-601">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="16023-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="16023-602">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-602">net"</span></span>
- <span data-ttu-id="16023-603">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-604">文字列 "password" または "pwd"</span><span class="sxs-lookup"><span data-stu-id="16023-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="16023-605">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-606">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-606">An equal sign (=)</span></span>
- <span data-ttu-id="16023-607">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-608">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="16023-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16023-609">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-610">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-610">Checksum</span></span>

<span data-ttu-id="16023-611">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-612">定義</span><span class="sxs-lookup"><span data-stu-id="16023-612">Definition</span></span>

<span data-ttu-id="16023-613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-614">正規表現 CEP_Regex_AzureRedisCacheConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="16023-615">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-616">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-618">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-619">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-619">contoso</span></span>
- <span data-ttu-id="16023-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-620">fabrikam</span></span>
- <span data-ttu-id="16023-621">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-621">northwind</span></span>
- <span data-ttu-id="16023-622">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-622">sandbox</span></span>
- <span data-ttu-id="16023-623">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-623">onebox</span></span>
- <span data-ttu-id="16023-624">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-624">localhost</span></span>
- <span data-ttu-id="16023-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-625">127.0.0.1</span></span>
- <span data-ttu-id="16023-626">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-627">com</span><span class="sxs-lookup"><span data-stu-id="16023-627">com</span></span>
- <span data-ttu-id="16023-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-629">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="16023-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="16023-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="16023-631">Format</span><span class="sxs-lookup"><span data-stu-id="16023-631">Format</span></span>

<span data-ttu-id="16023-632">文字列 "sig" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="16023-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-633">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-633">Pattern</span></span>

- <span data-ttu-id="16023-634">文字列 "sig"</span><span class="sxs-lookup"><span data-stu-id="16023-634">The string "sig"</span></span>
- <span data-ttu-id="16023-635">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-636">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-636">An equal sign (=)</span></span>
- <span data-ttu-id="16023-637">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-638">43-53 文字のうち、下位または大文字の文字、数字、またはパーセント記号 (%) の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="16023-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="16023-639">文字列 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="16023-639">The string "%3d"</span></span>
- <span data-ttu-id="16023-640">小文字または大文字、数字、パーセント記号 (%) 以外の文字</span><span class="sxs-lookup"><span data-stu-id="16023-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-641">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-641">Checksum</span></span>

<span data-ttu-id="16023-642">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-643">定義</span><span class="sxs-lookup"><span data-stu-id="16023-643">Definition</span></span>

<span data-ttu-id="16023-644">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-645">正規表現 CEP_Regex_AzureSAS は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="16023-646">Azure Service Bus の接続文字列</span><span class="sxs-lookup"><span data-stu-id="16023-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16023-647">Format</span><span class="sxs-lookup"><span data-stu-id="16023-647">Format</span></span>

<span data-ttu-id="16023-648">文字列 "EndPoint" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="16023-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="16023-649">net "および" Shared' キー "。</span><span class="sxs-lookup"><span data-stu-id="16023-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-650">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-650">Pattern</span></span>

- <span data-ttu-id="16023-651">文字列 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="16023-651">The string "EndPoint"</span></span>
- <span data-ttu-id="16023-652">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-653">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-653">An equal sign (=)</span></span>
- <span data-ttu-id="16023-654">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-655">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-656">文字列 "windows.</span><span class="sxs-lookup"><span data-stu-id="16023-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="16023-657">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-657">net"</span></span>
- <span data-ttu-id="16023-658">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-659">文字列 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="16023-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="16023-660">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-661">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-661">An equal sign (=)</span></span>
- <span data-ttu-id="16023-662">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-663">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="16023-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16023-664">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-665">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-665">Checksum</span></span>

<span data-ttu-id="16023-666">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-667">定義</span><span class="sxs-lookup"><span data-stu-id="16023-667">Definition</span></span>

<span data-ttu-id="16023-668">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-669">正規表現 CEP_Regex_AzureServiceBusConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="16023-670">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-671">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-673">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-674">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-674">contoso</span></span>
- <span data-ttu-id="16023-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-675">fabrikam</span></span>
- <span data-ttu-id="16023-676">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-676">northwind</span></span>
- <span data-ttu-id="16023-677">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-677">sandbox</span></span>
- <span data-ttu-id="16023-678">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-678">onebox</span></span>
- <span data-ttu-id="16023-679">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-679">localhost</span></span>
- <span data-ttu-id="16023-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-680">127.0.0.1</span></span>
- <span data-ttu-id="16023-681">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-682">com</span><span class="sxs-lookup"><span data-stu-id="16023-682">com</span></span>
- <span data-ttu-id="16023-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-684">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="16023-685">Azure ストレージアカウントキー</span><span class="sxs-lookup"><span data-stu-id="16023-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="16023-686">Format</span><span class="sxs-lookup"><span data-stu-id="16023-686">Format</span></span>

<span data-ttu-id="16023-687">文字列 "DefaultEndpointsProtocol" の後に、文字列 "AccountKey" を含む、次のパターンで概説されている文字および文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="16023-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-688">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-688">Pattern</span></span>

- <span data-ttu-id="16023-689">文字列 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="16023-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="16023-690">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-691">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-691">An equal sign (=)</span></span>
- <span data-ttu-id="16023-692">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-693">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-694">文字列 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="16023-694">The string "AccountKey"</span></span>
- <span data-ttu-id="16023-695">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-696">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-696">An equal sign (=)</span></span>
- <span data-ttu-id="16023-697">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="16023-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="16023-698">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="16023-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16023-699">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-700">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-700">Checksum</span></span>

<span data-ttu-id="16023-701">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-702">定義</span><span class="sxs-lookup"><span data-stu-id="16023-702">Definition</span></span>

<span data-ttu-id="16023-703">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-704">正規表現 CEP_Regex_AzureStorageAccountKey は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-705">正規表現 CEP_AzureEmulatorStorageAccountFilter は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="16023-706">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-707">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="16023-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="16023-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="16023-709">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="16023-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-712">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-713">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-713">contoso</span></span>
- <span data-ttu-id="16023-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-714">fabrikam</span></span>
- <span data-ttu-id="16023-715">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-715">northwind</span></span>
- <span data-ttu-id="16023-716">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-716">sandbox</span></span>
- <span data-ttu-id="16023-717">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-717">onebox</span></span>
- <span data-ttu-id="16023-718">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-718">localhost</span></span>
- <span data-ttu-id="16023-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-719">127.0.0.1</span></span>
- <span data-ttu-id="16023-720">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-721">com</span><span class="sxs-lookup"><span data-stu-id="16023-721">com</span></span>
- <span data-ttu-id="16023-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-723">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="16023-724">Azure ストレージアカウントキー (汎用)</span><span class="sxs-lookup"><span data-stu-id="16023-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="16023-725">Format</span><span class="sxs-lookup"><span data-stu-id="16023-725">Format</span></span>

<span data-ttu-id="16023-726">86の下または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせで、下のパターンで説明されている文字が前または後にある。</span><span class="sxs-lookup"><span data-stu-id="16023-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-727">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-727">Pattern</span></span>

- <span data-ttu-id="16023-728">0-1 より大きい記号 (>)、アポストロフィ (')、等号 (=)、引用符 (")、または番号記号 (#) を指定します。</span><span class="sxs-lookup"><span data-stu-id="16023-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="16023-729">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="16023-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="16023-730">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="16023-731">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-731">Checksum</span></span>

<span data-ttu-id="16023-732">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-733">定義</span><span class="sxs-lookup"><span data-stu-id="16023-733">Definition</span></span>

<span data-ttu-id="16023-734">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-735">正規表現 CEP_Regex_AzureStorageAccountKeyGeneric は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="16023-736">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="16023-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-737">Format</span><span class="sxs-lookup"><span data-stu-id="16023-737">Format</span></span>

<span data-ttu-id="16023-738">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="16023-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-739">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-739">Pattern</span></span>

<span data-ttu-id="16023-740">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="16023-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="16023-741">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="16023-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="16023-742">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-742">A hyphen</span></span> 
- <span data-ttu-id="16023-743">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="16023-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="16023-744">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="16023-744">A period</span></span> 
- <span data-ttu-id="16023-745">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-746">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-746">Checksum</span></span>

<span data-ttu-id="16023-747">はい</span><span class="sxs-lookup"><span data-stu-id="16023-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-748">定義</span><span class="sxs-lookup"><span data-stu-id="16023-748">Definition</span></span>

<span data-ttu-id="16023-749">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-750">関数 Func_belgium_national_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-751">Keyword_belgium_national_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="16023-752">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-753">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="16023-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="16023-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="16023-755">ID</span><span class="sxs-lookup"><span data-stu-id="16023-755">Identity</span></span>
- <span data-ttu-id="16023-756">レジスタ</span><span class="sxs-lookup"><span data-stu-id="16023-756">Registration</span></span>
- <span data-ttu-id="16023-757">Fim</span><span class="sxs-lookup"><span data-stu-id="16023-757">Identification</span></span> 
- <span data-ttu-id="16023-758">ID</span><span class="sxs-lookup"><span data-stu-id="16023-758">ID</span></span> 
- <span data-ttu-id="16023-759">「識別子」</span><span class="sxs-lookup"><span data-stu-id="16023-759">Identiteitskaart</span></span>
- <span data-ttu-id="16023-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="16023-760">Registratie nummer</span></span> 
- <span data-ttu-id="16023-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="16023-761">Identificatie nummer</span></span> 
- <span data-ttu-id="16023-762">識別子</span><span class="sxs-lookup"><span data-stu-id="16023-762">Identiteit</span></span>
- <span data-ttu-id="16023-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="16023-763">Registratie</span></span>
- <span data-ttu-id="16023-764">識別子</span><span class="sxs-lookup"><span data-stu-id="16023-764">Identificatie</span></span> 
- <span data-ttu-id="16023-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="16023-765">Carte d’identité</span></span> 
- <span data-ttu-id="16023-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="16023-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="16023-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="16023-767">numéro d'identification</span></span>
- <span data-ttu-id="16023-768">識別子</span><span class="sxs-lookup"><span data-stu-id="16023-768">identité</span></span> 
- <span data-ttu-id="16023-769">inscription</span><span class="sxs-lookup"><span data-stu-id="16023-769">inscription</span></span> 
- <span data-ttu-id="16023-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="16023-770">Identifikation</span></span>
- <span data-ttu-id="16023-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="16023-771">Identifizierung</span></span>
- <span data-ttu-id="16023-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-772">Identifikationsnummer</span></span>
- <span data-ttu-id="16023-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="16023-773">Personalausweis</span></span>
- <span data-ttu-id="16023-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="16023-774">Registrierung</span></span>
- <span data-ttu-id="16023-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="16023-776">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="16023-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-777">Format</span><span class="sxs-lookup"><span data-stu-id="16023-777">Format</span></span>

<span data-ttu-id="16023-778">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-779">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-779">Pattern</span></span>

<span data-ttu-id="16023-780">さ</span><span class="sxs-lookup"><span data-stu-id="16023-780">Formatted:</span></span>
- <span data-ttu-id="16023-781">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-781">Three digits</span></span> 
- <span data-ttu-id="16023-782">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-782">A period</span></span> 
- <span data-ttu-id="16023-783">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-783">Three digits</span></span> 
- <span data-ttu-id="16023-784">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-784">A period</span></span> 
- <span data-ttu-id="16023-785">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-785">Three digits</span></span> 
- <span data-ttu-id="16023-786">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-786">A hyphen</span></span> 
- <span data-ttu-id="16023-787">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-787">Two digits which are check digits</span></span>

<span data-ttu-id="16023-788">なし</span><span class="sxs-lookup"><span data-stu-id="16023-788">Unformatted:</span></span>
- <span data-ttu-id="16023-789">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="16023-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-790">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-790">Checksum</span></span>

<span data-ttu-id="16023-791">はい</span><span class="sxs-lookup"><span data-stu-id="16023-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-792">定義</span><span class="sxs-lookup"><span data-stu-id="16023-792">Definition</span></span>

<span data-ttu-id="16023-793">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-794">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-795">Keyword_brazil_cpf からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="16023-796">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-796">The checksum passes.</span></span>

<span data-ttu-id="16023-797">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-798">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-799">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-800">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="16023-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="16023-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="16023-802">CPF</span><span class="sxs-lookup"><span data-stu-id="16023-802">CPF</span></span>
- <span data-ttu-id="16023-803">Fim</span><span class="sxs-lookup"><span data-stu-id="16023-803">Identification</span></span>
- <span data-ttu-id="16023-804">レジスタ</span><span class="sxs-lookup"><span data-stu-id="16023-804">Registration</span></span>
- <span data-ttu-id="16023-805">増大</span><span class="sxs-lookup"><span data-stu-id="16023-805">Revenue</span></span>
- <span data-ttu-id="16023-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="16023-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="16023-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="16023-807">Imposto</span></span> 
- <span data-ttu-id="16023-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="16023-808">Identificação</span></span> 
- <span data-ttu-id="16023-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="16023-809">Inscrição</span></span> 
- <span data-ttu-id="16023-810">Receita</span><span class="sxs-lookup"><span data-stu-id="16023-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="16023-811">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="16023-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="16023-812">Format</span><span class="sxs-lookup"><span data-stu-id="16023-812">Format</span></span>

<span data-ttu-id="16023-813">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-814">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-814">Pattern</span></span>
<span data-ttu-id="16023-815">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="16023-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="16023-816">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-816">Two digits</span></span> 
- <span data-ttu-id="16023-817">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-817">A period</span></span> 
- <span data-ttu-id="16023-818">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-818">Three digits</span></span> 
- <span data-ttu-id="16023-819">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-819">A period</span></span> 
- <span data-ttu-id="16023-820">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="16023-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="16023-821">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-821">A forward slash</span></span> 
- <span data-ttu-id="16023-822">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="16023-822">Four-digit branch number</span></span> 
- <span data-ttu-id="16023-823">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-823">A hyphen</span></span> 
- <span data-ttu-id="16023-824">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-825">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-825">Checksum</span></span>

<span data-ttu-id="16023-826">はい</span><span class="sxs-lookup"><span data-stu-id="16023-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-827">定義</span><span class="sxs-lookup"><span data-stu-id="16023-827">Definition</span></span>

<span data-ttu-id="16023-828">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-829">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-830">Keyword_brazil_cnpj からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="16023-831">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-831">The checksum passes.</span></span>

<span data-ttu-id="16023-832">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-833">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-834">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-835">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="16023-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="16023-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="16023-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="16023-837">CNPJ</span></span> 
- <span data-ttu-id="16023-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="16023-838">CNPJ/MF</span></span> 
- <span data-ttu-id="16023-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="16023-839">CNPJ-MF</span></span> 
- <span data-ttu-id="16023-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="16023-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="16023-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="16023-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="16023-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="16023-842">Legal entity</span></span> 
- <span data-ttu-id="16023-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="16023-843">Legal entities</span></span> 
- <span data-ttu-id="16023-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="16023-844">Registration Status</span></span> 
- <span data-ttu-id="16023-845">ビジネス</span><span class="sxs-lookup"><span data-stu-id="16023-845">Business</span></span> 
- <span data-ttu-id="16023-846">Company</span><span class="sxs-lookup"><span data-stu-id="16023-846">Company</span></span>
- <span data-ttu-id="16023-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="16023-847">CNPJ</span></span> 
- <span data-ttu-id="16023-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="16023-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="16023-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="16023-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="16023-850">CGC</span><span class="sxs-lookup"><span data-stu-id="16023-850">CGC</span></span> 
- <span data-ttu-id="16023-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="16023-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="16023-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="16023-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="16023-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="16023-853">Situação cadastral</span></span> 
- <span data-ttu-id="16023-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="16023-854">Inscrição</span></span> 
- <span data-ttu-id="16023-855">サイト</span><span class="sxs-lookup"><span data-stu-id="16023-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="16023-856">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="16023-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="16023-857">Format</span><span class="sxs-lookup"><span data-stu-id="16023-857">Format</span></span>

<span data-ttu-id="16023-858">Registro Geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="16023-859">Registro de 識別子 Dade (RIC) (新しい形式):11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-860">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-860">Pattern</span></span>

<span data-ttu-id="16023-861">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="16023-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="16023-862">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-862">Two digits</span></span> 
- <span data-ttu-id="16023-863">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-863">A period</span></span> 
- <span data-ttu-id="16023-864">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-864">Three digits</span></span> 
- <span data-ttu-id="16023-865">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-865">A period</span></span> 
- <span data-ttu-id="16023-866">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-866">Three digits</span></span> 
- <span data-ttu-id="16023-867">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-867">A hyphen</span></span> 
- <span data-ttu-id="16023-868">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-868">One digit which is a check digit</span></span>

<span data-ttu-id="16023-869">Registro de 識別子 Dade (RIC) (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="16023-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="16023-870">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-870">10 digits</span></span> 
- <span data-ttu-id="16023-871">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-871">A hyphen</span></span> 
- <span data-ttu-id="16023-872">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-873">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-873">Checksum</span></span>

<span data-ttu-id="16023-874">はい</span><span class="sxs-lookup"><span data-stu-id="16023-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-875">定義</span><span class="sxs-lookup"><span data-stu-id="16023-875">Definition</span></span>

<span data-ttu-id="16023-876">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-877">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-878">Keyword_brazil_rg からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="16023-879">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-879">The checksum passes.</span></span>

<span data-ttu-id="16023-880">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-881">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-882">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-883">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="16023-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="16023-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="16023-885">Cédula de 識別子 dade id カード national id número de rregistro registro de I識別子 Dade registro geral このキーワードは大文字と小文字を区別します) RIC (このキーワードは大文字と小文字を区別します)</span><span class="sxs-lookup"><span data-stu-id="16023-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="16023-886">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-887">Format</span><span class="sxs-lookup"><span data-stu-id="16023-887">Format</span></span>

<span data-ttu-id="16023-888">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-889">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-889">Pattern</span></span>

<span data-ttu-id="16023-890">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="16023-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="16023-891">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16023-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="16023-892">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-892">Five digits</span></span> 
- <span data-ttu-id="16023-893">ハイフン</span><span class="sxs-lookup"><span data-stu-id="16023-893">A hyphen</span></span> 
- <span data-ttu-id="16023-894">3桁の数字または</span><span class="sxs-lookup"><span data-stu-id="16023-894">Three digits OR</span></span>
- <span data-ttu-id="16023-895">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="16023-895">A zero "0"</span></span> 
- <span data-ttu-id="16023-896">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-897">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-897">Checksum</span></span>

<span data-ttu-id="16023-898">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-899">定義</span><span class="sxs-lookup"><span data-stu-id="16023-899">Definition</span></span>

<span data-ttu-id="16023-900">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-901">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-902">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="16023-903">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="16023-904">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-905">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-906">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-907">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="16023-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="16023-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="16023-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="16023-909">canada savings bonds</span></span>
- <span data-ttu-id="16023-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="16023-910">canada revenue agency</span></span>
- <span data-ttu-id="16023-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="16023-911">canadian financial institution</span></span>
- <span data-ttu-id="16023-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="16023-912">direct deposit form</span></span>
- <span data-ttu-id="16023-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="16023-913">canadian citizen</span></span>
- <span data-ttu-id="16023-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="16023-914">legal representative</span></span>
- <span data-ttu-id="16023-915">notary public</span><span class="sxs-lookup"><span data-stu-id="16023-915">notary public</span></span>
- <span data-ttu-id="16023-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="16023-916">commissioner for oaths</span></span>
- <span data-ttu-id="16023-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="16023-917">child care benefit</span></span>
- <span data-ttu-id="16023-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="16023-918">universal child care</span></span>
- <span data-ttu-id="16023-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="16023-919">canada child tax benefit</span></span>
- <span data-ttu-id="16023-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="16023-920">income tax benefit</span></span>
- <span data-ttu-id="16023-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="16023-921">harmonized sales tax</span></span>
- <span data-ttu-id="16023-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="16023-922">social insurance number</span></span>
- <span data-ttu-id="16023-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="16023-923">income tax refund</span></span>
- <span data-ttu-id="16023-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="16023-924">child tax benefit</span></span>
- <span data-ttu-id="16023-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="16023-925">territorial payments</span></span>
- <span data-ttu-id="16023-926">institution number</span><span class="sxs-lookup"><span data-stu-id="16023-926">institution number</span></span>
- <span data-ttu-id="16023-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="16023-927">deposit request</span></span>
- <span data-ttu-id="16023-928">banking information</span><span class="sxs-lookup"><span data-stu-id="16023-928">banking information</span></span>
- <span data-ttu-id="16023-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="16023-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="16023-930">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-931">Format</span><span class="sxs-lookup"><span data-stu-id="16023-931">Format</span></span>

<span data-ttu-id="16023-932">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="16023-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-933">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-933">Pattern</span></span>

<span data-ttu-id="16023-934">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="16023-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-935">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-935">Checksum</span></span>

<span data-ttu-id="16023-936">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-937">定義</span><span class="sxs-lookup"><span data-stu-id="16023-937">Definition</span></span>

<span data-ttu-id="16023-938">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-939">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-940">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="16023-941">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-942">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="16023-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="16023-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="16023-944">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="16023-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="16023-945">州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="16023-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="16023-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16023-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="16023-947">DL</span><span class="sxs-lookup"><span data-stu-id="16023-947">DL</span></span>
- <span data-ttu-id="16023-948">DL</span><span class="sxs-lookup"><span data-stu-id="16023-948">DLS</span></span>
- <span data-ttu-id="16023-949">CDL</span><span class="sxs-lookup"><span data-stu-id="16023-949">CDL</span></span>
- <span data-ttu-id="16023-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="16023-950">CDLS</span></span>
- <span data-ttu-id="16023-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="16023-951">DriverLic</span></span>
- <span data-ttu-id="16023-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="16023-952">DriverLics</span></span>
- <span data-ttu-id="16023-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="16023-953">DriverLicense</span></span>
- <span data-ttu-id="16023-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="16023-954">DriverLicenses</span></span>
- <span data-ttu-id="16023-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="16023-955">DriverLicence</span></span>
- <span data-ttu-id="16023-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="16023-956">DriverLicences</span></span>
- <span data-ttu-id="16023-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="16023-957">Driver Lic</span></span>
- <span data-ttu-id="16023-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="16023-958">Driver Lics</span></span>
- <span data-ttu-id="16023-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="16023-959">Driver License</span></span>
- <span data-ttu-id="16023-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-960">Driver Licenses</span></span>
- <span data-ttu-id="16023-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="16023-961">Driver Licence</span></span>
- <span data-ttu-id="16023-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="16023-962">Driver Licences</span></span>
- <span data-ttu-id="16023-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="16023-963">DriversLic</span></span>
- <span data-ttu-id="16023-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="16023-964">DriversLics</span></span>
- <span data-ttu-id="16023-965">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-965">DriversLicence</span></span>
- <span data-ttu-id="16023-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="16023-966">DriversLicences</span></span>
- <span data-ttu-id="16023-967">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="16023-967">DriversLicense</span></span>
- <span data-ttu-id="16023-968">このライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-968">DriversLicenses</span></span>
- <span data-ttu-id="16023-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16023-969">Drivers Lic</span></span>
- <span data-ttu-id="16023-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="16023-970">Drivers Lics</span></span>
- <span data-ttu-id="16023-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16023-971">Drivers License</span></span>
- <span data-ttu-id="16023-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-972">Drivers Licenses</span></span>
- <span data-ttu-id="16023-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="16023-973">Drivers Licence</span></span>
- <span data-ttu-id="16023-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="16023-974">Drivers Licences</span></span>
- <span data-ttu-id="16023-975">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16023-975">Driver'Lic</span></span>
- <span data-ttu-id="16023-976">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16023-976">Driver'Lics</span></span>
- <span data-ttu-id="16023-977">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-977">Driver'License</span></span>
- <span data-ttu-id="16023-978">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-978">Driver'Licenses</span></span>
- <span data-ttu-id="16023-979">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-979">Driver'Licence</span></span>
- <span data-ttu-id="16023-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="16023-980">Driver'Licences</span></span>
- <span data-ttu-id="16023-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16023-981">Driver' Lic</span></span>
- <span data-ttu-id="16023-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16023-982">Driver' Lics</span></span>
- <span data-ttu-id="16023-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="16023-983">Driver' License</span></span>
- <span data-ttu-id="16023-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-984">Driver' Licenses</span></span>
- <span data-ttu-id="16023-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="16023-985">Driver' Licence</span></span>
- <span data-ttu-id="16023-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="16023-986">Driver' Licences</span></span>
- <span data-ttu-id="16023-987">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="16023-987">Driver'sLic</span></span>
- <span data-ttu-id="16023-988">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="16023-988">Driver'sLics</span></span>
- <span data-ttu-id="16023-989">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-989">Driver'sLicense</span></span>
- <span data-ttu-id="16023-990">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-990">Driver'sLicenses</span></span>
- <span data-ttu-id="16023-991">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="16023-991">Driver'sLicence</span></span>
- <span data-ttu-id="16023-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="16023-992">Driver'sLicences</span></span>
- <span data-ttu-id="16023-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16023-993">Driver's Lic</span></span>
- <span data-ttu-id="16023-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="16023-994">Driver's Lics</span></span>
- <span data-ttu-id="16023-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16023-995">Driver's License</span></span>
- <span data-ttu-id="16023-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-996">Driver's Licenses</span></span>
- <span data-ttu-id="16023-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="16023-997">Driver's Licence</span></span>
- <span data-ttu-id="16023-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="16023-998">Driver's Licences</span></span>
- <span data-ttu-id="16023-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="16023-999">Permis de Conduire</span></span>
- <span data-ttu-id="16023-1000">id</span><span class="sxs-lookup"><span data-stu-id="16023-1000">id</span></span>
- <span data-ttu-id="16023-1001">ids</span><span class="sxs-lookup"><span data-stu-id="16023-1001">ids</span></span>
- <span data-ttu-id="16023-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="16023-1002">idcard number</span></span>
- <span data-ttu-id="16023-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="16023-1003">idcard numbers</span></span>
- <span data-ttu-id="16023-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="16023-1004">idcard #</span></span>
- <span data-ttu-id="16023-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="16023-1005">idcard #s</span></span>
- <span data-ttu-id="16023-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="16023-1006">idcard card</span></span>
- <span data-ttu-id="16023-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="16023-1007">idcard cards</span></span>
- <span data-ttu-id="16023-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="16023-1008">idcard</span></span>
- <span data-ttu-id="16023-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="16023-1009">identification number</span></span>
- <span data-ttu-id="16023-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="16023-1010">identification numbers</span></span>
- <span data-ttu-id="16023-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="16023-1011">identification #</span></span>
- <span data-ttu-id="16023-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="16023-1012">identification #s</span></span>
- <span data-ttu-id="16023-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="16023-1013">identification card</span></span>
- <span data-ttu-id="16023-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="16023-1014">identification cards</span></span>
- <span data-ttu-id="16023-1015">fim</span><span class="sxs-lookup"><span data-stu-id="16023-1015">identification</span></span> 
- <span data-ttu-id="16023-1016">DL#</span><span class="sxs-lookup"><span data-stu-id="16023-1016">DL#</span></span>
- <span data-ttu-id="16023-1017">DL#</span><span class="sxs-lookup"><span data-stu-id="16023-1017">DLS#</span></span> 
- <span data-ttu-id="16023-1018">CDL#</span><span class="sxs-lookup"><span data-stu-id="16023-1018">CDL#</span></span> 
- <span data-ttu-id="16023-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="16023-1019">CDLS#</span></span> 
- <span data-ttu-id="16023-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="16023-1020">DriverLic#</span></span> 
- <span data-ttu-id="16023-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="16023-1021">DriverLics#</span></span> 
- <span data-ttu-id="16023-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="16023-1022">DriverLicense#</span></span> 
- <span data-ttu-id="16023-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="16023-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="16023-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="16023-1024">DriverLicence#</span></span> 
- <span data-ttu-id="16023-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="16023-1025">DriverLicences#</span></span> 
- <span data-ttu-id="16023-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-1026">Driver Lic#</span></span>
- <span data-ttu-id="16023-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-1027">Driver Lics#</span></span> 
- <span data-ttu-id="16023-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16023-1028">Driver License#</span></span> 
- <span data-ttu-id="16023-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="16023-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16023-1030">Driver License#</span></span> 
- <span data-ttu-id="16023-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-1031">Driver Licences#</span></span> 
- <span data-ttu-id="16023-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="16023-1032">DriversLic#</span></span> 
- <span data-ttu-id="16023-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="16023-1033">DriversLics#</span></span> 
- <span data-ttu-id="16023-1034">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="16023-1034">DriversLicense#</span></span> 
- <span data-ttu-id="16023-1035">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="16023-1036">その他のライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-1036">DriversLicence#</span></span> 
- <span data-ttu-id="16023-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="16023-1037">DriversLicences#</span></span> 
- <span data-ttu-id="16023-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="16023-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="16023-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="16023-1040">Drivers License#</span></span> 
- <span data-ttu-id="16023-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="16023-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="16023-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="16023-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="16023-1044">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="16023-1045">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="16023-1046">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-1046">Driver'License#</span></span> 
- <span data-ttu-id="16023-1047">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="16023-1048">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="16023-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="16023-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="16023-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="16023-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="16023-1052">Driver' License#</span></span> 
- <span data-ttu-id="16023-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="16023-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="16023-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="16023-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="16023-1056">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="16023-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="16023-1057">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="16023-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="16023-1058">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="16023-1059">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="16023-1060">ドライバ ' スライスの持続性#</span><span class="sxs-lookup"><span data-stu-id="16023-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="16023-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="16023-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="16023-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="16023-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="16023-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="16023-1064">Driver's License#</span></span> 
- <span data-ttu-id="16023-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="16023-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="16023-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="16023-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="16023-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="16023-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="16023-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="16023-1069">rid#</span><span class="sxs-lookup"><span data-stu-id="16023-1069">id#</span></span> 
- <span data-ttu-id="16023-1070">rid#</span><span class="sxs-lookup"><span data-stu-id="16023-1070">ids#</span></span> 
- <span data-ttu-id="16023-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="16023-1071">idcard card#</span></span> 
- <span data-ttu-id="16023-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="16023-1072">idcard cards#</span></span> 
- <span data-ttu-id="16023-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="16023-1073">idcard#</span></span> 
- <span data-ttu-id="16023-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="16023-1074">identification card#</span></span> 
- <span data-ttu-id="16023-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="16023-1075">identification cards#</span></span> 
- <span data-ttu-id="16023-1076">fim#</span><span class="sxs-lookup"><span data-stu-id="16023-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="16023-1077">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="16023-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1078">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1078">Format</span></span>

<span data-ttu-id="16023-1079">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1080">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1080">Pattern</span></span>

<span data-ttu-id="16023-1081">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1082">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1082">Checksum</span></span>

<span data-ttu-id="16023-1083">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1084">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1084">Definition</span></span>

<span data-ttu-id="16023-1085">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1086">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1087">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1088">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="16023-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="16023-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="16023-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="16023-1090">personal health number</span></span>
- <span data-ttu-id="16023-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="16023-1091">patient information</span></span>
- <span data-ttu-id="16023-1092">health services</span><span class="sxs-lookup"><span data-stu-id="16023-1092">health services</span></span>
- <span data-ttu-id="16023-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="16023-1093">speciality services</span></span>
- <span data-ttu-id="16023-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="16023-1094">automobile accident</span></span>
- <span data-ttu-id="16023-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="16023-1095">patient hospital</span></span>
- <span data-ttu-id="16023-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="16023-1096">psychiatrist</span></span>
- <span data-ttu-id="16023-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="16023-1097">workers compensation</span></span>
- <span data-ttu-id="16023-1098">身体</span><span class="sxs-lookup"><span data-stu-id="16023-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="16023-1099">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1100">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1100">Format</span></span>

<span data-ttu-id="16023-1101">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1102">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1102">Pattern</span></span>

<span data-ttu-id="16023-1103">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1104">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1104">Checksum</span></span>

<span data-ttu-id="16023-1105">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1106">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1106">Definition</span></span>

<span data-ttu-id="16023-1107">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1108">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1109">Keyword_canada_passport_number または Keyword_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1110">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="16023-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="16023-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="16023-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="16023-1112">canadian citizenship</span></span>
- <span data-ttu-id="16023-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="16023-1113">canadian passport</span></span>
- <span data-ttu-id="16023-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="16023-1114">passport application</span></span>
- <span data-ttu-id="16023-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="16023-1115">passport photos</span></span>
- <span data-ttu-id="16023-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="16023-1116">certified translator</span></span>
- <span data-ttu-id="16023-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="16023-1117">canadian citizens</span></span>
- <span data-ttu-id="16023-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="16023-1118">processing times</span></span>
- <span data-ttu-id="16023-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="16023-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="16023-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16023-1120">Keyword_passport</span></span>

- <span data-ttu-id="16023-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16023-1121">Passport Number</span></span>
- <span data-ttu-id="16023-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="16023-1122">Passport No</span></span>
- <span data-ttu-id="16023-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="16023-1123">Passport #</span></span>
- <span data-ttu-id="16023-1124">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="16023-1124">Passport#</span></span>
- <span data-ttu-id="16023-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="16023-1125">PassportID</span></span>
- <span data-ttu-id="16023-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="16023-1126">Passportno</span></span>
- <span data-ttu-id="16023-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16023-1127">passportnumber</span></span>
- <span data-ttu-id="16023-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="16023-1128">パスポート</span></span>
- <span data-ttu-id="16023-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-1129">パスポート番号</span></span>
- <span data-ttu-id="16023-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16023-1130">パスポートのNum</span></span>
- <span data-ttu-id="16023-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="16023-1131">パスポート＃</span></span>
- <span data-ttu-id="16023-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16023-1132">Numéro de passeport</span></span>
- <span data-ttu-id="16023-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16023-1133">Passeport n °</span></span>
- <span data-ttu-id="16023-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16023-1134">Passeport Non</span></span>
- <span data-ttu-id="16023-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16023-1135">Passeport #</span></span>
- <span data-ttu-id="16023-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="16023-1136">Passeport#</span></span>
- <span data-ttu-id="16023-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16023-1137">PasseportNon</span></span>
- <span data-ttu-id="16023-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16023-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="16023-1139">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="16023-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="16023-1140">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1140">Format</span></span>

<span data-ttu-id="16023-1141">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1142">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1142">Pattern</span></span>

<span data-ttu-id="16023-1143">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1144">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1144">Checksum</span></span>

<span data-ttu-id="16023-1145">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1146">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1146">Definition</span></span>

<span data-ttu-id="16023-1147">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_canada_phin は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="16023-1148">Keyword_canada_phin または Keyword_canada_provinces から少なくとも2つのキーワードが見つかります。</span><span class="sxs-lookup"><span data-stu-id="16023-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1149">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="16023-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="16023-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="16023-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="16023-1151">social insurance number</span></span>
- <span data-ttu-id="16023-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="16023-1152">health information act</span></span>
- <span data-ttu-id="16023-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="16023-1153">income tax information</span></span>
- <span data-ttu-id="16023-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="16023-1154">manitoba health</span></span>
- <span data-ttu-id="16023-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="16023-1155">health registration</span></span>
- <span data-ttu-id="16023-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="16023-1156">prescription purchases</span></span>
- <span data-ttu-id="16023-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="16023-1157">benefit eligibility</span></span>
- <span data-ttu-id="16023-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="16023-1158">personal health</span></span>
- <span data-ttu-id="16023-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="16023-1159">power of attorney</span></span>
- <span data-ttu-id="16023-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="16023-1160">registration number</span></span>
- <span data-ttu-id="16023-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="16023-1161">personal health number</span></span>
- <span data-ttu-id="16023-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="16023-1162">practitioner referral</span></span>
- <span data-ttu-id="16023-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="16023-1163">wellness professional</span></span>
- <span data-ttu-id="16023-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="16023-1164">patient referral</span></span>
- <span data-ttu-id="16023-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="16023-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="16023-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="16023-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="16023-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="16023-1167">Nunavut</span></span>
- <span data-ttu-id="16023-1168">州</span><span class="sxs-lookup"><span data-stu-id="16023-1168">Quebec</span></span>
- <span data-ttu-id="16023-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="16023-1169">Northwest Territories</span></span>
- <span data-ttu-id="16023-1170">オンタリオ州</span><span class="sxs-lookup"><span data-stu-id="16023-1170">Ontario</span></span>
- <span data-ttu-id="16023-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="16023-1171">British Columbia</span></span>
- <span data-ttu-id="16023-1172">州</span><span class="sxs-lookup"><span data-stu-id="16023-1172">Alberta</span></span>
- <span data-ttu-id="16023-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="16023-1173">Saskatchewan</span></span>
- <span data-ttu-id="16023-1174">マニトバ州</span><span class="sxs-lookup"><span data-stu-id="16023-1174">Manitoba</span></span>
- <span data-ttu-id="16023-1175">州</span><span class="sxs-lookup"><span data-stu-id="16023-1175">Yukon</span></span>
- <span data-ttu-id="16023-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="16023-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="16023-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="16023-1177">New Brunswick</span></span>
- <span data-ttu-id="16023-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="16023-1178">Nova Scotia</span></span>
- <span data-ttu-id="16023-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="16023-1179">Prince Edward Island</span></span>
- <span data-ttu-id="16023-1180">カナダ</span><span class="sxs-lookup"><span data-stu-id="16023-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="16023-1181">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="16023-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1182">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1182">Format</span></span>

<span data-ttu-id="16023-1183">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="16023-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1184">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1184">Pattern</span></span>

<span data-ttu-id="16023-1185">さ</span><span class="sxs-lookup"><span data-stu-id="16023-1185">Formatted:</span></span>
- <span data-ttu-id="16023-1186">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1186">Three digits</span></span> 
- <span data-ttu-id="16023-1187">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="16023-1187">A hyphen or space</span></span> 
- <span data-ttu-id="16023-1188">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1188">Three digits</span></span> 
- <span data-ttu-id="16023-1189">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="16023-1189">A hyphen or space</span></span> 
- <span data-ttu-id="16023-1190">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1190">Three digits</span></span>

<span data-ttu-id="16023-1191">書式なし: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1192">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1192">Checksum</span></span>

<span data-ttu-id="16023-1193">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1194">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1194">Definition</span></span>

<span data-ttu-id="16023-1195">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1196">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1197">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="16023-1198">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="16023-1199">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="16023-1200">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16023-1201">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1201">The checksum passes.</span></span>

<span data-ttu-id="16023-1202">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1203">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1204">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="16023-1205">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1206">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="16023-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="16023-1207">Keyword_sin</span></span>

- <span data-ttu-id="16023-1208">sin</span><span class="sxs-lookup"><span data-stu-id="16023-1208">sin</span></span> 
- <span data-ttu-id="16023-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="16023-1209">social insurance</span></span> 
- <span data-ttu-id="16023-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="16023-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="16023-1211">大罪</span><span class="sxs-lookup"><span data-stu-id="16023-1211">sins</span></span> 
- <span data-ttu-id="16023-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="16023-1212">ssn</span></span> 
- <span data-ttu-id="16023-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="16023-1213">ssns</span></span> 
- <span data-ttu-id="16023-1214">social security</span><span class="sxs-lookup"><span data-stu-id="16023-1214">social security</span></span> 
- <span data-ttu-id="16023-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="16023-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="16023-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="16023-1216">national identification number</span></span> 
- <span data-ttu-id="16023-1217">national id</span><span class="sxs-lookup"><span data-stu-id="16023-1217">national id</span></span> 
- <span data-ttu-id="16023-1218">sin#</span><span class="sxs-lookup"><span data-stu-id="16023-1218">sin#</span></span> 
- <span data-ttu-id="16023-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="16023-1219">soc ins</span></span> 
- <span data-ttu-id="16023-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="16023-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="16023-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="16023-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="16023-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="16023-1222">driver's license</span></span> 
- <span data-ttu-id="16023-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="16023-1223">drivers license</span></span> 
- <span data-ttu-id="16023-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="16023-1224">driver's licence</span></span> 
- <span data-ttu-id="16023-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="16023-1225">drivers licence</span></span> 
- <span data-ttu-id="16023-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="16023-1226">DOB</span></span> 
- <span data-ttu-id="16023-1227">誕生日</span><span class="sxs-lookup"><span data-stu-id="16023-1227">Birthdate</span></span> 
- <span data-ttu-id="16023-1228">Birthday</span><span class="sxs-lookup"><span data-stu-id="16023-1228">Birthday</span></span> 
- <span data-ttu-id="16023-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="16023-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="16023-1230">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="16023-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1231">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1231">Format</span></span>

<span data-ttu-id="16023-1232">7-8 桁の数字と区切り文字のチェックディジットまたは文字</span><span class="sxs-lookup"><span data-stu-id="16023-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1233">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1233">Pattern</span></span>

<span data-ttu-id="16023-1234">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="16023-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="16023-1235">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-1235">1-2 digits</span></span> 
- <span data-ttu-id="16023-1236">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-1236">A period</span></span> 
- <span data-ttu-id="16023-1237">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1237">Three digits</span></span> 
- <span data-ttu-id="16023-1238">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-1238">A period</span></span> 
- <span data-ttu-id="16023-1239">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1239">Three digits</span></span> 
- <span data-ttu-id="16023-1240">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-1240">A dash</span></span> 
- <span data-ttu-id="16023-1241">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="16023-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1242">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1242">Checksum</span></span>

<span data-ttu-id="16023-1243">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1244">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1244">Definition</span></span>

<span data-ttu-id="16023-1245">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1246">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1247">Keyword_chile_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="16023-1248">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1248">The checksum passes.</span></span>

<span data-ttu-id="16023-1249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1250">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1251">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1252">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="16023-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="16023-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="16023-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="16023-1254">National Identification Number</span></span> 
- <span data-ttu-id="16023-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="16023-1255">Identity card</span></span> 
- <span data-ttu-id="16023-1256">ID</span><span class="sxs-lookup"><span data-stu-id="16023-1256">ID</span></span> 
- <span data-ttu-id="16023-1257">Fim</span><span class="sxs-lookup"><span data-stu-id="16023-1257">Identification</span></span> 
- <span data-ttu-id="16023-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="16023-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="16023-1259">実行</span><span class="sxs-lookup"><span data-stu-id="16023-1259">RUN</span></span> 
- <span data-ttu-id="16023-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="16023-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="16023-1261">類型</span><span class="sxs-lookup"><span data-stu-id="16023-1261">RUT</span></span> 
- <span data-ttu-id="16023-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="16023-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="16023-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="16023-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="16023-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="16023-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="16023-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="16023-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="16023-1266">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1267">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1267">Format</span></span>

<span data-ttu-id="16023-1268">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1269">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1269">Pattern</span></span>

<span data-ttu-id="16023-1270">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-1270">18 digits:</span></span>
- <span data-ttu-id="16023-1271">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="16023-1272">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16023-1273">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="16023-1274">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1275">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1275">Checksum</span></span>

<span data-ttu-id="16023-1276">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1277">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1277">Definition</span></span>

<span data-ttu-id="16023-1278">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1279">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1280">Keyword_china_resident_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="16023-1281">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1281">The checksum passes.</span></span>

<span data-ttu-id="16023-1282">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1283">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1284">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1285">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="16023-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="16023-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="16023-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="16023-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="16023-1288">PRC</span><span class="sxs-lookup"><span data-stu-id="16023-1288">PRC</span></span> 
- <span data-ttu-id="16023-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="16023-1289">National Identification Card</span></span> 
- <span data-ttu-id="16023-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="16023-1290">身份证</span></span> 
- <span data-ttu-id="16023-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="16023-1291">居民 身份证</span></span> 
- <span data-ttu-id="16023-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="16023-1292">居民身份证</span></span> 
- <span data-ttu-id="16023-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="16023-1293">鉴定</span></span> 
- <span data-ttu-id="16023-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="16023-1294">身分證</span></span> 
- <span data-ttu-id="16023-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="16023-1295">居民 身份證</span></span>
- <span data-ttu-id="16023-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="16023-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="16023-1297">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1298">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1298">Format</span></span>

<span data-ttu-id="16023-1299">書式設定または書式設定ができない16桁の数字 (dddddddddddddddd)。 Luhn テストに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1300">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1300">Pattern</span></span>

<span data-ttu-id="16023-1301">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="16023-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1302">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1302">Checksum</span></span>

<span data-ttu-id="16023-1303">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="16023-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1304">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1304">Definition</span></span>

<span data-ttu-id="16023-1305">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1306">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1307">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-1307">One of the following is true:</span></span>
    - <span data-ttu-id="16023-1308">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="16023-1309">Keyword_cc_name からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="16023-1310">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16023-1311">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1311">The checksum passes.</span></span>

<span data-ttu-id="16023-1312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1313">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1314">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1315">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="16023-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="16023-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="16023-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="16023-1317">card verification</span></span>
- <span data-ttu-id="16023-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="16023-1318">card identification number</span></span>
- <span data-ttu-id="16023-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="16023-1319">cvn</span></span>
- <span data-ttu-id="16023-1320">cid</span><span class="sxs-lookup"><span data-stu-id="16023-1320">cid</span></span>
- <span data-ttu-id="16023-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="16023-1321">cvc2</span></span>
- <span data-ttu-id="16023-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="16023-1322">cvv2</span></span>
- <span data-ttu-id="16023-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="16023-1323">pin block</span></span>
- <span data-ttu-id="16023-1324">security code</span><span class="sxs-lookup"><span data-stu-id="16023-1324">security code</span></span>
- <span data-ttu-id="16023-1325">security number</span><span class="sxs-lookup"><span data-stu-id="16023-1325">security number</span></span>
- <span data-ttu-id="16023-1326">security no</span><span class="sxs-lookup"><span data-stu-id="16023-1326">security no</span></span>
- <span data-ttu-id="16023-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="16023-1327">issue number</span></span>
- <span data-ttu-id="16023-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="16023-1328">issue no</span></span>
- <span data-ttu-id="16023-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="16023-1329">cryptogramme</span></span>
- <span data-ttu-id="16023-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="16023-1330">numéro de sécurité</span></span>
- <span data-ttu-id="16023-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="16023-1331">numero de securite</span></span>
- <span data-ttu-id="16023-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="16023-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="16023-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="16023-1334">prüfziffer</span></span>
- <span data-ttu-id="16023-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="16023-1335">prufziffer</span></span>
- <span data-ttu-id="16023-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="16023-1336">sicherheits Kode</span></span>
- <span data-ttu-id="16023-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="16023-1337">sicherheitscode</span></span>
- <span data-ttu-id="16023-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="16023-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="16023-1339">verfalldatum</span></span>
- <span data-ttu-id="16023-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="16023-1340">codice di verifica</span></span>
- <span data-ttu-id="16023-1341">cod.</span><span class="sxs-lookup"><span data-stu-id="16023-1341">cod.</span></span> <span data-ttu-id="16023-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="16023-1342">sicurezza</span></span>
- <span data-ttu-id="16023-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="16023-1343">cod sicurezza</span></span>
- <span data-ttu-id="16023-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="16023-1344">n autorizzazione</span></span>
- <span data-ttu-id="16023-1345">código</span><span class="sxs-lookup"><span data-stu-id="16023-1345">código</span></span>
- <span data-ttu-id="16023-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="16023-1346">codigo</span></span>
- <span data-ttu-id="16023-1347">cod.</span><span class="sxs-lookup"><span data-stu-id="16023-1347">cod.</span></span> <span data-ttu-id="16023-1348">seg</span><span class="sxs-lookup"><span data-stu-id="16023-1348">seg</span></span>
- <span data-ttu-id="16023-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="16023-1349">cod seg</span></span>
- <span data-ttu-id="16023-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1350">código de segurança</span></span>
- <span data-ttu-id="16023-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1351">codigo de seguranca</span></span>
- <span data-ttu-id="16023-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1352">codigo de segurança</span></span>
- <span data-ttu-id="16023-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1353">código de seguranca</span></span>
- <span data-ttu-id="16023-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="16023-1354">cód.</span></span> <span data-ttu-id="16023-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1355">segurança</span></span>
- <span data-ttu-id="16023-1356">cod.</span><span class="sxs-lookup"><span data-stu-id="16023-1356">cod.</span></span> <span data-ttu-id="16023-1357">seguranca cod。</span><span class="sxs-lookup"><span data-stu-id="16023-1357">seguranca cod.</span></span> <span data-ttu-id="16023-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1358">segurança</span></span>
- <span data-ttu-id="16023-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="16023-1359">cód.</span></span> <span data-ttu-id="16023-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1360">seguranca</span></span>
- <span data-ttu-id="16023-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1361">cód segurança</span></span>
- <span data-ttu-id="16023-1362">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="16023-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1363">cód seguranca</span></span>
- <span data-ttu-id="16023-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="16023-1364">número de verificação</span></span>
- <span data-ttu-id="16023-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="16023-1365">numero de verificacao</span></span>
- <span data-ttu-id="16023-1366">ablん f</span><span class="sxs-lookup"><span data-stu-id="16023-1366">ablauf</span></span>
- <span data-ttu-id="16023-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="16023-1367">gültig bis</span></span>
- <span data-ttu-id="16023-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16023-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="16023-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="16023-1369">gultig bis</span></span>
- <span data-ttu-id="16023-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16023-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="16023-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="16023-1371">scadenza</span></span>
- <span data-ttu-id="16023-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="16023-1372">data scad</span></span>
- <span data-ttu-id="16023-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="16023-1373">fecha de expiracion</span></span>
- <span data-ttu-id="16023-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="16023-1374">fecha de venc</span></span>
- <span data-ttu-id="16023-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="16023-1375">vencimiento</span></span>
- <span data-ttu-id="16023-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="16023-1376">válido hasta</span></span>
- <span data-ttu-id="16023-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="16023-1377">valido hasta</span></span>
- <span data-ttu-id="16023-1378">vto</span><span class="sxs-lookup"><span data-stu-id="16023-1378">vto</span></span>
- <span data-ttu-id="16023-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="16023-1379">data de expiração</span></span>
- <span data-ttu-id="16023-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="16023-1380">data de expiracao</span></span>
- <span data-ttu-id="16023-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="16023-1381">data em que expira</span></span>
- <span data-ttu-id="16023-1382">validade</span><span class="sxs-lookup"><span data-stu-id="16023-1382">validade</span></span>
- <span data-ttu-id="16023-1383">valor は</span><span class="sxs-lookup"><span data-stu-id="16023-1383">valor</span></span>
- <span data-ttu-id="16023-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="16023-1384">vencimento</span></span>
- <span data-ttu-id="16023-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="16023-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="16023-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="16023-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="16023-1387">amex</span><span class="sxs-lookup"><span data-stu-id="16023-1387">amex</span></span>
- <span data-ttu-id="16023-1388">american express</span><span class="sxs-lookup"><span data-stu-id="16023-1388">american express</span></span>
- <span data-ttu-id="16023-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="16023-1389">americanexpress</span></span>
- <span data-ttu-id="16023-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="16023-1390">Visa</span></span>
- <span data-ttu-id="16023-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="16023-1391">mastercard</span></span>
- <span data-ttu-id="16023-1392">master card</span><span class="sxs-lookup"><span data-stu-id="16023-1392">master card</span></span>
- <span data-ttu-id="16023-1393">mc</span><span class="sxs-lookup"><span data-stu-id="16023-1393">mc</span></span> 
- <span data-ttu-id="16023-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="16023-1394">mastercards</span></span>
- <span data-ttu-id="16023-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="16023-1395">master cards</span></span>
- <span data-ttu-id="16023-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="16023-1396">diner's Club</span></span>
- <span data-ttu-id="16023-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="16023-1397">diners club</span></span>
- <span data-ttu-id="16023-1398">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="16023-1398">dinersclub</span></span>
- <span data-ttu-id="16023-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="16023-1399">discover card</span></span>
- <span data-ttu-id="16023-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="16023-1400">discovercard</span></span>
- <span data-ttu-id="16023-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="16023-1401">discover cards</span></span>
- <span data-ttu-id="16023-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="16023-1402">JCB</span></span>
- <span data-ttu-id="16023-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="16023-1403">japanese card bureau</span></span>
- <span data-ttu-id="16023-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="16023-1404">carte blanche</span></span>
- <span data-ttu-id="16023-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="16023-1405">carteblanche</span></span>
- <span data-ttu-id="16023-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="16023-1406">credit card</span></span>
- <span data-ttu-id="16023-1407">]#</span><span class="sxs-lookup"><span data-stu-id="16023-1407">cc#</span></span>
- <span data-ttu-id="16023-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="16023-1408">cc#:</span></span>
- <span data-ttu-id="16023-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="16023-1409">expiration date</span></span>
- <span data-ttu-id="16023-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="16023-1410">exp date</span></span>
- <span data-ttu-id="16023-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="16023-1411">expiry date</span></span>
- <span data-ttu-id="16023-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="16023-1412">date d’expiration</span></span>
- <span data-ttu-id="16023-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="16023-1413">date d'exp</span></span>
- <span data-ttu-id="16023-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="16023-1414">date expiration</span></span>
- <span data-ttu-id="16023-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="16023-1415">bank card</span></span>
- <span data-ttu-id="16023-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="16023-1416">bankcard</span></span>
- <span data-ttu-id="16023-1417">card number</span><span class="sxs-lookup"><span data-stu-id="16023-1417">card number</span></span>
- <span data-ttu-id="16023-1418">card num</span><span class="sxs-lookup"><span data-stu-id="16023-1418">card num</span></span>
- <span data-ttu-id="16023-1419">カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-1419">cardnumber</span></span>
- <span data-ttu-id="16023-1420">カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-1420">cardnumbers</span></span>
- <span data-ttu-id="16023-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="16023-1421">card numbers</span></span>
- <span data-ttu-id="16023-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="16023-1422">creditcard</span></span>
- <span data-ttu-id="16023-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="16023-1423">credit cards</span></span>
- <span data-ttu-id="16023-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="16023-1424">creditcards</span></span>
- <span data-ttu-id="16023-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="16023-1425">ccn</span></span>
- <span data-ttu-id="16023-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="16023-1426">card holder</span></span>
- <span data-ttu-id="16023-1427">所有者</span><span class="sxs-lookup"><span data-stu-id="16023-1427">cardholder</span></span>
- <span data-ttu-id="16023-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="16023-1428">card holders</span></span>
- <span data-ttu-id="16023-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="16023-1429">cardholders</span></span>
- <span data-ttu-id="16023-1430">check card</span><span class="sxs-lookup"><span data-stu-id="16023-1430">check card</span></span>
- <span data-ttu-id="16023-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="16023-1431">checkcard</span></span>
- <span data-ttu-id="16023-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="16023-1432">check cards</span></span>
- <span data-ttu-id="16023-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="16023-1433">checkcards</span></span>
- <span data-ttu-id="16023-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="16023-1434">debit card</span></span>
- <span data-ttu-id="16023-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="16023-1435">debitcard</span></span>
- <span data-ttu-id="16023-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="16023-1436">debit cards</span></span>
- <span data-ttu-id="16023-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="16023-1437">debitcards</span></span>
- <span data-ttu-id="16023-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="16023-1438">atm card</span></span>
- <span data-ttu-id="16023-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="16023-1439">atmcard</span></span>
- <span data-ttu-id="16023-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="16023-1440">atm cards</span></span>
- <span data-ttu-id="16023-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="16023-1441">atmcards</span></span>
- <span data-ttu-id="16023-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="16023-1442">enroute</span></span>
- <span data-ttu-id="16023-1443">en route</span><span class="sxs-lookup"><span data-stu-id="16023-1443">en route</span></span>
- <span data-ttu-id="16023-1444">card type</span><span class="sxs-lookup"><span data-stu-id="16023-1444">card type</span></span>
- <span data-ttu-id="16023-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="16023-1445">carte bancaire</span></span>
- <span data-ttu-id="16023-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="16023-1446">carte de crédit</span></span>
- <span data-ttu-id="16023-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="16023-1447">carte de credit</span></span>
- <span data-ttu-id="16023-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="16023-1448">numéro de carte</span></span>
- <span data-ttu-id="16023-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="16023-1449">numero de carte</span></span>
- <span data-ttu-id="16023-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="16023-1450">nº de la carte</span></span>
- <span data-ttu-id="16023-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="16023-1451">nº de carte</span></span>
- <span data-ttu-id="16023-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="16023-1452">kreditkarte</span></span>
- <span data-ttu-id="16023-1453">karte</span><span class="sxs-lookup"><span data-stu-id="16023-1453">karte</span></span>
- <span data-ttu-id="16023-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="16023-1454">karteninhaber</span></span>
- <span data-ttu-id="16023-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="16023-1455">karteninhabers</span></span>
- <span data-ttu-id="16023-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="16023-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="16023-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="16023-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="16023-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="16023-1458">kreditkartentyp</span></span>
- <span data-ttu-id="16023-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="16023-1459">eigentümername</span></span>
- <span data-ttu-id="16023-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="16023-1460">kartennr</span></span> 
- <span data-ttu-id="16023-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="16023-1461">kartennummer</span></span>
- <span data-ttu-id="16023-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="16023-1462">kreditkartennummer</span></span>
- <span data-ttu-id="16023-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="16023-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="16023-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="16023-1464">carta di credito</span></span>
- <span data-ttu-id="16023-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="16023-1465">carta credito</span></span>
- <span data-ttu-id="16023-1466">carta</span><span class="sxs-lookup"><span data-stu-id="16023-1466">carta</span></span>
- <span data-ttu-id="16023-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="16023-1467">n carta</span></span>
- <span data-ttu-id="16023-1468">nr.</span><span class="sxs-lookup"><span data-stu-id="16023-1468">nr.</span></span> <span data-ttu-id="16023-1469">carta</span><span class="sxs-lookup"><span data-stu-id="16023-1469">carta</span></span>
- <span data-ttu-id="16023-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="16023-1470">nr carta</span></span>
- <span data-ttu-id="16023-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="16023-1471">numero carta</span></span>
- <span data-ttu-id="16023-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="16023-1472">numero della carta</span></span>
- <span data-ttu-id="16023-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="16023-1473">numero di carta</span></span>
- <span data-ttu-id="16023-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="16023-1474">tarjeta credito</span></span>
- <span data-ttu-id="16023-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="16023-1475">tarjeta de credito</span></span>
- <span data-ttu-id="16023-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="16023-1476">tarjeta crédito</span></span>
- <span data-ttu-id="16023-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="16023-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="16023-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="16023-1478">tarjeta de atm</span></span>
- <span data-ttu-id="16023-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="16023-1479">tarjeta atm</span></span>
- <span data-ttu-id="16023-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="16023-1480">tarjeta debito</span></span>
- <span data-ttu-id="16023-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="16023-1481">tarjeta de debito</span></span>
- <span data-ttu-id="16023-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="16023-1482">tarjeta débito</span></span>
- <span data-ttu-id="16023-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="16023-1483">tarjeta de débito</span></span>
- <span data-ttu-id="16023-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1484">nº de tarjeta</span></span>
- <span data-ttu-id="16023-1485">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1485">no.</span></span> <span data-ttu-id="16023-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1486">de tarjeta</span></span>
- <span data-ttu-id="16023-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1487">no de tarjeta</span></span>
- <span data-ttu-id="16023-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1488">numero de tarjeta</span></span>
- <span data-ttu-id="16023-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1489">número de tarjeta</span></span>
- <span data-ttu-id="16023-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="16023-1490">tarjeta no</span></span>
- <span data-ttu-id="16023-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="16023-1491">tarjetahabiente</span></span>
- <span data-ttu-id="16023-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="16023-1492">cartão de crédito</span></span>
- <span data-ttu-id="16023-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="16023-1493">cartão de credito</span></span>
- <span data-ttu-id="16023-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="16023-1494">cartao de crédito</span></span>
- <span data-ttu-id="16023-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="16023-1495">cartao de credito</span></span>
- <span data-ttu-id="16023-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="16023-1496">cartão de débito</span></span>
- <span data-ttu-id="16023-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="16023-1497">cartao de débito</span></span>
- <span data-ttu-id="16023-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="16023-1498">cartão de debito</span></span>
- <span data-ttu-id="16023-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="16023-1499">cartao de debito</span></span>
- <span data-ttu-id="16023-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="16023-1500">débito automático</span></span>
- <span data-ttu-id="16023-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="16023-1501">debito automatico</span></span>
- <span data-ttu-id="16023-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1502">número do cartão</span></span>
- <span data-ttu-id="16023-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1503">numero do cartão</span></span> 
- <span data-ttu-id="16023-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1504">número do cartao</span></span>
- <span data-ttu-id="16023-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1505">numero do cartao</span></span>
- <span data-ttu-id="16023-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1506">número de cartão</span></span>
- <span data-ttu-id="16023-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1507">numero de cartão</span></span>
- <span data-ttu-id="16023-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1508">número de cartao</span></span>
- <span data-ttu-id="16023-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1509">numero de cartao</span></span>
- <span data-ttu-id="16023-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1510">nº do cartão</span></span>
- <span data-ttu-id="16023-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1511">nº do cartao</span></span>
- <span data-ttu-id="16023-1512">n °</span><span class="sxs-lookup"><span data-stu-id="16023-1512">nº.</span></span> <span data-ttu-id="16023-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1513">do cartão</span></span>
- <span data-ttu-id="16023-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1514">no do cartão</span></span>
- <span data-ttu-id="16023-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1515">no do cartao</span></span>
- <span data-ttu-id="16023-1516">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1516">no.</span></span> <span data-ttu-id="16023-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1517">do cartão</span></span>
- <span data-ttu-id="16023-1518">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1518">no.</span></span> <span data-ttu-id="16023-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="16023-1520">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="16023-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1521">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1521">Format</span></span>

<span data-ttu-id="16023-1522">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1523">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1523">Pattern</span></span>

<span data-ttu-id="16023-1524">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1525">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1525">Checksum</span></span>

<span data-ttu-id="16023-1526">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1527">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1527">Definition</span></span>

<span data-ttu-id="16023-1528">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1529">関数 Func_croatia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1530">Keyword_croatia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1531">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="16023-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="16023-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="16023-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="16023-1533">Croatian identity card</span></span>
- <span data-ttu-id="16023-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="16023-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="16023-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="16023-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1536">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1536">Format</span></span>

<span data-ttu-id="16023-1537">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1538">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1538">Pattern</span></span>

<span data-ttu-id="16023-1539">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-1539">11 digits:</span></span>
- <span data-ttu-id="16023-1540">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1540">10 digits</span></span> 
- <span data-ttu-id="16023-1541">最終桁は、国際的なデータ交換のためのチェックディジットです。 HR は11桁の数字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="16023-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1542">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1542">Checksum</span></span>

<span data-ttu-id="16023-1543">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1544">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1544">Definition</span></span>

<span data-ttu-id="16023-1545">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1546">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1547">Keyword_croatia_oib_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="16023-1548">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1548">The checksum passes.</span></span>

<span data-ttu-id="16023-1549">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1550">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1551">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1552">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="16023-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="16023-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="16023-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="16023-1554">Personal Identification Number</span></span>
- <span data-ttu-id="16023-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="16023-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="16023-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="16023-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="16023-1557">チェコの個人 Id 番号</span><span class="sxs-lookup"><span data-stu-id="16023-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1558">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1558">Format</span></span>

<span data-ttu-id="16023-1559">省略可能なスラッシュ (古い形式) を含む9桁の数字 (省略可能)。スラッシュ (新しい形式)</span><span class="sxs-lookup"><span data-stu-id="16023-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1560">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1560">Pattern</span></span>

<span data-ttu-id="16023-1561">9桁の数字 (古い形式):</span><span class="sxs-lookup"><span data-stu-id="16023-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="16023-1562">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1562">Nine digits</span></span>

<span data-ttu-id="16023-1563">または</span><span class="sxs-lookup"><span data-stu-id="16023-1563">OR</span></span>

- <span data-ttu-id="16023-1564">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="16023-1565">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-1565">A forward slash</span></span>
- <span data-ttu-id="16023-1566">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1566">Three digits</span></span>

<span data-ttu-id="16023-1567">10桁の数字 (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="16023-1567">10 digits (new format):</span></span>
- <span data-ttu-id="16023-1568">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1568">10 digits</span></span>

<span data-ttu-id="16023-1569">または</span><span class="sxs-lookup"><span data-stu-id="16023-1569">OR</span></span>

- <span data-ttu-id="16023-1570">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="16023-1571">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-1571">A forward slash</span></span> 
- <span data-ttu-id="16023-1572">4桁の数字 (最後の桁はチェックディジット)</span><span class="sxs-lookup"><span data-stu-id="16023-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1573">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1573">Checksum</span></span>

<span data-ttu-id="16023-1574">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1575">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1575">Definition</span></span>

<span data-ttu-id="16023-1576">DLP ポリシーは85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_czech_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="16023-1577">Keyword_czech_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="16023-1578">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="16023-1579">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1579">Keywords</span></span>

- <span data-ttu-id="16023-1580">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="16023-1580">czech personal identity number</span></span>
- <span data-ttu-id="16023-1581">Rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="16023-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="16023-1582">	Denmark Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="16023-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1583">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1583">Format</span></span>

<span data-ttu-id="16023-1584">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1585">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1585">Pattern</span></span>

<span data-ttu-id="16023-1586">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-1586">10 digits:</span></span>
- <span data-ttu-id="16023-1587">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="16023-1588">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-1588">A hyphen</span></span> 
- <span data-ttu-id="16023-1589">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="16023-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1590">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1590">Checksum</span></span>

<span data-ttu-id="16023-1591">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1592">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1592">Definition</span></span>

<span data-ttu-id="16023-1593">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_denmark_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="16023-1594">Keyword_denmark_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="16023-1595">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1596">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="16023-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="16023-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="16023-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="16023-1598">Personal Identification Number</span></span>
- <span data-ttu-id="16023-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="16023-1599">CPR</span></span>
- <span data-ttu-id="16023-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="16023-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="16023-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="16023-1602">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1603">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1603">Format</span></span>

<span data-ttu-id="16023-1604">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1605">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1605">Pattern</span></span>

<span data-ttu-id="16023-1606">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="16023-1607">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="16023-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="16023-1608">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="16023-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="16023-1609">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="16023-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1610">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1610">Checksum</span></span>

<span data-ttu-id="16023-1611">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1612">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1612">Definition</span></span>

<span data-ttu-id="16023-1613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1614">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1615">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1616">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1616">Keywords</span></span>

<span data-ttu-id="16023-1617">なし</span><span class="sxs-lookup"><span data-stu-id="16023-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="16023-1618">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1619">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1619">Format</span></span>

<span data-ttu-id="16023-1620">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1621">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1621">Pattern</span></span>

<span data-ttu-id="16023-1622">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="16023-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1623">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1623">Checksum</span></span>

<span data-ttu-id="16023-1624">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1625">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1625">Definition</span></span>

<span data-ttu-id="16023-1626">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1627">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1628">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="16023-1629">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="16023-1630">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="16023-1631">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="16023-1632">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="16023-1633">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16023-1634">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1635">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="16023-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="16023-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="16023-1637">account number</span><span class="sxs-lookup"><span data-stu-id="16023-1637">account number</span></span> 
- <span data-ttu-id="16023-1638">card number</span><span class="sxs-lookup"><span data-stu-id="16023-1638">card number</span></span> 
- <span data-ttu-id="16023-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="16023-1639">card no.</span></span> 
- <span data-ttu-id="16023-1640">security number</span><span class="sxs-lookup"><span data-stu-id="16023-1640">security number</span></span> 
- <span data-ttu-id="16023-1641">]#</span><span class="sxs-lookup"><span data-stu-id="16023-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="16023-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="16023-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="16023-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="16023-1643">acct nbr</span></span> 
- <span data-ttu-id="16023-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="16023-1644">acct num</span></span> 
- <span data-ttu-id="16023-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="16023-1645">acct no</span></span> 
- <span data-ttu-id="16023-1646">american express</span><span class="sxs-lookup"><span data-stu-id="16023-1646">american express</span></span> 
- <span data-ttu-id="16023-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="16023-1647">americanexpress</span></span> 
- <span data-ttu-id="16023-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="16023-1648">americano espresso</span></span> 
- <span data-ttu-id="16023-1649">amex</span><span class="sxs-lookup"><span data-stu-id="16023-1649">amex</span></span> 
- <span data-ttu-id="16023-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="16023-1650">atm card</span></span> 
- <span data-ttu-id="16023-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="16023-1651">atm cards</span></span> 
- <span data-ttu-id="16023-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="16023-1652">atm kaart</span></span> 
- <span data-ttu-id="16023-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="16023-1653">atmcard</span></span> 
- <span data-ttu-id="16023-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="16023-1654">atmcards</span></span> 
- <span data-ttu-id="16023-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="16023-1655">atmkaart</span></span> 
- <span data-ttu-id="16023-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="16023-1656">atmkaarten</span></span> 
- <span data-ttu-id="16023-1657"># # の連絡先</span><span class="sxs-lookup"><span data-stu-id="16023-1657">bancontact</span></span> 
- <span data-ttu-id="16023-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="16023-1658">bank card</span></span> 
- <span data-ttu-id="16023-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="16023-1659">bankkaart</span></span> 
- <span data-ttu-id="16023-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="16023-1660">card holder</span></span> 
- <span data-ttu-id="16023-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="16023-1661">card holders</span></span> 
- <span data-ttu-id="16023-1662">card num</span><span class="sxs-lookup"><span data-stu-id="16023-1662">card num</span></span> 
- <span data-ttu-id="16023-1663">card number</span><span class="sxs-lookup"><span data-stu-id="16023-1663">card number</span></span> 
- <span data-ttu-id="16023-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="16023-1664">card numbers</span></span> 
- <span data-ttu-id="16023-1665">card type</span><span class="sxs-lookup"><span data-stu-id="16023-1665">card type</span></span> 
- <span data-ttu-id="16023-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="16023-1666">cardano numerico</span></span> 
- <span data-ttu-id="16023-1667">所有者</span><span class="sxs-lookup"><span data-stu-id="16023-1667">cardholder</span></span> 
- <span data-ttu-id="16023-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="16023-1668">cardholders</span></span> 
- <span data-ttu-id="16023-1669">カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-1669">cardnumber</span></span> 
- <span data-ttu-id="16023-1670">カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-1670">cardnumbers</span></span> 
- <span data-ttu-id="16023-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="16023-1671">carta bianca</span></span> 
- <span data-ttu-id="16023-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="16023-1672">carta credito</span></span> 
- <span data-ttu-id="16023-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="16023-1673">carta di credito</span></span> 
- <span data-ttu-id="16023-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="16023-1674">cartao de credito</span></span> 
- <span data-ttu-id="16023-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="16023-1675">cartao de crédito</span></span> 
- <span data-ttu-id="16023-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="16023-1676">cartao de debito</span></span> 
- <span data-ttu-id="16023-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="16023-1677">cartao de débito</span></span> 
- <span data-ttu-id="16023-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="16023-1678">carte bancaire</span></span> 
- <span data-ttu-id="16023-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="16023-1679">carte blanche</span></span> 
- <span data-ttu-id="16023-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="16023-1680">carte bleue</span></span> 
- <span data-ttu-id="16023-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="16023-1681">carte de credit</span></span> 
- <span data-ttu-id="16023-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="16023-1682">carte de crédit</span></span> 
- <span data-ttu-id="16023-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="16023-1683">carte di credito</span></span> 
- <span data-ttu-id="16023-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="16023-1684">carteblanche</span></span> 
- <span data-ttu-id="16023-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="16023-1685">cartão de credito</span></span> 
- <span data-ttu-id="16023-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="16023-1686">cartão de crédito</span></span> 
- <span data-ttu-id="16023-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="16023-1687">cartão de debito</span></span> 
- <span data-ttu-id="16023-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="16023-1688">cartão de débito</span></span> 
- <span data-ttu-id="16023-1689">cb</span><span class="sxs-lookup"><span data-stu-id="16023-1689">cb</span></span> 
- <span data-ttu-id="16023-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="16023-1690">ccn</span></span> 
- <span data-ttu-id="16023-1691">check card</span><span class="sxs-lookup"><span data-stu-id="16023-1691">check card</span></span> 
- <span data-ttu-id="16023-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="16023-1692">check cards</span></span> 
- <span data-ttu-id="16023-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="16023-1693">checkcard</span></span>
- <span data-ttu-id="16023-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="16023-1694">checkcards</span></span> 
- <span data-ttu-id="16023-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="16023-1695">chequekaart</span></span> 
- <span data-ttu-id="16023-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="16023-1696">cirrus</span></span> 
- <span data-ttu-id="16023-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="16023-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="16023-1698">lekaart の方法</span><span class="sxs-lookup"><span data-stu-id="16023-1698">controlekaart</span></span> 
- <span data-ttu-id="16023-1699">lekaar10 の場合</span><span class="sxs-lookup"><span data-stu-id="16023-1699">controlekaarten</span></span> 
- <span data-ttu-id="16023-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="16023-1700">credit card</span></span> 
- <span data-ttu-id="16023-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="16023-1701">credit cards</span></span> 
- <span data-ttu-id="16023-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="16023-1702">creditcard</span></span> 
- <span data-ttu-id="16023-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="16023-1703">creditcards</span></span> 
- <span data-ttu-id="16023-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="16023-1704">debetkaart</span></span> 
- <span data-ttu-id="16023-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="16023-1705">debetkaarten</span></span> 
- <span data-ttu-id="16023-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="16023-1706">debit card</span></span> 
- <span data-ttu-id="16023-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="16023-1707">debit cards</span></span> 
- <span data-ttu-id="16023-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="16023-1708">debitcard</span></span> 
- <span data-ttu-id="16023-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="16023-1709">debitcards</span></span> 
- <span data-ttu-id="16023-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="16023-1710">debito automatico</span></span> 
- <span data-ttu-id="16023-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="16023-1711">diners club</span></span> 
- <span data-ttu-id="16023-1712">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="16023-1712">dinersclub</span></span> 
- <span data-ttu-id="16023-1713">開示</span><span class="sxs-lookup"><span data-stu-id="16023-1713">discover</span></span> 
- <span data-ttu-id="16023-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="16023-1714">discover card</span></span> 
- <span data-ttu-id="16023-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="16023-1715">discover cards</span></span> 
- <span data-ttu-id="16023-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="16023-1716">discovercard</span></span> 
- <span data-ttu-id="16023-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="16023-1717">discovercards</span></span> 
- <span data-ttu-id="16023-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="16023-1718">débito automático</span></span>
- <span data-ttu-id="16023-1719">edc</span><span class="sxs-lookup"><span data-stu-id="16023-1719">edc</span></span> 
- <span data-ttu-id="16023-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="16023-1720">eigentümername</span></span> 
- <span data-ttu-id="16023-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="16023-1721">european debit card</span></span> 
- <span data-ttu-id="16023-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="16023-1722">hoofdkaart</span></span> 
- <span data-ttu-id="16023-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="16023-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="16023-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="16023-1724">in viaggio</span></span> 
- <span data-ttu-id="16023-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="16023-1725">japanese card bureau</span></span> 
- <span data-ttu-id="16023-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="16023-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="16023-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="16023-1727">jcb</span></span> 
- <span data-ttu-id="16023-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="16023-1728">kaart</span></span> 
- <span data-ttu-id="16023-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="16023-1729">kaart num</span></span> 
- <span data-ttu-id="16023-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="16023-1730">kaartaantal</span></span> 
- <span data-ttu-id="16023-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="16023-1731">kaartaantallen</span></span> 
- <span data-ttu-id="16023-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="16023-1732">kaarthouder</span></span> 
- <span data-ttu-id="16023-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="16023-1733">kaarthouders</span></span> 
- <span data-ttu-id="16023-1734">karte</span><span class="sxs-lookup"><span data-stu-id="16023-1734">karte</span></span>  
- <span data-ttu-id="16023-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="16023-1735">karteninhaber</span></span> 
- <span data-ttu-id="16023-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="16023-1736">karteninhabers</span></span>
- <span data-ttu-id="16023-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="16023-1737">kartennr</span></span> 
- <span data-ttu-id="16023-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="16023-1738">kartennummer</span></span> 
- <span data-ttu-id="16023-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="16023-1739">kreditkarte</span></span> 
- <span data-ttu-id="16023-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="16023-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="16023-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="16023-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="16023-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="16023-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="16023-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="16023-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="16023-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="16023-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="16023-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="16023-1745">maestro</span></span> 
- <span data-ttu-id="16023-1746">master card</span><span class="sxs-lookup"><span data-stu-id="16023-1746">master card</span></span> 
- <span data-ttu-id="16023-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="16023-1747">master cards</span></span> 
- <span data-ttu-id="16023-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="16023-1748">mastercard</span></span> 
- <span data-ttu-id="16023-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="16023-1749">mastercards</span></span> 
- <span data-ttu-id="16023-1750">mc</span><span class="sxs-lookup"><span data-stu-id="16023-1750">mc</span></span> 
- <span data-ttu-id="16023-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="16023-1751">mister cash</span></span> 
- <span data-ttu-id="16023-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="16023-1752">n carta</span></span> 
- <span data-ttu-id="16023-1753">carta</span><span class="sxs-lookup"><span data-stu-id="16023-1753">carta</span></span> 
- <span data-ttu-id="16023-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1754">no de tarjeta</span></span> 
- <span data-ttu-id="16023-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1755">no do cartao</span></span> 
- <span data-ttu-id="16023-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1756">no do cartão</span></span> 
- <span data-ttu-id="16023-1757">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1757">no.</span></span> <span data-ttu-id="16023-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1758">de tarjeta</span></span> 
- <span data-ttu-id="16023-1759">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1759">no.</span></span> <span data-ttu-id="16023-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1760">do cartao</span></span> 
- <span data-ttu-id="16023-1761">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1761">no.</span></span> <span data-ttu-id="16023-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1762">do cartão</span></span> 
- <span data-ttu-id="16023-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="16023-1763">nr carta</span></span> 
- <span data-ttu-id="16023-1764">nr.</span><span class="sxs-lookup"><span data-stu-id="16023-1764">nr.</span></span> <span data-ttu-id="16023-1765">carta</span><span class="sxs-lookup"><span data-stu-id="16023-1765">carta</span></span> 
- <span data-ttu-id="16023-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1766">numeri di scheda</span></span> 
- <span data-ttu-id="16023-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="16023-1767">numero carta</span></span> 
- <span data-ttu-id="16023-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1768">numero de cartao</span></span> 
- <span data-ttu-id="16023-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="16023-1769">numero de carte</span></span> 
- <span data-ttu-id="16023-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1770">numero de cartão</span></span> 
- <span data-ttu-id="16023-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1771">numero de tarjeta</span></span>
- <span data-ttu-id="16023-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="16023-1772">numero della carta</span></span> 
- <span data-ttu-id="16023-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="16023-1773">numero di carta</span></span> 
- <span data-ttu-id="16023-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1774">numero di scheda</span></span> 
- <span data-ttu-id="16023-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1775">numero do cartao</span></span> 
- <span data-ttu-id="16023-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1776">numero do cartão</span></span> 
- <span data-ttu-id="16023-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="16023-1777">numéro de carte</span></span> 
- <span data-ttu-id="16023-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="16023-1778">nº carta</span></span> 
- <span data-ttu-id="16023-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="16023-1779">nº de carte</span></span> 
- <span data-ttu-id="16023-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="16023-1780">nº de la carte</span></span> 
- <span data-ttu-id="16023-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="16023-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1782">nº do cartao</span></span> 
- <span data-ttu-id="16023-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1783">nº do cartão</span></span> 
- <span data-ttu-id="16023-1784">n °</span><span class="sxs-lookup"><span data-stu-id="16023-1784">nº.</span></span> <span data-ttu-id="16023-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1785">do cartão</span></span> 
- <span data-ttu-id="16023-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1786">número de cartao</span></span> 
- <span data-ttu-id="16023-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="16023-1787">número de cartão</span></span> 
- <span data-ttu-id="16023-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="16023-1788">número de tarjeta</span></span> 
- <span data-ttu-id="16023-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="16023-1789">número do cartao</span></span> 
- <span data-ttu-id="16023-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="16023-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="16023-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="16023-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="16023-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="16023-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="16023-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="16023-1793">scheda della banca</span></span> 
- <span data-ttu-id="16023-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="16023-1794">scheda di controllo</span></span> 
- <span data-ttu-id="16023-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="16023-1795">scheda di debito</span></span> 
- <span data-ttu-id="16023-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="16023-1796">scheda matrice</span></span> 
- <span data-ttu-id="16023-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="16023-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="16023-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="16023-1798">schede di controllo</span></span> 
- <span data-ttu-id="16023-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="16023-1799">schede di debito</span></span> 
- <span data-ttu-id="16023-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="16023-1800">schede matrici</span></span> 
- <span data-ttu-id="16023-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="16023-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="16023-1802">scoprono le schede</span></span> 
- <span data-ttu-id="16023-1803">単独</span><span class="sxs-lookup"><span data-stu-id="16023-1803">solo</span></span> 
- <span data-ttu-id="16023-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1804">supporti di scheda</span></span> 
- <span data-ttu-id="16023-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1805">supporto di scheda</span></span> 
- <span data-ttu-id="16023-1806">switch</span><span class="sxs-lookup"><span data-stu-id="16023-1806">switch</span></span> 
- <span data-ttu-id="16023-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="16023-1807">tarjeta atm</span></span> 
- <span data-ttu-id="16023-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="16023-1808">tarjeta credito</span></span> 
- <span data-ttu-id="16023-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="16023-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="16023-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="16023-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="16023-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="16023-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="16023-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="16023-1812">tarjeta debito</span></span> 
- <span data-ttu-id="16023-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="16023-1813">tarjeta no</span></span>
- <span data-ttu-id="16023-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="16023-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="16023-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1815">tipo della scheda</span></span> 
- <span data-ttu-id="16023-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="16023-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="16023-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1817">scheda</span></span> 
- <span data-ttu-id="16023-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="16023-1818">v pay</span></span> 
- <span data-ttu-id="16023-1819">v-支払い</span><span class="sxs-lookup"><span data-stu-id="16023-1819">v-pay</span></span> 
- <span data-ttu-id="16023-1820">visa</span><span class="sxs-lookup"><span data-stu-id="16023-1820">visa</span></span> 
- <span data-ttu-id="16023-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="16023-1821">visa plus</span></span> 
- <span data-ttu-id="16023-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="16023-1822">visa electron</span></span> 
- <span data-ttu-id="16023-1823">visto</span><span class="sxs-lookup"><span data-stu-id="16023-1823">visto</span></span> 
- <span data-ttu-id="16023-1824">visum</span><span class="sxs-lookup"><span data-stu-id="16023-1824">visum</span></span> 
- <span data-ttu-id="16023-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="16023-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="16023-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="16023-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="16023-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="16023-1827">card identification number</span></span>
- <span data-ttu-id="16023-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="16023-1828">card verification</span></span> 
- <span data-ttu-id="16023-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="16023-1829">cardi la verifica</span></span> 
- <span data-ttu-id="16023-1830">cid</span><span class="sxs-lookup"><span data-stu-id="16023-1830">cid</span></span> 
- <span data-ttu-id="16023-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="16023-1831">cod seg</span></span> 
- <span data-ttu-id="16023-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1832">cod seguranca</span></span> 
- <span data-ttu-id="16023-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1833">cod segurança</span></span> 
- <span data-ttu-id="16023-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="16023-1834">cod sicurezza</span></span> 
- <span data-ttu-id="16023-1835">cod.</span><span class="sxs-lookup"><span data-stu-id="16023-1835">cod.</span></span> <span data-ttu-id="16023-1836">seg</span><span class="sxs-lookup"><span data-stu-id="16023-1836">seg</span></span> 
- <span data-ttu-id="16023-1837">cod.</span><span class="sxs-lookup"><span data-stu-id="16023-1837">cod.</span></span> <span data-ttu-id="16023-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1838">seguranca</span></span> 
- <span data-ttu-id="16023-1839">cod.</span><span class="sxs-lookup"><span data-stu-id="16023-1839">cod.</span></span> <span data-ttu-id="16023-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1840">segurança</span></span> 
- <span data-ttu-id="16023-1841">cod.</span><span class="sxs-lookup"><span data-stu-id="16023-1841">cod.</span></span> <span data-ttu-id="16023-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="16023-1842">sicurezza</span></span> 
- <span data-ttu-id="16023-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="16023-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="16023-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="16023-1844">codice di verifica</span></span> 
- <span data-ttu-id="16023-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="16023-1845">codigo</span></span> 
- <span data-ttu-id="16023-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="16023-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1847">codigo de segurança</span></span> 
- <span data-ttu-id="16023-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="16023-1848">crittogramma</span></span> 
- <span data-ttu-id="16023-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="16023-1849">cryptogram</span></span> 
- <span data-ttu-id="16023-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="16023-1850">cryptogramme</span></span> 
- <span data-ttu-id="16023-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="16023-1851">cv2</span></span> 
- <span data-ttu-id="16023-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="16023-1852">cvc</span></span> 
- <span data-ttu-id="16023-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="16023-1853">cvc2</span></span> 
- <span data-ttu-id="16023-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="16023-1854">cvn</span></span> 
- <span data-ttu-id="16023-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="16023-1855">cvv</span></span> 
- <span data-ttu-id="16023-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="16023-1856">cvv2</span></span> 
- <span data-ttu-id="16023-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1857">cód seguranca</span></span> 
- <span data-ttu-id="16023-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1858">cód segurança</span></span> 
- <span data-ttu-id="16023-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="16023-1859">cód.</span></span> <span data-ttu-id="16023-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1860">seguranca</span></span> 
- <span data-ttu-id="16023-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="16023-1861">cód.</span></span> <span data-ttu-id="16023-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1862">segurança</span></span> 
- <span data-ttu-id="16023-1863">código</span><span class="sxs-lookup"><span data-stu-id="16023-1863">código</span></span> 
- <span data-ttu-id="16023-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="16023-1864">código de seguranca</span></span> 
- <span data-ttu-id="16023-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="16023-1865">código de segurança</span></span> 
- <span data-ttu-id="16023-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="16023-1866">de kaart controle</span></span> 
- <span data-ttu-id="16023-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="16023-1867">geeft nr uit</span></span> 
- <span data-ttu-id="16023-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="16023-1868">issue no</span></span> 
- <span data-ttu-id="16023-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="16023-1869">issue number</span></span> 
- <span data-ttu-id="16023-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="16023-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="16023-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="16023-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="16023-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="16023-1873">kwestieaantal</span></span> 
- <span data-ttu-id="16023-1874">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1874">no.</span></span> <span data-ttu-id="16023-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="16023-1875">dell'edizione</span></span> 
- <span data-ttu-id="16023-1876">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-1876">no.</span></span> <span data-ttu-id="16023-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="16023-1877">di sicurezza</span></span> 
- <span data-ttu-id="16023-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="16023-1878">numero de securite</span></span> 
- <span data-ttu-id="16023-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="16023-1879">numero de verificacao</span></span> 
- <span data-ttu-id="16023-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="16023-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="16023-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="16023-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="16023-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="16023-1882">scheda</span></span> 
- <span data-ttu-id="16023-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="16023-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="16023-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="16023-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="16023-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="16023-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="16023-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="16023-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="16023-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="16023-1887">número de verificação</span></span> 
- <span data-ttu-id="16023-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="16023-1888">perno il blocco</span></span> 
- <span data-ttu-id="16023-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="16023-1889">pin block</span></span> 
- <span data-ttu-id="16023-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="16023-1890">prufziffer</span></span> 
- <span data-ttu-id="16023-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="16023-1891">prüfziffer</span></span> 
- <span data-ttu-id="16023-1892">security code</span><span class="sxs-lookup"><span data-stu-id="16023-1892">security code</span></span> 
- <span data-ttu-id="16023-1893">security no</span><span class="sxs-lookup"><span data-stu-id="16023-1893">security no</span></span> 
- <span data-ttu-id="16023-1894">security number</span><span class="sxs-lookup"><span data-stu-id="16023-1894">security number</span></span> 
- <span data-ttu-id="16023-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="16023-1895">sicherheits kode</span></span> 
- <span data-ttu-id="16023-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="16023-1896">sicherheitscode</span></span> 
- <span data-ttu-id="16023-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="16023-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="16023-1898">speldblok</span></span> 
- <span data-ttu-id="16023-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="16023-1899">veiligheid nr</span></span> 
- <span data-ttu-id="16023-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="16023-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="16023-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="16023-1901">veiligheidscode</span></span> 
- <span data-ttu-id="16023-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="16023-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="16023-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="16023-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="16023-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="16023-1905">ablん f</span><span class="sxs-lookup"><span data-stu-id="16023-1905">ablauf</span></span> 
- <span data-ttu-id="16023-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="16023-1906">data de expiracao</span></span> 
- <span data-ttu-id="16023-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="16023-1907">data de expiração</span></span> 
- <span data-ttu-id="16023-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="16023-1908">data del exp</span></span> 
- <span data-ttu-id="16023-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="16023-1909">data di exp</span></span> 
- <span data-ttu-id="16023-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="16023-1910">data di scadenza</span></span> 
- <span data-ttu-id="16023-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="16023-1911">data em que expira</span></span> 
- <span data-ttu-id="16023-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="16023-1912">data scad</span></span> 
- <span data-ttu-id="16023-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="16023-1913">data scadenza</span></span> 
- <span data-ttu-id="16023-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="16023-1914">date de validité</span></span> 
- <span data-ttu-id="16023-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="16023-1915">datum afloop</span></span> 
- <span data-ttu-id="16023-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="16023-1916">datum van exp</span></span> 
- <span data-ttu-id="16023-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="16023-1917">de afloop</span></span> 
- <span data-ttu-id="16023-1918">espira</span><span class="sxs-lookup"><span data-stu-id="16023-1918">espira</span></span> 
- <span data-ttu-id="16023-1919">espira</span><span class="sxs-lookup"><span data-stu-id="16023-1919">espira</span></span> 
- <span data-ttu-id="16023-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="16023-1920">exp date</span></span> 
- <span data-ttu-id="16023-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="16023-1921">exp datum</span></span> 
- <span data-ttu-id="16023-1922">nntp</span><span class="sxs-lookup"><span data-stu-id="16023-1922">expiration</span></span> 
- <span data-ttu-id="16023-1923">無効</span><span class="sxs-lookup"><span data-stu-id="16023-1923">expire</span></span> 
- <span data-ttu-id="16023-1924">期限</span><span class="sxs-lookup"><span data-stu-id="16023-1924">expires</span></span> 
- <span data-ttu-id="16023-1925">期限</span><span class="sxs-lookup"><span data-stu-id="16023-1925">expiry</span></span> 
- <span data-ttu-id="16023-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="16023-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="16023-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="16023-1927">fecha de venc</span></span> 
- <span data-ttu-id="16023-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="16023-1928">gultig bis</span></span> 
- <span data-ttu-id="16023-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16023-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="16023-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="16023-1930">gültig bis</span></span> 
- <span data-ttu-id="16023-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="16023-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="16023-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="16023-1932">la scadenza</span></span> 
- <span data-ttu-id="16023-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="16023-1933">scadenza</span></span> 
- <span data-ttu-id="16023-1934">valable</span><span class="sxs-lookup"><span data-stu-id="16023-1934">valable</span></span> 
- <span data-ttu-id="16023-1935">validade</span><span class="sxs-lookup"><span data-stu-id="16023-1935">validade</span></span> 
- <span data-ttu-id="16023-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="16023-1936">valido hasta</span></span> 
- <span data-ttu-id="16023-1937">valor は</span><span class="sxs-lookup"><span data-stu-id="16023-1937">valor</span></span> 
- <span data-ttu-id="16023-1938">venc</span><span class="sxs-lookup"><span data-stu-id="16023-1938">venc</span></span> 
- <span data-ttu-id="16023-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="16023-1939">vencimento</span></span> 
- <span data-ttu-id="16023-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="16023-1940">vencimiento</span></span> 
- <span data-ttu-id="16023-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="16023-1941">verloopt</span></span> 
- <span data-ttu-id="16023-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="16023-1942">vervaldag</span></span> 
- <span data-ttu-id="16023-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="16023-1943">vervaldatum</span></span> 
- <span data-ttu-id="16023-1944">vto</span><span class="sxs-lookup"><span data-stu-id="16023-1944">vto</span></span> 
- <span data-ttu-id="16023-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="16023-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="16023-1946">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-1946">EU Driver's License Number</span></span>

<span data-ttu-id="16023-1947">詳細については、「 [EU ドライバーのライセンス番号の機密情報の種類](eu-driver-s-license-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="16023-1948">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-1948">EU National Identification Number</span></span>

<span data-ttu-id="16023-1949">詳細については、「 [EU 国立 Id 番号の機密情報の種類](eu-national-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="16023-1950">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-1950">EU Passport Number</span></span>

<span data-ttu-id="16023-1951">詳細については、「 [EU パスポート番号の機密情報の種類](eu-passport-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="16023-1952">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="16023-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="16023-1953">詳細については、「 [EU 社会保障番号または同等の ID の機密情報の種類](eu-social-security-number-or-equivalent-id.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="16023-1954">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="16023-1955">詳細については、「 [EU 税務識別番号の機密情報の種類](eu-tax-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="16023-1956">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="16023-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="16023-1957">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1957">Format</span></span>

<span data-ttu-id="16023-1958">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="16023-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1959">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1959">Pattern</span></span>

<span data-ttu-id="16023-1960">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="16023-1961">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="16023-1962">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="16023-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="16023-1963">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="16023-1964">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="16023-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1965">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1965">Checksum</span></span>

<span data-ttu-id="16023-1966">はい</span><span class="sxs-lookup"><span data-stu-id="16023-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1967">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1967">Definition</span></span>

<span data-ttu-id="16023-1968">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1969">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1970">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="16023-1971">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1972">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1972">Keywords</span></span>

- <span data-ttu-id="16023-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="16023-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="16023-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="16023-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="16023-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="16023-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="16023-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="16023-1976">Personbeteckning</span></span>
- <span data-ttu-id="16023-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="16023-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="16023-1978">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-1978">Finland Passport Number</span></span>

<span data-ttu-id="16023-1979">次の9つの文字と数字のパターンの組み合わせを書式設定します。9桁の文字 (大文字小文字を区別しない)、7桁のチェックサムを定義しません。 DLP ポリシーは75% で、この種類の機密情報がある場合に、300文字の近接: 正規表現 Regex_finland_passport_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="16023-1980">Keyword_finland_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="16023-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="16023-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="16023-1982">キーワード Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="16023-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="16023-1983">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-1984">Format</span><span class="sxs-lookup"><span data-stu-id="16023-1984">Format</span></span>

<span data-ttu-id="16023-1985">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-1986">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-1986">Pattern</span></span>

<span data-ttu-id="16023-1987">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-1988">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-1988">Checksum</span></span>

<span data-ttu-id="16023-1989">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-1990">定義</span><span class="sxs-lookup"><span data-stu-id="16023-1990">Definition</span></span>

<span data-ttu-id="16023-1991">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-1992">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-1993">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="16023-1994">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="16023-1995">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-1996">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="16023-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16023-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="16023-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="16023-1998">drivers licence</span></span>
- <span data-ttu-id="16023-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="16023-1999">drivers license</span></span>
- <span data-ttu-id="16023-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="16023-2000">driving licence</span></span>
- <span data-ttu-id="16023-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="16023-2001">driving license</span></span>
- <span data-ttu-id="16023-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="16023-2002">permis de conduire</span></span>
- <span data-ttu-id="16023-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="16023-2003">licence number</span></span>
- <span data-ttu-id="16023-2004">license number</span><span class="sxs-lookup"><span data-stu-id="16023-2004">license number</span></span>
- <span data-ttu-id="16023-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="16023-2005">licence numbers</span></span>
- <span data-ttu-id="16023-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="16023-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="16023-2007">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="16023-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2008">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2008">Format</span></span>

<span data-ttu-id="16023-2009">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2010">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2010">Pattern</span></span>

<span data-ttu-id="16023-2011">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2012">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2012">Checksum</span></span>

<span data-ttu-id="16023-2013">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2014">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2014">Definition</span></span>

<span data-ttu-id="16023-2015">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2016">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2017">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2017">Keywords</span></span>

<span data-ttu-id="16023-2018">なし</span><span class="sxs-lookup"><span data-stu-id="16023-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="16023-2019">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2020">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2020">Format</span></span>

<span data-ttu-id="16023-2021">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="16023-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2022">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2022">Pattern</span></span>

<span data-ttu-id="16023-2023">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="16023-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="16023-2024">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2024">Two digits</span></span> 
- <span data-ttu-id="16023-2025">2 つの文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="16023-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="16023-2026">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2027">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2027">Checksum</span></span>

<span data-ttu-id="16023-2028">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2029">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2029">Definition</span></span>

<span data-ttu-id="16023-2030">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2031">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2032">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2033">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="16023-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16023-2034">Keyword_passport</span></span>

- <span data-ttu-id="16023-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16023-2035">Passport Number</span></span>
- <span data-ttu-id="16023-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="16023-2036">Passport No</span></span>
- <span data-ttu-id="16023-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="16023-2037">Passport #</span></span>
- <span data-ttu-id="16023-2038">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="16023-2038">Passport#</span></span>
- <span data-ttu-id="16023-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="16023-2039">PassportID</span></span>
- <span data-ttu-id="16023-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="16023-2040">Passportno</span></span>
- <span data-ttu-id="16023-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16023-2041">passportnumber</span></span>
- <span data-ttu-id="16023-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="16023-2042">パスポート</span></span>
- <span data-ttu-id="16023-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-2043">パスポート番号</span></span>
- <span data-ttu-id="16023-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16023-2044">パスポートのNum</span></span>
- <span data-ttu-id="16023-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="16023-2045">パスポート ＃</span></span> 
- <span data-ttu-id="16023-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16023-2046">Numéro de passeport</span></span>
- <span data-ttu-id="16023-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16023-2047">Passeport n °</span></span>
- <span data-ttu-id="16023-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16023-2048">Passeport Non</span></span>
- <span data-ttu-id="16023-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16023-2049">Passeport #</span></span>
- <span data-ttu-id="16023-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="16023-2050">Passeport#</span></span>
- <span data-ttu-id="16023-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16023-2051">PasseportNon</span></span>
- <span data-ttu-id="16023-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16023-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="16023-2053">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="16023-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2054">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2054">Format</span></span>

<span data-ttu-id="16023-2055">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2056">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2056">Pattern</span></span>

<span data-ttu-id="16023-2057">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="16023-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="16023-2058">13桁の数字の後にスペースを続け、2桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="16023-2059">または</span><span class="sxs-lookup"><span data-stu-id="16023-2059">or</span></span>
- <span data-ttu-id="16023-2060">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2061">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2061">Checksum</span></span>

<span data-ttu-id="16023-2062">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2063">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2063">Definition</span></span>

<span data-ttu-id="16023-2064">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2065">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2066">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="16023-2067">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2067">The checksum passes.</span></span>

<span data-ttu-id="16023-2068">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2069">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2070">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="16023-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="16023-2071">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2071">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2072">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="16023-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="16023-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="16023-2074">insee</span><span class="sxs-lookup"><span data-stu-id="16023-2074">insee</span></span>
- <span data-ttu-id="16023-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="16023-2075">securité sociale</span></span>
- <span data-ttu-id="16023-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="16023-2076">securite sociale</span></span>
- <span data-ttu-id="16023-2077">national id</span><span class="sxs-lookup"><span data-stu-id="16023-2077">national id</span></span>
- <span data-ttu-id="16023-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="16023-2078">national identification</span></span>
- <span data-ttu-id="16023-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="16023-2079">numéro d'identité</span></span>
- <span data-ttu-id="16023-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="16023-2080">no d'identité</span></span>
- <span data-ttu-id="16023-2081">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-2081">no.</span></span> <span data-ttu-id="16023-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="16023-2082">d'identité</span></span>
- <span data-ttu-id="16023-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="16023-2083">numero d'identite</span></span>
- <span data-ttu-id="16023-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="16023-2084">no d'identite</span></span>
- <span data-ttu-id="16023-2085">違います。</span><span class="sxs-lookup"><span data-stu-id="16023-2085">no.</span></span> <span data-ttu-id="16023-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="16023-2086">d'identite</span></span>
- <span data-ttu-id="16023-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="16023-2087">social security number</span></span>
- <span data-ttu-id="16023-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="16023-2088">social security code</span></span>
- <span data-ttu-id="16023-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="16023-2089">social insurance number</span></span>
- <span data-ttu-id="16023-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="16023-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="16023-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="16023-2091">d'identité nationale</span></span>
- <span data-ttu-id="16023-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="16023-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="16023-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="16023-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="16023-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="16023-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="16023-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="16023-2095">numéro de sécu</span></span>
- <span data-ttu-id="16023-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="16023-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="16023-2097">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2098">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2098">Format</span></span>

<span data-ttu-id="16023-2099">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2100">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2100">Pattern</span></span>

<span data-ttu-id="16023-2101">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="16023-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="16023-2102">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="16023-2102">A digit or letter</span></span> 
- <span data-ttu-id="16023-2103">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2103">Two digits</span></span> 
- <span data-ttu-id="16023-2104">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="16023-2104">Six digits or letters</span></span> 
- <span data-ttu-id="16023-2105">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2105">A digit</span></span> 
- <span data-ttu-id="16023-2106">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="16023-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2107">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2107">Checksum</span></span>

<span data-ttu-id="16023-2108">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2109">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2109">Definition</span></span>

<span data-ttu-id="16023-2110">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2111">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2112">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="16023-2113">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="16023-2114">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="16023-2115">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="16023-2116">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2116">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2117">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="16023-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16023-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="16023-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="16023-2119">Führerschein</span></span>
- <span data-ttu-id="16023-2120">Futex</span><span class="sxs-lookup"><span data-stu-id="16023-2120">Fuhrerschein</span></span>
- <span data-ttu-id="16023-2121">Futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="16023-2121">Fuehrerschein</span></span>
- <span data-ttu-id="16023-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="16023-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="16023-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="16023-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="16023-2125">Führerschein-</span></span> 
- <span data-ttu-id="16023-2126">Futex (中)</span><span class="sxs-lookup"><span data-stu-id="16023-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="16023-2127">Futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="16023-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="16023-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16023-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="16023-2129">Futex がある Hていません Einnumnr</span><span class="sxs-lookup"><span data-stu-id="16023-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="16023-2130">Futex の Ehの再リリース/Einnumnr</span><span class="sxs-lookup"><span data-stu-id="16023-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="16023-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16023-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="16023-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16023-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="16023-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16023-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="16023-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16023-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="16023-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16023-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="16023-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16023-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="16023-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16023-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="16023-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16023-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="16023-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16023-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="16023-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="16023-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="16023-2141">Futex がある Hていません Einnumnr</span><span class="sxs-lookup"><span data-stu-id="16023-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="16023-2142">Futex の Ehの再リリース/Einnumnr</span><span class="sxs-lookup"><span data-stu-id="16023-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="16023-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16023-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="16023-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16023-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="16023-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="16023-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="16023-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16023-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="16023-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16023-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="16023-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="16023-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="16023-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16023-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="16023-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16023-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="16023-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="16023-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="16023-2152">DL</span><span class="sxs-lookup"><span data-stu-id="16023-2152">DL</span></span> 
- <span data-ttu-id="16023-2153">DL</span><span class="sxs-lookup"><span data-stu-id="16023-2153">DLS</span></span>
- <span data-ttu-id="16023-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="16023-2154">Driv Lic</span></span> 
- <span data-ttu-id="16023-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="16023-2155">Driv Licen</span></span> 
- <span data-ttu-id="16023-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="16023-2156">Driv License</span></span>
- <span data-ttu-id="16023-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2157">Driv Licenses</span></span> 
- <span data-ttu-id="16023-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="16023-2158">Driv Licence</span></span> 
- <span data-ttu-id="16023-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="16023-2159">Driv Licences</span></span> 
- <span data-ttu-id="16023-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="16023-2160">Driv Lic</span></span> 
- <span data-ttu-id="16023-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="16023-2161">Driver Licen</span></span> 
- <span data-ttu-id="16023-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="16023-2162">Driver License</span></span> 
- <span data-ttu-id="16023-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2163">Driver Licenses</span></span> 
- <span data-ttu-id="16023-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="16023-2164">Driver Licence</span></span> 
- <span data-ttu-id="16023-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="16023-2165">Driver Licences</span></span> 
- <span data-ttu-id="16023-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16023-2166">Drivers Lic</span></span> 
- <span data-ttu-id="16023-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="16023-2167">Drivers Licen</span></span> 
- <span data-ttu-id="16023-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16023-2168">Drivers License</span></span> 
- <span data-ttu-id="16023-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="16023-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="16023-2170">Drivers Licence</span></span> 
- <span data-ttu-id="16023-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="16023-2171">Drivers Licences</span></span> 
- <span data-ttu-id="16023-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16023-2172">Driver's Lic</span></span> 
- <span data-ttu-id="16023-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="16023-2173">Driver's Licen</span></span> 
- <span data-ttu-id="16023-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16023-2174">Driver's License</span></span> 
- <span data-ttu-id="16023-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="16023-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="16023-2176">Driver's Licence</span></span> 
- <span data-ttu-id="16023-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="16023-2177">Driver's Licences</span></span> 
- <span data-ttu-id="16023-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="16023-2178">Driving Lic</span></span> 
- <span data-ttu-id="16023-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="16023-2179">Driving Licen</span></span> 
- <span data-ttu-id="16023-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="16023-2180">Driving License</span></span> 
- <span data-ttu-id="16023-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2181">Driving Licenses</span></span> 
- <span data-ttu-id="16023-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="16023-2182">Driving Licence</span></span> 
- <span data-ttu-id="16023-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="16023-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="16023-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="16023-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="16023-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16023-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="16023-2186">Nr-Futex</span><span class="sxs-lookup"><span data-stu-id="16023-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="16023-2187">"Nr" という Futex</span><span class="sxs-lookup"><span data-stu-id="16023-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="16023-2188">Führerschein</span><span class="sxs-lookup"><span data-stu-id="16023-2188">No-Führerschein</span></span> 
- <span data-ttu-id="16023-2189">(Futex なし)</span><span class="sxs-lookup"><span data-stu-id="16023-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="16023-2190">その他の Ehの場合</span><span class="sxs-lookup"><span data-stu-id="16023-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="16023-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16023-2191">N-Führerschein</span></span> 
- <span data-ttu-id="16023-2192">N の Futex</span><span class="sxs-lookup"><span data-stu-id="16023-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="16023-2193">N 桁の Ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="16023-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="16023-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16023-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="16023-2195">Nr-Futex</span><span class="sxs-lookup"><span data-stu-id="16023-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="16023-2196">"Nr" という Futex</span><span class="sxs-lookup"><span data-stu-id="16023-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="16023-2197">Führerschein</span><span class="sxs-lookup"><span data-stu-id="16023-2197">No-Führerschein</span></span> 
- <span data-ttu-id="16023-2198">(Futex なし)</span><span class="sxs-lookup"><span data-stu-id="16023-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="16023-2199">その他の Ehの場合</span><span class="sxs-lookup"><span data-stu-id="16023-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="16023-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="16023-2200">N-Führerschein</span></span> 
- <span data-ttu-id="16023-2201">N の Futex</span><span class="sxs-lookup"><span data-stu-id="16023-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="16023-2202">N 桁の Ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="16023-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="16023-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16023-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="16023-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="16023-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="16023-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="16023-2205">ausstellungsort</span></span>
- <span data-ttu-id="16023-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="16023-2206">ausstellende behöde</span></span>
- <span data-ttu-id="16023-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="16023-2207">ausstellende behorde</span></span>
- <span data-ttu-id="16023-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="16023-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="16023-2209">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2210">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2210">Format</span></span>

<span data-ttu-id="16023-2211">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="16023-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2212">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2212">Pattern</span></span>

<span data-ttu-id="16023-2213">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="16023-2214">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="16023-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="16023-2215">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2215">Three digits</span></span> 
- <span data-ttu-id="16023-2216">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="16023-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="16023-2217">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2218">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2218">Checksum</span></span>

<span data-ttu-id="16023-2219">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2220">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2220">Definition</span></span>

<span data-ttu-id="16023-2221">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2222">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2223">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="16023-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="16023-2224">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2224">The checksum passes.</span></span>

<span data-ttu-id="16023-2225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2226">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2227">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="16023-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="16023-2228">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2228">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2229">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="16023-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="16023-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="16023-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="16023-2231">reisepass</span></span>
- <span data-ttu-id="16023-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="16023-2232">reisepasse</span></span>
- <span data-ttu-id="16023-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2233">reisepassnummer</span></span>
- <span data-ttu-id="16023-2234">サインアウト</span><span class="sxs-lookup"><span data-stu-id="16023-2234">passport</span></span>
- <span data-ttu-id="16023-2235">passport</span><span class="sxs-lookup"><span data-stu-id="16023-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="16023-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="16023-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="16023-2237">ge気流 tsdatum</span><span class="sxs-lookup"><span data-stu-id="16023-2237">geburtsdatum</span></span>
- <span data-ttu-id="16023-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="16023-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="16023-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="16023-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="16023-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="16023-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="16023-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="16023-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="16023-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="16023-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="16023-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="16023-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="16023-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="16023-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="16023-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="16023-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="16023-2246">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="16023-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2247">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2247">Format</span></span>

<span data-ttu-id="16023-2248">2010年11月1日以降: 9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="16023-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="16023-2249">1987年4月1日から2010年10月31日まで:10 桁</span><span class="sxs-lookup"><span data-stu-id="16023-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2250">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2250">Pattern</span></span>

<span data-ttu-id="16023-2251">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="16023-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="16023-2252">1 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="16023-2253">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2253">Eight digits</span></span>

<span data-ttu-id="16023-2254">1987年4月1日から2010年10月31日まで。</span><span class="sxs-lookup"><span data-stu-id="16023-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="16023-2255">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2256">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2256">Checksum</span></span>

<span data-ttu-id="16023-2257">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2258">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2258">Definition</span></span>

<span data-ttu-id="16023-2259">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2260">正規表現 Regex_germany_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2261">Keyword_germany_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2262">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="16023-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="16023-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="16023-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="16023-2264">Identity Card</span></span>
- <span data-ttu-id="16023-2265">ID</span><span class="sxs-lookup"><span data-stu-id="16023-2265">ID</span></span>
- <span data-ttu-id="16023-2266">Fim</span><span class="sxs-lookup"><span data-stu-id="16023-2266">Identification</span></span>
- <span data-ttu-id="16023-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="16023-2267">Personalausweis</span></span>
- <span data-ttu-id="16023-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="16023-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="16023-2269">Ausweis</span></span>
- <span data-ttu-id="16023-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="16023-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="16023-2271">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="16023-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="16023-2272">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2272">Format</span></span>

<span data-ttu-id="16023-2273">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="16023-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2274">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2274">Pattern</span></span>

<span data-ttu-id="16023-2275">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="16023-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="16023-2276">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="16023-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="16023-2277">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-2277">A dash</span></span> 
- <span data-ttu-id="16023-2278">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2278">Six digits</span></span>

<span data-ttu-id="16023-2279">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="16023-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="16023-2280">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="16023-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="16023-2281">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-2281">A dash</span></span> 
- <span data-ttu-id="16023-2282">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2283">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2283">Checksum</span></span>

<span data-ttu-id="16023-2284">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2285">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2285">Definition</span></span>

<span data-ttu-id="16023-2286">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2287">正規表現 Regex_greece_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2288">Keyword_greece_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2289">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="16023-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="16023-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="16023-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="16023-2291">Greek identity Card</span></span>
- <span data-ttu-id="16023-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="16023-2292">Tautotita</span></span>
- <span data-ttu-id="16023-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="16023-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="16023-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="16023-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="16023-2295">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2296">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2296">Format</span></span>

<span data-ttu-id="16023-2297">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="16023-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2298">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2298">Pattern</span></span>

<span data-ttu-id="16023-2299">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="16023-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="16023-2300">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="16023-2301">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2301">Six digits</span></span> 
- <span data-ttu-id="16023-2302">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="16023-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2303">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2303">Checksum</span></span>

<span data-ttu-id="16023-2304">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2305">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2305">Definition</span></span>

<span data-ttu-id="16023-2306">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2307">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2308">Keyword_hong_kong_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="16023-2309">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2309">The checksum passes.</span></span>

<span data-ttu-id="16023-2310">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2311">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2312">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2312">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2313">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="16023-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="16023-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="16023-2315">香港の id カード</span><span class="sxs-lookup"><span data-stu-id="16023-2315">hong kong identity card</span></span>
- <span data-ttu-id="16023-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="16023-2316">HKIDC</span></span>
- <span data-ttu-id="16023-2317">id card</span><span class="sxs-lookup"><span data-stu-id="16023-2317">id card</span></span>
- <span data-ttu-id="16023-2318">Identity card</span><span class="sxs-lookup"><span data-stu-id="16023-2318">identity card</span></span>
- <span data-ttu-id="16023-2319">hk の id カード</span><span class="sxs-lookup"><span data-stu-id="16023-2319">hk identity card</span></span>
- <span data-ttu-id="16023-2320">香港特別行政 id</span><span class="sxs-lookup"><span data-stu-id="16023-2320">hong kong id</span></span>
- <span data-ttu-id="16023-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2321">香港身份證</span></span>
- <span data-ttu-id="16023-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="16023-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2323">身份證</span></span>
- <span data-ttu-id="16023-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="16023-2324">身份証</span></span>
- <span data-ttu-id="16023-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="16023-2325">身分證</span></span>
- <span data-ttu-id="16023-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="16023-2326">身分証</span></span>
- <span data-ttu-id="16023-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="16023-2327">香港身份証</span></span>
- <span data-ttu-id="16023-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="16023-2328">香港身分證</span></span>
- <span data-ttu-id="16023-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="16023-2329">香港身分証</span></span>
- <span data-ttu-id="16023-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2330">香港身份證</span></span>
- <span data-ttu-id="16023-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2331">香港居民身份證</span></span>
- <span data-ttu-id="16023-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="16023-2332">香港居民身份証</span></span>
- <span data-ttu-id="16023-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="16023-2333">香港居民身分證</span></span>
- <span data-ttu-id="16023-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="16023-2334">香港居民身分証</span></span>
- <span data-ttu-id="16023-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16023-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="16023-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16023-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="16023-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16023-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="16023-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="16023-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="16023-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16023-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="16023-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16023-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="16023-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16023-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="16023-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="16023-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16023-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="16023-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16023-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="16023-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16023-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="16023-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="16023-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="16023-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="16023-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="16023-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="16023-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="16023-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="16023-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="16023-2351">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="16023-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2352">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2352">Format</span></span>

<span data-ttu-id="16023-2353">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="16023-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2354">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2354">Pattern</span></span>

<span data-ttu-id="16023-2355">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2355">10 letters or digits:</span></span>
- <span data-ttu-id="16023-2356">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="16023-2357">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2357">Four digits</span></span> 
- <span data-ttu-id="16023-2358">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="16023-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2359">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2359">Checksum</span></span>

<span data-ttu-id="16023-2360">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2361">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2361">Definition</span></span>

<span data-ttu-id="16023-2362">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2363">正規表現 Regex_india_permanent_account_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2364">Keyword_india_permanent_account_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="16023-2365">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2366">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="16023-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="16023-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="16023-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="16023-2369">ペン</span><span class="sxs-lookup"><span data-stu-id="16023-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="16023-2370">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2371">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2371">Format</span></span>

<span data-ttu-id="16023-2372">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2373">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2373">Pattern</span></span>

<span data-ttu-id="16023-2374">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2374">12 digits:</span></span>
- <span data-ttu-id="16023-2375">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2375">Four digits</span></span> 
- <span data-ttu-id="16023-2376">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2376">An optional space or dash</span></span> 
- <span data-ttu-id="16023-2377">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2377">Four digits</span></span> 
- <span data-ttu-id="16023-2378">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2378">An optional space or dash</span></span> 
- <span data-ttu-id="16023-2379">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="16023-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2380">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2380">Checksum</span></span>

<span data-ttu-id="16023-2381">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2382">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2382">Definition</span></span>

<span data-ttu-id="16023-2383">DLP ポリシーは85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="16023-2384">Keyword_india_aadhar からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="16023-2385">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2385">The checksum passes.</span></span>
<span data-ttu-id="16023-2386">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="16023-2387">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="16023-2388">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="16023-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="16023-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="16023-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="16023-2390">Aadhar</span></span>
- <span data-ttu-id="16023-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="16023-2391">Aadhaar</span></span>
- <span data-ttu-id="16023-2392">UID</span><span class="sxs-lookup"><span data-stu-id="16023-2392">UID</span></span>
- <span data-ttu-id="16023-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="16023-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="16023-2394">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2395">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2395">Format</span></span>

<span data-ttu-id="16023-2396">省略可能なピリオドを含む 16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2397">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2397">Pattern</span></span>

<span data-ttu-id="16023-2398">16 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2398">16 digits:</span></span>
- <span data-ttu-id="16023-2399">2 桁の行政区コード </span><span class="sxs-lookup"><span data-stu-id="16023-2399">Two-digit province code</span></span> 
- <span data-ttu-id="16023-2400">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2400">A period (optional)</span></span> 
- <span data-ttu-id="16023-2401">2 桁の行政区または市コード </span><span class="sxs-lookup"><span data-stu-id="16023-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="16023-2402">2 桁の分区コード </span><span class="sxs-lookup"><span data-stu-id="16023-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="16023-2403">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2403">A period (optional)</span></span> 
- <span data-ttu-id="16023-2404">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="16023-2405">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2405">A period (optional)</span></span> 
- <span data-ttu-id="16023-2406">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2407">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2407">Checksum</span></span>

<span data-ttu-id="16023-2408">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2409">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2409">Definition</span></span>

<span data-ttu-id="16023-2410">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2411">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2412">Keyword_indonesia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="16023-2413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2414">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2415">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="16023-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="16023-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="16023-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="16023-2417">KTP</span></span>
- <span data-ttu-id="16023-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="16023-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="16023-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="16023-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="16023-2420">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="16023-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2421">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2421">Format</span></span>

<span data-ttu-id="16023-2422">国コード (2 文字)、チェックディジット (2 桁)、および番号を bban 最大30文字)</span><span class="sxs-lookup"><span data-stu-id="16023-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2423">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2423">Pattern</span></span>

<span data-ttu-id="16023-2424">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="16023-2425">2文字の国コード</span><span class="sxs-lookup"><span data-stu-id="16023-2425">Two-letter country code</span></span>
- <span data-ttu-id="16023-2426">2つのチェックディジット (オプションのスペースが続く)</span><span class="sxs-lookup"><span data-stu-id="16023-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="16023-2427">1-7 4 つの文字または数字のグループ (スペースで区切ることができます)</span><span class="sxs-lookup"><span data-stu-id="16023-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="16023-2428">1 ～ 3 個の文字または数字</span><span class="sxs-lookup"><span data-stu-id="16023-2428">1-3 letters or digits</span></span>

<span data-ttu-id="16023-2429">各国の形式は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="16023-2429">The format for each country is slightly different.</span></span> <span data-ttu-id="16023-2430">IBAN 機密情報の種類には、次の60国が含まれています。</span><span class="sxs-lookup"><span data-stu-id="16023-2430">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="16023-2431">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、hu、gl、gr、hr、、ie、il、、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg</span><span class="sxs-lookup"><span data-stu-id="16023-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2432">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2432">Checksum</span></span>

<span data-ttu-id="16023-2433">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2434">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2434">Definition</span></span>

<span data-ttu-id="16023-2435">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2436">関数 Func_iban がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2437">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2438">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2438">Keywords</span></span>

<span data-ttu-id="16023-2439">なし</span><span class="sxs-lookup"><span data-stu-id="16023-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="16023-2440">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="16023-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="16023-2441">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="16023-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="16023-2442">IPv4:</span></span>
<span data-ttu-id="16023-2443">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="16023-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="16023-2444">IPv6</span><span class="sxs-lookup"><span data-stu-id="16023-2444">IPv6:</span></span>
<span data-ttu-id="16023-2445"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="16023-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2446">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2447">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2447">Checksum</span></span>

<span data-ttu-id="16023-2448">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2449">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2449">Definition</span></span>

<span data-ttu-id="16023-2450">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2451">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2452">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="16023-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="16023-2453">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2454">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2455">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="16023-2456">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2457">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2458">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="16023-2458">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2459">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="16023-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="16023-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="16023-2461">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="16023-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="16023-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="16023-2462">ip address</span></span> 
- <span data-ttu-id="16023-2463">ip addresses</span><span class="sxs-lookup"><span data-stu-id="16023-2463">ip addresses</span></span>
- <span data-ttu-id="16023-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="16023-2464">internet protocol</span></span>
- <span data-ttu-id="16023-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="16023-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="16023-2466">Diseases の国際分類 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="16023-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2467">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2467">Format</span></span>

<span data-ttu-id="16023-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="16023-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2469">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2469">Pattern</span></span>

<span data-ttu-id="16023-2470">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2471">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2471">Checksum</span></span>

<span data-ttu-id="16023-2472">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2473">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2473">Definition</span></span>

<span data-ttu-id="16023-2474">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2475">Dictionary_icd_10_updated からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="16023-2476">Dictionary_icd_10_codes からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="16023-2477">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2478">Dictionary_icd_10_ 更新されたキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="16023-2479">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2479">Keywords</span></span>

<span data-ttu-id="16023-2480">Dictionary_icd_10_updated キーワードディクショナリからの任意の用語。 [Diseases、10リビジョン、臨床修正 (icd-10-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="16023-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="16023-2481">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="16023-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="16023-2482">Dictionary_icd_10_codes キーワードディクショナリからの任意の用語。 [Diseases、10リビジョン、臨床修正 (icd-10-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="16023-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="16023-2483">この型は、説明ではなく、保険コードに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="16023-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="16023-2484">Diseases の国際分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="16023-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2485">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2485">Format</span></span>

<span data-ttu-id="16023-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="16023-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2487">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2487">Pattern</span></span>

<span data-ttu-id="16023-2488">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2489">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2489">Checksum</span></span>

<span data-ttu-id="16023-2490">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2491">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2491">Definition</span></span>

<span data-ttu-id="16023-2492">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2493">Dictionary_icd_9_updated からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="16023-2494">Dictionary_icd_9_codes からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="16023-2495">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2496">Dictionary_icd_9_updated からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2497">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2497">Keywords</span></span>

<span data-ttu-id="16023-2498">Dictionary_icd_9_updated キーワードディクショナリの任意の用語。 [Diseases、9リビジョン、臨床修正 (icd-9-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="16023-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="16023-2499">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="16023-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="16023-2500">Dictionary_icd_9_codes キーワードディクショナリの任意の用語。 [Diseases、9リビジョン、臨床修正 (icd-9-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="16023-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="16023-2501">この型は、説明ではなく、保険コードに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="16023-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="16023-2502">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2503">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2503">Format</span></span>

<span data-ttu-id="16023-2504">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="16023-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="16023-2505">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="16023-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="16023-2506">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="16023-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="16023-2507">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="16023-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2508">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2508">Pattern</span></span>

<span data-ttu-id="16023-2509">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="16023-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="16023-2510">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-2510">Seven digits</span></span> 
- <span data-ttu-id="16023-2511">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="16023-2512">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="16023-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="16023-2513">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-2513">Seven digits</span></span> 
- <span data-ttu-id="16023-2514">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="16023-2515">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="16023-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2516">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2516">Checksum</span></span>

<span data-ttu-id="16023-2517">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2518">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2518">Definition</span></span>

<span data-ttu-id="16023-2519">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2520">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2521">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-2521">One of the following is true:</span></span>
    - <span data-ttu-id="16023-2522">Keyword_ireland_pps からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="16023-2523">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="16023-2524">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2524">The checksum passes.</span></span>

<span data-ttu-id="16023-2525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2526">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2527">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2527">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2528">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="16023-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="16023-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="16023-2530">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="16023-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="16023-2531">PPS Number</span><span class="sxs-lookup"><span data-stu-id="16023-2531">PPS Number</span></span> 
- <span data-ttu-id="16023-2532">PPS Num</span><span class="sxs-lookup"><span data-stu-id="16023-2532">PPS Num</span></span> 
- <span data-ttu-id="16023-2533">PPS No.</span><span class="sxs-lookup"><span data-stu-id="16023-2533">PPS No.</span></span> 
- <span data-ttu-id="16023-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="16023-2534">PPS #</span></span> 
- <span data-ttu-id="16023-2535">PPS#</span><span class="sxs-lookup"><span data-stu-id="16023-2535">PPS#</span></span> 
- <span data-ttu-id="16023-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="16023-2536">PPSN</span></span> 
- <span data-ttu-id="16023-2537">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="16023-2537">Public Services Card</span></span> 
- <span data-ttu-id="16023-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="16023-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="16023-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="16023-2539">Uimh.</span></span> <span data-ttu-id="16023-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="16023-2540">PSP</span></span> 
- <span data-ttu-id="16023-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="16023-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="16023-2542">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2543">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2543">Format</span></span>

<span data-ttu-id="16023-2544">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2545">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2545">Pattern</span></span>

<span data-ttu-id="16023-2546">さ</span><span class="sxs-lookup"><span data-stu-id="16023-2546">Formatted:</span></span>
- <span data-ttu-id="16023-2547">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2547">Two digits</span></span> 
- <span data-ttu-id="16023-2548">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-2548">A dash</span></span> 
- <span data-ttu-id="16023-2549">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2549">Three digits</span></span> 
- <span data-ttu-id="16023-2550">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-2550">A dash</span></span> 
- <span data-ttu-id="16023-2551">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2551">Eight digits</span></span>

<span data-ttu-id="16023-2552">なし</span><span class="sxs-lookup"><span data-stu-id="16023-2552">Unformatted:</span></span>
- <span data-ttu-id="16023-2553">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2554">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2554">Checksum</span></span>

<span data-ttu-id="16023-2555">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2556">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2556">Definition</span></span>

<span data-ttu-id="16023-2557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2558">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2559">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2560">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="16023-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="16023-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="16023-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-2562">Bank Account Number</span></span> 
- <span data-ttu-id="16023-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="16023-2563">Bank Account</span></span> 
- <span data-ttu-id="16023-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-2564">Account Number</span></span> 
- <span data-ttu-id="16023-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="16023-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="16023-2566">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="16023-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="16023-2567">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2567">Format</span></span>

<span data-ttu-id="16023-2568">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2569">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2569">Pattern</span></span>

<span data-ttu-id="16023-2570">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2571">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2571">Checksum</span></span>

<span data-ttu-id="16023-2572">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2573">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2573">Definition</span></span>

<span data-ttu-id="16023-2574">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2575">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2576">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="16023-2577">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2577">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2578">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="16023-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="16023-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="16023-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="16023-2580">מספר זהות</span></span> 
- <span data-ttu-id="16023-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="16023-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="16023-2582">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2583">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2583">Format</span></span>

<span data-ttu-id="16023-2584">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2585">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2585">Pattern</span></span>

- <span data-ttu-id="16023-2586">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="16023-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="16023-2587">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="16023-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="16023-2588">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="16023-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="16023-2589">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="16023-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="16023-2590">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="16023-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2591">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2591">Checksum</span></span>

<span data-ttu-id="16023-2592">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2593">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2593">Definition</span></span>

<span data-ttu-id="16023-2594">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2595">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2596">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2597">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="16023-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16023-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="16023-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="16023-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="16023-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="16023-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="16023-2601">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2602">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2602">Format</span></span>

<span data-ttu-id="16023-2603">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2604">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2604">Pattern</span></span>

<span data-ttu-id="16023-2605">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="16023-2605">Bank account number:</span></span>
- <span data-ttu-id="16023-2606">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2606">Seven or eight digits</span></span>
- <span data-ttu-id="16023-2607">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="16023-2607">Bank account branch code:</span></span>
- <span data-ttu-id="16023-2608">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2608">Four digits</span></span> 
- <span data-ttu-id="16023-2609">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="16023-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="16023-2610">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2610">Three digits</span></span>

<span data-ttu-id="16023-2611">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2611">Checksum</span></span>

<span data-ttu-id="16023-2612">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2613">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2613">Definition</span></span>

<span data-ttu-id="16023-2614">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2615">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2616">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="16023-2617">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-2617">One of the following is true:</span></span>
- <span data-ttu-id="16023-2618">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2619">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="16023-2620">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2621">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2622">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2623">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="16023-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="16023-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="16023-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-2625">Checking Account Number</span></span> 
- <span data-ttu-id="16023-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="16023-2626">Checking Account</span></span> 
- <span data-ttu-id="16023-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="16023-2627">Checking Account #</span></span> 
- <span data-ttu-id="16023-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="16023-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-2629">Checking Acct #</span></span> 
- <span data-ttu-id="16023-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="16023-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-2631">Checking Account No.</span></span> 
- <span data-ttu-id="16023-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-2632">Bank Account Number</span></span> 
- <span data-ttu-id="16023-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="16023-2633">Bank Account</span></span> 
- <span data-ttu-id="16023-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="16023-2634">Bank Account #</span></span> 
- <span data-ttu-id="16023-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="16023-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-2636">Bank Acct #</span></span> 
- <span data-ttu-id="16023-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="16023-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-2638">Bank Account No.</span></span> 
- <span data-ttu-id="16023-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-2639">Savings Account Number</span></span> 
- <span data-ttu-id="16023-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="16023-2640">Savings Account</span></span> 
- <span data-ttu-id="16023-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="16023-2641">Savings Account #</span></span> 
- <span data-ttu-id="16023-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="16023-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-2643">Savings Acct #</span></span> 
- <span data-ttu-id="16023-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="16023-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-2645">Savings Account No.</span></span> 
- <span data-ttu-id="16023-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-2646">Debit Account Number</span></span> 
- <span data-ttu-id="16023-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="16023-2647">Debit Account</span></span> 
- <span data-ttu-id="16023-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="16023-2648">Debit Account #</span></span> 
- <span data-ttu-id="16023-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="16023-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-2650">Debit Acct #</span></span> 
- <span data-ttu-id="16023-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="16023-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-2652">Debit Account No.</span></span> 
- <span data-ttu-id="16023-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="16023-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="16023-2654">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="16023-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="16023-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="16023-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="16023-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="16023-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="16023-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="16023-2657">口座番号の確認</span></span> 
- <span data-ttu-id="16023-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2658">銀行口座番号</span></span> 
- <span data-ttu-id="16023-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="16023-2659">銀行口座</span></span> 
- <span data-ttu-id="16023-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="16023-2660">銀行口座＃</span></span> 
- <span data-ttu-id="16023-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="16023-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="16023-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="16023-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="16023-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="16023-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2664">銀行口座番号</span></span>
- <span data-ttu-id="16023-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="16023-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="16023-2666">預金口座</span></span> 
- <span data-ttu-id="16023-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="16023-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="16023-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="16023-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="16023-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="16023-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="16023-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="16023-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="16023-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="16023-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="16023-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2673">口座番号</span></span> 
- <span data-ttu-id="16023-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="16023-2674">口座番号＃</span></span> 
- <span data-ttu-id="16023-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="16023-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="16023-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="16023-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="16023-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="16023-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="16023-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="16023-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="16023-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="16023-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="16023-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="16023-2681">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2682">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2682">Format</span></span>

<span data-ttu-id="16023-2683">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2684">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2684">Pattern</span></span>

<span data-ttu-id="16023-2685">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2686">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2686">Checksum</span></span>

<span data-ttu-id="16023-2687">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2688">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2688">Definition</span></span>

<span data-ttu-id="16023-2689">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2690">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2691">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2692">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="16023-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="16023-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="16023-2694">dl#</span><span class="sxs-lookup"><span data-stu-id="16023-2694">dl#</span></span> 
- <span data-ttu-id="16023-2695">DL</span><span class="sxs-lookup"><span data-stu-id="16023-2695">DL＃</span></span> 
- <span data-ttu-id="16023-2696">dl#</span><span class="sxs-lookup"><span data-stu-id="16023-2696">dls#</span></span> 
- <span data-ttu-id="16023-2697">DL</span><span class="sxs-lookup"><span data-stu-id="16023-2697">DLS＃</span></span> 
- <span data-ttu-id="16023-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="16023-2698">driver license</span></span> 
- <span data-ttu-id="16023-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2699">driver licenses</span></span> 
- <span data-ttu-id="16023-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="16023-2700">drivers license</span></span> 
- <span data-ttu-id="16023-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="16023-2701">driver's license</span></span> 
- <span data-ttu-id="16023-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2702">drivers licenses</span></span> 
- <span data-ttu-id="16023-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="16023-2703">driver's licenses</span></span> 
- <span data-ttu-id="16023-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="16023-2704">driving licence</span></span> 
- <span data-ttu-id="16023-2705">そして#</span><span class="sxs-lookup"><span data-stu-id="16023-2705">lic#</span></span> 
- <span data-ttu-id="16023-2706">そして</span><span class="sxs-lookup"><span data-stu-id="16023-2706">LIC＃</span></span> 
- <span data-ttu-id="16023-2707">lics#</span><span class="sxs-lookup"><span data-stu-id="16023-2707">lics#</span></span> 
- <span data-ttu-id="16023-2708">state id</span><span class="sxs-lookup"><span data-stu-id="16023-2708">state id</span></span> 
- <span data-ttu-id="16023-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="16023-2709">state identification</span></span> 
- <span data-ttu-id="16023-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="16023-2710">state identification number</span></span> 
- <span data-ttu-id="16023-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="16023-2711">低所得国＃</span></span> 
- <span data-ttu-id="16023-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="16023-2712">免許証</span></span> 
- <span data-ttu-id="16023-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="16023-2713">状態ID</span></span>
- <span data-ttu-id="16023-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="16023-2714">状態の識別</span></span> 
- <span data-ttu-id="16023-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-2715">状態の識別番号</span></span> 
- <span data-ttu-id="16023-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="16023-2716">運転免許</span></span> 
- <span data-ttu-id="16023-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="16023-2717">運転免許証</span></span> 
- <span data-ttu-id="16023-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="16023-2719">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2720">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2720">Format</span></span>

<span data-ttu-id="16023-2721">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2722">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2722">Pattern</span></span>

<span data-ttu-id="16023-2723">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2724">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2724">Checksum</span></span>

<span data-ttu-id="16023-2725">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2726">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2726">Definition</span></span>

<span data-ttu-id="16023-2727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2728">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2729">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2730">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="16023-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="16023-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="16023-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="16023-2732">パスポート</span></span> 
- <span data-ttu-id="16023-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-2733">パスポート番号</span></span> 
- <span data-ttu-id="16023-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16023-2734">パスポートのNum</span></span> 
- <span data-ttu-id="16023-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="16023-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="16023-2736">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="16023-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2737">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2737">Format</span></span>

<span data-ttu-id="16023-2738">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2739">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2739">Pattern</span></span>

<span data-ttu-id="16023-2740">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2741">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2741">Checksum</span></span>

<span data-ttu-id="16023-2742">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2743">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2743">Definition</span></span>

<span data-ttu-id="16023-2744">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2745">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2746">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2747">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="16023-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="16023-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="16023-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="16023-2749">Resident Registration Number</span></span>
- <span data-ttu-id="16023-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="16023-2750">Resident Register Number</span></span> 
- <span data-ttu-id="16023-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="16023-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="16023-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="16023-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="16023-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="16023-2753">Resident Register No.</span></span> 
- <span data-ttu-id="16023-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="16023-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="16023-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="16023-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="16023-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="16023-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="16023-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="16023-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="16023-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="16023-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="16023-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="16023-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="16023-2760">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="16023-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2761">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2761">Format</span></span>

<span data-ttu-id="16023-2762">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2763">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2763">Pattern</span></span>

<span data-ttu-id="16023-2764">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2764">7-12 digits:</span></span>
- <span data-ttu-id="16023-2765">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2765">Four digits</span></span> 
- <span data-ttu-id="16023-2766">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="16023-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="16023-2767">6桁の数字または</span><span class="sxs-lookup"><span data-stu-id="16023-2767">Six digits OR</span></span>
- <span data-ttu-id="16023-2768">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2769">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2769">Checksum</span></span>

<span data-ttu-id="16023-2770">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2771">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2771">Definition</span></span>

<span data-ttu-id="16023-2772">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2773">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2774">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="16023-2775">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2776">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2777">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2777">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2778">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="16023-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="16023-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="16023-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="16023-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="16023-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="16023-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="16023-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="16023-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="16023-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="16023-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="16023-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="16023-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="16023-2785">日本の居住カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2786">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2786">Format</span></span>

<span data-ttu-id="16023-2787">12桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="16023-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2788">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2788">Pattern</span></span>

<span data-ttu-id="16023-2789">12桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2789">12 letters and digits:</span></span>
- <span data-ttu-id="16023-2790">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="16023-2791">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2791">Eight digits</span></span> 
- <span data-ttu-id="16023-2792">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2793">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2793">Checksum</span></span>

<span data-ttu-id="16023-2794">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2795">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2795">Definition</span></span>

<span data-ttu-id="16023-2796">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2797">正規表現 Regex_jp_residence_card_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2798">Keyword_jp_residence_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2799">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="16023-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="16023-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="16023-2801">居住カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-2801">Residence card number</span></span>
- <span data-ttu-id="16023-2802">住居カードなし</span><span class="sxs-lookup"><span data-stu-id="16023-2802">Residence card no</span></span>
- <span data-ttu-id="16023-2803">住居カード#</span><span class="sxs-lookup"><span data-stu-id="16023-2803">Residence card #</span></span>
- <span data-ttu-id="16023-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="16023-2805">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2806">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2806">Format</span></span>

<span data-ttu-id="16023-2807">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2808">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2808">Pattern</span></span>

<span data-ttu-id="16023-2809">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2809">12 digits:</span></span>
- <span data-ttu-id="16023-2810">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16023-2811">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2811">A dash (optional)</span></span> 
- <span data-ttu-id="16023-2812">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="16023-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="16023-2813">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2813">A dash (optional)</span></span> 
- <span data-ttu-id="16023-2814">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="16023-2814">Three random digits</span></span> 
- <span data-ttu-id="16023-2815">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="16023-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2816">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2816">Checksum</span></span>

<span data-ttu-id="16023-2817">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2818">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2818">Definition</span></span>

<span data-ttu-id="16023-2819">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2820">正規表現 Regex_malaysia_id_card_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2821">Keyword_malaysia_id_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2822">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="16023-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="16023-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="16023-2824">デジタルアプリケーションカード</span><span class="sxs-lookup"><span data-stu-id="16023-2824">digital application card</span></span>
- <span data-ttu-id="16023-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="16023-2825">i/c</span></span>
- <span data-ttu-id="16023-2826">i/c いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2826">i/c no</span></span>
- <span data-ttu-id="16023-2827">ic</span><span class="sxs-lookup"><span data-stu-id="16023-2827">ic</span></span>
- <span data-ttu-id="16023-2828">ic no</span><span class="sxs-lookup"><span data-stu-id="16023-2828">ic no</span></span>
- <span data-ttu-id="16023-2829">id card</span><span class="sxs-lookup"><span data-stu-id="16023-2829">id card</span></span>
- <span data-ttu-id="16023-2830">識別カード</span><span class="sxs-lookup"><span data-stu-id="16023-2830">identification Card</span></span>
- <span data-ttu-id="16023-2831">Identity card</span><span class="sxs-lookup"><span data-stu-id="16023-2831">identity card</span></span>
- <span data-ttu-id="16023-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="16023-2832">k/p</span></span>
- <span data-ttu-id="16023-2833">k/p no</span><span class="sxs-lookup"><span data-stu-id="16023-2833">k/p no</span></span>
- <span data-ttu-id="16023-2834">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="16023-2834">kad akuan diri</span></span>
- <span data-ttu-id="16023-2835">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="16023-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="16023-2836">kad の genalan マレーシア</span><span class="sxs-lookup"><span data-stu-id="16023-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="16023-2837">kp</span><span class="sxs-lookup"><span data-stu-id="16023-2837">kp</span></span>
- <span data-ttu-id="16023-2838">kp no</span><span class="sxs-lookup"><span data-stu-id="16023-2838">kp no</span></span>
- <span data-ttu-id="16023-2839">mykad</span><span class="sxs-lookup"><span data-stu-id="16023-2839">mykad</span></span>
- <span data-ttu-id="16023-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="16023-2840">mykas</span></span>
- <span data-ttu-id="16023-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="16023-2841">mykid</span></span>
- <span data-ttu-id="16023-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="16023-2842">mypr</span></span>
- <span data-ttu-id="16023-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="16023-2843">mytentera</span></span>
- <span data-ttu-id="16023-2844">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="16023-2844">malaysia identity card</span></span>
- <span data-ttu-id="16023-2845">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="16023-2845">malaysian identity card</span></span>
- <span data-ttu-id="16023-2846">nric</span><span class="sxs-lookup"><span data-stu-id="16023-2846">nric</span></span>
- <span data-ttu-id="16023-2847">個人識別カード</span><span class="sxs-lookup"><span data-stu-id="16023-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="16023-2848">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2849">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2849">Format</span></span>

<span data-ttu-id="16023-2850">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2851">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2851">Pattern</span></span>

<span data-ttu-id="16023-2852">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2852">8-9 digits:</span></span>
- <span data-ttu-id="16023-2853">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2853">Three digits</span></span> 
- <span data-ttu-id="16023-2854">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2854">A space (optional)</span></span> 
- <span data-ttu-id="16023-2855">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2855">Three digits</span></span> 
- <span data-ttu-id="16023-2856">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="16023-2856">A space (optional)</span></span> 
- <span data-ttu-id="16023-2857">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2858">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2858">Checksum</span></span>

<span data-ttu-id="16023-2859">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2860">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2860">Definition</span></span>

<span data-ttu-id="16023-2861">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2862">関数 Func_netherlands_bsn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2863">Keyword_netherlands_bsn からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="16023-2864">関数 Func_eu_date2 は、日付を正しい日付形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="16023-2865">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2865">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2866">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="16023-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="16023-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="16023-2868">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="16023-2868">Citizen service number</span></span> 
- <span data-ttu-id="16023-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="16023-2869">BSN</span></span> 
- <span data-ttu-id="16023-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="16023-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="16023-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="16023-2871">Sofinummer</span></span> 
- <span data-ttu-id="16023-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="16023-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="16023-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="16023-2874">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="16023-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2875">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2875">Format</span></span>

<span data-ttu-id="16023-2876">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2877">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2877">Pattern</span></span>

<span data-ttu-id="16023-2878">3文字 (大文字小文字を区別しない) スペース (省略可能)、4桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2879">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2879">Checksum</span></span>

<span data-ttu-id="16023-2880">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2881">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2881">Definition</span></span>

<span data-ttu-id="16023-2882">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2883">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2884">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="16023-2885">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2885">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="16023-2886">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2886">Keywords</span></span>

<span data-ttu-id="16023-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="16023-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="16023-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="16023-2888">NHI</span></span> 
- <span data-ttu-id="16023-2889">New Zealand</span><span class="sxs-lookup"><span data-stu-id="16023-2889">New Zealand</span></span> 
- <span data-ttu-id="16023-2890">正常性</span><span class="sxs-lookup"><span data-stu-id="16023-2890">Health</span></span> 
- <span data-ttu-id="16023-2891">処理</span><span class="sxs-lookup"><span data-stu-id="16023-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="16023-2892">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2893">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2893">Format</span></span>

<span data-ttu-id="16023-2894">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2895">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2895">Pattern</span></span>

<span data-ttu-id="16023-2896">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2896">11 digits:</span></span>
- <span data-ttu-id="16023-2897">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="16023-2898">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="16023-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="16023-2899">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="16023-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2900">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2900">Checksum</span></span>

<span data-ttu-id="16023-2901">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2902">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2902">Definition</span></span>

<span data-ttu-id="16023-2903">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2904">関数 Func_norway_id_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2905">Keyword_norway_id_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="16023-2906">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2906">The checksum passes.</span></span>
- <span data-ttu-id="16023-2907">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2908">関数 Func_norway_id_numbe は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2909">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2909">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2910">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="16023-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="16023-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="16023-2912">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="16023-2912">Personal identification number</span></span>
- <span data-ttu-id="16023-2913">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="16023-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="16023-2914">ID Number</span><span class="sxs-lookup"><span data-stu-id="16023-2914">ID Number</span></span>
- <span data-ttu-id="16023-2915">Fim</span><span class="sxs-lookup"><span data-stu-id="16023-2915">Identification</span></span>
- <span data-ttu-id="16023-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2916">Personnummer</span></span>
- <span data-ttu-id="16023-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="16023-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="16023-2918">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="16023-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2919">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2919">Format</span></span>

<span data-ttu-id="16023-2920">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2921">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2921">Pattern</span></span>

<span data-ttu-id="16023-2922">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-2922">12 digits:</span></span>
- <span data-ttu-id="16023-2923">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2923">Four digits</span></span> 
- <span data-ttu-id="16023-2924">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-2924">A hyphen</span></span> 
- <span data-ttu-id="16023-2925">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-2925">Seven digits</span></span> 
- <span data-ttu-id="16023-2926">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-2926">A hyphen</span></span> 
- <span data-ttu-id="16023-2927">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2928">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2928">Checksum</span></span>

<span data-ttu-id="16023-2929">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2930">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2930">Definition</span></span>

<span data-ttu-id="16023-2931">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2932">正規表現 Regex_philippines_unified_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2933">Keyword_philippines_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2934">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="16023-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="16023-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="16023-2936">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="16023-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="16023-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="16023-2937">UMID</span></span> 
- <span data-ttu-id="16023-2938">Identity Card</span><span class="sxs-lookup"><span data-stu-id="16023-2938">Identity Card</span></span> 
- <span data-ttu-id="16023-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="16023-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="16023-2940">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="16023-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="16023-2941">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2941">Format</span></span>

<span data-ttu-id="16023-2942">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2943">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2943">Pattern</span></span>

<span data-ttu-id="16023-2944">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2945">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2945">Checksum</span></span>

<span data-ttu-id="16023-2946">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2947">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2947">Definition</span></span>

<span data-ttu-id="16023-2948">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_polish_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="16023-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="16023-2949">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="16023-2950">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2951">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="16023-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="16023-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="16023-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="16023-2953">Dowód osobisty</span></span>
- <span data-ttu-id="16023-2954">特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="16023-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="16023-2955">Nazwa i 特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="16023-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="16023-2956">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="16023-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="16023-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="16023-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="16023-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="16023-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="16023-2959">dow.</span><span class="sxs-lookup"><span data-stu-id="16023-2959">dow.</span></span> <span data-ttu-id="16023-2960">hp-ux.</span><span class="sxs-lookup"><span data-stu-id="16023-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="16023-2961">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="16023-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="16023-2962">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2962">Format</span></span>

<span data-ttu-id="16023-2963">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2964">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2964">Pattern</span></span>

<span data-ttu-id="16023-2965">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2966">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2966">Checksum</span></span>

<span data-ttu-id="16023-2967">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2968">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2968">Definition</span></span>

<span data-ttu-id="16023-2969">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2970">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2971">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="16023-2972">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-2973">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="16023-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="16023-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="16023-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="16023-2975">Nr PESEL</span></span>
- <span data-ttu-id="16023-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="16023-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="16023-2977">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="16023-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="16023-2978">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2978">Format</span></span>

<span data-ttu-id="16023-2979">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2980">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2980">Pattern</span></span>

<span data-ttu-id="16023-2981">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-2982">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-2982">Checksum</span></span>

<span data-ttu-id="16023-2983">はい</span><span class="sxs-lookup"><span data-stu-id="16023-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-2984">定義</span><span class="sxs-lookup"><span data-stu-id="16023-2984">Definition</span></span>

<span data-ttu-id="16023-2985">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-2986">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-2987">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="16023-2988">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-2988">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="16023-2989">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="16023-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="16023-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="16023-2991">特定の引数</span><span class="sxs-lookup"><span data-stu-id="16023-2991">Numer paszportu</span></span>
- <span data-ttu-id="16023-2992">Nr.</span><span class="sxs-lookup"><span data-stu-id="16023-2992">Nr.</span></span> <span data-ttu-id="16023-2993">大き zportu</span><span class="sxs-lookup"><span data-stu-id="16023-2993">Paszportu</span></span>
- <span data-ttu-id="16023-2994">があります</span><span class="sxs-lookup"><span data-stu-id="16023-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="16023-2995">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="16023-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-2996">Format</span><span class="sxs-lookup"><span data-stu-id="16023-2996">Format</span></span>

<span data-ttu-id="16023-2997">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-2998">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-2998">Pattern</span></span>

<span data-ttu-id="16023-2999">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3000">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3000">Checksum</span></span>

<span data-ttu-id="16023-3001">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3002">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3002">Definition</span></span>

<span data-ttu-id="16023-3003">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3004">正規表現 Regex_portugal_citizen_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3005">Keyword_portugal_citizen_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3006">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="16023-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="16023-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="16023-3008">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="16023-3008">Citizen Card</span></span>
- <span data-ttu-id="16023-3009">National ID Card</span><span class="sxs-lookup"><span data-stu-id="16023-3009">National ID Card</span></span>
- <span data-ttu-id="16023-3010">CC</span><span class="sxs-lookup"><span data-stu-id="16023-3010">CC</span></span>
- <span data-ttu-id="16023-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="16023-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="16023-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="16023-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="16023-3013">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="16023-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="16023-3014">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3014">Format</span></span>

<span data-ttu-id="16023-3015">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3016">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3016">Pattern</span></span>

<span data-ttu-id="16023-3017">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3018">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3018">Checksum</span></span>

<span data-ttu-id="16023-3019">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3020">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3020">Definition</span></span>

<span data-ttu-id="16023-3021">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3022">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3023">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3024">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="16023-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="16023-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="16023-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="16023-3026">Identification Card</span></span> 
- <span data-ttu-id="16023-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="16023-3027">I card number</span></span> 
- <span data-ttu-id="16023-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="16023-3028">ID number</span></span> 
- <span data-ttu-id="16023-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="16023-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="16023-3030">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3031">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3031">Format</span></span>

<span data-ttu-id="16023-3032">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="16023-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3033">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3033">Pattern</span></span>

- <span data-ttu-id="16023-3034">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="16023-3035">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="16023-3036">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-3036">Seven digits</span></span> 
- <span data-ttu-id="16023-3037">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="16023-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3038">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3038">Checksum</span></span>

<span data-ttu-id="16023-3039">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3040">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3040">Definition</span></span>

<span data-ttu-id="16023-3041">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3042">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3043">Keyword_singapore_nric からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="16023-3044">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3044">The checksum passes.</span></span>

<span data-ttu-id="16023-3045">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3046">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3047">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3047">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3048">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="16023-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="16023-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="16023-3050">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="16023-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="16023-3051">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="16023-3051">Identity Card Number</span></span> 
- <span data-ttu-id="16023-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="16023-3052">NRIC</span></span> 
- <span data-ttu-id="16023-3053">IC</span><span class="sxs-lookup"><span data-stu-id="16023-3053">IC</span></span> 
- <span data-ttu-id="16023-3054">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="16023-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="16023-3055">FIN</span><span class="sxs-lookup"><span data-stu-id="16023-3055">FIN</span></span> 
- <span data-ttu-id="16023-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="16023-3056">身份证</span></span> 
- <span data-ttu-id="16023-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="16023-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="16023-3058">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3059">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3059">Format</span></span>

<span data-ttu-id="16023-3060">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3061">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3061">Pattern</span></span>

<span data-ttu-id="16023-3062">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3062">13 digits:</span></span>
- <span data-ttu-id="16023-3063">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16023-3064">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3064">Four digits</span></span> 
- <span data-ttu-id="16023-3065">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="16023-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="16023-3066">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="16023-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="16023-3067">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3068">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3068">Checksum</span></span>

<span data-ttu-id="16023-3069">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3070">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3070">Definition</span></span>

<span data-ttu-id="16023-3071">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3072">関数 Func_south_africa_identification_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3073">Keyword_south_africa_identification_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="16023-3074">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3075">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="16023-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="16023-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="16023-3077">Identity card</span><span class="sxs-lookup"><span data-stu-id="16023-3077">Identity card</span></span>
- <span data-ttu-id="16023-3078">ID</span><span class="sxs-lookup"><span data-stu-id="16023-3078">ID</span></span>
- <span data-ttu-id="16023-3079">Fim</span><span class="sxs-lookup"><span data-stu-id="16023-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="16023-3080">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="16023-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3081">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3081">Format</span></span>

<span data-ttu-id="16023-3082">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3083">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3083">Pattern</span></span>

<span data-ttu-id="16023-3084">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3084">13 digits:</span></span>
- <span data-ttu-id="16023-3085">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="16023-3086">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="16023-3086">A hyphen</span></span> 
- <span data-ttu-id="16023-3087">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="16023-3088">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="16023-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="16023-3089">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="16023-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="16023-3090">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="16023-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3091">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3091">Checksum</span></span>

<span data-ttu-id="16023-3092">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3093">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3093">Definition</span></span>

<span data-ttu-id="16023-3094">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3095">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3096">Keyword_south_korea_resident_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="16023-3097">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3097">The checksum passes.</span></span>

<span data-ttu-id="16023-3098">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3099">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3100">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3100">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3101">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="16023-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="16023-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="16023-3103">National ID card</span><span class="sxs-lookup"><span data-stu-id="16023-3103">National ID card</span></span> 
- <span data-ttu-id="16023-3104">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="16023-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="16023-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="16023-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="16023-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="16023-3106">RRN</span></span> 
- <span data-ttu-id="16023-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="16023-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="16023-3108">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="16023-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="16023-3109">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3109">Format</span></span>

<span data-ttu-id="16023-3110">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3111">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3111">Pattern</span></span>

<span data-ttu-id="16023-3112">11-12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3112">11-12 digits:</span></span>
- <span data-ttu-id="16023-3113">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3113">Two digits</span></span> 
- <span data-ttu-id="16023-3114">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="16023-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="16023-3115">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3115">7-8 digits</span></span> 
- <span data-ttu-id="16023-3116">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="16023-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="16023-3117">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3118">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3118">Checksum</span></span>

<span data-ttu-id="16023-3119">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3120">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3120">Definition</span></span>

<span data-ttu-id="16023-3121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3122">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3123">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3124">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3124">Keywords</span></span>

<span data-ttu-id="16023-3125">なし</span><span class="sxs-lookup"><span data-stu-id="16023-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="16023-3126">SQL Server の接続文字列</span><span class="sxs-lookup"><span data-stu-id="16023-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="16023-3127">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3127">Format</span></span>

<span data-ttu-id="16023-3128">文字列 "User Id"、"User ID"、"uid"、または "UserId" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="16023-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3129">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3129">Pattern</span></span>

- <span data-ttu-id="16023-3130">文字列 "User Id"、"User ID"、"uid"、または "UserId"</span><span class="sxs-lookup"><span data-stu-id="16023-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="16023-3131">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16023-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="16023-3132">文字列 "Password" または "pwd" ("pwd" の前に小文字が含まれていません)</span><span class="sxs-lookup"><span data-stu-id="16023-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="16023-3133">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-3133">An equal sign (=)</span></span>
- <span data-ttu-id="16023-3134">ドル記号 ($)、パーセント記号 (%)、不等号 (>)、記号 (@)、二重引用符 (")、セミコロン (;)、左中かっこ ([)、左かっこ ({) のいずれでもない文字</span><span class="sxs-lookup"><span data-stu-id="16023-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="16023-3135">セミコロンではない7-128 文字の任意の組み合わせ (;)、スラッシュ (/)、または引用符 (")</span><span class="sxs-lookup"><span data-stu-id="16023-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="16023-3136">セミコロン (;)または二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="16023-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3137">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3137">Checksum</span></span>

<span data-ttu-id="16023-3138">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3139">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3139">Definition</span></span>

<span data-ttu-id="16023-3140">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3141">正規表現 CEP_Regex_SQLServerConnectionString は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3142">CEP_GlobalFilter からのキーワードが見つかり**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="16023-3143">正規表現 CEP_PasswordPlaceHolder は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3144">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="16023-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3145">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="16023-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="16023-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="16023-3147">パスワードの一部</span><span class="sxs-lookup"><span data-stu-id="16023-3147">some-password</span></span>
- <span data-ttu-id="16023-3148">パスワード</span><span class="sxs-lookup"><span data-stu-id="16023-3148">somepassword</span></span>
- <span data-ttu-id="16023-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="16023-3149">secretPassword</span></span>
- <span data-ttu-id="16023-3150">示す</span><span class="sxs-lookup"><span data-stu-id="16023-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="16023-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="16023-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="16023-3152">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-3153">Password または pwd の後に、0-2 スペース、等号 (=)、0-2 スペース、アスタリスク (\*)、または--</span><span class="sxs-lookup"><span data-stu-id="16023-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="16023-3154">Password または pwd の後に、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="16023-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="16023-3155">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="16023-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="16023-3156">不等号 (<)</span><span class="sxs-lookup"><span data-stu-id="16023-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="16023-3157">1-200 文字の大文字と小文字、数字、アスタリスク (\*)、ハイフン (-)、下線 (_)、または空白文字の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="16023-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="16023-3158">不等号 (>)</span><span class="sxs-lookup"><span data-stu-id="16023-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="16023-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="16023-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="16023-3160">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="16023-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="16023-3161">拠点</span><span class="sxs-lookup"><span data-stu-id="16023-3161">contoso</span></span>
- <span data-ttu-id="16023-3162">fabrikam</span><span class="sxs-lookup"><span data-stu-id="16023-3162">fabrikam</span></span>
- <span data-ttu-id="16023-3163">ノース</span><span class="sxs-lookup"><span data-stu-id="16023-3163">northwind</span></span>
- <span data-ttu-id="16023-3164">サンド</span><span class="sxs-lookup"><span data-stu-id="16023-3164">sandbox</span></span>
- <span data-ttu-id="16023-3165">onebox</span><span class="sxs-lookup"><span data-stu-id="16023-3165">onebox</span></span>
- <span data-ttu-id="16023-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="16023-3166">localhost</span></span>
- <span data-ttu-id="16023-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="16023-3167">127.0.0.1</span></span>
- <span data-ttu-id="16023-3168">testacs。</span><span class="sxs-lookup"><span data-stu-id="16023-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="16023-3169">com</span><span class="sxs-lookup"><span data-stu-id="16023-3169">com</span></span>
- <span data-ttu-id="16023-3170">s-int。</span><span class="sxs-lookup"><span data-stu-id="16023-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="16023-3171">ネット</span><span class="sxs-lookup"><span data-stu-id="16023-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="16023-3172">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="16023-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="16023-3173">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3173">Format</span></span>

<span data-ttu-id="16023-3174">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="16023-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3175">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3175">Pattern</span></span>

<span data-ttu-id="16023-3176">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="16023-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="16023-3177">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="16023-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="16023-3178">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="16023-3179">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="16023-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="16023-3180">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3181">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3181">Checksum</span></span>

<span data-ttu-id="16023-3182">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3183">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3183">Definition</span></span>

<span data-ttu-id="16023-3184">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3185">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3186">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3187">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3187">Keywords</span></span>

<span data-ttu-id="16023-3188">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="16023-3189">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3190">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3190">Format</span></span>

<span data-ttu-id="16023-3191">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3192">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3192">Pattern</span></span>

<span data-ttu-id="16023-3193">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3194">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3194">Checksum</span></span>

<span data-ttu-id="16023-3195">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3196">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3196">Definition</span></span>

<span data-ttu-id="16023-3197">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3198">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3199">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-3199">One of the following is true:</span></span>
    - <span data-ttu-id="16023-3200">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="16023-3201">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3201">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3202">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="16023-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="16023-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="16023-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="16023-3204">visa requirements</span></span> 
- <span data-ttu-id="16023-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="16023-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="16023-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="16023-3206">Schengen visas</span></span> 
- <span data-ttu-id="16023-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="16023-3207">Schengen visa</span></span> 
- <span data-ttu-id="16023-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="16023-3208">Visa Processing</span></span> 
- <span data-ttu-id="16023-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="16023-3209">Visa Type</span></span> 
- <span data-ttu-id="16023-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="16023-3210">Single Entry</span></span> 
- <span data-ttu-id="16023-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="16023-3211">Multiple Entry</span></span> 
- <span data-ttu-id="16023-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="16023-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="16023-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16023-3213">Keyword_passport</span></span>

- <span data-ttu-id="16023-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16023-3214">Passport Number</span></span> 
- <span data-ttu-id="16023-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="16023-3215">Passport No</span></span> 
- <span data-ttu-id="16023-3216">Passport #</span><span class="sxs-lookup"><span data-stu-id="16023-3216">Passport #</span></span> 
- <span data-ttu-id="16023-3217">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="16023-3217">Passport#</span></span> 
- <span data-ttu-id="16023-3218">PassportID</span><span class="sxs-lookup"><span data-stu-id="16023-3218">PassportID</span></span> 
- <span data-ttu-id="16023-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="16023-3219">Passportno</span></span> 
- <span data-ttu-id="16023-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16023-3220">passportnumber</span></span> 
- <span data-ttu-id="16023-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="16023-3221">パスポート</span></span> 
- <span data-ttu-id="16023-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-3222">パスポート番号</span></span> 
- <span data-ttu-id="16023-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16023-3223">パスポートのNum</span></span> 
- <span data-ttu-id="16023-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="16023-3224">パスポート＃</span></span> 
- <span data-ttu-id="16023-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16023-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="16023-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16023-3226">Passeport n °</span></span> 
- <span data-ttu-id="16023-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16023-3227">Passeport Non</span></span> 
- <span data-ttu-id="16023-3228">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16023-3228">Passeport #</span></span> 
- <span data-ttu-id="16023-3229">Passeport#</span><span class="sxs-lookup"><span data-stu-id="16023-3229">Passeport#</span></span> 
- <span data-ttu-id="16023-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16023-3230">PasseportNon</span></span> 
- <span data-ttu-id="16023-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16023-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="16023-3232">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="16023-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="16023-3233">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3233">Format</span></span>

<span data-ttu-id="16023-3234">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="16023-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3235">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3235">Pattern</span></span>

<span data-ttu-id="16023-3236">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="16023-3237">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="16023-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="16023-3238">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="16023-3238">An optional space</span></span> 
- <span data-ttu-id="16023-3239">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="16023-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="16023-3240">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="16023-3240">An optional space</span></span> 
- <span data-ttu-id="16023-3241">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="16023-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3242">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3242">Checksum</span></span>

<span data-ttu-id="16023-3243">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3244">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3244">Definition</span></span>

<span data-ttu-id="16023-3245">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3246">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3247">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3248">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="16023-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="16023-3249">Keyword_swift</span></span>

- <span data-ttu-id="16023-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="16023-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="16023-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="16023-3251">iso 9362</span></span> 
- <span data-ttu-id="16023-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="16023-3252">iso9362</span></span> 
- <span data-ttu-id="16023-3253">実現\#</span><span class="sxs-lookup"><span data-stu-id="16023-3253">swift\#</span></span> 
- <span data-ttu-id="16023-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="16023-3254">swiftcode</span></span> 
- <span data-ttu-id="16023-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="16023-3255">swiftnumber</span></span> 
- <span data-ttu-id="16023-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="16023-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="16023-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="16023-3257">swift code</span></span> 
- <span data-ttu-id="16023-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="16023-3258">swift number #</span></span> 
- <span data-ttu-id="16023-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="16023-3259">swift routing number</span></span> 
- <span data-ttu-id="16023-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="16023-3260">bic number</span></span> 
- <span data-ttu-id="16023-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="16023-3261">bic code</span></span> 
- <span data-ttu-id="16023-3262">bic\#</span><span class="sxs-lookup"><span data-stu-id="16023-3262">bic \#</span></span> 
- <span data-ttu-id="16023-3263">bic\#</span><span class="sxs-lookup"><span data-stu-id="16023-3263">bic\#</span></span> 
- <span data-ttu-id="16023-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="16023-3264">bank identifier code</span></span> 
- <span data-ttu-id="16023-3265">標準化9362</span><span class="sxs-lookup"><span data-stu-id="16023-3265">標準化9362</span></span> 
- <span data-ttu-id="16023-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="16023-3266">迅速＃</span></span> 
- <span data-ttu-id="16023-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="16023-3267">SWIFTコード</span></span> 
- <span data-ttu-id="16023-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="16023-3268">SWIFT番号</span></span> 
- <span data-ttu-id="16023-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="16023-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="16023-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="16023-3270">BIC番号</span></span> 
- <span data-ttu-id="16023-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="16023-3271">BICコード</span></span> 
- <span data-ttu-id="16023-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="16023-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="16023-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="16023-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="16023-3274">rapide\#</span><span class="sxs-lookup"><span data-stu-id="16023-3274">rapide \#</span></span> 
- <span data-ttu-id="16023-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="16023-3275">code SWIFT</span></span> 
- <span data-ttu-id="16023-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="16023-3276">le numéro de swift</span></span> 
- <span data-ttu-id="16023-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="16023-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="16023-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="16023-3278">le numéro BIC</span></span> 
- <span data-ttu-id="16023-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="16023-3279">\# BIC</span></span> 
- <span data-ttu-id="16023-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="16023-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="16023-3281">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="16023-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="16023-3282">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3282">Format</span></span>

<span data-ttu-id="16023-3283">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3284">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3284">Pattern</span></span>

<span data-ttu-id="16023-3285">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="16023-3286">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="16023-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="16023-3287">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="16023-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="16023-3288">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3289">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3289">Checksum</span></span>

<span data-ttu-id="16023-3290">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3291">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3291">Definition</span></span>

<span data-ttu-id="16023-3292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3293">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3294">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="16023-3295">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3296">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="16023-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="16023-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="16023-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="16023-3298">身份證字號</span></span> 
- <span data-ttu-id="16023-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="16023-3299">身份證</span></span> 
- <span data-ttu-id="16023-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="16023-3300">身份證號碼</span></span> 
- <span data-ttu-id="16023-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="16023-3301">身份證號</span></span> 
- <span data-ttu-id="16023-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="16023-3302">身分證字號</span></span> 
- <span data-ttu-id="16023-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="16023-3303">身分證</span></span> 
- <span data-ttu-id="16023-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="16023-3304">身分證號碼</span></span> 
- <span data-ttu-id="16023-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="16023-3305">身份證號</span></span> 
- <span data-ttu-id="16023-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="16023-3306">身分證統一編號</span></span> 
- <span data-ttu-id="16023-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="16023-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="16023-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="16023-3308">簽名</span></span> 
- <span data-ttu-id="16023-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="16023-3309">蓋章</span></span> 
- <span data-ttu-id="16023-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="16023-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="16023-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="16023-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="16023-3312">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3313">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3313">Format</span></span>

- <span data-ttu-id="16023-3314">バイオメトリックパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="16023-3315">バイオメトリクスでないパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3316">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3316">Pattern</span></span>
<span data-ttu-id="16023-3317">バイオメトリックパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="16023-3317">Biometric passport number:</span></span>
- <span data-ttu-id="16023-3318">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="16023-3318">The digit "3"</span></span> 
- <span data-ttu-id="16023-3319">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3319">Eight digits</span></span>

<span data-ttu-id="16023-3320">バイオメトリクスではないパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="16023-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="16023-3321">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3322">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3322">Checksum</span></span>

<span data-ttu-id="16023-3323">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3324">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3324">Definition</span></span>

<span data-ttu-id="16023-3325">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3326">正規表現 Regex_taiwan_passport は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3327">Keyword_taiwan_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3328">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="16023-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="16023-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="16023-3330">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="16023-3330">ROC passport number</span></span> 
- <span data-ttu-id="16023-3331">Passport number</span><span class="sxs-lookup"><span data-stu-id="16023-3331">Passport number</span></span> 
- <span data-ttu-id="16023-3332">Passport no</span><span class="sxs-lookup"><span data-stu-id="16023-3332">Passport no</span></span> 
- <span data-ttu-id="16023-3333">Passport Num</span><span class="sxs-lookup"><span data-stu-id="16023-3333">Passport Num</span></span> 
- <span data-ttu-id="16023-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="16023-3334">Passport #</span></span> 
- <span data-ttu-id="16023-3335">护照</span><span class="sxs-lookup"><span data-stu-id="16023-3335">护照</span></span> 
- <span data-ttu-id="16023-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="16023-3336">中華民國護照</span></span> 
- <span data-ttu-id="16023-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="16023-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="16023-3338">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="16023-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3339">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3339">Format</span></span>

<span data-ttu-id="16023-3340">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="16023-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3341">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3341">Pattern</span></span>

<span data-ttu-id="16023-3342">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3342">10 letters and digits:</span></span>
- <span data-ttu-id="16023-3343">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="16023-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="16023-3344">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3345">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3345">Checksum</span></span>

<span data-ttu-id="16023-3346">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3347">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3347">Definition</span></span>

<span data-ttu-id="16023-3348">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3349">正規表現 Regex_taiwan_resident_certificate は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3350">Keyword_taiwan_resident_certificate からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3351">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="16023-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="16023-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="16023-3353">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="16023-3353">Resident Certificate</span></span> 
- <span data-ttu-id="16023-3354">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="16023-3354">Resident Cert</span></span> 
- <span data-ttu-id="16023-3355">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="16023-3355">Resident Cert.</span></span> 
- <span data-ttu-id="16023-3356">Identification card</span><span class="sxs-lookup"><span data-stu-id="16023-3356">Identification card</span></span> 
- <span data-ttu-id="16023-3357">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="16023-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="16023-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="16023-3358">ARC</span></span> 
- <span data-ttu-id="16023-3359">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="16023-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="16023-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="16023-3360">TARC</span></span> 
- <span data-ttu-id="16023-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="16023-3361">居留證</span></span> 
- <span data-ttu-id="16023-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="16023-3362">外僑居留證</span></span> 
- <span data-ttu-id="16023-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="16023-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="16023-3364">タイ語の母集団識別コード</span><span class="sxs-lookup"><span data-stu-id="16023-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="16023-3365">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3365">Format</span></span>

<span data-ttu-id="16023-3366">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3367">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3367">Pattern</span></span>

<span data-ttu-id="16023-3368">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3368">13 digits:</span></span>
- <span data-ttu-id="16023-3369">最初の桁が0または9ではない</span><span class="sxs-lookup"><span data-stu-id="16023-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="16023-3370">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3371">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3371">Checksum</span></span>

<span data-ttu-id="16023-3372">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3373">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3373">Definition</span></span>

<span data-ttu-id="16023-3374">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3375">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3376">Keyword_Thai_Citizen_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="16023-3377">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3378">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3379">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="16023-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="16023-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="16023-3381">ID Number</span><span class="sxs-lookup"><span data-stu-id="16023-3381">ID Number</span></span>
- <span data-ttu-id="16023-3382">識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-3382">Identification Number</span></span>
- <span data-ttu-id="16023-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16023-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="16023-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16023-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="16023-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16023-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="16023-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="16023-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="16023-3387">トルコの国の識別番号</span><span class="sxs-lookup"><span data-stu-id="16023-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3388">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3388">Format</span></span>

<span data-ttu-id="16023-3389">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3390">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3390">Pattern</span></span>

<span data-ttu-id="16023-3391">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3392">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3392">Checksum</span></span>

<span data-ttu-id="16023-3393">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3394">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3394">Definition</span></span>

<span data-ttu-id="16023-3395">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3396">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3397">Keyword_Turkish_National_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="16023-3398">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3399">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3400">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="16023-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="16023-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="16023-3402">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="16023-3402">TC Kimlik No</span></span>
- <span data-ttu-id="16023-3403">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="16023-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="16023-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="16023-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="16023-3405">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="16023-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="16023-p144">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3408">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3408">Format</span></span>

<span data-ttu-id="16023-3409">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="16023-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3410">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3410">Pattern</span></span>

<span data-ttu-id="16023-3411">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3411">18 letters and digits:</span></span>
- <span data-ttu-id="16023-3412">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="16023-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="16023-3413">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3413">One digit</span></span> 
- <span data-ttu-id="16023-3414">誕生日の日付形式 MMDDY の5桁の数字 (7 文字目は、driver が女性の場合は50にインクリメントされます。つまり、01から12の代わりに51から 62)</span><span class="sxs-lookup"><span data-stu-id="16023-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="16023-3415">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="16023-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="16023-3416">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3417">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3417">Checksum</span></span>

<span data-ttu-id="16023-3418">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3419">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3419">Definition</span></span>

<span data-ttu-id="16023-3420">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3421">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3422">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="16023-3423">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3424">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="16023-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16023-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="16023-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="16023-3426">DVLA</span></span> 
- <span data-ttu-id="16023-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="16023-3427">light vans</span></span> 
- <span data-ttu-id="16023-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="16023-3428">quadbikes</span></span> 
- <span data-ttu-id="16023-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="16023-3429">motor cars</span></span> 
- <span data-ttu-id="16023-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="16023-3430">125cc</span></span> 
- <span data-ttu-id="16023-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="16023-3431">sidecar</span></span> 
- <span data-ttu-id="16023-3432">tricycles</span><span class="sxs-lookup"><span data-stu-id="16023-3432">tricycles</span></span> 
- <span data-ttu-id="16023-3433">motorcycles</span><span class="sxs-lookup"><span data-stu-id="16023-3433">motorcycles</span></span> 
- <span data-ttu-id="16023-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="16023-3434">photocard licence</span></span> 
- <span data-ttu-id="16023-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="16023-3435">learner drivers</span></span> 
- <span data-ttu-id="16023-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="16023-3436">licence holder</span></span> 
- <span data-ttu-id="16023-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="16023-3437">licence holders</span></span> 
- <span data-ttu-id="16023-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="16023-3438">driving licences</span></span> 
- <span data-ttu-id="16023-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="16023-3439">driving licence</span></span> 
- <span data-ttu-id="16023-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="16023-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="16023-p145">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="16023-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3443">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3443">Format</span></span>

<span data-ttu-id="16023-3444">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3445">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3445">Pattern</span></span>

<span data-ttu-id="16023-3446">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3447">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3447">Checksum</span></span>

<span data-ttu-id="16023-3448">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3449">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3449">Definition</span></span>

<span data-ttu-id="16023-3450">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3451">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3452">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3452">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3453">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="16023-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="16023-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="16023-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="16023-3455">council nomination</span></span> 
- <span data-ttu-id="16023-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="16023-3456">nomination form</span></span> 
- <span data-ttu-id="16023-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="16023-3457">electoral register</span></span> 
- <span data-ttu-id="16023-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="16023-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="16023-p146">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="16023-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3461">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3461">Format</span></span>

<span data-ttu-id="16023-3462">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3463">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3463">Pattern</span></span>

<span data-ttu-id="16023-3464">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="16023-3464">10-17 digits:</span></span>
- <span data-ttu-id="16023-3465">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="16023-3466">スペース</span><span class="sxs-lookup"><span data-stu-id="16023-3466">A space</span></span> 
- <span data-ttu-id="16023-3467">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3467">Three digits</span></span> 
- <span data-ttu-id="16023-3468">スペース</span><span class="sxs-lookup"><span data-stu-id="16023-3468">A space</span></span> 
- <span data-ttu-id="16023-3469">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3470">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3470">Checksum</span></span>

<span data-ttu-id="16023-3471">はい</span><span class="sxs-lookup"><span data-stu-id="16023-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3472">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3472">Definition</span></span>

<span data-ttu-id="16023-3473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3474">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3475">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-3475">One of the following is true:</span></span>
    - <span data-ttu-id="16023-3476">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="16023-3477">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="16023-3478">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="16023-3479">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="16023-3479">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3480">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="16023-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="16023-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="16023-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="16023-3482">national health service</span></span> 
- <span data-ttu-id="16023-3483">nhs</span><span class="sxs-lookup"><span data-stu-id="16023-3483">nhs</span></span> 
- <span data-ttu-id="16023-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="16023-3484">health services authority</span></span> 
- <span data-ttu-id="16023-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="16023-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="16023-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="16023-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="16023-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="16023-3487">patient id</span></span> 
- <span data-ttu-id="16023-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="16023-3488">patient identification</span></span> 
- <span data-ttu-id="16023-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="16023-3489">patient no</span></span> 
- <span data-ttu-id="16023-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="16023-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="16023-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="16023-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="16023-3492">GP</span><span class="sxs-lookup"><span data-stu-id="16023-3492">GP</span></span> 
- <span data-ttu-id="16023-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="16023-3493">DOB</span></span> 
- <span data-ttu-id="16023-3494">D.</span><span class="sxs-lookup"><span data-stu-id="16023-3494">D.O.B</span></span> 
- <span data-ttu-id="16023-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="16023-3495">Date of Birth</span></span> 
- <span data-ttu-id="16023-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="16023-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="16023-p147">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="16023-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="16023-3499">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3499">Format</span></span>

<span data-ttu-id="16023-3500">スペースまたはダッシュで区切られた7文字または9文字</span><span class="sxs-lookup"><span data-stu-id="16023-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3501">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3501">Pattern</span></span>

<span data-ttu-id="16023-3502">次の2つのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="16023-3502">Two possible patterns:</span></span>

- <span data-ttu-id="16023-3503">2文字 (有効な NINOs このプレフィックスには特定の文字のみを使用します。このパターンは、大文字小文字を区別しません)。</span><span class="sxs-lookup"><span data-stu-id="16023-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="16023-3504">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3504">Six digits</span></span>
- <span data-ttu-id="16023-3505">「A」、「B」、「C」、または「d」 (プレフィックスと同様に、サフィックスには特定の文字のみ指定できます。大文字と小文字は区別されません)</span><span class="sxs-lookup"><span data-stu-id="16023-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="16023-3506">または</span><span class="sxs-lookup"><span data-stu-id="16023-3506">OR</span></span>

- <span data-ttu-id="16023-3507">2文字</span><span class="sxs-lookup"><span data-stu-id="16023-3507">Two letters</span></span>
- <span data-ttu-id="16023-3508">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-3508">A space or dash</span></span>
- <span data-ttu-id="16023-3509">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3509">Two digits</span></span>
- <span data-ttu-id="16023-3510">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-3510">A space or dash</span></span>
- <span data-ttu-id="16023-3511">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3511">Two digits</span></span>
- <span data-ttu-id="16023-3512">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-3512">A space or dash</span></span>
- <span data-ttu-id="16023-3513">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3513">Two digits</span></span>
- <span data-ttu-id="16023-3514">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-3514">A space or dash</span></span>
- <span data-ttu-id="16023-3515">' A '、' B '、' C '、または ' d ' のどちらか</span><span class="sxs-lookup"><span data-stu-id="16023-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3516">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3516">Checksum</span></span>

<span data-ttu-id="16023-3517">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3518">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3518">Definition</span></span>

<span data-ttu-id="16023-3519">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3520">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3521">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="16023-3522">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3523">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3524">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="16023-3524">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3525">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="16023-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="16023-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="16023-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="16023-3527">national insurance number</span></span> 
- <span data-ttu-id="16023-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="16023-3528">national insurance contributions</span></span> 
- <span data-ttu-id="16023-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="16023-3529">protection act</span></span> 
- <span data-ttu-id="16023-3530">金</span><span class="sxs-lookup"><span data-stu-id="16023-3530">insurance</span></span> 
- <span data-ttu-id="16023-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="16023-3531">social security number</span></span> 
- <span data-ttu-id="16023-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="16023-3532">insurance application</span></span> 
- <span data-ttu-id="16023-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="16023-3533">medical application</span></span> 
- <span data-ttu-id="16023-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="16023-3534">social insurance</span></span> 
- <span data-ttu-id="16023-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="16023-3535">medical attention</span></span> 
- <span data-ttu-id="16023-3536">social security</span><span class="sxs-lookup"><span data-stu-id="16023-3536">social security</span></span> 
- <span data-ttu-id="16023-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="16023-3537">great britain</span></span> 
- <span data-ttu-id="16023-3538">金</span><span class="sxs-lookup"><span data-stu-id="16023-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="16023-p148">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3541">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3541">Format</span></span>

<span data-ttu-id="16023-3542">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3543">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3543">Pattern</span></span>

<span data-ttu-id="16023-3544">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3545">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3545">Checksum</span></span>

<span data-ttu-id="16023-3546">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3547">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3547">Definition</span></span>

<span data-ttu-id="16023-3548">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3549">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3550">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3551">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="16023-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="16023-3552">Keyword_passport</span></span>

- <span data-ttu-id="16023-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="16023-3553">Passport Number</span></span> 
- <span data-ttu-id="16023-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="16023-3554">Passport No</span></span> 
- <span data-ttu-id="16023-3555">Passport #</span><span class="sxs-lookup"><span data-stu-id="16023-3555">Passport #</span></span> 
- <span data-ttu-id="16023-3556">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="16023-3556">Passport#</span></span> 
- <span data-ttu-id="16023-3557">PassportID</span><span class="sxs-lookup"><span data-stu-id="16023-3557">PassportID</span></span> 
- <span data-ttu-id="16023-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="16023-3558">Passportno</span></span> 
- <span data-ttu-id="16023-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="16023-3559">passportnumber</span></span> 
- <span data-ttu-id="16023-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="16023-3560">パスポート</span></span> 
- <span data-ttu-id="16023-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="16023-3561">パスポート番号</span></span> 
- <span data-ttu-id="16023-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="16023-3562">パスポートのNum</span></span> 
- <span data-ttu-id="16023-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="16023-3563">パスポート＃</span></span> 
- <span data-ttu-id="16023-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="16023-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="16023-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="16023-3565">Passeport n °</span></span> 
- <span data-ttu-id="16023-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="16023-3566">Passeport Non</span></span> 
- <span data-ttu-id="16023-3567">Passeport #</span><span class="sxs-lookup"><span data-stu-id="16023-3567">Passeport #</span></span> 
- <span data-ttu-id="16023-3568">Passeport#</span><span class="sxs-lookup"><span data-stu-id="16023-3568">Passeport#</span></span> 
- <span data-ttu-id="16023-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="16023-3569">PasseportNon</span></span> 
- <span data-ttu-id="16023-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="16023-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="16023-3571">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="16023-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3572">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3572">Format</span></span>

<span data-ttu-id="16023-3573">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3574">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3574">Pattern</span></span>

<span data-ttu-id="16023-3575">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="16023-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3576">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3576">Checksum</span></span>

<span data-ttu-id="16023-3577">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3578">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3578">Definition</span></span>

<span data-ttu-id="16023-3579">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3580">正規表現 Regex_usa_bank_account_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3581">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3582">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="16023-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="16023-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="16023-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-3584">Checking Account Number</span></span> 
- <span data-ttu-id="16023-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="16023-3585">Checking Account</span></span> 
- <span data-ttu-id="16023-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="16023-3586">Checking Account #</span></span> 
- <span data-ttu-id="16023-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="16023-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-3588">Checking Acct #</span></span> 
- <span data-ttu-id="16023-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="16023-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-3590">Checking Account No.</span></span> 
- <span data-ttu-id="16023-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-3591">Bank Account Number</span></span> 
- <span data-ttu-id="16023-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="16023-3592">Bank Account #</span></span> 
- <span data-ttu-id="16023-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="16023-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-3594">Bank Acct #</span></span> 
- <span data-ttu-id="16023-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="16023-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-3596">Bank Account No.</span></span> 
- <span data-ttu-id="16023-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-3597">Savings Account Number</span></span> 
- <span data-ttu-id="16023-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="16023-3598">Savings Account.</span></span> 
- <span data-ttu-id="16023-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="16023-3599">Savings Account #</span></span> 
- <span data-ttu-id="16023-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="16023-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-3601">Savings Acct #</span></span> 
- <span data-ttu-id="16023-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="16023-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-3603">Savings Account No.</span></span> 
- <span data-ttu-id="16023-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="16023-3604">Debit Account Number</span></span> 
- <span data-ttu-id="16023-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="16023-3605">Debit Account</span></span> 
- <span data-ttu-id="16023-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="16023-3606">Debit Account #</span></span> 
- <span data-ttu-id="16023-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="16023-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="16023-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="16023-3608">Debit Acct #</span></span> 
- <span data-ttu-id="16023-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="16023-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="16023-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="16023-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="16023-3611">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="16023-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="16023-3612">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3612">Format</span></span>

<span data-ttu-id="16023-3613">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="16023-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3614">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3614">Pattern</span></span>

<span data-ttu-id="16023-3615">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="16023-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="16023-3616">Ddd ddd ddd のような形式の9桁の数字は一致します。</span><span class="sxs-lookup"><span data-stu-id="16023-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="16023-3617">Ddddddddd のように9桁の数字は一致しません。</span><span class="sxs-lookup"><span data-stu-id="16023-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3618">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3618">Checksum</span></span>

<span data-ttu-id="16023-3619">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3620">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3620">Definition</span></span>

<span data-ttu-id="16023-3621">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3622">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3623">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="16023-3624">Keyword_us_drivers_license からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="16023-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="16023-3625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3626">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3627">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="16023-3628">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="16023-3629">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="16023-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a><span data-ttu-id="16023-3630">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="16023-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="16023-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="16023-3632">DL</span><span class="sxs-lookup"><span data-stu-id="16023-3632">DL</span></span> 
- <span data-ttu-id="16023-3633">DL</span><span class="sxs-lookup"><span data-stu-id="16023-3633">DLS</span></span> 
- <span data-ttu-id="16023-3634">CDL</span><span class="sxs-lookup"><span data-stu-id="16023-3634">CDL</span></span> 
- <span data-ttu-id="16023-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="16023-3635">CDLS</span></span> 
- <span data-ttu-id="16023-3636">ID</span><span class="sxs-lookup"><span data-stu-id="16023-3636">ID</span></span> 
- <span data-ttu-id="16023-3637">Rid</span><span class="sxs-lookup"><span data-stu-id="16023-3637">IDs</span></span> 
- <span data-ttu-id="16023-3638">DL#</span><span class="sxs-lookup"><span data-stu-id="16023-3638">DL#</span></span> 
- <span data-ttu-id="16023-3639">DL#</span><span class="sxs-lookup"><span data-stu-id="16023-3639">DLS#</span></span> 
- <span data-ttu-id="16023-3640">CDL#</span><span class="sxs-lookup"><span data-stu-id="16023-3640">CDL#</span></span> 
- <span data-ttu-id="16023-3641">CDLS#</span><span class="sxs-lookup"><span data-stu-id="16023-3641">CDLS#</span></span> 
- <span data-ttu-id="16023-3642">RID#</span><span class="sxs-lookup"><span data-stu-id="16023-3642">ID#</span></span>
- <span data-ttu-id="16023-3643">Rid#</span><span class="sxs-lookup"><span data-stu-id="16023-3643">IDs#</span></span> 
- <span data-ttu-id="16023-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="16023-3644">ID number</span></span> 
- <span data-ttu-id="16023-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="16023-3645">ID numbers</span></span> 
- <span data-ttu-id="16023-3646">そして</span><span class="sxs-lookup"><span data-stu-id="16023-3646">LIC</span></span> 
- <span data-ttu-id="16023-3647">そして#</span><span class="sxs-lookup"><span data-stu-id="16023-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="16023-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="16023-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="16023-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="16023-3649">DriverLic</span></span> 
- <span data-ttu-id="16023-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="16023-3650">DriverLics</span></span> 
- <span data-ttu-id="16023-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="16023-3651">DriverLicense</span></span> 
- <span data-ttu-id="16023-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="16023-3652">DriverLicenses</span></span> 
- <span data-ttu-id="16023-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="16023-3653">Driver Lic</span></span> 
- <span data-ttu-id="16023-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="16023-3654">Driver Lics</span></span> 
- <span data-ttu-id="16023-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="16023-3655">Driver License</span></span> 
- <span data-ttu-id="16023-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-3656">Driver Licenses</span></span> 
- <span data-ttu-id="16023-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="16023-3657">DriversLic</span></span> 
- <span data-ttu-id="16023-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="16023-3658">DriversLics</span></span> 
- <span data-ttu-id="16023-3659">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="16023-3659">DriversLicense</span></span> 
- <span data-ttu-id="16023-3660">このライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-3660">DriversLicenses</span></span> 
- <span data-ttu-id="16023-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="16023-3661">Drivers Lic</span></span> 
- <span data-ttu-id="16023-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="16023-3662">Drivers Lics</span></span> 
- <span data-ttu-id="16023-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="16023-3663">Drivers License</span></span> 
- <span data-ttu-id="16023-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="16023-3665">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16023-3665">Driver'Lic</span></span> 
- <span data-ttu-id="16023-3666">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16023-3666">Driver'Lics</span></span> 
- <span data-ttu-id="16023-3667">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-3667">Driver'License</span></span> 
- <span data-ttu-id="16023-3668">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="16023-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="16023-3669">Driver' Lic</span></span> 
- <span data-ttu-id="16023-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="16023-3670">Driver' Lics</span></span> 
- <span data-ttu-id="16023-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="16023-3671">Driver' License</span></span> 
- <span data-ttu-id="16023-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-3672">Driver' Licenses</span></span>
- <span data-ttu-id="16023-3673">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="16023-3673">Driver'sLic</span></span> 
- <span data-ttu-id="16023-3674">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="16023-3674">Driver'sLics</span></span> 
- <span data-ttu-id="16023-3675">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="16023-3676">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="16023-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="16023-3677">Driver's Lic</span></span> 
- <span data-ttu-id="16023-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="16023-3678">Driver's Lics</span></span> 
- <span data-ttu-id="16023-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="16023-3679">Driver's License</span></span> 
- <span data-ttu-id="16023-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="16023-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="16023-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="16023-3681">identification number</span></span> 
- <span data-ttu-id="16023-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="16023-3682">identification numbers</span></span> 
- <span data-ttu-id="16023-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="16023-3683">identification #</span></span> 
- <span data-ttu-id="16023-3684">id card</span><span class="sxs-lookup"><span data-stu-id="16023-3684">id card</span></span> 
- <span data-ttu-id="16023-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="16023-3685">id cards</span></span> 
- <span data-ttu-id="16023-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="16023-3686">identification card</span></span> 
- <span data-ttu-id="16023-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="16023-3687">identification cards</span></span> 
- <span data-ttu-id="16023-3688">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="16023-3688">DriverLic#</span></span> 
- <span data-ttu-id="16023-3689">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="16023-3689">DriverLics#</span></span> 
- <span data-ttu-id="16023-3690">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="16023-3690">DriverLicense#</span></span> 
- <span data-ttu-id="16023-3691">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="16023-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="16023-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-3692">Driver Lic#</span></span> 
- <span data-ttu-id="16023-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-3693">Driver Lics#</span></span> 
- <span data-ttu-id="16023-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="16023-3694">Driver License#</span></span> 
- <span data-ttu-id="16023-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="16023-3696">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="16023-3696">DriversLic#</span></span> 
- <span data-ttu-id="16023-3697">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="16023-3697">DriversLics#</span></span> 
- <span data-ttu-id="16023-3698">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="16023-3698">DriversLicense#</span></span> 
- <span data-ttu-id="16023-3699">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="16023-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="16023-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="16023-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="16023-3702">Drivers License#</span></span> 
- <span data-ttu-id="16023-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="16023-3704">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="16023-3705">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="16023-3706">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-3706">Driver'License#</span></span> 
- <span data-ttu-id="16023-3707">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="16023-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="16023-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="16023-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="16023-3710">Driver' License#</span></span> 
- <span data-ttu-id="16023-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="16023-3712">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="16023-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="16023-3713">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="16023-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="16023-3714">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="16023-3715">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="16023-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="16023-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="16023-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="16023-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="16023-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="16023-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="16023-3718">Driver's License#</span></span> 
- <span data-ttu-id="16023-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="16023-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="16023-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="16023-3720">id card#</span></span> 
- <span data-ttu-id="16023-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="16023-3721">id cards#</span></span> 
- <span data-ttu-id="16023-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="16023-3722">identification card#</span></span> 
- <span data-ttu-id="16023-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="16023-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="16023-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="16023-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="16023-3725">州の略号 (たとえば、"NY")</span><span class="sxs-lookup"><span data-stu-id="16023-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="16023-3726">州の名前 (たとえば、"New York")</span><span class="sxs-lookup"><span data-stu-id="16023-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="16023-3727">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="16023-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="16023-3728">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3728">Format</span></span>

<span data-ttu-id="16023-3729">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="16023-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3730">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3730">Pattern</span></span>

<span data-ttu-id="16023-3731">さ</span><span class="sxs-lookup"><span data-stu-id="16023-3731">Formatted:</span></span>
- <span data-ttu-id="16023-3732">数字「9」</span><span class="sxs-lookup"><span data-stu-id="16023-3732">The digit "9"</span></span> 
- <span data-ttu-id="16023-3733">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3733">Two digits</span></span> 
- <span data-ttu-id="16023-3734">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-3734">A space or dash</span></span> 
- <span data-ttu-id="16023-3735">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="16023-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="16023-3736">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3736">A digit</span></span> 
- <span data-ttu-id="16023-3737">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="16023-3737">A space, or dash</span></span> 
- <span data-ttu-id="16023-3738">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3738">Four digits</span></span>

<span data-ttu-id="16023-3739">なし</span><span class="sxs-lookup"><span data-stu-id="16023-3739">Unformatted:</span></span>
- <span data-ttu-id="16023-3740">数字「9」</span><span class="sxs-lookup"><span data-stu-id="16023-3740">The digit "9"</span></span> 
- <span data-ttu-id="16023-3741">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3741">Two digits</span></span> 
- <span data-ttu-id="16023-3742">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="16023-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="16023-3743">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3744">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3744">Checksum</span></span>

<span data-ttu-id="16023-3745">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="16023-3746">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3746">Definition</span></span>

<span data-ttu-id="16023-3747">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3748">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3749">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="16023-3750">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="16023-3751">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="16023-3752">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="16023-3753">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="16023-3754">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3755">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3756">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="16023-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="16023-3757">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="16023-3758">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="16023-3759">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3759">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3760">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="16023-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="16023-3761">Keyword_itin</span></span>

- <span data-ttu-id="16023-3762">納税</span><span class="sxs-lookup"><span data-stu-id="16023-3762">taxpayer</span></span> 
- <span data-ttu-id="16023-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="16023-3763">tax id</span></span> 
- <span data-ttu-id="16023-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="16023-3764">tax identification</span></span> 
- <span data-ttu-id="16023-3765">itin</span><span class="sxs-lookup"><span data-stu-id="16023-3765">itin</span></span> 
- <span data-ttu-id="16023-3766">ssn</span><span class="sxs-lookup"><span data-stu-id="16023-3766">ssn</span></span> 
- <span data-ttu-id="16023-3767">は</span><span class="sxs-lookup"><span data-stu-id="16023-3767">tin</span></span> 
- <span data-ttu-id="16023-3768">social security</span><span class="sxs-lookup"><span data-stu-id="16023-3768">social security</span></span> 
- <span data-ttu-id="16023-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="16023-3769">tax payer</span></span> 
- <span data-ttu-id="16023-3770">itins</span><span class="sxs-lookup"><span data-stu-id="16023-3770">itins</span></span> 
- <span data-ttu-id="16023-3771">taxid</span><span class="sxs-lookup"><span data-stu-id="16023-3771">taxid</span></span> 
- <span data-ttu-id="16023-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="16023-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="16023-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="16023-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="16023-3774">ライセンス</span><span class="sxs-lookup"><span data-stu-id="16023-3774">License</span></span> 
- <span data-ttu-id="16023-3775">DL</span><span class="sxs-lookup"><span data-stu-id="16023-3775">DL</span></span> 
- <span data-ttu-id="16023-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="16023-3776">DOB</span></span> 
- <span data-ttu-id="16023-3777">誕生日</span><span class="sxs-lookup"><span data-stu-id="16023-3777">Birthdate</span></span> 
- <span data-ttu-id="16023-3778">Birthday</span><span class="sxs-lookup"><span data-stu-id="16023-3778">Birthday</span></span> 
- <span data-ttu-id="16023-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="16023-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="16023-3780">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="16023-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="16023-3781">Format</span><span class="sxs-lookup"><span data-stu-id="16023-3781">Format</span></span>

<span data-ttu-id="16023-3782">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="16023-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="16023-3783">2011より前に発行された場合、SSN の書式には、特定の範囲内にある特定の範囲内にある必要があり、チェックサムがないという厳密な形式があります。</span><span class="sxs-lookup"><span data-stu-id="16023-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="16023-3784">パターン</span><span class="sxs-lookup"><span data-stu-id="16023-3784">Pattern</span></span>

<span data-ttu-id="16023-3785">次の4つの異なるパターンで SSNs を検索する4つの関数があります。</span><span class="sxs-lookup"><span data-stu-id="16023-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="16023-3786">Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="16023-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="16023-3787">Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="16023-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="16023-3788">Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="16023-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="16023-3789">Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="16023-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="16023-3790">Checksum</span><span class="sxs-lookup"><span data-stu-id="16023-3790">Checksum</span></span>

<span data-ttu-id="16023-3791">いいえ</span><span class="sxs-lookup"><span data-stu-id="16023-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="16023-3792">定義</span><span class="sxs-lookup"><span data-stu-id="16023-3792">Definition</span></span>

<span data-ttu-id="16023-3793">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3794">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3795">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3795">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="16023-3796">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3797">関数 Func_unformatted_ssn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="16023-3797">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3798">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3798">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="16023-3799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3799">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3800">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3800">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3801">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3801">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="16023-3802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="16023-3802">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="16023-3803">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3803">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="16023-3804">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="16023-3804">A keyword from Keyword_ssn is found.</span></span>


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a><span data-ttu-id="16023-3805">キーワード</span><span class="sxs-lookup"><span data-stu-id="16023-3805">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="16023-3806">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="16023-3806">Keyword_ssn</span></span>

- <span data-ttu-id="16023-3807">Social Security</span><span class="sxs-lookup"><span data-stu-id="16023-3807">Social Security</span></span> 
- <span data-ttu-id="16023-3808">Social Security#</span><span class="sxs-lookup"><span data-stu-id="16023-3808">Social Security#</span></span> 
- <span data-ttu-id="16023-3809">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="16023-3809">Soc Sec</span></span> 
- <span data-ttu-id="16023-3810">SSN</span><span class="sxs-lookup"><span data-stu-id="16023-3810">SSN</span></span> 
- <span data-ttu-id="16023-3811">SSN</span><span class="sxs-lookup"><span data-stu-id="16023-3811">SSNS</span></span> 
- <span data-ttu-id="16023-3812">SSN#</span><span class="sxs-lookup"><span data-stu-id="16023-3812">SSN#</span></span> 
- <span data-ttu-id="16023-3813">秒#</span><span class="sxs-lookup"><span data-stu-id="16023-3813">SS#</span></span> 
- <span data-ttu-id="16023-3814">SSID</span><span class="sxs-lookup"><span data-stu-id="16023-3814">SSID</span></span> 
   

