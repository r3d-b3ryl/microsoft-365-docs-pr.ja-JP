---
title: EU 社会保障番号または同等の ID
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号または同等の ID の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 1f2d1d9c61f27fb47b0c7ac0ce544b17175d4254
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "41591228"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="51a77-104">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="51a77-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="51a77-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号 (SSN) または同等の ID 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="51a77-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="51a77-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="51a77-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="51a77-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="51a77-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="51a77-108">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-108">Format</span></span>

<span data-ttu-id="51a77-109">指定した形式の10桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-110">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-110">Pattern</span></span>

<span data-ttu-id="51a77-111">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="51a77-111">10 digits:</span></span>
  
-  <span data-ttu-id="51a77-112">シリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="51a77-113">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="51a77-113">One check digit</span></span>
    
- <span data-ttu-id="51a77-114">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="51a77-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51a77-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-115">Checksum</span></span>

<span data-ttu-id="51a77-116">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-117">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-117">Definition</span></span>

<span data-ttu-id="51a77-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-119">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-120">From `Keywords_austria_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-122">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-123">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-125">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="51a77-125">social security no</span></span>
  
<span data-ttu-id="51a77-126">social security number</span><span class="sxs-lookup"><span data-stu-id="51a77-126">social security number</span></span>
  
<span data-ttu-id="51a77-127">social security code</span><span class="sxs-lookup"><span data-stu-id="51a77-127">social security code</span></span>
  
<span data-ttu-id="51a77-128">保険番号</span><span class="sxs-lookup"><span data-stu-id="51a77-128">insurance number</span></span>
  
<span data-ttu-id="51a77-129">オーストリア ssn</span><span class="sxs-lookup"><span data-stu-id="51a77-129">austrian ssn</span></span>
  
<span data-ttu-id="51a77-130">ssn#</span><span class="sxs-lookup"><span data-stu-id="51a77-130">ssn#</span></span>
  
<span data-ttu-id="51a77-131">ssn</span><span class="sxs-lookup"><span data-stu-id="51a77-131">ssn</span></span>
  
<span data-ttu-id="51a77-132">保険コード</span><span class="sxs-lookup"><span data-stu-id="51a77-132">insurance code</span></span>
  
<span data-ttu-id="51a77-133">保険コード#</span><span class="sxs-lookup"><span data-stu-id="51a77-133">insurance code#</span></span>
  
<span data-ttu-id="51a77-134">"社会 securityno"#</span><span class="sxs-lookup"><span data-stu-id="51a77-134">socialsecurityno#</span></span>
  
<span data-ttu-id="51a77-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="51a77-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="51a77-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="51a77-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="51a77-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="51a77-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="51a77-138">ベルギー</span><span class="sxs-lookup"><span data-stu-id="51a77-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="51a77-139">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-139">Format</span></span>

<span data-ttu-id="51a77-140">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="51a77-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-141">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-141">Pattern</span></span>

<span data-ttu-id="51a77-142">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51a77-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-143">Checksum</span></span>

<span data-ttu-id="51a77-144">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-145">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-145">Definition</span></span>

<span data-ttu-id="51a77-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-147">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-148">From `Keywords_belgium_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-149">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-150">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-151">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-153">ベルギーの国番号</span><span class="sxs-lookup"><span data-stu-id="51a77-153">belgian national number</span></span>
  
<span data-ttu-id="51a77-154">国番号</span><span class="sxs-lookup"><span data-stu-id="51a77-154">national number</span></span>
  
<span data-ttu-id="51a77-155">social security number</span><span class="sxs-lookup"><span data-stu-id="51a77-155">social security number</span></span>
  
<span data-ttu-id="51a77-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-156">nationalnumber#</span></span>
  
<span data-ttu-id="51a77-157">ssn#</span><span class="sxs-lookup"><span data-stu-id="51a77-157">ssn#</span></span>
  
<span data-ttu-id="51a77-158">ssn</span><span class="sxs-lookup"><span data-stu-id="51a77-158">ssn</span></span>
  
<span data-ttu-id="51a77-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="51a77-159">nationalnumber</span></span>
  
<span data-ttu-id="51a77-160">bnn#</span><span class="sxs-lookup"><span data-stu-id="51a77-160">bnn#</span></span>
  
