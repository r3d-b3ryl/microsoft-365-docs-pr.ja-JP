---
title: EU 税務識別番号
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
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591018"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="3347d-104">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-104">EU Tax Identification Number</span></span>

<span data-ttu-id="3347d-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号 (TIN) 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="3347d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="3347d-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="3347d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3347d-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="3347d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3347d-108">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-108">Format</span></span>

<span data-ttu-id="3347d-109">任意指定のハイフンとスラッシュ (/) を含む9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-110">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-110">Pattern</span></span>

<span data-ttu-id="3347d-111">任意指定のハイフンとスラッシュ (/) を含む9桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="3347d-112">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-112">Two digits</span></span> 
    
- <span data-ttu-id="3347d-113">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="3347d-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="3347d-114">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-114">Three digits</span></span>
    
- <span data-ttu-id="3347d-115">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="3347d-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="3347d-116">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-117">Checksum</span></span>

<span data-ttu-id="3347d-118">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-119">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-119">Definition</span></span>

<span data-ttu-id="3347d-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-121">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-122">From `Keywords_austria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-123">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-124">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-125">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="3347d-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-127">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-127">tax number</span></span>
  
<span data-ttu-id="3347d-128">番号</span><span class="sxs-lookup"><span data-stu-id="3347d-128">number</span></span>
  
<span data-ttu-id="3347d-129">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="3347d-129">tax registration number</span></span>
  
<span data-ttu-id="3347d-130">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-130">tax id</span></span>
  
<span data-ttu-id="3347d-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="3347d-131">st.nr.</span></span>
  
<span data-ttu-id="3347d-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="3347d-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="3347d-133">ベルギー</span><span class="sxs-lookup"><span data-stu-id="3347d-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3347d-134">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-134">Format</span></span>

<span data-ttu-id="3347d-135">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-136">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-136">Pattern</span></span>

<span data-ttu-id="3347d-137">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-137">11 digits:</span></span>
  
- <span data-ttu-id="3347d-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-138">Two digits</span></span>
    
- <span data-ttu-id="3347d-139">"0" または "1"</span><span class="sxs-lookup"><span data-stu-id="3347d-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="3347d-140">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-140">One digit</span></span>
    
- <span data-ttu-id="3347d-141">"0" または "1" または "2" または "3"</span><span class="sxs-lookup"><span data-stu-id="3347d-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="3347d-142">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-143">Checksum</span></span>

<span data-ttu-id="3347d-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-145">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-145">Definition</span></span>

<span data-ttu-id="3347d-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-147">正規表現`Regex_belgium_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3347d-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-148">From `Keywords_belgium_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="3347d-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-151">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-151">tax number</span></span>
  
<span data-ttu-id="3347d-152">国内登録番号</span><span class="sxs-lookup"><span data-stu-id="3347d-152">national registration number</span></span>
  
<span data-ttu-id="3347d-153">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="3347d-153">tax registration number</span></span>
  
<span data-ttu-id="3347d-154">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-154">tax id</span></span>
  
<span data-ttu-id="3347d-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="3347d-155">nif</span></span>
  
<span data-ttu-id="3347d-156">\n\n#</span><span class="sxs-lookup"><span data-stu-id="3347d-156">nif#</span></span>
  
<span data-ttu-id="3347d-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="3347d-157">numéro de registre national</span></span>
  
<span data-ttu-id="3347d-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="3347d-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="3347d-159">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="3347d-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3347d-160">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-160">Format</span></span>

<span data-ttu-id="3347d-161">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-162">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-162">Pattern</span></span>

<span data-ttu-id="3347d-163">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-164">Checksum</span></span>

<span data-ttu-id="3347d-165">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-166">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-166">Definition</span></span>

<span data-ttu-id="3347d-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-168">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-169">From `Keywords_bulgaria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-170">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-171">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-172">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="3347d-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-174">bucn</span><span class="sxs-lookup"><span data-stu-id="3347d-174">bucn</span></span>
  
<span data-ttu-id="3347d-175">一律の民事番号</span><span class="sxs-lookup"><span data-stu-id="3347d-175">uniform civil number</span></span>
  
<span data-ttu-id="3347d-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="3347d-176">bucn#</span></span>
  
<span data-ttu-id="3347d-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="3347d-178">uniform 民事 id</span><span class="sxs-lookup"><span data-stu-id="3347d-178">uniform civil id</span></span>
  
<span data-ttu-id="3347d-179">uniform 民事 no</span><span class="sxs-lookup"><span data-stu-id="3347d-179">uniform civil no</span></span>
  
<span data-ttu-id="3347d-180">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="3347d-180">egn</span></span>
  
<span data-ttu-id="3347d-181">ブルガリアの一様な民事訴訟番号</span><span class="sxs-lookup"><span data-stu-id="3347d-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="3347d-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="3347d-182">uniformcivilno#</span></span>
  
<span data-ttu-id="3347d-183">「//入力 n」#</span><span class="sxs-lookup"><span data-stu-id="3347d-183">egn#</span></span>
  
<span data-ttu-id="3347d-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="3347d-184">униформ граждански номер</span></span>
  
<span data-ttu-id="3347d-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="3347d-185">униформ id</span></span>
  
<span data-ttu-id="3347d-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="3347d-186">униформ граждански id</span></span>
  
<span data-ttu-id="3347d-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="3347d-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="3347d-188">クロアチア</span><span class="sxs-lookup"><span data-stu-id="3347d-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3347d-189">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-189">Format</span></span>

<span data-ttu-id="3347d-190">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-191">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-191">Pattern</span></span>

<span data-ttu-id="3347d-192">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-192">11 digits:</span></span>
  
- <span data-ttu-id="3347d-193">ランダムに選択された10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="3347d-194">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="3347d-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-195">Checksum</span></span>

<span data-ttu-id="3347d-196">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-197">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-197">Definition</span></span>

<span data-ttu-id="3347d-198">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-199">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-200">From `Keywords_croatia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-202">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-203">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="3347d-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-205">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-205">tax number</span></span>
  
<span data-ttu-id="3347d-206">申告</span><span class="sxs-lookup"><span data-stu-id="3347d-206">tax</span></span>
  
<span data-ttu-id="3347d-207">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-207">tax id</span></span>
  
<span data-ttu-id="3347d-208">oid</span><span class="sxs-lookup"><span data-stu-id="3347d-208">oid</span></span>
  
<span data-ttu-id="3347d-209">ドーナツ#</span><span class="sxs-lookup"><span data-stu-id="3347d-209">oid#</span></span>
  
<span data-ttu-id="3347d-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="3347d-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="3347d-211">キプロス</span><span class="sxs-lookup"><span data-stu-id="3347d-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3347d-212">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-212">Format</span></span>

<span data-ttu-id="3347d-213">指定したパターンの8桁の数字と1文字</span><span class="sxs-lookup"><span data-stu-id="3347d-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-214">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-214">Pattern</span></span>

<span data-ttu-id="3347d-215">8桁の数字と1つの文字:</span><span class="sxs-lookup"><span data-stu-id="3347d-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="3347d-216">"0"</span><span class="sxs-lookup"><span data-stu-id="3347d-216">A "0"</span></span> 
    
- <span data-ttu-id="3347d-217">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="3347d-217">Seven digits</span></span>
    
- <span data-ttu-id="3347d-218">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3347d-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-219">Checksum</span></span>

<span data-ttu-id="3347d-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-221">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-221">Definition</span></span>

<span data-ttu-id="3347d-222">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-223">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-224">From `Keywords_cyprus_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-226">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="3347d-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-229">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-229">tax number</span></span>
  
