---
title: EU 運転免許証番号
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 2e75a8724dc91ef2d895c977fdd5fcc21e7a1da4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938831"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="9b0d2-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-104">EU Driver's License Number</span></span>

<span data-ttu-id="9b0d2-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="9b0d2-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9b0d2-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-108">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-108">Format</span></span>

<span data-ttu-id="9b0d2-109">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-110">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-110">Pattern</span></span>

<span data-ttu-id="9b0d2-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-112">Checksum</span></span>

<span data-ttu-id="9b0d2-113">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-114">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-114">Definition</span></span>

<span data-ttu-id="9b0d2-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-116">正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-117">From `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="9b0d2-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-118">Keywords</span></span>

<span data-ttu-id="9b0d2-119">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-119">| |</span></span>
|<span data-ttu-id="9b0d2-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-121">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-121">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-122">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-122">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-123">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-123">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-124">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-124">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-125">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-125">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-126">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-127">driver's licence</span></span>  <br/> <span data-ttu-id="9b0d2-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-128">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-129">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-130">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="9b0d2-131">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-131">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-132">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-133">futex</span><span class="sxs-lookup"><span data-stu-id="9b0d2-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="9b0d2-134">futex (futex) republik osterreich</span><span class="sxs-lookup"><span data-stu-id="9b0d2-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="9b0d2-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="9b0d2-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-136">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-136">Format</span></span>

<span data-ttu-id="9b0d2-137">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-138">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-138">Pattern</span></span>

<span data-ttu-id="9b0d2-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-140">Checksum</span></span>

<span data-ttu-id="9b0d2-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-142">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-142">Definition</span></span>

<span data-ttu-id="9b0d2-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-144">正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-145">From `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9b0d2-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-146">Keywords</span></span>

<span data-ttu-id="9b0d2-147">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-147">| |</span></span>
|<span data-ttu-id="9b0d2-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-149">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-149">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-150">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-150">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-151">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-151">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-152">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-152">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-153">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-153">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-154">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-155">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-156">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-157">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-158">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-158">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-159">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="9b0d2-160">rijbewijs</span></span>  <br/> <span data-ttu-id="9b0d2-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="9b0d2-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="9b0d2-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9b0d2-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="9b0d2-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9b0d2-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="9b0d2-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9b0d2-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="9b0d2-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="9b0d2-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="9b0d2-166">futex の eh/Nr</span><span class="sxs-lookup"><span data-stu-id="9b0d2-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="9b0d2-167">futex の eh/nr</span><span class="sxs-lookup"><span data-stu-id="9b0d2-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="9b0d2-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-169">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-169">Format</span></span>

<span data-ttu-id="9b0d2-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-171">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-171">Pattern</span></span>

<span data-ttu-id="9b0d2-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-173">Checksum</span></span>

<span data-ttu-id="9b0d2-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-175">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-175">Definition</span></span>

<span data-ttu-id="9b0d2-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-177">正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-178">From `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="9b0d2-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-179">Keywords</span></span>

<span data-ttu-id="9b0d2-180">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-180">| |</span></span>
|<span data-ttu-id="9b0d2-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-182">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-182">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-183">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-183">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-184">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-184">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-185">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-185">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-186">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-186">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-187">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-188">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-189">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-190">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-191">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-191">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-192">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-192">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-193">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="9b0d2-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="9b0d2-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="9b0d2-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="9b0d2-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="9b0d2-196">сумпс</span></span>  <br/> <span data-ttu-id="9b0d2-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="9b0d2-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="9b0d2-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-199">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-199">Format</span></span>

<span data-ttu-id="9b0d2-200">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-201">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-201">Pattern</span></span>

<span data-ttu-id="9b0d2-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-203">Checksum</span></span>

<span data-ttu-id="9b0d2-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-205">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-205">Definition</span></span>

<span data-ttu-id="9b0d2-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-207">正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-208">From `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9b0d2-209">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-209">Keywords</span></span>

