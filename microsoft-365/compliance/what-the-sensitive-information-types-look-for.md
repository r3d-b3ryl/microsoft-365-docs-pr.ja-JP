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
ms.openlocfilehash: aa3a08961ccad92c9986db16c1d8180d9b0cd17e
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240286"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="8412a-104">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="8412a-104">What the sensitive information types look for</span></span>

<span data-ttu-id="8412a-105">Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できるさまざまな機密情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8412a-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="8412a-106">このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="8412a-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="8412a-107">機密情報の種類はパターンで定義され、正規表現または関数で識別できます。</span><span class="sxs-lookup"><span data-stu-id="8412a-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="8412a-108">機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="8412a-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="8412a-109">信頼レベルと近接も、評価プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8412a-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="8412a-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="8412a-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-111">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-111">Format</span></span>

<span data-ttu-id="8412a-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-113">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-113">Pattern</span></span>

<span data-ttu-id="8412a-114">さ</span><span class="sxs-lookup"><span data-stu-id="8412a-114">Formatted:</span></span>
- <span data-ttu-id="8412a-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="8412a-116">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-116">A hyphen</span></span>
- <span data-ttu-id="8412a-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-117">Four digits</span></span>
- <span data-ttu-id="8412a-118">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-118">A hyphen</span></span>
- <span data-ttu-id="8412a-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-119">A digit</span></span>

<span data-ttu-id="8412a-120">書式なし: 0、1、2、3、6、7、または8で始まる9桁の連続した数字</span><span class="sxs-lookup"><span data-stu-id="8412a-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="8412a-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-121">Checksum</span></span>

<span data-ttu-id="8412a-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-123">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-123">Definition</span></span>

<span data-ttu-id="8412a-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="8412a-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="8412a-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="8412a-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="8412a-129">aba</span><span class="sxs-lookup"><span data-stu-id="8412a-129">aba</span></span>
- <span data-ttu-id="8412a-130">aba #</span><span class="sxs-lookup"><span data-stu-id="8412a-130">aba #</span></span>
- <span data-ttu-id="8412a-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="8412a-131">aba routing #</span></span>
- <span data-ttu-id="8412a-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="8412a-132">aba routing number</span></span>
- <span data-ttu-id="8412a-133">aba#</span><span class="sxs-lookup"><span data-stu-id="8412a-133">aba#</span></span>
- <span data-ttu-id="8412a-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="8412a-134">abarouting#</span></span>
- <span data-ttu-id="8412a-135">aba number</span><span class="sxs-lookup"><span data-stu-id="8412a-135">aba number</span></span>
- <span data-ttu-id="8412a-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-136">abaroutingnumber</span></span>
- <span data-ttu-id="8412a-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="8412a-137">american bank association routing #</span></span>
- <span data-ttu-id="8412a-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="8412a-138">american bank association routing number</span></span>
- <span data-ttu-id="8412a-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="8412a-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="8412a-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="8412a-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="8412a-141">bank routing number</span></span>
- <span data-ttu-id="8412a-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="8412a-142">bankrouting#</span></span>
- <span data-ttu-id="8412a-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-143">bankroutingnumber</span></span>
- <span data-ttu-id="8412a-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="8412a-144">routing transit number</span></span>
- <span data-ttu-id="8412a-145">RTN</span><span class="sxs-lookup"><span data-stu-id="8412a-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="8412a-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-147">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-147">Format</span></span>

<span data-ttu-id="8412a-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-149">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-149">Pattern</span></span>

<span data-ttu-id="8412a-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-150">Eight digits:</span></span>
- <span data-ttu-id="8412a-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-151">Two digits</span></span>
- <span data-ttu-id="8412a-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-152">A period</span></span>
- <span data-ttu-id="8412a-153">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-153">Three digits</span></span>
- <span data-ttu-id="8412a-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-154">A period</span></span>
- <span data-ttu-id="8412a-155">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-156">Checksum</span></span>

<span data-ttu-id="8412a-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-158">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-158">Definition</span></span>

<span data-ttu-id="8412a-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-160">正規表現 Regex_argentina_national_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-161">Keyword_argentina_national_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="8412a-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="8412a-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="8412a-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="8412a-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="8412a-165">Identity</span><span class="sxs-lookup"><span data-stu-id="8412a-165">Identity</span></span> 
- <span data-ttu-id="8412a-166">識別国の Id カード</span><span class="sxs-lookup"><span data-stu-id="8412a-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="8412a-167">DNI</span><span class="sxs-lookup"><span data-stu-id="8412a-167">DNI</span></span> 
- <span data-ttu-id="8412a-168">個人の NIC National レジストリ</span><span class="sxs-lookup"><span data-stu-id="8412a-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="8412a-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="8412a-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="8412a-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="8412a-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="8412a-171">Dad の識別子</span><span class="sxs-lookup"><span data-stu-id="8412a-171">Identidad</span></span> 
- <span data-ttu-id="8412a-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="8412a-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="8412a-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-174">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-174">Format</span></span>

<span data-ttu-id="8412a-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-176">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-176">Pattern</span></span>

<span data-ttu-id="8412a-177">口座番号は 6 ～ 10 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="8412a-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="8412a-178">オーストラリアの銀行の州支店番号:</span><span class="sxs-lookup"><span data-stu-id="8412a-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="8412a-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-179">Three digits</span></span> 
- <span data-ttu-id="8412a-180">ハイフン</span><span class="sxs-lookup"><span data-stu-id="8412a-180">A hyphen</span></span> 
- <span data-ttu-id="8412a-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-182">Checksum</span></span>

<span data-ttu-id="8412a-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-184">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-184">Definition</span></span>

<span data-ttu-id="8412a-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="8412a-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="8412a-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="8412a-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="8412a-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="8412a-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="8412a-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="8412a-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="8412a-194">swift bank code</span></span>
- <span data-ttu-id="8412a-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="8412a-195">correspondent bank</span></span>
- <span data-ttu-id="8412a-196">base currency</span><span class="sxs-lookup"><span data-stu-id="8412a-196">base currency</span></span>
- <span data-ttu-id="8412a-197">usa account</span><span class="sxs-lookup"><span data-stu-id="8412a-197">usa account</span></span>
- <span data-ttu-id="8412a-198">holder address</span><span class="sxs-lookup"><span data-stu-id="8412a-198">holder address</span></span>
- <span data-ttu-id="8412a-199">bank address</span><span class="sxs-lookup"><span data-stu-id="8412a-199">bank address</span></span>
- <span data-ttu-id="8412a-200">information account</span><span class="sxs-lookup"><span data-stu-id="8412a-200">information account</span></span>
- <span data-ttu-id="8412a-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="8412a-201">fund transfers</span></span>
- <span data-ttu-id="8412a-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="8412a-202">bank charges</span></span>
- <span data-ttu-id="8412a-203">bank details</span><span class="sxs-lookup"><span data-stu-id="8412a-203">bank details</span></span>
- <span data-ttu-id="8412a-204">banking information</span><span class="sxs-lookup"><span data-stu-id="8412a-204">banking information</span></span>
- <span data-ttu-id="8412a-205">full names</span><span class="sxs-lookup"><span data-stu-id="8412a-205">full names</span></span>
- <span data-ttu-id="8412a-206">iaea</span><span class="sxs-lookup"><span data-stu-id="8412a-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="8412a-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-208">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-208">Format</span></span>

<span data-ttu-id="8412a-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="8412a-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-210">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-210">Pattern</span></span>

<span data-ttu-id="8412a-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="8412a-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="8412a-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-213">Two digits</span></span> 
- <span data-ttu-id="8412a-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="8412a-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="8412a-215">OR</span><span class="sxs-lookup"><span data-stu-id="8412a-215">OR</span></span>

- <span data-ttu-id="8412a-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-217">4-9 digits</span></span>

<span data-ttu-id="8412a-218">OR</span><span class="sxs-lookup"><span data-stu-id="8412a-218">OR</span></span>

- <span data-ttu-id="8412a-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="8412a-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-220">Checksum</span></span>

<span data-ttu-id="8412a-221">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-222">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-222">Definition</span></span>

<span data-ttu-id="8412a-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="8412a-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="8412a-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="8412a-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8412a-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="8412a-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="8412a-229">international driving permits</span></span>
- <span data-ttu-id="8412a-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="8412a-230">australian automobile association</span></span>
- <span data-ttu-id="8412a-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="8412a-231">international driving permit</span></span>
- <span data-ttu-id="8412a-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="8412a-232">DriverLicence</span></span>
- <span data-ttu-id="8412a-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="8412a-233">DriverLicences</span></span>
- <span data-ttu-id="8412a-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-234">Driver Lic</span></span>
- <span data-ttu-id="8412a-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-235">Driver Licence</span></span>
- <span data-ttu-id="8412a-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-236">Driver Licences</span></span>
- <span data-ttu-id="8412a-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="8412a-237">DriversLic</span></span>
- <span data-ttu-id="8412a-238">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-238">DriversLicence</span></span>
- <span data-ttu-id="8412a-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="8412a-239">DriversLicences</span></span>
- <span data-ttu-id="8412a-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-240">Drivers Lic</span></span>
- <span data-ttu-id="8412a-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-241">Drivers Lics</span></span>
- <span data-ttu-id="8412a-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-242">Drivers Licence</span></span>
- <span data-ttu-id="8412a-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-243">Drivers Licences</span></span>
- <span data-ttu-id="8412a-244">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-244">Driver'Lic</span></span>
- <span data-ttu-id="8412a-245">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-245">Driver'Lics</span></span>
- <span data-ttu-id="8412a-246">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-246">Driver'Licence</span></span>
- <span data-ttu-id="8412a-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-247">Driver'Licences</span></span>
- <span data-ttu-id="8412a-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-248">Driver' Lic</span></span>
- <span data-ttu-id="8412a-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-249">Driver' Lics</span></span>
- <span data-ttu-id="8412a-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-250">Driver' Licence</span></span>
- <span data-ttu-id="8412a-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-251">Driver' Licences</span></span>
- <span data-ttu-id="8412a-252">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="8412a-252">Driver'sLic</span></span>
- <span data-ttu-id="8412a-253">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="8412a-253">Driver'sLics</span></span>
- <span data-ttu-id="8412a-254">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="8412a-254">Driver'sLicence</span></span>
- <span data-ttu-id="8412a-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="8412a-255">Driver'sLicences</span></span>
- <span data-ttu-id="8412a-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-256">Driver's Lic</span></span>
- <span data-ttu-id="8412a-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-257">Driver's Lics</span></span>
- <span data-ttu-id="8412a-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-258">Driver's Licence</span></span>
- <span data-ttu-id="8412a-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-259">Driver's Licences</span></span>
- <span data-ttu-id="8412a-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="8412a-260">DriverLic#</span></span>
- <span data-ttu-id="8412a-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="8412a-261">DriverLics#</span></span>
- <span data-ttu-id="8412a-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="8412a-262">DriverLicence#</span></span>
- <span data-ttu-id="8412a-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="8412a-263">DriverLicences#</span></span>
- <span data-ttu-id="8412a-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-264">Driver Lic#</span></span>
- <span data-ttu-id="8412a-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-265">Driver Lics#</span></span>
- <span data-ttu-id="8412a-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="8412a-266">Driver Licence#</span></span>
- <span data-ttu-id="8412a-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-267">Driver Licences#</span></span>
- <span data-ttu-id="8412a-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="8412a-268">DriversLic#</span></span>
- <span data-ttu-id="8412a-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="8412a-269">DriversLics#</span></span>
- <span data-ttu-id="8412a-270">その他のライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-270">DriversLicence#</span></span>
- <span data-ttu-id="8412a-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="8412a-271">DriversLicences#</span></span>
- <span data-ttu-id="8412a-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-272">Drivers Lic#</span></span>
- <span data-ttu-id="8412a-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-273">Drivers Lics#</span></span>
- <span data-ttu-id="8412a-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="8412a-274">Drivers Licence#</span></span>
- <span data-ttu-id="8412a-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-275">Drivers Licences#</span></span>
- <span data-ttu-id="8412a-276">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-276">Driver'Lic#</span></span>
- <span data-ttu-id="8412a-277">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-277">Driver'Lics#</span></span>
- <span data-ttu-id="8412a-278">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-278">Driver'Licence#</span></span>
- <span data-ttu-id="8412a-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-279">Driver'Licences#</span></span>
- <span data-ttu-id="8412a-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-280">Driver' Lic#</span></span>
- <span data-ttu-id="8412a-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-281">Driver' Lics#</span></span>
- <span data-ttu-id="8412a-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="8412a-282">Driver' Licence#</span></span>
- <span data-ttu-id="8412a-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-283">Driver' Licences#</span></span>
- <span data-ttu-id="8412a-284">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="8412a-284">Driver'sLic#</span></span>
- <span data-ttu-id="8412a-285">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="8412a-285">Driver'sLics#</span></span>
- <span data-ttu-id="8412a-286">ドライバ ' スライスの持続性#</span><span class="sxs-lookup"><span data-stu-id="8412a-286">Driver'sLicence#</span></span>
- <span data-ttu-id="8412a-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="8412a-287">Driver'sLicences#</span></span>
- <span data-ttu-id="8412a-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-288">Driver's Lic#</span></span>
- <span data-ttu-id="8412a-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-289">Driver's Lics#</span></span>
- <span data-ttu-id="8412a-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="8412a-290">Driver's Licence#</span></span>
- <span data-ttu-id="8412a-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="8412a-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="8412a-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="8412a-293">aaa</span><span class="sxs-lookup"><span data-stu-id="8412a-293">aaa</span></span>
- <span data-ttu-id="8412a-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="8412a-294">DriverLicense</span></span>
- <span data-ttu-id="8412a-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="8412a-295">DriverLicenses</span></span>
- <span data-ttu-id="8412a-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="8412a-296">Driver License</span></span>
- <span data-ttu-id="8412a-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-297">Driver Licenses</span></span>
- <span data-ttu-id="8412a-298">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="8412a-298">DriversLicense</span></span>
- <span data-ttu-id="8412a-299">このライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-299">DriversLicenses</span></span>
- <span data-ttu-id="8412a-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8412a-300">Drivers License</span></span>
- <span data-ttu-id="8412a-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-301">Drivers Licenses</span></span>
- <span data-ttu-id="8412a-302">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-302">Driver'License</span></span>
- <span data-ttu-id="8412a-303">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-303">Driver'Licenses</span></span>
- <span data-ttu-id="8412a-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="8412a-304">Driver' License</span></span>
- <span data-ttu-id="8412a-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-305">Driver' Licenses</span></span>
- <span data-ttu-id="8412a-306">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-306">Driver'sLicense</span></span>
- <span data-ttu-id="8412a-307">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-307">Driver'sLicenses</span></span>
- <span data-ttu-id="8412a-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8412a-308">Driver's License</span></span>
- <span data-ttu-id="8412a-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-309">Driver's Licenses</span></span>
- <span data-ttu-id="8412a-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="8412a-310">DriverLicense#</span></span>
- <span data-ttu-id="8412a-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-311">DriverLicenses#</span></span>
- <span data-ttu-id="8412a-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8412a-312">Driver License#</span></span>
- <span data-ttu-id="8412a-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-313">Driver Licenses#</span></span>
- <span data-ttu-id="8412a-314">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="8412a-314">DriversLicense#</span></span>
- <span data-ttu-id="8412a-315">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-315">DriversLicenses#</span></span>
- <span data-ttu-id="8412a-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="8412a-316">Drivers License#</span></span>
- <span data-ttu-id="8412a-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-317">Drivers Licenses#</span></span>
- <span data-ttu-id="8412a-318">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-318">Driver'License#</span></span>
- <span data-ttu-id="8412a-319">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-319">Driver'Licenses#</span></span>
- <span data-ttu-id="8412a-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="8412a-320">Driver' License#</span></span>
- <span data-ttu-id="8412a-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-321">Driver' Licenses#</span></span>
- <span data-ttu-id="8412a-322">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-322">Driver'sLicense#</span></span>
- <span data-ttu-id="8412a-323">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="8412a-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="8412a-324">Driver's License#</span></span>
- <span data-ttu-id="8412a-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="8412a-326">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-327">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-327">Format</span></span>

<span data-ttu-id="8412a-328">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-329">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-329">Pattern</span></span>

<span data-ttu-id="8412a-330">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-330">10-11 digits:</span></span>
- <span data-ttu-id="8412a-331">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="8412a-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="8412a-332">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="8412a-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="8412a-333">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="8412a-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="8412a-334">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="8412a-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-335">Checksum</span></span>

<span data-ttu-id="8412a-336">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-337">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-337">Definition</span></span>

<span data-ttu-id="8412a-338">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-339">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-340">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="8412a-341">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-341">The checksum passes.</span></span>

<span data-ttu-id="8412a-342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-343">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-344">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-345">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="8412a-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="8412a-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="8412a-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="8412a-347">bank account details</span></span>
- <span data-ttu-id="8412a-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="8412a-348">medicare payments</span></span>
- <span data-ttu-id="8412a-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="8412a-349">mortgage account</span></span>
- <span data-ttu-id="8412a-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="8412a-350">bank payments</span></span>
- <span data-ttu-id="8412a-351">information branch</span><span class="sxs-lookup"><span data-stu-id="8412a-351">information branch</span></span>
- <span data-ttu-id="8412a-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="8412a-352">credit card loan</span></span>
- <span data-ttu-id="8412a-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="8412a-353">department of human services</span></span>
- <span data-ttu-id="8412a-354">local service</span><span class="sxs-lookup"><span data-stu-id="8412a-354">local service</span></span>
- <span data-ttu-id="8412a-355">medicare</span><span class="sxs-lookup"><span data-stu-id="8412a-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="8412a-356">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-357">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-357">Format</span></span>

<span data-ttu-id="8412a-358">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-359">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-359">Pattern</span></span>

<span data-ttu-id="8412a-360">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-361">Checksum</span></span>

<span data-ttu-id="8412a-362">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-363">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-363">Definition</span></span>

<span data-ttu-id="8412a-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-365">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-366">Keyword_passport または Keyword_australia_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-367">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="8412a-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-368">Keyword_passport</span></span>

- <span data-ttu-id="8412a-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8412a-369">Passport Number</span></span>
- <span data-ttu-id="8412a-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="8412a-370">Passport No</span></span>
- <span data-ttu-id="8412a-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="8412a-371">Passport #</span></span>
- <span data-ttu-id="8412a-372">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="8412a-372">Passport#</span></span>
- <span data-ttu-id="8412a-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="8412a-373">PassportID</span></span>
- <span data-ttu-id="8412a-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="8412a-374">Passportno</span></span>
- <span data-ttu-id="8412a-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-375">passportnumber</span></span>
- <span data-ttu-id="8412a-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="8412a-376">パスポート</span></span>
- <span data-ttu-id="8412a-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-377">パスポート番号</span></span>
- <span data-ttu-id="8412a-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8412a-378">パスポートのNum</span></span>
- <span data-ttu-id="8412a-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="8412a-379">パスポート ＃</span></span> 
- <span data-ttu-id="8412a-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8412a-380">Numéro de passeport</span></span>
- <span data-ttu-id="8412a-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8412a-381">Passeport n °</span></span>
- <span data-ttu-id="8412a-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8412a-382">Passeport Non</span></span>
- <span data-ttu-id="8412a-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="8412a-383">Passeport #</span></span>
- <span data-ttu-id="8412a-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8412a-384">Passeport#</span></span>
- <span data-ttu-id="8412a-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8412a-385">PasseportNon</span></span>
- <span data-ttu-id="8412a-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8412a-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="8412a-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="8412a-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="8412a-388">サインアウト</span><span class="sxs-lookup"><span data-stu-id="8412a-388">passport</span></span>
- <span data-ttu-id="8412a-389">passport details</span><span class="sxs-lookup"><span data-stu-id="8412a-389">passport details</span></span>
- <span data-ttu-id="8412a-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="8412a-390">immigration and citizenship</span></span>
- <span data-ttu-id="8412a-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="8412a-391">commonwealth of australia</span></span>
- <span data-ttu-id="8412a-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="8412a-392">department of immigration</span></span>
- <span data-ttu-id="8412a-393">residential address</span><span class="sxs-lookup"><span data-stu-id="8412a-393">residential address</span></span>
- <span data-ttu-id="8412a-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="8412a-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="8412a-395">visa</span><span class="sxs-lookup"><span data-stu-id="8412a-395">visa</span></span>
- <span data-ttu-id="8412a-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="8412a-396">national identity card</span></span>
- <span data-ttu-id="8412a-397">passport number</span><span class="sxs-lookup"><span data-stu-id="8412a-397">passport number</span></span>
- <span data-ttu-id="8412a-398">travel document</span><span class="sxs-lookup"><span data-stu-id="8412a-398">travel document</span></span>
- <span data-ttu-id="8412a-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="8412a-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="8412a-400">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="8412a-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-401">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-401">Format</span></span>

<span data-ttu-id="8412a-402">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-403">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-403">Pattern</span></span>

<span data-ttu-id="8412a-404">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8412a-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="8412a-405">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-405">Three digits</span></span> 
- <span data-ttu-id="8412a-406">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="8412a-406">An optional space</span></span> 
- <span data-ttu-id="8412a-407">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-407">Three digits</span></span> 
- <span data-ttu-id="8412a-408">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="8412a-408">An optional space</span></span> 
- <span data-ttu-id="8412a-409">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="8412a-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-410">Checksum</span></span>

<span data-ttu-id="8412a-411">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-412">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-412">Definition</span></span>

<span data-ttu-id="8412a-413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-414">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-415">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="8412a-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="8412a-416">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="8412a-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="8412a-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="8412a-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="8412a-419">australian business number</span></span>
- <span data-ttu-id="8412a-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="8412a-420">marginal tax rate</span></span>
- <span data-ttu-id="8412a-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="8412a-421">medicare levy</span></span>
- <span data-ttu-id="8412a-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="8412a-422">portfolio number</span></span>
- <span data-ttu-id="8412a-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="8412a-423">service veterans</span></span>
- <span data-ttu-id="8412a-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="8412a-424">withholding tax</span></span>
- <span data-ttu-id="8412a-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="8412a-425">individual tax return</span></span>
- <span data-ttu-id="8412a-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="8412a-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="8412a-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="8412a-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="8412a-428">00000000</span><span class="sxs-lookup"><span data-stu-id="8412a-428">00000000</span></span>
- <span data-ttu-id="8412a-429">11111111</span><span class="sxs-lookup"><span data-stu-id="8412a-429">11111111</span></span>
- <span data-ttu-id="8412a-430">22222222</span><span class="sxs-lookup"><span data-stu-id="8412a-430">22222222</span></span>
- <span data-ttu-id="8412a-431">33333333</span><span class="sxs-lookup"><span data-stu-id="8412a-431">33333333</span></span>
- <span data-ttu-id="8412a-432">44444444</span><span class="sxs-lookup"><span data-stu-id="8412a-432">44444444</span></span>
- <span data-ttu-id="8412a-433">55555555</span><span class="sxs-lookup"><span data-stu-id="8412a-433">55555555</span></span>
- <span data-ttu-id="8412a-434">66666666</span><span class="sxs-lookup"><span data-stu-id="8412a-434">66666666</span></span>
- <span data-ttu-id="8412a-435">77777777</span><span class="sxs-lookup"><span data-stu-id="8412a-435">77777777</span></span>
- <span data-ttu-id="8412a-436">88888888</span><span class="sxs-lookup"><span data-stu-id="8412a-436">88888888</span></span>
- <span data-ttu-id="8412a-437">99999999</span><span class="sxs-lookup"><span data-stu-id="8412a-437">99999999</span></span>
- <span data-ttu-id="8412a-438">000000000</span><span class="sxs-lookup"><span data-stu-id="8412a-438">000000000</span></span>
- <span data-ttu-id="8412a-439">111111111</span><span class="sxs-lookup"><span data-stu-id="8412a-439">111111111</span></span>
- <span data-ttu-id="8412a-440">222222222</span><span class="sxs-lookup"><span data-stu-id="8412a-440">222222222</span></span>
- <span data-ttu-id="8412a-441">333333333</span><span class="sxs-lookup"><span data-stu-id="8412a-441">333333333</span></span>
- <span data-ttu-id="8412a-442">444444444</span><span class="sxs-lookup"><span data-stu-id="8412a-442">444444444</span></span>
- <span data-ttu-id="8412a-443">555555555</span><span class="sxs-lookup"><span data-stu-id="8412a-443">555555555</span></span>
- <span data-ttu-id="8412a-444">666666666</span><span class="sxs-lookup"><span data-stu-id="8412a-444">666666666</span></span>
- <span data-ttu-id="8412a-445">777777777</span><span class="sxs-lookup"><span data-stu-id="8412a-445">777777777</span></span>
- <span data-ttu-id="8412a-446">888888888</span><span class="sxs-lookup"><span data-stu-id="8412a-446">888888888</span></span>
- <span data-ttu-id="8412a-447">999999999</span><span class="sxs-lookup"><span data-stu-id="8412a-447">999999999</span></span>
- <span data-ttu-id="8412a-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="8412a-448">0000000000</span></span>
- <span data-ttu-id="8412a-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="8412a-449">1111111111</span></span>
- <span data-ttu-id="8412a-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="8412a-450">2222222222</span></span>
- <span data-ttu-id="8412a-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="8412a-451">3333333333</span></span>
- <span data-ttu-id="8412a-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="8412a-452">4444444444</span></span>
- <span data-ttu-id="8412a-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="8412a-453">5555555555</span></span>
- <span data-ttu-id="8412a-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="8412a-454">6666666666</span></span>
- <span data-ttu-id="8412a-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="8412a-455">7777777777</span></span>
- <span data-ttu-id="8412a-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="8412a-456">8888888888</span></span>
- <span data-ttu-id="8412a-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="8412a-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="8412a-458">Azure DocumentDB 認証キー</span><span class="sxs-lookup"><span data-stu-id="8412a-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="8412a-459">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-459">Format</span></span>

<span data-ttu-id="8412a-460">文字列 "DocumentDb" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="8412a-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-461">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-461">Pattern</span></span>

- <span data-ttu-id="8412a-462">文字列 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="8412a-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="8412a-463">3-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-464">より大きい記号 (>)、等号 (=)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="8412a-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="8412a-465">86の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="8412a-466">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-467">Checksum</span></span>

<span data-ttu-id="8412a-468">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-469">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-469">Definition</span></span>

<span data-ttu-id="8412a-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-471">正規表現 CEP_Regex_AzureDocumentDBAuthKey は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-472">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-473">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-475">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-476">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-476">contoso</span></span>
- <span data-ttu-id="8412a-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-477">fabrikam</span></span>
- <span data-ttu-id="8412a-478">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-478">northwind</span></span>
- <span data-ttu-id="8412a-479">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-479">sandbox</span></span>
- <span data-ttu-id="8412a-480">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-480">onebox</span></span>
- <span data-ttu-id="8412a-481">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-481">localhost</span></span>
- <span data-ttu-id="8412a-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-482">127.0.0.1</span></span>
- <span data-ttu-id="8412a-483">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-484">com</span><span class="sxs-lookup"><span data-stu-id="8412a-484">com</span></span>
- <span data-ttu-id="8412a-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-486">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="8412a-487">Azure IAAS データベースの接続文字列と Azure SQL 接続文字列</span><span class="sxs-lookup"><span data-stu-id="8412a-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="8412a-488">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-488">Format</span></span>

<span data-ttu-id="8412a-489">文字列 "Server"、"server"、または "data source" の後に、次のパターンで概説されている文字と文字列を指定します (文字列 "cloudapp" を含む)。</span><span class="sxs-lookup"><span data-stu-id="8412a-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-490">com または "cloudapp azure。</span><span class="sxs-lookup"><span data-stu-id="8412a-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-491">net "または" database "です。</span><span class="sxs-lookup"><span data-stu-id="8412a-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-492">net "、および" Password "または" pwd "という文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-493">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-493">Pattern</span></span>

