---
title: EU パスポート番号
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 56eb79dd067ca89600f92ea57eaaf01e562f9388
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938741"
---
# <a name="eu-passport-number"></a><span data-ttu-id="cf8b2-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-104">EU Passport Number</span></span>

<span data-ttu-id="cf8b2-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="cf8b2-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="cf8b2-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-108">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-108">Format</span></span>

<span data-ttu-id="cf8b2-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-110">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-110">Pattern</span></span>

<span data-ttu-id="cf8b2-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="cf8b2-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="cf8b2-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-113">One space (optional)</span></span>
    
- <span data-ttu-id="cf8b2-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cf8b2-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-115">Checksum</span></span>

<span data-ttu-id="cf8b2-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-117">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-117">Definition</span></span>

<span data-ttu-id="cf8b2-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-120">From `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-121">Keywords</span></span>

<span data-ttu-id="cf8b2-122">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-122">| |</span></span>
|<span data-ttu-id="cf8b2-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-124">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-124">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-125">austrian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-126">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="cf8b2-127">reisepass</span></span>  <br/> <span data-ttu-id="cf8b2-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="cf8b2-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="cf8b2-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="cf8b2-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-130">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-130">Format</span></span>

<span data-ttu-id="cf8b2-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-132">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-132">Pattern</span></span>

<span data-ttu-id="cf8b2-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-134">Checksum</span></span>

<span data-ttu-id="cf8b2-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-136">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-136">Definition</span></span>

<span data-ttu-id="cf8b2-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-139">From `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-140">Keywords</span></span>

<span data-ttu-id="cf8b2-141">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-141">| |</span></span>
|<span data-ttu-id="cf8b2-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-143">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-143">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-144">belgian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-145">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="cf8b2-146">paspoort</span></span>  <br/> <span data-ttu-id="cf8b2-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="cf8b2-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="cf8b2-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="cf8b2-148">reisepass kein</span></span>  <br/> <span data-ttu-id="cf8b2-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="cf8b2-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="cf8b2-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-151">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-151">Format</span></span>

<span data-ttu-id="cf8b2-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-153">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-153">Pattern</span></span>

 <span data-ttu-id="cf8b2-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-155">Checksum</span></span>

<span data-ttu-id="cf8b2-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-157">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-157">Definition</span></span>

<span data-ttu-id="cf8b2-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-160">From `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-161">Keywords</span></span>

<span data-ttu-id="cf8b2-162">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-162">| |</span></span>
|<span data-ttu-id="cf8b2-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-164">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-164">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-166">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="cf8b2-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="cf8b2-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-169">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-169">Format</span></span>

<span data-ttu-id="cf8b2-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-171">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-171">Pattern</span></span>

 <span data-ttu-id="cf8b2-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-173">Checksum</span></span>

<span data-ttu-id="cf8b2-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-175">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-175">Definition</span></span>

<span data-ttu-id="cf8b2-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-178">From `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-179">Keywords</span></span>

<span data-ttu-id="cf8b2-180">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-180">| |</span></span>
|<span data-ttu-id="cf8b2-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-182">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-182">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-183">croatian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-184">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="cf8b2-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="cf8b2-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="cf8b2-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-187">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-187">Format</span></span>

<span data-ttu-id="cf8b2-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-189">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-189">Pattern</span></span>

<span data-ttu-id="cf8b2-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-191">Checksum</span></span>

<span data-ttu-id="cf8b2-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-193">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-193">Definition</span></span>

<span data-ttu-id="cf8b2-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-196">From `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-197">Keywords</span></span>

<span data-ttu-id="cf8b2-198">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-198">| |</span></span>
|<span data-ttu-id="cf8b2-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-200">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-200">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="cf8b2-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-202">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="cf8b2-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="cf8b2-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="cf8b2-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-205">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-205">Format</span></span>

<span data-ttu-id="cf8b2-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-207">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-207">Pattern</span></span>

<span data-ttu-id="cf8b2-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-209">Checksum</span></span>

<span data-ttu-id="cf8b2-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-211">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-211">Definition</span></span>

<span data-ttu-id="cf8b2-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-214">From `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-215">Keywords</span></span>

<span data-ttu-id="cf8b2-216">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-216">| |</span></span>
|<span data-ttu-id="cf8b2-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-218">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-218">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-219">czech passport number</span></span>  <br/> <span data-ttu-id="cf8b2-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-220">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="cf8b2-221">cestovní pas</span></span>  <br/> <span data-ttu-id="cf8b2-222">pas</span><span class="sxs-lookup"><span data-stu-id="cf8b2-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="cf8b2-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="cf8b2-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-224">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-224">Format</span></span>

