---
title: EU 運転免許証番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085884"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="3e80b-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-104">EU Driver's License Number</span></span>

<span data-ttu-id="3e80b-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="3e80b-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="3e80b-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3e80b-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="3e80b-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-108">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-108">Format</span></span>

<span data-ttu-id="3e80b-109">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-110">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-110">Pattern</span></span>

<span data-ttu-id="3e80b-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-112">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-112">Checksum</span></span>

<span data-ttu-id="3e80b-113">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-114">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-114">Definition</span></span>

<span data-ttu-id="3e80b-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-116">正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-117">From `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="3e80b-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-118">Keywords</span></span>

<span data-ttu-id="3e80b-119">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-119"></span></span>
|<span data-ttu-id="3e80b-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-121">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-121">dl#</span></span>  <br/> <span data-ttu-id="3e80b-122">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-122">driver license</span></span>  <br/> <span data-ttu-id="3e80b-123">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-123">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-124">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-124">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-125">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-125">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-126">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-127">driver's licence</span></span>  <br/> <span data-ttu-id="3e80b-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-128">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-129">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-130">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="3e80b-131">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-131">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-132">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-133">futex</span><span class="sxs-lookup"><span data-stu-id="3e80b-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="3e80b-134">futex (futex) republik osterreich</span><span class="sxs-lookup"><span data-stu-id="3e80b-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="3e80b-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="3e80b-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-136">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-136">Format</span></span>

<span data-ttu-id="3e80b-137">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-138">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-138">Pattern</span></span>

<span data-ttu-id="3e80b-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-140">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-140">Checksum</span></span>

<span data-ttu-id="3e80b-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-142">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-142">Definition</span></span>

<span data-ttu-id="3e80b-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-144">正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-145">From `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3e80b-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-146">Keywords</span></span>

<span data-ttu-id="3e80b-147">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-147"></span></span>
|<span data-ttu-id="3e80b-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-149">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-149">dl#</span></span>  <br/> <span data-ttu-id="3e80b-150">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-150">driver license</span></span>  <br/> <span data-ttu-id="3e80b-151">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-151">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-152">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-152">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-153">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-153">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-154">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-155">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-156">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-157">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-158">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-158">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-159">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="3e80b-160">rijbewijs</span></span>  <br/> <span data-ttu-id="3e80b-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="3e80b-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="3e80b-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="3e80b-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="3e80b-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="3e80b-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="3e80b-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="3e80b-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="3e80b-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="3e80b-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="3e80b-166">futex の eh/Nr</span><span class="sxs-lookup"><span data-stu-id="3e80b-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="3e80b-167">futex の eh/nr</span><span class="sxs-lookup"><span data-stu-id="3e80b-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="3e80b-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="3e80b-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-169">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-169">Format</span></span>

<span data-ttu-id="3e80b-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-171">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-171">Pattern</span></span>

<span data-ttu-id="3e80b-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-173">Checksum</span></span>

<span data-ttu-id="3e80b-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-175">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-175">Definition</span></span>

<span data-ttu-id="3e80b-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-177">正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-178">From `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="3e80b-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-179">Keywords</span></span>

<span data-ttu-id="3e80b-180">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-180"></span></span>
|<span data-ttu-id="3e80b-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-182">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-182">dl#</span></span>  <br/> <span data-ttu-id="3e80b-183">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-183">driver license</span></span>  <br/> <span data-ttu-id="3e80b-184">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-184">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-185">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-185">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-186">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-186">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-187">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-188">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-189">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-190">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-191">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-191">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-192">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-192">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-193">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="3e80b-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="3e80b-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="3e80b-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="3e80b-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="3e80b-196">сумпс</span></span>  <br/> <span data-ttu-id="3e80b-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="3e80b-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="3e80b-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="3e80b-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-199">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-199">Format</span></span>

<span data-ttu-id="3e80b-200">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-201">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-201">Pattern</span></span>

<span data-ttu-id="3e80b-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-203">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-203">Checksum</span></span>

<span data-ttu-id="3e80b-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-205">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-205">Definition</span></span>

<span data-ttu-id="3e80b-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-207">正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-208">From `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3e80b-209">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-209">Keywords</span></span>