<span data-ttu-id="9b0d2-210">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-210">| |</span></span>
|<span data-ttu-id="9b0d2-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-212">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-212">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-213">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-213">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-214">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-214">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-215">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-215">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-216">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-216">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-217">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-218">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-219">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-220">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-221">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-221">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-222">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-222">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-223">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="9b0d2-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="9b0d2-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-226">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-226">Format</span></span>

<span data-ttu-id="9b0d2-227">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-228">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-228">Pattern</span></span>

<span data-ttu-id="9b0d2-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-230">Checksum</span></span>

<span data-ttu-id="9b0d2-231">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-232">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-232">Definition</span></span>

<span data-ttu-id="9b0d2-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-234">正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-235">From `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-236">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-236">Keywords</span></span>

<span data-ttu-id="9b0d2-237">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-237">| |</span></span>
|<span data-ttu-id="9b0d2-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-239">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-239">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-240">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-240">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-241">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-241">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-242">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-243">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-243">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-244">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-245">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-246">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-247">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-247">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-248">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-248">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-249">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="9b0d2-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="9b0d2-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="9b0d2-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-252">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-252">Format</span></span>

<span data-ttu-id="9b0d2-253">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-254">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-254">Pattern</span></span>

<span data-ttu-id="9b0d2-255">8つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="9b0d2-256">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="9b0d2-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="9b0d2-257">A space (optional)</span></span>
    
- <span data-ttu-id="9b0d2-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-259">Checksum</span></span>

<span data-ttu-id="9b0d2-260">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-261">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-261">Definition</span></span>

<span data-ttu-id="9b0d2-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-263">正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-264">From `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9b0d2-265">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-265">Keywords</span></span>

<span data-ttu-id="9b0d2-266">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-266">| |</span></span>
|<span data-ttu-id="9b0d2-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-268">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-268">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-269">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-269">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-270">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-270">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-271">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-271">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-272">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-272">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-273">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-274">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-275">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-276">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-277">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-278">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-278">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-279">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-279">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-280">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="9b0d2-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="9b0d2-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="9b0d2-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-283">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-283">Format</span></span>

<span data-ttu-id="9b0d2-284">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-285">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-285">Pattern</span></span>

<span data-ttu-id="9b0d2-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-287">Checksum</span></span>

<span data-ttu-id="9b0d2-288">はい</span><span class="sxs-lookup"><span data-stu-id="9b0d2-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-289">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-289">Definition</span></span>

<span data-ttu-id="9b0d2-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-291">正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-292">From `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="9b0d2-293">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-293">Keywords</span></span>

<span data-ttu-id="9b0d2-294">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-294">| |</span></span>
|<span data-ttu-id="9b0d2-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-296">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-296">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-297">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-297">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-298">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-298">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-299">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-299">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-300">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-300">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-301">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-302">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-303">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-304">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-305">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-305">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-306">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-306">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-307">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="9b0d2-308">kørekort</span></span>  <br/> <span data-ttu-id="9b0d2-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="9b0d2-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="9b0d2-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-311">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-311">Format</span></span>

<span data-ttu-id="9b0d2-312">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-313">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-313">Pattern</span></span>

<span data-ttu-id="9b0d2-314">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="9b0d2-315">文字 "ET" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9b0d2-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-317">Checksum</span></span>

<span data-ttu-id="9b0d2-318">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-319">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-319">Definition</span></span>

<span data-ttu-id="9b0d2-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-321">正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-322">From `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-323">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-323">Keywords</span></span>

<span data-ttu-id="9b0d2-324">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-324">| |</span></span>
|<span data-ttu-id="9b0d2-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-326">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-326">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-327">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-327">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-328">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-328">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-329">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-329">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-330">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-331">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-331">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-332">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-333">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-334">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-335">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-336">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-336">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-337">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="9b0d2-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="9b0d2-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="9b0d2-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-340">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-340">Format</span></span>

