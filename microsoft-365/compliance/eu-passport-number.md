---
title: EU パスポート番号
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805950"
---
# <a name="eu-passport-number"></a><span data-ttu-id="2d43a-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-104">EU Passport Number</span></span>

<span data-ttu-id="2d43a-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="2d43a-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="2d43a-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2d43a-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="2d43a-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-108">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-108">Format</span></span>

<span data-ttu-id="2d43a-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-110">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-110">Pattern</span></span>

<span data-ttu-id="2d43a-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="2d43a-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="2d43a-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="2d43a-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="2d43a-113">One space (optional)</span></span>
    
- <span data-ttu-id="2d43a-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d43a-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-115">Checksum</span></span>

<span data-ttu-id="2d43a-116">該当しない</span><span class="sxs-lookup"><span data-stu-id="2d43a-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-117">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-117">Definition</span></span>

<span data-ttu-id="2d43a-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-120">From `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-121">Keywords</span></span>

<span data-ttu-id="2d43a-122">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-122"></span></span>
|<span data-ttu-id="2d43a-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-124">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-124">passport number</span></span>  <br/> <span data-ttu-id="2d43a-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-125">austrian passport number</span></span>  <br/> <span data-ttu-id="2d43a-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-126">passport no</span></span>  <br/> <span data-ttu-id="2d43a-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="2d43a-127">reisepass</span></span>  <br/> <span data-ttu-id="2d43a-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="2d43a-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="2d43a-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="2d43a-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-130">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-130">Format</span></span>

<span data-ttu-id="2d43a-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-132">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-132">Pattern</span></span>

<span data-ttu-id="2d43a-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-134">Checksum</span></span>

<span data-ttu-id="2d43a-135">該当しない</span><span class="sxs-lookup"><span data-stu-id="2d43a-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-136">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-136">Definition</span></span>

<span data-ttu-id="2d43a-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-139">From `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-140">Keywords</span></span>

<span data-ttu-id="2d43a-141">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-141"></span></span>
|<span data-ttu-id="2d43a-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-143">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-143">passport number</span></span>  <br/> <span data-ttu-id="2d43a-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-144">belgian passport number</span></span>  <br/> <span data-ttu-id="2d43a-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-145">passport no</span></span>  <br/> <span data-ttu-id="2d43a-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="2d43a-146">paspoort</span></span>  <br/> <span data-ttu-id="2d43a-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="2d43a-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="2d43a-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="2d43a-148">reisepass kein</span></span>  <br/> <span data-ttu-id="2d43a-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="2d43a-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="2d43a-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="2d43a-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-151">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-151">Format</span></span>

<span data-ttu-id="2d43a-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-153">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-153">Pattern</span></span>

 <span data-ttu-id="2d43a-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2d43a-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-155">Checksum</span></span>

<span data-ttu-id="2d43a-156">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-157">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-157">Definition</span></span>

<span data-ttu-id="2d43a-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-160">From `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-161">Keywords</span></span>

<span data-ttu-id="2d43a-162">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-162"></span></span>
|<span data-ttu-id="2d43a-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-164">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-164">passport number</span></span>  <br/> <span data-ttu-id="2d43a-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="2d43a-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-166">passport no</span></span>  <br/> <span data-ttu-id="2d43a-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="2d43a-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="2d43a-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="2d43a-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-169">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-169">Format</span></span>

<span data-ttu-id="2d43a-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-171">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-171">Pattern</span></span>

 <span data-ttu-id="2d43a-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2d43a-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-173">Checksum</span></span>

<span data-ttu-id="2d43a-174">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-175">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-175">Definition</span></span>

<span data-ttu-id="2d43a-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-178">From `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-179">Keywords</span></span>

<span data-ttu-id="2d43a-180">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-180"></span></span>
|<span data-ttu-id="2d43a-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-182">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-182">passport number</span></span>  <br/> <span data-ttu-id="2d43a-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-183">croatian passport number</span></span>  <br/> <span data-ttu-id="2d43a-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-184">passport no</span></span>  <br/> <span data-ttu-id="2d43a-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="2d43a-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="2d43a-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="2d43a-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-187">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-187">Format</span></span>

<span data-ttu-id="2d43a-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-189">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-189">Pattern</span></span>

<span data-ttu-id="2d43a-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-191">Checksum</span></span>

<span data-ttu-id="2d43a-192">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-193">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-193">Definition</span></span>

