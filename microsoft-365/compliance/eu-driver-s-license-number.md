---
title: EU 運転免許証番号
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
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805960"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="47a25-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-104">EU Driver's License Number</span></span>

<span data-ttu-id="47a25-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="47a25-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="47a25-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="47a25-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="47a25-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="47a25-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="47a25-108">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-108">Format</span></span>

<span data-ttu-id="47a25-109">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-110">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-110">Pattern</span></span>

<span data-ttu-id="47a25-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-112">Checksum</span></span>

<span data-ttu-id="47a25-113">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-114">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-114">Definition</span></span>

<span data-ttu-id="47a25-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-116">正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-117">From `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="47a25-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-118">Keywords</span></span>

<span data-ttu-id="47a25-119">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-119"></span></span>
|<span data-ttu-id="47a25-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-121">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-121">dl#</span></span>  <br/> <span data-ttu-id="47a25-122">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-122">driver license</span></span>  <br/> <span data-ttu-id="47a25-123">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-123">driver license number</span></span>  <br/> <span data-ttu-id="47a25-124">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-124">driver licence</span></span>  <br/> <span data-ttu-id="47a25-125">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-125">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-126">drivers license</span></span>  <br/> <span data-ttu-id="47a25-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="47a25-127">driver's licence</span></span>  <br/> <span data-ttu-id="47a25-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-128">driver's license</span></span>  <br/> <span data-ttu-id="47a25-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-129">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-130">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="47a25-131">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-131">driving license number</span></span>  <br/> <span data-ttu-id="47a25-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-132">dlno#</span></span>  <br/> <span data-ttu-id="47a25-133">futex</span><span class="sxs-lookup"><span data-stu-id="47a25-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="47a25-134">futex (futex) republik osterreich</span><span class="sxs-lookup"><span data-stu-id="47a25-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="47a25-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="47a25-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="47a25-136">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-136">Format</span></span>

<span data-ttu-id="47a25-137">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-138">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-138">Pattern</span></span>

<span data-ttu-id="47a25-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-140">Checksum</span></span>

<span data-ttu-id="47a25-141">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-142">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-142">Definition</span></span>

<span data-ttu-id="47a25-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-144">正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-145">From `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="47a25-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-146">Keywords</span></span>

<span data-ttu-id="47a25-147">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-147"></span></span>
|<span data-ttu-id="47a25-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-149">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-149">dl#</span></span>  <br/> <span data-ttu-id="47a25-150">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-150">driver license</span></span>  <br/> <span data-ttu-id="47a25-151">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-151">driver license number</span></span>  <br/> <span data-ttu-id="47a25-152">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-152">driver licence</span></span>  <br/> <span data-ttu-id="47a25-153">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-153">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-154">drivers license</span></span>  <br/> <span data-ttu-id="47a25-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-155">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-156">driver's license</span></span>  <br/> <span data-ttu-id="47a25-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-157">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-158">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-158">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-159">dlno#</span></span>  <br/> <span data-ttu-id="47a25-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="47a25-160">rijbewijs</span></span>  <br/> <span data-ttu-id="47a25-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="47a25-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="47a25-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="47a25-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="47a25-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="47a25-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="47a25-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="47a25-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="47a25-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="47a25-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="47a25-166">futex の eh/Nr</span><span class="sxs-lookup"><span data-stu-id="47a25-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="47a25-167">futex の eh/nr</span><span class="sxs-lookup"><span data-stu-id="47a25-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="47a25-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="47a25-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="47a25-169">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-169">Format</span></span>

<span data-ttu-id="47a25-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-171">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-171">Pattern</span></span>

<span data-ttu-id="47a25-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-173">Checksum</span></span>

<span data-ttu-id="47a25-174">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-175">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-175">Definition</span></span>

<span data-ttu-id="47a25-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-177">正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-178">From `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="47a25-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-179">Keywords</span></span>

<span data-ttu-id="47a25-180">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-180"></span></span>
|<span data-ttu-id="47a25-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-182">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-182">dl#</span></span>  <br/> <span data-ttu-id="47a25-183">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-183">driver license</span></span>  <br/> <span data-ttu-id="47a25-184">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-184">driver license number</span></span>  <br/> <span data-ttu-id="47a25-185">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-185">driver licence</span></span>  <br/> <span data-ttu-id="47a25-186">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-186">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-187">drivers license</span></span>  <br/> <span data-ttu-id="47a25-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-188">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-189">driver's license</span></span>  <br/> <span data-ttu-id="47a25-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-190">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-191">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-191">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-192">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-192">driving license number</span></span>  <br/> <span data-ttu-id="47a25-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-193">dlno#</span></span>  <br/> <span data-ttu-id="47a25-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="47a25-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="47a25-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="47a25-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="47a25-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="47a25-196">сумпс</span></span>  <br/> <span data-ttu-id="47a25-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="47a25-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="47a25-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="47a25-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="47a25-199">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-199">Format</span></span>

