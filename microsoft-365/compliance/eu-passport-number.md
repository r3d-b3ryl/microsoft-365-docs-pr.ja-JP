---
title: EU パスポート番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085872"
---
# <a name="eu-passport-number"></a><span data-ttu-id="991b5-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-104">EU Passport Number</span></span>

<span data-ttu-id="991b5-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="991b5-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="991b5-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="991b5-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="991b5-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="991b5-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="991b5-108">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-108">Format</span></span>

<span data-ttu-id="991b5-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-110">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-110">Pattern</span></span>

<span data-ttu-id="991b5-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="991b5-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="991b5-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="991b5-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="991b5-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="991b5-113">One space (optional)</span></span>
    
- <span data-ttu-id="991b5-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="991b5-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-115">Checksum</span></span>

<span data-ttu-id="991b5-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="991b5-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-117">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-117">Definition</span></span>

<span data-ttu-id="991b5-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-120">From `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-121">Keywords</span></span>

<span data-ttu-id="991b5-122">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-122"></span></span>
|<span data-ttu-id="991b5-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-124">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-124">passport number</span></span>  <br/> <span data-ttu-id="991b5-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-125">austrian passport number</span></span>  <br/> <span data-ttu-id="991b5-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-126">passport no</span></span>  <br/> <span data-ttu-id="991b5-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="991b5-127">reisepass</span></span>  <br/> <span data-ttu-id="991b5-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="991b5-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="991b5-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="991b5-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="991b5-130">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-130">Format</span></span>

<span data-ttu-id="991b5-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="991b5-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-132">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-132">Pattern</span></span>

<span data-ttu-id="991b5-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-134">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-134">Checksum</span></span>

<span data-ttu-id="991b5-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="991b5-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-136">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-136">Definition</span></span>

<span data-ttu-id="991b5-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-139">From `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-140">Keywords</span></span>

<span data-ttu-id="991b5-141">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-141"></span></span>
|<span data-ttu-id="991b5-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-143">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-143">passport number</span></span>  <br/> <span data-ttu-id="991b5-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-144">belgian passport number</span></span>  <br/> <span data-ttu-id="991b5-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-145">passport no</span></span>  <br/> <span data-ttu-id="991b5-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="991b5-146">paspoort</span></span>  <br/> <span data-ttu-id="991b5-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="991b5-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="991b5-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="991b5-148">reisepass kein</span></span>  <br/> <span data-ttu-id="991b5-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="991b5-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="991b5-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="991b5-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="991b5-151">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-151">Format</span></span>

<span data-ttu-id="991b5-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-153">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-153">Pattern</span></span>

 <span data-ttu-id="991b5-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="991b5-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-155">Checksum</span></span>

<span data-ttu-id="991b5-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-157">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-157">Definition</span></span>

<span data-ttu-id="991b5-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-160">From `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-161">Keywords</span></span>

<span data-ttu-id="991b5-162">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-162"></span></span>
|<span data-ttu-id="991b5-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-164">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-164">passport number</span></span>  <br/> <span data-ttu-id="991b5-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="991b5-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-166">passport no</span></span>  <br/> <span data-ttu-id="991b5-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="991b5-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="991b5-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="991b5-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="991b5-169">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-169">Format</span></span>

<span data-ttu-id="991b5-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-171">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-171">Pattern</span></span>

 <span data-ttu-id="991b5-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="991b5-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-173">Checksum</span></span>

<span data-ttu-id="991b5-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-175">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-175">Definition</span></span>

<span data-ttu-id="991b5-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-178">From `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-179">Keywords</span></span>

<span data-ttu-id="991b5-180">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-180"></span></span>
|<span data-ttu-id="991b5-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-182">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-182">passport number</span></span>  <br/> <span data-ttu-id="991b5-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-183">croatian passport number</span></span>  <br/> <span data-ttu-id="991b5-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-184">passport no</span></span>  <br/> <span data-ttu-id="991b5-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="991b5-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="991b5-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="991b5-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="991b5-187">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-187">Format</span></span>

<span data-ttu-id="991b5-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-189">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-189">Pattern</span></span>

<span data-ttu-id="991b5-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-191">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-191">Checksum</span></span>

