---
title: EU 社会保障番号または同等の ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号または同等の ID の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085869"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="14487-104">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="14487-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="14487-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号 (SSN) または同等の ID 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="14487-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="14487-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="14487-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="14487-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="14487-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="14487-108">Format</span><span class="sxs-lookup"><span data-stu-id="14487-108">Format</span></span>

<span data-ttu-id="14487-109">指定した形式の10桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-110">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-110">Pattern</span></span>

<span data-ttu-id="14487-111">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="14487-111">10 digits:</span></span>
  
-  <span data-ttu-id="14487-112">シリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="14487-113">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="14487-113">One check digit</span></span>
    
- <span data-ttu-id="14487-114">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="14487-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="14487-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-115">Checksum</span></span>

<span data-ttu-id="14487-116">はい</span><span class="sxs-lookup"><span data-stu-id="14487-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-117">定義</span><span class="sxs-lookup"><span data-stu-id="14487-117">Definition</span></span>

<span data-ttu-id="14487-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-119">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-120">From `Keywords_austria_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-122">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-123">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-125">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="14487-125">social security no</span></span>
  
<span data-ttu-id="14487-126">social security number</span><span class="sxs-lookup"><span data-stu-id="14487-126">social security number</span></span>
  
<span data-ttu-id="14487-127">social security code</span><span class="sxs-lookup"><span data-stu-id="14487-127">social security code</span></span>
  
<span data-ttu-id="14487-128">保険番号</span><span class="sxs-lookup"><span data-stu-id="14487-128">insurance number</span></span>
  
<span data-ttu-id="14487-129">オーストリア ssn</span><span class="sxs-lookup"><span data-stu-id="14487-129">austrian ssn</span></span>
  
<span data-ttu-id="14487-130">ssn#</span><span class="sxs-lookup"><span data-stu-id="14487-130">ssn#</span></span>
  
<span data-ttu-id="14487-131">ssn</span><span class="sxs-lookup"><span data-stu-id="14487-131">ssn</span></span>
  
<span data-ttu-id="14487-132">保険コード</span><span class="sxs-lookup"><span data-stu-id="14487-132">insurance code</span></span>
  
<span data-ttu-id="14487-133">保険コード#</span><span class="sxs-lookup"><span data-stu-id="14487-133">insurance code#</span></span>
  
<span data-ttu-id="14487-134">"社会 securityno"#</span><span class="sxs-lookup"><span data-stu-id="14487-134">socialsecurityno#</span></span>
  
<span data-ttu-id="14487-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="14487-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="14487-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="14487-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="14487-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="14487-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="14487-138">ベルギー</span><span class="sxs-lookup"><span data-stu-id="14487-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="14487-139">Format</span><span class="sxs-lookup"><span data-stu-id="14487-139">Format</span></span>

<span data-ttu-id="14487-140">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="14487-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-141">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-141">Pattern</span></span>

<span data-ttu-id="14487-142">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="14487-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-143">Checksum</span></span>

<span data-ttu-id="14487-144">はい</span><span class="sxs-lookup"><span data-stu-id="14487-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-145">定義</span><span class="sxs-lookup"><span data-stu-id="14487-145">Definition</span></span>

<span data-ttu-id="14487-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-147">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-148">From `Keywords_belgium_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-149">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-150">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-151">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-153">ベルギーの国番号</span><span class="sxs-lookup"><span data-stu-id="14487-153">belgian national number</span></span>
  
<span data-ttu-id="14487-154">国番号</span><span class="sxs-lookup"><span data-stu-id="14487-154">national number</span></span>
  
<span data-ttu-id="14487-155">social security number</span><span class="sxs-lookup"><span data-stu-id="14487-155">social security number</span></span>
  
<span data-ttu-id="14487-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-156">nationalnumber#</span></span>
  
<span data-ttu-id="14487-157">ssn#</span><span class="sxs-lookup"><span data-stu-id="14487-157">ssn#</span></span>
  
<span data-ttu-id="14487-158">ssn</span><span class="sxs-lookup"><span data-stu-id="14487-158">ssn</span></span>
  
<span data-ttu-id="14487-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="14487-159">nationalnumber</span></span>
  
<span data-ttu-id="14487-160">bnn#</span><span class="sxs-lookup"><span data-stu-id="14487-160">bnn#</span></span>
  