<span data-ttu-id="47a25-200">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-201">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-201">Pattern</span></span>

<span data-ttu-id="47a25-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-203">Checksum</span></span>

<span data-ttu-id="47a25-204">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-205">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-205">Definition</span></span>

<span data-ttu-id="47a25-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-207">正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-208">From `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="47a25-209">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-209">Keywords</span></span>

<span data-ttu-id="47a25-210">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-210"></span></span>
|<span data-ttu-id="47a25-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-212">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-212">dl#</span></span>  <br/> <span data-ttu-id="47a25-213">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-213">driver license</span></span>  <br/> <span data-ttu-id="47a25-214">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-214">driver license number</span></span>  <br/> <span data-ttu-id="47a25-215">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-215">driver licence</span></span>  <br/> <span data-ttu-id="47a25-216">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-216">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-217">drivers license</span></span>  <br/> <span data-ttu-id="47a25-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-218">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-219">driver's license</span></span>  <br/> <span data-ttu-id="47a25-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-220">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-221">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-221">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-222">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-222">driving license number</span></span>  <br/> <span data-ttu-id="47a25-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-223">dlno#</span></span>  <br/> <span data-ttu-id="47a25-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="47a25-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="47a25-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="47a25-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="47a25-226">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-226">Format</span></span>

<span data-ttu-id="47a25-227">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="47a25-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-228">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-228">Pattern</span></span>

<span data-ttu-id="47a25-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-230">Checksum</span></span>

<span data-ttu-id="47a25-231">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-232">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-232">Definition</span></span>

<span data-ttu-id="47a25-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-234">正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-235">From `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-236">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-236">Keywords</span></span>

<span data-ttu-id="47a25-237">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-237"></span></span>
|<span data-ttu-id="47a25-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-239">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-239">dl#</span></span>  <br/> <span data-ttu-id="47a25-240">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-240">driver license</span></span>  <br/> <span data-ttu-id="47a25-241">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-241">driver license number</span></span>  <br/> <span data-ttu-id="47a25-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-242">driver licence</span></span>  <br/> <span data-ttu-id="47a25-243">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-243">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-244">drivers license</span></span>  <br/> <span data-ttu-id="47a25-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-245">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-246">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-247">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-247">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-248">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-248">driving license number</span></span>  <br/> <span data-ttu-id="47a25-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-249">dlno#</span></span>  <br/> <span data-ttu-id="47a25-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="47a25-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="47a25-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="47a25-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="47a25-252">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-252">Format</span></span>

<span data-ttu-id="47a25-253">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-254">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-254">Pattern</span></span>

<span data-ttu-id="47a25-255">8つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="47a25-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="47a25-256">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="47a25-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="47a25-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="47a25-257">A space (optional)</span></span>
    
- <span data-ttu-id="47a25-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-259">Checksum</span></span>

<span data-ttu-id="47a25-260">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-261">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-261">Definition</span></span>

<span data-ttu-id="47a25-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-263">正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-264">From `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="47a25-265">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-265">Keywords</span></span>

<span data-ttu-id="47a25-266">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-266"></span></span>
|<span data-ttu-id="47a25-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-268">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-268">dl#</span></span>  <br/> <span data-ttu-id="47a25-269">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-269">driver license</span></span>  <br/> <span data-ttu-id="47a25-270">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-270">driver license number</span></span>  <br/> <span data-ttu-id="47a25-271">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-271">driver licence</span></span>  <br/> <span data-ttu-id="47a25-272">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-272">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-273">drivers license</span></span>  <br/> <span data-ttu-id="47a25-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-274">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-275">driver's license</span></span>  <br/> <span data-ttu-id="47a25-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-276">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-277">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-278">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-278">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-279">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-279">driving license number</span></span>  <br/> <span data-ttu-id="47a25-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-280">dlno#</span></span>  <br/> <span data-ttu-id="47a25-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="47a25-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="47a25-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="47a25-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="47a25-283">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-283">Format</span></span>

<span data-ttu-id="47a25-284">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-285">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-285">Pattern</span></span>

<span data-ttu-id="47a25-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-287">Checksum</span></span>

<span data-ttu-id="47a25-288">はい</span><span class="sxs-lookup"><span data-stu-id="47a25-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-289">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-289">Definition</span></span>

<span data-ttu-id="47a25-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-291">正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-292">From `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="47a25-293">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-293">Keywords</span></span>

<span data-ttu-id="47a25-294">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-294"></span></span>
|<span data-ttu-id="47a25-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-296">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-296">dl#</span></span>  <br/> <span data-ttu-id="47a25-297">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-297">driver license</span></span>  <br/> <span data-ttu-id="47a25-298">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-298">driver license number</span></span>  <br/> <span data-ttu-id="47a25-299">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-299">driver licence</span></span>  <br/> <span data-ttu-id="47a25-300">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-300">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-301">drivers license</span></span>  <br/> <span data-ttu-id="47a25-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-302">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-303">driver's license</span></span>  <br/> <span data-ttu-id="47a25-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-304">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-305">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-305">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-306">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-306">driving license number</span></span>  <br/> <span data-ttu-id="47a25-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-307">dlno#</span></span>  <br/> <span data-ttu-id="47a25-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="47a25-308">kørekort</span></span>  <br/> <span data-ttu-id="47a25-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="47a25-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="47a25-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="47a25-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="47a25-311">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-311">Format</span></span>

