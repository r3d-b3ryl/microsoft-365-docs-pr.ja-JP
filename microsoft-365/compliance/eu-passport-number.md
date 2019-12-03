---
title: EU パスポート番号
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662802"
---
# <a name="eu-passport-number"></a><span data-ttu-id="911fe-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-104">EU Passport Number</span></span>

<span data-ttu-id="911fe-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="911fe-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="911fe-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="911fe-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="911fe-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="911fe-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="911fe-108">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-108">Format</span></span>

<span data-ttu-id="911fe-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-110">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-110">Pattern</span></span>

<span data-ttu-id="911fe-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="911fe-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="911fe-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="911fe-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="911fe-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="911fe-113">One space (optional)</span></span>
    
- <span data-ttu-id="911fe-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="911fe-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-115">Checksum</span></span>

<span data-ttu-id="911fe-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="911fe-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-117">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-117">Definition</span></span>

<span data-ttu-id="911fe-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-120">From `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-121">Keywords</span></span>

<span data-ttu-id="911fe-122">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-122"></span></span>
|<span data-ttu-id="911fe-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-124">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-124">passport number</span></span>  <br/> <span data-ttu-id="911fe-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-125">austrian passport number</span></span>  <br/> <span data-ttu-id="911fe-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-126">passport no</span></span>  <br/> <span data-ttu-id="911fe-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="911fe-127">reisepass</span></span>  <br/> <span data-ttu-id="911fe-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="911fe-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="911fe-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="911fe-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="911fe-130">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-130">Format</span></span>

<span data-ttu-id="911fe-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="911fe-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-132">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-132">Pattern</span></span>

<span data-ttu-id="911fe-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-134">Checksum</span></span>

<span data-ttu-id="911fe-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="911fe-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-136">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-136">Definition</span></span>

<span data-ttu-id="911fe-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-139">From `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-140">Keywords</span></span>

<span data-ttu-id="911fe-141">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-141"></span></span>
|<span data-ttu-id="911fe-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-143">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-143">passport number</span></span>  <br/> <span data-ttu-id="911fe-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-144">belgian passport number</span></span>  <br/> <span data-ttu-id="911fe-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-145">passport no</span></span>  <br/> <span data-ttu-id="911fe-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="911fe-146">paspoort</span></span>  <br/> <span data-ttu-id="911fe-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="911fe-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="911fe-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="911fe-148">reisepass kein</span></span>  <br/> <span data-ttu-id="911fe-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="911fe-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="911fe-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="911fe-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="911fe-151">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-151">Format</span></span>

<span data-ttu-id="911fe-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-153">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-153">Pattern</span></span>

 <span data-ttu-id="911fe-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="911fe-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-155">Checksum</span></span>

<span data-ttu-id="911fe-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-157">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-157">Definition</span></span>

<span data-ttu-id="911fe-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-160">From `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-161">Keywords</span></span>

<span data-ttu-id="911fe-162">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-162"></span></span>
|<span data-ttu-id="911fe-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-164">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-164">passport number</span></span>  <br/> <span data-ttu-id="911fe-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="911fe-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-166">passport no</span></span>  <br/> <span data-ttu-id="911fe-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="911fe-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="911fe-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="911fe-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="911fe-169">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-169">Format</span></span>

<span data-ttu-id="911fe-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-171">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-171">Pattern</span></span>

 <span data-ttu-id="911fe-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="911fe-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-173">Checksum</span></span>

<span data-ttu-id="911fe-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-175">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-175">Definition</span></span>

<span data-ttu-id="911fe-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-178">From `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-179">Keywords</span></span>

<span data-ttu-id="911fe-180">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-180"></span></span>
|<span data-ttu-id="911fe-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-182">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-182">passport number</span></span>  <br/> <span data-ttu-id="911fe-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-183">croatian passport number</span></span>  <br/> <span data-ttu-id="911fe-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-184">passport no</span></span>  <br/> <span data-ttu-id="911fe-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="911fe-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="911fe-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="911fe-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="911fe-187">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-187">Format</span></span>

<span data-ttu-id="911fe-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-189">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-189">Pattern</span></span>

<span data-ttu-id="911fe-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-191">Checksum</span></span>