<span data-ttu-id="14487-161">bnn</span><span class="sxs-lookup"><span data-stu-id="14487-161">bnn</span></span>
  
<span data-ttu-id="14487-162">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-162">personal id number</span></span>
  
<span data-ttu-id="14487-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-163">personalidnumber#</span></span>
  
<span data-ttu-id="14487-164">numéro national</span><span class="sxs-lookup"><span data-stu-id="14487-164">numéro national</span></span>
  
<span data-ttu-id="14487-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="14487-165">numéro de sécurité</span></span>
  
<span data-ttu-id="14487-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="14487-166">numéro d'assuré</span></span>
  
<span data-ttu-id="14487-167">identifiant national</span><span class="sxs-lookup"><span data-stu-id="14487-167">identifiant national</span></span>
  
<span data-ttu-id="14487-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="14487-168">identifiantnational#</span></span>
  
<span data-ttu-id="14487-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="14487-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="14487-170">クロアチア</span><span class="sxs-lookup"><span data-stu-id="14487-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="14487-171">Format</span><span class="sxs-lookup"><span data-stu-id="14487-171">Format</span></span>

<span data-ttu-id="14487-172">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-173">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-173">Pattern</span></span>

 <span data-ttu-id="14487-174">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="14487-174">11 digits:</span></span> 
  
-  <span data-ttu-id="14487-175">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-175">Ten digits</span></span> 
    
- <span data-ttu-id="14487-176">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="14487-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="14487-177">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-177">Checksum</span></span>

<span data-ttu-id="14487-178">はい</span><span class="sxs-lookup"><span data-stu-id="14487-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-179">定義</span><span class="sxs-lookup"><span data-stu-id="14487-179">Definition</span></span>

<span data-ttu-id="14487-180">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-181">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-182">From `Keywords_croatia_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-183">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-184">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-185">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-187">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="14487-187">personal identification number</span></span>
  
<span data-ttu-id="14487-188">マスター市民番号</span><span class="sxs-lookup"><span data-stu-id="14487-188">master citizen number</span></span>
  
<span data-ttu-id="14487-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="14487-189">national identification number</span></span>
  
<span data-ttu-id="14487-190">social security number</span><span class="sxs-lookup"><span data-stu-id="14487-190">social security number</span></span>
  
<span data-ttu-id="14487-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-191">nationalnumber#</span></span>
  
<span data-ttu-id="14487-192">ssn#</span><span class="sxs-lookup"><span data-stu-id="14487-192">ssn#</span></span>
  
<span data-ttu-id="14487-193">ssn</span><span class="sxs-lookup"><span data-stu-id="14487-193">ssn</span></span>
  
<span data-ttu-id="14487-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="14487-194">nationalnumber</span></span>
  
<span data-ttu-id="14487-195">bnn#</span><span class="sxs-lookup"><span data-stu-id="14487-195">bnn#</span></span>
  
<span data-ttu-id="14487-196">bnn</span><span class="sxs-lookup"><span data-stu-id="14487-196">bnn</span></span>
  
<span data-ttu-id="14487-197">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-197">personal id number</span></span>
  
<span data-ttu-id="14487-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-198">personalidnumber#</span></span>
  
<span data-ttu-id="14487-199">oib</span><span class="sxs-lookup"><span data-stu-id="14487-199">oib</span></span>
  
<span data-ttu-id="14487-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="14487-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="14487-201">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="14487-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="14487-202">Format</span><span class="sxs-lookup"><span data-stu-id="14487-202">Format</span></span>

<span data-ttu-id="14487-203">指定したパターンの10桁の数字と円記号</span><span class="sxs-lookup"><span data-stu-id="14487-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-204">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-204">Pattern</span></span>

<span data-ttu-id="14487-205">10桁の数字と円記号:</span><span class="sxs-lookup"><span data-stu-id="14487-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="14487-206">誕生日に対応する6桁の数字 (YYMMDD という):</span><span class="sxs-lookup"><span data-stu-id="14487-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="14487-207">円記号</span><span class="sxs-lookup"><span data-stu-id="14487-207">A backslash</span></span>
    
- <span data-ttu-id="14487-208">同じ日付で個人の出生を区切るシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="14487-209">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="14487-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="14487-210">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-210">Checksum</span></span>

<span data-ttu-id="14487-211">はい</span><span class="sxs-lookup"><span data-stu-id="14487-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-212">定義</span><span class="sxs-lookup"><span data-stu-id="14487-212">Definition</span></span>

<span data-ttu-id="14487-213">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-214">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-215">From `Keywords_czech_republic_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-216">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-217">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-218">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-220">出生地番号</span><span class="sxs-lookup"><span data-stu-id="14487-220">birth number</span></span>
  