<span data-ttu-id="47a25-312">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-313">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-313">Pattern</span></span>

<span data-ttu-id="47a25-314">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="47a25-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="47a25-315">文字 "ET" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="47a25-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="47a25-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-317">Checksum</span></span>

<span data-ttu-id="47a25-318">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-319">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-319">Definition</span></span>

<span data-ttu-id="47a25-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-321">正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-322">From `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-323">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-323">Keywords</span></span>

<span data-ttu-id="47a25-324">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-324"></span></span>
|<span data-ttu-id="47a25-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-326">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-326">dl#</span></span>  <br/> <span data-ttu-id="47a25-327">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-327">driver license</span></span>  <br/> <span data-ttu-id="47a25-328">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-328">driver license number</span></span>  <br/> <span data-ttu-id="47a25-329">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-329">driver license number</span></span>  <br/> <span data-ttu-id="47a25-330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-330">driver licence</span></span>  <br/> <span data-ttu-id="47a25-331">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-331">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-332">drivers license</span></span>  <br/> <span data-ttu-id="47a25-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-333">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-334">driver's license</span></span>  <br/> <span data-ttu-id="47a25-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-335">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-336">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-336">driving license number</span></span>  <br/> <span data-ttu-id="47a25-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-337">dlno#</span></span>  <br/> <span data-ttu-id="47a25-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="47a25-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="47a25-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="47a25-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="47a25-340">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-340">Format</span></span>

<span data-ttu-id="47a25-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-342">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-342">Pattern</span></span>

<span data-ttu-id="47a25-343">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="47a25-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="47a25-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-344">Six digits</span></span> 
    
- <span data-ttu-id="47a25-345">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="47a25-345">A hyphen</span></span>
    
-  <span data-ttu-id="47a25-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="47a25-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-347">Checksum</span></span>

<span data-ttu-id="47a25-348">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-349">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-349">Definition</span></span>

<span data-ttu-id="47a25-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-351">正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-352">From `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-353">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-353">Keywords</span></span>

<span data-ttu-id="47a25-354">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-354"></span></span>
|<span data-ttu-id="47a25-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-356">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-356">dl#</span></span>  <br/> <span data-ttu-id="47a25-357">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-357">driver license</span></span>  <br/> <span data-ttu-id="47a25-358">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-358">driver license number</span></span>  <br/> <span data-ttu-id="47a25-359">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-359">driver licence</span></span>  <br/> <span data-ttu-id="47a25-360">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-360">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-361">drivers license</span></span>  <br/> <span data-ttu-id="47a25-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-362">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-363">driver's license</span></span>  <br/> <span data-ttu-id="47a25-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-364">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-365">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-365">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-366">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-366">driving license number</span></span>  <br/> <span data-ttu-id="47a25-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-367">dlno#</span></span>  <br/> <span data-ttu-id="47a25-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="47a25-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="47a25-369">フランス</span><span class="sxs-lookup"><span data-stu-id="47a25-369">France</span></span>

<span data-ttu-id="47a25-370">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47a25-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="47a25-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="47a25-371">Germany</span></span>

<span data-ttu-id="47a25-372">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47a25-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="47a25-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="47a25-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="47a25-374">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-374">Format</span></span>

<span data-ttu-id="47a25-375">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-376">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-376">Pattern</span></span>

 <span data-ttu-id="47a25-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="47a25-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-378">Checksum</span></span>

<span data-ttu-id="47a25-379">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-380">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-380">Definition</span></span>

<span data-ttu-id="47a25-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-382">正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-383">From `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-384">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-384">Keywords</span></span>

<span data-ttu-id="47a25-385">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-385"></span></span>
|<span data-ttu-id="47a25-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-387">ライブラリ#</span><span class="sxs-lookup"><span data-stu-id="47a25-387">dlL#</span></span>  <br/> <span data-ttu-id="47a25-388">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-388">driver license</span></span>  <br/> <span data-ttu-id="47a25-389">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-389">driver license number</span></span>  <br/> <span data-ttu-id="47a25-390">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-390">driver licence</span></span>  <br/> <span data-ttu-id="47a25-391">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-391">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-392">drivers license</span></span>  <br/> <span data-ttu-id="47a25-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-393">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-394">driver's license</span></span>  <br/> <span data-ttu-id="47a25-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-395">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-396">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-396">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-397">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-397">driving license number</span></span>  <br/> <span data-ttu-id="47a25-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-398">dlno#</span></span>  <br/> <span data-ttu-id="47a25-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="47a25-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="47a25-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="47a25-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="47a25-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="47a25-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="47a25-402">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-402">Format</span></span>