<span data-ttu-id="9b0d2-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-342">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-342">Pattern</span></span>

<span data-ttu-id="9b0d2-343">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="9b0d2-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-344">Six digits</span></span> 
    
- <span data-ttu-id="9b0d2-345">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-345">A hyphen</span></span>
    
-  <span data-ttu-id="9b0d2-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-347">Checksum</span></span>

<span data-ttu-id="9b0d2-348">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-349">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-349">Definition</span></span>

<span data-ttu-id="9b0d2-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-351">正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-352">From `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-353">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-353">Keywords</span></span>

<span data-ttu-id="9b0d2-354">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-354">| |</span></span>
|<span data-ttu-id="9b0d2-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-356">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-356">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-357">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-357">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-358">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-358">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-359">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-359">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-360">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-360">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-361">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-362">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-363">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-364">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-365">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-365">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-366">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-366">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-367">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="9b0d2-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="9b0d2-369">フランス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-369">France</span></span>

<span data-ttu-id="9b0d2-370">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="9b0d2-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-371">Germany</span></span>

<span data-ttu-id="9b0d2-372">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="9b0d2-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-374">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-374">Format</span></span>

<span data-ttu-id="9b0d2-375">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-376">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-376">Pattern</span></span>

 <span data-ttu-id="9b0d2-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-378">Checksum</span></span>

<span data-ttu-id="9b0d2-379">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-380">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-380">Definition</span></span>

<span data-ttu-id="9b0d2-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-382">正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-383">From `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-384">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-384">Keywords</span></span>

<span data-ttu-id="9b0d2-385">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-385">| |</span></span>
|<span data-ttu-id="9b0d2-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-387">ライブラリ#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-387">dlL#</span></span>  <br/> <span data-ttu-id="9b0d2-388">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-388">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-389">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-389">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-390">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-390">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-391">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-391">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-392">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-393">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-394">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-395">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-396">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-396">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-397">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-397">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-398">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="9b0d2-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="9b0d2-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="9b0d2-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="9b0d2-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="9b0d2-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-402">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-402">Format</span></span>

<span data-ttu-id="9b0d2-403">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-404">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-404">Pattern</span></span>

<span data-ttu-id="9b0d2-405">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="9b0d2-406">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9b0d2-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-408">Checksum</span></span>

<span data-ttu-id="9b0d2-409">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-410">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-410">Definition</span></span>

<span data-ttu-id="9b0d2-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-412">正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-413">From `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-414">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-414">Keywords</span></span>

<span data-ttu-id="9b0d2-415">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-415">| |</span></span>
|<span data-ttu-id="9b0d2-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-417">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-417">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-418">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-418">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-419">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-419">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-420">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-420">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-421">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-421">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-422">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-423">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-424">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-425">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-426">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-426">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-427">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-427">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-428">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="9b0d2-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="9b0d2-430">アイルランド</span><span class="sxs-lookup"><span data-stu-id="9b0d2-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-431">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-431">Format</span></span>

<span data-ttu-id="9b0d2-432">6桁の数字の後に4文字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-433">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-433">Pattern</span></span>

<span data-ttu-id="9b0d2-434">6桁の数字と4文字:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="9b0d2-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-435">Six digits</span></span>
    
- <span data-ttu-id="9b0d2-436">4桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-437">Checksum</span></span>

<span data-ttu-id="9b0d2-438">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-439">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-439">Definition</span></span>

<span data-ttu-id="9b0d2-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-441">正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-442">From `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-443">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-443">Keywords</span></span>

<span data-ttu-id="9b0d2-444">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-444">| |</span></span>
|<span data-ttu-id="9b0d2-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-446">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-446">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-447">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-447">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-448">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-448">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-449">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-449">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-450">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-450">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-451">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-452">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-453">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-454">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-455">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-455">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-456">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-456">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-457">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="9b0d2-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="9b0d2-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-459">Italy</span></span>