<span data-ttu-id="14487-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="14487-221">national identification number</span></span>
  
<span data-ttu-id="14487-222">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="14487-222">personal identification number</span></span>
  
<span data-ttu-id="14487-223">social security number</span><span class="sxs-lookup"><span data-stu-id="14487-223">social security number</span></span>
  
<span data-ttu-id="14487-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-224">nationalnumber#</span></span>
  
<span data-ttu-id="14487-225">ssn#</span><span class="sxs-lookup"><span data-stu-id="14487-225">ssn#</span></span>
  
<span data-ttu-id="14487-226">ssn</span><span class="sxs-lookup"><span data-stu-id="14487-226">ssn</span></span>
  
<span data-ttu-id="14487-227">国番号</span><span class="sxs-lookup"><span data-stu-id="14487-227">national number</span></span>
  
<span data-ttu-id="14487-228">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-228">personal id number</span></span>
  
<span data-ttu-id="14487-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-229">personalidnumber#</span></span>
  
<span data-ttu-id="14487-230">rč</span><span class="sxs-lookup"><span data-stu-id="14487-230">rč</span></span>
  
<span data-ttu-id="14487-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="14487-231">rodné číslo</span></span>
  
<span data-ttu-id="14487-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="14487-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="14487-233">デンマーク</span><span class="sxs-lookup"><span data-stu-id="14487-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="14487-234">Format</span><span class="sxs-lookup"><span data-stu-id="14487-234">Format</span></span>

<span data-ttu-id="14487-235">指定したパターンの10桁の数字とハイフン</span><span class="sxs-lookup"><span data-stu-id="14487-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-236">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-236">Pattern</span></span>

<span data-ttu-id="14487-237">10桁の数字とハイフン:</span><span class="sxs-lookup"><span data-stu-id="14487-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="14487-238">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="14487-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="14487-239">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="14487-239">A hyphen</span></span>
    
- <span data-ttu-id="14487-240">シーケンス番号に対応する4桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="14487-241">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-241">Checksum</span></span>

<span data-ttu-id="14487-242">はい</span><span class="sxs-lookup"><span data-stu-id="14487-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-243">定義</span><span class="sxs-lookup"><span data-stu-id="14487-243">Definition</span></span>

<span data-ttu-id="14487-244">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-245">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-246">From `Keywords_denmark_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-247">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-248">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-249">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-251">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="14487-251">personal identification number</span></span>
  
<span data-ttu-id="14487-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="14487-252">national identification number</span></span>
  
<span data-ttu-id="14487-253">social security number</span><span class="sxs-lookup"><span data-stu-id="14487-253">social security number</span></span>
  
<span data-ttu-id="14487-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-254">nationalnumber#</span></span>
  
<span data-ttu-id="14487-255">ssn#</span><span class="sxs-lookup"><span data-stu-id="14487-255">ssn#</span></span>
  
<span data-ttu-id="14487-256">ssn</span><span class="sxs-lookup"><span data-stu-id="14487-256">ssn</span></span>
  
<span data-ttu-id="14487-257">国番号</span><span class="sxs-lookup"><span data-stu-id="14487-257">national number</span></span>
  
<span data-ttu-id="14487-258">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-258">personal id number</span></span>
  
<span data-ttu-id="14487-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-259">personalidnumber#</span></span>
  
<span data-ttu-id="14487-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="14487-260">cpr-nummer</span></span>
  
<span data-ttu-id="14487-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="14487-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="14487-262">フィンランド</span><span class="sxs-lookup"><span data-stu-id="14487-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="14487-263">Format</span><span class="sxs-lookup"><span data-stu-id="14487-263">Format</span></span>

<span data-ttu-id="14487-264">指定した書式の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="14487-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-265">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-265">Pattern</span></span>

<span data-ttu-id="14487-266">指定した形式の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="14487-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="14487-267">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-267">Six digits</span></span> 
    
- <span data-ttu-id="14487-268">次のいずれかのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="14487-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="14487-269">プラス記号</span><span class="sxs-lookup"><span data-stu-id="14487-269">Plus symbol</span></span>
    
  - <span data-ttu-id="14487-270">マイナス記号</span><span class="sxs-lookup"><span data-stu-id="14487-270">Minus symbol</span></span>
    
  - <span data-ttu-id="14487-271">文字 "A" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="14487-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="14487-272">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-272">Three digits</span></span>
    
- <span data-ttu-id="14487-273">1文字または1桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="14487-274">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-274">Checksum</span></span>

<span data-ttu-id="14487-275">はい</span><span class="sxs-lookup"><span data-stu-id="14487-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-276">定義</span><span class="sxs-lookup"><span data-stu-id="14487-276">Definition</span></span>

<span data-ttu-id="14487-277">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-278">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-279">From `Keywords_finland_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-280">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-281">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-282">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-284">identification number</span><span class="sxs-lookup"><span data-stu-id="14487-284">identification number</span></span>
  