<span data-ttu-id="2d43a-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-196">From `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-197">Keywords</span></span>

<span data-ttu-id="2d43a-198">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-198"></span></span>
|<span data-ttu-id="2d43a-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-200">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-200">passport number</span></span>  <br/> <span data-ttu-id="2d43a-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="2d43a-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-202">passport no</span></span>  <br/> <span data-ttu-id="2d43a-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="2d43a-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="2d43a-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="2d43a-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-205">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-205">Format</span></span>

<span data-ttu-id="2d43a-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-207">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-207">Pattern</span></span>

<span data-ttu-id="2d43a-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-209">Checksum</span></span>

<span data-ttu-id="2d43a-210">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-211">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-211">Definition</span></span>

<span data-ttu-id="2d43a-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-214">From `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-215">Keywords</span></span>

<span data-ttu-id="2d43a-216">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-216"></span></span>
|<span data-ttu-id="2d43a-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-218">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-218">passport number</span></span>  <br/> <span data-ttu-id="2d43a-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-219">czech passport number</span></span>  <br/> <span data-ttu-id="2d43a-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-220">passport no</span></span>  <br/> <span data-ttu-id="2d43a-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="2d43a-221">cestovní pas</span></span>  <br/> <span data-ttu-id="2d43a-222">pas</span><span class="sxs-lookup"><span data-stu-id="2d43a-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="2d43a-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="2d43a-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-224">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-224">Format</span></span>

<span data-ttu-id="2d43a-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-226">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-226">Pattern</span></span>

 <span data-ttu-id="2d43a-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2d43a-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-228">Checksum</span></span>

<span data-ttu-id="2d43a-229">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-230">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-230">Definition</span></span>

<span data-ttu-id="2d43a-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-233">From `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-234">Keywords</span></span>

<span data-ttu-id="2d43a-235">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-235"></span></span>
|<span data-ttu-id="2d43a-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-237">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-237">passport number</span></span>  <br/> <span data-ttu-id="2d43a-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-238">danish passport number</span></span>  <br/> <span data-ttu-id="2d43a-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-239">passport no</span></span>  <br/> <span data-ttu-id="2d43a-240">pas</span><span class="sxs-lookup"><span data-stu-id="2d43a-240">pas</span></span>  <br/> <span data-ttu-id="2d43a-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="2d43a-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="2d43a-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="2d43a-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-243">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-243">Format</span></span>

<span data-ttu-id="2d43a-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="2d43a-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-245">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-245">Pattern</span></span>

<span data-ttu-id="2d43a-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-247">Checksum</span></span>

<span data-ttu-id="2d43a-248">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-249">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-249">Definition</span></span>

<span data-ttu-id="2d43a-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-252">From `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-253">Keywords</span></span>

<span data-ttu-id="2d43a-254">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-254"></span></span>
|<span data-ttu-id="2d43a-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-256">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-256">passport number</span></span>  <br/> <span data-ttu-id="2d43a-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-257">estonian passport number</span></span>  <br/> <span data-ttu-id="2d43a-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-258">passport no</span></span>  <br/> <span data-ttu-id="2d43a-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="2d43a-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="2d43a-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="2d43a-260">Finland</span></span>

<span data-ttu-id="2d43a-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d43a-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="2d43a-262">フランス</span><span class="sxs-lookup"><span data-stu-id="2d43a-262">France</span></span>

<span data-ttu-id="2d43a-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d43a-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="2d43a-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="2d43a-264">Germany</span></span>

<span data-ttu-id="2d43a-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d43a-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="2d43a-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="2d43a-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-267">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-267">Format</span></span>

<span data-ttu-id="2d43a-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-269">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-269">Pattern</span></span>

<span data-ttu-id="2d43a-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-271">Checksum</span></span>

<span data-ttu-id="2d43a-272">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-273">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-273">Definition</span></span>

<span data-ttu-id="2d43a-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-276">From `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-277">Keywords</span></span>

<span data-ttu-id="2d43a-278">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-278"></span></span>
|<span data-ttu-id="2d43a-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-280">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-280">passport number</span></span>  <br/> <span data-ttu-id="2d43a-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-281">greek passport number</span></span>  <br/> <span data-ttu-id="2d43a-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-282">passport no</span></span>  <br/> <span data-ttu-id="2d43a-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="2d43a-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="2d43a-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="2d43a-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-285">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-285">Format</span></span>

<span data-ttu-id="2d43a-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-287">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-287">Pattern</span></span>

<span data-ttu-id="2d43a-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-289">Checksum</span></span>

<span data-ttu-id="2d43a-290">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-291">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-291">Definition</span></span>

<span data-ttu-id="2d43a-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-294">From `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-295">Keywords</span></span>