<span data-ttu-id="3e80b-210">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-210"></span></span>
|<span data-ttu-id="3e80b-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-212">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-212">dl#</span></span>  <br/> <span data-ttu-id="3e80b-213">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-213">driver license</span></span>  <br/> <span data-ttu-id="3e80b-214">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-214">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-215">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-215">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-216">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-216">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-217">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-218">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-219">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-220">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-221">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-221">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-222">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-222">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-223">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="3e80b-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="3e80b-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="3e80b-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-226">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-226">Format</span></span>

<span data-ttu-id="3e80b-227">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="3e80b-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-228">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-228">Pattern</span></span>

<span data-ttu-id="3e80b-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-230">Checksum</span></span>

<span data-ttu-id="3e80b-231">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-232">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-232">Definition</span></span>

<span data-ttu-id="3e80b-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-234">正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-235">From `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-236">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-236">Keywords</span></span>

<span data-ttu-id="3e80b-237">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-237"></span></span>
|<span data-ttu-id="3e80b-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-239">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-239">dl#</span></span>  <br/> <span data-ttu-id="3e80b-240">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-240">driver license</span></span>  <br/> <span data-ttu-id="3e80b-241">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-241">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-242">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-243">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-243">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-244">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-245">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-246">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-247">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-247">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-248">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-248">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-249">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="3e80b-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="3e80b-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="3e80b-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-252">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-252">Format</span></span>

<span data-ttu-id="3e80b-253">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-254">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-254">Pattern</span></span>

<span data-ttu-id="3e80b-255">8つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="3e80b-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="3e80b-256">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3e80b-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="3e80b-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="3e80b-257">A space (optional)</span></span>
    
- <span data-ttu-id="3e80b-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-259">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-259">Checksum</span></span>

<span data-ttu-id="3e80b-260">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-261">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-261">Definition</span></span>

<span data-ttu-id="3e80b-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-263">正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-264">From `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3e80b-265">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-265">Keywords</span></span>

<span data-ttu-id="3e80b-266">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-266"></span></span>
|<span data-ttu-id="3e80b-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-268">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-268">dl#</span></span>  <br/> <span data-ttu-id="3e80b-269">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-269">driver license</span></span>  <br/> <span data-ttu-id="3e80b-270">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-270">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-271">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-271">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-272">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-272">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-273">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-274">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-275">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-276">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-277">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-278">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-278">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-279">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-279">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-280">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="3e80b-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="3e80b-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="3e80b-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-283">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-283">Format</span></span>

<span data-ttu-id="3e80b-284">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-285">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-285">Pattern</span></span>

<span data-ttu-id="3e80b-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-287">Checksum</span></span>

<span data-ttu-id="3e80b-288">はい</span><span class="sxs-lookup"><span data-stu-id="3e80b-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-289">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-289">Definition</span></span>

<span data-ttu-id="3e80b-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-291">正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-292">From `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3e80b-293">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-293">Keywords</span></span>

<span data-ttu-id="3e80b-294">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-294"></span></span>
|<span data-ttu-id="3e80b-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-296">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-296">dl#</span></span>  <br/> <span data-ttu-id="3e80b-297">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-297">driver license</span></span>  <br/> <span data-ttu-id="3e80b-298">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-298">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-299">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-299">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-300">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-300">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-301">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-302">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-303">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-304">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-305">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-305">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-306">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-306">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-307">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="3e80b-308">kørekort</span></span>  <br/> <span data-ttu-id="3e80b-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="3e80b-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="3e80b-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="3e80b-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-311">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-311">Format</span></span>

<span data-ttu-id="3e80b-312">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-313">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-313">Pattern</span></span>

<span data-ttu-id="3e80b-314">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3e80b-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="3e80b-315">文字 "ET" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3e80b-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3e80b-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-317">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-317">Checksum</span></span>

<span data-ttu-id="3e80b-318">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-319">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-319">Definition</span></span>

<span data-ttu-id="3e80b-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-321">正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-322">From `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-323">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-323">Keywords</span></span>

<span data-ttu-id="3e80b-324">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-324"></span></span>
|<span data-ttu-id="3e80b-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-326">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-326">dl#</span></span>  <br/> <span data-ttu-id="3e80b-327">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-327">driver license</span></span>  <br/> <span data-ttu-id="3e80b-328">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-328">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-329">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-329">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-330">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-331">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-331">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-332">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-333">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-334">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-335">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-336">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-336">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-337">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="3e80b-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="3e80b-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="3e80b-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-340">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-340">Format</span></span>

<span data-ttu-id="3e80b-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-342">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-342">Pattern</span></span>