<span data-ttu-id="14487-285">個人 id</span><span class="sxs-lookup"><span data-stu-id="14487-285">personal id</span></span>
  
<span data-ttu-id="14487-286">id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-286">identity number</span></span>
  
<span data-ttu-id="14487-287">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-287">finnish national id number</span></span>
  
<span data-ttu-id="14487-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="14487-288">personalidnumber#</span></span>
  
<span data-ttu-id="14487-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="14487-289">national identification number</span></span>
  
<span data-ttu-id="14487-290">id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-290">id number</span></span>
  
<span data-ttu-id="14487-291">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-291">national id no.</span></span>
  
<span data-ttu-id="14487-292">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-292">national id number</span></span>
  
<span data-ttu-id="14487-293">id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-293">id no</span></span>
  
<span data-ttu-id="14487-294">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="14487-294">tunnistenumero</span></span>
  
<span data-ttu-id="14487-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="14487-295">henkilötunnus</span></span>
  
<span data-ttu-id="14487-296">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="14487-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="14487-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="14487-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="14487-298">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="14487-298">identiteetti numero</span></span>
  
<span data-ttu-id="14487-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="14487-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="14487-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="14487-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="14487-301">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="14487-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="14487-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="14487-302">tunnusnumero</span></span>
  
<span data-ttu-id="14487-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="14487-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="14487-304">hetu</span><span class="sxs-lookup"><span data-stu-id="14487-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="14487-305">フランス</span><span class="sxs-lookup"><span data-stu-id="14487-305">France</span></span>

<span data-ttu-id="14487-306">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの社会保障番号 (insee)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14487-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="14487-307">ドイツ</span><span class="sxs-lookup"><span data-stu-id="14487-307">Germany</span></span>

<span data-ttu-id="14487-308">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの Id カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14487-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="14487-309">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="14487-309">Greece</span></span>

<span data-ttu-id="14487-310">詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14487-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="14487-311">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="14487-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="14487-312">Format</span><span class="sxs-lookup"><span data-stu-id="14487-312">Format</span></span>

<span data-ttu-id="14487-313">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-314">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-314">Pattern</span></span>

<span data-ttu-id="14487-315">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="14487-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="14487-316">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-316">Checksum</span></span>

<span data-ttu-id="14487-317">はい</span><span class="sxs-lookup"><span data-stu-id="14487-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-318">定義</span><span class="sxs-lookup"><span data-stu-id="14487-318">Definition</span></span>