<span data-ttu-id="991b5-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-193">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-193">Definition</span></span>

<span data-ttu-id="991b5-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-196">From `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-197">Keywords</span></span>

<span data-ttu-id="991b5-198">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-198"></span></span>
|<span data-ttu-id="991b5-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-200">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-200">passport number</span></span>  <br/> <span data-ttu-id="991b5-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="991b5-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-202">passport no</span></span>  <br/> <span data-ttu-id="991b5-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="991b5-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="991b5-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="991b5-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="991b5-205">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-205">Format</span></span>

<span data-ttu-id="991b5-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-207">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-207">Pattern</span></span>

<span data-ttu-id="991b5-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-209">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-209">Checksum</span></span>

<span data-ttu-id="991b5-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-211">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-211">Definition</span></span>

<span data-ttu-id="991b5-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-214">From `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-215">Keywords</span></span>

<span data-ttu-id="991b5-216">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-216"></span></span>
|<span data-ttu-id="991b5-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-218">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-218">passport number</span></span>  <br/> <span data-ttu-id="991b5-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-219">czech passport number</span></span>  <br/> <span data-ttu-id="991b5-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-220">passport no</span></span>  <br/> <span data-ttu-id="991b5-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="991b5-221">cestovní pas</span></span>  <br/> <span data-ttu-id="991b5-222">pas</span><span class="sxs-lookup"><span data-stu-id="991b5-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="991b5-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="991b5-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="991b5-224">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-224">Format</span></span>

<span data-ttu-id="991b5-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-226">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-226">Pattern</span></span>

 <span data-ttu-id="991b5-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="991b5-228">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-228">Checksum</span></span>

<span data-ttu-id="991b5-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-230">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-230">Definition</span></span>

<span data-ttu-id="991b5-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-233">From `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-234">Keywords</span></span>

<span data-ttu-id="991b5-235">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-235"></span></span>
|<span data-ttu-id="991b5-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-237">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-237">passport number</span></span>  <br/> <span data-ttu-id="991b5-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-238">danish passport number</span></span>  <br/> <span data-ttu-id="991b5-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-239">passport no</span></span>  <br/> <span data-ttu-id="991b5-240">pas</span><span class="sxs-lookup"><span data-stu-id="991b5-240">pas</span></span>  <br/> <span data-ttu-id="991b5-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="991b5-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="991b5-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="991b5-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="991b5-243">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-243">Format</span></span>

<span data-ttu-id="991b5-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="991b5-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-245">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-245">Pattern</span></span>

<span data-ttu-id="991b5-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-247">Checksum</span></span>

<span data-ttu-id="991b5-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-249">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-249">Definition</span></span>

<span data-ttu-id="991b5-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-252">From `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-253">Keywords</span></span>

<span data-ttu-id="991b5-254">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-254"></span></span>
|<span data-ttu-id="991b5-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-256">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-256">passport number</span></span>  <br/> <span data-ttu-id="991b5-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-257">estonian passport number</span></span>  <br/> <span data-ttu-id="991b5-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-258">passport no</span></span>  <br/> <span data-ttu-id="991b5-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="991b5-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="991b5-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="991b5-260">Finland</span></span>

<span data-ttu-id="991b5-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991b5-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="991b5-262">フランス</span><span class="sxs-lookup"><span data-stu-id="991b5-262">France</span></span>

<span data-ttu-id="991b5-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991b5-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="991b5-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="991b5-264">Germany</span></span>

<span data-ttu-id="991b5-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991b5-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="991b5-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="991b5-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="991b5-267">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-267">Format</span></span>

<span data-ttu-id="991b5-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-269">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-269">Pattern</span></span>

<span data-ttu-id="991b5-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-271">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-271">Checksum</span></span>

<span data-ttu-id="991b5-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-273">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-273">Definition</span></span>

<span data-ttu-id="991b5-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-276">From `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-277">Keywords</span></span>

<span data-ttu-id="991b5-278">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-278"></span></span>
|<span data-ttu-id="991b5-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-280">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-280">passport number</span></span>  <br/> <span data-ttu-id="991b5-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-281">greek passport number</span></span>  <br/> <span data-ttu-id="991b5-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-282">passport no</span></span>  <br/> <span data-ttu-id="991b5-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="991b5-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="991b5-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="991b5-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="991b5-285">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-285">Format</span></span>

<span data-ttu-id="991b5-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-287">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-287">Pattern</span></span>

<span data-ttu-id="991b5-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-289">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-289">Checksum</span></span>

<span data-ttu-id="991b5-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-291">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-291">Definition</span></span>

<span data-ttu-id="991b5-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-294">From `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-295">Keywords</span></span>