<span data-ttu-id="cf8b2-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-226">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-226">Pattern</span></span>

 <span data-ttu-id="cf8b2-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-228">Checksum</span></span>

<span data-ttu-id="cf8b2-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-230">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-230">Definition</span></span>

<span data-ttu-id="cf8b2-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-233">From `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-234">Keywords</span></span>

<span data-ttu-id="cf8b2-235">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-235">| |</span></span>
|<span data-ttu-id="cf8b2-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-237">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-237">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-238">danish passport number</span></span>  <br/> <span data-ttu-id="cf8b2-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-239">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-240">pas</span><span class="sxs-lookup"><span data-stu-id="cf8b2-240">pas</span></span>  <br/> <span data-ttu-id="cf8b2-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="cf8b2-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="cf8b2-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-243">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-243">Format</span></span>

<span data-ttu-id="cf8b2-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-245">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-245">Pattern</span></span>

<span data-ttu-id="cf8b2-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-247">Checksum</span></span>

<span data-ttu-id="cf8b2-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-249">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-249">Definition</span></span>

<span data-ttu-id="cf8b2-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-252">From `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-253">Keywords</span></span>

<span data-ttu-id="cf8b2-254">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-254">| |</span></span>
|<span data-ttu-id="cf8b2-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-256">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-256">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-257">estonian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-258">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="cf8b2-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="cf8b2-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="cf8b2-260">Finland</span></span>

<span data-ttu-id="cf8b2-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="cf8b2-262">フランス</span><span class="sxs-lookup"><span data-stu-id="cf8b2-262">France</span></span>

<span data-ttu-id="cf8b2-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="cf8b2-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-264">Germany</span></span>

<span data-ttu-id="cf8b2-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="cf8b2-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-267">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-267">Format</span></span>

<span data-ttu-id="cf8b2-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-269">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-269">Pattern</span></span>

<span data-ttu-id="cf8b2-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-271">Checksum</span></span>

<span data-ttu-id="cf8b2-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-273">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-273">Definition</span></span>

<span data-ttu-id="cf8b2-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-276">From `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-277">Keywords</span></span>

<span data-ttu-id="cf8b2-278">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-278">| |</span></span>
|<span data-ttu-id="cf8b2-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-280">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-280">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-281">greek passport number</span></span>  <br/> <span data-ttu-id="cf8b2-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-282">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="cf8b2-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="cf8b2-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="cf8b2-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-285">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-285">Format</span></span>

<span data-ttu-id="cf8b2-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-287">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-287">Pattern</span></span>

<span data-ttu-id="cf8b2-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-289">Checksum</span></span>

<span data-ttu-id="cf8b2-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-291">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-291">Definition</span></span>

<span data-ttu-id="cf8b2-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-294">From `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-295">Keywords</span></span>

<span data-ttu-id="cf8b2-296">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-296">| |</span></span>
|<span data-ttu-id="cf8b2-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-298">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-298">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-300">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="cf8b2-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="cf8b2-302">アイルランド</span><span class="sxs-lookup"><span data-stu-id="cf8b2-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-303">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-303">Format</span></span>

<span data-ttu-id="cf8b2-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-305">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-305">Pattern</span></span>

<span data-ttu-id="cf8b2-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="cf8b2-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="cf8b2-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cf8b2-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-309">Checksum</span></span>

<span data-ttu-id="cf8b2-310">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-311">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-311">Definition</span></span>

<span data-ttu-id="cf8b2-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-314">From `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-315">Keywords</span></span>

<span data-ttu-id="cf8b2-316">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-316">| |</span></span>
|<span data-ttu-id="cf8b2-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-318">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-318">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-319">irish passport number</span></span>  <br/> <span data-ttu-id="cf8b2-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-320">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-321">pas</span><span class="sxs-lookup"><span data-stu-id="cf8b2-321">pas</span></span>  <br/> <span data-ttu-id="cf8b2-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="cf8b2-322">passport</span></span>  <br/> <span data-ttu-id="cf8b2-323">passeport</span><span class="sxs-lookup"><span data-stu-id="cf8b2-323">passeport</span></span>  <br/> <span data-ttu-id="cf8b2-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="cf8b2-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="cf8b2-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-326">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-326">Format</span></span>

<span data-ttu-id="cf8b2-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-328">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-328">Pattern</span></span>

<span data-ttu-id="cf8b2-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="cf8b2-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="cf8b2-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cf8b2-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-332">Checksum</span></span>

<span data-ttu-id="cf8b2-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-334">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-334">Definition</span></span>

<span data-ttu-id="cf8b2-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-337">From `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-338">Keywords</span></span>