<span data-ttu-id="51a77-161">bnn</span><span class="sxs-lookup"><span data-stu-id="51a77-161">bnn</span></span>
  
<span data-ttu-id="51a77-162">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-162">personal id number</span></span>
  
<span data-ttu-id="51a77-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-163">personalidnumber#</span></span>
  
<span data-ttu-id="51a77-164">numéro national</span><span class="sxs-lookup"><span data-stu-id="51a77-164">numéro national</span></span>
  
<span data-ttu-id="51a77-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="51a77-165">numéro de sécurité</span></span>
  
<span data-ttu-id="51a77-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="51a77-166">numéro d'assuré</span></span>
  
<span data-ttu-id="51a77-167">identifiant national</span><span class="sxs-lookup"><span data-stu-id="51a77-167">identifiant national</span></span>
  
<span data-ttu-id="51a77-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="51a77-168">identifiantnational#</span></span>
  
<span data-ttu-id="51a77-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="51a77-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="51a77-170">クロアチア</span><span class="sxs-lookup"><span data-stu-id="51a77-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="51a77-171">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-171">Format</span></span>

<span data-ttu-id="51a77-172">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-173">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-173">Pattern</span></span>

 <span data-ttu-id="51a77-174">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="51a77-174">11 digits:</span></span> 
  
-  <span data-ttu-id="51a77-175">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-175">Ten digits</span></span> 
    
- <span data-ttu-id="51a77-176">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="51a77-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51a77-177">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-177">Checksum</span></span>

<span data-ttu-id="51a77-178">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-179">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-179">Definition</span></span>

<span data-ttu-id="51a77-180">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-181">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-182">From `Keywords_croatia_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-183">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-184">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-185">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-187">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="51a77-187">personal identification number</span></span>
  
<span data-ttu-id="51a77-188">マスター市民番号</span><span class="sxs-lookup"><span data-stu-id="51a77-188">master citizen number</span></span>
  
<span data-ttu-id="51a77-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="51a77-189">national identification number</span></span>
  
<span data-ttu-id="51a77-190">social security number</span><span class="sxs-lookup"><span data-stu-id="51a77-190">social security number</span></span>
  
<span data-ttu-id="51a77-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-191">nationalnumber#</span></span>
  
<span data-ttu-id="51a77-192">ssn#</span><span class="sxs-lookup"><span data-stu-id="51a77-192">ssn#</span></span>
  
<span data-ttu-id="51a77-193">ssn</span><span class="sxs-lookup"><span data-stu-id="51a77-193">ssn</span></span>
  
<span data-ttu-id="51a77-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="51a77-194">nationalnumber</span></span>
  
<span data-ttu-id="51a77-195">bnn#</span><span class="sxs-lookup"><span data-stu-id="51a77-195">bnn#</span></span>
  
<span data-ttu-id="51a77-196">bnn</span><span class="sxs-lookup"><span data-stu-id="51a77-196">bnn</span></span>
  
<span data-ttu-id="51a77-197">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-197">personal id number</span></span>
  
<span data-ttu-id="51a77-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-198">personalidnumber#</span></span>
  
<span data-ttu-id="51a77-199">oib</span><span class="sxs-lookup"><span data-stu-id="51a77-199">oib</span></span>
  
<span data-ttu-id="51a77-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="51a77-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="51a77-201">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="51a77-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="51a77-202">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-202">Format</span></span>

<span data-ttu-id="51a77-203">指定したパターンの10桁の数字と円記号</span><span class="sxs-lookup"><span data-stu-id="51a77-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-204">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-204">Pattern</span></span>

<span data-ttu-id="51a77-205">10桁の数字と円記号:</span><span class="sxs-lookup"><span data-stu-id="51a77-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="51a77-206">誕生日に対応する6桁の数字 (YYMMDD という):</span><span class="sxs-lookup"><span data-stu-id="51a77-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="51a77-207">円記号</span><span class="sxs-lookup"><span data-stu-id="51a77-207">A backslash</span></span>
    
- <span data-ttu-id="51a77-208">同じ日付で個人の出生を区切るシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="51a77-209">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="51a77-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51a77-210">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-210">Checksum</span></span>

<span data-ttu-id="51a77-211">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-212">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-212">Definition</span></span>

<span data-ttu-id="51a77-213">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-214">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-215">From `Keywords_czech_republic_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-216">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-217">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-218">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-220">出生地番号</span><span class="sxs-lookup"><span data-stu-id="51a77-220">birth number</span></span>
  
