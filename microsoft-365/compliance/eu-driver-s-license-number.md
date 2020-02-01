---
title: EU 運転免許証番号
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
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592658"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="40fae-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-104">EU Driver's License Number</span></span>

<span data-ttu-id="40fae-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="40fae-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="40fae-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="40fae-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="40fae-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="40fae-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="40fae-108">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-108">Format</span></span>

<span data-ttu-id="40fae-109">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-110">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-110">Pattern</span></span>

<span data-ttu-id="40fae-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-112">Checksum</span></span>

<span data-ttu-id="40fae-113">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-114">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-114">Definition</span></span>

<span data-ttu-id="40fae-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-116">正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-117">From `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="40fae-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-118">Keywords</span></span>

<span data-ttu-id="40fae-119">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-119">| |</span></span>
|<span data-ttu-id="40fae-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-121">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-121">dl#</span></span>  <br/> <span data-ttu-id="40fae-122">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-122">driver license</span></span>  <br/> <span data-ttu-id="40fae-123">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-123">driver license number</span></span>  <br/> <span data-ttu-id="40fae-124">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-124">driver licence</span></span>  <br/> <span data-ttu-id="40fae-125">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-125">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-126">drivers license</span></span>  <br/> <span data-ttu-id="40fae-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="40fae-127">driver's licence</span></span>  <br/> <span data-ttu-id="40fae-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-128">driver's license</span></span>  <br/> <span data-ttu-id="40fae-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-129">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-130">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="40fae-131">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-131">driving license number</span></span>  <br/> <span data-ttu-id="40fae-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-132">dlno#</span></span>  <br/> <span data-ttu-id="40fae-133">futex</span><span class="sxs-lookup"><span data-stu-id="40fae-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="40fae-134">futex (futex) republik osterreich</span><span class="sxs-lookup"><span data-stu-id="40fae-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="40fae-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="40fae-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="40fae-136">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-136">Format</span></span>

<span data-ttu-id="40fae-137">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-138">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-138">Pattern</span></span>

<span data-ttu-id="40fae-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-140">Checksum</span></span>

<span data-ttu-id="40fae-141">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-142">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-142">Definition</span></span>

<span data-ttu-id="40fae-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-144">正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-145">From `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="40fae-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-146">Keywords</span></span>

<span data-ttu-id="40fae-147">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-147">| |</span></span>
|<span data-ttu-id="40fae-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-149">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-149">dl#</span></span>  <br/> <span data-ttu-id="40fae-150">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-150">driver license</span></span>  <br/> <span data-ttu-id="40fae-151">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-151">driver license number</span></span>  <br/> <span data-ttu-id="40fae-152">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-152">driver licence</span></span>  <br/> <span data-ttu-id="40fae-153">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-153">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-154">drivers license</span></span>  <br/> <span data-ttu-id="40fae-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-155">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-156">driver's license</span></span>  <br/> <span data-ttu-id="40fae-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-157">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-158">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-158">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-159">dlno#</span></span>  <br/> <span data-ttu-id="40fae-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="40fae-160">rijbewijs</span></span>  <br/> <span data-ttu-id="40fae-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="40fae-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="40fae-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="40fae-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="40fae-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="40fae-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="40fae-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="40fae-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="40fae-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="40fae-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="40fae-166">futex の eh/Nr</span><span class="sxs-lookup"><span data-stu-id="40fae-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="40fae-167">futex の eh/nr</span><span class="sxs-lookup"><span data-stu-id="40fae-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="40fae-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="40fae-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="40fae-169">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-169">Format</span></span>

<span data-ttu-id="40fae-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-171">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-171">Pattern</span></span>

<span data-ttu-id="40fae-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-173">Checksum</span></span>

<span data-ttu-id="40fae-174">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-175">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-175">Definition</span></span>

<span data-ttu-id="40fae-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-177">正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-178">From `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="40fae-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-179">Keywords</span></span>

<span data-ttu-id="40fae-180">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-180">| |</span></span>
|<span data-ttu-id="40fae-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-182">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-182">dl#</span></span>  <br/> <span data-ttu-id="40fae-183">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-183">driver license</span></span>  <br/> <span data-ttu-id="40fae-184">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-184">driver license number</span></span>  <br/> <span data-ttu-id="40fae-185">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-185">driver licence</span></span>  <br/> <span data-ttu-id="40fae-186">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-186">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-187">drivers license</span></span>  <br/> <span data-ttu-id="40fae-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-188">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-189">driver's license</span></span>  <br/> <span data-ttu-id="40fae-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-190">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-191">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-191">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-192">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-192">driving license number</span></span>  <br/> <span data-ttu-id="40fae-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-193">dlno#</span></span>  <br/> <span data-ttu-id="40fae-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="40fae-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="40fae-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="40fae-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="40fae-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="40fae-196">сумпс</span></span>  <br/> <span data-ttu-id="40fae-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="40fae-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="40fae-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="40fae-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="40fae-199">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-199">Format</span></span>