<span data-ttu-id="9b0d2-460">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="9b0d2-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-462">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-462">Format</span></span>

<span data-ttu-id="9b0d2-463">3つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-464">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-464">Pattern</span></span>

<span data-ttu-id="9b0d2-465">3つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="9b0d2-466">3桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9b0d2-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-468">Checksum</span></span>

<span data-ttu-id="9b0d2-469">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-470">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-470">Definition</span></span>

<span data-ttu-id="9b0d2-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-472">正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-473">From `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-474">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-474">Keywords</span></span>

<span data-ttu-id="9b0d2-475">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-475">| |</span></span>
|<span data-ttu-id="9b0d2-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-477">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-477">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-478">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-478">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-479">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-479">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-480">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-480">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-481">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-481">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-482">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-483">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-484">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-485">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-486">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-486">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-487">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-487">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-488">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="9b0d2-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="9b0d2-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-491">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-491">Format</span></span>

<span data-ttu-id="9b0d2-492">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-493">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-493">Pattern</span></span>

 <span data-ttu-id="9b0d2-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-495">Checksum</span></span>

<span data-ttu-id="9b0d2-496">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-497">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-497">Definition</span></span>

<span data-ttu-id="9b0d2-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-499">正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-500">From `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-501">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-501">Keywords</span></span>

<span data-ttu-id="9b0d2-502">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-502">| |</span></span>
|<span data-ttu-id="9b0d2-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-504">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-504">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-505">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-505">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-506">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-506">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-507">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-507">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-508">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-508">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-509">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-510">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-511">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-512">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-513">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-513">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-514">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-514">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-515">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-516">vエア uotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="9b0d2-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="9b0d2-517">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="9b0d2-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-518">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-518">Format</span></span>

<span data-ttu-id="9b0d2-519">スペースと区切り文字を含まない6桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-520">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-520">Pattern</span></span>

 <span data-ttu-id="9b0d2-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-522">Checksum</span></span>

<span data-ttu-id="9b0d2-523">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-524">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-524">Definition</span></span>

<span data-ttu-id="9b0d2-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-526">正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-527">From `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-528">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-528">Keywords</span></span>

<span data-ttu-id="9b0d2-529">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-529">| |</span></span>
|<span data-ttu-id="9b0d2-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-531">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-531">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-532">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-532">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-533">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-533">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-534">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-534">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-535">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-535">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-536">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-537">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-538">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-539">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-540">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-540">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-541">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-541">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-542">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-543">fahて fabnis</span><span class="sxs-lookup"><span data-stu-id="9b0d2-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="9b0d2-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-545">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-545">Format</span></span>

<span data-ttu-id="9b0d2-546">指定したパターンの2つの文字と6桁の数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-547">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-547">Pattern</span></span>

<span data-ttu-id="9b0d2-548">2つの文字と6桁の数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="9b0d2-549">2つの文字 (大文字小文字を区別しない数字または文字)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="9b0d2-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="9b0d2-550">A space (optional)</span></span>
    
- <span data-ttu-id="9b0d2-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-551">Three digits</span></span>
    
- <span data-ttu-id="9b0d2-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="9b0d2-552">A space (optional)</span></span>
    
- <span data-ttu-id="9b0d2-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-554">Checksum</span></span>

<span data-ttu-id="9b0d2-555">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-556">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-556">Definition</span></span>

<span data-ttu-id="9b0d2-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-558">正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-559">From `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-560">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-560">Keywords</span></span>

<span data-ttu-id="9b0d2-561">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-561">| |</span></span>
|<span data-ttu-id="9b0d2-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-563">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-563">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-564">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-564">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-565">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-565">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-566">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-566">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-567">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-567">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-568">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-569">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-570">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-571">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-572">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-572">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-573">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-573">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-574">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="9b0d2-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="9b0d2-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-577">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-577">Format</span></span>

<span data-ttu-id="9b0d2-578">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-579">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-579">Pattern</span></span>