<span data-ttu-id="991b5-296">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-296"></span></span>
|<span data-ttu-id="991b5-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-298">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-298">passport number</span></span>  <br/> <span data-ttu-id="991b5-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="991b5-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-300">passport no</span></span>  <br/> <span data-ttu-id="991b5-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="991b5-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="991b5-302">アイルランド</span><span class="sxs-lookup"><span data-stu-id="991b5-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="991b5-303">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-303">Format</span></span>

<span data-ttu-id="991b5-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-305">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-305">Pattern</span></span>

<span data-ttu-id="991b5-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="991b5-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="991b5-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="991b5-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="991b5-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="991b5-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-309">Checksum</span></span>

<span data-ttu-id="991b5-310">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-311">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-311">Definition</span></span>

<span data-ttu-id="991b5-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-314">From `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-315">Keywords</span></span>

<span data-ttu-id="991b5-316">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-316"></span></span>
|<span data-ttu-id="991b5-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-318">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-318">passport number</span></span>  <br/> <span data-ttu-id="991b5-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-319">irish passport number</span></span>  <br/> <span data-ttu-id="991b5-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-320">passport no</span></span>  <br/> <span data-ttu-id="991b5-321">pas</span><span class="sxs-lookup"><span data-stu-id="991b5-321">pas</span></span>  <br/> <span data-ttu-id="991b5-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="991b5-322">passport</span></span>  <br/> <span data-ttu-id="991b5-323">passeport</span><span class="sxs-lookup"><span data-stu-id="991b5-323">passeport</span></span>  <br/> <span data-ttu-id="991b5-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="991b5-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="991b5-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="991b5-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="991b5-326">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-326">Format</span></span>

<span data-ttu-id="991b5-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-328">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-328">Pattern</span></span>

<span data-ttu-id="991b5-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="991b5-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="991b5-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="991b5-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="991b5-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="991b5-332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-332">Checksum</span></span>

<span data-ttu-id="991b5-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="991b5-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-334">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-334">Definition</span></span>

<span data-ttu-id="991b5-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-337">From `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-338">Keywords</span></span>

<span data-ttu-id="991b5-339">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-339"></span></span>
|<span data-ttu-id="991b5-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-341">italian passport number</span></span>  <br/> <span data-ttu-id="991b5-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="991b5-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="991b5-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="991b5-343">passaporto</span></span>  <br/> <span data-ttu-id="991b5-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="991b5-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="991b5-345">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-345">passport number</span></span>  <br/> <span data-ttu-id="991b5-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="991b5-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="991b5-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="991b5-347">passaporto numero</span></span>  <br/> <span data-ttu-id="991b5-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="991b5-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="991b5-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="991b5-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="991b5-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="991b5-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="991b5-351">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-351">Format</span></span>

<span data-ttu-id="991b5-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-353">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-353">Pattern</span></span>

<span data-ttu-id="991b5-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="991b5-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="991b5-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="991b5-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="991b5-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="991b5-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-357">Checksum</span></span>

<span data-ttu-id="991b5-358">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-359">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-359">Definition</span></span>

<span data-ttu-id="991b5-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-362">From `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-363">Keywords</span></span>

<span data-ttu-id="991b5-364">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-364"></span></span>
|<span data-ttu-id="991b5-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-366">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-366">passport number</span></span>  <br/> <span data-ttu-id="991b5-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-367">latvian passport number</span></span>  <br/> <span data-ttu-id="991b5-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-368">passport no</span></span>  <br/> <span data-ttu-id="991b5-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="991b5-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="991b5-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="991b5-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="991b5-371">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-371">Format</span></span>

<span data-ttu-id="991b5-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="991b5-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-373">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-373">Pattern</span></span>

<span data-ttu-id="991b5-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="991b5-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-375">Checksum</span></span>

<span data-ttu-id="991b5-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="991b5-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-377">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-377">Definition</span></span>

<span data-ttu-id="991b5-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-380">From `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-381">Keywords</span></span>