<span data-ttu-id="47a25-403">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-404">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-404">Pattern</span></span>

<span data-ttu-id="47a25-405">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="47a25-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="47a25-406">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="47a25-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="47a25-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-408">Checksum</span></span>

<span data-ttu-id="47a25-409">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-410">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-410">Definition</span></span>

<span data-ttu-id="47a25-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-412">正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-413">From `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-414">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-414">Keywords</span></span>

<span data-ttu-id="47a25-415">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-415"></span></span>
|<span data-ttu-id="47a25-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-417">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-417">dl#</span></span>  <br/> <span data-ttu-id="47a25-418">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-418">driver license</span></span>  <br/> <span data-ttu-id="47a25-419">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-419">driver license number</span></span>  <br/> <span data-ttu-id="47a25-420">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-420">driver licence</span></span>  <br/> <span data-ttu-id="47a25-421">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-421">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-422">drivers license</span></span>  <br/> <span data-ttu-id="47a25-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-423">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-424">driver's license</span></span>  <br/> <span data-ttu-id="47a25-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-425">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-426">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-426">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-427">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-427">driving license number</span></span>  <br/> <span data-ttu-id="47a25-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-428">dlno#</span></span>  <br/> <span data-ttu-id="47a25-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="47a25-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="47a25-430">アイルランド</span><span class="sxs-lookup"><span data-stu-id="47a25-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="47a25-431">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-431">Format</span></span>

<span data-ttu-id="47a25-432">6桁の数字の後に4文字</span><span class="sxs-lookup"><span data-stu-id="47a25-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-433">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-433">Pattern</span></span>

<span data-ttu-id="47a25-434">6桁の数字と4文字:</span><span class="sxs-lookup"><span data-stu-id="47a25-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="47a25-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-435">Six digits</span></span>
    
- <span data-ttu-id="47a25-436">4桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="47a25-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-437">Checksum</span></span>

<span data-ttu-id="47a25-438">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-439">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-439">Definition</span></span>

<span data-ttu-id="47a25-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-441">正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-442">From `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-443">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-443">Keywords</span></span>

<span data-ttu-id="47a25-444">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-444"></span></span>
|<span data-ttu-id="47a25-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-446">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-446">dl#</span></span>  <br/> <span data-ttu-id="47a25-447">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-447">driver license</span></span>  <br/> <span data-ttu-id="47a25-448">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-448">driver license number</span></span>  <br/> <span data-ttu-id="47a25-449">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-449">driver licence</span></span>  <br/> <span data-ttu-id="47a25-450">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-450">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-451">drivers license</span></span>  <br/> <span data-ttu-id="47a25-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-452">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-453">driver's license</span></span>  <br/> <span data-ttu-id="47a25-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-454">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-455">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-455">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-456">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-456">driving license number</span></span>  <br/> <span data-ttu-id="47a25-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-457">dlno#</span></span>  <br/> <span data-ttu-id="47a25-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="47a25-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="47a25-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="47a25-459">Italy</span></span>

<span data-ttu-id="47a25-460">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47a25-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="47a25-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="47a25-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="47a25-462">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-462">Format</span></span>

<span data-ttu-id="47a25-463">3つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-464">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-464">Pattern</span></span>

<span data-ttu-id="47a25-465">3つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="47a25-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="47a25-466">3桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="47a25-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="47a25-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-468">Checksum</span></span>

<span data-ttu-id="47a25-469">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-470">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-470">Definition</span></span>

<span data-ttu-id="47a25-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-472">正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-473">From `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-474">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-474">Keywords</span></span>

<span data-ttu-id="47a25-475">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-475"></span></span>
|<span data-ttu-id="47a25-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-477">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-477">dl#</span></span>  <br/> <span data-ttu-id="47a25-478">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-478">driver license</span></span>  <br/> <span data-ttu-id="47a25-479">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-479">driver license number</span></span>  <br/> <span data-ttu-id="47a25-480">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-480">driver licence</span></span>  <br/> <span data-ttu-id="47a25-481">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-481">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-482">drivers license</span></span>  <br/> <span data-ttu-id="47a25-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-483">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-484">driver's license</span></span>  <br/> <span data-ttu-id="47a25-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-485">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-486">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-486">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-487">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-487">driving license number</span></span>  <br/> <span data-ttu-id="47a25-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-488">dlno#</span></span>  <br/> <span data-ttu-id="47a25-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="47a25-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="47a25-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="47a25-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="47a25-491">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-491">Format</span></span>

<span data-ttu-id="47a25-492">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-493">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-493">Pattern</span></span>

 <span data-ttu-id="47a25-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="47a25-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-495">Checksum</span></span>

<span data-ttu-id="47a25-496">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-497">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-497">Definition</span></span>