<span data-ttu-id="3347d-230">申告</span><span class="sxs-lookup"><span data-stu-id="3347d-230">tax</span></span>
  
<span data-ttu-id="3347d-231">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-231">tax id</span></span>
  
<span data-ttu-id="3347d-232">税 id コード</span><span class="sxs-lookup"><span data-stu-id="3347d-232">tax identification code</span></span>
  
<span data-ttu-id="3347d-233">認め</span><span class="sxs-lookup"><span data-stu-id="3347d-233">tic</span></span>
  
<span data-ttu-id="3347d-234">認め#</span><span class="sxs-lookup"><span data-stu-id="3347d-234">tic#</span></span>
  
<span data-ttu-id="3347d-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="3347d-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="3347d-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="3347d-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="3347d-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="3347d-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="3347d-238">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="3347d-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3347d-239">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-239">Format</span></span>

<span data-ttu-id="3347d-240">9桁または10桁の数字 (省略可能な円記号付き)</span><span class="sxs-lookup"><span data-stu-id="3347d-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-241">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-241">Pattern</span></span>

<span data-ttu-id="3347d-242">9桁または10桁の数字で、省略可能な backslashl を指定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="3347d-243">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-243">Six digits</span></span> 
    
- <span data-ttu-id="3347d-244">円記号 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="3347d-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="3347d-245">3桁または4桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-246">Checksum</span></span>

<span data-ttu-id="3347d-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-248">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-248">Definition</span></span>

<span data-ttu-id="3347d-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-250">正規表現`Regex_czech_republic_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3347d-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-251">From `Keywords_czech_republic_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-252">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="3347d-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-254">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-254">tax number</span></span>
  
<span data-ttu-id="3347d-255">申告</span><span class="sxs-lookup"><span data-stu-id="3347d-255">tax</span></span>
  
<span data-ttu-id="3347d-256">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-256">tax id</span></span>
  
<span data-ttu-id="3347d-257">個人番号</span><span class="sxs-lookup"><span data-stu-id="3347d-257">personal number</span></span>
  
<span data-ttu-id="3347d-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="3347d-258">daňové číslo</span></span>
  
<span data-ttu-id="3347d-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="3347d-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="3347d-260">デンマーク</span><span class="sxs-lookup"><span data-stu-id="3347d-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3347d-261">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-261">Format</span></span>

<span data-ttu-id="3347d-262">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="3347d-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-263">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-263">Pattern</span></span>

<span data-ttu-id="3347d-264">Hyphenl を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="3347d-265">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="3347d-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="3347d-266">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="3347d-266">A hyphen</span></span>
    
