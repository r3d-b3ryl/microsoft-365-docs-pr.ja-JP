---
title: EU パスポート番号
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592118"
---
# <a name="eu-passport-number"></a><span data-ttu-id="5e8a4-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-104">EU Passport Number</span></span>

<span data-ttu-id="5e8a4-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="5e8a4-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5e8a4-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-108">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-108">Format</span></span>

<span data-ttu-id="5e8a4-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-110">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-110">Pattern</span></span>

<span data-ttu-id="5e8a4-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="5e8a4-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="5e8a4-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-113">One space (optional)</span></span>
    
- <span data-ttu-id="5e8a4-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e8a4-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-115">Checksum</span></span>

<span data-ttu-id="5e8a4-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-117">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-117">Definition</span></span>

<span data-ttu-id="5e8a4-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-120">From `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-121">Keywords</span></span>

<span data-ttu-id="5e8a4-122">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-122">| |</span></span>
|<span data-ttu-id="5e8a4-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-124">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-124">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-125">austrian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-126">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="5e8a4-127">reisepass</span></span>  <br/> <span data-ttu-id="5e8a4-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="5e8a4-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="5e8a4-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="5e8a4-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-130">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-130">Format</span></span>

<span data-ttu-id="5e8a4-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-132">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-132">Pattern</span></span>

<span data-ttu-id="5e8a4-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-134">Checksum</span></span>

<span data-ttu-id="5e8a4-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-136">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-136">Definition</span></span>

<span data-ttu-id="5e8a4-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-139">From `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-140">Keywords</span></span>

<span data-ttu-id="5e8a4-141">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-141">| |</span></span>
|<span data-ttu-id="5e8a4-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-143">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-143">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-144">belgian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-145">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="5e8a4-146">paspoort</span></span>  <br/> <span data-ttu-id="5e8a4-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="5e8a4-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="5e8a4-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="5e8a4-148">reisepass kein</span></span>  <br/> <span data-ttu-id="5e8a4-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="5e8a4-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="5e8a4-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-151">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-151">Format</span></span>

<span data-ttu-id="5e8a4-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-153">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-153">Pattern</span></span>

 <span data-ttu-id="5e8a4-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-155">Checksum</span></span>

<span data-ttu-id="5e8a4-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-157">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-157">Definition</span></span>

<span data-ttu-id="5e8a4-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-160">From `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-161">Keywords</span></span>

<span data-ttu-id="5e8a4-162">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-162">| |</span></span>
|<span data-ttu-id="5e8a4-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-164">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-164">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-166">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="5e8a4-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="5e8a4-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-169">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-169">Format</span></span>

<span data-ttu-id="5e8a4-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-171">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-171">Pattern</span></span>

 <span data-ttu-id="5e8a4-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-173">Checksum</span></span>

<span data-ttu-id="5e8a4-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-175">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-175">Definition</span></span>

<span data-ttu-id="5e8a4-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-178">From `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-179">Keywords</span></span>

<span data-ttu-id="5e8a4-180">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-180">| |</span></span>
|<span data-ttu-id="5e8a4-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-182">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-182">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-183">croatian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-184">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="5e8a4-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="5e8a4-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="5e8a4-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-187">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-187">Format</span></span>

<span data-ttu-id="5e8a4-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-189">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-189">Pattern</span></span>

<span data-ttu-id="5e8a4-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-191">Checksum</span></span>

<span data-ttu-id="5e8a4-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-193">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-193">Definition</span></span>

<span data-ttu-id="5e8a4-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-196">From `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-197">Keywords</span></span>

<span data-ttu-id="5e8a4-198">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-198">| |</span></span>
|<span data-ttu-id="5e8a4-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-200">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-200">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="5e8a4-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-202">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="5e8a4-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="5e8a4-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="5e8a4-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-205">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-205">Format</span></span>

<span data-ttu-id="5e8a4-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-207">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-207">Pattern</span></span>

<span data-ttu-id="5e8a4-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-209">Checksum</span></span>

<span data-ttu-id="5e8a4-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-211">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-211">Definition</span></span>

<span data-ttu-id="5e8a4-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-214">From `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-215">Keywords</span></span>

<span data-ttu-id="5e8a4-216">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-216">| |</span></span>
|<span data-ttu-id="5e8a4-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-218">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-218">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-219">czech passport number</span></span>  <br/> <span data-ttu-id="5e8a4-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-220">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="5e8a4-221">cestovní pas</span></span>  <br/> <span data-ttu-id="5e8a4-222">pas</span><span class="sxs-lookup"><span data-stu-id="5e8a4-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="5e8a4-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="5e8a4-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-224">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-224">Format</span></span>