<span data-ttu-id="9b0d2-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-581">Checksum</span></span>

<span data-ttu-id="9b0d2-582">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-583">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-583">Definition</span></span>

<span data-ttu-id="9b0d2-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-585">正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-586">From `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-587">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-587">Keywords</span></span>

<span data-ttu-id="9b0d2-588">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-588">| |</span></span>
|<span data-ttu-id="9b0d2-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-590">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-590">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-591">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-591">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-592">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-592">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-593">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-593">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-594">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-594">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-595">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-596">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-597">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-598">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-599">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-599">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-600">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-600">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-601">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="9b0d2-602">permis de conduire</span></span>  <br/> <span data-ttu-id="9b0d2-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="9b0d2-603">rijbewijs</span></span>  <br/> <span data-ttu-id="9b0d2-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="9b0d2-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="9b0d2-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="9b0d2-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-606">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-606">Format</span></span>

<span data-ttu-id="9b0d2-607">2つのスラッシュを含む14桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-608">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-608">Pattern</span></span>

<span data-ttu-id="9b0d2-609">14桁の数字と2つのスラッシュ:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="9b0d2-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-610">Five digits</span></span> 
    
- <span data-ttu-id="9b0d2-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="9b0d2-611">A forward slash</span></span>
    
- <span data-ttu-id="9b0d2-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-612">Two digits</span></span>
    
- <span data-ttu-id="9b0d2-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="9b0d2-613">A forward slash</span></span>
    
- <span data-ttu-id="9b0d2-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-615">Checksum</span></span>

<span data-ttu-id="9b0d2-616">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-617">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-617">Definition</span></span>

<span data-ttu-id="9b0d2-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-619">正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-620">From `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-621">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-621">Keywords</span></span>

<span data-ttu-id="9b0d2-622">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-622">| |</span></span>
|<span data-ttu-id="9b0d2-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-624">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-624">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-625">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-625">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-626">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-626">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-627">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-627">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-628">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-628">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-629">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-630">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-631">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-632">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-633">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-633">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-634">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-634">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-635">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="9b0d2-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="9b0d2-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="9b0d2-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-638">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-638">Format</span></span>

<span data-ttu-id="9b0d2-639">指定したパターンの2文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-640">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-640">Pattern</span></span>

<span data-ttu-id="9b0d2-641">2つの文字の後に特殊文字を含む7個の数字。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="9b0d2-642">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="9b0d2-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="9b0d2-643">A hyphen</span></span>
    
- <span data-ttu-id="9b0d2-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-644">Six digits</span></span>
    
- <span data-ttu-id="9b0d2-645">スペース</span><span class="sxs-lookup"><span data-stu-id="9b0d2-645">A space</span></span>
    
- <span data-ttu-id="9b0d2-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-647">Checksum</span></span>

<span data-ttu-id="9b0d2-648">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-649">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-649">Definition</span></span>

<span data-ttu-id="9b0d2-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-651">正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-652">From `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-653">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-653">Keywords</span></span>

<span data-ttu-id="9b0d2-654">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-654">| |</span></span>
|<span data-ttu-id="9b0d2-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-656">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-656">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-657">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-657">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-658">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-658">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-659">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-659">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-660">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-660">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-661">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-662">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-663">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-664">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-665">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-665">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-666">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-666">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-667">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="9b0d2-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="9b0d2-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-670">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-670">Format</span></span>

<span data-ttu-id="9b0d2-671">1文字の後に8桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-672">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-672">Pattern</span></span>

<span data-ttu-id="9b0d2-673">1文字の後に8桁の数字。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="9b0d2-674">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="9b0d2-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-676">Checksum</span></span>

<span data-ttu-id="9b0d2-677">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-678">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-678">Definition</span></span>

<span data-ttu-id="9b0d2-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-680">正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-681">From `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-682">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-682">Keywords</span></span>