- <span data-ttu-id="3347d-267">1桁目が誕生日の世紀に対応し、最後の桁は個人の性別に対応する4桁の数字 (男性の場合は奇数、女性の場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="3347d-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-268">Checksum</span></span>

<span data-ttu-id="3347d-269">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-270">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-270">Definition</span></span>

<span data-ttu-id="3347d-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-272">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-273">From `Keywords_denmark_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-275">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-276">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="3347d-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-278">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-278">tax number</span></span>
  
<span data-ttu-id="3347d-279">申告</span><span class="sxs-lookup"><span data-stu-id="3347d-279">tax</span></span>
  
<span data-ttu-id="3347d-280">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-280">tax id</span></span>
  
<span data-ttu-id="3347d-281">cpr 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-281">cpr number</span></span>
  
<span data-ttu-id="3347d-282">cpr#</span><span class="sxs-lookup"><span data-stu-id="3347d-282">cpr#</span></span>
  
<span data-ttu-id="3347d-283">nummer の sk</span><span class="sxs-lookup"><span data-stu-id="3347d-283">skat nummer</span></span>
  
<span data-ttu-id="3347d-284">id の sk</span><span class="sxs-lookup"><span data-stu-id="3347d-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="3347d-285">エストニア</span><span class="sxs-lookup"><span data-stu-id="3347d-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3347d-286">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-286">Format</span></span>

<span data-ttu-id="3347d-287">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-288">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-288">Pattern</span></span>

<span data-ttu-id="3347d-289">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-289">11 digits:</span></span>
  
-  <span data-ttu-id="3347d-290">性別と世紀に対応する1桁の数字。奇数は男性を表し、偶数の場合は1、2は19世紀に対しては女性を示します。20世紀に3、4世紀。21世紀の場合は5、6。</span><span class="sxs-lookup"><span data-stu-id="3347d-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="3347d-291">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="3347d-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="3347d-292">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="3347d-293">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="3347d-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-294">Checksum</span></span>

<span data-ttu-id="3347d-295">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-296">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-296">Definition</span></span>

<span data-ttu-id="3347d-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-298">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-299">From `Keywords_estonia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-301">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-302">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="3347d-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-304">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-304">tax number</span></span>
  
<span data-ttu-id="3347d-305">申告</span><span class="sxs-lookup"><span data-stu-id="3347d-305">tax</span></span>
  
<span data-ttu-id="3347d-306">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-306">tax id</span></span>
  
<span data-ttu-id="3347d-307">個人コード</span><span class="sxs-lookup"><span data-stu-id="3347d-307">personal code</span></span>
  
<span data-ttu-id="3347d-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="3347d-308">maksunumber</span></span>
  
<span data-ttu-id="3347d-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="3347d-309">maksu id</span></span>
  
<span data-ttu-id="3347d-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="3347d-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="3347d-311">フィンランド</span><span class="sxs-lookup"><span data-stu-id="3347d-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="3347d-312">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-312">Format</span></span>

<span data-ttu-id="3347d-313">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="3347d-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-314">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-314">Pattern</span></span>

<span data-ttu-id="3347d-315">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="3347d-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="3347d-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-316">Six digits</span></span>
    
- <span data-ttu-id="3347d-317">プラス記号、マイナス記号、または文字 "A" (大文字小文字を区別しない) の1つ。プラス記号を1800-1899 の間に置きます。マイナス記号は、1900-1999 の間に出生することを意味2000します。</span><span class="sxs-lookup"><span data-stu-id="3347d-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="3347d-318">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-318">Three digits</span></span>
    
- <span data-ttu-id="3347d-319">1つの文字または1つの番号</span><span class="sxs-lookup"><span data-stu-id="3347d-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-320">Checksum</span></span>

<span data-ttu-id="3347d-321">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-322">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-322">Definition</span></span>

<span data-ttu-id="3347d-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-324">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-325">From `Keywords_finland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-327">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-328">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="3347d-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-330">identification number</span><span class="sxs-lookup"><span data-stu-id="3347d-330">identification number</span></span>
  
<span data-ttu-id="3347d-331">個人 id</span><span class="sxs-lookup"><span data-stu-id="3347d-331">personal id</span></span>
  
<span data-ttu-id="3347d-332">id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-332">identity number</span></span>
  
<span data-ttu-id="3347d-333">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-333">finnish national id number</span></span>
  
<span data-ttu-id="3347d-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-334">personalidnumber#</span></span>
  
<span data-ttu-id="3347d-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="3347d-335">national identification number</span></span>
  
<span data-ttu-id="3347d-336">id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-336">id number</span></span>
  
<span data-ttu-id="3347d-337">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-337">national id no.</span></span>
  
<span data-ttu-id="3347d-338">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-338">national id number</span></span>
  
<span data-ttu-id="3347d-339">id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-339">id no</span></span>
  
<span data-ttu-id="3347d-340">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="3347d-340">tunnistenumero</span></span>
  
<span data-ttu-id="3347d-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="3347d-341">henkilötunnus</span></span>
  
<span data-ttu-id="3347d-342">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="3347d-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="3347d-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="3347d-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="3347d-344">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="3347d-344">identiteetti numero</span></span>
  
<span data-ttu-id="3347d-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="3347d-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="3347d-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="3347d-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="3347d-347">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="3347d-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="3347d-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="3347d-348">tunnusnumero</span></span>
  
<span data-ttu-id="3347d-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="3347d-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="3347d-350">フランス</span><span class="sxs-lookup"><span data-stu-id="3347d-350">France</span></span>

### <a name="format"></a><span data-ttu-id="3347d-351">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-351">Format</span></span>

<span data-ttu-id="3347d-352">各ユーザーの13桁の数字、およびエンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-353">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-353">Pattern</span></span>

<span data-ttu-id="3347d-354">個人の場合は13桁。</span><span class="sxs-lookup"><span data-stu-id="3347d-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="3347d-355">0、1、2、または3である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="3347d-356">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-356">12 digits</span></span>
    
<span data-ttu-id="3347d-357">エンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-358">Checksum</span></span>

<span data-ttu-id="3347d-359">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-360">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-360">Definition</span></span>

<span data-ttu-id="3347d-361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-362">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-363">From `Keywords_france_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-365">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-366">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="3347d-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-368">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-368">tax identification number</span></span>
  
<span data-ttu-id="3347d-369">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-369">tax number</span></span>
  
<span data-ttu-id="3347d-370">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-370">tax id</span></span>
  
<span data-ttu-id="3347d-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="3347d-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="3347d-372">ドイツ</span><span class="sxs-lookup"><span data-stu-id="3347d-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="3347d-373">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-373">Format</span></span>

<span data-ttu-id="3347d-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-375">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-375">Pattern</span></span>

<span data-ttu-id="3347d-376">11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-376">11 digits :</span></span>
  
-  <span data-ttu-id="3347d-377">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-377">Ten digits</span></span> 
    
- <span data-ttu-id="3347d-378">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="3347d-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-379">Checksum</span></span>

<span data-ttu-id="3347d-380">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-381">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-381">Definition</span></span>

<span data-ttu-id="3347d-382">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-383">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-384">From `Keywords_germany_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-386">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="3347d-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-389">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-389">tax number</span></span>
  
<span data-ttu-id="3347d-390">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-390">tax no.</span></span>
  
<span data-ttu-id="3347d-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-391">taxno#</span></span>
  
<span data-ttu-id="3347d-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-392">taxnumber#</span></span>
  
<span data-ttu-id="3347d-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-393">taxnumber</span></span>
  
<span data-ttu-id="3347d-394">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-394">tax id</span></span>
  
<span data-ttu-id="3347d-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-395">taxid#</span></span>
  
<span data-ttu-id="3347d-396">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-396">tax identification number</span></span>
  
<span data-ttu-id="3347d-397">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-397">tax identification no.</span></span>
  
<span data-ttu-id="3347d-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="3347d-398">steuernummer</span></span>
  
<span data-ttu-id="3347d-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="3347d-399">steuer id</span></span>
  
<span data-ttu-id="3347d-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="3347d-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="3347d-401">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="3347d-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3347d-402">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-402">Format</span></span>

<span data-ttu-id="3347d-403">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-404">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-404">Pattern</span></span>

<span data-ttu-id="3347d-405">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-406">Checksum</span></span>

<span data-ttu-id="3347d-407">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-408">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-408">Definition</span></span>

<span data-ttu-id="3347d-409">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-410">正規表現`Regex_greece_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3347d-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-411">From `Keywords_greece_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-412">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="3347d-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-414">afm</span><span class="sxs-lookup"><span data-stu-id="3347d-414">afm</span></span>
  
<span data-ttu-id="3347d-415">は</span><span class="sxs-lookup"><span data-stu-id="3347d-415">tin</span></span>
  
<span data-ttu-id="3347d-416">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-416">tax id no.</span></span>
  
<span data-ttu-id="3347d-417">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-417">tax id no</span></span>
  
<span data-ttu-id="3347d-418">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-418">tax identification number</span></span>
  
<span data-ttu-id="3347d-419">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-419">tax registry number</span></span>
  
<span data-ttu-id="3347d-420">納税レジストリ番号</span><span class="sxs-lookup"><span data-stu-id="3347d-420">tax registry no.</span></span>
  
<span data-ttu-id="3347d-421">afm#</span><span class="sxs-lookup"><span data-stu-id="3347d-421">afm#</span></span>
  
<span data-ttu-id="3347d-422">は#</span><span class="sxs-lookup"><span data-stu-id="3347d-422">tin#</span></span>
  
<span data-ttu-id="3347d-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="3347d-423">taxidno#</span></span>
  
<span data-ttu-id="3347d-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="3347d-424">taxregistryno#</span></span>
  
<span data-ttu-id="3347d-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="3347d-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="3347d-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="3347d-426">aφμ</span></span>
  
<span data-ttu-id="3347d-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="3347d-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="3347d-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="3347d-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="3347d-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="3347d-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="3347d-430">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="3347d-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3347d-431">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-431">Format</span></span>

<span data-ttu-id="3347d-432">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-433">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-433">Pattern</span></span>

<span data-ttu-id="3347d-434">10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-434">Ten digits:</span></span>
  
-  <span data-ttu-id="3347d-435">"8" である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="3347d-436">日付01/01/1867 と個人の誕生日との間の日数に対応する5桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="3347d-437">同じ日に生まれた個人を区別する機会によって生成された番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="3347d-438">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="3347d-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-439">Checksum</span></span>

<span data-ttu-id="3347d-440">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-441">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-441">Definition</span></span>

<span data-ttu-id="3347d-442">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-443">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-444">From `Keywords_hungary_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-446">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-447">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="3347d-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-449">ハンガリーの税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="3347d-450">ハンガリー tin</span><span class="sxs-lookup"><span data-stu-id="3347d-450">hungarian tin</span></span>
  
<span data-ttu-id="3347d-451">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-451">tax id number</span></span>
  
<span data-ttu-id="3347d-452">vat 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-452">vat number</span></span>
  
<span data-ttu-id="3347d-453">税務当局番号</span><span class="sxs-lookup"><span data-stu-id="3347d-453">tax authority no</span></span>
  
<span data-ttu-id="3347d-454">課税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-454">tax id tax identity number</span></span>
  
<span data-ttu-id="3347d-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-455">taxidnumber#</span></span>
  
<span data-ttu-id="3347d-456">は#</span><span class="sxs-lookup"><span data-stu-id="3347d-456">tin#</span></span>
  
<span data-ttu-id="3347d-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="3347d-457">hungatiantin#</span></span>
  
<span data-ttu-id="3347d-458">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-458">tax identification no</span></span>
  
<span data-ttu-id="3347d-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="3347d-459">taxidno#</span></span>
  
<span data-ttu-id="3347d-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="3347d-460">adóazonosító szám</span></span>
  
<span data-ttu-id="3347d-461">adószám</span><span class="sxs-lookup"><span data-stu-id="3347d-461">adószám</span></span>
  
<span data-ttu-id="3347d-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="3347d-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="3347d-463">アイルランド</span><span class="sxs-lookup"><span data-stu-id="3347d-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3347d-464">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-464">Format</span></span>

<span data-ttu-id="3347d-465">7桁の数字の後にスペースまたは区切り文字を含まない文字</span><span class="sxs-lookup"><span data-stu-id="3347d-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-466">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-466">Pattern</span></span>

<span data-ttu-id="3347d-467">7桁の数字の後に、文字を続けます。</span><span class="sxs-lookup"><span data-stu-id="3347d-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="3347d-468">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="3347d-468">Seven digits</span></span> 
    
- <span data-ttu-id="3347d-469">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3347d-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-470">Checksum</span></span>

<span data-ttu-id="3347d-471">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-472">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-472">Definition</span></span>

<span data-ttu-id="3347d-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-474">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-475">From `Keywords_ireland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-476">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-477">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="3347d-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-480">パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="3347d-480">public service no</span></span>
  
<span data-ttu-id="3347d-481">個人用パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="3347d-481">personal public service no</span></span>
  
<span data-ttu-id="3347d-482">pps no</span><span class="sxs-lookup"><span data-stu-id="3347d-482">pps no</span></span>
  
<span data-ttu-id="3347d-483">個人サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="3347d-483">personal service no</span></span>
  
<span data-ttu-id="3347d-484">pps サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="3347d-484">pps service no</span></span>
  
<span data-ttu-id="3347d-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="3347d-485">ppsno#</span></span>
  
<span data-ttu-id="3347d-486">アイルランド語 (pps)</span><span class="sxs-lookup"><span data-stu-id="3347d-486">irish pps no</span></span>
  
<span data-ttu-id="3347d-487">publicserviceno ありません#</span><span class="sxs-lookup"><span data-stu-id="3347d-487">publicserviceno#</span></span>
  
<span data-ttu-id="3347d-488">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="3347d-488">personal public service number</span></span>
  
<span data-ttu-id="3347d-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="3347d-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="3347d-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="3347d-490">pps uimh</span></span>
  
<span data-ttu-id="3347d-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="3347d-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="3347d-492">イタリア</span><span class="sxs-lookup"><span data-stu-id="3347d-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="3347d-493">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-493">Format</span></span>

<span data-ttu-id="3347d-494">指定したパターンの16桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="3347d-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-495">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-495">Pattern</span></span>

<span data-ttu-id="3347d-496">16桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="3347d-497">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="3347d-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="3347d-498">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="3347d-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="3347d-499">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="3347d-500">誕生日に対応する1桁の数字。文字はアルファベット順に使用されますが、A から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は A と10月は R)。</span><span class="sxs-lookup"><span data-stu-id="3347d-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="3347d-501">誕生日に対応する2桁の数字。40が男性と区別するために女性の誕生日に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3347d-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="3347d-502">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字。国全体のコードが外国の国に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3347d-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="3347d-503">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="3347d-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-504">Checksum</span></span>