<span data-ttu-id="47a25-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-499">正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-500">From `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-501">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-501">Keywords</span></span>

<span data-ttu-id="47a25-502">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-502"></span></span>
|<span data-ttu-id="47a25-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-504">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-504">dl#</span></span>  <br/> <span data-ttu-id="47a25-505">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-505">driver license</span></span>  <br/> <span data-ttu-id="47a25-506">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-506">driver license number</span></span>  <br/> <span data-ttu-id="47a25-507">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-507">driver licence</span></span>  <br/> <span data-ttu-id="47a25-508">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-508">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-509">drivers license</span></span>  <br/> <span data-ttu-id="47a25-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-510">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-511">driver's license</span></span>  <br/> <span data-ttu-id="47a25-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-512">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-513">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-513">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-514">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-514">driving license number</span></span>  <br/> <span data-ttu-id="47a25-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-515">dlno#</span></span>  <br/> <span data-ttu-id="47a25-516">vエア uotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="47a25-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="47a25-517">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="47a25-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="47a25-518">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-518">Format</span></span>

<span data-ttu-id="47a25-519">スペースと区切り文字を含まない6桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-520">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-520">Pattern</span></span>

 <span data-ttu-id="47a25-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="47a25-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-522">Checksum</span></span>

<span data-ttu-id="47a25-523">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-524">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-524">Definition</span></span>

<span data-ttu-id="47a25-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-526">正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-527">From `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-528">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-528">Keywords</span></span>

<span data-ttu-id="47a25-529">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-529"></span></span>
|<span data-ttu-id="47a25-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-531">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-531">dl#</span></span>  <br/> <span data-ttu-id="47a25-532">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-532">driver license</span></span>  <br/> <span data-ttu-id="47a25-533">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-533">driver license number</span></span>  <br/> <span data-ttu-id="47a25-534">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-534">driver licence</span></span>  <br/> <span data-ttu-id="47a25-535">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-535">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-536">drivers license</span></span>  <br/> <span data-ttu-id="47a25-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-537">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-538">driver's license</span></span>  <br/> <span data-ttu-id="47a25-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-539">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-540">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-540">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-541">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-541">driving license number</span></span>  <br/> <span data-ttu-id="47a25-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-542">dlno#</span></span>  <br/> <span data-ttu-id="47a25-543">fahて fabnis</span><span class="sxs-lookup"><span data-stu-id="47a25-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="47a25-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="47a25-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="47a25-545">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-545">Format</span></span>

<span data-ttu-id="47a25-546">指定したパターンの2つの文字と6桁の数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="47a25-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-547">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-547">Pattern</span></span>

<span data-ttu-id="47a25-548">2つの文字と6桁の数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="47a25-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="47a25-549">2つの文字 (大文字小文字を区別しない数字または文字)</span><span class="sxs-lookup"><span data-stu-id="47a25-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="47a25-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="47a25-550">A space (optional)</span></span>
    
- <span data-ttu-id="47a25-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-551">Three digits</span></span>
    
- <span data-ttu-id="47a25-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="47a25-552">A space (optional)</span></span>
    
- <span data-ttu-id="47a25-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-554">Checksum</span></span>

<span data-ttu-id="47a25-555">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-556">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-556">Definition</span></span>

<span data-ttu-id="47a25-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-558">正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-559">From `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-560">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-560">Keywords</span></span>

<span data-ttu-id="47a25-561">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-561"></span></span>
|<span data-ttu-id="47a25-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-563">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-563">dl#</span></span>  <br/> <span data-ttu-id="47a25-564">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-564">driver license</span></span>  <br/> <span data-ttu-id="47a25-565">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-565">driver license number</span></span>  <br/> <span data-ttu-id="47a25-566">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-566">driver licence</span></span>  <br/> <span data-ttu-id="47a25-567">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-567">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-568">drivers license</span></span>  <br/> <span data-ttu-id="47a25-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-569">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-570">driver's license</span></span>  <br/> <span data-ttu-id="47a25-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-571">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-572">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-572">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-573">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-573">driving license number</span></span>  <br/> <span data-ttu-id="47a25-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-574">dlno#</span></span>  <br/> <span data-ttu-id="47a25-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="47a25-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="47a25-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="47a25-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="47a25-577">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-577">Format</span></span>

<span data-ttu-id="47a25-578">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-579">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-579">Pattern</span></span>

<span data-ttu-id="47a25-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-581">Checksum</span></span>

<span data-ttu-id="47a25-582">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-583">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-583">Definition</span></span>

<span data-ttu-id="47a25-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-585">正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-586">From `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-587">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-587">Keywords</span></span>