<span data-ttu-id="911fe-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-193">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-193">Definition</span></span>

<span data-ttu-id="911fe-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-196">From `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-197">Keywords</span></span>

<span data-ttu-id="911fe-198">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-198"></span></span>
|<span data-ttu-id="911fe-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-200">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-200">passport number</span></span>  <br/> <span data-ttu-id="911fe-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="911fe-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-202">passport no</span></span>  <br/> <span data-ttu-id="911fe-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="911fe-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="911fe-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="911fe-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="911fe-205">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-205">Format</span></span>

<span data-ttu-id="911fe-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-207">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-207">Pattern</span></span>

<span data-ttu-id="911fe-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-209">Checksum</span></span>

<span data-ttu-id="911fe-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-211">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-211">Definition</span></span>

<span data-ttu-id="911fe-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-214">From `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-215">Keywords</span></span>

<span data-ttu-id="911fe-216">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-216"></span></span>
|<span data-ttu-id="911fe-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-218">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-218">passport number</span></span>  <br/> <span data-ttu-id="911fe-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-219">czech passport number</span></span>  <br/> <span data-ttu-id="911fe-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-220">passport no</span></span>  <br/> <span data-ttu-id="911fe-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="911fe-221">cestovní pas</span></span>  <br/> <span data-ttu-id="911fe-222">pas</span><span class="sxs-lookup"><span data-stu-id="911fe-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="911fe-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="911fe-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="911fe-224">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-224">Format</span></span>

<span data-ttu-id="911fe-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-226">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-226">Pattern</span></span>

 <span data-ttu-id="911fe-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="911fe-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-228">Checksum</span></span>

<span data-ttu-id="911fe-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-230">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-230">Definition</span></span>

<span data-ttu-id="911fe-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-233">From `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-234">Keywords</span></span>

<span data-ttu-id="911fe-235">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-235"></span></span>
|<span data-ttu-id="911fe-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-237">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-237">passport number</span></span>  <br/> <span data-ttu-id="911fe-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-238">danish passport number</span></span>  <br/> <span data-ttu-id="911fe-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-239">passport no</span></span>  <br/> <span data-ttu-id="911fe-240">pas</span><span class="sxs-lookup"><span data-stu-id="911fe-240">pas</span></span>  <br/> <span data-ttu-id="911fe-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="911fe-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="911fe-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="911fe-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="911fe-243">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-243">Format</span></span>

<span data-ttu-id="911fe-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="911fe-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-245">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-245">Pattern</span></span>

<span data-ttu-id="911fe-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-247">Checksum</span></span>

<span data-ttu-id="911fe-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-249">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-249">Definition</span></span>

<span data-ttu-id="911fe-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-252">From `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-253">Keywords</span></span>

<span data-ttu-id="911fe-254">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-254"></span></span>
|<span data-ttu-id="911fe-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-256">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-256">passport number</span></span>  <br/> <span data-ttu-id="911fe-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-257">estonian passport number</span></span>  <br/> <span data-ttu-id="911fe-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-258">passport no</span></span>  <br/> <span data-ttu-id="911fe-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="911fe-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="911fe-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="911fe-260">Finland</span></span>

<span data-ttu-id="911fe-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="911fe-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="911fe-262">フランス</span><span class="sxs-lookup"><span data-stu-id="911fe-262">France</span></span>

<span data-ttu-id="911fe-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="911fe-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="911fe-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="911fe-264">Germany</span></span>

<span data-ttu-id="911fe-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="911fe-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="911fe-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="911fe-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="911fe-267">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-267">Format</span></span>

<span data-ttu-id="911fe-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-269">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-269">Pattern</span></span>

<span data-ttu-id="911fe-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-271">Checksum</span></span>

<span data-ttu-id="911fe-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-273">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-273">Definition</span></span>

<span data-ttu-id="911fe-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-276">From `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-277">Keywords</span></span>

<span data-ttu-id="911fe-278">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-278"></span></span>
|<span data-ttu-id="911fe-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-280">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-280">passport number</span></span>  <br/> <span data-ttu-id="911fe-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-281">greek passport number</span></span>  <br/> <span data-ttu-id="911fe-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-282">passport no</span></span>  <br/> <span data-ttu-id="911fe-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="911fe-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="911fe-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="911fe-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="911fe-285">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-285">Format</span></span>

<span data-ttu-id="911fe-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-287">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-287">Pattern</span></span>

<span data-ttu-id="911fe-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-289">Checksum</span></span>

<span data-ttu-id="911fe-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-291">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-291">Definition</span></span>

<span data-ttu-id="911fe-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-294">From `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-295">Keywords</span></span>