<span data-ttu-id="991b5-382">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-382"></span></span>
|<span data-ttu-id="991b5-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-384">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-384">passport number</span></span>  <br/> <span data-ttu-id="991b5-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="991b5-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-386">passport no</span></span>  <br/> <span data-ttu-id="991b5-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="991b5-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="991b5-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="991b5-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="991b5-389">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-389">Format</span></span>

<span data-ttu-id="991b5-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="991b5-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-391">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-391">Pattern</span></span>

<span data-ttu-id="991b5-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="991b5-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-393">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-393">Checksum</span></span>

<span data-ttu-id="991b5-394">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-395">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-395">Definition</span></span>

<span data-ttu-id="991b5-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-398">From `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-399">Keywords</span></span>

<span data-ttu-id="991b5-400">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-400"></span></span>
|<span data-ttu-id="991b5-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-402">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-402">passport number</span></span>  <br/> <span data-ttu-id="991b5-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-403">latvian passport number</span></span>  <br/> <span data-ttu-id="991b5-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-404">passport no</span></span>  <br/> <span data-ttu-id="991b5-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="991b5-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="991b5-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="991b5-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="991b5-407">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-407">Format</span></span>

<span data-ttu-id="991b5-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-409">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-409">Pattern</span></span>

 <span data-ttu-id="991b5-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="991b5-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-411">Checksum</span></span>

<span data-ttu-id="991b5-412">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-413">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-413">Definition</span></span>

<span data-ttu-id="991b5-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-416">From `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-417">Keywords</span></span>

<span data-ttu-id="991b5-418">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-418"></span></span>
|<span data-ttu-id="991b5-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-420">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-420">passport number</span></span>  <br/> <span data-ttu-id="991b5-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-421">maltese passport number</span></span>  <br/> <span data-ttu-id="991b5-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-422">passport no</span></span>  <br/> <span data-ttu-id="991b5-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="991b5-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="991b5-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="991b5-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="991b5-425">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-425">Format</span></span>

<span data-ttu-id="991b5-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="991b5-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-427">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-427">Pattern</span></span>

<span data-ttu-id="991b5-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="991b5-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-429">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-429">Checksum</span></span>

<span data-ttu-id="991b5-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="991b5-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-431">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-431">Definition</span></span>

<span data-ttu-id="991b5-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-434">From `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-435">Keywords</span></span>

<span data-ttu-id="991b5-436">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-436"></span></span>
|<span data-ttu-id="991b5-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-438">dutch passport number</span></span>  <br/> <span data-ttu-id="991b5-439">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-439">passport number</span></span>  <br/> <span data-ttu-id="991b5-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="991b5-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="991b5-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="991b5-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="991b5-442">paspoort</span></span>  <br/> <span data-ttu-id="991b5-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="991b5-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="991b5-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="991b5-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="991b5-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="991b5-445">Poland</span></span>

<span data-ttu-id="991b5-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991b5-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="991b5-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="991b5-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="991b5-448">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-448">Format</span></span>

<span data-ttu-id="991b5-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="991b5-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-450">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-450">Pattern</span></span>

<span data-ttu-id="991b5-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="991b5-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="991b5-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="991b5-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="991b5-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="991b5-454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-454">Checksum</span></span>

<span data-ttu-id="991b5-455">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-456">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-456">Definition</span></span>

<span data-ttu-id="991b5-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-459">From `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-460">Keywords</span></span>

<span data-ttu-id="991b5-461">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-461"></span></span>
|<span data-ttu-id="991b5-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-463">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-463">passport number</span></span>  <br/> <span data-ttu-id="991b5-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="991b5-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-465">passport no</span></span>  <br/> <span data-ttu-id="991b5-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="991b5-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="991b5-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="991b5-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="991b5-468">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-468">Format</span></span>

<span data-ttu-id="991b5-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-470">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-470">Pattern</span></span>

<span data-ttu-id="991b5-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-472">Checksum</span></span>

<span data-ttu-id="991b5-473">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-474">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-474">Definition</span></span>