<span data-ttu-id="47a25-588">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-588"></span></span>
|<span data-ttu-id="47a25-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-590">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-590">dl#</span></span>  <br/> <span data-ttu-id="47a25-591">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-591">driver license</span></span>  <br/> <span data-ttu-id="47a25-592">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-592">driver license number</span></span>  <br/> <span data-ttu-id="47a25-593">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-593">driver licence</span></span>  <br/> <span data-ttu-id="47a25-594">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-594">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-595">drivers license</span></span>  <br/> <span data-ttu-id="47a25-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-596">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-597">driver's license</span></span>  <br/> <span data-ttu-id="47a25-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-598">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-599">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-599">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-600">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-600">driving license number</span></span>  <br/> <span data-ttu-id="47a25-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-601">dlno#</span></span>  <br/> <span data-ttu-id="47a25-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="47a25-602">permis de conduire</span></span>  <br/> <span data-ttu-id="47a25-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="47a25-603">rijbewijs</span></span>  <br/> <span data-ttu-id="47a25-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="47a25-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="47a25-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="47a25-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="47a25-606">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-606">Format</span></span>

<span data-ttu-id="47a25-607">2つのスラッシュを含む14桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-608">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-608">Pattern</span></span>

<span data-ttu-id="47a25-609">14桁の数字と2つのスラッシュ:</span><span class="sxs-lookup"><span data-stu-id="47a25-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="47a25-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-610">Five digits</span></span> 
    
- <span data-ttu-id="47a25-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="47a25-611">A forward slash</span></span>
    
- <span data-ttu-id="47a25-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-612">Two digits</span></span>
    
- <span data-ttu-id="47a25-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="47a25-613">A forward slash</span></span>
    
- <span data-ttu-id="47a25-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-615">Checksum</span></span>

<span data-ttu-id="47a25-616">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-617">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-617">Definition</span></span>

<span data-ttu-id="47a25-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-619">正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-620">From `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-621">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-621">Keywords</span></span>

<span data-ttu-id="47a25-622">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-622"></span></span>
|<span data-ttu-id="47a25-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-624">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-624">dl#</span></span>  <br/> <span data-ttu-id="47a25-625">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-625">driver license</span></span>  <br/> <span data-ttu-id="47a25-626">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-626">driver license number</span></span>  <br/> <span data-ttu-id="47a25-627">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-627">driver licence</span></span>  <br/> <span data-ttu-id="47a25-628">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-628">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-629">drivers license</span></span>  <br/> <span data-ttu-id="47a25-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-630">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-631">driver's license</span></span>  <br/> <span data-ttu-id="47a25-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-632">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-633">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-633">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-634">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-634">driving license number</span></span>  <br/> <span data-ttu-id="47a25-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-635">dlno#</span></span>  <br/> <span data-ttu-id="47a25-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="47a25-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="47a25-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="47a25-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="47a25-638">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-638">Format</span></span>

<span data-ttu-id="47a25-639">指定したパターンの2文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-640">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-640">Pattern</span></span>

<span data-ttu-id="47a25-641">2つの文字の後に特殊文字を含む7個の数字。</span><span class="sxs-lookup"><span data-stu-id="47a25-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="47a25-642">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="47a25-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="47a25-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="47a25-643">A hyphen</span></span>
    
- <span data-ttu-id="47a25-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-644">Six digits</span></span>
    
- <span data-ttu-id="47a25-645">スペース</span><span class="sxs-lookup"><span data-stu-id="47a25-645">A space</span></span>
    
- <span data-ttu-id="47a25-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-647">Checksum</span></span>

<span data-ttu-id="47a25-648">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-649">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-649">Definition</span></span>

<span data-ttu-id="47a25-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-651">正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-652">From `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-653">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-653">Keywords</span></span>

<span data-ttu-id="47a25-654">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-654"></span></span>
|<span data-ttu-id="47a25-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-656">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-656">dl#</span></span>  <br/> <span data-ttu-id="47a25-657">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-657">driver license</span></span>  <br/> <span data-ttu-id="47a25-658">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-658">driver license number</span></span>  <br/> <span data-ttu-id="47a25-659">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-659">driver licence</span></span>  <br/> <span data-ttu-id="47a25-660">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-660">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-661">drivers license</span></span>  <br/> <span data-ttu-id="47a25-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-662">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-663">driver's license</span></span>  <br/> <span data-ttu-id="47a25-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-664">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-665">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-665">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-666">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-666">driving license number</span></span>  <br/> <span data-ttu-id="47a25-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-667">dlno#</span></span>  <br/> <span data-ttu-id="47a25-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="47a25-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="47a25-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="47a25-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="47a25-670">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-670">Format</span></span>

<span data-ttu-id="47a25-671">1文字の後に8桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-672">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-672">Pattern</span></span>

<span data-ttu-id="47a25-673">1文字の後に8桁の数字。</span><span class="sxs-lookup"><span data-stu-id="47a25-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="47a25-674">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="47a25-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="47a25-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-676">Checksum</span></span>

<span data-ttu-id="47a25-677">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-678">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-678">Definition</span></span>

<span data-ttu-id="47a25-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-680">正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-681">From `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-682">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-682">Keywords</span></span>