<span data-ttu-id="3347d-505">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-506">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-506">Definition</span></span>

<span data-ttu-id="3347d-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-508">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-509">From `Keywords_italy_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-511">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-512">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="3347d-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-514">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-514">tax number</span></span>
  
<span data-ttu-id="3347d-515">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-515">tax no.</span></span>
  
<span data-ttu-id="3347d-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-516">taxno#</span></span>
  
<span data-ttu-id="3347d-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-517">taxnumber#</span></span>
  
<span data-ttu-id="3347d-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-518">taxnumber</span></span>
  
<span data-ttu-id="3347d-519">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-519">tax id</span></span>
  
<span data-ttu-id="3347d-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-520">taxid#</span></span>
  
<span data-ttu-id="3347d-521">会計コード</span><span class="sxs-lookup"><span data-stu-id="3347d-521">fiscal code</span></span>
  
<span data-ttu-id="3347d-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="3347d-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="3347d-523">ラトビア</span><span class="sxs-lookup"><span data-stu-id="3347d-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3347d-524">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-524">Format</span></span>

<span data-ttu-id="3347d-525">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-526">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-526">Pattern</span></span>

<span data-ttu-id="3347d-527">指定したパターンの11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="3347d-528">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="3347d-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="3347d-529">"0" が19世紀に対応する1桁の数字、"1" は20世紀に、"2" は21世紀に対応します。</span><span class="sxs-lookup"><span data-stu-id="3347d-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="3347d-530">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-531">Checksum</span></span>

<span data-ttu-id="3347d-532">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-533">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-533">Definition</span></span>