<span data-ttu-id="40fae-200">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-201">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-201">Pattern</span></span>

<span data-ttu-id="40fae-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-203">Checksum</span></span>

<span data-ttu-id="40fae-204">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-205">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-205">Definition</span></span>

<span data-ttu-id="40fae-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-207">正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-208">From `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="40fae-209">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-209">Keywords</span></span>

<span data-ttu-id="40fae-210">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-210">| |</span></span>
|<span data-ttu-id="40fae-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-212">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-212">dl#</span></span>  <br/> <span data-ttu-id="40fae-213">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-213">driver license</span></span>  <br/> <span data-ttu-id="40fae-214">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-214">driver license number</span></span>  <br/> <span data-ttu-id="40fae-215">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-215">driver licence</span></span>  <br/> <span data-ttu-id="40fae-216">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-216">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-217">drivers license</span></span>  <br/> <span data-ttu-id="40fae-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-218">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-219">driver's license</span></span>  <br/> <span data-ttu-id="40fae-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-220">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-221">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-221">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-222">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-222">driving license number</span></span>  <br/> <span data-ttu-id="40fae-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-223">dlno#</span></span>  <br/> <span data-ttu-id="40fae-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="40fae-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="40fae-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="40fae-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="40fae-226">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-226">Format</span></span>

<span data-ttu-id="40fae-227">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="40fae-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-228">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-228">Pattern</span></span>

<span data-ttu-id="40fae-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-230">Checksum</span></span>

<span data-ttu-id="40fae-231">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-232">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-232">Definition</span></span>

<span data-ttu-id="40fae-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-234">正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-235">From `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-236">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-236">Keywords</span></span>

<span data-ttu-id="40fae-237">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-237">| |</span></span>
|<span data-ttu-id="40fae-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-239">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-239">dl#</span></span>  <br/> <span data-ttu-id="40fae-240">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-240">driver license</span></span>  <br/> <span data-ttu-id="40fae-241">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-241">driver license number</span></span>  <br/> <span data-ttu-id="40fae-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-242">driver licence</span></span>  <br/> <span data-ttu-id="40fae-243">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-243">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-244">drivers license</span></span>  <br/> <span data-ttu-id="40fae-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-245">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-246">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-247">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-247">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-248">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-248">driving license number</span></span>  <br/> <span data-ttu-id="40fae-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-249">dlno#</span></span>  <br/> <span data-ttu-id="40fae-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="40fae-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="40fae-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="40fae-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="40fae-252">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-252">Format</span></span>

<span data-ttu-id="40fae-253">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-254">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-254">Pattern</span></span>

<span data-ttu-id="40fae-255">8つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="40fae-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="40fae-256">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="40fae-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="40fae-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="40fae-257">A space (optional)</span></span>
    
- <span data-ttu-id="40fae-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-259">Checksum</span></span>

<span data-ttu-id="40fae-260">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-261">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-261">Definition</span></span>

<span data-ttu-id="40fae-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-263">正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-264">From `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="40fae-265">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-265">Keywords</span></span>

<span data-ttu-id="40fae-266">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-266">| |</span></span>
|<span data-ttu-id="40fae-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-268">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-268">dl#</span></span>  <br/> <span data-ttu-id="40fae-269">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-269">driver license</span></span>  <br/> <span data-ttu-id="40fae-270">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-270">driver license number</span></span>  <br/> <span data-ttu-id="40fae-271">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-271">driver licence</span></span>  <br/> <span data-ttu-id="40fae-272">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-272">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-273">drivers license</span></span>  <br/> <span data-ttu-id="40fae-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-274">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-275">driver's license</span></span>  <br/> <span data-ttu-id="40fae-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-276">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-277">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-278">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-278">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-279">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-279">driving license number</span></span>  <br/> <span data-ttu-id="40fae-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-280">dlno#</span></span>  <br/> <span data-ttu-id="40fae-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="40fae-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="40fae-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="40fae-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="40fae-283">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-283">Format</span></span>

<span data-ttu-id="40fae-284">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-285">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-285">Pattern</span></span>

<span data-ttu-id="40fae-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-287">Checksum</span></span>

<span data-ttu-id="40fae-288">はい</span><span class="sxs-lookup"><span data-stu-id="40fae-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-289">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-289">Definition</span></span>

<span data-ttu-id="40fae-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-291">正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-292">From `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="40fae-293">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-293">Keywords</span></span>

<span data-ttu-id="40fae-294">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-294">| |</span></span>
|<span data-ttu-id="40fae-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-296">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-296">dl#</span></span>  <br/> <span data-ttu-id="40fae-297">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-297">driver license</span></span>  <br/> <span data-ttu-id="40fae-298">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-298">driver license number</span></span>  <br/> <span data-ttu-id="40fae-299">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-299">driver licence</span></span>  <br/> <span data-ttu-id="40fae-300">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-300">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-301">drivers license</span></span>  <br/> <span data-ttu-id="40fae-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-302">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-303">driver's license</span></span>  <br/> <span data-ttu-id="40fae-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-304">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-305">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-305">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-306">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-306">driving license number</span></span>  <br/> <span data-ttu-id="40fae-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-307">dlno#</span></span>  <br/> <span data-ttu-id="40fae-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="40fae-308">kørekort</span></span>  <br/> <span data-ttu-id="40fae-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="40fae-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="40fae-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="40fae-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="40fae-311">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-311">Format</span></span>