<span data-ttu-id="47a25-683">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-683"></span></span>
|<span data-ttu-id="47a25-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-685">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-685">dl#</span></span>  <br/> <span data-ttu-id="47a25-686">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-686">driver license</span></span>  <br/> <span data-ttu-id="47a25-687">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-687">driver license number</span></span>  <br/> <span data-ttu-id="47a25-688">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-688">driver licence</span></span>  <br/> <span data-ttu-id="47a25-689">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-689">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-690">drivers license</span></span>  <br/> <span data-ttu-id="47a25-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-691">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-692">driver's license</span></span>  <br/> <span data-ttu-id="47a25-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-693">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-694">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-694">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-695">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-695">driving license number</span></span>  <br/> <span data-ttu-id="47a25-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-696">dlno#</span></span>  <br/> <span data-ttu-id="47a25-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="47a25-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="47a25-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="47a25-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="47a25-699">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-699">Format</span></span>

<span data-ttu-id="47a25-700">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-701">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-701">Pattern</span></span>

<span data-ttu-id="47a25-702">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="47a25-703">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="47a25-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="47a25-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="47a25-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-705">Checksum</span></span>

<span data-ttu-id="47a25-706">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-707">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-707">Definition</span></span>

<span data-ttu-id="47a25-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-709">正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-710">From `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-711">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-711">Keywords</span></span>

<span data-ttu-id="47a25-712">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-712"></span></span>
|<span data-ttu-id="47a25-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-714">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-714">dl#</span></span>  <br/> <span data-ttu-id="47a25-715">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-715">driver license</span></span>  <br/> <span data-ttu-id="47a25-716">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-716">driver license number</span></span>  <br/> <span data-ttu-id="47a25-717">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-717">driver licence</span></span>  <br/> <span data-ttu-id="47a25-718">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-718">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-719">drivers license</span></span>  <br/> <span data-ttu-id="47a25-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-720">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-721">driver's license</span></span>  <br/> <span data-ttu-id="47a25-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-722">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-723">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-723">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-724">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-724">driving license number</span></span>  <br/> <span data-ttu-id="47a25-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-725">dlno#</span></span>  <br/> <span data-ttu-id="47a25-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="47a25-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="47a25-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="47a25-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="47a25-728">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-728">Format</span></span>

<span data-ttu-id="47a25-729">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-730">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-730">Pattern</span></span>

<span data-ttu-id="47a25-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="47a25-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-732">Checksum</span></span>

<span data-ttu-id="47a25-733">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-734">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-734">Definition</span></span>

<span data-ttu-id="47a25-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-736">正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-737">From `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-738">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-738">Keywords</span></span>

<span data-ttu-id="47a25-739">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-739"></span></span>
|<span data-ttu-id="47a25-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-741">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-741">dl#</span></span>  <br/> <span data-ttu-id="47a25-742">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-742">driver license</span></span>  <br/> <span data-ttu-id="47a25-743">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-743">driver license number</span></span>  <br/> <span data-ttu-id="47a25-744">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-744">driver licence</span></span>  <br/> <span data-ttu-id="47a25-745">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-745">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-746">drivers license</span></span>  <br/> <span data-ttu-id="47a25-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-747">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-748">driver's license</span></span>  <br/> <span data-ttu-id="47a25-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-749">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-750">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-750">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-751">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-751">driving license number</span></span>  <br/> <span data-ttu-id="47a25-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-752">dlno#</span></span>  <br/> <span data-ttu-id="47a25-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="47a25-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="47a25-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="47a25-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="47a25-755">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-755">Format</span></span>

<span data-ttu-id="47a25-756">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="47a25-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-757">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-757">Pattern</span></span>

<span data-ttu-id="47a25-758">8桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="47a25-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="47a25-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-759">Eight digits</span></span> 
    
- <span data-ttu-id="47a25-760">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="47a25-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-761">Checksum</span></span>

<span data-ttu-id="47a25-762">はい</span><span class="sxs-lookup"><span data-stu-id="47a25-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-763">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-763">Definition</span></span>