<span data-ttu-id="3347d-534">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-535">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-536">From `Keywords_latvia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-537">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-538">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-539">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="3347d-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-541">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-541">tax number</span></span>
  
<span data-ttu-id="3347d-542">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-542">tax no.</span></span>
  
<span data-ttu-id="3347d-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-543">taxno#</span></span>
  
<span data-ttu-id="3347d-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-544">taxnumber#</span></span>
  
<span data-ttu-id="3347d-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-545">taxnumber</span></span>
  
<span data-ttu-id="3347d-546">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-546">tax id</span></span>
  
<span data-ttu-id="3347d-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-547">taxid#</span></span>
  
<span data-ttu-id="3347d-548">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-548">tax identification number</span></span>
  
<span data-ttu-id="3347d-549">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-549">tax identification no.</span></span>
  
<span data-ttu-id="3347d-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="3347d-550">nodokļa numurs</span></span>
  
<span data-ttu-id="3347d-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="3347d-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="3347d-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="3347d-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="3347d-553">リトアニア</span><span class="sxs-lookup"><span data-stu-id="3347d-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3347d-554">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-554">Format</span></span>

<span data-ttu-id="3347d-555">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="3347d-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-556">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-556">Pattern</span></span>

<span data-ttu-id="3347d-557">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-558">Checksum</span></span>

<span data-ttu-id="3347d-559">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-560">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-560">Definition</span></span>

<span data-ttu-id="3347d-561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-562">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-563">From `Keywords_lithuania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-564">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-565">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="3347d-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-568">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-568">tax number</span></span>
  
<span data-ttu-id="3347d-569">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-569">tax no.</span></span>
  
<span data-ttu-id="3347d-570">課税番号#</span><span class="sxs-lookup"><span data-stu-id="3347d-570">tax no#</span></span>
  
<span data-ttu-id="3347d-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-571">taxnumber#</span></span>
  
<span data-ttu-id="3347d-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-572">taxnumber</span></span>
  
<span data-ttu-id="3347d-573">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-573">tax id</span></span>
  
<span data-ttu-id="3347d-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-574">taxid#</span></span>
  
<span data-ttu-id="3347d-575">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-575">tax identification number</span></span>
  
<span data-ttu-id="3347d-576">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-576">tax identification no.</span></span>
  
<span data-ttu-id="3347d-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="3347d-577">mokesčių id</span></span>
  
<span data-ttu-id="3347d-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="3347d-578">mokesčių numeris</span></span>
  
<span data-ttu-id="3347d-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="3347d-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="3347d-580">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="3347d-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3347d-581">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-581">Format</span></span>

<span data-ttu-id="3347d-582">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="3347d-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-583">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-583">Pattern</span></span>

<span data-ttu-id="3347d-584">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-584">13 digits:</span></span>
  
-  <span data-ttu-id="3347d-585">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-585">11 digits</span></span> 
    
- <span data-ttu-id="3347d-586">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="3347d-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-587">Checksum</span></span>

<span data-ttu-id="3347d-588">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-589">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-589">Definition</span></span>

<span data-ttu-id="3347d-590">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-591">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-592">From `Keywords_luxemburg_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-593">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-594">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-595">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="3347d-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-597">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-597">tax number</span></span>
  
<span data-ttu-id="3347d-598">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-598">tax no.</span></span>
  
<span data-ttu-id="3347d-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-599">taxno#</span></span>
  
<span data-ttu-id="3347d-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-600">taxnumber#</span></span>
  
<span data-ttu-id="3347d-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-601">taxnumber</span></span>
  
<span data-ttu-id="3347d-602">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-602">tax id</span></span>
  
<span data-ttu-id="3347d-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-603">taxid#</span></span>
  
<span data-ttu-id="3347d-604">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-604">tax identification number</span></span>
  
<span data-ttu-id="3347d-605">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-605">tax identification no.</span></span>
  
<span data-ttu-id="3347d-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="3347d-606">steuernummer</span></span>
  
<span data-ttu-id="3347d-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="3347d-607">steuer id</span></span>
  
<span data-ttu-id="3347d-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="3347d-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="3347d-609">マルタ</span><span class="sxs-lookup"><span data-stu-id="3347d-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3347d-610">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-610">Format</span></span>

<span data-ttu-id="3347d-611">マルタ nationals の場合: 7 桁の数字と、指定したパターンの1文字</span><span class="sxs-lookup"><span data-stu-id="3347d-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="3347d-612">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-613">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-613">Pattern</span></span>

<span data-ttu-id="3347d-614">マルタ nationals: 7 桁と1文字</span><span class="sxs-lookup"><span data-stu-id="3347d-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="3347d-615">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="3347d-615">Seven digits</span></span> 
    
- <span data-ttu-id="3347d-616">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="3347d-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="3347d-617">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="3347d-618">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3347d-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-619">Checksum</span></span>

<span data-ttu-id="3347d-620">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-621">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-621">Definition</span></span>

<span data-ttu-id="3347d-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-623">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-624">From `Keywords_malta_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-626">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-627">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="3347d-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-629">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-629">tax number</span></span>
  
<span data-ttu-id="3347d-630">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-630">tax no.</span></span>
  
<span data-ttu-id="3347d-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-631">taxno#</span></span>
  
<span data-ttu-id="3347d-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-632">taxnumber#</span></span>
  
<span data-ttu-id="3347d-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-633">taxnumber</span></span>
  
<span data-ttu-id="3347d-634">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-634">tax id</span></span>
  
<span data-ttu-id="3347d-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-635">taxid#</span></span>
  
<span data-ttu-id="3347d-636">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-636">tax identification number</span></span>
  
<span data-ttu-id="3347d-637">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-637">tax identification no.</span></span>
  
<span data-ttu-id="3347d-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="3347d-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="3347d-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="3347d-639">id tat-taxxa</span></span>
  
<span data-ttu-id="3347d-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="3347d-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="3347d-641">オランダ</span><span class="sxs-lookup"><span data-stu-id="3347d-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3347d-642">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-642">Format</span></span>

<span data-ttu-id="3347d-643">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-644">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-644">Pattern</span></span>

<span data-ttu-id="3347d-645">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3347d-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-646">Checksum</span></span>

<span data-ttu-id="3347d-647">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-648">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-648">Definition</span></span>