<span data-ttu-id="40fae-312">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-313">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-313">Pattern</span></span>

<span data-ttu-id="40fae-314">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="40fae-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="40fae-315">文字 "ET" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="40fae-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="40fae-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-317">Checksum</span></span>

<span data-ttu-id="40fae-318">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-319">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-319">Definition</span></span>

<span data-ttu-id="40fae-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-321">正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-322">From `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-323">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-323">Keywords</span></span>

<span data-ttu-id="40fae-324">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-324">| |</span></span>
|<span data-ttu-id="40fae-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-326">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-326">dl#</span></span>  <br/> <span data-ttu-id="40fae-327">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-327">driver license</span></span>  <br/> <span data-ttu-id="40fae-328">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-328">driver license number</span></span>  <br/> <span data-ttu-id="40fae-329">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-329">driver license number</span></span>  <br/> <span data-ttu-id="40fae-330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-330">driver licence</span></span>  <br/> <span data-ttu-id="40fae-331">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-331">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-332">drivers license</span></span>  <br/> <span data-ttu-id="40fae-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-333">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-334">driver's license</span></span>  <br/> <span data-ttu-id="40fae-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-335">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-336">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-336">driving license number</span></span>  <br/> <span data-ttu-id="40fae-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-337">dlno#</span></span>  <br/> <span data-ttu-id="40fae-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="40fae-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="40fae-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="40fae-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="40fae-340">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-340">Format</span></span>

<span data-ttu-id="40fae-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-342">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-342">Pattern</span></span>

<span data-ttu-id="40fae-343">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="40fae-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="40fae-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-344">Six digits</span></span> 
    
- <span data-ttu-id="40fae-345">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="40fae-345">A hyphen</span></span>
    
-  <span data-ttu-id="40fae-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="40fae-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-347">Checksum</span></span>

<span data-ttu-id="40fae-348">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-349">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-349">Definition</span></span>

<span data-ttu-id="40fae-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-351">正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-352">From `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-353">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-353">Keywords</span></span>

<span data-ttu-id="40fae-354">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-354">| |</span></span>
|<span data-ttu-id="40fae-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-356">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-356">dl#</span></span>  <br/> <span data-ttu-id="40fae-357">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-357">driver license</span></span>  <br/> <span data-ttu-id="40fae-358">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-358">driver license number</span></span>  <br/> <span data-ttu-id="40fae-359">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-359">driver licence</span></span>  <br/> <span data-ttu-id="40fae-360">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-360">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-361">drivers license</span></span>  <br/> <span data-ttu-id="40fae-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-362">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-363">driver's license</span></span>  <br/> <span data-ttu-id="40fae-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-364">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-365">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-365">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-366">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-366">driving license number</span></span>  <br/> <span data-ttu-id="40fae-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-367">dlno#</span></span>  <br/> <span data-ttu-id="40fae-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="40fae-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="40fae-369">フランス</span><span class="sxs-lookup"><span data-stu-id="40fae-369">France</span></span>

<span data-ttu-id="40fae-370">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40fae-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="40fae-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="40fae-371">Germany</span></span>

<span data-ttu-id="40fae-372">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40fae-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="40fae-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="40fae-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="40fae-374">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-374">Format</span></span>

<span data-ttu-id="40fae-375">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-376">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-376">Pattern</span></span>

 <span data-ttu-id="40fae-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="40fae-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-378">Checksum</span></span>

<span data-ttu-id="40fae-379">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-380">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-380">Definition</span></span>

<span data-ttu-id="40fae-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-382">正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-383">From `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-384">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-384">Keywords</span></span>

<span data-ttu-id="40fae-385">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-385">| |</span></span>
|<span data-ttu-id="40fae-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-387">ライブラリ#</span><span class="sxs-lookup"><span data-stu-id="40fae-387">dlL#</span></span>  <br/> <span data-ttu-id="40fae-388">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-388">driver license</span></span>  <br/> <span data-ttu-id="40fae-389">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-389">driver license number</span></span>  <br/> <span data-ttu-id="40fae-390">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-390">driver licence</span></span>  <br/> <span data-ttu-id="40fae-391">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-391">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-392">drivers license</span></span>  <br/> <span data-ttu-id="40fae-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-393">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-394">driver's license</span></span>  <br/> <span data-ttu-id="40fae-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-395">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-396">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-396">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-397">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-397">driving license number</span></span>  <br/> <span data-ttu-id="40fae-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-398">dlno#</span></span>  <br/> <span data-ttu-id="40fae-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="40fae-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="40fae-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="40fae-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="40fae-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="40fae-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="40fae-402">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-402">Format</span></span>