<span data-ttu-id="2d43a-296">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-296"></span></span>
|<span data-ttu-id="2d43a-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-298">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-298">passport number</span></span>  <br/> <span data-ttu-id="2d43a-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="2d43a-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-300">passport no</span></span>  <br/> <span data-ttu-id="2d43a-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="2d43a-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="2d43a-302">アイルランド</span><span class="sxs-lookup"><span data-stu-id="2d43a-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-303">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-303">Format</span></span>

<span data-ttu-id="2d43a-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-305">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-305">Pattern</span></span>

<span data-ttu-id="2d43a-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="2d43a-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="2d43a-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="2d43a-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d43a-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-309">Checksum</span></span>

<span data-ttu-id="2d43a-310">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-311">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-311">Definition</span></span>

<span data-ttu-id="2d43a-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-314">From `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-315">Keywords</span></span>

<span data-ttu-id="2d43a-316">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-316"></span></span>
|<span data-ttu-id="2d43a-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-318">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-318">passport number</span></span>  <br/> <span data-ttu-id="2d43a-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-319">irish passport number</span></span>  <br/> <span data-ttu-id="2d43a-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-320">passport no</span></span>  <br/> <span data-ttu-id="2d43a-321">pas</span><span class="sxs-lookup"><span data-stu-id="2d43a-321">pas</span></span>  <br/> <span data-ttu-id="2d43a-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="2d43a-322">passport</span></span>  <br/> <span data-ttu-id="2d43a-323">passeport</span><span class="sxs-lookup"><span data-stu-id="2d43a-323">passeport</span></span>  <br/> <span data-ttu-id="2d43a-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="2d43a-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="2d43a-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="2d43a-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-326">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-326">Format</span></span>

<span data-ttu-id="2d43a-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-328">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-328">Pattern</span></span>

<span data-ttu-id="2d43a-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="2d43a-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="2d43a-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="2d43a-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d43a-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-332">Checksum</span></span>

<span data-ttu-id="2d43a-333">該当しない</span><span class="sxs-lookup"><span data-stu-id="2d43a-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-334">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-334">Definition</span></span>

<span data-ttu-id="2d43a-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-337">From `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-338">Keywords</span></span>

<span data-ttu-id="2d43a-339">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-339"></span></span>
|<span data-ttu-id="2d43a-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-341">italian passport number</span></span>  <br/> <span data-ttu-id="2d43a-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="2d43a-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="2d43a-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="2d43a-343">passaporto</span></span>  <br/> <span data-ttu-id="2d43a-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="2d43a-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="2d43a-345">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-345">passport number</span></span>  <br/> <span data-ttu-id="2d43a-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="2d43a-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="2d43a-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="2d43a-347">passaporto numero</span></span>  <br/> <span data-ttu-id="2d43a-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="2d43a-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="2d43a-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="2d43a-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="2d43a-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="2d43a-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-351">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-351">Format</span></span>

<span data-ttu-id="2d43a-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-353">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-353">Pattern</span></span>

<span data-ttu-id="2d43a-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="2d43a-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="2d43a-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="2d43a-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d43a-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-357">Checksum</span></span>

<span data-ttu-id="2d43a-358">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-359">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-359">Definition</span></span>

<span data-ttu-id="2d43a-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-362">From `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-363">Keywords</span></span>

<span data-ttu-id="2d43a-364">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-364"></span></span>
|<span data-ttu-id="2d43a-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-366">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-366">passport number</span></span>  <br/> <span data-ttu-id="2d43a-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-367">latvian passport number</span></span>  <br/> <span data-ttu-id="2d43a-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-368">passport no</span></span>  <br/> <span data-ttu-id="2d43a-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="2d43a-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="2d43a-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="2d43a-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-371">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-371">Format</span></span>

<span data-ttu-id="2d43a-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="2d43a-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-373">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-373">Pattern</span></span>

<span data-ttu-id="2d43a-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-375">Checksum</span></span>

<span data-ttu-id="2d43a-376">該当しない</span><span class="sxs-lookup"><span data-stu-id="2d43a-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-377">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-377">Definition</span></span>

<span data-ttu-id="2d43a-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-380">From `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-381">Keywords</span></span>