<span data-ttu-id="991b5-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-477">From `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-478">Keywords</span></span>

<span data-ttu-id="991b5-479">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-479"></span></span>
|<span data-ttu-id="991b5-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-481">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-481">passport number</span></span>  <br/> <span data-ttu-id="991b5-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-482">romanian passport number</span></span>  <br/> <span data-ttu-id="991b5-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-483">passport no</span></span>  <br/> <span data-ttu-id="991b5-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="991b5-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="991b5-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="991b5-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="991b5-486">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-486">Format</span></span>

<span data-ttu-id="991b5-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="991b5-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-488">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-488">Pattern</span></span>

<span data-ttu-id="991b5-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="991b5-490">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-490">Checksum</span></span>

<span data-ttu-id="991b5-491">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-492">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-492">Definition</span></span>

<span data-ttu-id="991b5-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-495">From `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-496">Keywords</span></span>

<span data-ttu-id="991b5-497">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-497"></span></span>
|<span data-ttu-id="991b5-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-499">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-499">passport number</span></span>  <br/> <span data-ttu-id="991b5-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="991b5-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-501">passport no</span></span>  <br/> <span data-ttu-id="991b5-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="991b5-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="991b5-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="991b5-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="991b5-504">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-504">Format</span></span>

<span data-ttu-id="991b5-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-506">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-506">Pattern</span></span>

<span data-ttu-id="991b5-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="991b5-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="991b5-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="991b5-508">The letter "P"</span></span>
    
- <span data-ttu-id="991b5-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="991b5-509">One uppercase letter</span></span>
    
- <span data-ttu-id="991b5-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="991b5-511">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-511">Checksum</span></span>

<span data-ttu-id="991b5-512">いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-513">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-513">Definition</span></span>

<span data-ttu-id="991b5-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-516">From `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-517">Keywords</span></span>

<span data-ttu-id="991b5-518">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-518"></span></span>
|<span data-ttu-id="991b5-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-520">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-520">passport number</span></span>  <br/> <span data-ttu-id="991b5-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="991b5-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-522">passport no</span></span>  <br/> <span data-ttu-id="991b5-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="991b5-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="991b5-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="991b5-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="991b5-525">Format</span><span class="sxs-lookup"><span data-stu-id="991b5-525">Format</span></span>

<span data-ttu-id="991b5-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="991b5-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="991b5-527">パターン</span><span class="sxs-lookup"><span data-stu-id="991b5-527">Pattern</span></span>

<span data-ttu-id="991b5-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="991b5-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="991b5-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="991b5-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="991b5-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="991b5-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="991b5-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="991b5-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="991b5-532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="991b5-532">Checksum</span></span>

<span data-ttu-id="991b5-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="991b5-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="991b5-534">定義</span><span class="sxs-lookup"><span data-stu-id="991b5-534">Definition</span></span>

<span data-ttu-id="991b5-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="991b5-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="991b5-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="991b5-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="991b5-537">From `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="991b5-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="991b5-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="991b5-538">Keywords</span></span>

<span data-ttu-id="991b5-539">| |</span><span class="sxs-lookup"><span data-stu-id="991b5-539"></span></span>
|<span data-ttu-id="991b5-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="991b5-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="991b5-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="991b5-541">passport</span></span>  <br/> <span data-ttu-id="991b5-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="991b5-542">spain passport</span></span>  <br/> <span data-ttu-id="991b5-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="991b5-543">passport book</span></span>  <br/> <span data-ttu-id="991b5-544">passport number</span><span class="sxs-lookup"><span data-stu-id="991b5-544">passport number</span></span>  <br/> <span data-ttu-id="991b5-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="991b5-545">passport no</span></span>  <br/> <span data-ttu-id="991b5-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="991b5-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="991b5-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="991b5-547">número pasaporte</span></span>  <br/> <span data-ttu-id="991b5-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="991b5-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="991b5-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="991b5-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="991b5-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="991b5-550">Sweden</span></span>

<span data-ttu-id="991b5-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991b5-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="991b5-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="991b5-552">UK</span></span>

<span data-ttu-id="991b5-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991b5-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="991b5-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="991b5-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="991b5-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="991b5-555">See also</span></span>

[<span data-ttu-id="991b5-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="991b5-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