<span data-ttu-id="40fae-403">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-404">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-404">Pattern</span></span>

<span data-ttu-id="40fae-405">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="40fae-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="40fae-406">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="40fae-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="40fae-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-408">Checksum</span></span>

<span data-ttu-id="40fae-409">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-410">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-410">Definition</span></span>

<span data-ttu-id="40fae-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-412">正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-413">From `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-414">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-414">Keywords</span></span>

<span data-ttu-id="40fae-415">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-415">| |</span></span>
|<span data-ttu-id="40fae-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-417">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-417">dl#</span></span>  <br/> <span data-ttu-id="40fae-418">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-418">driver license</span></span>  <br/> <span data-ttu-id="40fae-419">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-419">driver license number</span></span>  <br/> <span data-ttu-id="40fae-420">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-420">driver licence</span></span>  <br/> <span data-ttu-id="40fae-421">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-421">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-422">drivers license</span></span>  <br/> <span data-ttu-id="40fae-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-423">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-424">driver's license</span></span>  <br/> <span data-ttu-id="40fae-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-425">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-426">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-426">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-427">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-427">driving license number</span></span>  <br/> <span data-ttu-id="40fae-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-428">dlno#</span></span>  <br/> <span data-ttu-id="40fae-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="40fae-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="40fae-430">アイルランド</span><span class="sxs-lookup"><span data-stu-id="40fae-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="40fae-431">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-431">Format</span></span>

<span data-ttu-id="40fae-432">6桁の数字の後に4文字</span><span class="sxs-lookup"><span data-stu-id="40fae-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-433">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-433">Pattern</span></span>

<span data-ttu-id="40fae-434">6桁の数字と4文字:</span><span class="sxs-lookup"><span data-stu-id="40fae-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="40fae-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-435">Six digits</span></span>
    
- <span data-ttu-id="40fae-436">4桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="40fae-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-437">Checksum</span></span>

<span data-ttu-id="40fae-438">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-439">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-439">Definition</span></span>

<span data-ttu-id="40fae-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-441">正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-442">From `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-443">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-443">Keywords</span></span>

<span data-ttu-id="40fae-444">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-444">| |</span></span>
|<span data-ttu-id="40fae-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-446">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-446">dl#</span></span>  <br/> <span data-ttu-id="40fae-447">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-447">driver license</span></span>  <br/> <span data-ttu-id="40fae-448">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-448">driver license number</span></span>  <br/> <span data-ttu-id="40fae-449">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-449">driver licence</span></span>  <br/> <span data-ttu-id="40fae-450">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-450">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-451">drivers license</span></span>  <br/> <span data-ttu-id="40fae-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-452">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-453">driver's license</span></span>  <br/> <span data-ttu-id="40fae-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-454">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-455">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-455">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-456">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-456">driving license number</span></span>  <br/> <span data-ttu-id="40fae-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-457">dlno#</span></span>  <br/> <span data-ttu-id="40fae-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="40fae-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="40fae-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="40fae-459">Italy</span></span>

<span data-ttu-id="40fae-460">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40fae-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="40fae-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="40fae-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="40fae-462">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-462">Format</span></span>

<span data-ttu-id="40fae-463">3つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-464">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-464">Pattern</span></span>

<span data-ttu-id="40fae-465">3つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="40fae-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="40fae-466">3桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="40fae-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="40fae-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-468">Checksum</span></span>

<span data-ttu-id="40fae-469">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-470">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-470">Definition</span></span>

<span data-ttu-id="40fae-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-472">正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-473">From `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-474">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-474">Keywords</span></span>

<span data-ttu-id="40fae-475">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-475">| |</span></span>
|<span data-ttu-id="40fae-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-477">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-477">dl#</span></span>  <br/> <span data-ttu-id="40fae-478">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-478">driver license</span></span>  <br/> <span data-ttu-id="40fae-479">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-479">driver license number</span></span>  <br/> <span data-ttu-id="40fae-480">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-480">driver licence</span></span>  <br/> <span data-ttu-id="40fae-481">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-481">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-482">drivers license</span></span>  <br/> <span data-ttu-id="40fae-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-483">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-484">driver's license</span></span>  <br/> <span data-ttu-id="40fae-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-485">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-486">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-486">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-487">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-487">driving license number</span></span>  <br/> <span data-ttu-id="40fae-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-488">dlno#</span></span>  <br/> <span data-ttu-id="40fae-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="40fae-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="40fae-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="40fae-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="40fae-491">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-491">Format</span></span>

<span data-ttu-id="40fae-492">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-493">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-493">Pattern</span></span>

 <span data-ttu-id="40fae-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="40fae-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-495">Checksum</span></span>

<span data-ttu-id="40fae-496">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-497">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-497">Definition</span></span>