<span data-ttu-id="3347d-649">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-650">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-651">From `Keywords_netherlands_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-652">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-653">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-654">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="3347d-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-656">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="3347d-657">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="3347d-657">netherlands tax identification</span></span>
  
<span data-ttu-id="3347d-658">netherland の税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="3347d-659">netherland の税 id</span><span class="sxs-lookup"><span data-stu-id="3347d-659">netherland's tax identification</span></span>
  
<span data-ttu-id="3347d-660">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-660">tax identification number</span></span>
  
<span data-ttu-id="3347d-661">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-661">dutch tax id</span></span>
  
<span data-ttu-id="3347d-662">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-662">dutch tax identification number</span></span>
  
<span data-ttu-id="3347d-663">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-663">tax id</span></span>
  
<span data-ttu-id="3347d-664">納税者番号#</span><span class="sxs-lookup"><span data-stu-id="3347d-664">tax id#</span></span>
  
<span data-ttu-id="3347d-665">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-665">tax number</span></span>
  
<span data-ttu-id="3347d-666">課税番号#</span><span class="sxs-lookup"><span data-stu-id="3347d-666">tax no#</span></span>
  
<span data-ttu-id="3347d-667">申告#</span><span class="sxs-lookup"><span data-stu-id="3347d-667">tax#</span></span>
  
<span data-ttu-id="3347d-668">は</span><span class="sxs-lookup"><span data-stu-id="3347d-668">tin</span></span>
  
<span data-ttu-id="3347d-669">は#</span><span class="sxs-lookup"><span data-stu-id="3347d-669">tin#</span></span>
  
<span data-ttu-id="3347d-670">オランダ tin</span><span class="sxs-lookup"><span data-stu-id="3347d-670">netherlands tin</span></span>
  
<span data-ttu-id="3347d-671">netherland の tin</span><span class="sxs-lookup"><span data-stu-id="3347d-671">netherland's tin</span></span>
  
<span data-ttu-id="3347d-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="3347d-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="3347d-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="3347d-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="3347d-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="3347d-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="3347d-675">nederlands belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="3347d-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="3347d-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="3347d-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="3347d-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="3347d-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="3347d-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="3347d-678">btw nummer</span></span>
  
<span data-ttu-id="3347d-679">nederlandse belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="3347d-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="3347d-680">ポーランド</span><span class="sxs-lookup"><span data-stu-id="3347d-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="3347d-681">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-681">Format</span></span>

<span data-ttu-id="3347d-682">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-683">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-683">Pattern</span></span>

<span data-ttu-id="3347d-684">11桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-685">Checksum</span></span>

<span data-ttu-id="3347d-686">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-687">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-687">Definition</span></span>

<span data-ttu-id="3347d-688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-689">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-690">From `Keywords_poland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-691">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-692">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-693">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="3347d-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-695">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-695">tax number</span></span>
  
<span data-ttu-id="3347d-696">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-696">tax no.</span></span>
  
<span data-ttu-id="3347d-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-697">taxno#</span></span>
  
<span data-ttu-id="3347d-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-698">taxnumber#</span></span>
  
<span data-ttu-id="3347d-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-699">taxnumber</span></span>
  
<span data-ttu-id="3347d-700">nip</span><span class="sxs-lookup"><span data-stu-id="3347d-700">nip</span></span>
  
<span data-ttu-id="3347d-701">nip#</span><span class="sxs-lookup"><span data-stu-id="3347d-701">nip#</span></span>
  
<span data-ttu-id="3347d-702">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-702">tax id</span></span>
  
<span data-ttu-id="3347d-703">納税者番号#</span><span class="sxs-lookup"><span data-stu-id="3347d-703">tax id#</span></span>
  
<span data-ttu-id="3347d-704">nip id</span><span class="sxs-lookup"><span data-stu-id="3347d-704">nip id</span></span>
  
<span data-ttu-id="3347d-705">nip id#</span><span class="sxs-lookup"><span data-stu-id="3347d-705">nip id#</span></span>
  
<span data-ttu-id="3347d-706">税識別番号</span><span class="sxs-lookup"><span data-stu-id="3347d-706">tax identification number</span></span>
  
<span data-ttu-id="3347d-707">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-707">tax identification no.</span></span>
  
<span data-ttu-id="3347d-708">vat 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-708">vat number</span></span>
  
<span data-ttu-id="3347d-709">vat 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-709">vat no.</span></span>
  
<span data-ttu-id="3347d-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="3347d-710">vatno#</span></span>
  
<span data-ttu-id="3347d-711">vat id</span><span class="sxs-lookup"><span data-stu-id="3347d-711">vat id</span></span>
  
<span data-ttu-id="3347d-712">vat id#</span><span class="sxs-lookup"><span data-stu-id="3347d-712">vat id#</span></span>
  
<span data-ttu-id="3347d-713">特定 identyfikacji podat・ wewej</span><span class="sxs-lookup"><span data-stu-id="3347d-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="3347d-714">polski 特定 identyfikacji podat・ wej</span><span class="sxs-lookup"><span data-stu-id="3347d-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="3347d-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="3347d-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="3347d-716">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="3347d-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3347d-717">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-717">Format</span></span>

<span data-ttu-id="3347d-718">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-719">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-719">Pattern</span></span>

<span data-ttu-id="3347d-720">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-721">Checksum</span></span>

<span data-ttu-id="3347d-722">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-723">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-723">Definition</span></span>

<span data-ttu-id="3347d-724">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-725">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-726">From `Keywords_portugal_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-728">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-729">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="3347d-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-731">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-731">tax number</span></span>
  
<span data-ttu-id="3347d-732">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-732">tax no.</span></span>
  
<span data-ttu-id="3347d-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-733">taxno#</span></span>
  
<span data-ttu-id="3347d-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="3347d-734">taxnumber#</span></span>
  
<span data-ttu-id="3347d-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="3347d-735">taxnumber</span></span>
  
<span data-ttu-id="3347d-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="3347d-736">nif</span></span>
  
<span data-ttu-id="3347d-737">\n\n#</span><span class="sxs-lookup"><span data-stu-id="3347d-737">nif#</span></span>
  
<span data-ttu-id="3347d-738">numero 会計</span><span class="sxs-lookup"><span data-stu-id="3347d-738">numero fiscal</span></span>
  
<span data-ttu-id="3347d-739">número de identificação 会計</span><span class="sxs-lookup"><span data-stu-id="3347d-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="3347d-740">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="3347d-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3347d-741">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-741">Format</span></span>

<span data-ttu-id="3347d-742">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="3347d-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-743">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-743">Pattern</span></span>

<span data-ttu-id="3347d-744">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-745">Checksum</span></span>

<span data-ttu-id="3347d-746">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-747">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-747">Definition</span></span>

<span data-ttu-id="3347d-748">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-749">正規表現`Regex_romania_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3347d-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-750">From `Keywords_romania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-751">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="3347d-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-753">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-753">tax id</span></span>
  
<span data-ttu-id="3347d-754">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-754">tax id number</span></span>
  
<span data-ttu-id="3347d-755">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="3347d-755">tax file no</span></span>
  
<span data-ttu-id="3347d-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="3347d-756">tax file number</span></span>
  
<span data-ttu-id="3347d-757">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-757">tax no</span></span>
  
<span data-ttu-id="3347d-758">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-758">tax number</span></span>
  
<span data-ttu-id="3347d-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-759">taxid#</span></span>
  
<span data-ttu-id="3347d-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-760">taxno#</span></span>
  
<span data-ttu-id="3347d-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="3347d-761">id-ul taxei</span></span>
  