<span data-ttu-id="9b0d2-683">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-683">| |</span></span>
|<span data-ttu-id="9b0d2-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-685">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-685">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-686">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-686">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-687">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-687">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-688">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-688">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-689">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-689">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-690">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-691">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-692">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-693">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-694">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-694">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-695">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-695">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-696">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="9b0d2-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="9b0d2-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-699">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-699">Format</span></span>

<span data-ttu-id="9b0d2-700">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-701">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-701">Pattern</span></span>

<span data-ttu-id="9b0d2-702">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="9b0d2-703">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="9b0d2-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-705">Checksum</span></span>

<span data-ttu-id="9b0d2-706">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-707">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-707">Definition</span></span>

<span data-ttu-id="9b0d2-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-709">正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-710">From `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-711">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-711">Keywords</span></span>

<span data-ttu-id="9b0d2-712">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-712">| |</span></span>
|<span data-ttu-id="9b0d2-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-714">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-714">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-715">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-715">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-716">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-716">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-717">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-717">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-718">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-718">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-719">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-720">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-721">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-722">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-723">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-723">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-724">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-724">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-725">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="9b0d2-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="9b0d2-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="9b0d2-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-728">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-728">Format</span></span>

<span data-ttu-id="9b0d2-729">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-730">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-730">Pattern</span></span>

<span data-ttu-id="9b0d2-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9b0d2-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-732">Checksum</span></span>

<span data-ttu-id="9b0d2-733">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-734">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-734">Definition</span></span>

<span data-ttu-id="9b0d2-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-736">正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-737">From `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-738">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-738">Keywords</span></span>

<span data-ttu-id="9b0d2-739">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-739">| |</span></span>
|<span data-ttu-id="9b0d2-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-741">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-741">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-742">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-742">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-743">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-743">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-744">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-744">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-745">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-745">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-746">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-747">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-748">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-749">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-750">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-750">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-751">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-751">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-752">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="9b0d2-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="9b0d2-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-755">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-755">Format</span></span>

<span data-ttu-id="9b0d2-756">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-757">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-757">Pattern</span></span>

<span data-ttu-id="9b0d2-758">8桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="9b0d2-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-759">Eight digits</span></span> 
    
- <span data-ttu-id="9b0d2-760">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-761">Checksum</span></span>

<span data-ttu-id="9b0d2-762">はい</span><span class="sxs-lookup"><span data-stu-id="9b0d2-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-763">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-763">Definition</span></span>

<span data-ttu-id="9b0d2-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-765">関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-766">From `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-767">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-767">Keywords</span></span>

<span data-ttu-id="9b0d2-768">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-768">| |</span></span>
|<span data-ttu-id="9b0d2-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-770">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-771">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-771">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-772">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-772">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-773">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-773">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-774">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-774">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-775">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-776">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-777">driver's licence</span></span>  <br/> <span data-ttu-id="9b0d2-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-778">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-779">driving licence</span></span>  <br/> <span data-ttu-id="9b0d2-780">driving license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-780">driving license</span></span>  <br/> <span data-ttu-id="9b0d2-781">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-781">driver licence number</span></span>  <br/> <span data-ttu-id="9b0d2-782">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-782">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-783">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-783">drivers licence number</span></span>  <br/> <span data-ttu-id="9b0d2-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-784">drivers license number</span></span>  <br/> <span data-ttu-id="9b0d2-785">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-785">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-786">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-787">ライセンス番号の運転</span><span class="sxs-lookup"><span data-stu-id="9b0d2-787">driving licence number</span></span>  <br/> <span data-ttu-id="9b0d2-788">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-788">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-789">許可の推進</span><span class="sxs-lookup"><span data-stu-id="9b0d2-789">driving permit</span></span>  <br/> <span data-ttu-id="9b0d2-790">許可番号の運転</span><span class="sxs-lookup"><span data-stu-id="9b0d2-790">driving permit number</span></span>  <br/> <span data-ttu-id="9b0d2-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="9b0d2-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="9b0d2-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="9b0d2-792">permiso conducción</span></span>  <br/> <span data-ttu-id="9b0d2-793">número/encia conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="9b0d2-794">número デカーネット de conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="9b0d2-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="9b0d2-796">/暗号化 ia conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-796">licencia conducir</span></span>  <br/> <span data-ttu-id="9b0d2-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="9b0d2-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="9b0d2-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="9b0d2-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-800">permiso conducir</span></span>  <br/> <span data-ttu-id="9b0d2-801">-encia de manejo</span><span class="sxs-lookup"><span data-stu-id="9b0d2-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="9b0d2-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="9b0d2-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="9b0d2-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="9b0d2-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="9b0d2-805">Format</span><span class="sxs-lookup"><span data-stu-id="9b0d2-805">Format</span></span>