<span data-ttu-id="2d43a-382">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-382"></span></span>
|<span data-ttu-id="2d43a-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-384">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-384">passport number</span></span>  <br/> <span data-ttu-id="2d43a-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="2d43a-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-386">passport no</span></span>  <br/> <span data-ttu-id="2d43a-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="2d43a-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="2d43a-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="2d43a-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-389">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-389">Format</span></span>

<span data-ttu-id="2d43a-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="2d43a-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-391">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-391">Pattern</span></span>

<span data-ttu-id="2d43a-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-393">Checksum</span></span>

<span data-ttu-id="2d43a-394">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-395">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-395">Definition</span></span>

<span data-ttu-id="2d43a-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-398">From `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-399">Keywords</span></span>

<span data-ttu-id="2d43a-400">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-400"></span></span>
|<span data-ttu-id="2d43a-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-402">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-402">passport number</span></span>  <br/> <span data-ttu-id="2d43a-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-403">latvian passport number</span></span>  <br/> <span data-ttu-id="2d43a-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-404">passport no</span></span>  <br/> <span data-ttu-id="2d43a-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="2d43a-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="2d43a-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="2d43a-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-407">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-407">Format</span></span>

<span data-ttu-id="2d43a-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-409">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-409">Pattern</span></span>

 <span data-ttu-id="2d43a-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2d43a-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-411">Checksum</span></span>

<span data-ttu-id="2d43a-412">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-413">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-413">Definition</span></span>

<span data-ttu-id="2d43a-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-416">From `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-417">Keywords</span></span>

<span data-ttu-id="2d43a-418">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-418"></span></span>
|<span data-ttu-id="2d43a-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-420">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-420">passport number</span></span>  <br/> <span data-ttu-id="2d43a-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-421">maltese passport number</span></span>  <br/> <span data-ttu-id="2d43a-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-422">passport no</span></span>  <br/> <span data-ttu-id="2d43a-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="2d43a-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="2d43a-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="2d43a-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-425">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-425">Format</span></span>

<span data-ttu-id="2d43a-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="2d43a-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-427">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-427">Pattern</span></span>

<span data-ttu-id="2d43a-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-429">Checksum</span></span>

<span data-ttu-id="2d43a-430">該当しない</span><span class="sxs-lookup"><span data-stu-id="2d43a-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-431">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-431">Definition</span></span>

<span data-ttu-id="2d43a-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-434">From `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-435">Keywords</span></span>

<span data-ttu-id="2d43a-436">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-436"></span></span>
|<span data-ttu-id="2d43a-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-438">dutch passport number</span></span>  <br/> <span data-ttu-id="2d43a-439">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-439">passport number</span></span>  <br/> <span data-ttu-id="2d43a-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="2d43a-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="2d43a-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="2d43a-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="2d43a-442">paspoort</span></span>  <br/> <span data-ttu-id="2d43a-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="2d43a-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="2d43a-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="2d43a-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="2d43a-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="2d43a-445">Poland</span></span>

<span data-ttu-id="2d43a-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d43a-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="2d43a-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="2d43a-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-448">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-448">Format</span></span>

<span data-ttu-id="2d43a-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-450">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-450">Pattern</span></span>

<span data-ttu-id="2d43a-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2d43a-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="2d43a-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2d43a-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="2d43a-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d43a-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-454">Checksum</span></span>

<span data-ttu-id="2d43a-455">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-456">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-456">Definition</span></span>

<span data-ttu-id="2d43a-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-459">From `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-460">Keywords</span></span>

<span data-ttu-id="2d43a-461">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-461"></span></span>
|<span data-ttu-id="2d43a-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-463">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-463">passport number</span></span>  <br/> <span data-ttu-id="2d43a-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="2d43a-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-465">passport no</span></span>  <br/> <span data-ttu-id="2d43a-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="2d43a-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="2d43a-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="2d43a-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-468">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-468">Format</span></span>

<span data-ttu-id="2d43a-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-470">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-470">Pattern</span></span>

<span data-ttu-id="2d43a-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-472">Checksum</span></span>

<span data-ttu-id="2d43a-473">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-474">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-474">Definition</span></span>