<span data-ttu-id="40fae-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-499">正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-500">From `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-501">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-501">Keywords</span></span>

<span data-ttu-id="40fae-502">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-502">| |</span></span>
|<span data-ttu-id="40fae-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-504">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-504">dl#</span></span>  <br/> <span data-ttu-id="40fae-505">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-505">driver license</span></span>  <br/> <span data-ttu-id="40fae-506">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-506">driver license number</span></span>  <br/> <span data-ttu-id="40fae-507">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-507">driver licence</span></span>  <br/> <span data-ttu-id="40fae-508">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-508">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-509">drivers license</span></span>  <br/> <span data-ttu-id="40fae-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-510">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-511">driver's license</span></span>  <br/> <span data-ttu-id="40fae-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-512">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-513">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-513">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-514">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-514">driving license number</span></span>  <br/> <span data-ttu-id="40fae-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-515">dlno#</span></span>  <br/> <span data-ttu-id="40fae-516">vエア uotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="40fae-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="40fae-517">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="40fae-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="40fae-518">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-518">Format</span></span>

<span data-ttu-id="40fae-519">スペースと区切り文字を含まない6桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-520">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-520">Pattern</span></span>

 <span data-ttu-id="40fae-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="40fae-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-522">Checksum</span></span>

<span data-ttu-id="40fae-523">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-524">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-524">Definition</span></span>

<span data-ttu-id="40fae-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-526">正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-527">From `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-528">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-528">Keywords</span></span>

<span data-ttu-id="40fae-529">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-529">| |</span></span>
|<span data-ttu-id="40fae-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-531">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-531">dl#</span></span>  <br/> <span data-ttu-id="40fae-532">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-532">driver license</span></span>  <br/> <span data-ttu-id="40fae-533">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-533">driver license number</span></span>  <br/> <span data-ttu-id="40fae-534">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-534">driver licence</span></span>  <br/> <span data-ttu-id="40fae-535">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-535">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-536">drivers license</span></span>  <br/> <span data-ttu-id="40fae-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-537">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-538">driver's license</span></span>  <br/> <span data-ttu-id="40fae-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-539">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-540">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-540">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-541">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-541">driving license number</span></span>  <br/> <span data-ttu-id="40fae-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-542">dlno#</span></span>  <br/> <span data-ttu-id="40fae-543">fahて fabnis</span><span class="sxs-lookup"><span data-stu-id="40fae-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="40fae-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="40fae-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="40fae-545">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-545">Format</span></span>

<span data-ttu-id="40fae-546">指定したパターンの2つの文字と6桁の数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="40fae-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-547">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-547">Pattern</span></span>

<span data-ttu-id="40fae-548">2つの文字と6桁の数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="40fae-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="40fae-549">2つの文字 (大文字小文字を区別しない数字または文字)</span><span class="sxs-lookup"><span data-stu-id="40fae-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="40fae-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="40fae-550">A space (optional)</span></span>
    
- <span data-ttu-id="40fae-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-551">Three digits</span></span>
    
- <span data-ttu-id="40fae-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="40fae-552">A space (optional)</span></span>
    
- <span data-ttu-id="40fae-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-554">Checksum</span></span>

<span data-ttu-id="40fae-555">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-556">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-556">Definition</span></span>

<span data-ttu-id="40fae-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-558">正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-559">From `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-560">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-560">Keywords</span></span>

<span data-ttu-id="40fae-561">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-561">| |</span></span>
|<span data-ttu-id="40fae-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-563">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-563">dl#</span></span>  <br/> <span data-ttu-id="40fae-564">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-564">driver license</span></span>  <br/> <span data-ttu-id="40fae-565">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-565">driver license number</span></span>  <br/> <span data-ttu-id="40fae-566">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-566">driver licence</span></span>  <br/> <span data-ttu-id="40fae-567">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-567">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-568">drivers license</span></span>  <br/> <span data-ttu-id="40fae-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-569">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-570">driver's license</span></span>  <br/> <span data-ttu-id="40fae-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-571">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-572">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-572">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-573">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-573">driving license number</span></span>  <br/> <span data-ttu-id="40fae-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-574">dlno#</span></span>  <br/> <span data-ttu-id="40fae-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="40fae-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="40fae-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="40fae-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="40fae-577">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-577">Format</span></span>

<span data-ttu-id="40fae-578">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-579">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-579">Pattern</span></span>

<span data-ttu-id="40fae-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-581">Checksum</span></span>

<span data-ttu-id="40fae-582">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-583">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-583">Definition</span></span>

<span data-ttu-id="40fae-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-585">正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-586">From `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-587">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-587">Keywords</span></span>