<span data-ttu-id="9b0d2-806">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="9b0d2-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9b0d2-807">パターン</span><span class="sxs-lookup"><span data-stu-id="9b0d2-807">Pattern</span></span>

<span data-ttu-id="9b0d2-808">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9b0d2-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="9b0d2-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-809">Six digits</span></span> 
    
- <span data-ttu-id="9b0d2-810">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-810">A hyphen</span></span>
    
- <span data-ttu-id="9b0d2-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9b0d2-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9b0d2-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="9b0d2-812">Checksum</span></span>

<span data-ttu-id="9b0d2-813">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b0d2-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="9b0d2-814">定義</span><span class="sxs-lookup"><span data-stu-id="9b0d2-814">Definition</span></span>

<span data-ttu-id="9b0d2-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9b0d2-816">正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9b0d2-817">From `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="9b0d2-818">キーワード</span><span class="sxs-lookup"><span data-stu-id="9b0d2-818">Keywords</span></span>

<span data-ttu-id="9b0d2-819">| |</span><span class="sxs-lookup"><span data-stu-id="9b0d2-819">| |</span></span>
|<span data-ttu-id="9b0d2-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="9b0d2-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="9b0d2-821">dl#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-821">dl#</span></span>  <br/> <span data-ttu-id="9b0d2-822">driver license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-822">driver license</span></span>  <br/> <span data-ttu-id="9b0d2-823">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-823">driver license number</span></span>  <br/> <span data-ttu-id="9b0d2-824">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="9b0d2-824">driver licence</span></span>  <br/> <span data-ttu-id="9b0d2-825">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="9b0d2-825">drivers lic.</span></span>  <br/> <span data-ttu-id="9b0d2-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-826">drivers license</span></span>  <br/> <span data-ttu-id="9b0d2-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9b0d2-827">drivers licence</span></span>  <br/> <span data-ttu-id="9b0d2-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="9b0d2-828">driver's license</span></span>  <br/> <span data-ttu-id="9b0d2-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-829">driver's license number</span></span>  <br/> <span data-ttu-id="9b0d2-830">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-830">driver's licence number</span></span>  <br/> <span data-ttu-id="9b0d2-831">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="9b0d2-831">driving license number</span></span>  <br/> <span data-ttu-id="9b0d2-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="9b0d2-832">dlno#</span></span>  <br/> <span data-ttu-id="9b0d2-833">körkort</span><span class="sxs-lookup"><span data-stu-id="9b0d2-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="9b0d2-834">佐賀</span><span class="sxs-lookup"><span data-stu-id="9b0d2-834">UK</span></span>

<span data-ttu-id="9b0d2-835">詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="9b0d2-835">For details, see the section "U.K.</span></span> <span data-ttu-id="9b0d2-836">[[機密情報の種類](what-the-sensitive-information-types-look-for.md)] に表示される運転免許証番号。</span><span class="sxs-lookup"><span data-stu-id="9b0d2-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b0d2-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b0d2-837">See also</span></span>

[<span data-ttu-id="9b0d2-838">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="9b0d2-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