<span data-ttu-id="51a77-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="51a77-221">national identification number</span></span>
  
<span data-ttu-id="51a77-222">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="51a77-222">personal identification number</span></span>
  
<span data-ttu-id="51a77-223">social security number</span><span class="sxs-lookup"><span data-stu-id="51a77-223">social security number</span></span>
  
<span data-ttu-id="51a77-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-224">nationalnumber#</span></span>
  
<span data-ttu-id="51a77-225">ssn#</span><span class="sxs-lookup"><span data-stu-id="51a77-225">ssn#</span></span>
  
<span data-ttu-id="51a77-226">ssn</span><span class="sxs-lookup"><span data-stu-id="51a77-226">ssn</span></span>
  
<span data-ttu-id="51a77-227">国番号</span><span class="sxs-lookup"><span data-stu-id="51a77-227">national number</span></span>
  
<span data-ttu-id="51a77-228">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-228">personal id number</span></span>
  
<span data-ttu-id="51a77-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-229">personalidnumber#</span></span>
  
<span data-ttu-id="51a77-230">rč</span><span class="sxs-lookup"><span data-stu-id="51a77-230">rč</span></span>
  
<span data-ttu-id="51a77-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="51a77-231">rodné číslo</span></span>
  
<span data-ttu-id="51a77-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="51a77-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="51a77-233">デンマーク</span><span class="sxs-lookup"><span data-stu-id="51a77-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="51a77-234">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-234">Format</span></span>

<span data-ttu-id="51a77-235">指定したパターンの10桁の数字とハイフン</span><span class="sxs-lookup"><span data-stu-id="51a77-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-236">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-236">Pattern</span></span>

<span data-ttu-id="51a77-237">10桁の数字とハイフン:</span><span class="sxs-lookup"><span data-stu-id="51a77-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="51a77-238">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="51a77-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="51a77-239">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="51a77-239">A hyphen</span></span>
    
- <span data-ttu-id="51a77-240">シーケンス番号に対応する4桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51a77-241">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-241">Checksum</span></span>

<span data-ttu-id="51a77-242">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-243">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-243">Definition</span></span>

<span data-ttu-id="51a77-244">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-245">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-246">From `Keywords_denmark_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-247">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-248">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-249">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-251">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="51a77-251">personal identification number</span></span>
  
<span data-ttu-id="51a77-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="51a77-252">national identification number</span></span>
  
<span data-ttu-id="51a77-253">social security number</span><span class="sxs-lookup"><span data-stu-id="51a77-253">social security number</span></span>
  
<span data-ttu-id="51a77-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-254">nationalnumber#</span></span>
  
<span data-ttu-id="51a77-255">ssn#</span><span class="sxs-lookup"><span data-stu-id="51a77-255">ssn#</span></span>
  
<span data-ttu-id="51a77-256">ssn</span><span class="sxs-lookup"><span data-stu-id="51a77-256">ssn</span></span>
  
<span data-ttu-id="51a77-257">国番号</span><span class="sxs-lookup"><span data-stu-id="51a77-257">national number</span></span>
  
<span data-ttu-id="51a77-258">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-258">personal id number</span></span>
  
<span data-ttu-id="51a77-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-259">personalidnumber#</span></span>
  
<span data-ttu-id="51a77-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="51a77-260">cpr-nummer</span></span>
  
<span data-ttu-id="51a77-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="51a77-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="51a77-262">フィンランド</span><span class="sxs-lookup"><span data-stu-id="51a77-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="51a77-263">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-263">Format</span></span>

<span data-ttu-id="51a77-264">指定した書式の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="51a77-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-265">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-265">Pattern</span></span>

<span data-ttu-id="51a77-266">指定した形式の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="51a77-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="51a77-267">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-267">Six digits</span></span> 
    
- <span data-ttu-id="51a77-268">次のいずれかのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="51a77-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="51a77-269">プラス記号</span><span class="sxs-lookup"><span data-stu-id="51a77-269">Plus symbol</span></span>
    
  - <span data-ttu-id="51a77-270">マイナス記号</span><span class="sxs-lookup"><span data-stu-id="51a77-270">Minus symbol</span></span>
    
  - <span data-ttu-id="51a77-271">文字 "A" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="51a77-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="51a77-272">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-272">Three digits</span></span>
    
- <span data-ttu-id="51a77-273">1文字または1桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51a77-274">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-274">Checksum</span></span>

<span data-ttu-id="51a77-275">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-276">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-276">Definition</span></span>

<span data-ttu-id="51a77-277">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-278">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-279">From `Keywords_finland_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-280">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-281">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-282">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-284">identification number</span><span class="sxs-lookup"><span data-stu-id="51a77-284">identification number</span></span>
  