<span data-ttu-id="3e80b-343">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3e80b-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="3e80b-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-344">Six digits</span></span> 
    
- <span data-ttu-id="3e80b-345">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="3e80b-345">A hyphen</span></span>
    
-  <span data-ttu-id="3e80b-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3e80b-347">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-347">Checksum</span></span>

<span data-ttu-id="3e80b-348">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-349">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-349">Definition</span></span>

<span data-ttu-id="3e80b-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-351">正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-352">From `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-353">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-353">Keywords</span></span>

<span data-ttu-id="3e80b-354">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-354"></span></span>
|<span data-ttu-id="3e80b-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-356">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-356">dl#</span></span>  <br/> <span data-ttu-id="3e80b-357">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-357">driver license</span></span>  <br/> <span data-ttu-id="3e80b-358">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-358">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-359">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-359">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-360">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-360">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-361">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-362">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-363">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-364">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-365">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-365">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-366">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-366">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-367">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="3e80b-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="3e80b-369">フランス</span><span class="sxs-lookup"><span data-stu-id="3e80b-369">France</span></span>

<span data-ttu-id="3e80b-370">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e80b-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3e80b-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="3e80b-371">Germany</span></span>

<span data-ttu-id="3e80b-372">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e80b-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3e80b-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="3e80b-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-374">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-374">Format</span></span>

<span data-ttu-id="3e80b-375">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-376">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-376">Pattern</span></span>

 <span data-ttu-id="3e80b-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3e80b-378">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-378">Checksum</span></span>

<span data-ttu-id="3e80b-379">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-380">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-380">Definition</span></span>

<span data-ttu-id="3e80b-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-382">正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-383">From `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-384">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-384">Keywords</span></span>

<span data-ttu-id="3e80b-385">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-385"></span></span>
|<span data-ttu-id="3e80b-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-387">ライブラリ#</span><span class="sxs-lookup"><span data-stu-id="3e80b-387">dlL#</span></span>  <br/> <span data-ttu-id="3e80b-388">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-388">driver license</span></span>  <br/> <span data-ttu-id="3e80b-389">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-389">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-390">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-390">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-391">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-391">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-392">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-393">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-394">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-395">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-396">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-396">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-397">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-397">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-398">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="3e80b-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="3e80b-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="3e80b-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="3e80b-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="3e80b-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-402">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-402">Format</span></span>

<span data-ttu-id="3e80b-403">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-404">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-404">Pattern</span></span>

<span data-ttu-id="3e80b-405">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3e80b-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="3e80b-406">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3e80b-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3e80b-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-408">Checksum</span></span>

<span data-ttu-id="3e80b-409">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-410">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-410">Definition</span></span>

<span data-ttu-id="3e80b-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-412">正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-413">From `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-414">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-414">Keywords</span></span>

<span data-ttu-id="3e80b-415">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-415"></span></span>
|<span data-ttu-id="3e80b-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-417">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-417">dl#</span></span>  <br/> <span data-ttu-id="3e80b-418">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-418">driver license</span></span>  <br/> <span data-ttu-id="3e80b-419">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-419">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-420">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-420">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-421">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-421">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-422">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-423">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-424">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-425">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-426">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-426">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-427">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-427">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-428">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="3e80b-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="3e80b-430">アイルランド</span><span class="sxs-lookup"><span data-stu-id="3e80b-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-431">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-431">Format</span></span>

<span data-ttu-id="3e80b-432">6桁の数字の後に4文字</span><span class="sxs-lookup"><span data-stu-id="3e80b-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-433">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-433">Pattern</span></span>

<span data-ttu-id="3e80b-434">6桁の数字と4文字:</span><span class="sxs-lookup"><span data-stu-id="3e80b-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="3e80b-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-435">Six digits</span></span>
    
- <span data-ttu-id="3e80b-436">4桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3e80b-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-437">Checksum</span></span>

<span data-ttu-id="3e80b-438">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-439">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-439">Definition</span></span>

<span data-ttu-id="3e80b-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-441">正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-442">From `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-443">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-443">Keywords</span></span>

<span data-ttu-id="3e80b-444">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-444"></span></span>
|<span data-ttu-id="3e80b-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-446">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-446">dl#</span></span>  <br/> <span data-ttu-id="3e80b-447">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-447">driver license</span></span>  <br/> <span data-ttu-id="3e80b-448">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-448">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-449">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-449">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-450">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-450">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-451">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-452">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-453">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-454">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-455">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-455">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-456">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-456">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-457">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="3e80b-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="3e80b-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="3e80b-459">Italy</span></span>