<span data-ttu-id="40fae-588">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-588">| |</span></span>
|<span data-ttu-id="40fae-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-590">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-590">dl#</span></span>  <br/> <span data-ttu-id="40fae-591">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-591">driver license</span></span>  <br/> <span data-ttu-id="40fae-592">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-592">driver license number</span></span>  <br/> <span data-ttu-id="40fae-593">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-593">driver licence</span></span>  <br/> <span data-ttu-id="40fae-594">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-594">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-595">drivers license</span></span>  <br/> <span data-ttu-id="40fae-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-596">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-597">driver's license</span></span>  <br/> <span data-ttu-id="40fae-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-598">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-599">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-599">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-600">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-600">driving license number</span></span>  <br/> <span data-ttu-id="40fae-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-601">dlno#</span></span>  <br/> <span data-ttu-id="40fae-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="40fae-602">permis de conduire</span></span>  <br/> <span data-ttu-id="40fae-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="40fae-603">rijbewijs</span></span>  <br/> <span data-ttu-id="40fae-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="40fae-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="40fae-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="40fae-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="40fae-606">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-606">Format</span></span>

<span data-ttu-id="40fae-607">2つのスラッシュを含む14桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-608">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-608">Pattern</span></span>

<span data-ttu-id="40fae-609">14桁の数字と2つのスラッシュ:</span><span class="sxs-lookup"><span data-stu-id="40fae-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="40fae-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-610">Five digits</span></span> 
    
- <span data-ttu-id="40fae-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="40fae-611">A forward slash</span></span>
    
- <span data-ttu-id="40fae-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-612">Two digits</span></span>
    
- <span data-ttu-id="40fae-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="40fae-613">A forward slash</span></span>
    
- <span data-ttu-id="40fae-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-615">Checksum</span></span>

<span data-ttu-id="40fae-616">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-617">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-617">Definition</span></span>

<span data-ttu-id="40fae-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-619">正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-620">From `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-621">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-621">Keywords</span></span>

<span data-ttu-id="40fae-622">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-622">| |</span></span>
|<span data-ttu-id="40fae-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-624">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-624">dl#</span></span>  <br/> <span data-ttu-id="40fae-625">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-625">driver license</span></span>  <br/> <span data-ttu-id="40fae-626">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-626">driver license number</span></span>  <br/> <span data-ttu-id="40fae-627">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-627">driver licence</span></span>  <br/> <span data-ttu-id="40fae-628">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-628">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-629">drivers license</span></span>  <br/> <span data-ttu-id="40fae-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-630">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-631">driver's license</span></span>  <br/> <span data-ttu-id="40fae-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-632">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-633">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-633">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-634">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-634">driving license number</span></span>  <br/> <span data-ttu-id="40fae-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-635">dlno#</span></span>  <br/> <span data-ttu-id="40fae-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="40fae-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="40fae-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="40fae-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="40fae-638">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-638">Format</span></span>

<span data-ttu-id="40fae-639">指定したパターンの2文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-640">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-640">Pattern</span></span>

<span data-ttu-id="40fae-641">2つの文字の後に特殊文字を含む7個の数字。</span><span class="sxs-lookup"><span data-stu-id="40fae-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="40fae-642">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="40fae-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="40fae-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="40fae-643">A hyphen</span></span>
    
- <span data-ttu-id="40fae-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-644">Six digits</span></span>
    
- <span data-ttu-id="40fae-645">スペース</span><span class="sxs-lookup"><span data-stu-id="40fae-645">A space</span></span>
    
- <span data-ttu-id="40fae-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-647">Checksum</span></span>

<span data-ttu-id="40fae-648">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-649">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-649">Definition</span></span>

<span data-ttu-id="40fae-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-651">正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-652">From `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-653">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-653">Keywords</span></span>

<span data-ttu-id="40fae-654">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-654">| |</span></span>
|<span data-ttu-id="40fae-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-656">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-656">dl#</span></span>  <br/> <span data-ttu-id="40fae-657">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-657">driver license</span></span>  <br/> <span data-ttu-id="40fae-658">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-658">driver license number</span></span>  <br/> <span data-ttu-id="40fae-659">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-659">driver licence</span></span>  <br/> <span data-ttu-id="40fae-660">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-660">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-661">drivers license</span></span>  <br/> <span data-ttu-id="40fae-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-662">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-663">driver's license</span></span>  <br/> <span data-ttu-id="40fae-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-664">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-665">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-665">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-666">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-666">driving license number</span></span>  <br/> <span data-ttu-id="40fae-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-667">dlno#</span></span>  <br/> <span data-ttu-id="40fae-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="40fae-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="40fae-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="40fae-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="40fae-670">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-670">Format</span></span>

<span data-ttu-id="40fae-671">1文字の後に8桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-672">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-672">Pattern</span></span>

<span data-ttu-id="40fae-673">1文字の後に8桁の数字。</span><span class="sxs-lookup"><span data-stu-id="40fae-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="40fae-674">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="40fae-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="40fae-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-676">Checksum</span></span>

<span data-ttu-id="40fae-677">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-678">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-678">Definition</span></span>

<span data-ttu-id="40fae-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-680">正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-681">From `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-682">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-682">Keywords</span></span>