<span data-ttu-id="51a77-285">個人 id</span><span class="sxs-lookup"><span data-stu-id="51a77-285">personal id</span></span>
  
<span data-ttu-id="51a77-286">id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-286">identity number</span></span>
  
<span data-ttu-id="51a77-287">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-287">finnish national id number</span></span>
  
<span data-ttu-id="51a77-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="51a77-288">personalidnumber#</span></span>
  
<span data-ttu-id="51a77-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="51a77-289">national identification number</span></span>
  
<span data-ttu-id="51a77-290">id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-290">id number</span></span>
  
<span data-ttu-id="51a77-291">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-291">national id no.</span></span>
  
<span data-ttu-id="51a77-292">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-292">national id number</span></span>
  
<span data-ttu-id="51a77-293">id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-293">id no</span></span>
  
<span data-ttu-id="51a77-294">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="51a77-294">tunnistenumero</span></span>
  
<span data-ttu-id="51a77-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="51a77-295">henkilötunnus</span></span>
  
<span data-ttu-id="51a77-296">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="51a77-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="51a77-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="51a77-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="51a77-298">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="51a77-298">identiteetti numero</span></span>
  
<span data-ttu-id="51a77-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="51a77-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="51a77-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="51a77-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="51a77-301">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="51a77-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="51a77-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="51a77-302">tunnusnumero</span></span>
  
<span data-ttu-id="51a77-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="51a77-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="51a77-304">hetu</span><span class="sxs-lookup"><span data-stu-id="51a77-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="51a77-305">フランス</span><span class="sxs-lookup"><span data-stu-id="51a77-305">France</span></span>

<span data-ttu-id="51a77-306">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの社会保障番号 (insee)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a77-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="51a77-307">ドイツ</span><span class="sxs-lookup"><span data-stu-id="51a77-307">Germany</span></span>

<span data-ttu-id="51a77-308">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの Id カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a77-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="51a77-309">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="51a77-309">Greece</span></span>

<span data-ttu-id="51a77-310">詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a77-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="51a77-311">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="51a77-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="51a77-312">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-312">Format</span></span>

<span data-ttu-id="51a77-313">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-314">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-314">Pattern</span></span>

<span data-ttu-id="51a77-315">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="51a77-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51a77-316">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-316">Checksum</span></span>

<span data-ttu-id="51a77-317">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-318">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-318">Definition</span></span>