<span data-ttu-id="5e8a4-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-226">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-226">Pattern</span></span>

 <span data-ttu-id="5e8a4-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-228">Checksum</span></span>

<span data-ttu-id="5e8a4-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-230">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-230">Definition</span></span>

<span data-ttu-id="5e8a4-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-233">From `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-234">Keywords</span></span>

<span data-ttu-id="5e8a4-235">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-235">| |</span></span>
|<span data-ttu-id="5e8a4-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-237">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-237">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-238">danish passport number</span></span>  <br/> <span data-ttu-id="5e8a4-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-239">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-240">pas</span><span class="sxs-lookup"><span data-stu-id="5e8a4-240">pas</span></span>  <br/> <span data-ttu-id="5e8a4-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="5e8a4-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="5e8a4-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-243">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-243">Format</span></span>

<span data-ttu-id="5e8a4-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-245">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-245">Pattern</span></span>

<span data-ttu-id="5e8a4-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-247">Checksum</span></span>

<span data-ttu-id="5e8a4-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-249">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-249">Definition</span></span>

<span data-ttu-id="5e8a4-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-252">From `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-253">Keywords</span></span>

<span data-ttu-id="5e8a4-254">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-254">| |</span></span>
|<span data-ttu-id="5e8a4-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-256">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-256">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-257">estonian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-258">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="5e8a4-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="5e8a4-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="5e8a4-260">Finland</span></span>

<span data-ttu-id="5e8a4-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="5e8a4-262">フランス</span><span class="sxs-lookup"><span data-stu-id="5e8a4-262">France</span></span>

<span data-ttu-id="5e8a4-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="5e8a4-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-264">Germany</span></span>

<span data-ttu-id="5e8a4-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="5e8a4-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-267">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-267">Format</span></span>

<span data-ttu-id="5e8a4-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-269">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-269">Pattern</span></span>

<span data-ttu-id="5e8a4-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-271">Checksum</span></span>

<span data-ttu-id="5e8a4-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-273">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-273">Definition</span></span>

<span data-ttu-id="5e8a4-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-276">From `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-277">Keywords</span></span>

<span data-ttu-id="5e8a4-278">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-278">| |</span></span>
|<span data-ttu-id="5e8a4-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-280">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-280">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-281">greek passport number</span></span>  <br/> <span data-ttu-id="5e8a4-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-282">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="5e8a4-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="5e8a4-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="5e8a4-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-285">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-285">Format</span></span>

<span data-ttu-id="5e8a4-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-287">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-287">Pattern</span></span>

<span data-ttu-id="5e8a4-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-289">Checksum</span></span>

<span data-ttu-id="5e8a4-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-291">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-291">Definition</span></span>

<span data-ttu-id="5e8a4-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-294">From `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-295">Keywords</span></span>

<span data-ttu-id="5e8a4-296">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-296">| |</span></span>
|<span data-ttu-id="5e8a4-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-298">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-298">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-300">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="5e8a4-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="5e8a4-302">アイルランド</span><span class="sxs-lookup"><span data-stu-id="5e8a4-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-303">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-303">Format</span></span>

<span data-ttu-id="5e8a4-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-305">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-305">Pattern</span></span>

<span data-ttu-id="5e8a4-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="5e8a4-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="5e8a4-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e8a4-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-309">Checksum</span></span>

<span data-ttu-id="5e8a4-310">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-311">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-311">Definition</span></span>

<span data-ttu-id="5e8a4-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-314">From `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-315">Keywords</span></span>

<span data-ttu-id="5e8a4-316">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-316">| |</span></span>
|<span data-ttu-id="5e8a4-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-318">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-318">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-319">irish passport number</span></span>  <br/> <span data-ttu-id="5e8a4-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-320">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-321">pas</span><span class="sxs-lookup"><span data-stu-id="5e8a4-321">pas</span></span>  <br/> <span data-ttu-id="5e8a4-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="5e8a4-322">passport</span></span>  <br/> <span data-ttu-id="5e8a4-323">passeport</span><span class="sxs-lookup"><span data-stu-id="5e8a4-323">passeport</span></span>  <br/> <span data-ttu-id="5e8a4-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="5e8a4-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="5e8a4-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-326">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-326">Format</span></span>

<span data-ttu-id="5e8a4-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-328">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-328">Pattern</span></span>

<span data-ttu-id="5e8a4-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="5e8a4-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="5e8a4-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e8a4-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-332">Checksum</span></span>

<span data-ttu-id="5e8a4-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-334">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-334">Definition</span></span>

<span data-ttu-id="5e8a4-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-337">From `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-338">Keywords</span></span>