- <span data-ttu-id="8412a-494">文字列 "Server"、"server"、または "data source"</span><span class="sxs-lookup"><span data-stu-id="8412a-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="8412a-495">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-496">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-496">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-497">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-498">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-499">文字列 "cloudapp。</span><span class="sxs-lookup"><span data-stu-id="8412a-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-500">com "," cloudapp。</span><span class="sxs-lookup"><span data-stu-id="8412a-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-501">net "、または" database "です。</span><span class="sxs-lookup"><span data-stu-id="8412a-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-502">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-502">net"</span></span>
- <span data-ttu-id="8412a-503">1-300 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-504">文字列 "Password"、"password"、または "pwd"</span><span class="sxs-lookup"><span data-stu-id="8412a-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="8412a-505">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-506">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-506">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-507">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-508">セミコロンではない1つ以上の文字 (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="8412a-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="8412a-509">セミコロン (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="8412a-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-510">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-510">Checksum</span></span>

<span data-ttu-id="8412a-511">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-512">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-512">Definition</span></span>

<span data-ttu-id="8412a-513">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-514">正規表現 CEP_Regex_AzureConnectionString は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-515">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-516">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-518">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-519">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-519">contoso</span></span>
- <span data-ttu-id="8412a-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-520">fabrikam</span></span>
- <span data-ttu-id="8412a-521">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-521">northwind</span></span>
- <span data-ttu-id="8412a-522">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-522">sandbox</span></span>
- <span data-ttu-id="8412a-523">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-523">onebox</span></span>
- <span data-ttu-id="8412a-524">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-524">localhost</span></span>
- <span data-ttu-id="8412a-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-525">127.0.0.1</span></span>
- <span data-ttu-id="8412a-526">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-527">com</span><span class="sxs-lookup"><span data-stu-id="8412a-527">com</span></span>
- <span data-ttu-id="8412a-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-529">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="8412a-530">Azure IoT 接続文字列</span><span class="sxs-lookup"><span data-stu-id="8412a-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="8412a-531">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-531">Format</span></span>

<span data-ttu-id="8412a-532">文字列 "HostName" の後に、次のパターンで概説されている文字と文字列 ("azure デバイス" を含む)。</span><span class="sxs-lookup"><span data-stu-id="8412a-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-533">net "および" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="8412a-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-534">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-534">Pattern</span></span>

- <span data-ttu-id="8412a-535">文字列 "HostName"</span><span class="sxs-lookup"><span data-stu-id="8412a-535">The string "HostName"</span></span>
- <span data-ttu-id="8412a-536">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-537">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-537">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-538">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-539">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-540">文字列 "azure デバイス。</span><span class="sxs-lookup"><span data-stu-id="8412a-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-541">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-541">net"</span></span>
- <span data-ttu-id="8412a-542">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-543">文字列 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="8412a-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="8412a-544">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-545">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-545">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-546">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-547">43の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="8412a-548">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-549">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-549">Checksum</span></span>

<span data-ttu-id="8412a-550">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-551">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-551">Definition</span></span>

<span data-ttu-id="8412a-552">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-553">正規表現 CEP_Regex_AzureIoTConnectionString は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-554">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-555">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-557">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-558">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-558">contoso</span></span>
- <span data-ttu-id="8412a-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-559">fabrikam</span></span>
- <span data-ttu-id="8412a-560">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-560">northwind</span></span>
- <span data-ttu-id="8412a-561">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-561">sandbox</span></span>
- <span data-ttu-id="8412a-562">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-562">onebox</span></span>
- <span data-ttu-id="8412a-563">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-563">localhost</span></span>
- <span data-ttu-id="8412a-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-564">127.0.0.1</span></span>
- <span data-ttu-id="8412a-565">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-566">com</span><span class="sxs-lookup"><span data-stu-id="8412a-566">com</span></span>
- <span data-ttu-id="8412a-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-568">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="8412a-569">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="8412a-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="8412a-570">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-570">Format</span></span>

<span data-ttu-id="8412a-571">文字列 "userpwd =" に続けて英数字の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-572">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-572">Pattern</span></span>

- <span data-ttu-id="8412a-573">文字列 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="8412a-573">The string "userpwd="</span></span>
- <span data-ttu-id="8412a-574">60小文字または数字の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="8412a-575">二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="8412a-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-576">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-576">Checksum</span></span>

<span data-ttu-id="8412a-577">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-578">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-578">Definition</span></span>

<span data-ttu-id="8412a-579">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-580">正規表現 CEP_Regex_AzurePublishSettingPasswords は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-581">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="8412a-582">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-584">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-585">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-585">contoso</span></span>
- <span data-ttu-id="8412a-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-586">fabrikam</span></span>
- <span data-ttu-id="8412a-587">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-587">northwind</span></span>
- <span data-ttu-id="8412a-588">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-588">sandbox</span></span>
- <span data-ttu-id="8412a-589">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-589">onebox</span></span>
- <span data-ttu-id="8412a-590">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-590">localhost</span></span>
- <span data-ttu-id="8412a-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-591">127.0.0.1</span></span>
- <span data-ttu-id="8412a-592">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-593">com</span><span class="sxs-lookup"><span data-stu-id="8412a-593">com</span></span>
- <span data-ttu-id="8412a-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-595">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="8412a-596">Azure Redis Cache 接続文字列</span><span class="sxs-lookup"><span data-stu-id="8412a-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="8412a-597">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-597">Format</span></span>

<span data-ttu-id="8412a-598">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="8412a-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-599">net "の後に、次のパターンで概説されている文字と文字列を指定します。文字列" password "または" pwd "が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8412a-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-600">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-600">Pattern</span></span>

- <span data-ttu-id="8412a-601">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="8412a-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-602">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-602">net"</span></span>
- <span data-ttu-id="8412a-603">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-604">文字列 "password" または "pwd"</span><span class="sxs-lookup"><span data-stu-id="8412a-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="8412a-605">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-606">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-606">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-607">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-608">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="8412a-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="8412a-609">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-610">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-610">Checksum</span></span>

<span data-ttu-id="8412a-611">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-612">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-612">Definition</span></span>

<span data-ttu-id="8412a-613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-614">正規表現 CEP_Regex_AzureRedisCacheConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="8412a-615">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-616">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-618">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-619">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-619">contoso</span></span>
- <span data-ttu-id="8412a-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-620">fabrikam</span></span>
- <span data-ttu-id="8412a-621">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-621">northwind</span></span>
- <span data-ttu-id="8412a-622">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-622">sandbox</span></span>
- <span data-ttu-id="8412a-623">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-623">onebox</span></span>
- <span data-ttu-id="8412a-624">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-624">localhost</span></span>
- <span data-ttu-id="8412a-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-625">127.0.0.1</span></span>
- <span data-ttu-id="8412a-626">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-627">com</span><span class="sxs-lookup"><span data-stu-id="8412a-627">com</span></span>
- <span data-ttu-id="8412a-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-629">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="8412a-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="8412a-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="8412a-631">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-631">Format</span></span>

<span data-ttu-id="8412a-632">文字列 "sig" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="8412a-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-633">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-633">Pattern</span></span>

- <span data-ttu-id="8412a-634">文字列 "sig"</span><span class="sxs-lookup"><span data-stu-id="8412a-634">The string "sig"</span></span>
- <span data-ttu-id="8412a-635">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-636">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-636">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-637">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-638">43-53 文字のうち、下位または大文字の文字、数字、またはパーセント記号 (%) の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="8412a-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="8412a-639">文字列 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="8412a-639">The string "%3d"</span></span>
- <span data-ttu-id="8412a-640">小文字または大文字、数字、パーセント記号 (%) 以外の文字</span><span class="sxs-lookup"><span data-stu-id="8412a-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-641">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-641">Checksum</span></span>

<span data-ttu-id="8412a-642">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-643">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-643">Definition</span></span>

<span data-ttu-id="8412a-644">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-645">正規表現 CEP_Regex_AzureSAS は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="8412a-646">Azure Service Bus の接続文字列</span><span class="sxs-lookup"><span data-stu-id="8412a-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="8412a-647">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-647">Format</span></span>

<span data-ttu-id="8412a-648">文字列 "EndPoint" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="8412a-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-649">net "および" Shared' キー "。</span><span class="sxs-lookup"><span data-stu-id="8412a-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-650">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-650">Pattern</span></span>

- <span data-ttu-id="8412a-651">文字列 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="8412a-651">The string "EndPoint"</span></span>
- <span data-ttu-id="8412a-652">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-653">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-653">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-654">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-655">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-656">文字列 "windows.</span><span class="sxs-lookup"><span data-stu-id="8412a-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-657">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-657">net"</span></span>
- <span data-ttu-id="8412a-658">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-659">文字列 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="8412a-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="8412a-660">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-661">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-661">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-662">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-663">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="8412a-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="8412a-664">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-665">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-665">Checksum</span></span>

<span data-ttu-id="8412a-666">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-667">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-667">Definition</span></span>

<span data-ttu-id="8412a-668">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-669">正規表現 CEP_Regex_AzureServiceBusConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="8412a-670">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-671">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-673">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-674">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-674">contoso</span></span>
- <span data-ttu-id="8412a-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-675">fabrikam</span></span>
- <span data-ttu-id="8412a-676">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-676">northwind</span></span>
- <span data-ttu-id="8412a-677">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-677">sandbox</span></span>
- <span data-ttu-id="8412a-678">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-678">onebox</span></span>
- <span data-ttu-id="8412a-679">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-679">localhost</span></span>
- <span data-ttu-id="8412a-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-680">127.0.0.1</span></span>
- <span data-ttu-id="8412a-681">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-682">com</span><span class="sxs-lookup"><span data-stu-id="8412a-682">com</span></span>
- <span data-ttu-id="8412a-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-684">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="8412a-685">Azure ストレージアカウントキー</span><span class="sxs-lookup"><span data-stu-id="8412a-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="8412a-686">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-686">Format</span></span>

<span data-ttu-id="8412a-687">文字列 "DefaultEndpointsProtocol" の後に、文字列 "AccountKey" を含む、次のパターンで概説されている文字および文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="8412a-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-688">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-688">Pattern</span></span>

- <span data-ttu-id="8412a-689">文字列 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="8412a-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="8412a-690">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-691">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-691">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-692">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-693">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-694">文字列 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="8412a-694">The string "AccountKey"</span></span>
- <span data-ttu-id="8412a-695">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-696">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-696">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-697">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="8412a-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="8412a-698">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="8412a-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="8412a-699">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-700">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-700">Checksum</span></span>

<span data-ttu-id="8412a-701">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-702">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-702">Definition</span></span>

<span data-ttu-id="8412a-703">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-704">正規表現 CEP_Regex_AzureStorageAccountKey は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-705">正規表現 CEP_AzureEmulatorStorageAccountFilter は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-706">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-707">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="8412a-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="8412a-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="8412a-709">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="8412a-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-712">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-713">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-713">contoso</span></span>
- <span data-ttu-id="8412a-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-714">fabrikam</span></span>
- <span data-ttu-id="8412a-715">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-715">northwind</span></span>
- <span data-ttu-id="8412a-716">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-716">sandbox</span></span>
- <span data-ttu-id="8412a-717">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-717">onebox</span></span>
- <span data-ttu-id="8412a-718">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-718">localhost</span></span>
- <span data-ttu-id="8412a-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-719">127.0.0.1</span></span>
- <span data-ttu-id="8412a-720">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-721">com</span><span class="sxs-lookup"><span data-stu-id="8412a-721">com</span></span>
- <span data-ttu-id="8412a-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-723">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="8412a-724">Azure ストレージアカウントキー (汎用)</span><span class="sxs-lookup"><span data-stu-id="8412a-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-725">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-725">Format</span></span>

<span data-ttu-id="8412a-726">86の下または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせで、下のパターンで説明されている文字が前または後にある。</span><span class="sxs-lookup"><span data-stu-id="8412a-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-727">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-727">Pattern</span></span>

- <span data-ttu-id="8412a-728">0-1 より大きい記号 (>)、アポストロフィ (')、等号 (=)、引用符 (")、または番号記号 (#) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="8412a-729">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="8412a-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="8412a-730">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="8412a-731">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-731">Checksum</span></span>

<span data-ttu-id="8412a-732">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-733">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-733">Definition</span></span>

<span data-ttu-id="8412a-734">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-735">正規表現 CEP_Regex_AzureStorageAccountKeyGeneric は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="8412a-736">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="8412a-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-737">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-737">Format</span></span>

<span data-ttu-id="8412a-738">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="8412a-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-739">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-739">Pattern</span></span>

<span data-ttu-id="8412a-740">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="8412a-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="8412a-741">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="8412a-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="8412a-742">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-742">A hyphen</span></span> 
- <span data-ttu-id="8412a-743">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="8412a-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="8412a-744">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="8412a-744">A period</span></span> 
- <span data-ttu-id="8412a-745">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-746">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-746">Checksum</span></span>

<span data-ttu-id="8412a-747">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-748">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-748">Definition</span></span>

<span data-ttu-id="8412a-749">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-750">関数 Func_belgium_national_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-751">Keyword_belgium_national_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="8412a-752">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-753">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="8412a-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="8412a-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="8412a-755">Identity</span><span class="sxs-lookup"><span data-stu-id="8412a-755">Identity</span></span>
- <span data-ttu-id="8412a-756">レジスタ</span><span class="sxs-lookup"><span data-stu-id="8412a-756">Registration</span></span>
- <span data-ttu-id="8412a-757">Fim</span><span class="sxs-lookup"><span data-stu-id="8412a-757">Identification</span></span> 
- <span data-ttu-id="8412a-758">ID</span><span class="sxs-lookup"><span data-stu-id="8412a-758">ID</span></span> 
- <span data-ttu-id="8412a-759">「識別子」</span><span class="sxs-lookup"><span data-stu-id="8412a-759">Identiteitskaart</span></span>
- <span data-ttu-id="8412a-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="8412a-760">Registratie nummer</span></span> 
- <span data-ttu-id="8412a-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="8412a-761">Identificatie nummer</span></span> 
- <span data-ttu-id="8412a-762">識別子</span><span class="sxs-lookup"><span data-stu-id="8412a-762">Identiteit</span></span>
- <span data-ttu-id="8412a-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="8412a-763">Registratie</span></span>
- <span data-ttu-id="8412a-764">識別子</span><span class="sxs-lookup"><span data-stu-id="8412a-764">Identificatie</span></span> 
- <span data-ttu-id="8412a-765">個別の d'identité</span><span class="sxs-lookup"><span data-stu-id="8412a-765">Carte d'identité</span></span> 
- <span data-ttu-id="8412a-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="8412a-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="8412a-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="8412a-767">numéro d'identification</span></span>
- <span data-ttu-id="8412a-768">識別子</span><span class="sxs-lookup"><span data-stu-id="8412a-768">identité</span></span> 
- <span data-ttu-id="8412a-769">inscription</span><span class="sxs-lookup"><span data-stu-id="8412a-769">inscription</span></span> 
- <span data-ttu-id="8412a-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="8412a-770">Identifikation</span></span>
- <span data-ttu-id="8412a-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="8412a-771">Identifizierung</span></span>
- <span data-ttu-id="8412a-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-772">Identifikationsnummer</span></span>
- <span data-ttu-id="8412a-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="8412a-773">Personalausweis</span></span>
- <span data-ttu-id="8412a-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="8412a-774">Registrierung</span></span>
- <span data-ttu-id="8412a-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="8412a-776">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-777">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-777">Format</span></span>

<span data-ttu-id="8412a-778">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-779">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-779">Pattern</span></span>

<span data-ttu-id="8412a-780">さ</span><span class="sxs-lookup"><span data-stu-id="8412a-780">Formatted:</span></span>
- <span data-ttu-id="8412a-781">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-781">Three digits</span></span> 
- <span data-ttu-id="8412a-782">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-782">A period</span></span> 
- <span data-ttu-id="8412a-783">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-783">Three digits</span></span> 
- <span data-ttu-id="8412a-784">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-784">A period</span></span> 
- <span data-ttu-id="8412a-785">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-785">Three digits</span></span> 
- <span data-ttu-id="8412a-786">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-786">A hyphen</span></span> 
- <span data-ttu-id="8412a-787">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-787">Two digits which are check digits</span></span>

<span data-ttu-id="8412a-788">なし</span><span class="sxs-lookup"><span data-stu-id="8412a-788">Unformatted:</span></span>
- <span data-ttu-id="8412a-789">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="8412a-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-790">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-790">Checksum</span></span>

<span data-ttu-id="8412a-791">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-792">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-792">Definition</span></span>

<span data-ttu-id="8412a-793">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-794">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-795">Keyword_brazil_cpf からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="8412a-796">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-796">The checksum passes.</span></span>

<span data-ttu-id="8412a-797">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-798">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-799">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-800">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="8412a-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="8412a-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="8412a-802">CPF</span><span class="sxs-lookup"><span data-stu-id="8412a-802">CPF</span></span>
- <span data-ttu-id="8412a-803">Fim</span><span class="sxs-lookup"><span data-stu-id="8412a-803">Identification</span></span>
- <span data-ttu-id="8412a-804">レジスタ</span><span class="sxs-lookup"><span data-stu-id="8412a-804">Registration</span></span>
- <span data-ttu-id="8412a-805">増大</span><span class="sxs-lookup"><span data-stu-id="8412a-805">Revenue</span></span>
- <span data-ttu-id="8412a-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="8412a-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="8412a-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="8412a-807">Imposto</span></span> 
- <span data-ttu-id="8412a-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="8412a-808">Identificação</span></span> 
- <span data-ttu-id="8412a-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="8412a-809">Inscrição</span></span> 
- <span data-ttu-id="8412a-810">Receita</span><span class="sxs-lookup"><span data-stu-id="8412a-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="8412a-811">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8412a-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-812">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-812">Format</span></span>

<span data-ttu-id="8412a-813">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-814">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-814">Pattern</span></span>
<span data-ttu-id="8412a-815">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="8412a-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="8412a-816">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-816">Two digits</span></span> 
- <span data-ttu-id="8412a-817">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-817">A period</span></span> 
- <span data-ttu-id="8412a-818">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-818">Three digits</span></span> 
- <span data-ttu-id="8412a-819">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-819">A period</span></span> 
- <span data-ttu-id="8412a-820">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="8412a-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="8412a-821">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-821">A forward slash</span></span> 
- <span data-ttu-id="8412a-822">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="8412a-822">Four-digit branch number</span></span> 
- <span data-ttu-id="8412a-823">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-823">A hyphen</span></span> 
- <span data-ttu-id="8412a-824">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-825">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-825">Checksum</span></span>

<span data-ttu-id="8412a-826">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-827">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-827">Definition</span></span>

<span data-ttu-id="8412a-828">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-829">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-830">Keyword_brazil_cnpj からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="8412a-831">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-831">The checksum passes.</span></span>

<span data-ttu-id="8412a-832">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-833">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-834">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-835">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="8412a-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="8412a-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="8412a-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="8412a-837">CNPJ</span></span> 
- <span data-ttu-id="8412a-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="8412a-838">CNPJ/MF</span></span> 
- <span data-ttu-id="8412a-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="8412a-839">CNPJ-MF</span></span> 
- <span data-ttu-id="8412a-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="8412a-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="8412a-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="8412a-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="8412a-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="8412a-842">Legal entity</span></span> 
- <span data-ttu-id="8412a-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="8412a-843">Legal entities</span></span> 
- <span data-ttu-id="8412a-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="8412a-844">Registration Status</span></span> 
- <span data-ttu-id="8412a-845">Business</span><span class="sxs-lookup"><span data-stu-id="8412a-845">Business</span></span> 
- <span data-ttu-id="8412a-846">会社名</span><span class="sxs-lookup"><span data-stu-id="8412a-846">Company</span></span>
- <span data-ttu-id="8412a-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="8412a-847">CNPJ</span></span> 
- <span data-ttu-id="8412a-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="8412a-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="8412a-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="8412a-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="8412a-850">CGC</span><span class="sxs-lookup"><span data-stu-id="8412a-850">CGC</span></span> 
- <span data-ttu-id="8412a-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="8412a-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="8412a-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="8412a-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="8412a-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="8412a-853">Situação cadastral</span></span> 
- <span data-ttu-id="8412a-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="8412a-854">Inscrição</span></span> 
- <span data-ttu-id="8412a-855">サイト</span><span class="sxs-lookup"><span data-stu-id="8412a-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="8412a-856">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="8412a-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-857">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-857">Format</span></span>

<span data-ttu-id="8412a-858">Registro Geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="8412a-859">Registro de 識別子 Dade (RIC) (新しい形式):11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-860">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-860">Pattern</span></span>

<span data-ttu-id="8412a-861">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="8412a-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="8412a-862">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-862">Two digits</span></span> 
- <span data-ttu-id="8412a-863">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-863">A period</span></span> 
- <span data-ttu-id="8412a-864">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-864">Three digits</span></span> 
- <span data-ttu-id="8412a-865">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-865">A period</span></span> 
- <span data-ttu-id="8412a-866">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-866">Three digits</span></span> 
- <span data-ttu-id="8412a-867">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-867">A hyphen</span></span> 
- <span data-ttu-id="8412a-868">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-868">One digit which is a check digit</span></span>

<span data-ttu-id="8412a-869">Registro de 識別子 Dade (RIC) (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="8412a-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="8412a-870">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-870">10 digits</span></span> 
- <span data-ttu-id="8412a-871">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-871">A hyphen</span></span> 
- <span data-ttu-id="8412a-872">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-873">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-873">Checksum</span></span>

<span data-ttu-id="8412a-874">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-875">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-875">Definition</span></span>

<span data-ttu-id="8412a-876">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-877">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-878">Keyword_brazil_rg からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="8412a-879">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-879">The checksum passes.</span></span>

<span data-ttu-id="8412a-880">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-881">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-882">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-883">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="8412a-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="8412a-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="8412a-885">Cédula de 識別子 dade id カード national id número de rregistro registro de I識別子 Dade registro geral このキーワードは大文字と小文字を区別します) RIC (このキーワードは大文字と小文字を区別します)</span><span class="sxs-lookup"><span data-stu-id="8412a-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="8412a-886">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-887">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-887">Format</span></span>

<span data-ttu-id="8412a-888">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-889">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-889">Pattern</span></span>

<span data-ttu-id="8412a-890">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="8412a-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="8412a-891">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8412a-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="8412a-892">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-892">Five digits</span></span> 
- <span data-ttu-id="8412a-893">ハイフン</span><span class="sxs-lookup"><span data-stu-id="8412a-893">A hyphen</span></span> 
- <span data-ttu-id="8412a-894">3桁の数字または</span><span class="sxs-lookup"><span data-stu-id="8412a-894">Three digits OR</span></span>
- <span data-ttu-id="8412a-895">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="8412a-895">A zero "0"</span></span> 
- <span data-ttu-id="8412a-896">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-897">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-897">Checksum</span></span>

<span data-ttu-id="8412a-898">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-899">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-899">Definition</span></span>

<span data-ttu-id="8412a-900">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-901">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-902">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="8412a-903">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="8412a-904">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-905">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-906">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-907">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="8412a-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="8412a-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="8412a-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="8412a-909">canada savings bonds</span></span>
- <span data-ttu-id="8412a-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="8412a-910">canada revenue agency</span></span>
- <span data-ttu-id="8412a-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="8412a-911">canadian financial institution</span></span>
- <span data-ttu-id="8412a-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="8412a-912">direct deposit form</span></span>
- <span data-ttu-id="8412a-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="8412a-913">canadian citizen</span></span>
- <span data-ttu-id="8412a-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="8412a-914">legal representative</span></span>
- <span data-ttu-id="8412a-915">notary public</span><span class="sxs-lookup"><span data-stu-id="8412a-915">notary public</span></span>
- <span data-ttu-id="8412a-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="8412a-916">commissioner for oaths</span></span>
- <span data-ttu-id="8412a-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="8412a-917">child care benefit</span></span>
- <span data-ttu-id="8412a-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="8412a-918">universal child care</span></span>
- <span data-ttu-id="8412a-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="8412a-919">canada child tax benefit</span></span>
- <span data-ttu-id="8412a-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="8412a-920">income tax benefit</span></span>
- <span data-ttu-id="8412a-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="8412a-921">harmonized sales tax</span></span>
- <span data-ttu-id="8412a-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="8412a-922">social insurance number</span></span>
- <span data-ttu-id="8412a-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="8412a-923">income tax refund</span></span>
- <span data-ttu-id="8412a-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="8412a-924">child tax benefit</span></span>
- <span data-ttu-id="8412a-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="8412a-925">territorial payments</span></span>
- <span data-ttu-id="8412a-926">institution number</span><span class="sxs-lookup"><span data-stu-id="8412a-926">institution number</span></span>
- <span data-ttu-id="8412a-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="8412a-927">deposit request</span></span>
- <span data-ttu-id="8412a-928">banking information</span><span class="sxs-lookup"><span data-stu-id="8412a-928">banking information</span></span>
- <span data-ttu-id="8412a-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="8412a-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="8412a-930">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-931">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-931">Format</span></span>

<span data-ttu-id="8412a-932">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="8412a-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-933">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-933">Pattern</span></span>

<span data-ttu-id="8412a-934">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-935">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-935">Checksum</span></span>

<span data-ttu-id="8412a-936">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-937">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-937">Definition</span></span>

<span data-ttu-id="8412a-938">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-939">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-940">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="8412a-941">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-942">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="8412a-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="8412a-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="8412a-944">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="8412a-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="8412a-945">州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="8412a-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="8412a-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8412a-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="8412a-947">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-947">DL</span></span>
- <span data-ttu-id="8412a-948">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-948">DLS</span></span>
- <span data-ttu-id="8412a-949">CDL</span><span class="sxs-lookup"><span data-stu-id="8412a-949">CDL</span></span>
- <span data-ttu-id="8412a-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="8412a-950">CDLS</span></span>
- <span data-ttu-id="8412a-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="8412a-951">DriverLic</span></span>
- <span data-ttu-id="8412a-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="8412a-952">DriverLics</span></span>
- <span data-ttu-id="8412a-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="8412a-953">DriverLicense</span></span>
- <span data-ttu-id="8412a-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="8412a-954">DriverLicenses</span></span>
- <span data-ttu-id="8412a-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="8412a-955">DriverLicence</span></span>
- <span data-ttu-id="8412a-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="8412a-956">DriverLicences</span></span>
- <span data-ttu-id="8412a-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-957">Driver Lic</span></span>
- <span data-ttu-id="8412a-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-958">Driver Lics</span></span>
- <span data-ttu-id="8412a-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="8412a-959">Driver License</span></span>
- <span data-ttu-id="8412a-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-960">Driver Licenses</span></span>
- <span data-ttu-id="8412a-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-961">Driver Licence</span></span>
- <span data-ttu-id="8412a-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-962">Driver Licences</span></span>
- <span data-ttu-id="8412a-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="8412a-963">DriversLic</span></span>
- <span data-ttu-id="8412a-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="8412a-964">DriversLics</span></span>
- <span data-ttu-id="8412a-965">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-965">DriversLicence</span></span>
- <span data-ttu-id="8412a-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="8412a-966">DriversLicences</span></span>
- <span data-ttu-id="8412a-967">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="8412a-967">DriversLicense</span></span>
- <span data-ttu-id="8412a-968">このライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-968">DriversLicenses</span></span>
- <span data-ttu-id="8412a-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-969">Drivers Lic</span></span>
- <span data-ttu-id="8412a-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-970">Drivers Lics</span></span>
- <span data-ttu-id="8412a-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8412a-971">Drivers License</span></span>
- <span data-ttu-id="8412a-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-972">Drivers Licenses</span></span>
- <span data-ttu-id="8412a-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-973">Drivers Licence</span></span>
- <span data-ttu-id="8412a-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-974">Drivers Licences</span></span>
- <span data-ttu-id="8412a-975">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-975">Driver'Lic</span></span>
- <span data-ttu-id="8412a-976">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-976">Driver'Lics</span></span>
- <span data-ttu-id="8412a-977">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-977">Driver'License</span></span>
- <span data-ttu-id="8412a-978">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-978">Driver'Licenses</span></span>
- <span data-ttu-id="8412a-979">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-979">Driver'Licence</span></span>
- <span data-ttu-id="8412a-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-980">Driver'Licences</span></span>
- <span data-ttu-id="8412a-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-981">Driver' Lic</span></span>
- <span data-ttu-id="8412a-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-982">Driver' Lics</span></span>
- <span data-ttu-id="8412a-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="8412a-983">Driver' License</span></span>
- <span data-ttu-id="8412a-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-984">Driver' Licenses</span></span>
- <span data-ttu-id="8412a-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-985">Driver' Licence</span></span>
- <span data-ttu-id="8412a-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-986">Driver' Licences</span></span>
- <span data-ttu-id="8412a-987">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="8412a-987">Driver'sLic</span></span>
- <span data-ttu-id="8412a-988">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="8412a-988">Driver'sLics</span></span>
- <span data-ttu-id="8412a-989">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-989">Driver'sLicense</span></span>
- <span data-ttu-id="8412a-990">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-990">Driver'sLicenses</span></span>
- <span data-ttu-id="8412a-991">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="8412a-991">Driver'sLicence</span></span>
- <span data-ttu-id="8412a-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="8412a-992">Driver'sLicences</span></span>
- <span data-ttu-id="8412a-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-993">Driver's Lic</span></span>
- <span data-ttu-id="8412a-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-994">Driver's Lics</span></span>
- <span data-ttu-id="8412a-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8412a-995">Driver's License</span></span>
- <span data-ttu-id="8412a-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-996">Driver's Licenses</span></span>
- <span data-ttu-id="8412a-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-997">Driver's Licence</span></span>
- <span data-ttu-id="8412a-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-998">Driver's Licences</span></span>
- <span data-ttu-id="8412a-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="8412a-999">Permis de Conduire</span></span>
- <span data-ttu-id="8412a-1000">id</span><span class="sxs-lookup"><span data-stu-id="8412a-1000">id</span></span>
- <span data-ttu-id="8412a-1001">ids</span><span class="sxs-lookup"><span data-stu-id="8412a-1001">ids</span></span>
- <span data-ttu-id="8412a-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="8412a-1002">idcard number</span></span>
- <span data-ttu-id="8412a-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-1003">idcard numbers</span></span>
- <span data-ttu-id="8412a-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="8412a-1004">idcard #</span></span>
- <span data-ttu-id="8412a-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="8412a-1005">idcard #s</span></span>
- <span data-ttu-id="8412a-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="8412a-1006">idcard card</span></span>
- <span data-ttu-id="8412a-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1007">idcard cards</span></span>
- <span data-ttu-id="8412a-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1008">idcard</span></span>
- <span data-ttu-id="8412a-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="8412a-1009">identification number</span></span>
- <span data-ttu-id="8412a-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-1010">identification numbers</span></span>
- <span data-ttu-id="8412a-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="8412a-1011">identification #</span></span>
- <span data-ttu-id="8412a-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="8412a-1012">identification #s</span></span>
- <span data-ttu-id="8412a-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="8412a-1013">identification card</span></span>
- <span data-ttu-id="8412a-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1014">identification cards</span></span>
- <span data-ttu-id="8412a-1015">fim</span><span class="sxs-lookup"><span data-stu-id="8412a-1015">identification</span></span> 
- <span data-ttu-id="8412a-1016">DL#</span><span class="sxs-lookup"><span data-stu-id="8412a-1016">DL#</span></span>
- <span data-ttu-id="8412a-1017">DL#</span><span class="sxs-lookup"><span data-stu-id="8412a-1017">DLS#</span></span> 
- <span data-ttu-id="8412a-1018">CDL#</span><span class="sxs-lookup"><span data-stu-id="8412a-1018">CDL#</span></span> 
- <span data-ttu-id="8412a-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="8412a-1019">CDLS#</span></span> 
- <span data-ttu-id="8412a-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1020">DriverLic#</span></span> 
- <span data-ttu-id="8412a-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1021">DriverLics#</span></span> 
- <span data-ttu-id="8412a-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="8412a-1022">DriverLicense#</span></span> 
- <span data-ttu-id="8412a-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="8412a-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="8412a-1024">DriverLicence#</span></span> 
- <span data-ttu-id="8412a-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1025">DriverLicences#</span></span> 
- <span data-ttu-id="8412a-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1026">Driver Lic#</span></span>
- <span data-ttu-id="8412a-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1027">Driver Lics#</span></span> 
- <span data-ttu-id="8412a-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8412a-1028">Driver License#</span></span> 
- <span data-ttu-id="8412a-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="8412a-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8412a-1030">Driver License#</span></span> 
- <span data-ttu-id="8412a-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1031">Driver Licences#</span></span> 
- <span data-ttu-id="8412a-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1032">DriversLic#</span></span> 
- <span data-ttu-id="8412a-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1033">DriversLics#</span></span> 
- <span data-ttu-id="8412a-1034">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="8412a-1034">DriversLicense#</span></span> 
- <span data-ttu-id="8412a-1035">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="8412a-1036">その他のライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-1036">DriversLicence#</span></span> 
- <span data-ttu-id="8412a-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1037">DriversLicences#</span></span> 
- <span data-ttu-id="8412a-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="8412a-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="8412a-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="8412a-1040">Drivers License#</span></span> 
- <span data-ttu-id="8412a-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="8412a-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="8412a-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="8412a-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="8412a-1044">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="8412a-1045">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="8412a-1046">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-1046">Driver'License#</span></span> 
- <span data-ttu-id="8412a-1047">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="8412a-1048">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="8412a-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="8412a-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="8412a-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="8412a-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="8412a-1052">Driver' License#</span></span> 
- <span data-ttu-id="8412a-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="8412a-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="8412a-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="8412a-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="8412a-1056">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="8412a-1057">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="8412a-1058">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="8412a-1059">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="8412a-1060">ドライバ ' スライスの持続性#</span><span class="sxs-lookup"><span data-stu-id="8412a-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="8412a-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="8412a-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="8412a-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="8412a-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="8412a-1064">Driver's License#</span></span> 
- <span data-ttu-id="8412a-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="8412a-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="8412a-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="8412a-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="8412a-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="8412a-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="8412a-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="8412a-1069">rid#</span><span class="sxs-lookup"><span data-stu-id="8412a-1069">id#</span></span> 
- <span data-ttu-id="8412a-1070">rid#</span><span class="sxs-lookup"><span data-stu-id="8412a-1070">ids#</span></span> 
- <span data-ttu-id="8412a-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="8412a-1071">idcard card#</span></span> 
- <span data-ttu-id="8412a-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="8412a-1072">idcard cards#</span></span> 
- <span data-ttu-id="8412a-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="8412a-1073">idcard#</span></span> 
- <span data-ttu-id="8412a-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="8412a-1074">identification card#</span></span> 
- <span data-ttu-id="8412a-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="8412a-1075">identification cards#</span></span> 
- <span data-ttu-id="8412a-1076">fim#</span><span class="sxs-lookup"><span data-stu-id="8412a-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="8412a-1077">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1078">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1078">Format</span></span>

<span data-ttu-id="8412a-1079">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1080">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1080">Pattern</span></span>

<span data-ttu-id="8412a-1081">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1082">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1082">Checksum</span></span>

<span data-ttu-id="8412a-1083">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1084">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1084">Definition</span></span>

<span data-ttu-id="8412a-1085">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1086">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1087">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1088">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="8412a-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="8412a-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="8412a-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="8412a-1090">personal health number</span></span>
- <span data-ttu-id="8412a-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="8412a-1091">patient information</span></span>
- <span data-ttu-id="8412a-1092">health services</span><span class="sxs-lookup"><span data-stu-id="8412a-1092">health services</span></span>
- <span data-ttu-id="8412a-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="8412a-1093">speciality services</span></span>
- <span data-ttu-id="8412a-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="8412a-1094">automobile accident</span></span>
- <span data-ttu-id="8412a-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="8412a-1095">patient hospital</span></span>
- <span data-ttu-id="8412a-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="8412a-1096">psychiatrist</span></span>
- <span data-ttu-id="8412a-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="8412a-1097">workers compensation</span></span>
- <span data-ttu-id="8412a-1098">身体</span><span class="sxs-lookup"><span data-stu-id="8412a-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="8412a-1099">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1100">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1100">Format</span></span>

<span data-ttu-id="8412a-1101">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1102">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1102">Pattern</span></span>

<span data-ttu-id="8412a-1103">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1104">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1104">Checksum</span></span>

<span data-ttu-id="8412a-1105">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1106">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1106">Definition</span></span>

<span data-ttu-id="8412a-1107">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1108">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1109">Keyword_canada_passport_number または Keyword_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1110">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="8412a-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="8412a-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="8412a-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="8412a-1112">canadian citizenship</span></span>
- <span data-ttu-id="8412a-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="8412a-1113">canadian passport</span></span>
- <span data-ttu-id="8412a-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="8412a-1114">passport application</span></span>
- <span data-ttu-id="8412a-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="8412a-1115">passport photos</span></span>
- <span data-ttu-id="8412a-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="8412a-1116">certified translator</span></span>
- <span data-ttu-id="8412a-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="8412a-1117">canadian citizens</span></span>
- <span data-ttu-id="8412a-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="8412a-1118">processing times</span></span>
- <span data-ttu-id="8412a-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="8412a-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="8412a-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-1120">Keyword_passport</span></span>

- <span data-ttu-id="8412a-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8412a-1121">Passport Number</span></span>
- <span data-ttu-id="8412a-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="8412a-1122">Passport No</span></span>
- <span data-ttu-id="8412a-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="8412a-1123">Passport #</span></span>
- <span data-ttu-id="8412a-1124">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="8412a-1124">Passport#</span></span>
- <span data-ttu-id="8412a-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="8412a-1125">PassportID</span></span>
- <span data-ttu-id="8412a-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="8412a-1126">Passportno</span></span>
- <span data-ttu-id="8412a-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-1127">passportnumber</span></span>
- <span data-ttu-id="8412a-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="8412a-1128">パスポート</span></span>
- <span data-ttu-id="8412a-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1129">パスポート番号</span></span>
- <span data-ttu-id="8412a-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8412a-1130">パスポートのNum</span></span>
- <span data-ttu-id="8412a-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="8412a-1131">パスポート＃</span></span>
- <span data-ttu-id="8412a-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8412a-1132">Numéro de passeport</span></span>
- <span data-ttu-id="8412a-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8412a-1133">Passeport n °</span></span>
- <span data-ttu-id="8412a-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8412a-1134">Passeport Non</span></span>
- <span data-ttu-id="8412a-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="8412a-1135">Passeport #</span></span>
- <span data-ttu-id="8412a-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8412a-1136">Passeport#</span></span>
- <span data-ttu-id="8412a-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8412a-1137">PasseportNon</span></span>
- <span data-ttu-id="8412a-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8412a-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="8412a-1139">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="8412a-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1140">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1140">Format</span></span>

<span data-ttu-id="8412a-1141">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1142">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1142">Pattern</span></span>

<span data-ttu-id="8412a-1143">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1144">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1144">Checksum</span></span>

<span data-ttu-id="8412a-1145">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1146">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1146">Definition</span></span>

<span data-ttu-id="8412a-1147">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_canada_phin は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="8412a-1148">Keyword_canada_phin または Keyword_canada_provinces から少なくとも2つのキーワードが見つかります。</span><span class="sxs-lookup"><span data-stu-id="8412a-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1149">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="8412a-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="8412a-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="8412a-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="8412a-1151">social insurance number</span></span>
- <span data-ttu-id="8412a-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="8412a-1152">health information act</span></span>
- <span data-ttu-id="8412a-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="8412a-1153">income tax information</span></span>
- <span data-ttu-id="8412a-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="8412a-1154">manitoba health</span></span>
- <span data-ttu-id="8412a-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="8412a-1155">health registration</span></span>
- <span data-ttu-id="8412a-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="8412a-1156">prescription purchases</span></span>
- <span data-ttu-id="8412a-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="8412a-1157">benefit eligibility</span></span>
- <span data-ttu-id="8412a-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="8412a-1158">personal health</span></span>
- <span data-ttu-id="8412a-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="8412a-1159">power of attorney</span></span>
- <span data-ttu-id="8412a-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="8412a-1160">registration number</span></span>
- <span data-ttu-id="8412a-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="8412a-1161">personal health number</span></span>
- <span data-ttu-id="8412a-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="8412a-1162">practitioner referral</span></span>
- <span data-ttu-id="8412a-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="8412a-1163">wellness professional</span></span>
- <span data-ttu-id="8412a-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="8412a-1164">patient referral</span></span>
- <span data-ttu-id="8412a-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="8412a-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="8412a-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="8412a-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="8412a-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="8412a-1167">Nunavut</span></span>
- <span data-ttu-id="8412a-1168">州</span><span class="sxs-lookup"><span data-stu-id="8412a-1168">Quebec</span></span>
- <span data-ttu-id="8412a-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="8412a-1169">Northwest Territories</span></span>
- <span data-ttu-id="8412a-1170">オンタリオ州</span><span class="sxs-lookup"><span data-stu-id="8412a-1170">Ontario</span></span>
- <span data-ttu-id="8412a-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="8412a-1171">British Columbia</span></span>
- <span data-ttu-id="8412a-1172">州</span><span class="sxs-lookup"><span data-stu-id="8412a-1172">Alberta</span></span>
- <span data-ttu-id="8412a-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="8412a-1173">Saskatchewan</span></span>
- <span data-ttu-id="8412a-1174">マニトバ州</span><span class="sxs-lookup"><span data-stu-id="8412a-1174">Manitoba</span></span>
- <span data-ttu-id="8412a-1175">州</span><span class="sxs-lookup"><span data-stu-id="8412a-1175">Yukon</span></span>
- <span data-ttu-id="8412a-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="8412a-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="8412a-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="8412a-1177">New Brunswick</span></span>
- <span data-ttu-id="8412a-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="8412a-1178">Nova Scotia</span></span>
- <span data-ttu-id="8412a-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="8412a-1179">Prince Edward Island</span></span>
- <span data-ttu-id="8412a-1180">カナダ</span><span class="sxs-lookup"><span data-stu-id="8412a-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="8412a-1181">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1182">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1182">Format</span></span>

<span data-ttu-id="8412a-1183">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="8412a-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1184">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1184">Pattern</span></span>

<span data-ttu-id="8412a-1185">さ</span><span class="sxs-lookup"><span data-stu-id="8412a-1185">Formatted:</span></span>
- <span data-ttu-id="8412a-1186">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1186">Three digits</span></span> 
- <span data-ttu-id="8412a-1187">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="8412a-1187">A hyphen or space</span></span> 
- <span data-ttu-id="8412a-1188">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1188">Three digits</span></span> 
- <span data-ttu-id="8412a-1189">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="8412a-1189">A hyphen or space</span></span> 
- <span data-ttu-id="8412a-1190">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1190">Three digits</span></span>

<span data-ttu-id="8412a-1191">書式なし: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1192">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1192">Checksum</span></span>

<span data-ttu-id="8412a-1193">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1194">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1194">Definition</span></span>

<span data-ttu-id="8412a-1195">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1196">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1197">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="8412a-1198">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="8412a-1199">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="8412a-1200">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8412a-1201">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1201">The checksum passes.</span></span>

<span data-ttu-id="8412a-1202">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1203">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1204">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="8412a-1205">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1206">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="8412a-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="8412a-1207">Keyword_sin</span></span>

- <span data-ttu-id="8412a-1208">sin</span><span class="sxs-lookup"><span data-stu-id="8412a-1208">sin</span></span> 
- <span data-ttu-id="8412a-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="8412a-1209">social insurance</span></span> 
- <span data-ttu-id="8412a-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="8412a-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="8412a-1211">大罪</span><span class="sxs-lookup"><span data-stu-id="8412a-1211">sins</span></span> 
- <span data-ttu-id="8412a-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="8412a-1212">ssn</span></span> 
- <span data-ttu-id="8412a-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="8412a-1213">ssns</span></span> 
- <span data-ttu-id="8412a-1214">social security</span><span class="sxs-lookup"><span data-stu-id="8412a-1214">social security</span></span> 
- <span data-ttu-id="8412a-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="8412a-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="8412a-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="8412a-1216">national identification number</span></span> 
- <span data-ttu-id="8412a-1217">national id</span><span class="sxs-lookup"><span data-stu-id="8412a-1217">national id</span></span> 
- <span data-ttu-id="8412a-1218">sin#</span><span class="sxs-lookup"><span data-stu-id="8412a-1218">sin#</span></span> 
- <span data-ttu-id="8412a-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="8412a-1219">soc ins</span></span> 
- <span data-ttu-id="8412a-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="8412a-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="8412a-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="8412a-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="8412a-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="8412a-1222">driver's license</span></span> 
- <span data-ttu-id="8412a-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="8412a-1223">drivers license</span></span> 
- <span data-ttu-id="8412a-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8412a-1224">driver's licence</span></span> 
- <span data-ttu-id="8412a-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8412a-1225">drivers licence</span></span> 
- <span data-ttu-id="8412a-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="8412a-1226">DOB</span></span> 
- <span data-ttu-id="8412a-1227">誕生日</span><span class="sxs-lookup"><span data-stu-id="8412a-1227">Birthdate</span></span> 
- <span data-ttu-id="8412a-1228">Birthday</span><span class="sxs-lookup"><span data-stu-id="8412a-1228">Birthday</span></span> 
- <span data-ttu-id="8412a-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="8412a-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="8412a-1230">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1231">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1231">Format</span></span>

<span data-ttu-id="8412a-1232">7-8 桁の数字と区切り文字のチェックディジットまたは文字</span><span class="sxs-lookup"><span data-stu-id="8412a-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1233">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1233">Pattern</span></span>

<span data-ttu-id="8412a-1234">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="8412a-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="8412a-1235">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-1235">1-2 digits</span></span> 
- <span data-ttu-id="8412a-1236">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-1236">A period</span></span> 
- <span data-ttu-id="8412a-1237">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1237">Three digits</span></span> 
- <span data-ttu-id="8412a-1238">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-1238">A period</span></span> 
- <span data-ttu-id="8412a-1239">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1239">Three digits</span></span> 
- <span data-ttu-id="8412a-1240">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-1240">A dash</span></span> 
- <span data-ttu-id="8412a-1241">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="8412a-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1242">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1242">Checksum</span></span>

<span data-ttu-id="8412a-1243">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1244">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1244">Definition</span></span>

<span data-ttu-id="8412a-1245">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1246">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1247">Keyword_chile_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="8412a-1248">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1248">The checksum passes.</span></span>

<span data-ttu-id="8412a-1249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1250">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1251">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1252">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="8412a-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="8412a-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="8412a-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="8412a-1254">National Identification Number</span></span> 
- <span data-ttu-id="8412a-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="8412a-1255">Identity card</span></span> 
- <span data-ttu-id="8412a-1256">ID</span><span class="sxs-lookup"><span data-stu-id="8412a-1256">ID</span></span> 
- <span data-ttu-id="8412a-1257">Fim</span><span class="sxs-lookup"><span data-stu-id="8412a-1257">Identification</span></span> 
- <span data-ttu-id="8412a-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="8412a-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="8412a-1259">実行</span><span class="sxs-lookup"><span data-stu-id="8412a-1259">RUN</span></span> 
- <span data-ttu-id="8412a-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="8412a-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="8412a-1261">類型</span><span class="sxs-lookup"><span data-stu-id="8412a-1261">RUT</span></span> 
- <span data-ttu-id="8412a-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="8412a-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="8412a-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="8412a-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="8412a-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="8412a-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="8412a-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="8412a-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="8412a-1266">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1267">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1267">Format</span></span>

<span data-ttu-id="8412a-1268">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1269">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1269">Pattern</span></span>

<span data-ttu-id="8412a-1270">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-1270">18 digits:</span></span>
- <span data-ttu-id="8412a-1271">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="8412a-1272">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8412a-1273">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="8412a-1274">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1275">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1275">Checksum</span></span>

<span data-ttu-id="8412a-1276">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1277">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1277">Definition</span></span>

<span data-ttu-id="8412a-1278">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1279">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1280">Keyword_china_resident_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="8412a-1281">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1281">The checksum passes.</span></span>

<span data-ttu-id="8412a-1282">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1283">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1284">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1285">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="8412a-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="8412a-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="8412a-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="8412a-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="8412a-1288">PRC</span><span class="sxs-lookup"><span data-stu-id="8412a-1288">PRC</span></span> 
- <span data-ttu-id="8412a-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="8412a-1289">National Identification Card</span></span> 
- <span data-ttu-id="8412a-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="8412a-1290">身份证</span></span> 
- <span data-ttu-id="8412a-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="8412a-1291">居民 身份证</span></span> 
- <span data-ttu-id="8412a-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="8412a-1292">居民身份证</span></span> 
- <span data-ttu-id="8412a-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="8412a-1293">鉴定</span></span> 
- <span data-ttu-id="8412a-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-1294">身分證</span></span> 
- <span data-ttu-id="8412a-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-1295">居民 身份證</span></span>
- <span data-ttu-id="8412a-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="8412a-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="8412a-1297">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1298">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1298">Format</span></span>

<span data-ttu-id="8412a-1299">書式設定または書式設定なし (dddddddddddddddd) で、Luhn テストに合格する必要がある14から16桁の数字。</span><span class="sxs-lookup"><span data-stu-id="8412a-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1300">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1300">Pattern</span></span>

<span data-ttu-id="8412a-1301">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="8412a-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1302">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1302">Checksum</span></span>

<span data-ttu-id="8412a-1303">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="8412a-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1304">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1304">Definition</span></span>

<span data-ttu-id="8412a-1305">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1306">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1307">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-1307">One of the following is true:</span></span>
    - <span data-ttu-id="8412a-1308">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="8412a-1309">Keyword_cc_name からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="8412a-1310">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8412a-1311">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1311">The checksum passes.</span></span>

<span data-ttu-id="8412a-1312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1313">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1314">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1315">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="8412a-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="8412a-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="8412a-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="8412a-1317">card verification</span></span>
- <span data-ttu-id="8412a-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="8412a-1318">card identification number</span></span>
- <span data-ttu-id="8412a-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="8412a-1319">cvn</span></span>
- <span data-ttu-id="8412a-1320">cid</span><span class="sxs-lookup"><span data-stu-id="8412a-1320">cid</span></span>
- <span data-ttu-id="8412a-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="8412a-1321">cvc2</span></span>
- <span data-ttu-id="8412a-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="8412a-1322">cvv2</span></span>
- <span data-ttu-id="8412a-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="8412a-1323">pin block</span></span>
- <span data-ttu-id="8412a-1324">security code</span><span class="sxs-lookup"><span data-stu-id="8412a-1324">security code</span></span>
- <span data-ttu-id="8412a-1325">security number</span><span class="sxs-lookup"><span data-stu-id="8412a-1325">security number</span></span>
- <span data-ttu-id="8412a-1326">security no</span><span class="sxs-lookup"><span data-stu-id="8412a-1326">security no</span></span>
- <span data-ttu-id="8412a-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="8412a-1327">issue number</span></span>
- <span data-ttu-id="8412a-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="8412a-1328">issue no</span></span>
- <span data-ttu-id="8412a-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="8412a-1329">cryptogramme</span></span>
- <span data-ttu-id="8412a-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="8412a-1330">numéro de sécurité</span></span>
- <span data-ttu-id="8412a-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="8412a-1331">numero de securite</span></span>
- <span data-ttu-id="8412a-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="8412a-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="8412a-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="8412a-1334">prüfziffer</span></span>
- <span data-ttu-id="8412a-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="8412a-1335">prufziffer</span></span>
- <span data-ttu-id="8412a-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="8412a-1336">sicherheits Kode</span></span>
- <span data-ttu-id="8412a-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="8412a-1337">sicherheitscode</span></span>
- <span data-ttu-id="8412a-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="8412a-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="8412a-1339">verfalldatum</span></span>
- <span data-ttu-id="8412a-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="8412a-1340">codice di verifica</span></span>
- <span data-ttu-id="8412a-1341">cod.</span><span class="sxs-lookup"><span data-stu-id="8412a-1341">cod.</span></span> <span data-ttu-id="8412a-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="8412a-1342">sicurezza</span></span>
- <span data-ttu-id="8412a-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="8412a-1343">cod sicurezza</span></span>
- <span data-ttu-id="8412a-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8412a-1344">n autorizzazione</span></span>
- <span data-ttu-id="8412a-1345">código</span><span class="sxs-lookup"><span data-stu-id="8412a-1345">código</span></span>
- <span data-ttu-id="8412a-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="8412a-1346">codigo</span></span>
- <span data-ttu-id="8412a-1347">cod.</span><span class="sxs-lookup"><span data-stu-id="8412a-1347">cod.</span></span> <span data-ttu-id="8412a-1348">seg</span><span class="sxs-lookup"><span data-stu-id="8412a-1348">seg</span></span>
- <span data-ttu-id="8412a-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="8412a-1349">cod seg</span></span>
- <span data-ttu-id="8412a-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1350">código de segurança</span></span>
- <span data-ttu-id="8412a-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1351">codigo de seguranca</span></span>
- <span data-ttu-id="8412a-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1352">codigo de segurança</span></span>
- <span data-ttu-id="8412a-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1353">código de seguranca</span></span>
- <span data-ttu-id="8412a-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="8412a-1354">cód.</span></span> <span data-ttu-id="8412a-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1355">segurança</span></span>
- <span data-ttu-id="8412a-1356">cod.</span><span class="sxs-lookup"><span data-stu-id="8412a-1356">cod.</span></span> <span data-ttu-id="8412a-1357">seguranca cod。</span><span class="sxs-lookup"><span data-stu-id="8412a-1357">seguranca cod.</span></span> <span data-ttu-id="8412a-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1358">segurança</span></span>
- <span data-ttu-id="8412a-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="8412a-1359">cód.</span></span> <span data-ttu-id="8412a-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1360">seguranca</span></span>
- <span data-ttu-id="8412a-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1361">cód segurança</span></span>
- <span data-ttu-id="8412a-1362">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="8412a-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1363">cód seguranca</span></span>
- <span data-ttu-id="8412a-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="8412a-1364">número de verificação</span></span>
- <span data-ttu-id="8412a-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="8412a-1365">numero de verificacao</span></span>
- <span data-ttu-id="8412a-1366">ablん f</span><span class="sxs-lookup"><span data-stu-id="8412a-1366">ablauf</span></span>
- <span data-ttu-id="8412a-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="8412a-1367">gültig bis</span></span>
- <span data-ttu-id="8412a-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8412a-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="8412a-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="8412a-1369">gultig bis</span></span>
- <span data-ttu-id="8412a-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8412a-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="8412a-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="8412a-1371">scadenza</span></span>
- <span data-ttu-id="8412a-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="8412a-1372">data scad</span></span>
- <span data-ttu-id="8412a-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="8412a-1373">fecha de expiracion</span></span>
- <span data-ttu-id="8412a-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="8412a-1374">fecha de venc</span></span>
- <span data-ttu-id="8412a-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="8412a-1375">vencimiento</span></span>
- <span data-ttu-id="8412a-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="8412a-1376">válido hasta</span></span>
- <span data-ttu-id="8412a-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="8412a-1377">valido hasta</span></span>
- <span data-ttu-id="8412a-1378">vto</span><span class="sxs-lookup"><span data-stu-id="8412a-1378">vto</span></span>
- <span data-ttu-id="8412a-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="8412a-1379">data de expiração</span></span>
- <span data-ttu-id="8412a-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="8412a-1380">data de expiracao</span></span>
- <span data-ttu-id="8412a-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="8412a-1381">data em que expira</span></span>
- <span data-ttu-id="8412a-1382">validade</span><span class="sxs-lookup"><span data-stu-id="8412a-1382">validade</span></span>
- <span data-ttu-id="8412a-1383">valor は</span><span class="sxs-lookup"><span data-stu-id="8412a-1383">valor</span></span>
- <span data-ttu-id="8412a-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="8412a-1384">vencimento</span></span>
- <span data-ttu-id="8412a-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="8412a-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="8412a-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="8412a-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="8412a-1387">amex</span><span class="sxs-lookup"><span data-stu-id="8412a-1387">amex</span></span>
- <span data-ttu-id="8412a-1388">american express</span><span class="sxs-lookup"><span data-stu-id="8412a-1388">american express</span></span>
- <span data-ttu-id="8412a-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="8412a-1389">americanexpress</span></span>
- <span data-ttu-id="8412a-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="8412a-1390">Visa</span></span>
- <span data-ttu-id="8412a-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="8412a-1391">mastercard</span></span>
- <span data-ttu-id="8412a-1392">master card</span><span class="sxs-lookup"><span data-stu-id="8412a-1392">master card</span></span>
- <span data-ttu-id="8412a-1393">mc</span><span class="sxs-lookup"><span data-stu-id="8412a-1393">mc</span></span> 
- <span data-ttu-id="8412a-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="8412a-1394">mastercards</span></span>
- <span data-ttu-id="8412a-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1395">master cards</span></span>
- <span data-ttu-id="8412a-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="8412a-1396">diner's Club</span></span>
- <span data-ttu-id="8412a-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="8412a-1397">diners club</span></span>
- <span data-ttu-id="8412a-1398">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="8412a-1398">dinersclub</span></span>
- <span data-ttu-id="8412a-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="8412a-1399">discover card</span></span>
- <span data-ttu-id="8412a-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="8412a-1400">discovercard</span></span>
- <span data-ttu-id="8412a-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1401">discover cards</span></span>
- <span data-ttu-id="8412a-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="8412a-1402">JCB</span></span>
- <span data-ttu-id="8412a-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="8412a-1403">japanese card bureau</span></span>
- <span data-ttu-id="8412a-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="8412a-1404">carte blanche</span></span>
- <span data-ttu-id="8412a-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="8412a-1405">carteblanche</span></span>
- <span data-ttu-id="8412a-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="8412a-1406">credit card</span></span>
- <span data-ttu-id="8412a-1407">]#</span><span class="sxs-lookup"><span data-stu-id="8412a-1407">cc#</span></span>
- <span data-ttu-id="8412a-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="8412a-1408">cc#:</span></span>
- <span data-ttu-id="8412a-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="8412a-1409">expiration date</span></span>
- <span data-ttu-id="8412a-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="8412a-1410">exp date</span></span>
- <span data-ttu-id="8412a-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="8412a-1411">expiry date</span></span>
- <span data-ttu-id="8412a-1412">日付 d'expiration</span><span class="sxs-lookup"><span data-stu-id="8412a-1412">date d'expiration</span></span>
- <span data-ttu-id="8412a-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="8412a-1413">date d'exp</span></span>
- <span data-ttu-id="8412a-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="8412a-1414">date expiration</span></span>
- <span data-ttu-id="8412a-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="8412a-1415">bank card</span></span>
- <span data-ttu-id="8412a-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1416">bankcard</span></span>
- <span data-ttu-id="8412a-1417">card number</span><span class="sxs-lookup"><span data-stu-id="8412a-1417">card number</span></span>
- <span data-ttu-id="8412a-1418">card num</span><span class="sxs-lookup"><span data-stu-id="8412a-1418">card num</span></span>
- <span data-ttu-id="8412a-1419">カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1419">cardnumber</span></span>
- <span data-ttu-id="8412a-1420">カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1420">cardnumbers</span></span>
- <span data-ttu-id="8412a-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-1421">card numbers</span></span>
- <span data-ttu-id="8412a-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1422">creditcard</span></span>
- <span data-ttu-id="8412a-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1423">credit cards</span></span>
- <span data-ttu-id="8412a-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1424">creditcards</span></span>
- <span data-ttu-id="8412a-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="8412a-1425">ccn</span></span>
- <span data-ttu-id="8412a-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="8412a-1426">card holder</span></span>
- <span data-ttu-id="8412a-1427">所有者</span><span class="sxs-lookup"><span data-stu-id="8412a-1427">cardholder</span></span>
- <span data-ttu-id="8412a-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="8412a-1428">card holders</span></span>
- <span data-ttu-id="8412a-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="8412a-1429">cardholders</span></span>
- <span data-ttu-id="8412a-1430">check card</span><span class="sxs-lookup"><span data-stu-id="8412a-1430">check card</span></span>
- <span data-ttu-id="8412a-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1431">checkcard</span></span>
- <span data-ttu-id="8412a-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1432">check cards</span></span>
- <span data-ttu-id="8412a-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1433">checkcards</span></span>
- <span data-ttu-id="8412a-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="8412a-1434">debit card</span></span>
- <span data-ttu-id="8412a-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1435">debitcard</span></span>
- <span data-ttu-id="8412a-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1436">debit cards</span></span>
- <span data-ttu-id="8412a-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1437">debitcards</span></span>
- <span data-ttu-id="8412a-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="8412a-1438">atm card</span></span>
- <span data-ttu-id="8412a-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1439">atmcard</span></span>
- <span data-ttu-id="8412a-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1440">atm cards</span></span>
- <span data-ttu-id="8412a-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1441">atmcards</span></span>
- <span data-ttu-id="8412a-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="8412a-1442">enroute</span></span>
- <span data-ttu-id="8412a-1443">en route</span><span class="sxs-lookup"><span data-stu-id="8412a-1443">en route</span></span>
- <span data-ttu-id="8412a-1444">card type</span><span class="sxs-lookup"><span data-stu-id="8412a-1444">card type</span></span>
- <span data-ttu-id="8412a-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="8412a-1445">carte bancaire</span></span>
- <span data-ttu-id="8412a-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="8412a-1446">carte de crédit</span></span>
- <span data-ttu-id="8412a-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="8412a-1447">carte de credit</span></span>
- <span data-ttu-id="8412a-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1448">numéro de carte</span></span>
- <span data-ttu-id="8412a-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1449">numero de carte</span></span>
- <span data-ttu-id="8412a-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1450">nº de la carte</span></span>
- <span data-ttu-id="8412a-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1451">nº de carte</span></span>
- <span data-ttu-id="8412a-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="8412a-1452">kreditkarte</span></span>
- <span data-ttu-id="8412a-1453">karte</span><span class="sxs-lookup"><span data-stu-id="8412a-1453">karte</span></span>
- <span data-ttu-id="8412a-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="8412a-1454">karteninhaber</span></span>
- <span data-ttu-id="8412a-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="8412a-1455">karteninhabers</span></span>
- <span data-ttu-id="8412a-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="8412a-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="8412a-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="8412a-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="8412a-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="8412a-1458">kreditkartentyp</span></span>
- <span data-ttu-id="8412a-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="8412a-1459">eigentümername</span></span>
- <span data-ttu-id="8412a-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="8412a-1460">kartennr</span></span> 
- <span data-ttu-id="8412a-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1461">kartennummer</span></span>
- <span data-ttu-id="8412a-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1462">kreditkartennummer</span></span>
- <span data-ttu-id="8412a-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="8412a-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1464">carta di credito</span></span>
- <span data-ttu-id="8412a-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1465">carta credito</span></span>
- <span data-ttu-id="8412a-1466">carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1466">carta</span></span>
- <span data-ttu-id="8412a-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1467">n carta</span></span>
- <span data-ttu-id="8412a-1468">nr.</span><span class="sxs-lookup"><span data-stu-id="8412a-1468">nr.</span></span> <span data-ttu-id="8412a-1469">carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1469">carta</span></span>
- <span data-ttu-id="8412a-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1470">nr carta</span></span>
- <span data-ttu-id="8412a-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1471">numero carta</span></span>
- <span data-ttu-id="8412a-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1472">numero della carta</span></span>
- <span data-ttu-id="8412a-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1473">numero di carta</span></span>
- <span data-ttu-id="8412a-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1474">tarjeta credito</span></span>
- <span data-ttu-id="8412a-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1475">tarjeta de credito</span></span>
- <span data-ttu-id="8412a-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="8412a-1476">tarjeta crédito</span></span>
- <span data-ttu-id="8412a-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="8412a-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="8412a-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="8412a-1478">tarjeta de atm</span></span>
- <span data-ttu-id="8412a-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="8412a-1479">tarjeta atm</span></span>
- <span data-ttu-id="8412a-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1480">tarjeta debito</span></span>
- <span data-ttu-id="8412a-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1481">tarjeta de debito</span></span>
- <span data-ttu-id="8412a-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="8412a-1482">tarjeta débito</span></span>
- <span data-ttu-id="8412a-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="8412a-1483">tarjeta de débito</span></span>
- <span data-ttu-id="8412a-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1484">nº de tarjeta</span></span>
- <span data-ttu-id="8412a-1485">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1485">no.</span></span> <span data-ttu-id="8412a-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1486">de tarjeta</span></span>
- <span data-ttu-id="8412a-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1487">no de tarjeta</span></span>
- <span data-ttu-id="8412a-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1488">numero de tarjeta</span></span>
- <span data-ttu-id="8412a-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1489">número de tarjeta</span></span>
- <span data-ttu-id="8412a-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="8412a-1490">tarjeta no</span></span>
- <span data-ttu-id="8412a-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="8412a-1491">tarjetahabiente</span></span>
- <span data-ttu-id="8412a-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="8412a-1492">cartão de crédito</span></span>
- <span data-ttu-id="8412a-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1493">cartão de credito</span></span>
- <span data-ttu-id="8412a-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="8412a-1494">cartao de crédito</span></span>
- <span data-ttu-id="8412a-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1495">cartao de credito</span></span>
- <span data-ttu-id="8412a-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="8412a-1496">cartão de débito</span></span>
- <span data-ttu-id="8412a-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="8412a-1497">cartao de débito</span></span>
- <span data-ttu-id="8412a-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1498">cartão de debito</span></span>
- <span data-ttu-id="8412a-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1499">cartao de debito</span></span>
- <span data-ttu-id="8412a-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="8412a-1500">débito automático</span></span>
- <span data-ttu-id="8412a-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="8412a-1501">debito automatico</span></span>
- <span data-ttu-id="8412a-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1502">número do cartão</span></span>
- <span data-ttu-id="8412a-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1503">numero do cartão</span></span> 
- <span data-ttu-id="8412a-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1504">número do cartao</span></span>
- <span data-ttu-id="8412a-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1505">numero do cartao</span></span>
- <span data-ttu-id="8412a-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1506">número de cartão</span></span>
- <span data-ttu-id="8412a-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1507">numero de cartão</span></span>
- <span data-ttu-id="8412a-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1508">número de cartao</span></span>
- <span data-ttu-id="8412a-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1509">numero de cartao</span></span>
- <span data-ttu-id="8412a-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1510">nº do cartão</span></span>
- <span data-ttu-id="8412a-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1511">nº do cartao</span></span>
- <span data-ttu-id="8412a-1512">n °</span><span class="sxs-lookup"><span data-stu-id="8412a-1512">nº.</span></span> <span data-ttu-id="8412a-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1513">do cartão</span></span>
- <span data-ttu-id="8412a-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1514">no do cartão</span></span>
- <span data-ttu-id="8412a-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1515">no do cartao</span></span>
- <span data-ttu-id="8412a-1516">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1516">no.</span></span> <span data-ttu-id="8412a-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1517">do cartão</span></span>
- <span data-ttu-id="8412a-1518">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1518">no.</span></span> <span data-ttu-id="8412a-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="8412a-1520">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1521">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1521">Format</span></span>

<span data-ttu-id="8412a-1522">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1523">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1523">Pattern</span></span>

<span data-ttu-id="8412a-1524">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1525">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1525">Checksum</span></span>

<span data-ttu-id="8412a-1526">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1527">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1527">Definition</span></span>

<span data-ttu-id="8412a-1528">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1529">関数 Func_croatia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1530">Keyword_croatia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-1531">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="8412a-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="8412a-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="8412a-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="8412a-1533">Croatian identity card</span></span>
- <span data-ttu-id="8412a-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="8412a-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="8412a-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="8412a-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1536">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1536">Format</span></span>

<span data-ttu-id="8412a-1537">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1538">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1538">Pattern</span></span>

<span data-ttu-id="8412a-1539">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-1539">11 digits:</span></span>
- <span data-ttu-id="8412a-1540">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1540">10 digits</span></span> 
- <span data-ttu-id="8412a-1541">最終桁は、国際的なデータ交換のためのチェックディジットです。 HR は11桁の数字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8412a-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1542">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1542">Checksum</span></span>

<span data-ttu-id="8412a-1543">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1544">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1544">Definition</span></span>

<span data-ttu-id="8412a-1545">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1546">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1547">Keyword_croatia_oib_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="8412a-1548">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1548">The checksum passes.</span></span>

<span data-ttu-id="8412a-1549">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1550">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1551">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1552">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="8412a-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="8412a-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="8412a-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="8412a-1554">Personal Identification Number</span></span>
- <span data-ttu-id="8412a-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="8412a-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="8412a-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="8412a-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="8412a-1557">チェコの個人 Id 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1558">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1558">Format</span></span>

<span data-ttu-id="8412a-1559">省略可能なスラッシュ (古い形式) を含む9桁の数字 (省略可能)。スラッシュ (新しい形式)</span><span class="sxs-lookup"><span data-stu-id="8412a-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1560">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1560">Pattern</span></span>

<span data-ttu-id="8412a-1561">9桁の数字 (古い形式):</span><span class="sxs-lookup"><span data-stu-id="8412a-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="8412a-1562">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1562">Nine digits</span></span>

<span data-ttu-id="8412a-1563">OR</span><span class="sxs-lookup"><span data-stu-id="8412a-1563">OR</span></span>

- <span data-ttu-id="8412a-1564">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="8412a-1565">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-1565">A forward slash</span></span>
- <span data-ttu-id="8412a-1566">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1566">Three digits</span></span>

<span data-ttu-id="8412a-1567">10桁の数字 (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="8412a-1567">10 digits (new format):</span></span>
- <span data-ttu-id="8412a-1568">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1568">10 digits</span></span>

<span data-ttu-id="8412a-1569">OR</span><span class="sxs-lookup"><span data-stu-id="8412a-1569">OR</span></span>

- <span data-ttu-id="8412a-1570">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="8412a-1571">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-1571">A forward slash</span></span> 
- <span data-ttu-id="8412a-1572">4桁の数字 (最後の桁はチェックディジット)</span><span class="sxs-lookup"><span data-stu-id="8412a-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1573">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1573">Checksum</span></span>

<span data-ttu-id="8412a-1574">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1575">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1575">Definition</span></span>

<span data-ttu-id="8412a-1576">DLP ポリシーは85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_czech_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="8412a-1577">Keyword_czech_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="8412a-1578">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="8412a-1579">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1579">Keywords</span></span>

- <span data-ttu-id="8412a-1580">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1580">czech personal identity number</span></span>
- <span data-ttu-id="8412a-1581">Rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="8412a-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="8412a-1582">	Denmark Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="8412a-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1583">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1583">Format</span></span>

<span data-ttu-id="8412a-1584">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1585">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1585">Pattern</span></span>

<span data-ttu-id="8412a-1586">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-1586">10 digits:</span></span>
- <span data-ttu-id="8412a-1587">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="8412a-1588">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-1588">A hyphen</span></span> 
- <span data-ttu-id="8412a-1589">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="8412a-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1590">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1590">Checksum</span></span>

<span data-ttu-id="8412a-1591">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1592">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1592">Definition</span></span>

<span data-ttu-id="8412a-1593">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_denmark_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="8412a-1594">Keyword_denmark_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="8412a-1595">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-1596">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="8412a-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="8412a-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="8412a-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="8412a-1598">Personal Identification Number</span></span>
- <span data-ttu-id="8412a-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="8412a-1599">CPR</span></span>
- <span data-ttu-id="8412a-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="8412a-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="8412a-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="8412a-1602">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1603">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1603">Format</span></span>

<span data-ttu-id="8412a-1604">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1605">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1605">Pattern</span></span>

<span data-ttu-id="8412a-1606">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8412a-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="8412a-1607">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="8412a-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="8412a-1608">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="8412a-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="8412a-1609">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="8412a-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1610">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1610">Checksum</span></span>

<span data-ttu-id="8412a-1611">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1612">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1612">Definition</span></span>

<span data-ttu-id="8412a-1613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1614">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1615">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-1616">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1616">Keywords</span></span>

<span data-ttu-id="8412a-1617">なし</span><span class="sxs-lookup"><span data-stu-id="8412a-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="8412a-1618">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1619">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1619">Format</span></span>

<span data-ttu-id="8412a-1620">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1621">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1621">Pattern</span></span>

<span data-ttu-id="8412a-1622">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1623">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1623">Checksum</span></span>

<span data-ttu-id="8412a-1624">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1625">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1625">Definition</span></span>

<span data-ttu-id="8412a-1626">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1627">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1628">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="8412a-1629">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="8412a-1630">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="8412a-1631">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="8412a-1632">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="8412a-1633">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8412a-1634">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-1635">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="8412a-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="8412a-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="8412a-1637">account number</span><span class="sxs-lookup"><span data-stu-id="8412a-1637">account number</span></span> 
- <span data-ttu-id="8412a-1638">card number</span><span class="sxs-lookup"><span data-stu-id="8412a-1638">card number</span></span> 
- <span data-ttu-id="8412a-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="8412a-1639">card no.</span></span> 
- <span data-ttu-id="8412a-1640">security number</span><span class="sxs-lookup"><span data-stu-id="8412a-1640">security number</span></span> 
- <span data-ttu-id="8412a-1641">]#</span><span class="sxs-lookup"><span data-stu-id="8412a-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="8412a-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="8412a-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="8412a-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="8412a-1643">acct nbr</span></span> 
- <span data-ttu-id="8412a-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="8412a-1644">acct num</span></span> 
- <span data-ttu-id="8412a-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="8412a-1645">acct no</span></span> 
- <span data-ttu-id="8412a-1646">american express</span><span class="sxs-lookup"><span data-stu-id="8412a-1646">american express</span></span> 
- <span data-ttu-id="8412a-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="8412a-1647">americanexpress</span></span> 
- <span data-ttu-id="8412a-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="8412a-1648">americano espresso</span></span> 
- <span data-ttu-id="8412a-1649">amex</span><span class="sxs-lookup"><span data-stu-id="8412a-1649">amex</span></span> 
- <span data-ttu-id="8412a-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="8412a-1650">atm card</span></span> 
- <span data-ttu-id="8412a-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1651">atm cards</span></span> 
- <span data-ttu-id="8412a-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="8412a-1652">atm kaart</span></span> 
- <span data-ttu-id="8412a-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1653">atmcard</span></span> 
- <span data-ttu-id="8412a-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1654">atmcards</span></span> 
- <span data-ttu-id="8412a-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="8412a-1655">atmkaart</span></span> 
- <span data-ttu-id="8412a-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="8412a-1656">atmkaarten</span></span> 
- <span data-ttu-id="8412a-1657"># # の連絡先</span><span class="sxs-lookup"><span data-stu-id="8412a-1657">bancontact</span></span> 
- <span data-ttu-id="8412a-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="8412a-1658">bank card</span></span> 
- <span data-ttu-id="8412a-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="8412a-1659">bankkaart</span></span> 
- <span data-ttu-id="8412a-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="8412a-1660">card holder</span></span> 
- <span data-ttu-id="8412a-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="8412a-1661">card holders</span></span> 
- <span data-ttu-id="8412a-1662">card num</span><span class="sxs-lookup"><span data-stu-id="8412a-1662">card num</span></span> 
- <span data-ttu-id="8412a-1663">card number</span><span class="sxs-lookup"><span data-stu-id="8412a-1663">card number</span></span> 
- <span data-ttu-id="8412a-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-1664">card numbers</span></span> 
- <span data-ttu-id="8412a-1665">card type</span><span class="sxs-lookup"><span data-stu-id="8412a-1665">card type</span></span> 
- <span data-ttu-id="8412a-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="8412a-1666">cardano numerico</span></span> 
- <span data-ttu-id="8412a-1667">所有者</span><span class="sxs-lookup"><span data-stu-id="8412a-1667">cardholder</span></span> 
- <span data-ttu-id="8412a-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="8412a-1668">cardholders</span></span> 
- <span data-ttu-id="8412a-1669">カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1669">cardnumber</span></span> 
- <span data-ttu-id="8412a-1670">カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1670">cardnumbers</span></span> 
- <span data-ttu-id="8412a-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="8412a-1671">carta bianca</span></span> 
- <span data-ttu-id="8412a-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1672">carta credito</span></span> 
- <span data-ttu-id="8412a-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1673">carta di credito</span></span> 
- <span data-ttu-id="8412a-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1674">cartao de credito</span></span> 
- <span data-ttu-id="8412a-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="8412a-1675">cartao de crédito</span></span> 
- <span data-ttu-id="8412a-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1676">cartao de debito</span></span> 
- <span data-ttu-id="8412a-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="8412a-1677">cartao de débito</span></span> 
- <span data-ttu-id="8412a-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="8412a-1678">carte bancaire</span></span> 
- <span data-ttu-id="8412a-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="8412a-1679">carte blanche</span></span> 
- <span data-ttu-id="8412a-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="8412a-1680">carte bleue</span></span> 
- <span data-ttu-id="8412a-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="8412a-1681">carte de credit</span></span> 
- <span data-ttu-id="8412a-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="8412a-1682">carte de crédit</span></span> 
- <span data-ttu-id="8412a-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1683">carte di credito</span></span> 
- <span data-ttu-id="8412a-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="8412a-1684">carteblanche</span></span> 
- <span data-ttu-id="8412a-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1685">cartão de credito</span></span> 
- <span data-ttu-id="8412a-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="8412a-1686">cartão de crédito</span></span> 
- <span data-ttu-id="8412a-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1687">cartão de debito</span></span> 
- <span data-ttu-id="8412a-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="8412a-1688">cartão de débito</span></span> 
- <span data-ttu-id="8412a-1689">cb</span><span class="sxs-lookup"><span data-stu-id="8412a-1689">cb</span></span> 
- <span data-ttu-id="8412a-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="8412a-1690">ccn</span></span> 
- <span data-ttu-id="8412a-1691">check card</span><span class="sxs-lookup"><span data-stu-id="8412a-1691">check card</span></span> 
- <span data-ttu-id="8412a-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1692">check cards</span></span> 
- <span data-ttu-id="8412a-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1693">checkcard</span></span>
- <span data-ttu-id="8412a-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1694">checkcards</span></span> 
- <span data-ttu-id="8412a-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="8412a-1695">chequekaart</span></span> 
- <span data-ttu-id="8412a-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="8412a-1696">cirrus</span></span> 
- <span data-ttu-id="8412a-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="8412a-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="8412a-1698">lekaart の方法</span><span class="sxs-lookup"><span data-stu-id="8412a-1698">controlekaart</span></span> 
- <span data-ttu-id="8412a-1699">lekaar10 の場合</span><span class="sxs-lookup"><span data-stu-id="8412a-1699">controlekaarten</span></span> 
- <span data-ttu-id="8412a-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="8412a-1700">credit card</span></span> 
- <span data-ttu-id="8412a-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1701">credit cards</span></span> 
- <span data-ttu-id="8412a-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1702">creditcard</span></span> 
- <span data-ttu-id="8412a-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1703">creditcards</span></span> 
- <span data-ttu-id="8412a-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="8412a-1704">debetkaart</span></span> 
- <span data-ttu-id="8412a-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="8412a-1705">debetkaarten</span></span> 
- <span data-ttu-id="8412a-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="8412a-1706">debit card</span></span> 
- <span data-ttu-id="8412a-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1707">debit cards</span></span> 
- <span data-ttu-id="8412a-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="8412a-1708">debitcard</span></span> 
- <span data-ttu-id="8412a-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="8412a-1709">debitcards</span></span> 
- <span data-ttu-id="8412a-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="8412a-1710">debito automatico</span></span> 
- <span data-ttu-id="8412a-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="8412a-1711">diners club</span></span> 
- <span data-ttu-id="8412a-1712">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="8412a-1712">dinersclub</span></span> 
- <span data-ttu-id="8412a-1713">開示</span><span class="sxs-lookup"><span data-stu-id="8412a-1713">discover</span></span> 
- <span data-ttu-id="8412a-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="8412a-1714">discover card</span></span> 
- <span data-ttu-id="8412a-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1715">discover cards</span></span> 
- <span data-ttu-id="8412a-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="8412a-1716">discovercard</span></span> 
- <span data-ttu-id="8412a-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="8412a-1717">discovercards</span></span> 
- <span data-ttu-id="8412a-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="8412a-1718">débito automático</span></span>
- <span data-ttu-id="8412a-1719">edc</span><span class="sxs-lookup"><span data-stu-id="8412a-1719">edc</span></span> 
- <span data-ttu-id="8412a-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="8412a-1720">eigentümername</span></span> 
- <span data-ttu-id="8412a-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="8412a-1721">european debit card</span></span> 
- <span data-ttu-id="8412a-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="8412a-1722">hoofdkaart</span></span> 
- <span data-ttu-id="8412a-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="8412a-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="8412a-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="8412a-1724">in viaggio</span></span> 
- <span data-ttu-id="8412a-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="8412a-1725">japanese card bureau</span></span> 
- <span data-ttu-id="8412a-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="8412a-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="8412a-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="8412a-1727">jcb</span></span> 
- <span data-ttu-id="8412a-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="8412a-1728">kaart</span></span> 
- <span data-ttu-id="8412a-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="8412a-1729">kaart num</span></span> 
- <span data-ttu-id="8412a-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="8412a-1730">kaartaantal</span></span> 
- <span data-ttu-id="8412a-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="8412a-1731">kaartaantallen</span></span> 
- <span data-ttu-id="8412a-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="8412a-1732">kaarthouder</span></span> 
- <span data-ttu-id="8412a-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="8412a-1733">kaarthouders</span></span> 
- <span data-ttu-id="8412a-1734">karte</span><span class="sxs-lookup"><span data-stu-id="8412a-1734">karte</span></span>  
- <span data-ttu-id="8412a-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="8412a-1735">karteninhaber</span></span> 
- <span data-ttu-id="8412a-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="8412a-1736">karteninhabers</span></span>
- <span data-ttu-id="8412a-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="8412a-1737">kartennr</span></span> 
- <span data-ttu-id="8412a-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1738">kartennummer</span></span> 
- <span data-ttu-id="8412a-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="8412a-1739">kreditkarte</span></span> 
- <span data-ttu-id="8412a-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="8412a-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="8412a-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="8412a-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="8412a-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="8412a-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="8412a-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="8412a-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="8412a-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="8412a-1745">maestro</span></span> 
- <span data-ttu-id="8412a-1746">master card</span><span class="sxs-lookup"><span data-stu-id="8412a-1746">master card</span></span> 
- <span data-ttu-id="8412a-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="8412a-1747">master cards</span></span> 
- <span data-ttu-id="8412a-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="8412a-1748">mastercard</span></span> 
- <span data-ttu-id="8412a-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="8412a-1749">mastercards</span></span> 
- <span data-ttu-id="8412a-1750">mc</span><span class="sxs-lookup"><span data-stu-id="8412a-1750">mc</span></span> 
- <span data-ttu-id="8412a-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="8412a-1751">mister cash</span></span> 
- <span data-ttu-id="8412a-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1752">n carta</span></span> 
- <span data-ttu-id="8412a-1753">carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1753">carta</span></span> 
- <span data-ttu-id="8412a-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1754">no de tarjeta</span></span> 
- <span data-ttu-id="8412a-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1755">no do cartao</span></span> 
- <span data-ttu-id="8412a-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1756">no do cartão</span></span> 
- <span data-ttu-id="8412a-1757">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1757">no.</span></span> <span data-ttu-id="8412a-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1758">de tarjeta</span></span> 
- <span data-ttu-id="8412a-1759">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1759">no.</span></span> <span data-ttu-id="8412a-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1760">do cartao</span></span> 
- <span data-ttu-id="8412a-1761">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1761">no.</span></span> <span data-ttu-id="8412a-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1762">do cartão</span></span> 
- <span data-ttu-id="8412a-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1763">nr carta</span></span> 
- <span data-ttu-id="8412a-1764">nr.</span><span class="sxs-lookup"><span data-stu-id="8412a-1764">nr.</span></span> <span data-ttu-id="8412a-1765">carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1765">carta</span></span> 
- <span data-ttu-id="8412a-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1766">numeri di scheda</span></span> 
- <span data-ttu-id="8412a-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1767">numero carta</span></span> 
- <span data-ttu-id="8412a-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1768">numero de cartao</span></span> 
- <span data-ttu-id="8412a-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1769">numero de carte</span></span> 
- <span data-ttu-id="8412a-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1770">numero de cartão</span></span> 
- <span data-ttu-id="8412a-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1771">numero de tarjeta</span></span>
- <span data-ttu-id="8412a-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1772">numero della carta</span></span> 
- <span data-ttu-id="8412a-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1773">numero di carta</span></span> 
- <span data-ttu-id="8412a-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1774">numero di scheda</span></span> 
- <span data-ttu-id="8412a-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1775">numero do cartao</span></span> 
- <span data-ttu-id="8412a-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1776">numero do cartão</span></span> 
- <span data-ttu-id="8412a-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1777">numéro de carte</span></span> 
- <span data-ttu-id="8412a-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="8412a-1778">nº carta</span></span> 
- <span data-ttu-id="8412a-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1779">nº de carte</span></span> 
- <span data-ttu-id="8412a-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="8412a-1780">nº de la carte</span></span> 
- <span data-ttu-id="8412a-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="8412a-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1782">nº do cartao</span></span> 
- <span data-ttu-id="8412a-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1783">nº do cartão</span></span> 
- <span data-ttu-id="8412a-1784">n °</span><span class="sxs-lookup"><span data-stu-id="8412a-1784">nº.</span></span> <span data-ttu-id="8412a-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1785">do cartão</span></span> 
- <span data-ttu-id="8412a-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1786">número de cartao</span></span> 
- <span data-ttu-id="8412a-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="8412a-1787">número de cartão</span></span> 
- <span data-ttu-id="8412a-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8412a-1788">número de tarjeta</span></span> 
- <span data-ttu-id="8412a-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="8412a-1789">número do cartao</span></span> 
- <span data-ttu-id="8412a-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="8412a-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="8412a-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="8412a-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="8412a-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="8412a-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="8412a-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="8412a-1793">scheda della banca</span></span> 
- <span data-ttu-id="8412a-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="8412a-1794">scheda di controllo</span></span> 
- <span data-ttu-id="8412a-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1795">scheda di debito</span></span> 
- <span data-ttu-id="8412a-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="8412a-1796">scheda matrice</span></span> 
- <span data-ttu-id="8412a-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="8412a-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="8412a-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="8412a-1798">schede di controllo</span></span> 
- <span data-ttu-id="8412a-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1799">schede di debito</span></span> 
- <span data-ttu-id="8412a-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="8412a-1800">schede matrici</span></span> 
- <span data-ttu-id="8412a-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="8412a-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="8412a-1802">scoprono le schede</span></span> 
- <span data-ttu-id="8412a-1803">単独</span><span class="sxs-lookup"><span data-stu-id="8412a-1803">solo</span></span> 
- <span data-ttu-id="8412a-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1804">supporti di scheda</span></span> 
- <span data-ttu-id="8412a-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1805">supporto di scheda</span></span> 
- <span data-ttu-id="8412a-1806">switch</span><span class="sxs-lookup"><span data-stu-id="8412a-1806">switch</span></span> 
- <span data-ttu-id="8412a-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="8412a-1807">tarjeta atm</span></span> 
- <span data-ttu-id="8412a-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1808">tarjeta credito</span></span> 
- <span data-ttu-id="8412a-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="8412a-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="8412a-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="8412a-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="8412a-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="8412a-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="8412a-1812">tarjeta debito</span></span> 
- <span data-ttu-id="8412a-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="8412a-1813">tarjeta no</span></span>
- <span data-ttu-id="8412a-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="8412a-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="8412a-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1815">tipo della scheda</span></span> 
- <span data-ttu-id="8412a-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="8412a-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="8412a-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1817">scheda</span></span> 
- <span data-ttu-id="8412a-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="8412a-1818">v pay</span></span> 
- <span data-ttu-id="8412a-1819">v-支払い</span><span class="sxs-lookup"><span data-stu-id="8412a-1819">v-pay</span></span> 
- <span data-ttu-id="8412a-1820">visa</span><span class="sxs-lookup"><span data-stu-id="8412a-1820">visa</span></span> 
- <span data-ttu-id="8412a-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="8412a-1821">visa plus</span></span> 
- <span data-ttu-id="8412a-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="8412a-1822">visa electron</span></span> 
- <span data-ttu-id="8412a-1823">visto</span><span class="sxs-lookup"><span data-stu-id="8412a-1823">visto</span></span> 
- <span data-ttu-id="8412a-1824">visum</span><span class="sxs-lookup"><span data-stu-id="8412a-1824">visum</span></span> 
- <span data-ttu-id="8412a-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="8412a-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="8412a-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="8412a-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="8412a-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="8412a-1827">card identification number</span></span>
- <span data-ttu-id="8412a-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="8412a-1828">card verification</span></span> 
- <span data-ttu-id="8412a-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="8412a-1829">cardi la verifica</span></span> 
- <span data-ttu-id="8412a-1830">cid</span><span class="sxs-lookup"><span data-stu-id="8412a-1830">cid</span></span> 
- <span data-ttu-id="8412a-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="8412a-1831">cod seg</span></span> 
- <span data-ttu-id="8412a-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1832">cod seguranca</span></span> 
- <span data-ttu-id="8412a-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1833">cod segurança</span></span> 
- <span data-ttu-id="8412a-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="8412a-1834">cod sicurezza</span></span> 
- <span data-ttu-id="8412a-1835">cod.</span><span class="sxs-lookup"><span data-stu-id="8412a-1835">cod.</span></span> <span data-ttu-id="8412a-1836">seg</span><span class="sxs-lookup"><span data-stu-id="8412a-1836">seg</span></span> 
- <span data-ttu-id="8412a-1837">cod.</span><span class="sxs-lookup"><span data-stu-id="8412a-1837">cod.</span></span> <span data-ttu-id="8412a-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1838">seguranca</span></span> 
- <span data-ttu-id="8412a-1839">cod.</span><span class="sxs-lookup"><span data-stu-id="8412a-1839">cod.</span></span> <span data-ttu-id="8412a-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1840">segurança</span></span> 
- <span data-ttu-id="8412a-1841">cod.</span><span class="sxs-lookup"><span data-stu-id="8412a-1841">cod.</span></span> <span data-ttu-id="8412a-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="8412a-1842">sicurezza</span></span> 
- <span data-ttu-id="8412a-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8412a-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="8412a-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="8412a-1844">codice di verifica</span></span> 
- <span data-ttu-id="8412a-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="8412a-1845">codigo</span></span> 
- <span data-ttu-id="8412a-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="8412a-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1847">codigo de segurança</span></span> 
- <span data-ttu-id="8412a-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="8412a-1848">crittogramma</span></span> 
- <span data-ttu-id="8412a-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="8412a-1849">cryptogram</span></span> 
- <span data-ttu-id="8412a-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="8412a-1850">cryptogramme</span></span> 
- <span data-ttu-id="8412a-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="8412a-1851">cv2</span></span> 
- <span data-ttu-id="8412a-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="8412a-1852">cvc</span></span> 
- <span data-ttu-id="8412a-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="8412a-1853">cvc2</span></span> 
- <span data-ttu-id="8412a-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="8412a-1854">cvn</span></span> 
- <span data-ttu-id="8412a-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="8412a-1855">cvv</span></span> 
- <span data-ttu-id="8412a-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="8412a-1856">cvv2</span></span> 
- <span data-ttu-id="8412a-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1857">cód seguranca</span></span> 
- <span data-ttu-id="8412a-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1858">cód segurança</span></span> 
- <span data-ttu-id="8412a-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="8412a-1859">cód.</span></span> <span data-ttu-id="8412a-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1860">seguranca</span></span> 
- <span data-ttu-id="8412a-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="8412a-1861">cód.</span></span> <span data-ttu-id="8412a-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1862">segurança</span></span> 
- <span data-ttu-id="8412a-1863">código</span><span class="sxs-lookup"><span data-stu-id="8412a-1863">código</span></span> 
- <span data-ttu-id="8412a-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="8412a-1864">código de seguranca</span></span> 
- <span data-ttu-id="8412a-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="8412a-1865">código de segurança</span></span> 
- <span data-ttu-id="8412a-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="8412a-1866">de kaart controle</span></span> 
- <span data-ttu-id="8412a-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="8412a-1867">geeft nr uit</span></span> 
- <span data-ttu-id="8412a-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="8412a-1868">issue no</span></span> 
- <span data-ttu-id="8412a-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="8412a-1869">issue number</span></span> 
- <span data-ttu-id="8412a-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="8412a-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="8412a-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="8412a-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="8412a-1873">kwestieaantal</span></span> 
- <span data-ttu-id="8412a-1874">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1874">no.</span></span> <span data-ttu-id="8412a-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="8412a-1875">dell'edizione</span></span> 
- <span data-ttu-id="8412a-1876">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-1876">no.</span></span> <span data-ttu-id="8412a-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8412a-1877">di sicurezza</span></span> 
- <span data-ttu-id="8412a-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="8412a-1878">numero de securite</span></span> 
- <span data-ttu-id="8412a-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="8412a-1879">numero de verificacao</span></span> 
- <span data-ttu-id="8412a-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="8412a-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="8412a-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="8412a-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="8412a-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="8412a-1882">scheda</span></span> 
- <span data-ttu-id="8412a-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8412a-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="8412a-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="8412a-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="8412a-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="8412a-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="8412a-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8412a-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="8412a-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="8412a-1887">número de verificação</span></span> 
- <span data-ttu-id="8412a-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="8412a-1888">perno il blocco</span></span> 
- <span data-ttu-id="8412a-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="8412a-1889">pin block</span></span> 
- <span data-ttu-id="8412a-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="8412a-1890">prufziffer</span></span> 
- <span data-ttu-id="8412a-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="8412a-1891">prüfziffer</span></span> 
- <span data-ttu-id="8412a-1892">security code</span><span class="sxs-lookup"><span data-stu-id="8412a-1892">security code</span></span> 
- <span data-ttu-id="8412a-1893">security no</span><span class="sxs-lookup"><span data-stu-id="8412a-1893">security no</span></span> 
- <span data-ttu-id="8412a-1894">security number</span><span class="sxs-lookup"><span data-stu-id="8412a-1894">security number</span></span> 
- <span data-ttu-id="8412a-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="8412a-1895">sicherheits kode</span></span> 
- <span data-ttu-id="8412a-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="8412a-1896">sicherheitscode</span></span> 
- <span data-ttu-id="8412a-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="8412a-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="8412a-1898">speldblok</span></span> 
- <span data-ttu-id="8412a-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="8412a-1899">veiligheid nr</span></span> 
- <span data-ttu-id="8412a-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="8412a-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="8412a-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="8412a-1901">veiligheidscode</span></span> 
- <span data-ttu-id="8412a-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="8412a-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="8412a-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="8412a-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="8412a-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="8412a-1905">ablん f</span><span class="sxs-lookup"><span data-stu-id="8412a-1905">ablauf</span></span> 
- <span data-ttu-id="8412a-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="8412a-1906">data de expiracao</span></span> 
- <span data-ttu-id="8412a-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="8412a-1907">data de expiração</span></span> 
- <span data-ttu-id="8412a-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="8412a-1908">data del exp</span></span> 
- <span data-ttu-id="8412a-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="8412a-1909">data di exp</span></span> 
- <span data-ttu-id="8412a-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="8412a-1910">data di scadenza</span></span> 
- <span data-ttu-id="8412a-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="8412a-1911">data em que expira</span></span> 
- <span data-ttu-id="8412a-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="8412a-1912">data scad</span></span> 
- <span data-ttu-id="8412a-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="8412a-1913">data scadenza</span></span> 
- <span data-ttu-id="8412a-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="8412a-1914">date de validité</span></span> 
- <span data-ttu-id="8412a-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="8412a-1915">datum afloop</span></span> 
- <span data-ttu-id="8412a-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="8412a-1916">datum van exp</span></span> 
- <span data-ttu-id="8412a-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="8412a-1917">de afloop</span></span> 
- <span data-ttu-id="8412a-1918">espira</span><span class="sxs-lookup"><span data-stu-id="8412a-1918">espira</span></span> 
- <span data-ttu-id="8412a-1919">espira</span><span class="sxs-lookup"><span data-stu-id="8412a-1919">espira</span></span> 
- <span data-ttu-id="8412a-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="8412a-1920">exp date</span></span> 
- <span data-ttu-id="8412a-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="8412a-1921">exp datum</span></span> 
- <span data-ttu-id="8412a-1922">nntp</span><span class="sxs-lookup"><span data-stu-id="8412a-1922">expiration</span></span> 
- <span data-ttu-id="8412a-1923">無効</span><span class="sxs-lookup"><span data-stu-id="8412a-1923">expire</span></span> 
- <span data-ttu-id="8412a-1924">期限</span><span class="sxs-lookup"><span data-stu-id="8412a-1924">expires</span></span> 
- <span data-ttu-id="8412a-1925">期限</span><span class="sxs-lookup"><span data-stu-id="8412a-1925">expiry</span></span> 
- <span data-ttu-id="8412a-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="8412a-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="8412a-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="8412a-1927">fecha de venc</span></span> 
- <span data-ttu-id="8412a-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="8412a-1928">gultig bis</span></span> 
- <span data-ttu-id="8412a-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8412a-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="8412a-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="8412a-1930">gültig bis</span></span> 
- <span data-ttu-id="8412a-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8412a-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="8412a-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="8412a-1932">la scadenza</span></span> 
- <span data-ttu-id="8412a-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="8412a-1933">scadenza</span></span> 
- <span data-ttu-id="8412a-1934">valable</span><span class="sxs-lookup"><span data-stu-id="8412a-1934">valable</span></span> 
- <span data-ttu-id="8412a-1935">validade</span><span class="sxs-lookup"><span data-stu-id="8412a-1935">validade</span></span> 
- <span data-ttu-id="8412a-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="8412a-1936">valido hasta</span></span> 
- <span data-ttu-id="8412a-1937">valor は</span><span class="sxs-lookup"><span data-stu-id="8412a-1937">valor</span></span> 
- <span data-ttu-id="8412a-1938">venc</span><span class="sxs-lookup"><span data-stu-id="8412a-1938">venc</span></span> 
- <span data-ttu-id="8412a-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="8412a-1939">vencimento</span></span> 
- <span data-ttu-id="8412a-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="8412a-1940">vencimiento</span></span> 
- <span data-ttu-id="8412a-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="8412a-1941">verloopt</span></span> 
- <span data-ttu-id="8412a-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="8412a-1942">vervaldag</span></span> 
- <span data-ttu-id="8412a-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="8412a-1943">vervaldatum</span></span> 
- <span data-ttu-id="8412a-1944">vto</span><span class="sxs-lookup"><span data-stu-id="8412a-1944">vto</span></span> 
- <span data-ttu-id="8412a-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="8412a-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="8412a-1946">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1946">EU Driver's License Number</span></span>

<span data-ttu-id="8412a-1947">詳細については、「 [EU ドライバーのライセンス番号の機密情報の種類](eu-driver-s-license-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8412a-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="8412a-1948">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1948">EU National Identification Number</span></span>

<span data-ttu-id="8412a-1949">詳細については、「 [EU 国立 Id 番号の機密情報の種類](eu-national-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8412a-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="8412a-1950">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1950">EU Passport Number</span></span>

<span data-ttu-id="8412a-1951">詳細については、「 [EU パスポート番号の機密情報の種類](eu-passport-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8412a-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="8412a-1952">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="8412a-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="8412a-1953">詳細については、「 [EU 社会保障番号または同等の ID の機密情報の種類](eu-social-security-number-or-equivalent-id.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8412a-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="8412a-1954">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="8412a-1955">詳細については、「 [EU 税務識別番号の機密情報の種類](eu-tax-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8412a-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="8412a-1956">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="8412a-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1957">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1957">Format</span></span>

<span data-ttu-id="8412a-1958">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="8412a-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1959">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1959">Pattern</span></span>

<span data-ttu-id="8412a-1960">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8412a-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="8412a-1961">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="8412a-1962">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="8412a-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="8412a-1963">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="8412a-1964">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="8412a-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1965">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1965">Checksum</span></span>

<span data-ttu-id="8412a-1966">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1967">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1967">Definition</span></span>

<span data-ttu-id="8412a-1968">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1969">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1970">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="8412a-1971">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-1972">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1972">Keywords</span></span>

- <span data-ttu-id="8412a-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="8412a-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="8412a-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="8412a-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="8412a-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="8412a-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="8412a-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="8412a-1976">Personbeteckning</span></span>
- <span data-ttu-id="8412a-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="8412a-1978">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1978">Finland Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1979">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1979">Format</span></span>
<span data-ttu-id="8412a-1980">9 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-1980">Combination of nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1981">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1981">Pattern</span></span>
<span data-ttu-id="8412a-1982">9桁の文字と数字の組み合わせ: 2 文字 (大文字小文字を区別しない) 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1982">Combination of nine letters and digits: Two letters (not case sensitive) Seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1983">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1983">Checksum</span></span>
<span data-ttu-id="8412a-1984">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-1984">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-1985">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-1985">Definition</span></span>
<span data-ttu-id="8412a-1986">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-1987">正規表現 Regex_finland_passport_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-1987">The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-1988">Keyword_finland_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-1988">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
```xml
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="8412a-1989">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-1989">Keywords</span></span>
- <span data-ttu-id="8412a-1990">Keyword_finland_passport_number</span><span class="sxs-lookup"><span data-stu-id="8412a-1990">Keyword_finland_passport_number</span></span>
- <span data-ttu-id="8412a-1991">サインアウト</span><span class="sxs-lookup"><span data-stu-id="8412a-1991">Passport</span></span>
- <span data-ttu-id="8412a-1992">Passi</span><span class="sxs-lookup"><span data-stu-id="8412a-1992">Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="8412a-1993">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-1993">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-1994">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-1994">Format</span></span>

<span data-ttu-id="8412a-1995">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1995">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-1996">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-1996">Pattern</span></span>

<span data-ttu-id="8412a-1997">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-1997">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-1998">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-1998">Checksum</span></span>

<span data-ttu-id="8412a-1999">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-1999">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2000">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2000">Definition</span></span>

<span data-ttu-id="8412a-2001">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2001">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2002">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2002">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2003">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-2003">At least one of the following is true:</span></span>
- <span data-ttu-id="8412a-2004">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2004">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="8412a-2005">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2005">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2006">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2006">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="8412a-2007">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8412a-2007">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="8412a-2008">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2008">drivers licence</span></span>
- <span data-ttu-id="8412a-2009">drivers license</span><span class="sxs-lookup"><span data-stu-id="8412a-2009">drivers license</span></span>
- <span data-ttu-id="8412a-2010">driving licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2010">driving licence</span></span>
- <span data-ttu-id="8412a-2011">driving license</span><span class="sxs-lookup"><span data-stu-id="8412a-2011">driving license</span></span>
- <span data-ttu-id="8412a-2012">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8412a-2012">permis de conduire</span></span>
- <span data-ttu-id="8412a-2013">licence number</span><span class="sxs-lookup"><span data-stu-id="8412a-2013">licence number</span></span>
- <span data-ttu-id="8412a-2014">license number</span><span class="sxs-lookup"><span data-stu-id="8412a-2014">license number</span></span>
- <span data-ttu-id="8412a-2015">licence numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-2015">licence numbers</span></span>
- <span data-ttu-id="8412a-2016">license numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-2016">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="8412a-2017">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="8412a-2017">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2018">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2018">Format</span></span>

<span data-ttu-id="8412a-2019">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2019">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2020">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2020">Pattern</span></span>

<span data-ttu-id="8412a-2021">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2021">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2022">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2022">Checksum</span></span>

<span data-ttu-id="8412a-2023">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2023">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2024">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2024">Definition</span></span>

<span data-ttu-id="8412a-2025">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2025">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2026">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2026">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2027">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2027">Keywords</span></span>

<span data-ttu-id="8412a-2028">なし</span><span class="sxs-lookup"><span data-stu-id="8412a-2028">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="8412a-2029">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2029">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2030">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2030">Format</span></span>

<span data-ttu-id="8412a-2031">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2031">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2032">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2032">Pattern</span></span>

<span data-ttu-id="8412a-2033">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2033">Nine digits and letters:</span></span>
- <span data-ttu-id="8412a-2034">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2034">Two digits</span></span> 
- <span data-ttu-id="8412a-2035">2 つの文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="8412a-2035">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-2036">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2036">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2037">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2037">Checksum</span></span>

<span data-ttu-id="8412a-2038">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2038">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2039">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2039">Definition</span></span>

<span data-ttu-id="8412a-2040">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2040">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2041">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2041">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2042">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2042">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2043">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2043">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="8412a-2044">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-2044">Keyword_passport</span></span>

- <span data-ttu-id="8412a-2045">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2045">Passport Number</span></span>
- <span data-ttu-id="8412a-2046">Passport No</span><span class="sxs-lookup"><span data-stu-id="8412a-2046">Passport No</span></span>
- <span data-ttu-id="8412a-2047">Passport #</span><span class="sxs-lookup"><span data-stu-id="8412a-2047">Passport #</span></span>
- <span data-ttu-id="8412a-2048">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="8412a-2048">Passport#</span></span>
- <span data-ttu-id="8412a-2049">PassportID</span><span class="sxs-lookup"><span data-stu-id="8412a-2049">PassportID</span></span>
- <span data-ttu-id="8412a-2050">Passportno</span><span class="sxs-lookup"><span data-stu-id="8412a-2050">Passportno</span></span>
- <span data-ttu-id="8412a-2051">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-2051">passportnumber</span></span>
- <span data-ttu-id="8412a-2052">パスポート</span><span class="sxs-lookup"><span data-stu-id="8412a-2052">パスポート</span></span>
- <span data-ttu-id="8412a-2053">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2053">パスポート番号</span></span>
- <span data-ttu-id="8412a-2054">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8412a-2054">パスポートのNum</span></span>
- <span data-ttu-id="8412a-2055">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2055">パスポート ＃</span></span> 
- <span data-ttu-id="8412a-2056">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8412a-2056">Numéro de passeport</span></span>
- <span data-ttu-id="8412a-2057">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8412a-2057">Passeport n °</span></span>
- <span data-ttu-id="8412a-2058">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8412a-2058">Passeport Non</span></span>
- <span data-ttu-id="8412a-2059">Passeport #</span><span class="sxs-lookup"><span data-stu-id="8412a-2059">Passeport #</span></span>
- <span data-ttu-id="8412a-2060">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8412a-2060">Passeport#</span></span>
- <span data-ttu-id="8412a-2061">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8412a-2061">PasseportNon</span></span>
- <span data-ttu-id="8412a-2062">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8412a-2062">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="8412a-2063">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="8412a-2063">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2064">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2064">Format</span></span>

<span data-ttu-id="8412a-2065">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2065">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2066">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2066">Pattern</span></span>

<span data-ttu-id="8412a-2067">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="8412a-2067">Must match one of two patterns:</span></span>
- <span data-ttu-id="8412a-2068">13桁の数字の後にスペースを続け、2桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2068">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="8412a-2069">または</span><span class="sxs-lookup"><span data-stu-id="8412a-2069">or</span></span>
- <span data-ttu-id="8412a-2070">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2070">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2071">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2071">Checksum</span></span>

<span data-ttu-id="8412a-2072">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2072">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2073">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2073">Definition</span></span>

<span data-ttu-id="8412a-2074">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2074">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2075">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2075">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2076">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2076">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="8412a-2077">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2077">The checksum passes.</span></span>

<span data-ttu-id="8412a-2078">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2078">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2079">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2079">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2080">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="8412a-2080">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="8412a-2081">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2081">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2082">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2082">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="8412a-2083">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="8412a-2083">Keyword_fr_insee</span></span>

- <span data-ttu-id="8412a-2084">insee</span><span class="sxs-lookup"><span data-stu-id="8412a-2084">insee</span></span>
- <span data-ttu-id="8412a-2085">securité sociale</span><span class="sxs-lookup"><span data-stu-id="8412a-2085">securité sociale</span></span>
- <span data-ttu-id="8412a-2086">securite sociale</span><span class="sxs-lookup"><span data-stu-id="8412a-2086">securite sociale</span></span>
- <span data-ttu-id="8412a-2087">national id</span><span class="sxs-lookup"><span data-stu-id="8412a-2087">national id</span></span>
- <span data-ttu-id="8412a-2088">national identification</span><span class="sxs-lookup"><span data-stu-id="8412a-2088">national identification</span></span>
- <span data-ttu-id="8412a-2089">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="8412a-2089">numéro d'identité</span></span>
- <span data-ttu-id="8412a-2090">no d'identité</span><span class="sxs-lookup"><span data-stu-id="8412a-2090">no d'identité</span></span>
- <span data-ttu-id="8412a-2091">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-2091">no.</span></span> <span data-ttu-id="8412a-2092">d'identité</span><span class="sxs-lookup"><span data-stu-id="8412a-2092">d'identité</span></span>
- <span data-ttu-id="8412a-2093">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="8412a-2093">numero d'identite</span></span>
- <span data-ttu-id="8412a-2094">no d'identite</span><span class="sxs-lookup"><span data-stu-id="8412a-2094">no d'identite</span></span>
- <span data-ttu-id="8412a-2095">違います。</span><span class="sxs-lookup"><span data-stu-id="8412a-2095">no.</span></span> <span data-ttu-id="8412a-2096">d'identite</span><span class="sxs-lookup"><span data-stu-id="8412a-2096">d'identite</span></span>
- <span data-ttu-id="8412a-2097">social security number</span><span class="sxs-lookup"><span data-stu-id="8412a-2097">social security number</span></span>
- <span data-ttu-id="8412a-2098">social security code</span><span class="sxs-lookup"><span data-stu-id="8412a-2098">social security code</span></span>
- <span data-ttu-id="8412a-2099">social insurance number</span><span class="sxs-lookup"><span data-stu-id="8412a-2099">social insurance number</span></span>
- <span data-ttu-id="8412a-2100">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="8412a-2100">le numéro d'identification nationale</span></span>
- <span data-ttu-id="8412a-2101">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="8412a-2101">d'identité nationale</span></span>
- <span data-ttu-id="8412a-2102">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="8412a-2102">numéro de sécurité sociale</span></span>
- <span data-ttu-id="8412a-2103">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="8412a-2103">le code de la sécurité sociale</span></span>
- <span data-ttu-id="8412a-2104">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="8412a-2104">numéro d'assurance sociale</span></span>
- <span data-ttu-id="8412a-2105">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="8412a-2105">numéro de sécu</span></span>
- <span data-ttu-id="8412a-2106">code sécu</span><span class="sxs-lookup"><span data-stu-id="8412a-2106">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="8412a-2107">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2107">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2108">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2108">Format</span></span>

<span data-ttu-id="8412a-2109">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-2109">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2110">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2110">Pattern</span></span>

<span data-ttu-id="8412a-2111">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="8412a-2111">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="8412a-2112">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2112">A digit or letter</span></span> 
- <span data-ttu-id="8412a-2113">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2113">Two digits</span></span> 
- <span data-ttu-id="8412a-2114">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2114">Six digits or letters</span></span> 
- <span data-ttu-id="8412a-2115">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2115">A digit</span></span> 
- <span data-ttu-id="8412a-2116">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2116">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2117">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2117">Checksum</span></span>

<span data-ttu-id="8412a-2118">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2118">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2119">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2119">Definition</span></span>

<span data-ttu-id="8412a-2120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2120">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2121">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2121">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2122">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-2122">At least one of the following is true:</span></span>
    - <span data-ttu-id="8412a-2123">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2123">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="8412a-2124">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2124">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="8412a-2125">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2125">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="8412a-2126">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2126">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2127">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2127">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="8412a-2128">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2128">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="8412a-2129">Führerschein</span><span class="sxs-lookup"><span data-stu-id="8412a-2129">Führerschein</span></span>
- <span data-ttu-id="8412a-2130">Futex</span><span class="sxs-lookup"><span data-stu-id="8412a-2130">Fuhrerschein</span></span>
- <span data-ttu-id="8412a-2131">Futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="8412a-2131">Fuehrerschein</span></span>
- <span data-ttu-id="8412a-2132">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2132">Führerscheinnummer</span></span>
- <span data-ttu-id="8412a-2133">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2133">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="8412a-2134">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2134">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="8412a-2135">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="8412a-2135">Führerschein-</span></span> 
- <span data-ttu-id="8412a-2136">Futex (中)</span><span class="sxs-lookup"><span data-stu-id="8412a-2136">Fuhrerschein-</span></span> 
- <span data-ttu-id="8412a-2137">Futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="8412a-2137">Fuehrerschein-</span></span> 
- <span data-ttu-id="8412a-2138">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8412a-2138">FührerscheinnummerNr</span></span>
- <span data-ttu-id="8412a-2139">Futex がある Hていません Einnumnr</span><span class="sxs-lookup"><span data-stu-id="8412a-2139">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="8412a-2140">Futex の Ehの再リリース/Einnumnr</span><span class="sxs-lookup"><span data-stu-id="8412a-2140">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="8412a-2141">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2141">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="8412a-2142">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2142">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="8412a-2143">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2143">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="8412a-2144">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8412a-2144">Führerschein- Nr</span></span>
- <span data-ttu-id="8412a-2145">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8412a-2145">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="8412a-2146">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8412a-2146">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="8412a-2147">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2147">Führerschein- Klasse</span></span> 
- <span data-ttu-id="8412a-2148">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2148">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="8412a-2149">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2149">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="8412a-2150">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8412a-2150">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="8412a-2151">Futex がある Hていません Einnumnr</span><span class="sxs-lookup"><span data-stu-id="8412a-2151">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="8412a-2152">Futex の Ehの再リリース/Einnumnr</span><span class="sxs-lookup"><span data-stu-id="8412a-2152">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="8412a-2153">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2153">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="8412a-2154">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2154">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="8412a-2155">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2155">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="8412a-2156">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8412a-2156">Führerschein- Nr</span></span> 
- <span data-ttu-id="8412a-2157">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8412a-2157">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="8412a-2158">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8412a-2158">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="8412a-2159">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2159">Führerschein- Klasse</span></span> 
- <span data-ttu-id="8412a-2160">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2160">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="8412a-2161">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2161">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="8412a-2162">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-2162">DL</span></span> 
- <span data-ttu-id="8412a-2163">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-2163">DLS</span></span>
- <span data-ttu-id="8412a-2164">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-2164">Driv Lic</span></span> 
- <span data-ttu-id="8412a-2165">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="8412a-2165">Driv Licen</span></span> 
- <span data-ttu-id="8412a-2166">Driv License</span><span class="sxs-lookup"><span data-stu-id="8412a-2166">Driv License</span></span>
- <span data-ttu-id="8412a-2167">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2167">Driv Licenses</span></span> 
- <span data-ttu-id="8412a-2168">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2168">Driv Licence</span></span> 
- <span data-ttu-id="8412a-2169">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-2169">Driv Licences</span></span> 
- <span data-ttu-id="8412a-2170">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-2170">Driv Lic</span></span> 
- <span data-ttu-id="8412a-2171">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="8412a-2171">Driver Licen</span></span> 
- <span data-ttu-id="8412a-2172">Driver License</span><span class="sxs-lookup"><span data-stu-id="8412a-2172">Driver License</span></span> 
- <span data-ttu-id="8412a-2173">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2173">Driver Licenses</span></span> 
- <span data-ttu-id="8412a-2174">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2174">Driver Licence</span></span> 
- <span data-ttu-id="8412a-2175">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-2175">Driver Licences</span></span> 
- <span data-ttu-id="8412a-2176">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-2176">Drivers Lic</span></span> 
- <span data-ttu-id="8412a-2177">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="8412a-2177">Drivers Licen</span></span> 
- <span data-ttu-id="8412a-2178">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8412a-2178">Drivers License</span></span> 
- <span data-ttu-id="8412a-2179">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2179">Drivers Licenses</span></span> 
- <span data-ttu-id="8412a-2180">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2180">Drivers Licence</span></span> 
- <span data-ttu-id="8412a-2181">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-2181">Drivers Licences</span></span> 
- <span data-ttu-id="8412a-2182">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-2182">Driver's Lic</span></span> 
- <span data-ttu-id="8412a-2183">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="8412a-2183">Driver's Licen</span></span> 
- <span data-ttu-id="8412a-2184">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8412a-2184">Driver's License</span></span> 
- <span data-ttu-id="8412a-2185">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2185">Driver's Licenses</span></span> 
- <span data-ttu-id="8412a-2186">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2186">Driver's Licence</span></span> 
- <span data-ttu-id="8412a-2187">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-2187">Driver's Licences</span></span> 
- <span data-ttu-id="8412a-2188">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-2188">Driving Lic</span></span> 
- <span data-ttu-id="8412a-2189">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="8412a-2189">Driving Licen</span></span> 
- <span data-ttu-id="8412a-2190">Driving License</span><span class="sxs-lookup"><span data-stu-id="8412a-2190">Driving License</span></span> 
- <span data-ttu-id="8412a-2191">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2191">Driving Licenses</span></span> 
- <span data-ttu-id="8412a-2192">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2192">Driving Licence</span></span> 
- <span data-ttu-id="8412a-2193">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="8412a-2193">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="8412a-2194">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="8412a-2194">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="8412a-2195">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8412a-2195">Nr-Führerschein</span></span> 
- <span data-ttu-id="8412a-2196">Nr-Futex</span><span class="sxs-lookup"><span data-stu-id="8412a-2196">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="8412a-2197">"Nr" という Futex</span><span class="sxs-lookup"><span data-stu-id="8412a-2197">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="8412a-2198">Führerschein</span><span class="sxs-lookup"><span data-stu-id="8412a-2198">No-Führerschein</span></span> 
- <span data-ttu-id="8412a-2199">(Futex なし)</span><span class="sxs-lookup"><span data-stu-id="8412a-2199">No-Fuhrerschein</span></span> 
- <span data-ttu-id="8412a-2200">その他の Ehの場合</span><span class="sxs-lookup"><span data-stu-id="8412a-2200">No-Fuehrerschein</span></span> 
- <span data-ttu-id="8412a-2201">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8412a-2201">N-Führerschein</span></span> 
- <span data-ttu-id="8412a-2202">N の Futex</span><span class="sxs-lookup"><span data-stu-id="8412a-2202">N-Fuhrerschein</span></span> 
- <span data-ttu-id="8412a-2203">N 桁の Ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="8412a-2203">N-Fuehrerschein</span></span>
- <span data-ttu-id="8412a-2204">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8412a-2204">Nr-Führerschein</span></span> 
- <span data-ttu-id="8412a-2205">Nr-Futex</span><span class="sxs-lookup"><span data-stu-id="8412a-2205">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="8412a-2206">"Nr" という Futex</span><span class="sxs-lookup"><span data-stu-id="8412a-2206">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="8412a-2207">Führerschein</span><span class="sxs-lookup"><span data-stu-id="8412a-2207">No-Führerschein</span></span> 
- <span data-ttu-id="8412a-2208">(Futex なし)</span><span class="sxs-lookup"><span data-stu-id="8412a-2208">No-Fuhrerschein</span></span> 
- <span data-ttu-id="8412a-2209">その他の Ehの場合</span><span class="sxs-lookup"><span data-stu-id="8412a-2209">No-Fuehrerschein</span></span> 
- <span data-ttu-id="8412a-2210">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8412a-2210">N-Führerschein</span></span> 
- <span data-ttu-id="8412a-2211">N の Futex</span><span class="sxs-lookup"><span data-stu-id="8412a-2211">N-Fuhrerschein</span></span> 
- <span data-ttu-id="8412a-2212">N 桁の Ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="8412a-2212">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="8412a-2213">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8412a-2213">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="8412a-2214">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="8412a-2214">ausstellungsdatum</span></span>
- <span data-ttu-id="8412a-2215">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="8412a-2215">ausstellungsort</span></span>
- <span data-ttu-id="8412a-2216">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="8412a-2216">ausstellende behöde</span></span>
- <span data-ttu-id="8412a-2217">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="8412a-2217">ausstellende behorde</span></span>
- <span data-ttu-id="8412a-2218">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="8412a-2218">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="8412a-2219">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2219">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2220">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2220">Format</span></span>

<span data-ttu-id="8412a-2221">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2221">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2222">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2222">Pattern</span></span>

<span data-ttu-id="8412a-2223">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8412a-2223">Pattern must include all of the following:</span></span>
- <span data-ttu-id="8412a-2224">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2224">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="8412a-2225">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2225">Three digits</span></span> 
- <span data-ttu-id="8412a-2226">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="8412a-2226">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="8412a-2227">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2227">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2228">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2228">Checksum</span></span>

<span data-ttu-id="8412a-2229">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2229">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2230">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2230">Definition</span></span>

<span data-ttu-id="8412a-2231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2231">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2232">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2232">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2233">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2233">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="8412a-2234">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2234">The checksum passes.</span></span>

<span data-ttu-id="8412a-2235">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2236">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2236">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2237">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2237">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="8412a-2238">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2238">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2239">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2239">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="8412a-2240">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-2240">Keyword_german_passport</span></span>

- <span data-ttu-id="8412a-2241">reisepass</span><span class="sxs-lookup"><span data-stu-id="8412a-2241">reisepass</span></span>
- <span data-ttu-id="8412a-2242">reisepasse</span><span class="sxs-lookup"><span data-stu-id="8412a-2242">reisepasse</span></span>
- <span data-ttu-id="8412a-2243">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2243">reisepassnummer</span></span>
- <span data-ttu-id="8412a-2244">サインアウト</span><span class="sxs-lookup"><span data-stu-id="8412a-2244">passport</span></span>
- <span data-ttu-id="8412a-2245">passport</span><span class="sxs-lookup"><span data-stu-id="8412a-2245">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="8412a-2246">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="8412a-2246">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="8412a-2247">ge気流 tsdatum</span><span class="sxs-lookup"><span data-stu-id="8412a-2247">geburtsdatum</span></span>
- <span data-ttu-id="8412a-2248">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="8412a-2248">ausstellungsdatum</span></span>
- <span data-ttu-id="8412a-2249">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="8412a-2249">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="8412a-2250">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2250">Keyword_german_passport_number</span></span>

<span data-ttu-id="8412a-2251">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="8412a-2251">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="8412a-2252">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="8412a-2252">Keyword_german_passport1</span></span>

<span data-ttu-id="8412a-2253">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="8412a-2253">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="8412a-2254">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="8412a-2254">Keyword_german_passport2</span></span>

<span data-ttu-id="8412a-2255">bnationalit</span><span class="sxs-lookup"><span data-stu-id="8412a-2255">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="8412a-2256">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2256">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2257">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2257">Format</span></span>

<span data-ttu-id="8412a-2258">2010年11月1日以降: 9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2258">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="8412a-2259">1987年4月1日から2010年10月31日まで:10 桁</span><span class="sxs-lookup"><span data-stu-id="8412a-2259">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2260">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2260">Pattern</span></span>

<span data-ttu-id="8412a-2261">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="8412a-2261">Since 1 November 2010:</span></span>
- <span data-ttu-id="8412a-2262">1 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-2262">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-2263">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2263">Eight digits</span></span>

<span data-ttu-id="8412a-2264">1987年4月1日から2010年10月31日まで。</span><span class="sxs-lookup"><span data-stu-id="8412a-2264">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="8412a-2265">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2265">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2266">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2266">Checksum</span></span>

<span data-ttu-id="8412a-2267">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2267">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2268">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2268">Definition</span></span>

<span data-ttu-id="8412a-2269">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2269">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2270">正規表現 Regex_germany_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2270">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2271">Keyword_germany_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2271">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2272">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2272">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="8412a-2273">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="8412a-2273">Keyword_germany_id_card</span></span>

- <span data-ttu-id="8412a-2274">Identity Card</span><span class="sxs-lookup"><span data-stu-id="8412a-2274">Identity Card</span></span>
- <span data-ttu-id="8412a-2275">ID</span><span class="sxs-lookup"><span data-stu-id="8412a-2275">ID</span></span>
- <span data-ttu-id="8412a-2276">Fim</span><span class="sxs-lookup"><span data-stu-id="8412a-2276">Identification</span></span>
- <span data-ttu-id="8412a-2277">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="8412a-2277">Personalausweis</span></span>
- <span data-ttu-id="8412a-2278">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2278">Identifizierungsnummer</span></span>
- <span data-ttu-id="8412a-2279">Ausweis</span><span class="sxs-lookup"><span data-stu-id="8412a-2279">Ausweis</span></span>
- <span data-ttu-id="8412a-2280">Identifikation</span><span class="sxs-lookup"><span data-stu-id="8412a-2280">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="8412a-2281">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2281">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2282">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2282">Format</span></span>

<span data-ttu-id="8412a-2283">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="8412a-2283">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2284">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2284">Pattern</span></span>

<span data-ttu-id="8412a-2285">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="8412a-2285">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="8412a-2286">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="8412a-2286">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="8412a-2287">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-2287">A dash</span></span> 
- <span data-ttu-id="8412a-2288">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2288">Six digits</span></span>

<span data-ttu-id="8412a-2289">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="8412a-2289">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="8412a-2290">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2290">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="8412a-2291">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-2291">A dash</span></span> 
- <span data-ttu-id="8412a-2292">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2292">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2293">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2293">Checksum</span></span>

<span data-ttu-id="8412a-2294">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2294">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2295">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2295">Definition</span></span>

<span data-ttu-id="8412a-2296">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2297">正規表現 Regex_greece_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2297">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2298">Keyword_greece_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2298">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2299">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2299">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="8412a-2300">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="8412a-2300">Keyword_greece_id_card</span></span>

- <span data-ttu-id="8412a-2301">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="8412a-2301">Greek identity Card</span></span>
- <span data-ttu-id="8412a-2302">Tautotita</span><span class="sxs-lookup"><span data-stu-id="8412a-2302">Tautotita</span></span>
- <span data-ttu-id="8412a-2303">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="8412a-2303">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="8412a-2304">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="8412a-2304">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="8412a-2305">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2305">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2306">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2306">Format</span></span>

<span data-ttu-id="8412a-2307">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="8412a-2307">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2308">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2308">Pattern</span></span>

<span data-ttu-id="8412a-2309">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="8412a-2309">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="8412a-2310">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-2310">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-2311">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2311">Six digits</span></span> 
- <span data-ttu-id="8412a-2312">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="8412a-2312">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2313">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2313">Checksum</span></span>

<span data-ttu-id="8412a-2314">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2314">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2315">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2315">Definition</span></span>

<span data-ttu-id="8412a-2316">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2317">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2317">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2318">Keyword_hong_kong_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2318">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="8412a-2319">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2319">The checksum passes.</span></span>

<span data-ttu-id="8412a-2320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2320">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2321">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2321">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2322">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2322">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2323">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2323">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="8412a-2324">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="8412a-2324">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="8412a-2325">香港の id カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2325">hong kong identity card</span></span>
- <span data-ttu-id="8412a-2326">HKIDC</span><span class="sxs-lookup"><span data-stu-id="8412a-2326">HKIDC</span></span>
- <span data-ttu-id="8412a-2327">id card</span><span class="sxs-lookup"><span data-stu-id="8412a-2327">id card</span></span>
- <span data-ttu-id="8412a-2328">Identity card</span><span class="sxs-lookup"><span data-stu-id="8412a-2328">identity card</span></span>
- <span data-ttu-id="8412a-2329">hk の id カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2329">hk identity card</span></span>
- <span data-ttu-id="8412a-2330">香港特別行政 id</span><span class="sxs-lookup"><span data-stu-id="8412a-2330">hong kong id</span></span>
- <span data-ttu-id="8412a-2331">香港身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2331">香港身份證</span></span>
- <span data-ttu-id="8412a-2332">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2332">香港永久性居民身份證</span></span>
- <span data-ttu-id="8412a-2333">身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2333">身份證</span></span>
- <span data-ttu-id="8412a-2334">身份証</span><span class="sxs-lookup"><span data-stu-id="8412a-2334">身份証</span></span>
- <span data-ttu-id="8412a-2335">身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-2335">身分證</span></span>
- <span data-ttu-id="8412a-2336">身分証</span><span class="sxs-lookup"><span data-stu-id="8412a-2336">身分証</span></span>
- <span data-ttu-id="8412a-2337">香港身份証</span><span class="sxs-lookup"><span data-stu-id="8412a-2337">香港身份証</span></span>
- <span data-ttu-id="8412a-2338">香港身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-2338">香港身分證</span></span>
- <span data-ttu-id="8412a-2339">香港身分証</span><span class="sxs-lookup"><span data-stu-id="8412a-2339">香港身分証</span></span>
- <span data-ttu-id="8412a-2340">香港身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2340">香港身份證</span></span>
- <span data-ttu-id="8412a-2341">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2341">香港居民身份證</span></span>
- <span data-ttu-id="8412a-2342">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="8412a-2342">香港居民身份証</span></span>
- <span data-ttu-id="8412a-2343">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-2343">香港居民身分證</span></span>
- <span data-ttu-id="8412a-2344">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="8412a-2344">香港居民身分証</span></span>
- <span data-ttu-id="8412a-2345">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8412a-2345">香港永久性居民身份証</span></span>
- <span data-ttu-id="8412a-2346">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-2346">香港永久性居民身分證</span></span>
- <span data-ttu-id="8412a-2347">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8412a-2347">香港永久性居民身分証</span></span>
- <span data-ttu-id="8412a-2348">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2348">香港永久性居民身份證</span></span>
- <span data-ttu-id="8412a-2349">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2349">香港非永久性居民身份證</span></span>
- <span data-ttu-id="8412a-2350">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8412a-2350">香港非永久性居民身份証</span></span>
- <span data-ttu-id="8412a-2351">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-2351">香港非永久性居民身分證</span></span>
- <span data-ttu-id="8412a-2352">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8412a-2352">香港非永久性居民身分証</span></span>
- <span data-ttu-id="8412a-2353">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2353">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="8412a-2354">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8412a-2354">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="8412a-2355">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-2355">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="8412a-2356">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8412a-2356">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="8412a-2357">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-2357">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="8412a-2358">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8412a-2358">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="8412a-2359">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-2359">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="8412a-2360">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8412a-2360">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="8412a-2361">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="8412a-2361">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2362">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2362">Format</span></span>

<span data-ttu-id="8412a-2363">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2363">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2364">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2364">Pattern</span></span>

<span data-ttu-id="8412a-2365">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2365">10 letters or digits:</span></span>
- <span data-ttu-id="8412a-2366">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-2366">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-2367">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2367">Four digits</span></span> 
- <span data-ttu-id="8412a-2368">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2368">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2369">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2369">Checksum</span></span>

<span data-ttu-id="8412a-2370">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2370">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2371">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2371">Definition</span></span>

<span data-ttu-id="8412a-2372">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2372">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2373">正規表現 Regex_india_permanent_account_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2373">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2374">Keyword_india_permanent_account_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2374">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="8412a-2375">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2375">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2376">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2376">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="8412a-2377">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2377">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="8412a-2378">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2378">Permanent Account Number</span></span> 
- <span data-ttu-id="8412a-2379">ペン</span><span class="sxs-lookup"><span data-stu-id="8412a-2379">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="8412a-2380">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2380">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2381">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2381">Format</span></span>

<span data-ttu-id="8412a-2382">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2382">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2383">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2383">Pattern</span></span>

<span data-ttu-id="8412a-2384">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2384">12 digits:</span></span>
- <span data-ttu-id="8412a-2385">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2385">Four digits</span></span> 
- <span data-ttu-id="8412a-2386">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2386">An optional space or dash</span></span> 
- <span data-ttu-id="8412a-2387">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2387">Four digits</span></span> 
- <span data-ttu-id="8412a-2388">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2388">An optional space or dash</span></span> 
- <span data-ttu-id="8412a-2389">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="8412a-2389">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2390">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2390">Checksum</span></span>

<span data-ttu-id="8412a-2391">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2391">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2392">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2392">Definition</span></span>

<span data-ttu-id="8412a-2393">DLP ポリシーは85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2393">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="8412a-2394">Keyword_india_aadhar からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2394">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="8412a-2395">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2395">The checksum passes.</span></span>
<span data-ttu-id="8412a-2396">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="8412a-2397">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2397">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="8412a-2398">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2398">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="8412a-2399">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="8412a-2399">Keyword_india_aadhar</span></span>
- <span data-ttu-id="8412a-2400">Aadhar</span><span class="sxs-lookup"><span data-stu-id="8412a-2400">Aadhar</span></span>
- <span data-ttu-id="8412a-2401">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="8412a-2401">Aadhaar</span></span>
- <span data-ttu-id="8412a-2402">UID</span><span class="sxs-lookup"><span data-stu-id="8412a-2402">UID</span></span>
- <span data-ttu-id="8412a-2403">आधार</span><span class="sxs-lookup"><span data-stu-id="8412a-2403">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="8412a-2404">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2404">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2405">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2405">Format</span></span>

<span data-ttu-id="8412a-2406">省略可能なピリオドを含む 16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2406">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2407">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2407">Pattern</span></span>

<span data-ttu-id="8412a-2408">16 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2408">16 digits:</span></span>
- <span data-ttu-id="8412a-2409">2 桁の行政区コード </span><span class="sxs-lookup"><span data-stu-id="8412a-2409">Two-digit province code</span></span> 
- <span data-ttu-id="8412a-2410">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2410">A period (optional)</span></span> 
- <span data-ttu-id="8412a-2411">2 桁の行政区または市コード </span><span class="sxs-lookup"><span data-stu-id="8412a-2411">Two-digit regency or city code</span></span> 
- <span data-ttu-id="8412a-2412">2 桁の分区コード </span><span class="sxs-lookup"><span data-stu-id="8412a-2412">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="8412a-2413">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2413">A period (optional)</span></span> 
- <span data-ttu-id="8412a-2414">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2414">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="8412a-2415">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2415">A period (optional)</span></span> 
- <span data-ttu-id="8412a-2416">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2416">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2417">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2417">Checksum</span></span>

<span data-ttu-id="8412a-2418">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2419">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2419">Definition</span></span>

<span data-ttu-id="8412a-2420">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2421">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2421">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2422">Keyword_indonesia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2422">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="8412a-2423">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2423">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2424">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2424">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2425">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2425">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="8412a-2426">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="8412a-2426">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="8412a-2427">KTP</span><span class="sxs-lookup"><span data-stu-id="8412a-2427">KTP</span></span>
- <span data-ttu-id="8412a-2428">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="8412a-2428">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="8412a-2429">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="8412a-2429">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="8412a-2430">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="8412a-2430">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2431">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2431">Format</span></span>

<span data-ttu-id="8412a-2432">国コード (2 文字)、チェックディジット (2 桁)、および番号を bban 最大30文字)</span><span class="sxs-lookup"><span data-stu-id="8412a-2432">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2433">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2433">Pattern</span></span>

<span data-ttu-id="8412a-2434">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8412a-2434">Pattern must include all of the following:</span></span>

- <span data-ttu-id="8412a-2435">2文字の国コード</span><span class="sxs-lookup"><span data-stu-id="8412a-2435">Two-letter country code</span></span>
- <span data-ttu-id="8412a-2436">2つのチェックディジット (オプションのスペースが続く)</span><span class="sxs-lookup"><span data-stu-id="8412a-2436">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="8412a-2437">1-7 4 つの文字または数字のグループ (スペースで区切ることができます)</span><span class="sxs-lookup"><span data-stu-id="8412a-2437">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="8412a-2438">1 ～ 3 個の文字または数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2438">1-3 letters or digits</span></span>

<span data-ttu-id="8412a-2439">各国の形式は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="8412a-2439">The format for each country is slightly different.</span></span> <span data-ttu-id="8412a-2440">IBAN 機密情報の種類には、次の60国が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8412a-2440">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="8412a-2441">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、gi、gl、gr、hr、hu、ie、[il]、[it]、[]、[(it)]、[(kz)]、[、li、lt、lu、lv、mc]、[]、[いいえ]、[mr]、[]、[]、[、]</span><span class="sxs-lookup"><span data-stu-id="8412a-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2442">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2442">Checksum</span></span>

<span data-ttu-id="8412a-2443">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2443">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2444">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2444">Definition</span></span>

<span data-ttu-id="8412a-2445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2445">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2446">関数 Func_iban がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2446">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2447">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2447">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2448">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2448">Keywords</span></span>

<span data-ttu-id="8412a-2449">なし</span><span class="sxs-lookup"><span data-stu-id="8412a-2449">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="8412a-2450">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="8412a-2450">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2451">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2451">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="8412a-2452">IPv4</span><span class="sxs-lookup"><span data-stu-id="8412a-2452">IPv4:</span></span>
<span data-ttu-id="8412a-2453">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2453">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="8412a-2454">IPv6</span><span class="sxs-lookup"><span data-stu-id="8412a-2454">IPv6:</span></span>
<span data-ttu-id="8412a-2455"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2455">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2456">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2456">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2457">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2457">Checksum</span></span>

<span data-ttu-id="8412a-2458">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2458">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2459">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2459">Definition</span></span>

<span data-ttu-id="8412a-2460">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2460">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2461">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2461">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2462">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="8412a-2462">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="8412a-2463">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2463">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2464">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2464">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2465">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2465">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="8412a-2466">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2466">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2467">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2467">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2468">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="8412a-2468">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2469">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2469">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="8412a-2470">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="8412a-2470">Keyword_ipaddress</span></span>

- <span data-ttu-id="8412a-2471">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="8412a-2471">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="8412a-2472">ip address</span><span class="sxs-lookup"><span data-stu-id="8412a-2472">ip address</span></span> 
- <span data-ttu-id="8412a-2473">ip addresses</span><span class="sxs-lookup"><span data-stu-id="8412a-2473">ip addresses</span></span>
- <span data-ttu-id="8412a-2474">internet protocol</span><span class="sxs-lookup"><span data-stu-id="8412a-2474">internet protocol</span></span>
- <span data-ttu-id="8412a-2475">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="8412a-2475">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="8412a-2476">Diseases の国際分類 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8412a-2476">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2477">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2477">Format</span></span>

<span data-ttu-id="8412a-2478">Dictionary</span><span class="sxs-lookup"><span data-stu-id="8412a-2478">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2479">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2479">Pattern</span></span>

<span data-ttu-id="8412a-2480">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2480">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2481">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2481">Checksum</span></span>

<span data-ttu-id="8412a-2482">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2482">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2483">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2483">Definition</span></span>

<span data-ttu-id="8412a-2484">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2485">Dictionary_icd_10_updated からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2485">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="8412a-2486">Dictionary_icd_10_codes からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2486">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="8412a-2487">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2487">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2488">Dictionary_icd_10_ 更新されたキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2488">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="8412a-2489">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2489">Keywords</span></span>

<span data-ttu-id="8412a-2490">Dictionary_icd_10_updated キーワードディクショナリからの任意の用語。 [Diseases、10リビジョン、臨床修正 (icd-10-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8412a-2490">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="8412a-2491">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8412a-2491">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="8412a-2492">Dictionary_icd_10_codes キーワードディクショナリからの任意の用語。 [Diseases、10リビジョン、臨床修正 (icd-10-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8412a-2492">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="8412a-2493">この型は、説明ではなく、保険コードに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8412a-2493">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="8412a-2494">Diseases の国際分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8412a-2494">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2495">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2495">Format</span></span>

<span data-ttu-id="8412a-2496">Dictionary</span><span class="sxs-lookup"><span data-stu-id="8412a-2496">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2497">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2497">Pattern</span></span>

<span data-ttu-id="8412a-2498">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2498">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2499">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2499">Checksum</span></span>

<span data-ttu-id="8412a-2500">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2500">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2501">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2501">Definition</span></span>

<span data-ttu-id="8412a-2502">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2502">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2503">Dictionary_icd_9_updated からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2503">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="8412a-2504">Dictionary_icd_9_codes からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2504">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="8412a-2505">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2505">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2506">Dictionary_icd_9_updated からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2506">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2507">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2507">Keywords</span></span>

<span data-ttu-id="8412a-2508">Dictionary_icd_9_updated キーワードディクショナリの任意の用語。 [Diseases、9リビジョン、臨床修正 (icd-9-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8412a-2508">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="8412a-2509">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8412a-2509">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="8412a-2510">Dictionary_icd_9_codes キーワードディクショナリの任意の用語。 [Diseases、9リビジョン、臨床修正 (icd-9-CM) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8412a-2510">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="8412a-2511">この型は、説明ではなく、保険コードに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8412a-2511">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="8412a-2512">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2512">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2513">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2513">Format</span></span>

<span data-ttu-id="8412a-2514">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="8412a-2514">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="8412a-2515">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2515">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="8412a-2516">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="8412a-2516">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="8412a-2517">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2517">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2518">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2518">Pattern</span></span>

<span data-ttu-id="8412a-2519">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="8412a-2519">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="8412a-2520">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2520">Seven digits</span></span> 
- <span data-ttu-id="8412a-2521">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-2521">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="8412a-2522">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="8412a-2522">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="8412a-2523">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2523">Seven digits</span></span> 
- <span data-ttu-id="8412a-2524">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-2524">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="8412a-2525">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="8412a-2525">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2526">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2526">Checksum</span></span>

<span data-ttu-id="8412a-2527">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2527">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2528">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2528">Definition</span></span>

<span data-ttu-id="8412a-2529">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2530">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2530">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2531">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-2531">One of the following is true:</span></span>
    - <span data-ttu-id="8412a-2532">Keyword_ireland_pps からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2532">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="8412a-2533">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2533">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8412a-2534">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2534">The checksum passes.</span></span>

<span data-ttu-id="8412a-2535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2535">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2536">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2536">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2537">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2537">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2538">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2538">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="8412a-2539">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="8412a-2539">Keyword_ireland_pps</span></span>

- <span data-ttu-id="8412a-2540">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2540">Personal Public Service Number</span></span> 
- <span data-ttu-id="8412a-2541">PPS Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2541">PPS Number</span></span> 
- <span data-ttu-id="8412a-2542">PPS Num</span><span class="sxs-lookup"><span data-stu-id="8412a-2542">PPS Num</span></span> 
- <span data-ttu-id="8412a-2543">PPS No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2543">PPS No.</span></span> 
- <span data-ttu-id="8412a-2544">PPS #</span><span class="sxs-lookup"><span data-stu-id="8412a-2544">PPS #</span></span> 
- <span data-ttu-id="8412a-2545">PPS#</span><span class="sxs-lookup"><span data-stu-id="8412a-2545">PPS#</span></span> 
- <span data-ttu-id="8412a-2546">PPSN</span><span class="sxs-lookup"><span data-stu-id="8412a-2546">PPSN</span></span> 
- <span data-ttu-id="8412a-2547">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="8412a-2547">Public Services Card</span></span> 
- <span data-ttu-id="8412a-2548">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="8412a-2548">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="8412a-2549">Uimh.</span><span class="sxs-lookup"><span data-stu-id="8412a-2549">Uimh.</span></span> <span data-ttu-id="8412a-2550">PSP</span><span class="sxs-lookup"><span data-stu-id="8412a-2550">PSP</span></span> 
- <span data-ttu-id="8412a-2551">PSP</span><span class="sxs-lookup"><span data-stu-id="8412a-2551">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="8412a-2552">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2552">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2553">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2553">Format</span></span>

<span data-ttu-id="8412a-2554">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2554">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2555">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2555">Pattern</span></span>

<span data-ttu-id="8412a-2556">さ</span><span class="sxs-lookup"><span data-stu-id="8412a-2556">Formatted:</span></span>
- <span data-ttu-id="8412a-2557">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2557">Two digits</span></span> 
- <span data-ttu-id="8412a-2558">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-2558">A dash</span></span> 
- <span data-ttu-id="8412a-2559">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2559">Three digits</span></span> 
- <span data-ttu-id="8412a-2560">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-2560">A dash</span></span> 
- <span data-ttu-id="8412a-2561">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2561">Eight digits</span></span>

<span data-ttu-id="8412a-2562">なし</span><span class="sxs-lookup"><span data-stu-id="8412a-2562">Unformatted:</span></span>
- <span data-ttu-id="8412a-2563">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2563">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2564">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2564">Checksum</span></span>

<span data-ttu-id="8412a-2565">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2565">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2566">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2566">Definition</span></span>

<span data-ttu-id="8412a-2567">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2568">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2568">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2569">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2569">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2570">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2570">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="8412a-2571">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2571">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="8412a-2572">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2572">Bank Account Number</span></span> 
- <span data-ttu-id="8412a-2573">Bank Account</span><span class="sxs-lookup"><span data-stu-id="8412a-2573">Bank Account</span></span> 
- <span data-ttu-id="8412a-2574">Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2574">Account Number</span></span> 
- <span data-ttu-id="8412a-2575">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="8412a-2575">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="8412a-2576">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="8412a-2576">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2577">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2577">Format</span></span>

<span data-ttu-id="8412a-2578">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2578">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2579">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2579">Pattern</span></span>

<span data-ttu-id="8412a-2580">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2580">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2581">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2581">Checksum</span></span>

<span data-ttu-id="8412a-2582">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2582">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2583">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2583">Definition</span></span>

<span data-ttu-id="8412a-2584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2585">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2585">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2586">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2586">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="8412a-2587">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2587">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2588">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2588">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="8412a-2589">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="8412a-2589">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="8412a-2590">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="8412a-2590">מספר זהות</span></span> 
- <span data-ttu-id="8412a-2591">National ID Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2591">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="8412a-2592">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2592">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2593">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2593">Format</span></span>

<span data-ttu-id="8412a-2594">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-2594">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2595">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2595">Pattern</span></span>

- <span data-ttu-id="8412a-2596">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="8412a-2596">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="8412a-2597">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="8412a-2597">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-2598">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="8412a-2598">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-2599">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="8412a-2599">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="8412a-2600">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="8412a-2600">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2601">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2601">Checksum</span></span>

<span data-ttu-id="8412a-2602">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2602">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2603">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2603">Definition</span></span>

<span data-ttu-id="8412a-2604">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2604">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2605">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2605">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2606">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2606">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2607">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2607">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="8412a-2608">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2608">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="8412a-2609">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="8412a-2609">numero di patente di guida</span></span> 
- <span data-ttu-id="8412a-2610">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8412a-2610">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="8412a-2611">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2611">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2612">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2612">Format</span></span>

<span data-ttu-id="8412a-2613">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2613">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2614">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2614">Pattern</span></span>

<span data-ttu-id="8412a-2615">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="8412a-2615">Bank account number:</span></span>
- <span data-ttu-id="8412a-2616">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2616">Seven or eight digits</span></span>
- <span data-ttu-id="8412a-2617">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="8412a-2617">Bank account branch code:</span></span>
- <span data-ttu-id="8412a-2618">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2618">Four digits</span></span> 
- <span data-ttu-id="8412a-2619">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8412a-2619">A space or dash (optional)</span></span> 
- <span data-ttu-id="8412a-2620">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2620">Three digits</span></span>

<span data-ttu-id="8412a-2621">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2621">Checksum</span></span>

<span data-ttu-id="8412a-2622">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2622">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2623">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2623">Definition</span></span>

<span data-ttu-id="8412a-2624">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2625">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2625">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2626">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2626">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="8412a-2627">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-2627">One of the following is true:</span></span>
- <span data-ttu-id="8412a-2628">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2628">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2629">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2629">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="8412a-2630">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2631">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2631">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2632">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2632">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2633">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2633">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="8412a-2634">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="8412a-2634">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="8412a-2635">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2635">Checking Account Number</span></span> 
- <span data-ttu-id="8412a-2636">Checking Account</span><span class="sxs-lookup"><span data-stu-id="8412a-2636">Checking Account</span></span> 
- <span data-ttu-id="8412a-2637">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-2637">Checking Account #</span></span> 
- <span data-ttu-id="8412a-2638">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2638">Checking Acct Number</span></span> 
- <span data-ttu-id="8412a-2639">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-2639">Checking Acct #</span></span> 
- <span data-ttu-id="8412a-2640">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2640">Checking Acct No.</span></span> 
- <span data-ttu-id="8412a-2641">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2641">Checking Account No.</span></span> 
- <span data-ttu-id="8412a-2642">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2642">Bank Account Number</span></span> 
- <span data-ttu-id="8412a-2643">Bank Account</span><span class="sxs-lookup"><span data-stu-id="8412a-2643">Bank Account</span></span> 
- <span data-ttu-id="8412a-2644">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-2644">Bank Account #</span></span> 
- <span data-ttu-id="8412a-2645">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2645">Bank Acct Number</span></span> 
- <span data-ttu-id="8412a-2646">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-2646">Bank Acct #</span></span> 
- <span data-ttu-id="8412a-2647">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2647">Bank Acct No.</span></span> 
- <span data-ttu-id="8412a-2648">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2648">Bank Account No.</span></span> 
- <span data-ttu-id="8412a-2649">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2649">Savings Account Number</span></span> 
- <span data-ttu-id="8412a-2650">Savings Account</span><span class="sxs-lookup"><span data-stu-id="8412a-2650">Savings Account</span></span> 
- <span data-ttu-id="8412a-2651">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-2651">Savings Account #</span></span> 
- <span data-ttu-id="8412a-2652">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2652">Savings Acct Number</span></span> 
- <span data-ttu-id="8412a-2653">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-2653">Savings Acct #</span></span> 
- <span data-ttu-id="8412a-2654">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2654">Savings Acct No.</span></span> 
- <span data-ttu-id="8412a-2655">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2655">Savings Account No.</span></span> 
- <span data-ttu-id="8412a-2656">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2656">Debit Account Number</span></span> 
- <span data-ttu-id="8412a-2657">Debit Account</span><span class="sxs-lookup"><span data-stu-id="8412a-2657">Debit Account</span></span> 
- <span data-ttu-id="8412a-2658">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-2658">Debit Account #</span></span> 
- <span data-ttu-id="8412a-2659">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2659">Debit Acct Number</span></span> 
- <span data-ttu-id="8412a-2660">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-2660">Debit Acct #</span></span> 
- <span data-ttu-id="8412a-2661">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2661">Debit Acct No.</span></span> 
- <span data-ttu-id="8412a-2662">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2662">Debit Account No.</span></span> 
- <span data-ttu-id="8412a-2663">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="8412a-2663">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="8412a-2664">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="8412a-2664">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="8412a-2665">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="8412a-2665">＃勘定の確認</span></span> 
- <span data-ttu-id="8412a-2666">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="8412a-2666">勘定番号の確認</span></span> 
- <span data-ttu-id="8412a-2667">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="8412a-2667">口座番号の確認</span></span> 
- <span data-ttu-id="8412a-2668">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2668">銀行口座番号</span></span> 
- <span data-ttu-id="8412a-2669">銀行口座</span><span class="sxs-lookup"><span data-stu-id="8412a-2669">銀行口座</span></span> 
- <span data-ttu-id="8412a-2670">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2670">銀行口座＃</span></span> 
- <span data-ttu-id="8412a-2671">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2671">銀行の勘定番号</span></span> 
- <span data-ttu-id="8412a-2672">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2672">銀行のacct＃</span></span> 
- <span data-ttu-id="8412a-2673">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2673">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="8412a-2674">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2674">銀行口座番号</span></span>
- <span data-ttu-id="8412a-2675">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2675">普通預金口座番号</span></span> 
- <span data-ttu-id="8412a-2676">預金口座</span><span class="sxs-lookup"><span data-stu-id="8412a-2676">預金口座</span></span> 
- <span data-ttu-id="8412a-2677">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2677">貯蓄口座＃</span></span> 
- <span data-ttu-id="8412a-2678">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="8412a-2678">貯蓄勘定の数</span></span> 
- <span data-ttu-id="8412a-2679">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2679">貯蓄勘定＃</span></span> 
- <span data-ttu-id="8412a-2680">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2680">貯蓄勘定番号</span></span> 
- <span data-ttu-id="8412a-2681">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2681">普通預金口座番号</span></span> 
- <span data-ttu-id="8412a-2682">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2682">引き落とし口座番号</span></span> 
- <span data-ttu-id="8412a-2683">口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2683">口座番号</span></span> 
- <span data-ttu-id="8412a-2684">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2684">口座番号＃</span></span> 
- <span data-ttu-id="8412a-2685">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2685">デビットのacct番号</span></span> 
- <span data-ttu-id="8412a-2686">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2686">デビット勘定＃</span></span> 
- <span data-ttu-id="8412a-2687">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2687">デビットACCTの番号</span></span> 
- <span data-ttu-id="8412a-2688">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2688">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="8412a-2689">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="8412a-2689">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="8412a-2690">Otemachi</span><span class="sxs-lookup"><span data-stu-id="8412a-2690">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="8412a-2691">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2691">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2692">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2692">Format</span></span>

<span data-ttu-id="8412a-2693">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2693">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2694">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2694">Pattern</span></span>

<span data-ttu-id="8412a-2695">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2695">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2696">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2696">Checksum</span></span>

<span data-ttu-id="8412a-2697">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2697">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2698">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2698">Definition</span></span>

<span data-ttu-id="8412a-2699">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2699">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2700">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2700">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2701">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2701">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2702">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2702">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="8412a-2703">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2703">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="8412a-2704">dl#</span><span class="sxs-lookup"><span data-stu-id="8412a-2704">dl#</span></span> 
- <span data-ttu-id="8412a-2705">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-2705">DL＃</span></span> 
- <span data-ttu-id="8412a-2706">dl#</span><span class="sxs-lookup"><span data-stu-id="8412a-2706">dls#</span></span> 
- <span data-ttu-id="8412a-2707">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-2707">DLS＃</span></span> 
- <span data-ttu-id="8412a-2708">driver license</span><span class="sxs-lookup"><span data-stu-id="8412a-2708">driver license</span></span> 
- <span data-ttu-id="8412a-2709">driver licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2709">driver licenses</span></span> 
- <span data-ttu-id="8412a-2710">drivers license</span><span class="sxs-lookup"><span data-stu-id="8412a-2710">drivers license</span></span> 
- <span data-ttu-id="8412a-2711">driver's license</span><span class="sxs-lookup"><span data-stu-id="8412a-2711">driver's license</span></span> 
- <span data-ttu-id="8412a-2712">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2712">drivers licenses</span></span> 
- <span data-ttu-id="8412a-2713">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-2713">driver's licenses</span></span> 
- <span data-ttu-id="8412a-2714">driving licence</span><span class="sxs-lookup"><span data-stu-id="8412a-2714">driving licence</span></span> 
- <span data-ttu-id="8412a-2715">そして#</span><span class="sxs-lookup"><span data-stu-id="8412a-2715">lic#</span></span> 
- <span data-ttu-id="8412a-2716">そして</span><span class="sxs-lookup"><span data-stu-id="8412a-2716">LIC＃</span></span> 
- <span data-ttu-id="8412a-2717">lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-2717">lics#</span></span> 
- <span data-ttu-id="8412a-2718">state id</span><span class="sxs-lookup"><span data-stu-id="8412a-2718">state id</span></span> 
- <span data-ttu-id="8412a-2719">state identification</span><span class="sxs-lookup"><span data-stu-id="8412a-2719">state identification</span></span> 
- <span data-ttu-id="8412a-2720">state identification number</span><span class="sxs-lookup"><span data-stu-id="8412a-2720">state identification number</span></span> 
- <span data-ttu-id="8412a-2721">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2721">低所得国＃</span></span> 
- <span data-ttu-id="8412a-2722">免許証</span><span class="sxs-lookup"><span data-stu-id="8412a-2722">免許証</span></span> 
- <span data-ttu-id="8412a-2723">状態ID</span><span class="sxs-lookup"><span data-stu-id="8412a-2723">状態ID</span></span>
- <span data-ttu-id="8412a-2724">状態の識別</span><span class="sxs-lookup"><span data-stu-id="8412a-2724">状態の識別</span></span> 
- <span data-ttu-id="8412a-2725">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2725">状態の識別番号</span></span> 
- <span data-ttu-id="8412a-2726">運転免許</span><span class="sxs-lookup"><span data-stu-id="8412a-2726">運転免許</span></span> 
- <span data-ttu-id="8412a-2727">運転免許証</span><span class="sxs-lookup"><span data-stu-id="8412a-2727">運転免許証</span></span> 
- <span data-ttu-id="8412a-2728">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2728">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="8412a-2729">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2729">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2730">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2730">Format</span></span>

<span data-ttu-id="8412a-2731">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2731">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2732">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2732">Pattern</span></span>

<span data-ttu-id="8412a-2733">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2733">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2734">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2734">Checksum</span></span>

<span data-ttu-id="8412a-2735">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2736">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2736">Definition</span></span>

<span data-ttu-id="8412a-2737">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2738">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2738">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2739">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2739">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2740">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2740">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="8412a-2741">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-2741">Keyword_jp_passport</span></span>

- <span data-ttu-id="8412a-2742">パスポート</span><span class="sxs-lookup"><span data-stu-id="8412a-2742">パスポート</span></span> 
- <span data-ttu-id="8412a-2743">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2743">パスポート番号</span></span> 
- <span data-ttu-id="8412a-2744">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8412a-2744">パスポートのNum</span></span> 
- <span data-ttu-id="8412a-2745">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="8412a-2745">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="8412a-2746">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2746">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2747">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2747">Format</span></span>

<span data-ttu-id="8412a-2748">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2748">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2749">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2749">Pattern</span></span>

<span data-ttu-id="8412a-2750">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2750">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2751">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2751">Checksum</span></span>

<span data-ttu-id="8412a-2752">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2752">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2753">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2753">Definition</span></span>

<span data-ttu-id="8412a-2754">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2755">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2755">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2756">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2756">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2757">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2757">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="8412a-2758">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2758">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="8412a-2759">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2759">Resident Registration Number</span></span>
- <span data-ttu-id="8412a-2760">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2760">Resident Register Number</span></span> 
- <span data-ttu-id="8412a-2761">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2761">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="8412a-2762">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2762">Resident Registration No.</span></span> 
- <span data-ttu-id="8412a-2763">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2763">Resident Register No.</span></span> 
- <span data-ttu-id="8412a-2764">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2764">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="8412a-2765">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2765">Basic Resident Register No.</span></span> 
- <span data-ttu-id="8412a-2766">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="8412a-2766">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="8412a-2767">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2767">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="8412a-2768">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="8412a-2768">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="8412a-2769">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2769">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="8412a-2770">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="8412a-2770">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2771">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2771">Format</span></span>

<span data-ttu-id="8412a-2772">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2772">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2773">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2773">Pattern</span></span>

<span data-ttu-id="8412a-2774">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2774">7-12 digits:</span></span>
- <span data-ttu-id="8412a-2775">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2775">Four digits</span></span> 
- <span data-ttu-id="8412a-2776">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8412a-2776">A hyphen (optional)</span></span> 
- <span data-ttu-id="8412a-2777">6桁の数字または</span><span class="sxs-lookup"><span data-stu-id="8412a-2777">Six digits OR</span></span>
- <span data-ttu-id="8412a-2778">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2778">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2779">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2779">Checksum</span></span>

<span data-ttu-id="8412a-2780">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2780">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2781">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2781">Definition</span></span>

<span data-ttu-id="8412a-2782">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2782">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2783">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2783">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2784">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2784">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="8412a-2785">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2785">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2786">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2786">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2787">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2787">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2788">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2788">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="8412a-2789">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="8412a-2789">Keyword_jp_sin</span></span>

- <span data-ttu-id="8412a-2790">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="8412a-2790">Social Insurance No.</span></span> 
- <span data-ttu-id="8412a-2791">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="8412a-2791">Social Insurance Num</span></span> 
- <span data-ttu-id="8412a-2792">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2792">Social Insurance Number</span></span> 
- <span data-ttu-id="8412a-2793">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="8412a-2793">社会保険のテンキー</span></span> 
- <span data-ttu-id="8412a-2794">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2794">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="8412a-2795">日本の居住カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2795">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2796">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2796">Format</span></span>

<span data-ttu-id="8412a-2797">12桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2797">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2798">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2798">Pattern</span></span>

<span data-ttu-id="8412a-2799">12桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2799">12 letters and digits:</span></span>
- <span data-ttu-id="8412a-2800">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-2800">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="8412a-2801">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2801">Eight digits</span></span> 
- <span data-ttu-id="8412a-2802">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-2802">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2803">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2803">Checksum</span></span>

<span data-ttu-id="8412a-2804">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2804">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2805">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2805">Definition</span></span>

<span data-ttu-id="8412a-2806">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2807">正規表現 Regex_jp_residence_card_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2807">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2808">Keyword_jp_residence_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2808">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2809">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2809">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="8412a-2810">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2810">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="8412a-2811">居住カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2811">Residence card number</span></span>
- <span data-ttu-id="8412a-2812">住居カードなし</span><span class="sxs-lookup"><span data-stu-id="8412a-2812">Residence card no</span></span>
- <span data-ttu-id="8412a-2813">住居カード#</span><span class="sxs-lookup"><span data-stu-id="8412a-2813">Residence card #</span></span>
- <span data-ttu-id="8412a-2814">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2814">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="8412a-2815">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2815">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2816">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2816">Format</span></span>

<span data-ttu-id="8412a-2817">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2817">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2818">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2818">Pattern</span></span>

<span data-ttu-id="8412a-2819">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2819">12 digits:</span></span>
- <span data-ttu-id="8412a-2820">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2820">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8412a-2821">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2821">A dash (optional)</span></span> 
- <span data-ttu-id="8412a-2822">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2822">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="8412a-2823">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2823">A dash (optional)</span></span> 
- <span data-ttu-id="8412a-2824">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2824">Three random digits</span></span> 
- <span data-ttu-id="8412a-2825">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="8412a-2825">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2826">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2826">Checksum</span></span>

<span data-ttu-id="8412a-2827">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2827">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2828">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2828">Definition</span></span>

<span data-ttu-id="8412a-2829">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2829">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2830">正規表現 Regex_malaysia_id_card_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2830">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2831">Keyword_malaysia_id_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2831">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2832">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2832">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="8412a-2833">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2833">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="8412a-2834">デジタルアプリケーションカード</span><span class="sxs-lookup"><span data-stu-id="8412a-2834">digital application card</span></span>
- <span data-ttu-id="8412a-2835">i/c</span><span class="sxs-lookup"><span data-stu-id="8412a-2835">i/c</span></span>
- <span data-ttu-id="8412a-2836">i/c いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2836">i/c no</span></span>
- <span data-ttu-id="8412a-2837">ic</span><span class="sxs-lookup"><span data-stu-id="8412a-2837">ic</span></span>
- <span data-ttu-id="8412a-2838">ic no</span><span class="sxs-lookup"><span data-stu-id="8412a-2838">ic no</span></span>
- <span data-ttu-id="8412a-2839">id card</span><span class="sxs-lookup"><span data-stu-id="8412a-2839">id card</span></span>
- <span data-ttu-id="8412a-2840">識別カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2840">identification Card</span></span>
- <span data-ttu-id="8412a-2841">Identity card</span><span class="sxs-lookup"><span data-stu-id="8412a-2841">identity card</span></span>
- <span data-ttu-id="8412a-2842">k/p</span><span class="sxs-lookup"><span data-stu-id="8412a-2842">k/p</span></span>
- <span data-ttu-id="8412a-2843">k/p no</span><span class="sxs-lookup"><span data-stu-id="8412a-2843">k/p no</span></span>
- <span data-ttu-id="8412a-2844">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="8412a-2844">kad akuan diri</span></span>
- <span data-ttu-id="8412a-2845">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="8412a-2845">kad aplikasi digital</span></span>
- <span data-ttu-id="8412a-2846">kad の genalan マレーシア</span><span class="sxs-lookup"><span data-stu-id="8412a-2846">kad pengenalan malaysia</span></span>
- <span data-ttu-id="8412a-2847">kp</span><span class="sxs-lookup"><span data-stu-id="8412a-2847">kp</span></span>
- <span data-ttu-id="8412a-2848">kp no</span><span class="sxs-lookup"><span data-stu-id="8412a-2848">kp no</span></span>
- <span data-ttu-id="8412a-2849">mykad</span><span class="sxs-lookup"><span data-stu-id="8412a-2849">mykad</span></span>
- <span data-ttu-id="8412a-2850">mykas</span><span class="sxs-lookup"><span data-stu-id="8412a-2850">mykas</span></span>
- <span data-ttu-id="8412a-2851">mykid</span><span class="sxs-lookup"><span data-stu-id="8412a-2851">mykid</span></span>
- <span data-ttu-id="8412a-2852">mypr</span><span class="sxs-lookup"><span data-stu-id="8412a-2852">mypr</span></span>
- <span data-ttu-id="8412a-2853">mytentera</span><span class="sxs-lookup"><span data-stu-id="8412a-2853">mytentera</span></span>
- <span data-ttu-id="8412a-2854">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2854">malaysia identity card</span></span>
- <span data-ttu-id="8412a-2855">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2855">malaysian identity card</span></span>
- <span data-ttu-id="8412a-2856">nric</span><span class="sxs-lookup"><span data-stu-id="8412a-2856">nric</span></span>
- <span data-ttu-id="8412a-2857">個人識別カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2857">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="8412a-2858">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2858">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2859">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2859">Format</span></span>

<span data-ttu-id="8412a-2860">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2860">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2861">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2861">Pattern</span></span>

<span data-ttu-id="8412a-2862">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2862">8-9 digits:</span></span>
- <span data-ttu-id="8412a-2863">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2863">Three digits</span></span> 
- <span data-ttu-id="8412a-2864">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2864">A space (optional)</span></span> 
- <span data-ttu-id="8412a-2865">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2865">Three digits</span></span> 
- <span data-ttu-id="8412a-2866">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="8412a-2866">A space (optional)</span></span> 
- <span data-ttu-id="8412a-2867">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2867">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2868">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2868">Checksum</span></span>

<span data-ttu-id="8412a-2869">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2869">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2870">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2870">Definition</span></span>

<span data-ttu-id="8412a-2871">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2871">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2872">関数 Func_netherlands_bsn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2872">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2873">Keyword_netherlands_bsn からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2873">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="8412a-2874">関数 Func_eu_date2 は、日付を正しい日付形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2874">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="8412a-2875">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2875">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2876">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2876">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="8412a-2877">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="8412a-2877">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="8412a-2878">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="8412a-2878">Citizen service number</span></span> 
- <span data-ttu-id="8412a-2879">BSN</span><span class="sxs-lookup"><span data-stu-id="8412a-2879">BSN</span></span> 
- <span data-ttu-id="8412a-2880">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2880">Burgerservicenummer</span></span> 
- <span data-ttu-id="8412a-2881">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2881">Sofinummer</span></span> 
- <span data-ttu-id="8412a-2882">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2882">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="8412a-2883">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2883">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="8412a-2884">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2884">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2885">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2885">Format</span></span>

<span data-ttu-id="8412a-2886">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2886">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2887">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2887">Pattern</span></span>

<span data-ttu-id="8412a-2888">3文字 (大文字小文字を区別しない) スペース (省略可能)、4桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2888">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2889">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2889">Checksum</span></span>

<span data-ttu-id="8412a-2890">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2890">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2891">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2891">Definition</span></span>

<span data-ttu-id="8412a-2892">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2892">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2893">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2893">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2894">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2894">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="8412a-2895">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2895">The checksum passes.</span></span>

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

<span data-ttu-id="8412a-2896">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2896">Keywords</span></span>

<span data-ttu-id="8412a-2897">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="8412a-2897">Keyword_nz_terms</span></span>

- <span data-ttu-id="8412a-2898">NHI</span><span class="sxs-lookup"><span data-stu-id="8412a-2898">NHI</span></span> 
- <span data-ttu-id="8412a-2899">New Zealand</span><span class="sxs-lookup"><span data-stu-id="8412a-2899">New Zealand</span></span> 
- <span data-ttu-id="8412a-2900">正常性</span><span class="sxs-lookup"><span data-stu-id="8412a-2900">Health</span></span> 
- <span data-ttu-id="8412a-2901">処理</span><span class="sxs-lookup"><span data-stu-id="8412a-2901">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="8412a-2902">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2902">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2903">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2903">Format</span></span>

<span data-ttu-id="8412a-2904">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2905">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2905">Pattern</span></span>

<span data-ttu-id="8412a-2906">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2906">11 digits:</span></span>
- <span data-ttu-id="8412a-2907">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2907">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="8412a-2908">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="8412a-2908">Three-digit individual number</span></span> 
- <span data-ttu-id="8412a-2909">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="8412a-2909">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2910">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2910">Checksum</span></span>

<span data-ttu-id="8412a-2911">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2912">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2912">Definition</span></span>

<span data-ttu-id="8412a-2913">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2913">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2914">関数 Func_norway_id_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2914">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2915">Keyword_norway_id_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2915">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="8412a-2916">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2916">The checksum passes.</span></span>
- <span data-ttu-id="8412a-2917">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2917">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2918">関数 Func_norway_id_numbe は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2918">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2919">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2919">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2920">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2920">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="8412a-2921">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2921">Keyword_norway_id_number</span></span>

- <span data-ttu-id="8412a-2922">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="8412a-2922">Personal identification number</span></span>
- <span data-ttu-id="8412a-2923">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2923">Norwegian ID Number</span></span>
- <span data-ttu-id="8412a-2924">ID Number</span><span class="sxs-lookup"><span data-stu-id="8412a-2924">ID Number</span></span>
- <span data-ttu-id="8412a-2925">Fim</span><span class="sxs-lookup"><span data-stu-id="8412a-2925">Identification</span></span>
- <span data-ttu-id="8412a-2926">Personnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2926">Personnummer</span></span>
- <span data-ttu-id="8412a-2927">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="8412a-2927">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="8412a-2928">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-2928">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2929">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2929">Format</span></span>

<span data-ttu-id="8412a-2930">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2930">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2931">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2931">Pattern</span></span>

<span data-ttu-id="8412a-2932">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-2932">12 digits:</span></span>
- <span data-ttu-id="8412a-2933">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2933">Four digits</span></span> 
- <span data-ttu-id="8412a-2934">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-2934">A hyphen</span></span> 
- <span data-ttu-id="8412a-2935">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-2935">Seven digits</span></span> 
- <span data-ttu-id="8412a-2936">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-2936">A hyphen</span></span> 
- <span data-ttu-id="8412a-2937">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2937">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2938">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2938">Checksum</span></span>

<span data-ttu-id="8412a-2939">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-2939">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2940">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2940">Definition</span></span>

<span data-ttu-id="8412a-2941">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2942">正規表現 Regex_philippines_unified_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2942">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2943">Keyword_philippines_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-2943">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2944">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2944">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="8412a-2945">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="8412a-2945">Keyword_philippines_id</span></span>

- <span data-ttu-id="8412a-2946">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="8412a-2946">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="8412a-2947">UMID</span><span class="sxs-lookup"><span data-stu-id="8412a-2947">UMID</span></span> 
- <span data-ttu-id="8412a-2948">Identity Card</span><span class="sxs-lookup"><span data-stu-id="8412a-2948">Identity Card</span></span> 
- <span data-ttu-id="8412a-2949">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="8412a-2949">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="8412a-2950">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="8412a-2950">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2951">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2951">Format</span></span>

<span data-ttu-id="8412a-2952">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2952">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2953">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2953">Pattern</span></span>

<span data-ttu-id="8412a-2954">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2954">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2955">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2955">Checksum</span></span>

<span data-ttu-id="8412a-2956">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2956">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2957">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2957">Definition</span></span>

<span data-ttu-id="8412a-2958">DLP ポリシーは75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_polish_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2958">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="8412a-2959">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2959">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="8412a-2960">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2960">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2961">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2961">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="8412a-2962">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2962">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="8412a-2963">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="8412a-2963">Dowód osobisty</span></span>
- <span data-ttu-id="8412a-2964">特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="8412a-2964">Numer dowodu osobistego</span></span>
- <span data-ttu-id="8412a-2965">Nazwa i 特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="8412a-2965">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="8412a-2966">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="8412a-2966">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="8412a-2967">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="8412a-2967">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="8412a-2968">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="8412a-2968">Dowód Tożsamości</span></span>
- <span data-ttu-id="8412a-2969">dow.</span><span class="sxs-lookup"><span data-stu-id="8412a-2969">dow.</span></span> <span data-ttu-id="8412a-2970">hp-ux.</span><span class="sxs-lookup"><span data-stu-id="8412a-2970">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="8412a-2971">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="8412a-2971">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2972">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2972">Format</span></span>

<span data-ttu-id="8412a-2973">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2973">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2974">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2974">Pattern</span></span>

<span data-ttu-id="8412a-2975">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2975">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2976">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2976">Checksum</span></span>

<span data-ttu-id="8412a-2977">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2977">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2978">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2978">Definition</span></span>

<span data-ttu-id="8412a-2979">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2979">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2980">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2980">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2981">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2981">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="8412a-2982">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2982">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-2983">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2983">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="8412a-2984">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="8412a-2984">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="8412a-2985">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="8412a-2985">Nr PESEL</span></span>
- <span data-ttu-id="8412a-2986">PESEL</span><span class="sxs-lookup"><span data-stu-id="8412a-2986">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="8412a-2987">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="8412a-2987">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="8412a-2988">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-2988">Format</span></span>

<span data-ttu-id="8412a-2989">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2989">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-2990">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-2990">Pattern</span></span>

<span data-ttu-id="8412a-2991">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-2991">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-2992">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-2992">Checksum</span></span>

<span data-ttu-id="8412a-2993">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-2993">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-2994">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-2994">Definition</span></span>

<span data-ttu-id="8412a-2995">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-2995">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-2996">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2996">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-2997">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-2997">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="8412a-2998">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-2998">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-2999">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-2999">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="8412a-3000">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="8412a-3000">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="8412a-3001">特定の引数</span><span class="sxs-lookup"><span data-stu-id="8412a-3001">Numer paszportu</span></span>
- <span data-ttu-id="8412a-3002">Nr.</span><span class="sxs-lookup"><span data-stu-id="8412a-3002">Nr.</span></span> <span data-ttu-id="8412a-3003">大き zportu</span><span class="sxs-lookup"><span data-stu-id="8412a-3003">Paszportu</span></span>
- <span data-ttu-id="8412a-3004">があります</span><span class="sxs-lookup"><span data-stu-id="8412a-3004">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="8412a-3005">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3005">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3006">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3006">Format</span></span>

<span data-ttu-id="8412a-3007">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3007">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3008">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3008">Pattern</span></span>

<span data-ttu-id="8412a-3009">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3009">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3010">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3010">Checksum</span></span>

<span data-ttu-id="8412a-3011">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3011">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3012">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3012">Definition</span></span>

<span data-ttu-id="8412a-3013">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3013">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3014">正規表現 Regex_portugal_citizen_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3014">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3015">Keyword_portugal_citizen_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3015">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3016">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3016">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="8412a-3017">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="8412a-3017">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="8412a-3018">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="8412a-3018">Citizen Card</span></span>
- <span data-ttu-id="8412a-3019">National ID Card</span><span class="sxs-lookup"><span data-stu-id="8412a-3019">National ID Card</span></span>
- <span data-ttu-id="8412a-3020">CC</span><span class="sxs-lookup"><span data-stu-id="8412a-3020">CC</span></span>
- <span data-ttu-id="8412a-3021">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="8412a-3021">Cartão de Cidadão</span></span>
- <span data-ttu-id="8412a-3022">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="8412a-3022">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="8412a-3023">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="8412a-3023">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3024">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3024">Format</span></span>

<span data-ttu-id="8412a-3025">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3025">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3026">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3026">Pattern</span></span>

<span data-ttu-id="8412a-3027">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3027">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3028">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3028">Checksum</span></span>

<span data-ttu-id="8412a-3029">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3029">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3030">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3030">Definition</span></span>

<span data-ttu-id="8412a-3031">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3031">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3032">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3032">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3033">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3033">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3034">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3034">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="8412a-3035">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="8412a-3035">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="8412a-3036">Identification Card</span><span class="sxs-lookup"><span data-stu-id="8412a-3036">Identification Card</span></span> 
- <span data-ttu-id="8412a-3037">I card number</span><span class="sxs-lookup"><span data-stu-id="8412a-3037">I card number</span></span> 
- <span data-ttu-id="8412a-3038">ID number</span><span class="sxs-lookup"><span data-stu-id="8412a-3038">ID number</span></span> 
- <span data-ttu-id="8412a-3039">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="8412a-3039">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="8412a-3040">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3040">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3041">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3041">Format</span></span>

<span data-ttu-id="8412a-3042">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3042">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3043">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3043">Pattern</span></span>

- <span data-ttu-id="8412a-3044">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3044">Nine letters and digits:</span></span>
- <span data-ttu-id="8412a-3045">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-3045">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-3046">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-3046">Seven digits</span></span> 
- <span data-ttu-id="8412a-3047">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="8412a-3047">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3048">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3048">Checksum</span></span>

<span data-ttu-id="8412a-3049">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3049">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3050">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3050">Definition</span></span>

<span data-ttu-id="8412a-3051">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3051">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3052">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3052">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3053">Keyword_singapore_nric からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3053">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="8412a-3054">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3054">The checksum passes.</span></span>

<span data-ttu-id="8412a-3055">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3055">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3056">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3056">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3057">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3057">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3058">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3058">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="8412a-3059">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="8412a-3059">Keyword_singapore_nric</span></span>

- <span data-ttu-id="8412a-3060">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="8412a-3060">National Registration Identity Card</span></span> 
- <span data-ttu-id="8412a-3061">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3061">Identity Card Number</span></span> 
- <span data-ttu-id="8412a-3062">NRIC</span><span class="sxs-lookup"><span data-stu-id="8412a-3062">NRIC</span></span> 
- <span data-ttu-id="8412a-3063">IC</span><span class="sxs-lookup"><span data-stu-id="8412a-3063">IC</span></span> 
- <span data-ttu-id="8412a-3064">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3064">Foreign Identification Number</span></span> 
- <span data-ttu-id="8412a-3065">FIN</span><span class="sxs-lookup"><span data-stu-id="8412a-3065">FIN</span></span> 
- <span data-ttu-id="8412a-3066">身份证</span><span class="sxs-lookup"><span data-stu-id="8412a-3066">身份证</span></span> 
- <span data-ttu-id="8412a-3067">身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-3067">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="8412a-3068">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3068">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3069">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3069">Format</span></span>

<span data-ttu-id="8412a-3070">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3070">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3071">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3071">Pattern</span></span>

<span data-ttu-id="8412a-3072">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3072">13 digits:</span></span>
- <span data-ttu-id="8412a-3073">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-3073">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8412a-3074">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3074">Four digits</span></span> 
- <span data-ttu-id="8412a-3075">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="8412a-3075">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="8412a-3076">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="8412a-3076">The digit "8" or "9"</span></span> 
- <span data-ttu-id="8412a-3077">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3077">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3078">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3078">Checksum</span></span>

<span data-ttu-id="8412a-3079">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3079">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3080">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3080">Definition</span></span>

<span data-ttu-id="8412a-3081">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3082">関数 Func_south_africa_identification_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3082">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3083">Keyword_south_africa_identification_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3083">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="8412a-3084">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3084">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3085">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3085">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="8412a-3086">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="8412a-3086">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="8412a-3087">Identity card</span><span class="sxs-lookup"><span data-stu-id="8412a-3087">Identity card</span></span>
- <span data-ttu-id="8412a-3088">ID</span><span class="sxs-lookup"><span data-stu-id="8412a-3088">ID</span></span>
- <span data-ttu-id="8412a-3089">Fim</span><span class="sxs-lookup"><span data-stu-id="8412a-3089">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="8412a-3090">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3090">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3091">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3091">Format</span></span>

<span data-ttu-id="8412a-3092">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3092">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3093">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3093">Pattern</span></span>

<span data-ttu-id="8412a-3094">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3094">13 digits:</span></span>
- <span data-ttu-id="8412a-3095">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-3095">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8412a-3096">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="8412a-3096">A hyphen</span></span> 
- <span data-ttu-id="8412a-3097">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-3097">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="8412a-3098">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="8412a-3098">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="8412a-3099">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="8412a-3099">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="8412a-3100">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="8412a-3100">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3101">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3101">Checksum</span></span>

<span data-ttu-id="8412a-3102">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3102">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3103">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3103">Definition</span></span>

<span data-ttu-id="8412a-3104">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3104">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3105">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3105">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3106">Keyword_south_korea_resident_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3106">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="8412a-3107">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3107">The checksum passes.</span></span>

<span data-ttu-id="8412a-3108">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3109">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3109">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3110">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3110">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3111">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3111">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="8412a-3112">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="8412a-3112">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="8412a-3113">National ID card</span><span class="sxs-lookup"><span data-stu-id="8412a-3113">National ID card</span></span> 
- <span data-ttu-id="8412a-3114">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3114">Citizen's Registration Number</span></span> 
- <span data-ttu-id="8412a-3115">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="8412a-3115">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="8412a-3116">RRN</span><span class="sxs-lookup"><span data-stu-id="8412a-3116">RRN</span></span> 
- <span data-ttu-id="8412a-3117">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="8412a-3117">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="8412a-3118">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="8412a-3118">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3119">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3119">Format</span></span>

<span data-ttu-id="8412a-3120">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3120">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3121">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3121">Pattern</span></span>

<span data-ttu-id="8412a-3122">11-12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3122">11-12 digits:</span></span>
- <span data-ttu-id="8412a-3123">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3123">Two digits</span></span> 
- <span data-ttu-id="8412a-3124">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8412a-3124">A forward slash (optional)</span></span> 
- <span data-ttu-id="8412a-3125">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3125">7-8 digits</span></span> 
- <span data-ttu-id="8412a-3126">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8412a-3126">A forward slash (optional)</span></span> 
- <span data-ttu-id="8412a-3127">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3127">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3128">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3128">Checksum</span></span>

<span data-ttu-id="8412a-3129">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3129">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3130">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3130">Definition</span></span>

<span data-ttu-id="8412a-3131">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3132">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3132">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3133">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3133">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3134">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3134">Keywords</span></span>

<span data-ttu-id="8412a-3135">なし</span><span class="sxs-lookup"><span data-stu-id="8412a-3135">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="8412a-3136">SQL Server の接続文字列</span><span class="sxs-lookup"><span data-stu-id="8412a-3136">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3137">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3137">Format</span></span>

<span data-ttu-id="8412a-3138">文字列 "User Id"、"User ID"、"uid"、または "UserId" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="8412a-3138">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3139">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3139">Pattern</span></span>

- <span data-ttu-id="8412a-3140">文字列 "User Id"、"User ID"、"uid"、または "UserId"</span><span class="sxs-lookup"><span data-stu-id="8412a-3140">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="8412a-3141">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8412a-3141">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="8412a-3142">文字列 "Password" または "pwd" ("pwd" の前に小文字が含まれていません)</span><span class="sxs-lookup"><span data-stu-id="8412a-3142">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="8412a-3143">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-3143">An equal sign (=)</span></span>
- <span data-ttu-id="8412a-3144">ドル記号 ($)、パーセント記号 (%)、不等号 (>)、記号 (@)、二重引用符 (")、セミコロン (;)、左中かっこ ([)、左かっこ ({) のいずれでもない文字</span><span class="sxs-lookup"><span data-stu-id="8412a-3144">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="8412a-3145">セミコロンではない7-128 文字の任意の組み合わせ (;)、スラッシュ (/)、または引用符 (")</span><span class="sxs-lookup"><span data-stu-id="8412a-3145">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="8412a-3146">セミコロン (;)または二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="8412a-3146">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3147">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3147">Checksum</span></span>

<span data-ttu-id="8412a-3148">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3148">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3149">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3149">Definition</span></span>

<span data-ttu-id="8412a-3150">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3150">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3151">正規表現 CEP_Regex_SQLServerConnectionString は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3151">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3152">CEP_GlobalFilter からのキーワードが見つかり**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-3152">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="8412a-3153">正規表現 CEP_PasswordPlaceHolder は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-3153">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3154">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="8412a-3154">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3155">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3155">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="8412a-3156">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="8412a-3156">CEP_GlobalFilter</span></span>

- <span data-ttu-id="8412a-3157">パスワードの一部</span><span class="sxs-lookup"><span data-stu-id="8412a-3157">some-password</span></span>
- <span data-ttu-id="8412a-3158">パスワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3158">somepassword</span></span>
- <span data-ttu-id="8412a-3159">secretPassword</span><span class="sxs-lookup"><span data-stu-id="8412a-3159">secretPassword</span></span>
- <span data-ttu-id="8412a-3160">示す</span><span class="sxs-lookup"><span data-stu-id="8412a-3160">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="8412a-3161">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="8412a-3161">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="8412a-3162">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-3162">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-3163">Password または pwd の後に、0-2 スペース、等号 (=)、0-2 スペース、アスタリスク (\*)、または--</span><span class="sxs-lookup"><span data-stu-id="8412a-3163">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="8412a-3164">Password または pwd の後に、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3164">Password or pwd followed by:</span></span>
    - <span data-ttu-id="8412a-3165">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="8412a-3165">Equal sign (=)</span></span>
    - <span data-ttu-id="8412a-3166">不等号 (<)</span><span class="sxs-lookup"><span data-stu-id="8412a-3166">Less than symbol (<)</span></span>
    - <span data-ttu-id="8412a-3167">1-200 文字の大文字と小文字、数字、アスタリスク (\*)、ハイフン (-)、下線 (_)、または空白文字の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="8412a-3167">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="8412a-3168">不等号 (>)</span><span class="sxs-lookup"><span data-stu-id="8412a-3168">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="8412a-3169">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="8412a-3169">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="8412a-3170">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8412a-3170">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="8412a-3171">拠点</span><span class="sxs-lookup"><span data-stu-id="8412a-3171">contoso</span></span>
- <span data-ttu-id="8412a-3172">fabrikam</span><span class="sxs-lookup"><span data-stu-id="8412a-3172">fabrikam</span></span>
- <span data-ttu-id="8412a-3173">ノース</span><span class="sxs-lookup"><span data-stu-id="8412a-3173">northwind</span></span>
- <span data-ttu-id="8412a-3174">サンド</span><span class="sxs-lookup"><span data-stu-id="8412a-3174">sandbox</span></span>
- <span data-ttu-id="8412a-3175">onebox</span><span class="sxs-lookup"><span data-stu-id="8412a-3175">onebox</span></span>
- <span data-ttu-id="8412a-3176">localhost</span><span class="sxs-lookup"><span data-stu-id="8412a-3176">localhost</span></span>
- <span data-ttu-id="8412a-3177">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="8412a-3177">127.0.0.1</span></span>
- <span data-ttu-id="8412a-3178">testacs。</span><span class="sxs-lookup"><span data-stu-id="8412a-3178">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-3179">com</span><span class="sxs-lookup"><span data-stu-id="8412a-3179">com</span></span>
- <span data-ttu-id="8412a-3180">s-int。</span><span class="sxs-lookup"><span data-stu-id="8412a-3180">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="8412a-3181">ネット</span><span class="sxs-lookup"><span data-stu-id="8412a-3181">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="8412a-3182">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="8412a-3182">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3183">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3183">Format</span></span>

<span data-ttu-id="8412a-3184">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="8412a-3184">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3185">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3185">Pattern</span></span>

<span data-ttu-id="8412a-3186">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="8412a-3186">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="8412a-3187">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8412a-3187">2-4 digits (optional)</span></span> 
- <span data-ttu-id="8412a-3188">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3188">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="8412a-3189">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="8412a-3189">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="8412a-3190">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3190">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3191">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3191">Checksum</span></span>

<span data-ttu-id="8412a-3192">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3192">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3193">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3193">Definition</span></span>

<span data-ttu-id="8412a-3194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3194">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3195">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3195">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3196">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3196">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3197">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3197">Keywords</span></span>

<span data-ttu-id="8412a-3198">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3198">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="8412a-3199">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3199">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3200">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3200">Format</span></span>

<span data-ttu-id="8412a-3201">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3201">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3202">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3202">Pattern</span></span>

<span data-ttu-id="8412a-3203">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3203">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3204">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3204">Checksum</span></span>

<span data-ttu-id="8412a-3205">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3205">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3206">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3206">Definition</span></span>

<span data-ttu-id="8412a-3207">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3208">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3208">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3209">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-3209">One of the following is true:</span></span>
    - <span data-ttu-id="8412a-3210">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3210">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="8412a-3211">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3211">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3212">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3212">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="8412a-3213">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-3213">Keyword_sweden_passport</span></span>

- <span data-ttu-id="8412a-3214">visa requirements</span><span class="sxs-lookup"><span data-stu-id="8412a-3214">visa requirements</span></span> 
- <span data-ttu-id="8412a-3215">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="8412a-3215">Alien Registration Card</span></span> 
- <span data-ttu-id="8412a-3216">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="8412a-3216">Schengen visas</span></span> 
- <span data-ttu-id="8412a-3217">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="8412a-3217">Schengen visa</span></span> 
- <span data-ttu-id="8412a-3218">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="8412a-3218">Visa Processing</span></span> 
- <span data-ttu-id="8412a-3219">Visa Type</span><span class="sxs-lookup"><span data-stu-id="8412a-3219">Visa Type</span></span> 
- <span data-ttu-id="8412a-3220">Single Entry</span><span class="sxs-lookup"><span data-stu-id="8412a-3220">Single Entry</span></span> 
- <span data-ttu-id="8412a-3221">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="8412a-3221">Multiple Entry</span></span> 
- <span data-ttu-id="8412a-3222">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="8412a-3222">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="8412a-3223">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-3223">Keyword_passport</span></span>

- <span data-ttu-id="8412a-3224">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3224">Passport Number</span></span> 
- <span data-ttu-id="8412a-3225">Passport No</span><span class="sxs-lookup"><span data-stu-id="8412a-3225">Passport No</span></span> 
- <span data-ttu-id="8412a-3226">Passport #</span><span class="sxs-lookup"><span data-stu-id="8412a-3226">Passport #</span></span> 
- <span data-ttu-id="8412a-3227">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="8412a-3227">Passport#</span></span> 
- <span data-ttu-id="8412a-3228">PassportID</span><span class="sxs-lookup"><span data-stu-id="8412a-3228">PassportID</span></span> 
- <span data-ttu-id="8412a-3229">Passportno</span><span class="sxs-lookup"><span data-stu-id="8412a-3229">Passportno</span></span> 
- <span data-ttu-id="8412a-3230">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-3230">passportnumber</span></span> 
- <span data-ttu-id="8412a-3231">パスポート</span><span class="sxs-lookup"><span data-stu-id="8412a-3231">パスポート</span></span> 
- <span data-ttu-id="8412a-3232">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3232">パスポート番号</span></span> 
- <span data-ttu-id="8412a-3233">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8412a-3233">パスポートのNum</span></span> 
- <span data-ttu-id="8412a-3234">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="8412a-3234">パスポート＃</span></span> 
- <span data-ttu-id="8412a-3235">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8412a-3235">Numéro de passeport</span></span> 
- <span data-ttu-id="8412a-3236">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8412a-3236">Passeport n °</span></span> 
- <span data-ttu-id="8412a-3237">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8412a-3237">Passeport Non</span></span> 
- <span data-ttu-id="8412a-3238">Passeport #</span><span class="sxs-lookup"><span data-stu-id="8412a-3238">Passeport #</span></span> 
- <span data-ttu-id="8412a-3239">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8412a-3239">Passeport#</span></span> 
- <span data-ttu-id="8412a-3240">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8412a-3240">PasseportNon</span></span> 
- <span data-ttu-id="8412a-3241">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8412a-3241">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="8412a-3242">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="8412a-3242">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3243">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3243">Format</span></span>

<span data-ttu-id="8412a-3244">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3244">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3245">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3245">Pattern</span></span>

<span data-ttu-id="8412a-3246">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3246">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="8412a-3247">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="8412a-3247">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-3248">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="8412a-3248">An optional space</span></span> 
- <span data-ttu-id="8412a-3249">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="8412a-3249">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="8412a-3250">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="8412a-3250">An optional space</span></span> 
- <span data-ttu-id="8412a-3251">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="8412a-3251">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3252">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3252">Checksum</span></span>

<span data-ttu-id="8412a-3253">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3253">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3254">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3254">Definition</span></span>

<span data-ttu-id="8412a-3255">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3256">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3256">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3257">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3257">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3258">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3258">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="8412a-3259">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="8412a-3259">Keyword_swift</span></span>

- <span data-ttu-id="8412a-3260">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="8412a-3260">international organization for standardization 9362</span></span> 
- <span data-ttu-id="8412a-3261">iso 9362</span><span class="sxs-lookup"><span data-stu-id="8412a-3261">iso 9362</span></span> 
- <span data-ttu-id="8412a-3262">iso9362</span><span class="sxs-lookup"><span data-stu-id="8412a-3262">iso9362</span></span> 
- <span data-ttu-id="8412a-3263">実現\#</span><span class="sxs-lookup"><span data-stu-id="8412a-3263">swift\#</span></span> 
- <span data-ttu-id="8412a-3264">swiftcode</span><span class="sxs-lookup"><span data-stu-id="8412a-3264">swiftcode</span></span> 
- <span data-ttu-id="8412a-3265">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-3265">swiftnumber</span></span> 
- <span data-ttu-id="8412a-3266">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-3266">swiftroutingnumber</span></span> 
- <span data-ttu-id="8412a-3267">swift code</span><span class="sxs-lookup"><span data-stu-id="8412a-3267">swift code</span></span> 
- <span data-ttu-id="8412a-3268">swift number #</span><span class="sxs-lookup"><span data-stu-id="8412a-3268">swift number #</span></span> 
- <span data-ttu-id="8412a-3269">swift routing number</span><span class="sxs-lookup"><span data-stu-id="8412a-3269">swift routing number</span></span> 
- <span data-ttu-id="8412a-3270">bic number</span><span class="sxs-lookup"><span data-stu-id="8412a-3270">bic number</span></span> 
- <span data-ttu-id="8412a-3271">bic code</span><span class="sxs-lookup"><span data-stu-id="8412a-3271">bic code</span></span> 
- <span data-ttu-id="8412a-3272">bic\#</span><span class="sxs-lookup"><span data-stu-id="8412a-3272">bic \#</span></span> 
- <span data-ttu-id="8412a-3273">bic\#</span><span class="sxs-lookup"><span data-stu-id="8412a-3273">bic\#</span></span> 
- <span data-ttu-id="8412a-3274">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="8412a-3274">bank identifier code</span></span> 
- <span data-ttu-id="8412a-3275">標準化9362</span><span class="sxs-lookup"><span data-stu-id="8412a-3275">標準化9362</span></span> 
- <span data-ttu-id="8412a-3276">迅速＃</span><span class="sxs-lookup"><span data-stu-id="8412a-3276">迅速＃</span></span> 
- <span data-ttu-id="8412a-3277">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="8412a-3277">SWIFTコード</span></span> 
- <span data-ttu-id="8412a-3278">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3278">SWIFT番号</span></span> 
- <span data-ttu-id="8412a-3279">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3279">迅速なルーティング番号</span></span> 
- <span data-ttu-id="8412a-3280">BIC番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3280">BIC番号</span></span> 
- <span data-ttu-id="8412a-3281">BICコード</span><span class="sxs-lookup"><span data-stu-id="8412a-3281">BICコード</span></span> 
- <span data-ttu-id="8412a-3282">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="8412a-3282">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="8412a-3283">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="8412a-3283">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="8412a-3284">rapide\#</span><span class="sxs-lookup"><span data-stu-id="8412a-3284">rapide \#</span></span> 
- <span data-ttu-id="8412a-3285">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="8412a-3285">code SWIFT</span></span> 
- <span data-ttu-id="8412a-3286">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="8412a-3286">le numéro de swift</span></span> 
- <span data-ttu-id="8412a-3287">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="8412a-3287">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="8412a-3288">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="8412a-3288">le numéro BIC</span></span> 
- <span data-ttu-id="8412a-3289">\#BIC</span><span class="sxs-lookup"><span data-stu-id="8412a-3289">\# BIC</span></span> 
- <span data-ttu-id="8412a-3290">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="8412a-3290">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="8412a-3291">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="8412a-3291">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3292">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3292">Format</span></span>

<span data-ttu-id="8412a-3293">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3293">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3294">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3294">Pattern</span></span>

<span data-ttu-id="8412a-3295">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3295">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="8412a-3296">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="8412a-3296">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="8412a-3297">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="8412a-3297">The digit "1" or "2"</span></span> 
- <span data-ttu-id="8412a-3298">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3298">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3299">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3299">Checksum</span></span>

<span data-ttu-id="8412a-3300">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3300">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3301">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3301">Definition</span></span>

<span data-ttu-id="8412a-3302">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3302">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3303">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3303">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3304">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3304">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="8412a-3305">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3305">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3306">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3306">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="8412a-3307">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="8412a-3307">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="8412a-3308">身份證字號</span><span class="sxs-lookup"><span data-stu-id="8412a-3308">身份證字號</span></span> 
- <span data-ttu-id="8412a-3309">身份證</span><span class="sxs-lookup"><span data-stu-id="8412a-3309">身份證</span></span> 
- <span data-ttu-id="8412a-3310">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="8412a-3310">身份證號碼</span></span> 
- <span data-ttu-id="8412a-3311">身份證號</span><span class="sxs-lookup"><span data-stu-id="8412a-3311">身份證號</span></span> 
- <span data-ttu-id="8412a-3312">身分證字號</span><span class="sxs-lookup"><span data-stu-id="8412a-3312">身分證字號</span></span> 
- <span data-ttu-id="8412a-3313">身分證</span><span class="sxs-lookup"><span data-stu-id="8412a-3313">身分證</span></span> 
- <span data-ttu-id="8412a-3314">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="8412a-3314">身分證號碼</span></span> 
- <span data-ttu-id="8412a-3315">身份證號</span><span class="sxs-lookup"><span data-stu-id="8412a-3315">身份證號</span></span> 
- <span data-ttu-id="8412a-3316">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="8412a-3316">身分證統一編號</span></span> 
- <span data-ttu-id="8412a-3317">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="8412a-3317">國民身分證統一編號</span></span> 
- <span data-ttu-id="8412a-3318">簽名</span><span class="sxs-lookup"><span data-stu-id="8412a-3318">簽名</span></span> 
- <span data-ttu-id="8412a-3319">蓋章</span><span class="sxs-lookup"><span data-stu-id="8412a-3319">蓋章</span></span> 
- <span data-ttu-id="8412a-3320">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="8412a-3320">簽名或蓋章</span></span> 
- <span data-ttu-id="8412a-3321">簽章</span><span class="sxs-lookup"><span data-stu-id="8412a-3321">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="8412a-3322">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3322">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3323">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3323">Format</span></span>

- <span data-ttu-id="8412a-3324">バイオメトリックパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3324">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="8412a-3325">バイオメトリクスでないパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3325">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3326">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3326">Pattern</span></span>
<span data-ttu-id="8412a-3327">バイオメトリックパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="8412a-3327">Biometric passport number:</span></span>
- <span data-ttu-id="8412a-3328">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="8412a-3328">The digit "3"</span></span> 
- <span data-ttu-id="8412a-3329">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3329">Eight digits</span></span>

<span data-ttu-id="8412a-3330">バイオメトリクスではないパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="8412a-3330">Non-biometric passport number:</span></span>
- <span data-ttu-id="8412a-3331">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3331">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3332">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3332">Checksum</span></span>

<span data-ttu-id="8412a-3333">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3333">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3334">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3334">Definition</span></span>

<span data-ttu-id="8412a-3335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3336">正規表現 Regex_taiwan_passport は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3336">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3337">Keyword_taiwan_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3337">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3338">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3338">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="8412a-3339">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-3339">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="8412a-3340">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="8412a-3340">ROC passport number</span></span> 
- <span data-ttu-id="8412a-3341">Passport number</span><span class="sxs-lookup"><span data-stu-id="8412a-3341">Passport number</span></span> 
- <span data-ttu-id="8412a-3342">Passport no</span><span class="sxs-lookup"><span data-stu-id="8412a-3342">Passport no</span></span> 
- <span data-ttu-id="8412a-3343">Passport Num</span><span class="sxs-lookup"><span data-stu-id="8412a-3343">Passport Num</span></span> 
- <span data-ttu-id="8412a-3344">Passport #</span><span class="sxs-lookup"><span data-stu-id="8412a-3344">Passport #</span></span> 
- <span data-ttu-id="8412a-3345">护照</span><span class="sxs-lookup"><span data-stu-id="8412a-3345">护照</span></span> 
- <span data-ttu-id="8412a-3346">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="8412a-3346">中華民國護照</span></span> 
- <span data-ttu-id="8412a-3347">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="8412a-3347">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="8412a-3348">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3348">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3349">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3349">Format</span></span>

<span data-ttu-id="8412a-3350">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3350">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3351">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3351">Pattern</span></span>

<span data-ttu-id="8412a-3352">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3352">10 letters and digits:</span></span>
- <span data-ttu-id="8412a-3353">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="8412a-3353">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="8412a-3354">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3354">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3355">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3355">Checksum</span></span>

<span data-ttu-id="8412a-3356">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3356">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3357">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3357">Definition</span></span>

<span data-ttu-id="8412a-3358">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3358">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3359">正規表現 Regex_taiwan_resident_certificate は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3359">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3360">Keyword_taiwan_resident_certificate からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3360">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3361">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3361">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="8412a-3362">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="8412a-3362">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="8412a-3363">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="8412a-3363">Resident Certificate</span></span> 
- <span data-ttu-id="8412a-3364">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="8412a-3364">Resident Cert</span></span> 
- <span data-ttu-id="8412a-3365">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="8412a-3365">Resident Cert.</span></span> 
- <span data-ttu-id="8412a-3366">Identification card</span><span class="sxs-lookup"><span data-stu-id="8412a-3366">Identification card</span></span> 
- <span data-ttu-id="8412a-3367">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="8412a-3367">Alien Resident Certificate</span></span> 
- <span data-ttu-id="8412a-3368">ARC</span><span class="sxs-lookup"><span data-stu-id="8412a-3368">ARC</span></span> 
- <span data-ttu-id="8412a-3369">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="8412a-3369">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="8412a-3370">TARC</span><span class="sxs-lookup"><span data-stu-id="8412a-3370">TARC</span></span> 
- <span data-ttu-id="8412a-3371">居留證</span><span class="sxs-lookup"><span data-stu-id="8412a-3371">居留證</span></span> 
- <span data-ttu-id="8412a-3372">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="8412a-3372">外僑居留證</span></span> 
- <span data-ttu-id="8412a-3373">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="8412a-3373">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="8412a-3374">タイ語の母集団識別コード</span><span class="sxs-lookup"><span data-stu-id="8412a-3374">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3375">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3375">Format</span></span>

<span data-ttu-id="8412a-3376">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3376">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3377">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3377">Pattern</span></span>

<span data-ttu-id="8412a-3378">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3378">13 digits:</span></span>
- <span data-ttu-id="8412a-3379">最初の桁が0または9ではない</span><span class="sxs-lookup"><span data-stu-id="8412a-3379">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="8412a-3380">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3380">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3381">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3381">Checksum</span></span>

<span data-ttu-id="8412a-3382">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3382">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3383">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3383">Definition</span></span>

<span data-ttu-id="8412a-3384">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3384">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3385">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3385">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3386">Keyword_Thai_Citizen_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3386">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="8412a-3387">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3387">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3388">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3388">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3389">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3389">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="8412a-3390">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="8412a-3390">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="8412a-3391">ID Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3391">ID Number</span></span>
- <span data-ttu-id="8412a-3392">識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3392">Identification Number</span></span>
- <span data-ttu-id="8412a-3393">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8412a-3393">บัตรประชาชน</span></span>
- <span data-ttu-id="8412a-3394">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8412a-3394">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="8412a-3395">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8412a-3395">บัตรประชาชน</span></span>
- <span data-ttu-id="8412a-3396">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8412a-3396">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="8412a-3397">トルコの国の識別番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3397">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3398">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3398">Format</span></span>

<span data-ttu-id="8412a-3399">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3399">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3400">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3400">Pattern</span></span>

<span data-ttu-id="8412a-3401">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3401">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3402">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3402">Checksum</span></span>

<span data-ttu-id="8412a-3403">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3403">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3404">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3404">Definition</span></span>

<span data-ttu-id="8412a-3405">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3405">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3406">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3406">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3407">Keyword_Turkish_National_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3407">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="8412a-3408">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3408">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3409">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3409">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3410">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3410">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="8412a-3411">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="8412a-3411">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="8412a-3412">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="8412a-3412">TC Kimlik No</span></span>
- <span data-ttu-id="8412a-3413">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="8412a-3413">TC Kimlik numarası</span></span>
- <span data-ttu-id="8412a-3414">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="8412a-3414">Vatandaşlık numarası</span></span>
- <span data-ttu-id="8412a-3415">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="8412a-3415">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="8412a-p142">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3418">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3418">Format</span></span>

<span data-ttu-id="8412a-3419">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3419">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3420">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3420">Pattern</span></span>

<span data-ttu-id="8412a-3421">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3421">18 letters and digits:</span></span>
- <span data-ttu-id="8412a-3422">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="8412a-3422">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="8412a-3423">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3423">One digit</span></span> 
- <span data-ttu-id="8412a-3424">誕生日の日付形式 MMDDY の5桁の数字 (7 文字目は、driver が女性の場合は50にインクリメントされます。つまり、01から12の代わりに51から 62)</span><span class="sxs-lookup"><span data-stu-id="8412a-3424">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="8412a-3425">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="8412a-3425">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="8412a-3426">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3426">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3427">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3427">Checksum</span></span>

<span data-ttu-id="8412a-3428">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3428">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3429">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3429">Definition</span></span>

<span data-ttu-id="8412a-3430">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3430">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3431">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3431">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3432">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3432">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="8412a-3433">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3433">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3434">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3434">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="8412a-3435">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8412a-3435">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="8412a-3436">DVLA</span><span class="sxs-lookup"><span data-stu-id="8412a-3436">DVLA</span></span> 
- <span data-ttu-id="8412a-3437">light vans</span><span class="sxs-lookup"><span data-stu-id="8412a-3437">light vans</span></span> 
- <span data-ttu-id="8412a-3438">quadbikes</span><span class="sxs-lookup"><span data-stu-id="8412a-3438">quadbikes</span></span> 
- <span data-ttu-id="8412a-3439">motor cars</span><span class="sxs-lookup"><span data-stu-id="8412a-3439">motor cars</span></span> 
- <span data-ttu-id="8412a-3440">125cc</span><span class="sxs-lookup"><span data-stu-id="8412a-3440">125cc</span></span> 
- <span data-ttu-id="8412a-3441">sidecar</span><span class="sxs-lookup"><span data-stu-id="8412a-3441">sidecar</span></span> 
- <span data-ttu-id="8412a-3442">tricycles</span><span class="sxs-lookup"><span data-stu-id="8412a-3442">tricycles</span></span> 
- <span data-ttu-id="8412a-3443">motorcycles</span><span class="sxs-lookup"><span data-stu-id="8412a-3443">motorcycles</span></span> 
- <span data-ttu-id="8412a-3444">photocard licence</span><span class="sxs-lookup"><span data-stu-id="8412a-3444">photocard licence</span></span> 
- <span data-ttu-id="8412a-3445">learner drivers</span><span class="sxs-lookup"><span data-stu-id="8412a-3445">learner drivers</span></span> 
- <span data-ttu-id="8412a-3446">licence holder</span><span class="sxs-lookup"><span data-stu-id="8412a-3446">licence holder</span></span> 
- <span data-ttu-id="8412a-3447">licence holders</span><span class="sxs-lookup"><span data-stu-id="8412a-3447">licence holders</span></span> 
- <span data-ttu-id="8412a-3448">driving licences</span><span class="sxs-lookup"><span data-stu-id="8412a-3448">driving licences</span></span> 
- <span data-ttu-id="8412a-3449">driving licence</span><span class="sxs-lookup"><span data-stu-id="8412a-3449">driving licence</span></span> 
- <span data-ttu-id="8412a-3450">dual control car</span><span class="sxs-lookup"><span data-stu-id="8412a-3450">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="8412a-p143">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="8412a-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3453">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3453">Format</span></span>

<span data-ttu-id="8412a-3454">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3454">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3455">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3455">Pattern</span></span>

<span data-ttu-id="8412a-3456">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3456">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3457">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3457">Checksum</span></span>

<span data-ttu-id="8412a-3458">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3459">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3459">Definition</span></span>

<span data-ttu-id="8412a-3460">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3460">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3461">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3461">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3462">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3462">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3463">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3463">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="8412a-3464">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="8412a-3464">Keyword_uk_electoral</span></span>

- <span data-ttu-id="8412a-3465">council nomination</span><span class="sxs-lookup"><span data-stu-id="8412a-3465">council nomination</span></span> 
- <span data-ttu-id="8412a-3466">nomination form</span><span class="sxs-lookup"><span data-stu-id="8412a-3466">nomination form</span></span> 
- <span data-ttu-id="8412a-3467">electoral register</span><span class="sxs-lookup"><span data-stu-id="8412a-3467">electoral register</span></span> 
- <span data-ttu-id="8412a-3468">electoral roll</span><span class="sxs-lookup"><span data-stu-id="8412a-3468">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="8412a-p144">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="8412a-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3471">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3471">Format</span></span>

<span data-ttu-id="8412a-3472">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3472">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3473">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3473">Pattern</span></span>

<span data-ttu-id="8412a-3474">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="8412a-3474">10-17 digits:</span></span>
- <span data-ttu-id="8412a-3475">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3475">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="8412a-3476">スペース</span><span class="sxs-lookup"><span data-stu-id="8412a-3476">A space</span></span> 
- <span data-ttu-id="8412a-3477">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3477">Three digits</span></span> 
- <span data-ttu-id="8412a-3478">スペース</span><span class="sxs-lookup"><span data-stu-id="8412a-3478">A space</span></span> 
- <span data-ttu-id="8412a-3479">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3479">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3480">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3480">Checksum</span></span>

<span data-ttu-id="8412a-3481">はい</span><span class="sxs-lookup"><span data-stu-id="8412a-3481">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3482">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3482">Definition</span></span>

<span data-ttu-id="8412a-3483">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3483">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3484">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3484">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3485">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-3485">One of the following is true:</span></span>
    - <span data-ttu-id="8412a-3486">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3486">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="8412a-3487">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3487">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="8412a-3488">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3488">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="8412a-3489">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="8412a-3489">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3490">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3490">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="8412a-3491">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="8412a-3491">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="8412a-3492">national health service</span><span class="sxs-lookup"><span data-stu-id="8412a-3492">national health service</span></span> 
- <span data-ttu-id="8412a-3493">nhs</span><span class="sxs-lookup"><span data-stu-id="8412a-3493">nhs</span></span> 
- <span data-ttu-id="8412a-3494">health services authority</span><span class="sxs-lookup"><span data-stu-id="8412a-3494">health services authority</span></span> 
- <span data-ttu-id="8412a-3495">health authority</span><span class="sxs-lookup"><span data-stu-id="8412a-3495">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="8412a-3496">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="8412a-3496">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="8412a-3497">patient id</span><span class="sxs-lookup"><span data-stu-id="8412a-3497">patient id</span></span> 
- <span data-ttu-id="8412a-3498">patient identification</span><span class="sxs-lookup"><span data-stu-id="8412a-3498">patient identification</span></span> 
- <span data-ttu-id="8412a-3499">patient no</span><span class="sxs-lookup"><span data-stu-id="8412a-3499">patient no</span></span> 
- <span data-ttu-id="8412a-3500">patient number</span><span class="sxs-lookup"><span data-stu-id="8412a-3500">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="8412a-3501">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="8412a-3501">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="8412a-3502">GP</span><span class="sxs-lookup"><span data-stu-id="8412a-3502">GP</span></span> 
- <span data-ttu-id="8412a-3503">DOB</span><span class="sxs-lookup"><span data-stu-id="8412a-3503">DOB</span></span> 
- <span data-ttu-id="8412a-3504">D.</span><span class="sxs-lookup"><span data-stu-id="8412a-3504">D.O.B</span></span> 
- <span data-ttu-id="8412a-3505">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="8412a-3505">Date of Birth</span></span> 
- <span data-ttu-id="8412a-3506">Birth Date</span><span class="sxs-lookup"><span data-stu-id="8412a-3506">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="8412a-p145">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="8412a-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3509">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3509">Format</span></span>

<span data-ttu-id="8412a-3510">スペースまたはダッシュで区切られた7文字または9文字</span><span class="sxs-lookup"><span data-stu-id="8412a-3510">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3511">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3511">Pattern</span></span>

<span data-ttu-id="8412a-3512">次の2つのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8412a-3512">Two possible patterns:</span></span>

- <span data-ttu-id="8412a-3513">2文字 (有効な NINOs このプレフィックスには特定の文字のみを使用します。このパターンは、大文字小文字を区別しません)。</span><span class="sxs-lookup"><span data-stu-id="8412a-3513">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="8412a-3514">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3514">Six digits</span></span>
- <span data-ttu-id="8412a-3515">「A」、「B」、「C」、または「d」 (プレフィックスと同様に、サフィックスには特定の文字のみ指定できます。大文字と小文字は区別されません)</span><span class="sxs-lookup"><span data-stu-id="8412a-3515">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="8412a-3516">OR</span><span class="sxs-lookup"><span data-stu-id="8412a-3516">OR</span></span>

- <span data-ttu-id="8412a-3517">2文字</span><span class="sxs-lookup"><span data-stu-id="8412a-3517">Two letters</span></span>
- <span data-ttu-id="8412a-3518">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-3518">A space or dash</span></span>
- <span data-ttu-id="8412a-3519">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3519">Two digits</span></span>
- <span data-ttu-id="8412a-3520">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-3520">A space or dash</span></span>
- <span data-ttu-id="8412a-3521">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3521">Two digits</span></span>
- <span data-ttu-id="8412a-3522">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-3522">A space or dash</span></span>
- <span data-ttu-id="8412a-3523">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3523">Two digits</span></span>
- <span data-ttu-id="8412a-3524">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-3524">A space or dash</span></span>
- <span data-ttu-id="8412a-3525">' A '、' B '、' C '、または ' d ' のどちらか</span><span class="sxs-lookup"><span data-stu-id="8412a-3525">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3526">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3526">Checksum</span></span>

<span data-ttu-id="8412a-3527">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3527">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3528">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3528">Definition</span></span>

<span data-ttu-id="8412a-3529">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3530">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3530">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3531">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3531">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="8412a-3532">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3532">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3533">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3533">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3534">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="8412a-3534">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3535">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3535">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="8412a-3536">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="8412a-3536">Keyword_uk_nino</span></span>

- <span data-ttu-id="8412a-3537">national insurance number</span><span class="sxs-lookup"><span data-stu-id="8412a-3537">national insurance number</span></span> 
- <span data-ttu-id="8412a-3538">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="8412a-3538">national insurance contributions</span></span> 
- <span data-ttu-id="8412a-3539">protection act</span><span class="sxs-lookup"><span data-stu-id="8412a-3539">protection act</span></span> 
- <span data-ttu-id="8412a-3540">金</span><span class="sxs-lookup"><span data-stu-id="8412a-3540">insurance</span></span> 
- <span data-ttu-id="8412a-3541">social security number</span><span class="sxs-lookup"><span data-stu-id="8412a-3541">social security number</span></span> 
- <span data-ttu-id="8412a-3542">insurance application</span><span class="sxs-lookup"><span data-stu-id="8412a-3542">insurance application</span></span> 
- <span data-ttu-id="8412a-3543">medical application</span><span class="sxs-lookup"><span data-stu-id="8412a-3543">medical application</span></span> 
- <span data-ttu-id="8412a-3544">social insurance</span><span class="sxs-lookup"><span data-stu-id="8412a-3544">social insurance</span></span> 
- <span data-ttu-id="8412a-3545">medical attention</span><span class="sxs-lookup"><span data-stu-id="8412a-3545">medical attention</span></span> 
- <span data-ttu-id="8412a-3546">social security</span><span class="sxs-lookup"><span data-stu-id="8412a-3546">social security</span></span> 
- <span data-ttu-id="8412a-3547">great britain</span><span class="sxs-lookup"><span data-stu-id="8412a-3547">great britain</span></span> 
- <span data-ttu-id="8412a-3548">金</span><span class="sxs-lookup"><span data-stu-id="8412a-3548">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="8412a-p146">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3551">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3551">Format</span></span>

<span data-ttu-id="8412a-3552">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3552">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3553">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3553">Pattern</span></span>

<span data-ttu-id="8412a-3554">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3554">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3555">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3555">Checksum</span></span>

<span data-ttu-id="8412a-3556">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3556">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3557">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3557">Definition</span></span>

<span data-ttu-id="8412a-3558">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3558">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3559">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3559">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3560">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3560">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3561">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3561">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="8412a-3562">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8412a-3562">Keyword_passport</span></span>

- <span data-ttu-id="8412a-3563">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3563">Passport Number</span></span> 
- <span data-ttu-id="8412a-3564">Passport No</span><span class="sxs-lookup"><span data-stu-id="8412a-3564">Passport No</span></span> 
- <span data-ttu-id="8412a-3565">Passport #</span><span class="sxs-lookup"><span data-stu-id="8412a-3565">Passport #</span></span> 
- <span data-ttu-id="8412a-3566">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="8412a-3566">Passport#</span></span> 
- <span data-ttu-id="8412a-3567">PassportID</span><span class="sxs-lookup"><span data-stu-id="8412a-3567">PassportID</span></span> 
- <span data-ttu-id="8412a-3568">Passportno</span><span class="sxs-lookup"><span data-stu-id="8412a-3568">Passportno</span></span> 
- <span data-ttu-id="8412a-3569">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8412a-3569">passportnumber</span></span> 
- <span data-ttu-id="8412a-3570">パスポート</span><span class="sxs-lookup"><span data-stu-id="8412a-3570">パスポート</span></span> 
- <span data-ttu-id="8412a-3571">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3571">パスポート番号</span></span> 
- <span data-ttu-id="8412a-3572">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8412a-3572">パスポートのNum</span></span> 
- <span data-ttu-id="8412a-3573">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="8412a-3573">パスポート＃</span></span> 
- <span data-ttu-id="8412a-3574">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8412a-3574">Numéro de passeport</span></span> 
- <span data-ttu-id="8412a-3575">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8412a-3575">Passeport n °</span></span> 
- <span data-ttu-id="8412a-3576">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8412a-3576">Passeport Non</span></span> 
- <span data-ttu-id="8412a-3577">Passeport #</span><span class="sxs-lookup"><span data-stu-id="8412a-3577">Passeport #</span></span> 
- <span data-ttu-id="8412a-3578">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8412a-3578">Passeport#</span></span> 
- <span data-ttu-id="8412a-3579">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8412a-3579">PasseportNon</span></span> 
- <span data-ttu-id="8412a-3580">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8412a-3580">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="8412a-3581">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3581">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3582">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3582">Format</span></span>

<span data-ttu-id="8412a-3583">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3583">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3584">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3584">Pattern</span></span>

<span data-ttu-id="8412a-3585">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3585">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3586">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3586">Checksum</span></span>

<span data-ttu-id="8412a-3587">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3587">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3588">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3588">Definition</span></span>

<span data-ttu-id="8412a-3589">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3589">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3590">正規表現 Regex_usa_bank_account_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3590">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3591">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3591">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3592">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3592">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="8412a-3593">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="8412a-3593">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="8412a-3594">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3594">Checking Account Number</span></span> 
- <span data-ttu-id="8412a-3595">Checking Account</span><span class="sxs-lookup"><span data-stu-id="8412a-3595">Checking Account</span></span> 
- <span data-ttu-id="8412a-3596">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-3596">Checking Account #</span></span> 
- <span data-ttu-id="8412a-3597">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3597">Checking Acct Number</span></span> 
- <span data-ttu-id="8412a-3598">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-3598">Checking Acct #</span></span> 
- <span data-ttu-id="8412a-3599">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3599">Checking Acct No.</span></span> 
- <span data-ttu-id="8412a-3600">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3600">Checking Account No.</span></span> 
- <span data-ttu-id="8412a-3601">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3601">Bank Account Number</span></span> 
- <span data-ttu-id="8412a-3602">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-3602">Bank Account #</span></span> 
- <span data-ttu-id="8412a-3603">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3603">Bank Acct Number</span></span> 
- <span data-ttu-id="8412a-3604">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-3604">Bank Acct #</span></span> 
- <span data-ttu-id="8412a-3605">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3605">Bank Acct No.</span></span> 
- <span data-ttu-id="8412a-3606">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3606">Bank Account No.</span></span> 
- <span data-ttu-id="8412a-3607">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3607">Savings Account Number</span></span> 
- <span data-ttu-id="8412a-3608">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="8412a-3608">Savings Account.</span></span> 
- <span data-ttu-id="8412a-3609">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-3609">Savings Account #</span></span> 
- <span data-ttu-id="8412a-3610">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3610">Savings Acct Number</span></span> 
- <span data-ttu-id="8412a-3611">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-3611">Savings Acct #</span></span> 
- <span data-ttu-id="8412a-3612">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3612">Savings Acct No.</span></span> 
- <span data-ttu-id="8412a-3613">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3613">Savings Account No.</span></span> 
- <span data-ttu-id="8412a-3614">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3614">Debit Account Number</span></span> 
- <span data-ttu-id="8412a-3615">Debit Account</span><span class="sxs-lookup"><span data-stu-id="8412a-3615">Debit Account</span></span> 
- <span data-ttu-id="8412a-3616">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="8412a-3616">Debit Account #</span></span> 
- <span data-ttu-id="8412a-3617">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="8412a-3617">Debit Acct Number</span></span> 
- <span data-ttu-id="8412a-3618">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="8412a-3618">Debit Acct #</span></span> 
- <span data-ttu-id="8412a-3619">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3619">Debit Acct No.</span></span> 
- <span data-ttu-id="8412a-3620">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="8412a-3620">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="8412a-3621">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8412a-3621">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3622">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3622">Format</span></span>

<span data-ttu-id="8412a-3623">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="8412a-3623">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3624">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3624">Pattern</span></span>

<span data-ttu-id="8412a-3625">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="8412a-3625">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="8412a-3626">Ddd ddd ddd のような形式の9桁の数字は一致します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3626">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="8412a-3627">Ddddddddd のように9桁の数字は一致しません。</span><span class="sxs-lookup"><span data-stu-id="8412a-3627">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3628">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3628">Checksum</span></span>

<span data-ttu-id="8412a-3629">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3629">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3630">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3630">Definition</span></span>

<span data-ttu-id="8412a-3631">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3631">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3632">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3632">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3633">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3633">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="8412a-3634">Keyword_us_drivers_license からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="8412a-3634">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="8412a-3635">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3635">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3636">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3636">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3637">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3637">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="8412a-3638">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3638">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="8412a-3639">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="8412a-3639">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
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
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8412a-3640">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3640">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="8412a-3641">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="8412a-3641">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="8412a-3642">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-3642">DL</span></span> 
- <span data-ttu-id="8412a-3643">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-3643">DLS</span></span> 
- <span data-ttu-id="8412a-3644">CDL</span><span class="sxs-lookup"><span data-stu-id="8412a-3644">CDL</span></span> 
- <span data-ttu-id="8412a-3645">CDLS</span><span class="sxs-lookup"><span data-stu-id="8412a-3645">CDLS</span></span> 
- <span data-ttu-id="8412a-3646">ID</span><span class="sxs-lookup"><span data-stu-id="8412a-3646">ID</span></span> 
- <span data-ttu-id="8412a-3647">Rid</span><span class="sxs-lookup"><span data-stu-id="8412a-3647">IDs</span></span> 
- <span data-ttu-id="8412a-3648">DL#</span><span class="sxs-lookup"><span data-stu-id="8412a-3648">DL#</span></span> 
- <span data-ttu-id="8412a-3649">DL#</span><span class="sxs-lookup"><span data-stu-id="8412a-3649">DLS#</span></span> 
- <span data-ttu-id="8412a-3650">CDL#</span><span class="sxs-lookup"><span data-stu-id="8412a-3650">CDL#</span></span> 
- <span data-ttu-id="8412a-3651">CDLS#</span><span class="sxs-lookup"><span data-stu-id="8412a-3651">CDLS#</span></span> 
- <span data-ttu-id="8412a-3652">RID#</span><span class="sxs-lookup"><span data-stu-id="8412a-3652">ID#</span></span>
- <span data-ttu-id="8412a-3653">Rid#</span><span class="sxs-lookup"><span data-stu-id="8412a-3653">IDs#</span></span> 
- <span data-ttu-id="8412a-3654">ID number</span><span class="sxs-lookup"><span data-stu-id="8412a-3654">ID number</span></span> 
- <span data-ttu-id="8412a-3655">ID numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-3655">ID numbers</span></span> 
- <span data-ttu-id="8412a-3656">そして</span><span class="sxs-lookup"><span data-stu-id="8412a-3656">LIC</span></span> 
- <span data-ttu-id="8412a-3657">そして#</span><span class="sxs-lookup"><span data-stu-id="8412a-3657">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="8412a-3658">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8412a-3658">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="8412a-3659">DriverLic</span><span class="sxs-lookup"><span data-stu-id="8412a-3659">DriverLic</span></span> 
- <span data-ttu-id="8412a-3660">DriverLics</span><span class="sxs-lookup"><span data-stu-id="8412a-3660">DriverLics</span></span> 
- <span data-ttu-id="8412a-3661">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="8412a-3661">DriverLicense</span></span> 
- <span data-ttu-id="8412a-3662">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="8412a-3662">DriverLicenses</span></span> 
- <span data-ttu-id="8412a-3663">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-3663">Driver Lic</span></span> 
- <span data-ttu-id="8412a-3664">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-3664">Driver Lics</span></span> 
- <span data-ttu-id="8412a-3665">Driver License</span><span class="sxs-lookup"><span data-stu-id="8412a-3665">Driver License</span></span> 
- <span data-ttu-id="8412a-3666">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-3666">Driver Licenses</span></span> 
- <span data-ttu-id="8412a-3667">DriversLic</span><span class="sxs-lookup"><span data-stu-id="8412a-3667">DriversLic</span></span> 
- <span data-ttu-id="8412a-3668">DriversLics</span><span class="sxs-lookup"><span data-stu-id="8412a-3668">DriversLics</span></span> 
- <span data-ttu-id="8412a-3669">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="8412a-3669">DriversLicense</span></span> 
- <span data-ttu-id="8412a-3670">このライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-3670">DriversLicenses</span></span> 
- <span data-ttu-id="8412a-3671">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-3671">Drivers Lic</span></span> 
- <span data-ttu-id="8412a-3672">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-3672">Drivers Lics</span></span> 
- <span data-ttu-id="8412a-3673">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8412a-3673">Drivers License</span></span> 
- <span data-ttu-id="8412a-3674">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-3674">Drivers Licenses</span></span> 
- <span data-ttu-id="8412a-3675">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-3675">Driver'Lic</span></span> 
- <span data-ttu-id="8412a-3676">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-3676">Driver'Lics</span></span> 
- <span data-ttu-id="8412a-3677">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-3677">Driver'License</span></span> 
- <span data-ttu-id="8412a-3678">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-3678">Driver'Licenses</span></span> 
- <span data-ttu-id="8412a-3679">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-3679">Driver' Lic</span></span> 
- <span data-ttu-id="8412a-3680">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-3680">Driver' Lics</span></span> 
- <span data-ttu-id="8412a-3681">Driver' License</span><span class="sxs-lookup"><span data-stu-id="8412a-3681">Driver' License</span></span> 
- <span data-ttu-id="8412a-3682">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-3682">Driver' Licenses</span></span>
- <span data-ttu-id="8412a-3683">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="8412a-3683">Driver'sLic</span></span> 
- <span data-ttu-id="8412a-3684">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="8412a-3684">Driver'sLics</span></span> 
- <span data-ttu-id="8412a-3685">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-3685">Driver'sLicense</span></span> 
- <span data-ttu-id="8412a-3686">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-3686">Driver'sLicenses</span></span> 
- <span data-ttu-id="8412a-3687">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8412a-3687">Driver's Lic</span></span> 
- <span data-ttu-id="8412a-3688">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="8412a-3688">Driver's Lics</span></span> 
- <span data-ttu-id="8412a-3689">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8412a-3689">Driver's License</span></span> 
- <span data-ttu-id="8412a-3690">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8412a-3690">Driver's Licenses</span></span> 
- <span data-ttu-id="8412a-3691">identification number</span><span class="sxs-lookup"><span data-stu-id="8412a-3691">identification number</span></span> 
- <span data-ttu-id="8412a-3692">identification numbers</span><span class="sxs-lookup"><span data-stu-id="8412a-3692">identification numbers</span></span> 
- <span data-ttu-id="8412a-3693">identification #</span><span class="sxs-lookup"><span data-stu-id="8412a-3693">identification #</span></span> 
- <span data-ttu-id="8412a-3694">id card</span><span class="sxs-lookup"><span data-stu-id="8412a-3694">id card</span></span> 
- <span data-ttu-id="8412a-3695">id cards</span><span class="sxs-lookup"><span data-stu-id="8412a-3695">id cards</span></span> 
- <span data-ttu-id="8412a-3696">identification card</span><span class="sxs-lookup"><span data-stu-id="8412a-3696">identification card</span></span> 
- <span data-ttu-id="8412a-3697">identification cards</span><span class="sxs-lookup"><span data-stu-id="8412a-3697">identification cards</span></span> 
- <span data-ttu-id="8412a-3698">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3698">DriverLic#</span></span> 
- <span data-ttu-id="8412a-3699">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3699">DriverLics#</span></span> 
- <span data-ttu-id="8412a-3700">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="8412a-3700">DriverLicense#</span></span> 
- <span data-ttu-id="8412a-3701">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-3701">DriverLicenses#</span></span> 
- <span data-ttu-id="8412a-3702">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3702">Driver Lic#</span></span> 
- <span data-ttu-id="8412a-3703">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3703">Driver Lics#</span></span> 
- <span data-ttu-id="8412a-3704">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8412a-3704">Driver License#</span></span> 
- <span data-ttu-id="8412a-3705">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-3705">Driver Licenses#</span></span> 
- <span data-ttu-id="8412a-3706">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3706">DriversLic#</span></span> 
- <span data-ttu-id="8412a-3707">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3707">DriversLics#</span></span> 
- <span data-ttu-id="8412a-3708">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="8412a-3708">DriversLicense#</span></span> 
- <span data-ttu-id="8412a-3709">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-3709">DriversLicenses#</span></span> 
- <span data-ttu-id="8412a-3710">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3710">Drivers Lic#</span></span> 
- <span data-ttu-id="8412a-3711">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3711">Drivers Lics#</span></span> 
- <span data-ttu-id="8412a-3712">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="8412a-3712">Drivers License#</span></span> 
- <span data-ttu-id="8412a-3713">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-3713">Drivers Licenses#</span></span> 
- <span data-ttu-id="8412a-3714">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3714">Driver'Lic#</span></span> 
- <span data-ttu-id="8412a-3715">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3715">Driver'Lics#</span></span> 
- <span data-ttu-id="8412a-3716">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-3716">Driver'License#</span></span> 
- <span data-ttu-id="8412a-3717">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-3717">Driver'Licenses#</span></span> 
- <span data-ttu-id="8412a-3718">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3718">Driver' Lic#</span></span> 
- <span data-ttu-id="8412a-3719">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3719">Driver' Lics#</span></span> 
- <span data-ttu-id="8412a-3720">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="8412a-3720">Driver' License#</span></span> 
- <span data-ttu-id="8412a-3721">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-3721">Driver' Licenses#</span></span> 
- <span data-ttu-id="8412a-3722">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3722">Driver'sLic#</span></span> 
- <span data-ttu-id="8412a-3723">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3723">Driver'sLics#</span></span> 
- <span data-ttu-id="8412a-3724">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-3724">Driver'sLicense#</span></span> 
- <span data-ttu-id="8412a-3725">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="8412a-3725">Driver'sLicenses#</span></span> 
- <span data-ttu-id="8412a-3726">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="8412a-3726">Driver's Lic#</span></span> 
- <span data-ttu-id="8412a-3727">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="8412a-3727">Driver's Lics#</span></span> 
- <span data-ttu-id="8412a-3728">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="8412a-3728">Driver's License#</span></span> 
- <span data-ttu-id="8412a-3729">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="8412a-3729">Driver's Licenses#</span></span> 
- <span data-ttu-id="8412a-3730">id card#</span><span class="sxs-lookup"><span data-stu-id="8412a-3730">id card#</span></span> 
- <span data-ttu-id="8412a-3731">id cards#</span><span class="sxs-lookup"><span data-stu-id="8412a-3731">id cards#</span></span> 
- <span data-ttu-id="8412a-3732">identification card#</span><span class="sxs-lookup"><span data-stu-id="8412a-3732">identification card#</span></span> 
- <span data-ttu-id="8412a-3733">identification cards#</span><span class="sxs-lookup"><span data-stu-id="8412a-3733">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="8412a-3734">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="8412a-3734">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="8412a-3735">州の略号 (たとえば、"NY")</span><span class="sxs-lookup"><span data-stu-id="8412a-3735">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="8412a-3736">州の名前 (たとえば、"New York")</span><span class="sxs-lookup"><span data-stu-id="8412a-3736">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="8412a-3737">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="8412a-3737">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3738">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3738">Format</span></span>

<span data-ttu-id="8412a-3739">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="8412a-3739">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3740">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3740">Pattern</span></span>

<span data-ttu-id="8412a-3741">さ</span><span class="sxs-lookup"><span data-stu-id="8412a-3741">Formatted:</span></span>
- <span data-ttu-id="8412a-3742">数字「9」</span><span class="sxs-lookup"><span data-stu-id="8412a-3742">The digit "9"</span></span> 
- <span data-ttu-id="8412a-3743">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3743">Two digits</span></span> 
- <span data-ttu-id="8412a-3744">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-3744">A space or dash</span></span> 
- <span data-ttu-id="8412a-3745">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="8412a-3745">A "7" or "8"</span></span> 
- <span data-ttu-id="8412a-3746">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3746">A digit</span></span> 
- <span data-ttu-id="8412a-3747">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="8412a-3747">A space, or dash</span></span> 
- <span data-ttu-id="8412a-3748">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3748">Four digits</span></span>

<span data-ttu-id="8412a-3749">なし</span><span class="sxs-lookup"><span data-stu-id="8412a-3749">Unformatted:</span></span>
- <span data-ttu-id="8412a-3750">数字「9」</span><span class="sxs-lookup"><span data-stu-id="8412a-3750">The digit "9"</span></span> 
- <span data-ttu-id="8412a-3751">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3751">Two digits</span></span> 
- <span data-ttu-id="8412a-3752">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="8412a-3752">A "7" or "8"</span></span> 
- <span data-ttu-id="8412a-3753">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3753">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3754">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3754">Checksum</span></span>

<span data-ttu-id="8412a-3755">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3755">No</span></span>

### <a name="definition"></a><span data-ttu-id="8412a-3756">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3756">Definition</span></span>

<span data-ttu-id="8412a-3757">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3757">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3758">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3758">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3759">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-3759">At least one of the following is true:</span></span>
    - <span data-ttu-id="8412a-3760">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3760">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="8412a-3761">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3761">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="8412a-3762">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3762">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="8412a-3763">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3763">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="8412a-3764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3765">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3765">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3766">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="8412a-3766">At least one of the following is true:</span></span>
    - <span data-ttu-id="8412a-3767">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3767">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="8412a-3768">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3768">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="8412a-3769">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3769">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="8412a-3770">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3770">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="8412a-3771">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="8412a-3771">Keyword_itin</span></span>

- <span data-ttu-id="8412a-3772">納税</span><span class="sxs-lookup"><span data-stu-id="8412a-3772">taxpayer</span></span> 
- <span data-ttu-id="8412a-3773">tax id</span><span class="sxs-lookup"><span data-stu-id="8412a-3773">tax id</span></span> 
- <span data-ttu-id="8412a-3774">tax identification</span><span class="sxs-lookup"><span data-stu-id="8412a-3774">tax identification</span></span> 
- <span data-ttu-id="8412a-3775">itin</span><span class="sxs-lookup"><span data-stu-id="8412a-3775">itin</span></span> 
- <span data-ttu-id="8412a-3776">ssn</span><span class="sxs-lookup"><span data-stu-id="8412a-3776">ssn</span></span> 
- <span data-ttu-id="8412a-3777">は</span><span class="sxs-lookup"><span data-stu-id="8412a-3777">tin</span></span> 
- <span data-ttu-id="8412a-3778">social security</span><span class="sxs-lookup"><span data-stu-id="8412a-3778">social security</span></span> 
- <span data-ttu-id="8412a-3779">tax payer</span><span class="sxs-lookup"><span data-stu-id="8412a-3779">tax payer</span></span> 
- <span data-ttu-id="8412a-3780">itins</span><span class="sxs-lookup"><span data-stu-id="8412a-3780">itins</span></span> 
- <span data-ttu-id="8412a-3781">taxid</span><span class="sxs-lookup"><span data-stu-id="8412a-3781">taxid</span></span> 
- <span data-ttu-id="8412a-3782">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="8412a-3782">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="8412a-3783">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="8412a-3783">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="8412a-3784">ライセンス</span><span class="sxs-lookup"><span data-stu-id="8412a-3784">License</span></span> 
- <span data-ttu-id="8412a-3785">DL</span><span class="sxs-lookup"><span data-stu-id="8412a-3785">DL</span></span> 
- <span data-ttu-id="8412a-3786">DOB</span><span class="sxs-lookup"><span data-stu-id="8412a-3786">DOB</span></span> 
- <span data-ttu-id="8412a-3787">誕生日</span><span class="sxs-lookup"><span data-stu-id="8412a-3787">Birthdate</span></span> 
- <span data-ttu-id="8412a-3788">Birthday</span><span class="sxs-lookup"><span data-stu-id="8412a-3788">Birthday</span></span> 
- <span data-ttu-id="8412a-3789">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="8412a-3789">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="8412a-3790">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="8412a-3790">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="8412a-3791">Format</span><span class="sxs-lookup"><span data-stu-id="8412a-3791">Format</span></span>

<span data-ttu-id="8412a-3792">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="8412a-3792">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="8412a-3793">2011より前に発行された場合、SSN の書式には、特定の範囲内にある特定の範囲内にある必要があり、チェックサムがないという厳密な形式があります。</span><span class="sxs-lookup"><span data-stu-id="8412a-3793">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="8412a-3794">パターン</span><span class="sxs-lookup"><span data-stu-id="8412a-3794">Pattern</span></span>

<span data-ttu-id="8412a-3795">次の4つの異なるパターンで SSNs を検索する4つの関数があります。</span><span class="sxs-lookup"><span data-stu-id="8412a-3795">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="8412a-3796">Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="8412a-3796">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="8412a-3797">Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="8412a-3797">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="8412a-3798">Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="8412a-3798">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="8412a-3799">Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="8412a-3799">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="8412a-3800">Checksum</span><span class="sxs-lookup"><span data-stu-id="8412a-3800">Checksum</span></span>

<span data-ttu-id="8412a-3801">いいえ</span><span class="sxs-lookup"><span data-stu-id="8412a-3801">No</span></span>


### <a name="definition"></a><span data-ttu-id="8412a-3802">定義</span><span class="sxs-lookup"><span data-stu-id="8412a-3802">Definition</span></span>

<span data-ttu-id="8412a-3803">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3803">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3804">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3804">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3805">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3805">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="8412a-3806">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3807">関数 Func_unformatted_ssn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3807">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3808">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3808">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="8412a-3809">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3809">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3810">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3810">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3811">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3811">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="8412a-3812">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="8412a-3812">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8412a-3813">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3813">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8412a-3814">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="8412a-3814">A keyword from Keyword_ssn is found.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="8412a-3815">キーワード</span><span class="sxs-lookup"><span data-stu-id="8412a-3815">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="8412a-3816">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="8412a-3816">Keyword_ssn</span></span>

- <span data-ttu-id="8412a-3817">Social Security</span><span class="sxs-lookup"><span data-stu-id="8412a-3817">Social Security</span></span> 
- <span data-ttu-id="8412a-3818">Social Security#</span><span class="sxs-lookup"><span data-stu-id="8412a-3818">Social Security#</span></span> 
- <span data-ttu-id="8412a-3819">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="8412a-3819">Soc Sec</span></span> 
- <span data-ttu-id="8412a-3820">SSN</span><span class="sxs-lookup"><span data-stu-id="8412a-3820">SSN</span></span> 
- <span data-ttu-id="8412a-3821">SSN</span><span class="sxs-lookup"><span data-stu-id="8412a-3821">SSNS</span></span> 
- <span data-ttu-id="8412a-3822">SSN#</span><span class="sxs-lookup"><span data-stu-id="8412a-3822">SSN#</span></span> 
- <span data-ttu-id="8412a-3823">秒#</span><span class="sxs-lookup"><span data-stu-id="8412a-3823">SS#</span></span> 
- <span data-ttu-id="8412a-3824">SSID</span><span class="sxs-lookup"><span data-stu-id="8412a-3824">SSID</span></span> 
   