<span data-ttu-id="cf8b2-339">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-339">| |</span></span>
|<span data-ttu-id="cf8b2-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-341">italian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="cf8b2-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="cf8b2-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="cf8b2-343">passaporto</span></span>  <br/> <span data-ttu-id="cf8b2-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="cf8b2-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="cf8b2-345">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-345">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="cf8b2-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="cf8b2-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="cf8b2-347">passaporto numero</span></span>  <br/> <span data-ttu-id="cf8b2-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="cf8b2-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="cf8b2-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="cf8b2-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="cf8b2-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-351">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-351">Format</span></span>

<span data-ttu-id="cf8b2-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-353">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-353">Pattern</span></span>

<span data-ttu-id="cf8b2-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="cf8b2-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="cf8b2-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cf8b2-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-357">Checksum</span></span>

<span data-ttu-id="cf8b2-358">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-359">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-359">Definition</span></span>

<span data-ttu-id="cf8b2-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-362">From `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-363">Keywords</span></span>

<span data-ttu-id="cf8b2-364">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-364">| |</span></span>
|<span data-ttu-id="cf8b2-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-366">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-366">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-367">latvian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-368">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="cf8b2-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="cf8b2-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-371">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-371">Format</span></span>

<span data-ttu-id="cf8b2-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-373">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-373">Pattern</span></span>

<span data-ttu-id="cf8b2-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-375">Checksum</span></span>

<span data-ttu-id="cf8b2-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-377">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-377">Definition</span></span>

<span data-ttu-id="cf8b2-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-380">From `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-381">Keywords</span></span>

<span data-ttu-id="cf8b2-382">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-382">| |</span></span>
|<span data-ttu-id="cf8b2-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-384">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-384">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-386">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="cf8b2-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="cf8b2-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="cf8b2-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-389">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-389">Format</span></span>

<span data-ttu-id="cf8b2-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-391">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-391">Pattern</span></span>

<span data-ttu-id="cf8b2-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-393">Checksum</span></span>

<span data-ttu-id="cf8b2-394">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-395">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-395">Definition</span></span>

<span data-ttu-id="cf8b2-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-398">From `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-399">Keywords</span></span>

<span data-ttu-id="cf8b2-400">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-400">| |</span></span>
|<span data-ttu-id="cf8b2-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-402">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-402">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-403">latvian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-404">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="cf8b2-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="cf8b2-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-407">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-407">Format</span></span>

<span data-ttu-id="cf8b2-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-409">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-409">Pattern</span></span>

 <span data-ttu-id="cf8b2-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-411">Checksum</span></span>

<span data-ttu-id="cf8b2-412">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-413">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-413">Definition</span></span>

<span data-ttu-id="cf8b2-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-416">From `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-417">Keywords</span></span>

<span data-ttu-id="cf8b2-418">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-418">| |</span></span>
|<span data-ttu-id="cf8b2-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-420">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-420">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-421">maltese passport number</span></span>  <br/> <span data-ttu-id="cf8b2-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-422">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="cf8b2-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="cf8b2-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-425">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-425">Format</span></span>

<span data-ttu-id="cf8b2-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-427">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-427">Pattern</span></span>

<span data-ttu-id="cf8b2-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-429">Checksum</span></span>

<span data-ttu-id="cf8b2-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-431">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-431">Definition</span></span>

<span data-ttu-id="cf8b2-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-434">From `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-435">Keywords</span></span>

<span data-ttu-id="cf8b2-436">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-436">| |</span></span>
|<span data-ttu-id="cf8b2-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-438">dutch passport number</span></span>  <br/> <span data-ttu-id="cf8b2-439">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-439">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="cf8b2-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="cf8b2-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="cf8b2-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="cf8b2-442">paspoort</span></span>  <br/> <span data-ttu-id="cf8b2-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="cf8b2-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="cf8b2-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="cf8b2-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="cf8b2-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="cf8b2-445">Poland</span></span>

<span data-ttu-id="cf8b2-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="cf8b2-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="cf8b2-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-448">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-448">Format</span></span>

<span data-ttu-id="cf8b2-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-450">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-450">Pattern</span></span>

<span data-ttu-id="cf8b2-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="cf8b2-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="cf8b2-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="cf8b2-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cf8b2-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-454">Checksum</span></span>

<span data-ttu-id="cf8b2-455">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-456">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-456">Definition</span></span>

<span data-ttu-id="cf8b2-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-459">From `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-460">Keywords</span></span>