<span data-ttu-id="911fe-296">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-296"></span></span>
|<span data-ttu-id="911fe-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-298">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-298">passport number</span></span>  <br/> <span data-ttu-id="911fe-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="911fe-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-300">passport no</span></span>  <br/> <span data-ttu-id="911fe-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="911fe-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="911fe-302">アイルランド</span><span class="sxs-lookup"><span data-stu-id="911fe-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="911fe-303">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-303">Format</span></span>

<span data-ttu-id="911fe-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-305">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-305">Pattern</span></span>

<span data-ttu-id="911fe-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="911fe-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="911fe-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="911fe-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="911fe-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="911fe-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-309">Checksum</span></span>

<span data-ttu-id="911fe-310">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-311">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-311">Definition</span></span>

<span data-ttu-id="911fe-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-314">From `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-315">Keywords</span></span>

<span data-ttu-id="911fe-316">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-316"></span></span>
|<span data-ttu-id="911fe-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-318">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-318">passport number</span></span>  <br/> <span data-ttu-id="911fe-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-319">irish passport number</span></span>  <br/> <span data-ttu-id="911fe-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-320">passport no</span></span>  <br/> <span data-ttu-id="911fe-321">pas</span><span class="sxs-lookup"><span data-stu-id="911fe-321">pas</span></span>  <br/> <span data-ttu-id="911fe-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="911fe-322">passport</span></span>  <br/> <span data-ttu-id="911fe-323">passeport</span><span class="sxs-lookup"><span data-stu-id="911fe-323">passeport</span></span>  <br/> <span data-ttu-id="911fe-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="911fe-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="911fe-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="911fe-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="911fe-326">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-326">Format</span></span>

<span data-ttu-id="911fe-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-328">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-328">Pattern</span></span>

<span data-ttu-id="911fe-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="911fe-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="911fe-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="911fe-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="911fe-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="911fe-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-332">Checksum</span></span>

<span data-ttu-id="911fe-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="911fe-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-334">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-334">Definition</span></span>

<span data-ttu-id="911fe-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-337">From `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-338">Keywords</span></span>

<span data-ttu-id="911fe-339">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-339"></span></span>
|<span data-ttu-id="911fe-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-341">italian passport number</span></span>  <br/> <span data-ttu-id="911fe-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="911fe-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="911fe-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="911fe-343">passaporto</span></span>  <br/> <span data-ttu-id="911fe-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="911fe-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="911fe-345">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-345">passport number</span></span>  <br/> <span data-ttu-id="911fe-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="911fe-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="911fe-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="911fe-347">passaporto numero</span></span>  <br/> <span data-ttu-id="911fe-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="911fe-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="911fe-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="911fe-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="911fe-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="911fe-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="911fe-351">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-351">Format</span></span>

<span data-ttu-id="911fe-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-353">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-353">Pattern</span></span>

<span data-ttu-id="911fe-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="911fe-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="911fe-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="911fe-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="911fe-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="911fe-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-357">Checksum</span></span>

<span data-ttu-id="911fe-358">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-359">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-359">Definition</span></span>

<span data-ttu-id="911fe-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-362">From `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-363">Keywords</span></span>

<span data-ttu-id="911fe-364">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-364"></span></span>
|<span data-ttu-id="911fe-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-366">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-366">passport number</span></span>  <br/> <span data-ttu-id="911fe-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-367">latvian passport number</span></span>  <br/> <span data-ttu-id="911fe-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-368">passport no</span></span>  <br/> <span data-ttu-id="911fe-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="911fe-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="911fe-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="911fe-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="911fe-371">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-371">Format</span></span>

<span data-ttu-id="911fe-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="911fe-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-373">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-373">Pattern</span></span>

<span data-ttu-id="911fe-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="911fe-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-375">Checksum</span></span>

<span data-ttu-id="911fe-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="911fe-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-377">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-377">Definition</span></span>

<span data-ttu-id="911fe-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-380">From `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-381">Keywords</span></span>