<span data-ttu-id="3e80b-460">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e80b-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="3e80b-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="3e80b-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-462">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-462">Format</span></span>

<span data-ttu-id="3e80b-463">3つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-464">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-464">Pattern</span></span>

<span data-ttu-id="3e80b-465">3つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3e80b-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="3e80b-466">3桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3e80b-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3e80b-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-468">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-468">Checksum</span></span>

<span data-ttu-id="3e80b-469">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-470">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-470">Definition</span></span>

<span data-ttu-id="3e80b-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-472">正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-473">From `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-474">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-474">Keywords</span></span>

<span data-ttu-id="3e80b-475">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-475"></span></span>
|<span data-ttu-id="3e80b-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-477">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-477">dl#</span></span>  <br/> <span data-ttu-id="3e80b-478">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-478">driver license</span></span>  <br/> <span data-ttu-id="3e80b-479">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-479">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-480">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-480">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-481">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-481">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-482">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-483">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-484">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-485">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-486">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-486">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-487">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-487">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-488">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="3e80b-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="3e80b-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="3e80b-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-491">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-491">Format</span></span>

<span data-ttu-id="3e80b-492">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-493">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-493">Pattern</span></span>

 <span data-ttu-id="3e80b-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3e80b-495">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-495">Checksum</span></span>

<span data-ttu-id="3e80b-496">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-497">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-497">Definition</span></span>

<span data-ttu-id="3e80b-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-499">正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-500">From `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-501">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-501">Keywords</span></span>

<span data-ttu-id="3e80b-502">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-502"></span></span>
|<span data-ttu-id="3e80b-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-504">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-504">dl#</span></span>  <br/> <span data-ttu-id="3e80b-505">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-505">driver license</span></span>  <br/> <span data-ttu-id="3e80b-506">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-506">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-507">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-507">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-508">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-508">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-509">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-510">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-511">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-512">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-513">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-513">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-514">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-514">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-515">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-516">vエア uotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="3e80b-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="3e80b-517">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="3e80b-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-518">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-518">Format</span></span>

<span data-ttu-id="3e80b-519">スペースと区切り文字を含まない6桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-520">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-520">Pattern</span></span>

 <span data-ttu-id="3e80b-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3e80b-522">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-522">Checksum</span></span>

<span data-ttu-id="3e80b-523">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-524">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-524">Definition</span></span>

<span data-ttu-id="3e80b-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-526">正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-527">From `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-528">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-528">Keywords</span></span>

<span data-ttu-id="3e80b-529">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-529"></span></span>
|<span data-ttu-id="3e80b-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-531">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-531">dl#</span></span>  <br/> <span data-ttu-id="3e80b-532">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-532">driver license</span></span>  <br/> <span data-ttu-id="3e80b-533">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-533">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-534">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-534">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-535">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-535">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-536">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-537">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-538">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-539">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-540">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-540">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-541">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-541">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-542">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-543">fahて fabnis</span><span class="sxs-lookup"><span data-stu-id="3e80b-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="3e80b-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="3e80b-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-545">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-545">Format</span></span>

<span data-ttu-id="3e80b-546">指定したパターンの2つの文字と6桁の数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="3e80b-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-547">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-547">Pattern</span></span>

<span data-ttu-id="3e80b-548">2つの文字と6桁の数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="3e80b-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="3e80b-549">2つの文字 (大文字小文字を区別しない数字または文字)</span><span class="sxs-lookup"><span data-stu-id="3e80b-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="3e80b-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="3e80b-550">A space (optional)</span></span>
    
- <span data-ttu-id="3e80b-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-551">Three digits</span></span>
    
- <span data-ttu-id="3e80b-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="3e80b-552">A space (optional)</span></span>
    
- <span data-ttu-id="3e80b-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-554">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-554">Checksum</span></span>

<span data-ttu-id="3e80b-555">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-556">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-556">Definition</span></span>

<span data-ttu-id="3e80b-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-558">正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-559">From `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-560">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-560">Keywords</span></span>

<span data-ttu-id="3e80b-561">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-561"></span></span>
|<span data-ttu-id="3e80b-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-563">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-563">dl#</span></span>  <br/> <span data-ttu-id="3e80b-564">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-564">driver license</span></span>  <br/> <span data-ttu-id="3e80b-565">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-565">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-566">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-566">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-567">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-567">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-568">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-569">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-570">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-571">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-572">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-572">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-573">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-573">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-574">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="3e80b-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="3e80b-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="3e80b-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-577">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-577">Format</span></span>