<span data-ttu-id="14487-319">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-320">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-321">From `Keywords_hungary_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-322">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-323">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-324">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-326">ハンガリーのソーシャルセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="14487-326">hungarian social security number</span></span>
  
<span data-ttu-id="14487-327">social security number</span><span class="sxs-lookup"><span data-stu-id="14487-327">social security number</span></span>
  
<span data-ttu-id="14487-328">指定した仮のセキュリティ番号#</span><span class="sxs-lookup"><span data-stu-id="14487-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="14487-329">hssn#</span><span class="sxs-lookup"><span data-stu-id="14487-329">hssn#</span></span>
  
<span data-ttu-id="14487-330">"対話型"</span><span class="sxs-lookup"><span data-stu-id="14487-330">socialsecuritynno</span></span>
  
<span data-ttu-id="14487-331">hssn</span><span class="sxs-lookup"><span data-stu-id="14487-331">hssn</span></span>
  
<span data-ttu-id="14487-332">taj</span><span class="sxs-lookup"><span data-stu-id="14487-332">taj</span></span>
  
<span data-ttu-id="14487-333">taj#</span><span class="sxs-lookup"><span data-stu-id="14487-333">taj#</span></span>
  
<span data-ttu-id="14487-334">ssn</span><span class="sxs-lookup"><span data-stu-id="14487-334">ssn</span></span>
  
<span data-ttu-id="14487-335">ssn#</span><span class="sxs-lookup"><span data-stu-id="14487-335">ssn#</span></span>
  
<span data-ttu-id="14487-336">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="14487-336">social security no</span></span>
  
<span data-ttu-id="14487-337">áfa</span><span class="sxs-lookup"><span data-stu-id="14487-337">áfa</span></span>
  
<span data-ttu-id="14487-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="14487-338">közösségi adószám</span></span>
  
<span data-ttu-id="14487-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="14487-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="14487-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="14487-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="14487-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="14487-341">áfa szám</span></span>
  
<span data-ttu-id="14487-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="14487-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="14487-343">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="14487-343">Portugal</span></span>

<span data-ttu-id="14487-344">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14487-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="14487-345">スペイン</span><span class="sxs-lookup"><span data-stu-id="14487-345">Spain</span></span>

<span data-ttu-id="14487-346">詳細については、「スペインの社会保障番号 (SSN)」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14487-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="14487-347">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="14487-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="14487-348">Format</span><span class="sxs-lookup"><span data-stu-id="14487-348">Format</span></span>

<span data-ttu-id="14487-349">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="14487-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="14487-350">パターン</span><span class="sxs-lookup"><span data-stu-id="14487-350">Pattern</span></span>

<span data-ttu-id="14487-351">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="14487-351">12 digits:</span></span>
  
-  <span data-ttu-id="14487-352">誕生日に対応する8桁の数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="14487-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="14487-353">次の場合、シリアル番号に対応する3桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="14487-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="14487-354">シリアル番号の最後の桁は、男性の場合は奇数、女性の場合は偶数の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="14487-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="14487-355">1990までの間、シリアル番号 corresponded は、番号のベアラーが生まれたか (1947 以前に作成された場合)、特別なコード (通常は7番目の数字) を使用して、税務1947レコードに従って、そのユーザーが生活していた市区郡に割り当てられています。immigrants</span><span class="sxs-lookup"><span data-stu-id="14487-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="14487-356">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="14487-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="14487-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14487-357">Checksum</span></span>

<span data-ttu-id="14487-358">はい</span><span class="sxs-lookup"><span data-stu-id="14487-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="14487-359">定義</span><span class="sxs-lookup"><span data-stu-id="14487-359">Definition</span></span>

<span data-ttu-id="14487-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-361">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="14487-362">From `Keywords_sweden_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="14487-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="14487-363">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="14487-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="14487-364">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="14487-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="14487-365">キーワード</span><span class="sxs-lookup"><span data-stu-id="14487-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="14487-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="14487-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="14487-367">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-367">personal id number</span></span>
  
<span data-ttu-id="14487-368">identification number</span><span class="sxs-lookup"><span data-stu-id="14487-368">identification number</span></span>
  
<span data-ttu-id="14487-369">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-369">personal id no</span></span>
  
<span data-ttu-id="14487-370">id 番号</span><span class="sxs-lookup"><span data-stu-id="14487-370">identity no</span></span>
  
<span data-ttu-id="14487-371">識別番号</span><span class="sxs-lookup"><span data-stu-id="14487-371">identification no</span></span>
  
<span data-ttu-id="14487-372">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="14487-372">personal identification no</span></span>
  
<span data-ttu-id="14487-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="14487-373">personnummer id</span></span>
  
<span data-ttu-id="14487-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="14487-374">personligt id-nummer</span></span>
  
<span data-ttu-id="14487-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="14487-375">unikt id-nummer</span></span>
  
<span data-ttu-id="14487-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="14487-376">personnummer</span></span>
  
<span data-ttu-id="14487-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="14487-377">identifikationsnumret</span></span>
  
<span data-ttu-id="14487-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="14487-378">personnummer#</span></span>
  
<span data-ttu-id="14487-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="14487-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="14487-380">関連項目</span><span class="sxs-lookup"><span data-stu-id="14487-380">See also</span></span>

[<span data-ttu-id="14487-381">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="14487-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