<span data-ttu-id="5e8a4-339">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-339">| |</span></span>
|<span data-ttu-id="5e8a4-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-341">italian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="5e8a4-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="5e8a4-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="5e8a4-343">passaporto</span></span>  <br/> <span data-ttu-id="5e8a4-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="5e8a4-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="5e8a4-345">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-345">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="5e8a4-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="5e8a4-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="5e8a4-347">passaporto numero</span></span>  <br/> <span data-ttu-id="5e8a4-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="5e8a4-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="5e8a4-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="5e8a4-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="5e8a4-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-351">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-351">Format</span></span>

<span data-ttu-id="5e8a4-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-353">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-353">Pattern</span></span>

<span data-ttu-id="5e8a4-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="5e8a4-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="5e8a4-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e8a4-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-357">Checksum</span></span>

<span data-ttu-id="5e8a4-358">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-359">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-359">Definition</span></span>

<span data-ttu-id="5e8a4-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-362">From `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-363">Keywords</span></span>

<span data-ttu-id="5e8a4-364">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-364">| |</span></span>
|<span data-ttu-id="5e8a4-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-366">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-366">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-367">latvian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-368">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="5e8a4-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="5e8a4-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-371">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-371">Format</span></span>

<span data-ttu-id="5e8a4-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-373">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-373">Pattern</span></span>

<span data-ttu-id="5e8a4-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-375">Checksum</span></span>

<span data-ttu-id="5e8a4-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-377">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-377">Definition</span></span>

<span data-ttu-id="5e8a4-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-380">From `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-381">Keywords</span></span>

<span data-ttu-id="5e8a4-382">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-382">| |</span></span>
|<span data-ttu-id="5e8a4-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-384">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-384">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-386">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="5e8a4-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="5e8a4-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="5e8a4-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-389">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-389">Format</span></span>

<span data-ttu-id="5e8a4-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-391">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-391">Pattern</span></span>

<span data-ttu-id="5e8a4-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-393">Checksum</span></span>

<span data-ttu-id="5e8a4-394">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-395">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-395">Definition</span></span>

<span data-ttu-id="5e8a4-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-398">From `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-399">Keywords</span></span>

<span data-ttu-id="5e8a4-400">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-400">| |</span></span>
|<span data-ttu-id="5e8a4-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-402">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-402">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-403">latvian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-404">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="5e8a4-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="5e8a4-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-407">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-407">Format</span></span>

<span data-ttu-id="5e8a4-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-409">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-409">Pattern</span></span>

 <span data-ttu-id="5e8a4-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-411">Checksum</span></span>

<span data-ttu-id="5e8a4-412">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-413">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-413">Definition</span></span>

<span data-ttu-id="5e8a4-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-416">From `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-417">Keywords</span></span>

<span data-ttu-id="5e8a4-418">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-418">| |</span></span>
|<span data-ttu-id="5e8a4-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-420">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-420">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-421">maltese passport number</span></span>  <br/> <span data-ttu-id="5e8a4-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-422">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="5e8a4-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="5e8a4-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-425">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-425">Format</span></span>

<span data-ttu-id="5e8a4-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-427">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-427">Pattern</span></span>

<span data-ttu-id="5e8a4-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-429">Checksum</span></span>

<span data-ttu-id="5e8a4-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-431">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-431">Definition</span></span>

<span data-ttu-id="5e8a4-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-434">From `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-435">Keywords</span></span>

<span data-ttu-id="5e8a4-436">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-436">| |</span></span>
|<span data-ttu-id="5e8a4-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-438">dutch passport number</span></span>  <br/> <span data-ttu-id="5e8a4-439">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-439">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="5e8a4-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="5e8a4-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="5e8a4-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="5e8a4-442">paspoort</span></span>  <br/> <span data-ttu-id="5e8a4-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="5e8a4-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="5e8a4-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="5e8a4-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="5e8a4-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="5e8a4-445">Poland</span></span>

<span data-ttu-id="5e8a4-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="5e8a4-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="5e8a4-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-448">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-448">Format</span></span>

<span data-ttu-id="5e8a4-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-450">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-450">Pattern</span></span>

<span data-ttu-id="5e8a4-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5e8a4-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="5e8a4-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="5e8a4-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e8a4-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-454">Checksum</span></span>

<span data-ttu-id="5e8a4-455">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-456">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-456">Definition</span></span>

<span data-ttu-id="5e8a4-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-459">From `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-460">Keywords</span></span>