<span data-ttu-id="911fe-382">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-382"></span></span>
|<span data-ttu-id="911fe-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-384">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-384">passport number</span></span>  <br/> <span data-ttu-id="911fe-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="911fe-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-386">passport no</span></span>  <br/> <span data-ttu-id="911fe-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="911fe-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="911fe-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="911fe-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="911fe-389">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-389">Format</span></span>

<span data-ttu-id="911fe-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="911fe-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-391">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-391">Pattern</span></span>

<span data-ttu-id="911fe-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="911fe-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-393">Checksum</span></span>

<span data-ttu-id="911fe-394">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-395">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-395">Definition</span></span>

<span data-ttu-id="911fe-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-398">From `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-399">Keywords</span></span>

<span data-ttu-id="911fe-400">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-400"></span></span>
|<span data-ttu-id="911fe-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-402">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-402">passport number</span></span>  <br/> <span data-ttu-id="911fe-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-403">latvian passport number</span></span>  <br/> <span data-ttu-id="911fe-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-404">passport no</span></span>  <br/> <span data-ttu-id="911fe-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="911fe-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="911fe-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="911fe-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="911fe-407">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-407">Format</span></span>

<span data-ttu-id="911fe-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-409">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-409">Pattern</span></span>

 <span data-ttu-id="911fe-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="911fe-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-411">Checksum</span></span>

<span data-ttu-id="911fe-412">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-413">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-413">Definition</span></span>

<span data-ttu-id="911fe-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-416">From `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-417">Keywords</span></span>

<span data-ttu-id="911fe-418">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-418"></span></span>
|<span data-ttu-id="911fe-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-420">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-420">passport number</span></span>  <br/> <span data-ttu-id="911fe-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-421">maltese passport number</span></span>  <br/> <span data-ttu-id="911fe-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-422">passport no</span></span>  <br/> <span data-ttu-id="911fe-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="911fe-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="911fe-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="911fe-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="911fe-425">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-425">Format</span></span>

<span data-ttu-id="911fe-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="911fe-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-427">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-427">Pattern</span></span>

<span data-ttu-id="911fe-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="911fe-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-429">Checksum</span></span>

<span data-ttu-id="911fe-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="911fe-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-431">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-431">Definition</span></span>

<span data-ttu-id="911fe-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-434">From `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-435">Keywords</span></span>

<span data-ttu-id="911fe-436">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-436"></span></span>
|<span data-ttu-id="911fe-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-438">dutch passport number</span></span>  <br/> <span data-ttu-id="911fe-439">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-439">passport number</span></span>  <br/> <span data-ttu-id="911fe-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="911fe-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="911fe-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="911fe-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="911fe-442">paspoort</span></span>  <br/> <span data-ttu-id="911fe-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="911fe-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="911fe-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="911fe-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="911fe-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="911fe-445">Poland</span></span>

<span data-ttu-id="911fe-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="911fe-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="911fe-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="911fe-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="911fe-448">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-448">Format</span></span>

<span data-ttu-id="911fe-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="911fe-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-450">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-450">Pattern</span></span>

<span data-ttu-id="911fe-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="911fe-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="911fe-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="911fe-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="911fe-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="911fe-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-454">Checksum</span></span>

<span data-ttu-id="911fe-455">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-456">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-456">Definition</span></span>

<span data-ttu-id="911fe-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-459">From `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-460">Keywords</span></span>

<span data-ttu-id="911fe-461">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-461"></span></span>
|<span data-ttu-id="911fe-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-463">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-463">passport number</span></span>  <br/> <span data-ttu-id="911fe-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="911fe-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-465">passport no</span></span>  <br/> <span data-ttu-id="911fe-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="911fe-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="911fe-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="911fe-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="911fe-468">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-468">Format</span></span>

<span data-ttu-id="911fe-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-470">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-470">Pattern</span></span>

<span data-ttu-id="911fe-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-472">Checksum</span></span>

<span data-ttu-id="911fe-473">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-474">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-474">Definition</span></span>