<span data-ttu-id="3e80b-578">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-579">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-579">Pattern</span></span>

<span data-ttu-id="3e80b-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-581">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-581">Checksum</span></span>

<span data-ttu-id="3e80b-582">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-583">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-583">Definition</span></span>

<span data-ttu-id="3e80b-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-585">正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-586">From `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-587">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-587">Keywords</span></span>

<span data-ttu-id="3e80b-588">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-588"></span></span>
|<span data-ttu-id="3e80b-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-590">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-590">dl#</span></span>  <br/> <span data-ttu-id="3e80b-591">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-591">driver license</span></span>  <br/> <span data-ttu-id="3e80b-592">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-592">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-593">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-593">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-594">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-594">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-595">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-596">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-597">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-598">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-599">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-599">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-600">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-600">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-601">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="3e80b-602">permis de conduire</span></span>  <br/> <span data-ttu-id="3e80b-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="3e80b-603">rijbewijs</span></span>  <br/> <span data-ttu-id="3e80b-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="3e80b-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="3e80b-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="3e80b-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-606">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-606">Format</span></span>

<span data-ttu-id="3e80b-607">2つのスラッシュを含む14桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-608">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-608">Pattern</span></span>

<span data-ttu-id="3e80b-609">14桁の数字と2つのスラッシュ:</span><span class="sxs-lookup"><span data-stu-id="3e80b-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="3e80b-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-610">Five digits</span></span> 
    
- <span data-ttu-id="3e80b-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="3e80b-611">A forward slash</span></span>
    
- <span data-ttu-id="3e80b-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-612">Two digits</span></span>
    
- <span data-ttu-id="3e80b-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="3e80b-613">A forward slash</span></span>
    
- <span data-ttu-id="3e80b-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-615">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-615">Checksum</span></span>

<span data-ttu-id="3e80b-616">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-617">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-617">Definition</span></span>

<span data-ttu-id="3e80b-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-619">正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-620">From `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-621">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-621">Keywords</span></span>

<span data-ttu-id="3e80b-622">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-622"></span></span>
|<span data-ttu-id="3e80b-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-624">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-624">dl#</span></span>  <br/> <span data-ttu-id="3e80b-625">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-625">driver license</span></span>  <br/> <span data-ttu-id="3e80b-626">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-626">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-627">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-627">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-628">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-628">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-629">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-630">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-631">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-632">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-633">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-633">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-634">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-634">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-635">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="3e80b-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="3e80b-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="3e80b-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-638">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-638">Format</span></span>

<span data-ttu-id="3e80b-639">指定したパターンの2文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-640">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-640">Pattern</span></span>

<span data-ttu-id="3e80b-641">2つの文字の後に特殊文字を含む7個の数字。</span><span class="sxs-lookup"><span data-stu-id="3e80b-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="3e80b-642">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3e80b-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3e80b-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="3e80b-643">A hyphen</span></span>
    
- <span data-ttu-id="3e80b-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-644">Six digits</span></span>
    
- <span data-ttu-id="3e80b-645">スペース</span><span class="sxs-lookup"><span data-stu-id="3e80b-645">A space</span></span>
    
- <span data-ttu-id="3e80b-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-647">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-647">Checksum</span></span>

<span data-ttu-id="3e80b-648">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-649">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-649">Definition</span></span>

<span data-ttu-id="3e80b-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-651">正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-652">From `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-653">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-653">Keywords</span></span>

<span data-ttu-id="3e80b-654">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-654"></span></span>
|<span data-ttu-id="3e80b-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-656">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-656">dl#</span></span>  <br/> <span data-ttu-id="3e80b-657">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-657">driver license</span></span>  <br/> <span data-ttu-id="3e80b-658">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-658">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-659">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-659">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-660">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-660">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-661">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-662">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-663">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-664">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-665">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-665">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-666">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-666">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-667">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="3e80b-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="3e80b-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="3e80b-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-670">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-670">Format</span></span>

<span data-ttu-id="3e80b-671">1文字の後に8桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-672">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-672">Pattern</span></span>

<span data-ttu-id="3e80b-673">1文字の後に8桁の数字。</span><span class="sxs-lookup"><span data-stu-id="3e80b-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="3e80b-674">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="3e80b-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-676">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-676">Checksum</span></span>