<span data-ttu-id="cf8b2-461">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-461">| |</span></span>
|<span data-ttu-id="cf8b2-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-463">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-463">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="cf8b2-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-465">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="cf8b2-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="cf8b2-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-468">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-468">Format</span></span>

<span data-ttu-id="cf8b2-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-470">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-470">Pattern</span></span>

<span data-ttu-id="cf8b2-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-472">Checksum</span></span>

<span data-ttu-id="cf8b2-473">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-474">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-474">Definition</span></span>

<span data-ttu-id="cf8b2-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-477">From `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-478">Keywords</span></span>

<span data-ttu-id="cf8b2-479">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-479">| |</span></span>
|<span data-ttu-id="cf8b2-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-481">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-481">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-482">romanian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-483">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="cf8b2-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="cf8b2-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-486">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-486">Format</span></span>

<span data-ttu-id="cf8b2-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-488">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-488">Pattern</span></span>

<span data-ttu-id="cf8b2-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cf8b2-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-490">Checksum</span></span>

<span data-ttu-id="cf8b2-491">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-492">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-492">Definition</span></span>

<span data-ttu-id="cf8b2-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-495">From `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-496">Keywords</span></span>

<span data-ttu-id="cf8b2-497">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-497">| |</span></span>
|<span data-ttu-id="cf8b2-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-499">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-499">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-501">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="cf8b2-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="cf8b2-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="cf8b2-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-504">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-504">Format</span></span>

<span data-ttu-id="cf8b2-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-506">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-506">Pattern</span></span>

<span data-ttu-id="cf8b2-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="cf8b2-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="cf8b2-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="cf8b2-508">The letter "P"</span></span>
    
- <span data-ttu-id="cf8b2-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-509">One uppercase letter</span></span>
    
- <span data-ttu-id="cf8b2-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cf8b2-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-511">Checksum</span></span>

<span data-ttu-id="cf8b2-512">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-513">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-513">Definition</span></span>

<span data-ttu-id="cf8b2-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-516">From `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-517">Keywords</span></span>

<span data-ttu-id="cf8b2-518">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-518">| |</span></span>
|<span data-ttu-id="cf8b2-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-520">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-520">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="cf8b2-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-522">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="cf8b2-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="cf8b2-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="cf8b2-525">Format</span><span class="sxs-lookup"><span data-stu-id="cf8b2-525">Format</span></span>

<span data-ttu-id="cf8b2-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cf8b2-527">パターン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-527">Pattern</span></span>

<span data-ttu-id="cf8b2-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="cf8b2-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="cf8b2-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="cf8b2-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="cf8b2-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="cf8b2-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cf8b2-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="cf8b2-532">Checksum</span></span>

<span data-ttu-id="cf8b2-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="cf8b2-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="cf8b2-534">定義</span><span class="sxs-lookup"><span data-stu-id="cf8b2-534">Definition</span></span>

<span data-ttu-id="cf8b2-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cf8b2-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cf8b2-537">From `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="cf8b2-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf8b2-538">Keywords</span></span>

<span data-ttu-id="cf8b2-539">| |</span><span class="sxs-lookup"><span data-stu-id="cf8b2-539">| |</span></span>
|<span data-ttu-id="cf8b2-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="cf8b2-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="cf8b2-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="cf8b2-541">passport</span></span>  <br/> <span data-ttu-id="cf8b2-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="cf8b2-542">spain passport</span></span>  <br/> <span data-ttu-id="cf8b2-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="cf8b2-543">passport book</span></span>  <br/> <span data-ttu-id="cf8b2-544">passport number</span><span class="sxs-lookup"><span data-stu-id="cf8b2-544">passport number</span></span>  <br/> <span data-ttu-id="cf8b2-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="cf8b2-545">passport no</span></span>  <br/> <span data-ttu-id="cf8b2-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="cf8b2-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="cf8b2-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="cf8b2-547">número pasaporte</span></span>  <br/> <span data-ttu-id="cf8b2-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="cf8b2-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="cf8b2-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="cf8b2-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="cf8b2-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="cf8b2-550">Sweden</span></span>

<span data-ttu-id="cf8b2-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="cf8b2-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="cf8b2-552">UK</span></span>

<span data-ttu-id="cf8b2-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8b2-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="cf8b2-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="cf8b2-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf8b2-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf8b2-555">See also</span></span>

[<span data-ttu-id="cf8b2-556">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="cf8b2-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