<span data-ttu-id="3347d-762">numărul de 識別子は fiscală</span><span class="sxs-lookup"><span data-stu-id="3347d-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="3347d-763">スロバキア</span><span class="sxs-lookup"><span data-stu-id="3347d-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3347d-764">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-764">Format</span></span>

<span data-ttu-id="3347d-765">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-766">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-766">Pattern</span></span>

<span data-ttu-id="3347d-767">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-768">Checksum</span></span>

<span data-ttu-id="3347d-769">該当なし</span><span class="sxs-lookup"><span data-stu-id="3347d-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-770">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-770">Definition</span></span>

<span data-ttu-id="3347d-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-772">正規表現`Regex_slovakia_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="3347d-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-773">From `Keywords_slovakia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-774">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="3347d-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-776">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-776">tax id</span></span>
  
<span data-ttu-id="3347d-777">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-777">tax id number</span></span>
  
<span data-ttu-id="3347d-778">tin id</span><span class="sxs-lookup"><span data-stu-id="3347d-778">tin id</span></span>
  
<span data-ttu-id="3347d-779">tin no</span><span class="sxs-lookup"><span data-stu-id="3347d-779">tin no</span></span>
  
<span data-ttu-id="3347d-780">スロバキア tin id</span><span class="sxs-lookup"><span data-stu-id="3347d-780">slovakian tin id</span></span>
  
<span data-ttu-id="3347d-781">は</span><span class="sxs-lookup"><span data-stu-id="3347d-781">tin</span></span>
  
<span data-ttu-id="3347d-782">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="3347d-782">tax file no</span></span>
  
<span data-ttu-id="3347d-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="3347d-783">tax file number</span></span>
  
<span data-ttu-id="3347d-784">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-784">tax no</span></span>
  
<span data-ttu-id="3347d-785">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-785">tax number</span></span>
  
<span data-ttu-id="3347d-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-786">taxid#</span></span>
  
<span data-ttu-id="3347d-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-787">taxno#</span></span>
  
<span data-ttu-id="3347d-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="3347d-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="3347d-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="3347d-789">daňové číslo</span></span>
  
<span data-ttu-id="3347d-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="3347d-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="3347d-791">スロベニア</span><span class="sxs-lookup"><span data-stu-id="3347d-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3347d-792">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-792">Format</span></span>

<span data-ttu-id="3347d-793">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-794">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-794">Pattern</span></span>

<span data-ttu-id="3347d-795">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-796">Checksum</span></span>

<span data-ttu-id="3347d-797">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-798">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-798">Definition</span></span>

<span data-ttu-id="3347d-799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-800">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-801">From `Keywords_slovenia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-803">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-804">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="3347d-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-806">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-806">tax id</span></span>
  
<span data-ttu-id="3347d-807">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-807">tax id number</span></span>
  
<span data-ttu-id="3347d-808">tin id</span><span class="sxs-lookup"><span data-stu-id="3347d-808">tin id</span></span>
  
<span data-ttu-id="3347d-809">tin no</span><span class="sxs-lookup"><span data-stu-id="3347d-809">tin no</span></span>
  
<span data-ttu-id="3347d-810">スロベニア tin id</span><span class="sxs-lookup"><span data-stu-id="3347d-810">slovenian tin id</span></span>
  
<span data-ttu-id="3347d-811">は</span><span class="sxs-lookup"><span data-stu-id="3347d-811">tin</span></span>
  
<span data-ttu-id="3347d-812">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="3347d-812">tax file no</span></span>
  
<span data-ttu-id="3347d-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="3347d-813">tax file number</span></span>
  
<span data-ttu-id="3347d-814">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-814">tax no</span></span>
  
<span data-ttu-id="3347d-815">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-815">tax number</span></span>
  
<span data-ttu-id="3347d-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-816">taxid#</span></span>
  
<span data-ttu-id="3347d-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-817">taxno#</span></span>
  
<span data-ttu-id="3347d-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="3347d-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="3347d-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="3347d-819">davčna številka</span></span>
  
<span data-ttu-id="3347d-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="3347d-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="3347d-821">スペイン</span><span class="sxs-lookup"><span data-stu-id="3347d-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3347d-822">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-822">Format</span></span>

<span data-ttu-id="3347d-823">7桁または8桁の数字と、指定したパターンの1文字または2文字</span><span class="sxs-lookup"><span data-stu-id="3347d-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-824">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-824">Pattern</span></span>

<span data-ttu-id="3347d-825">スペインの国民 Id カードを持つスペインの自然の人物:</span><span class="sxs-lookup"><span data-stu-id="3347d-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="3347d-826">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-826">Eight digits</span></span> 
    
- <span data-ttu-id="3347d-827">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="3347d-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="3347d-828">スペインの国民 Id カードを持たない非常駐 Spaniards</span><span class="sxs-lookup"><span data-stu-id="3347d-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="3347d-829">1つの大文字の "L" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="3347d-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="3347d-830">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="3347d-830">Seven digits</span></span>
    
- <span data-ttu-id="3347d-831">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="3347d-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="3347d-832">Spaniards は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3347d-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="3347d-833">1つの大文字の "K" (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="3347d-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="3347d-834">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="3347d-834">Seven digits</span></span> 
    
- <span data-ttu-id="3347d-835">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="3347d-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="3347d-836">Foreigner の Id 番号を持つ Foreigners</span><span class="sxs-lookup"><span data-stu-id="3347d-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="3347d-837">"X"、"Y"、または "Z" (大文字と小文字を区別) の1つの大文字</span><span class="sxs-lookup"><span data-stu-id="3347d-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="3347d-838">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="3347d-838">Seven digits</span></span>
    
- <span data-ttu-id="3347d-839">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="3347d-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="3347d-840">Foreigner の識別番号のない Foreigners</span><span class="sxs-lookup"><span data-stu-id="3347d-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="3347d-841">1つの大文字の "M" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="3347d-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="3347d-842">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="3347d-842">Seven digits</span></span>
    
- <span data-ttu-id="3347d-843">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="3347d-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3347d-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-844">Checksum</span></span>

<span data-ttu-id="3347d-845">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-846">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-846">Definition</span></span>

<span data-ttu-id="3347d-847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-848">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-849">From `Keywords_spain_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-851">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-852">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="3347d-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-854">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-854">tax id</span></span>
  
<span data-ttu-id="3347d-855">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-855">tax id number</span></span>
  
<span data-ttu-id="3347d-856">cif id</span><span class="sxs-lookup"><span data-stu-id="3347d-856">cif id</span></span>
  
<span data-ttu-id="3347d-857">cif 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-857">cif no</span></span>
  
<span data-ttu-id="3347d-858">スペインの cif id</span><span class="sxs-lookup"><span data-stu-id="3347d-858">spanish cif id</span></span>
  