<span data-ttu-id="3e80b-677">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-678">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-678">Definition</span></span>

<span data-ttu-id="3e80b-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-680">正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-681">From `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-682">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-682">Keywords</span></span>

<span data-ttu-id="3e80b-683">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-683"></span></span>
|<span data-ttu-id="3e80b-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-685">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-685">dl#</span></span>  <br/> <span data-ttu-id="3e80b-686">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-686">driver license</span></span>  <br/> <span data-ttu-id="3e80b-687">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-687">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-688">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-688">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-689">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-689">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-690">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-691">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-692">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-693">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-694">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-694">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-695">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-695">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-696">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="3e80b-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="3e80b-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="3e80b-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-699">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-699">Format</span></span>

<span data-ttu-id="3e80b-700">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-701">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-701">Pattern</span></span>

<span data-ttu-id="3e80b-702">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="3e80b-703">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="3e80b-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3e80b-705">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-705">Checksum</span></span>

<span data-ttu-id="3e80b-706">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-707">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-707">Definition</span></span>

<span data-ttu-id="3e80b-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-709">正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-710">From `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-711">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-711">Keywords</span></span>

<span data-ttu-id="3e80b-712">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-712"></span></span>
|<span data-ttu-id="3e80b-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-714">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-714">dl#</span></span>  <br/> <span data-ttu-id="3e80b-715">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-715">driver license</span></span>  <br/> <span data-ttu-id="3e80b-716">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-716">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-717">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-717">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-718">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-718">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-719">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-720">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-721">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-722">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-723">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-723">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-724">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-724">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-725">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="3e80b-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="3e80b-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="3e80b-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-728">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-728">Format</span></span>

<span data-ttu-id="3e80b-729">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-730">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-730">Pattern</span></span>

<span data-ttu-id="3e80b-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3e80b-732">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-732">Checksum</span></span>

<span data-ttu-id="3e80b-733">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-734">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-734">Definition</span></span>

<span data-ttu-id="3e80b-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-736">正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-737">From `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-738">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-738">Keywords</span></span>

<span data-ttu-id="3e80b-739">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-739"></span></span>
|<span data-ttu-id="3e80b-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-741">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-741">dl#</span></span>  <br/> <span data-ttu-id="3e80b-742">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-742">driver license</span></span>  <br/> <span data-ttu-id="3e80b-743">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-743">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-744">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-744">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-745">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-745">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-746">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-747">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-748">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-749">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-750">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-750">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-751">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-751">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-752">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="3e80b-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="3e80b-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="3e80b-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-755">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-755">Format</span></span>

<span data-ttu-id="3e80b-756">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="3e80b-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-757">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-757">Pattern</span></span>

<span data-ttu-id="3e80b-758">8桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="3e80b-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="3e80b-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-759">Eight digits</span></span> 
    
- <span data-ttu-id="3e80b-760">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3e80b-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-761">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-761">Checksum</span></span>

<span data-ttu-id="3e80b-762">はい</span><span class="sxs-lookup"><span data-stu-id="3e80b-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-763">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-763">Definition</span></span>

<span data-ttu-id="3e80b-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-765">関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-766">From `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3e80b-767">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-767">Keywords</span></span>