<span data-ttu-id="40fae-683">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-683">| |</span></span>
|<span data-ttu-id="40fae-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-685">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-685">dl#</span></span>  <br/> <span data-ttu-id="40fae-686">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-686">driver license</span></span>  <br/> <span data-ttu-id="40fae-687">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-687">driver license number</span></span>  <br/> <span data-ttu-id="40fae-688">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-688">driver licence</span></span>  <br/> <span data-ttu-id="40fae-689">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-689">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-690">drivers license</span></span>  <br/> <span data-ttu-id="40fae-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-691">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-692">driver's license</span></span>  <br/> <span data-ttu-id="40fae-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-693">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-694">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-694">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-695">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-695">driving license number</span></span>  <br/> <span data-ttu-id="40fae-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-696">dlno#</span></span>  <br/> <span data-ttu-id="40fae-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="40fae-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="40fae-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="40fae-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="40fae-699">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-699">Format</span></span>

<span data-ttu-id="40fae-700">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-701">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-701">Pattern</span></span>

<span data-ttu-id="40fae-702">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="40fae-703">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="40fae-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="40fae-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="40fae-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-705">Checksum</span></span>

<span data-ttu-id="40fae-706">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-707">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-707">Definition</span></span>

<span data-ttu-id="40fae-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-709">正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-710">From `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-711">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-711">Keywords</span></span>

<span data-ttu-id="40fae-712">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-712">| |</span></span>
|<span data-ttu-id="40fae-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-714">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-714">dl#</span></span>  <br/> <span data-ttu-id="40fae-715">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-715">driver license</span></span>  <br/> <span data-ttu-id="40fae-716">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-716">driver license number</span></span>  <br/> <span data-ttu-id="40fae-717">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-717">driver licence</span></span>  <br/> <span data-ttu-id="40fae-718">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-718">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-719">drivers license</span></span>  <br/> <span data-ttu-id="40fae-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-720">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-721">driver's license</span></span>  <br/> <span data-ttu-id="40fae-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-722">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-723">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-723">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-724">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-724">driving license number</span></span>  <br/> <span data-ttu-id="40fae-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-725">dlno#</span></span>  <br/> <span data-ttu-id="40fae-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="40fae-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="40fae-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="40fae-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="40fae-728">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-728">Format</span></span>

<span data-ttu-id="40fae-729">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-730">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-730">Pattern</span></span>

<span data-ttu-id="40fae-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="40fae-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-732">Checksum</span></span>

<span data-ttu-id="40fae-733">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-734">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-734">Definition</span></span>

<span data-ttu-id="40fae-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-736">正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-737">From `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-738">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-738">Keywords</span></span>

<span data-ttu-id="40fae-739">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-739">| |</span></span>
|<span data-ttu-id="40fae-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-741">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-741">dl#</span></span>  <br/> <span data-ttu-id="40fae-742">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-742">driver license</span></span>  <br/> <span data-ttu-id="40fae-743">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-743">driver license number</span></span>  <br/> <span data-ttu-id="40fae-744">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-744">driver licence</span></span>  <br/> <span data-ttu-id="40fae-745">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-745">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-746">drivers license</span></span>  <br/> <span data-ttu-id="40fae-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-747">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-748">driver's license</span></span>  <br/> <span data-ttu-id="40fae-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-749">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-750">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-750">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-751">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-751">driving license number</span></span>  <br/> <span data-ttu-id="40fae-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-752">dlno#</span></span>  <br/> <span data-ttu-id="40fae-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="40fae-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="40fae-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="40fae-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="40fae-755">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-755">Format</span></span>

<span data-ttu-id="40fae-756">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="40fae-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-757">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-757">Pattern</span></span>

<span data-ttu-id="40fae-758">8桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="40fae-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="40fae-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-759">Eight digits</span></span> 
    
- <span data-ttu-id="40fae-760">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="40fae-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-761">Checksum</span></span>

<span data-ttu-id="40fae-762">はい</span><span class="sxs-lookup"><span data-stu-id="40fae-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-763">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-763">Definition</span></span>