<span data-ttu-id="51a77-319">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-320">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-321">From `Keywords_hungary_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-322">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-323">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-324">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-326">ハンガリーのソーシャルセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="51a77-326">hungarian social security number</span></span>
  
<span data-ttu-id="51a77-327">social security number</span><span class="sxs-lookup"><span data-stu-id="51a77-327">social security number</span></span>
  
<span data-ttu-id="51a77-328">指定した仮のセキュリティ番号#</span><span class="sxs-lookup"><span data-stu-id="51a77-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="51a77-329">hssn#</span><span class="sxs-lookup"><span data-stu-id="51a77-329">hssn#</span></span>
  
<span data-ttu-id="51a77-330">"対話型"</span><span class="sxs-lookup"><span data-stu-id="51a77-330">socialsecuritynno</span></span>
  
<span data-ttu-id="51a77-331">hssn</span><span class="sxs-lookup"><span data-stu-id="51a77-331">hssn</span></span>
  
<span data-ttu-id="51a77-332">taj</span><span class="sxs-lookup"><span data-stu-id="51a77-332">taj</span></span>
  
<span data-ttu-id="51a77-333">taj#</span><span class="sxs-lookup"><span data-stu-id="51a77-333">taj#</span></span>
  
<span data-ttu-id="51a77-334">ssn</span><span class="sxs-lookup"><span data-stu-id="51a77-334">ssn</span></span>
  
<span data-ttu-id="51a77-335">ssn#</span><span class="sxs-lookup"><span data-stu-id="51a77-335">ssn#</span></span>
  
<span data-ttu-id="51a77-336">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="51a77-336">social security no</span></span>
  
<span data-ttu-id="51a77-337">áfa</span><span class="sxs-lookup"><span data-stu-id="51a77-337">áfa</span></span>
  
<span data-ttu-id="51a77-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="51a77-338">közösségi adószám</span></span>
  
<span data-ttu-id="51a77-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="51a77-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="51a77-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="51a77-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="51a77-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="51a77-341">áfa szám</span></span>
  
<span data-ttu-id="51a77-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="51a77-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="51a77-343">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="51a77-343">Portugal</span></span>

<span data-ttu-id="51a77-344">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a77-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="51a77-345">スペイン</span><span class="sxs-lookup"><span data-stu-id="51a77-345">Spain</span></span>

<span data-ttu-id="51a77-346">詳細については、「スペインの社会保障番号 (SSN)」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a77-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="51a77-347">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="51a77-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="51a77-348">Format</span><span class="sxs-lookup"><span data-stu-id="51a77-348">Format</span></span>

<span data-ttu-id="51a77-349">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="51a77-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51a77-350">パターン</span><span class="sxs-lookup"><span data-stu-id="51a77-350">Pattern</span></span>

<span data-ttu-id="51a77-351">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="51a77-351">12 digits:</span></span>
  
-  <span data-ttu-id="51a77-352">誕生日に対応する8桁の数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="51a77-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="51a77-353">次の場合、シリアル番号に対応する3桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="51a77-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="51a77-354">シリアル番号の最後の桁は、男性の場合は奇数、女性の場合は偶数の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="51a77-355">1990までの間、シリアル番号の corresponded を郡に割り当てます。これは、年1月 1947 1 日に税務レコードに従って、(通常は7番目の数字) を指定することによって、番号のベアラーが入社したか (1947 以前に作成された場合)、immigrants のための特別なコードになります。</span><span class="sxs-lookup"><span data-stu-id="51a77-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="51a77-356">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="51a77-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51a77-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="51a77-357">Checksum</span></span>

<span data-ttu-id="51a77-358">必要</span><span class="sxs-lookup"><span data-stu-id="51a77-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51a77-359">定義</span><span class="sxs-lookup"><span data-stu-id="51a77-359">Definition</span></span>

<span data-ttu-id="51a77-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-361">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51a77-362">From `Keywords_sweden_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="51a77-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="51a77-363">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="51a77-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51a77-364">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="51a77-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="51a77-365">キーワード</span><span class="sxs-lookup"><span data-stu-id="51a77-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="51a77-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="51a77-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="51a77-367">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-367">personal id number</span></span>
  
<span data-ttu-id="51a77-368">identification number</span><span class="sxs-lookup"><span data-stu-id="51a77-368">identification number</span></span>
  
<span data-ttu-id="51a77-369">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-369">personal id no</span></span>
  
<span data-ttu-id="51a77-370">id 番号</span><span class="sxs-lookup"><span data-stu-id="51a77-370">identity no</span></span>
  
<span data-ttu-id="51a77-371">識別番号</span><span class="sxs-lookup"><span data-stu-id="51a77-371">identification no</span></span>
  
<span data-ttu-id="51a77-372">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="51a77-372">personal identification no</span></span>
  
<span data-ttu-id="51a77-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="51a77-373">personnummer id</span></span>
  
<span data-ttu-id="51a77-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="51a77-374">personligt id-nummer</span></span>
  
<span data-ttu-id="51a77-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="51a77-375">unikt id-nummer</span></span>
  
<span data-ttu-id="51a77-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="51a77-376">personnummer</span></span>
  
<span data-ttu-id="51a77-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="51a77-377">identifikationsnumret</span></span>
  
<span data-ttu-id="51a77-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="51a77-378">personnummer#</span></span>
  
<span data-ttu-id="51a77-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="51a77-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51a77-380">関連項目</span><span class="sxs-lookup"><span data-stu-id="51a77-380">See also</span></span>

[<span data-ttu-id="51a77-381">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="51a77-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