<span data-ttu-id="911fe-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-477">From `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-478">Keywords</span></span>

<span data-ttu-id="911fe-479">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-479"></span></span>
|<span data-ttu-id="911fe-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-481">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-481">passport number</span></span>  <br/> <span data-ttu-id="911fe-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-482">romanian passport number</span></span>  <br/> <span data-ttu-id="911fe-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-483">passport no</span></span>  <br/> <span data-ttu-id="911fe-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="911fe-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="911fe-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="911fe-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="911fe-486">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-486">Format</span></span>

<span data-ttu-id="911fe-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="911fe-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-488">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-488">Pattern</span></span>

<span data-ttu-id="911fe-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="911fe-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-490">Checksum</span></span>

<span data-ttu-id="911fe-491">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-492">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-492">Definition</span></span>

<span data-ttu-id="911fe-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-495">From `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-496">Keywords</span></span>

<span data-ttu-id="911fe-497">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-497"></span></span>
|<span data-ttu-id="911fe-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-499">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-499">passport number</span></span>  <br/> <span data-ttu-id="911fe-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="911fe-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-501">passport no</span></span>  <br/> <span data-ttu-id="911fe-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="911fe-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="911fe-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="911fe-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="911fe-504">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-504">Format</span></span>

<span data-ttu-id="911fe-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-506">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-506">Pattern</span></span>

<span data-ttu-id="911fe-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="911fe-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="911fe-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="911fe-508">The letter "P"</span></span>
    
- <span data-ttu-id="911fe-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="911fe-509">One uppercase letter</span></span>
    
- <span data-ttu-id="911fe-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="911fe-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-511">Checksum</span></span>

<span data-ttu-id="911fe-512">いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-513">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-513">Definition</span></span>

<span data-ttu-id="911fe-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-516">From `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-517">Keywords</span></span>

<span data-ttu-id="911fe-518">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-518"></span></span>
|<span data-ttu-id="911fe-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-520">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-520">passport number</span></span>  <br/> <span data-ttu-id="911fe-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="911fe-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-522">passport no</span></span>  <br/> <span data-ttu-id="911fe-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="911fe-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="911fe-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="911fe-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="911fe-525">Format</span><span class="sxs-lookup"><span data-stu-id="911fe-525">Format</span></span>

<span data-ttu-id="911fe-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="911fe-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="911fe-527">パターン</span><span class="sxs-lookup"><span data-stu-id="911fe-527">Pattern</span></span>

<span data-ttu-id="911fe-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="911fe-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="911fe-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="911fe-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="911fe-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="911fe-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="911fe-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="911fe-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="911fe-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="911fe-532">Checksum</span></span>

<span data-ttu-id="911fe-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="911fe-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="911fe-534">定義</span><span class="sxs-lookup"><span data-stu-id="911fe-534">Definition</span></span>

<span data-ttu-id="911fe-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="911fe-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="911fe-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="911fe-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="911fe-537">From `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="911fe-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="911fe-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="911fe-538">Keywords</span></span>

<span data-ttu-id="911fe-539">| |</span><span class="sxs-lookup"><span data-stu-id="911fe-539"></span></span>
|<span data-ttu-id="911fe-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="911fe-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="911fe-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="911fe-541">passport</span></span>  <br/> <span data-ttu-id="911fe-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="911fe-542">spain passport</span></span>  <br/> <span data-ttu-id="911fe-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="911fe-543">passport book</span></span>  <br/> <span data-ttu-id="911fe-544">passport number</span><span class="sxs-lookup"><span data-stu-id="911fe-544">passport number</span></span>  <br/> <span data-ttu-id="911fe-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="911fe-545">passport no</span></span>  <br/> <span data-ttu-id="911fe-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="911fe-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="911fe-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="911fe-547">número pasaporte</span></span>  <br/> <span data-ttu-id="911fe-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="911fe-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="911fe-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="911fe-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="911fe-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="911fe-550">Sweden</span></span>

<span data-ttu-id="911fe-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="911fe-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="911fe-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="911fe-552">UK</span></span>

<span data-ttu-id="911fe-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="911fe-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="911fe-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="911fe-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="911fe-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="911fe-555">See also</span></span>

[<span data-ttu-id="911fe-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="911fe-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