<span data-ttu-id="40fae-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-765">関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="40fae-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-766">From `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40fae-767">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-767">Keywords</span></span>

<span data-ttu-id="40fae-768">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-768">| |</span></span>
|<span data-ttu-id="40fae-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-770">dlno#</span></span>  <br/> <span data-ttu-id="40fae-771">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-771">dl#</span></span>  <br/> <span data-ttu-id="40fae-772">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-772">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-773">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-773">driver licence</span></span>  <br/> <span data-ttu-id="40fae-774">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-774">driver license</span></span>  <br/> <span data-ttu-id="40fae-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-775">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-776">drivers license</span></span>  <br/> <span data-ttu-id="40fae-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="40fae-777">driver's licence</span></span>  <br/> <span data-ttu-id="40fae-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-778">driver's license</span></span>  <br/> <span data-ttu-id="40fae-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="40fae-779">driving licence</span></span>  <br/> <span data-ttu-id="40fae-780">driving license</span><span class="sxs-lookup"><span data-stu-id="40fae-780">driving license</span></span>  <br/> <span data-ttu-id="40fae-781">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-781">driver licence number</span></span>  <br/> <span data-ttu-id="40fae-782">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-782">driver license number</span></span>  <br/> <span data-ttu-id="40fae-783">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-783">drivers licence number</span></span>  <br/> <span data-ttu-id="40fae-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-784">drivers license number</span></span>  <br/> <span data-ttu-id="40fae-785">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-785">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-786">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-787">ライセンス番号の運転</span><span class="sxs-lookup"><span data-stu-id="40fae-787">driving licence number</span></span>  <br/> <span data-ttu-id="40fae-788">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-788">driving license number</span></span>  <br/> <span data-ttu-id="40fae-789">許可の推進</span><span class="sxs-lookup"><span data-stu-id="40fae-789">driving permit</span></span>  <br/> <span data-ttu-id="40fae-790">許可番号の運転</span><span class="sxs-lookup"><span data-stu-id="40fae-790">driving permit number</span></span>  <br/> <span data-ttu-id="40fae-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="40fae-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="40fae-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="40fae-792">permiso conducción</span></span>  <br/> <span data-ttu-id="40fae-793">número/encia conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="40fae-794">número デカーネット de conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="40fae-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="40fae-796">/暗号化 ia conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-796">licencia conducir</span></span>  <br/> <span data-ttu-id="40fae-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="40fae-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="40fae-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="40fae-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-800">permiso conducir</span></span>  <br/> <span data-ttu-id="40fae-801">-encia de manejo</span><span class="sxs-lookup"><span data-stu-id="40fae-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="40fae-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="40fae-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="40fae-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="40fae-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="40fae-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="40fae-805">Format</span><span class="sxs-lookup"><span data-stu-id="40fae-805">Format</span></span>

<span data-ttu-id="40fae-806">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="40fae-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="40fae-807">パターン</span><span class="sxs-lookup"><span data-stu-id="40fae-807">Pattern</span></span>

<span data-ttu-id="40fae-808">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="40fae-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="40fae-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-809">Six digits</span></span> 
    
- <span data-ttu-id="40fae-810">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="40fae-810">A hyphen</span></span>
    
- <span data-ttu-id="40fae-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="40fae-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="40fae-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="40fae-812">Checksum</span></span>

<span data-ttu-id="40fae-813">不要</span><span class="sxs-lookup"><span data-stu-id="40fae-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="40fae-814">定義</span><span class="sxs-lookup"><span data-stu-id="40fae-814">Definition</span></span>

<span data-ttu-id="40fae-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="40fae-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="40fae-816">正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="40fae-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="40fae-817">From `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="40fae-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="40fae-818">キーワード</span><span class="sxs-lookup"><span data-stu-id="40fae-818">Keywords</span></span>

<span data-ttu-id="40fae-819">| |</span><span class="sxs-lookup"><span data-stu-id="40fae-819">| |</span></span>
|<span data-ttu-id="40fae-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="40fae-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="40fae-821">dl#</span><span class="sxs-lookup"><span data-stu-id="40fae-821">dl#</span></span>  <br/> <span data-ttu-id="40fae-822">driver license</span><span class="sxs-lookup"><span data-stu-id="40fae-822">driver license</span></span>  <br/> <span data-ttu-id="40fae-823">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-823">driver license number</span></span>  <br/> <span data-ttu-id="40fae-824">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="40fae-824">driver licence</span></span>  <br/> <span data-ttu-id="40fae-825">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="40fae-825">drivers lic.</span></span>  <br/> <span data-ttu-id="40fae-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="40fae-826">drivers license</span></span>  <br/> <span data-ttu-id="40fae-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="40fae-827">drivers licence</span></span>  <br/> <span data-ttu-id="40fae-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="40fae-828">driver's license</span></span>  <br/> <span data-ttu-id="40fae-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-829">driver's license number</span></span>  <br/> <span data-ttu-id="40fae-830">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="40fae-830">driver's licence number</span></span>  <br/> <span data-ttu-id="40fae-831">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="40fae-831">driving license number</span></span>  <br/> <span data-ttu-id="40fae-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="40fae-832">dlno#</span></span>  <br/> <span data-ttu-id="40fae-833">körkort</span><span class="sxs-lookup"><span data-stu-id="40fae-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="40fae-834">佐賀</span><span class="sxs-lookup"><span data-stu-id="40fae-834">UK</span></span>

<span data-ttu-id="40fae-835">詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="40fae-835">For details, see the section "U.K.</span></span> <span data-ttu-id="40fae-836">[[機密情報の種類](what-the-sensitive-information-types-look-for.md)] に表示される運転免許証番号。</span><span class="sxs-lookup"><span data-stu-id="40fae-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40fae-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="40fae-837">See also</span></span>

[<span data-ttu-id="40fae-838">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="40fae-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