<span data-ttu-id="3347d-859">cif</span><span class="sxs-lookup"><span data-stu-id="3347d-859">cif</span></span>
  
<span data-ttu-id="3347d-860">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="3347d-860">tax file no</span></span>
  
<span data-ttu-id="3347d-861">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-861">spanish cif number</span></span>
  
<span data-ttu-id="3347d-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="3347d-862">tax file number</span></span>
  
<span data-ttu-id="3347d-863">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-863">spanish cif no</span></span>
  
<span data-ttu-id="3347d-864">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-864">tax no</span></span>
  
<span data-ttu-id="3347d-865">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-865">tax number</span></span>
  
<span data-ttu-id="3347d-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-866">taxid#</span></span>
  
<span data-ttu-id="3347d-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="3347d-867">taxno#</span></span>
  
<span data-ttu-id="3347d-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="3347d-868">cifid#</span></span>
  
<span data-ttu-id="3347d-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="3347d-869">spanishcifid#</span></span>
  
<span data-ttu-id="3347d-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="3347d-870">spanishcifno#</span></span>
  
<span data-ttu-id="3347d-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="3347d-871">número de contribuyente</span></span>
  
<span data-ttu-id="3347d-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="3347d-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="3347d-873">número de identificación 会計</span><span class="sxs-lookup"><span data-stu-id="3347d-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="3347d-874">cif número</span><span class="sxs-lookup"><span data-stu-id="3347d-874">cif número</span></span>
  
<span data-ttu-id="3347d-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="3347d-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="3347d-876">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="3347d-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="3347d-877">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-877">Format</span></span>

<span data-ttu-id="3347d-878">指定したパターンの10桁の数字と記号</span><span class="sxs-lookup"><span data-stu-id="3347d-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-879">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-879">Pattern</span></span>

<span data-ttu-id="3347d-880">10桁の数字と記号:</span><span class="sxs-lookup"><span data-stu-id="3347d-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="3347d-881">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="3347d-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="3347d-882">プラス記号、マイナス記号、または円記号</span><span class="sxs-lookup"><span data-stu-id="3347d-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="3347d-883">識別番号を一意にするための3桁の数字:</span><span class="sxs-lookup"><span data-stu-id="3347d-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="3347d-884">1990より前に発行された番号については、7桁目と8桁目の数字は、誕生日または外国出身の人物を識別します。</span><span class="sxs-lookup"><span data-stu-id="3347d-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="3347d-885">9桁の数字は、男性に対して、または女性に対して、性別を示します。</span><span class="sxs-lookup"><span data-stu-id="3347d-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="3347d-886">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="3347d-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3347d-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-887">Checksum</span></span>

<span data-ttu-id="3347d-888">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-889">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-889">Definition</span></span>

<span data-ttu-id="3347d-890">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-891">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-892">From `Keywords_sweden_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="3347d-893">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-894">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-895">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="3347d-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-897">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-897">tax id</span></span>
  
<span data-ttu-id="3347d-898">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-898">tax id no.</span></span>
  
<span data-ttu-id="3347d-899">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-899">tax id number</span></span>
  
<span data-ttu-id="3347d-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="3347d-900">tax identification</span></span>
  
<span data-ttu-id="3347d-901">税の識別#</span><span class="sxs-lookup"><span data-stu-id="3347d-901">tax identification#</span></span>
  
<span data-ttu-id="3347d-902">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-902">tax no.</span></span>
  
<span data-ttu-id="3347d-903">申告#</span><span class="sxs-lookup"><span data-stu-id="3347d-903">tax#</span></span>
  
<span data-ttu-id="3347d-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-904">taxid#</span></span>
  
<span data-ttu-id="3347d-905">税ファイル</span><span class="sxs-lookup"><span data-stu-id="3347d-905">tax file</span></span>
  
<span data-ttu-id="3347d-906">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="3347d-906">tax file no.</span></span>
  
<span data-ttu-id="3347d-907">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="3347d-907">personal id number</span></span>
  
<span data-ttu-id="3347d-908">skatt id の nummer</span><span class="sxs-lookup"><span data-stu-id="3347d-908">skatt id nummer</span></span>
  
<span data-ttu-id="3347d-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="3347d-909">skatt identifikation</span></span>
  
<span data-ttu-id="3347d-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="3347d-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="3347d-911">佐賀</span><span class="sxs-lookup"><span data-stu-id="3347d-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="3347d-912">Format</span><span class="sxs-lookup"><span data-stu-id="3347d-912">Format</span></span>

<span data-ttu-id="3347d-913">Unique 納税リファレンス (UTR): スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="3347d-914">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="3347d-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="3347d-915">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3347d-916">パターン</span><span class="sxs-lookup"><span data-stu-id="3347d-916">Pattern</span></span>

<span data-ttu-id="3347d-917">Unique 納税リファレンス (UTR):10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="3347d-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="3347d-918">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="3347d-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="3347d-919">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3347d-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="3347d-920">Checksum</span></span>

<span data-ttu-id="3347d-921">はい</span><span class="sxs-lookup"><span data-stu-id="3347d-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3347d-922">定義</span><span class="sxs-lookup"><span data-stu-id="3347d-922">Definition</span></span>

<span data-ttu-id="3347d-923">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="3347d-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3347d-924">関数`Func_uk_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="3347d-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3347d-925">From `Keywords_uk_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="3347d-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3347d-926">キーワード</span><span class="sxs-lookup"><span data-stu-id="3347d-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="3347d-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="3347d-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="3347d-928">tax id</span><span class="sxs-lookup"><span data-stu-id="3347d-928">tax id</span></span>
  
<span data-ttu-id="3347d-929">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-929">tax id no.</span></span>
  
<span data-ttu-id="3347d-930">納税者番号</span><span class="sxs-lookup"><span data-stu-id="3347d-930">tax id number</span></span>
  
<span data-ttu-id="3347d-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="3347d-931">tax identification</span></span>
  
<span data-ttu-id="3347d-932">税の識別#</span><span class="sxs-lookup"><span data-stu-id="3347d-932">tax identification#</span></span>
  
<span data-ttu-id="3347d-933">課税番号</span><span class="sxs-lookup"><span data-stu-id="3347d-933">tax no.</span></span>
  
<span data-ttu-id="3347d-934">申告#</span><span class="sxs-lookup"><span data-stu-id="3347d-934">tax#</span></span>
  
<span data-ttu-id="3347d-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="3347d-935">taxid#</span></span>
  
<span data-ttu-id="3347d-936">税ファイル</span><span class="sxs-lookup"><span data-stu-id="3347d-936">tax file</span></span>
  
<span data-ttu-id="3347d-937">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="3347d-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3347d-938">関連項目</span><span class="sxs-lookup"><span data-stu-id="3347d-938">See also</span></span>

[<span data-ttu-id="3347d-939">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="3347d-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