<span data-ttu-id="5e8a4-461">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-461">| |</span></span>
|<span data-ttu-id="5e8a4-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-463">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-463">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="5e8a4-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-465">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="5e8a4-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="5e8a4-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-468">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-468">Format</span></span>

<span data-ttu-id="5e8a4-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-470">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-470">Pattern</span></span>

<span data-ttu-id="5e8a4-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-472">Checksum</span></span>

<span data-ttu-id="5e8a4-473">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-474">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-474">Definition</span></span>

<span data-ttu-id="5e8a4-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-477">From `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-478">Keywords</span></span>

<span data-ttu-id="5e8a4-479">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-479">| |</span></span>
|<span data-ttu-id="5e8a4-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-481">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-481">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-482">romanian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-483">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="5e8a4-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="5e8a4-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-486">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-486">Format</span></span>

<span data-ttu-id="5e8a4-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-488">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-488">Pattern</span></span>

<span data-ttu-id="5e8a4-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e8a4-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-490">Checksum</span></span>

<span data-ttu-id="5e8a4-491">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-492">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-492">Definition</span></span>

<span data-ttu-id="5e8a4-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-495">From `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-496">Keywords</span></span>

<span data-ttu-id="5e8a4-497">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-497">| |</span></span>
|<span data-ttu-id="5e8a4-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-499">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-499">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-501">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="5e8a4-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="5e8a4-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="5e8a4-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-504">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-504">Format</span></span>

<span data-ttu-id="5e8a4-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-506">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-506">Pattern</span></span>

<span data-ttu-id="5e8a4-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5e8a4-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="5e8a4-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="5e8a4-508">The letter "P"</span></span>
    
- <span data-ttu-id="5e8a4-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-509">One uppercase letter</span></span>
    
- <span data-ttu-id="5e8a4-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e8a4-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-511">Checksum</span></span>

<span data-ttu-id="5e8a4-512">いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-513">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-513">Definition</span></span>

<span data-ttu-id="5e8a4-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-516">From `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-517">Keywords</span></span>

<span data-ttu-id="5e8a4-518">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-518">| |</span></span>
|<span data-ttu-id="5e8a4-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-520">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-520">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="5e8a4-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-522">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="5e8a4-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="5e8a4-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="5e8a4-525">Format</span><span class="sxs-lookup"><span data-stu-id="5e8a4-525">Format</span></span>

<span data-ttu-id="5e8a4-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e8a4-527">パターン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-527">Pattern</span></span>

<span data-ttu-id="5e8a4-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="5e8a4-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="5e8a4-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5e8a4-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="5e8a4-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5e8a4-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e8a4-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="5e8a4-532">Checksum</span></span>

<span data-ttu-id="5e8a4-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="5e8a4-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e8a4-534">定義</span><span class="sxs-lookup"><span data-stu-id="5e8a4-534">Definition</span></span>

<span data-ttu-id="5e8a4-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e8a4-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e8a4-537">From `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e8a4-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="5e8a4-538">Keywords</span></span>

<span data-ttu-id="5e8a4-539">| |</span><span class="sxs-lookup"><span data-stu-id="5e8a4-539">| |</span></span>
|<span data-ttu-id="5e8a4-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5e8a4-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5e8a4-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="5e8a4-541">passport</span></span>  <br/> <span data-ttu-id="5e8a4-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="5e8a4-542">spain passport</span></span>  <br/> <span data-ttu-id="5e8a4-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="5e8a4-543">passport book</span></span>  <br/> <span data-ttu-id="5e8a4-544">passport number</span><span class="sxs-lookup"><span data-stu-id="5e8a4-544">passport number</span></span>  <br/> <span data-ttu-id="5e8a4-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="5e8a4-545">passport no</span></span>  <br/> <span data-ttu-id="5e8a4-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="5e8a4-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="5e8a4-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="5e8a4-547">número pasaporte</span></span>  <br/> <span data-ttu-id="5e8a4-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="5e8a4-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="5e8a4-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="5e8a4-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="5e8a4-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="5e8a4-550">Sweden</span></span>

<span data-ttu-id="5e8a4-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="5e8a4-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="5e8a4-552">UK</span></span>

<span data-ttu-id="5e8a4-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e8a4-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="5e8a4-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="5e8a4-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e8a4-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e8a4-555">See also</span></span>

[<span data-ttu-id="5e8a4-556">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="5e8a4-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