<span data-ttu-id="47a25-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-765">関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="47a25-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-766">From `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="47a25-767">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-767">Keywords</span></span>

<span data-ttu-id="47a25-768">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-768"></span></span>
|<span data-ttu-id="47a25-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-770">dlno#</span></span>  <br/> <span data-ttu-id="47a25-771">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-771">dl#</span></span>  <br/> <span data-ttu-id="47a25-772">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-772">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-773">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-773">driver licence</span></span>  <br/> <span data-ttu-id="47a25-774">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-774">driver license</span></span>  <br/> <span data-ttu-id="47a25-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-775">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-776">drivers license</span></span>  <br/> <span data-ttu-id="47a25-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="47a25-777">driver's licence</span></span>  <br/> <span data-ttu-id="47a25-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-778">driver's license</span></span>  <br/> <span data-ttu-id="47a25-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="47a25-779">driving licence</span></span>  <br/> <span data-ttu-id="47a25-780">driving license</span><span class="sxs-lookup"><span data-stu-id="47a25-780">driving license</span></span>  <br/> <span data-ttu-id="47a25-781">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-781">driver licence number</span></span>  <br/> <span data-ttu-id="47a25-782">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-782">driver license number</span></span>  <br/> <span data-ttu-id="47a25-783">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-783">drivers licence number</span></span>  <br/> <span data-ttu-id="47a25-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-784">drivers license number</span></span>  <br/> <span data-ttu-id="47a25-785">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-785">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-786">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-787">ライセンス番号の運転</span><span class="sxs-lookup"><span data-stu-id="47a25-787">driving licence number</span></span>  <br/> <span data-ttu-id="47a25-788">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-788">driving license number</span></span>  <br/> <span data-ttu-id="47a25-789">許可の推進</span><span class="sxs-lookup"><span data-stu-id="47a25-789">driving permit</span></span>  <br/> <span data-ttu-id="47a25-790">許可番号の運転</span><span class="sxs-lookup"><span data-stu-id="47a25-790">driving permit number</span></span>  <br/> <span data-ttu-id="47a25-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="47a25-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="47a25-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="47a25-792">permiso conducción</span></span>  <br/> <span data-ttu-id="47a25-793">número/encia conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="47a25-794">número デカーネット de conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="47a25-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="47a25-796">/暗号化 ia conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-796">licencia conducir</span></span>  <br/> <span data-ttu-id="47a25-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="47a25-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="47a25-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="47a25-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-800">permiso conducir</span></span>  <br/> <span data-ttu-id="47a25-801">-encia de manejo</span><span class="sxs-lookup"><span data-stu-id="47a25-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="47a25-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="47a25-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="47a25-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="47a25-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="47a25-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="47a25-805">Format</span><span class="sxs-lookup"><span data-stu-id="47a25-805">Format</span></span>

<span data-ttu-id="47a25-806">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="47a25-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="47a25-807">パターン</span><span class="sxs-lookup"><span data-stu-id="47a25-807">Pattern</span></span>

<span data-ttu-id="47a25-808">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="47a25-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="47a25-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-809">Six digits</span></span> 
    
- <span data-ttu-id="47a25-810">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="47a25-810">A hyphen</span></span>
    
- <span data-ttu-id="47a25-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="47a25-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="47a25-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="47a25-812">Checksum</span></span>

<span data-ttu-id="47a25-813">不要</span><span class="sxs-lookup"><span data-stu-id="47a25-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="47a25-814">定義</span><span class="sxs-lookup"><span data-stu-id="47a25-814">Definition</span></span>

<span data-ttu-id="47a25-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="47a25-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="47a25-816">正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="47a25-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="47a25-817">From `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47a25-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="47a25-818">キーワード</span><span class="sxs-lookup"><span data-stu-id="47a25-818">Keywords</span></span>

<span data-ttu-id="47a25-819">| |</span><span class="sxs-lookup"><span data-stu-id="47a25-819"></span></span>
|<span data-ttu-id="47a25-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="47a25-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="47a25-821">dl#</span><span class="sxs-lookup"><span data-stu-id="47a25-821">dl#</span></span>  <br/> <span data-ttu-id="47a25-822">driver license</span><span class="sxs-lookup"><span data-stu-id="47a25-822">driver license</span></span>  <br/> <span data-ttu-id="47a25-823">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-823">driver license number</span></span>  <br/> <span data-ttu-id="47a25-824">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="47a25-824">driver licence</span></span>  <br/> <span data-ttu-id="47a25-825">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="47a25-825">drivers lic.</span></span>  <br/> <span data-ttu-id="47a25-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="47a25-826">drivers license</span></span>  <br/> <span data-ttu-id="47a25-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="47a25-827">drivers licence</span></span>  <br/> <span data-ttu-id="47a25-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="47a25-828">driver's license</span></span>  <br/> <span data-ttu-id="47a25-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-829">driver's license number</span></span>  <br/> <span data-ttu-id="47a25-830">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="47a25-830">driver's licence number</span></span>  <br/> <span data-ttu-id="47a25-831">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="47a25-831">driving license number</span></span>  <br/> <span data-ttu-id="47a25-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="47a25-832">dlno#</span></span>  <br/> <span data-ttu-id="47a25-833">körkort</span><span class="sxs-lookup"><span data-stu-id="47a25-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="47a25-834">佐賀</span><span class="sxs-lookup"><span data-stu-id="47a25-834">UK</span></span>

<span data-ttu-id="47a25-835">詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="47a25-835">For details, see the section "U.K.</span></span> <span data-ttu-id="47a25-836">[[機密情報の種類](what-the-sensitive-information-types-look-for.md)] に表示される運転免許証番号。</span><span class="sxs-lookup"><span data-stu-id="47a25-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47a25-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="47a25-837">See also</span></span>

[<span data-ttu-id="47a25-838">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="47a25-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