<span data-ttu-id="3e80b-768">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-768"></span></span>
|<span data-ttu-id="3e80b-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-770">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-771">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-771">dl#</span></span>  <br/> <span data-ttu-id="3e80b-772">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-772">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-773">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-773">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-774">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-774">driver license</span></span>  <br/> <span data-ttu-id="3e80b-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-775">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-776">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-777">driver's licence</span></span>  <br/> <span data-ttu-id="3e80b-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-778">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-779">driving licence</span></span>  <br/> <span data-ttu-id="3e80b-780">driving license</span><span class="sxs-lookup"><span data-stu-id="3e80b-780">driving license</span></span>  <br/> <span data-ttu-id="3e80b-781">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-781">driver licence number</span></span>  <br/> <span data-ttu-id="3e80b-782">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-782">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-783">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-783">drivers licence number</span></span>  <br/> <span data-ttu-id="3e80b-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-784">drivers license number</span></span>  <br/> <span data-ttu-id="3e80b-785">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-785">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-786">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-787">ライセンス番号の運転</span><span class="sxs-lookup"><span data-stu-id="3e80b-787">driving licence number</span></span>  <br/> <span data-ttu-id="3e80b-788">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-788">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-789">許可の推進</span><span class="sxs-lookup"><span data-stu-id="3e80b-789">driving permit</span></span>  <br/> <span data-ttu-id="3e80b-790">許可番号の運転</span><span class="sxs-lookup"><span data-stu-id="3e80b-790">driving permit number</span></span>  <br/> <span data-ttu-id="3e80b-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="3e80b-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="3e80b-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="3e80b-792">permiso conducción</span></span>  <br/> <span data-ttu-id="3e80b-793">número/encia conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="3e80b-794">número デカーネット de conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="3e80b-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="3e80b-796">/暗号化 ia conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-796">licencia conducir</span></span>  <br/> <span data-ttu-id="3e80b-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="3e80b-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="3e80b-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="3e80b-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-800">permiso conducir</span></span>  <br/> <span data-ttu-id="3e80b-801">-encia de manejo</span><span class="sxs-lookup"><span data-stu-id="3e80b-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="3e80b-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="3e80b-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="3e80b-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="3e80b-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="3e80b-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="3e80b-805">Format</span><span class="sxs-lookup"><span data-stu-id="3e80b-805">Format</span></span>

<span data-ttu-id="3e80b-806">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="3e80b-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3e80b-807">パターン</span><span class="sxs-lookup"><span data-stu-id="3e80b-807">Pattern</span></span>

<span data-ttu-id="3e80b-808">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3e80b-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="3e80b-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-809">Six digits</span></span> 
    
- <span data-ttu-id="3e80b-810">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="3e80b-810">A hyphen</span></span>
    
- <span data-ttu-id="3e80b-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3e80b-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3e80b-812">チェックサム</span><span class="sxs-lookup"><span data-stu-id="3e80b-812">Checksum</span></span>

<span data-ttu-id="3e80b-813">いいえ</span><span class="sxs-lookup"><span data-stu-id="3e80b-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3e80b-814">定義</span><span class="sxs-lookup"><span data-stu-id="3e80b-814">Definition</span></span>

<span data-ttu-id="3e80b-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3e80b-816">正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3e80b-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3e80b-817">From `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3e80b-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="3e80b-818">キーワード</span><span class="sxs-lookup"><span data-stu-id="3e80b-818">Keywords</span></span>

<span data-ttu-id="3e80b-819">| |</span><span class="sxs-lookup"><span data-stu-id="3e80b-819"></span></span>
|<span data-ttu-id="3e80b-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="3e80b-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3e80b-821">dl#</span><span class="sxs-lookup"><span data-stu-id="3e80b-821">dl#</span></span>  <br/> <span data-ttu-id="3e80b-822">driver license</span><span class="sxs-lookup"><span data-stu-id="3e80b-822">driver license</span></span>  <br/> <span data-ttu-id="3e80b-823">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-823">driver license number</span></span>  <br/> <span data-ttu-id="3e80b-824">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="3e80b-824">driver licence</span></span>  <br/> <span data-ttu-id="3e80b-825">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="3e80b-825">drivers lic.</span></span>  <br/> <span data-ttu-id="3e80b-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="3e80b-826">drivers license</span></span>  <br/> <span data-ttu-id="3e80b-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3e80b-827">drivers licence</span></span>  <br/> <span data-ttu-id="3e80b-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="3e80b-828">driver's license</span></span>  <br/> <span data-ttu-id="3e80b-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-829">driver's license number</span></span>  <br/> <span data-ttu-id="3e80b-830">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-830">driver's licence number</span></span>  <br/> <span data-ttu-id="3e80b-831">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="3e80b-831">driving license number</span></span>  <br/> <span data-ttu-id="3e80b-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="3e80b-832">dlno#</span></span>  <br/> <span data-ttu-id="3e80b-833">körkort</span><span class="sxs-lookup"><span data-stu-id="3e80b-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="3e80b-834">佐賀</span><span class="sxs-lookup"><span data-stu-id="3e80b-834">UK</span></span>

<span data-ttu-id="3e80b-835">詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="3e80b-835">For details, see the section "U.K.</span></span> <span data-ttu-id="3e80b-836">[[機密情報の種類](what-the-sensitive-information-types-look-for.md)] に表示される運転免許証番号。</span><span class="sxs-lookup"><span data-stu-id="3e80b-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e80b-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e80b-837">See also</span></span>

[<span data-ttu-id="3e80b-838">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="3e80b-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