<span data-ttu-id="2d43a-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-477">From `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-478">Keywords</span></span>

<span data-ttu-id="2d43a-479">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-479"></span></span>
|<span data-ttu-id="2d43a-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-481">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-481">passport number</span></span>  <br/> <span data-ttu-id="2d43a-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-482">romanian passport number</span></span>  <br/> <span data-ttu-id="2d43a-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-483">passport no</span></span>  <br/> <span data-ttu-id="2d43a-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="2d43a-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="2d43a-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="2d43a-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-486">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-486">Format</span></span>

<span data-ttu-id="2d43a-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="2d43a-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-488">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-488">Pattern</span></span>

<span data-ttu-id="2d43a-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d43a-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-490">Checksum</span></span>

<span data-ttu-id="2d43a-491">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-492">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-492">Definition</span></span>

<span data-ttu-id="2d43a-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-495">From `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-496">Keywords</span></span>

<span data-ttu-id="2d43a-497">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-497"></span></span>
|<span data-ttu-id="2d43a-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-499">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-499">passport number</span></span>  <br/> <span data-ttu-id="2d43a-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="2d43a-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-501">passport no</span></span>  <br/> <span data-ttu-id="2d43a-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="2d43a-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="2d43a-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="2d43a-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-504">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-504">Format</span></span>

<span data-ttu-id="2d43a-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-506">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-506">Pattern</span></span>

<span data-ttu-id="2d43a-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2d43a-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="2d43a-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="2d43a-508">The letter "P"</span></span>
    
- <span data-ttu-id="2d43a-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="2d43a-509">One uppercase letter</span></span>
    
- <span data-ttu-id="2d43a-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d43a-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-511">Checksum</span></span>

<span data-ttu-id="2d43a-512">不要</span><span class="sxs-lookup"><span data-stu-id="2d43a-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-513">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-513">Definition</span></span>

<span data-ttu-id="2d43a-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-516">From `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-517">Keywords</span></span>

<span data-ttu-id="2d43a-518">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-518"></span></span>
|<span data-ttu-id="2d43a-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-520">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-520">passport number</span></span>  <br/> <span data-ttu-id="2d43a-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="2d43a-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-522">passport no</span></span>  <br/> <span data-ttu-id="2d43a-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="2d43a-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="2d43a-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="2d43a-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2d43a-525">Format</span><span class="sxs-lookup"><span data-stu-id="2d43a-525">Format</span></span>

<span data-ttu-id="2d43a-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="2d43a-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d43a-527">パターン</span><span class="sxs-lookup"><span data-stu-id="2d43a-527">Pattern</span></span>

<span data-ttu-id="2d43a-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="2d43a-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="2d43a-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="2d43a-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="2d43a-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="2d43a-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="2d43a-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2d43a-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d43a-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d43a-532">Checksum</span></span>

<span data-ttu-id="2d43a-533">該当しない</span><span class="sxs-lookup"><span data-stu-id="2d43a-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d43a-534">定義</span><span class="sxs-lookup"><span data-stu-id="2d43a-534">Definition</span></span>

<span data-ttu-id="2d43a-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d43a-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d43a-537">From `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2d43a-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d43a-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="2d43a-538">Keywords</span></span>

<span data-ttu-id="2d43a-539">| |</span><span class="sxs-lookup"><span data-stu-id="2d43a-539"></span></span>
|<span data-ttu-id="2d43a-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="2d43a-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="2d43a-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="2d43a-541">passport</span></span>  <br/> <span data-ttu-id="2d43a-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="2d43a-542">spain passport</span></span>  <br/> <span data-ttu-id="2d43a-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="2d43a-543">passport book</span></span>  <br/> <span data-ttu-id="2d43a-544">passport number</span><span class="sxs-lookup"><span data-stu-id="2d43a-544">passport number</span></span>  <br/> <span data-ttu-id="2d43a-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="2d43a-545">passport no</span></span>  <br/> <span data-ttu-id="2d43a-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="2d43a-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="2d43a-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="2d43a-547">número pasaporte</span></span>  <br/> <span data-ttu-id="2d43a-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="2d43a-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="2d43a-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="2d43a-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="2d43a-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="2d43a-550">Sweden</span></span>

<span data-ttu-id="2d43a-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d43a-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="2d43a-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="2d43a-552">UK</span></span>

<span data-ttu-id="2d43a-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d43a-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="2d43a-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2d43a-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d43a-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d43a-555">See also</span></span>

[<span data-ttu-id="2d43a-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="2d43a-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

