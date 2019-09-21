---
title: EU 税務識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085864"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="db1dc-104">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-104">EU Tax Identification Number</span></span>

<span data-ttu-id="db1dc-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号 (TIN) 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="db1dc-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="db1dc-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="db1dc-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="db1dc-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-108">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-108">Format</span></span>

<span data-ttu-id="db1dc-109">任意指定のハイフンとスラッシュ (/) を含む9桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-110">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-110">Pattern</span></span>

<span data-ttu-id="db1dc-111">任意指定のハイフンとスラッシュ (/) を含む9桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="db1dc-112">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-112">Two digits</span></span> 
    
- <span data-ttu-id="db1dc-113">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="db1dc-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="db1dc-114">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-114">Three digits</span></span>
    
- <span data-ttu-id="db1dc-115">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="db1dc-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="db1dc-116">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-117">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-117">Checksum</span></span>

<span data-ttu-id="db1dc-118">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-119">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-119">Definition</span></span>

<span data-ttu-id="db1dc-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-121">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-122">From `Keywords_austria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-123">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-124">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-125">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="db1dc-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-127">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-127">tax number</span></span>
  
<span data-ttu-id="db1dc-128">番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-128">number</span></span>
  
<span data-ttu-id="db1dc-129">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-129">tax registration number</span></span>
  
<span data-ttu-id="db1dc-130">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-130">tax id</span></span>
  
<span data-ttu-id="db1dc-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="db1dc-131">st.nr.</span></span>
  
<span data-ttu-id="db1dc-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="db1dc-133">ベルギー</span><span class="sxs-lookup"><span data-stu-id="db1dc-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-134">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-134">Format</span></span>

<span data-ttu-id="db1dc-135">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-136">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-136">Pattern</span></span>

<span data-ttu-id="db1dc-137">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-137">11 digits:</span></span>
  
- <span data-ttu-id="db1dc-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-138">Two digits</span></span>
    
- <span data-ttu-id="db1dc-139">"0" または "1"</span><span class="sxs-lookup"><span data-stu-id="db1dc-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="db1dc-140">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-140">One digit</span></span>
    
- <span data-ttu-id="db1dc-141">"0" または "1" または "2" または "3"</span><span class="sxs-lookup"><span data-stu-id="db1dc-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="db1dc-142">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-143">Checksum</span></span>

<span data-ttu-id="db1dc-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-145">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-145">Definition</span></span>

<span data-ttu-id="db1dc-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-147">正規表現`Regex_belgium_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-148">From `Keywords_belgium_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db1dc-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="db1dc-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-151">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-151">tax number</span></span>
  
<span data-ttu-id="db1dc-152">国内登録番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-152">national registration number</span></span>
  
<span data-ttu-id="db1dc-153">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-153">tax registration number</span></span>
  
<span data-ttu-id="db1dc-154">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-154">tax id</span></span>
  
<span data-ttu-id="db1dc-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="db1dc-155">nif</span></span>
  
<span data-ttu-id="db1dc-156">\n\n#</span><span class="sxs-lookup"><span data-stu-id="db1dc-156">nif#</span></span>
  
<span data-ttu-id="db1dc-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="db1dc-157">numéro de registre national</span></span>
  
<span data-ttu-id="db1dc-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="db1dc-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="db1dc-159">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="db1dc-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-160">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-160">Format</span></span>

<span data-ttu-id="db1dc-161">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-162">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-162">Pattern</span></span>

<span data-ttu-id="db1dc-163">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-164">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-164">Checksum</span></span>

<span data-ttu-id="db1dc-165">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-166">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-166">Definition</span></span>

<span data-ttu-id="db1dc-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-168">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-169">From `Keywords_bulgaria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-170">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-171">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-172">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="db1dc-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-174">bucn</span><span class="sxs-lookup"><span data-stu-id="db1dc-174">bucn</span></span>
  
<span data-ttu-id="db1dc-175">一律の民事番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-175">uniform civil number</span></span>
  
<span data-ttu-id="db1dc-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="db1dc-176">bucn#</span></span>
  
<span data-ttu-id="db1dc-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="db1dc-178">uniform 民事 id</span><span class="sxs-lookup"><span data-stu-id="db1dc-178">uniform civil id</span></span>
  
<span data-ttu-id="db1dc-179">uniform 民事 no</span><span class="sxs-lookup"><span data-stu-id="db1dc-179">uniform civil no</span></span>
  
<span data-ttu-id="db1dc-180">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="db1dc-180">egn</span></span>
  
<span data-ttu-id="db1dc-181">ブルガリアの一様な民事訴訟番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="db1dc-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-182">uniformcivilno#</span></span>
  
<span data-ttu-id="db1dc-183">「//入力 n」#</span><span class="sxs-lookup"><span data-stu-id="db1dc-183">egn#</span></span>
  
<span data-ttu-id="db1dc-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="db1dc-184">униформ граждански номер</span></span>
  
<span data-ttu-id="db1dc-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="db1dc-185">униформ id</span></span>
  
<span data-ttu-id="db1dc-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="db1dc-186">униформ граждански id</span></span>
  
<span data-ttu-id="db1dc-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="db1dc-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="db1dc-188">クロアチア</span><span class="sxs-lookup"><span data-stu-id="db1dc-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-189">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-189">Format</span></span>

<span data-ttu-id="db1dc-190">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-191">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-191">Pattern</span></span>

<span data-ttu-id="db1dc-192">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-192">11 digits:</span></span>
  
- <span data-ttu-id="db1dc-193">ランダムに選択された10桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="db1dc-194">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="db1dc-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-195">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-195">Checksum</span></span>

<span data-ttu-id="db1dc-196">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-197">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-197">Definition</span></span>

<span data-ttu-id="db1dc-198">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-199">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-200">From `Keywords_croatia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-202">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-203">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="db1dc-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-205">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-205">tax number</span></span>
  
<span data-ttu-id="db1dc-206">申告</span><span class="sxs-lookup"><span data-stu-id="db1dc-206">tax</span></span>
  
<span data-ttu-id="db1dc-207">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-207">tax id</span></span>
  
<span data-ttu-id="db1dc-208">oid</span><span class="sxs-lookup"><span data-stu-id="db1dc-208">oid</span></span>
  
<span data-ttu-id="db1dc-209">ドーナツ#</span><span class="sxs-lookup"><span data-stu-id="db1dc-209">oid#</span></span>
  
<span data-ttu-id="db1dc-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="db1dc-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="db1dc-211">キプロス</span><span class="sxs-lookup"><span data-stu-id="db1dc-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-212">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-212">Format</span></span>

<span data-ttu-id="db1dc-213">指定したパターンの8桁の数字と1文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-214">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-214">Pattern</span></span>

<span data-ttu-id="db1dc-215">8桁の数字と1つの文字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="db1dc-216">"0"</span><span class="sxs-lookup"><span data-stu-id="db1dc-216">A "0"</span></span> 
    
- <span data-ttu-id="db1dc-217">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="db1dc-217">Seven digits</span></span>
    
- <span data-ttu-id="db1dc-218">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="db1dc-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-219">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-219">Checksum</span></span>

<span data-ttu-id="db1dc-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-221">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-221">Definition</span></span>

<span data-ttu-id="db1dc-222">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-223">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-224">From `Keywords_cyprus_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-226">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="db1dc-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-229">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-229">tax number</span></span>
  
<span data-ttu-id="db1dc-230">申告</span><span class="sxs-lookup"><span data-stu-id="db1dc-230">tax</span></span>
  
<span data-ttu-id="db1dc-231">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-231">tax id</span></span>
  
<span data-ttu-id="db1dc-232">税 id コード</span><span class="sxs-lookup"><span data-stu-id="db1dc-232">tax identification code</span></span>
  
<span data-ttu-id="db1dc-233">認め</span><span class="sxs-lookup"><span data-stu-id="db1dc-233">tic</span></span>
  
<span data-ttu-id="db1dc-234">認め#</span><span class="sxs-lookup"><span data-stu-id="db1dc-234">tic#</span></span>
  
<span data-ttu-id="db1dc-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="db1dc-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="db1dc-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="db1dc-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="db1dc-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="db1dc-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="db1dc-238">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="db1dc-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-239">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-239">Format</span></span>

<span data-ttu-id="db1dc-240">9桁または10桁の数字 (省略可能な円記号付き)</span><span class="sxs-lookup"><span data-stu-id="db1dc-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-241">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-241">Pattern</span></span>

<span data-ttu-id="db1dc-242">9桁または10桁の数字で、省略可能な backslashl を指定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="db1dc-243">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-243">Six digits</span></span> 
    
- <span data-ttu-id="db1dc-244">円記号 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="db1dc-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="db1dc-245">3桁または4桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-246">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-246">Checksum</span></span>

<span data-ttu-id="db1dc-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-248">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-248">Definition</span></span>

<span data-ttu-id="db1dc-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-250">正規表現`Regex_czech_republic_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-251">From `Keywords_czech_republic_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db1dc-252">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="db1dc-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-254">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-254">tax number</span></span>
  
<span data-ttu-id="db1dc-255">申告</span><span class="sxs-lookup"><span data-stu-id="db1dc-255">tax</span></span>
  
<span data-ttu-id="db1dc-256">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-256">tax id</span></span>
  
<span data-ttu-id="db1dc-257">個人番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-257">personal number</span></span>
  
<span data-ttu-id="db1dc-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="db1dc-258">daňové číslo</span></span>
  
<span data-ttu-id="db1dc-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="db1dc-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="db1dc-260">デンマーク</span><span class="sxs-lookup"><span data-stu-id="db1dc-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-261">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-261">Format</span></span>

<span data-ttu-id="db1dc-262">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="db1dc-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-263">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-263">Pattern</span></span>

<span data-ttu-id="db1dc-264">Hyphenl を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="db1dc-265">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="db1dc-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="db1dc-266">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="db1dc-266">A hyphen</span></span>
    
- <span data-ttu-id="db1dc-267">1桁目が誕生日の世紀に対応し、最後の桁は個人の性別に対応する4桁の数字 (男性の場合は奇数、女性の場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="db1dc-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-268">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-268">Checksum</span></span>

<span data-ttu-id="db1dc-269">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-270">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-270">Definition</span></span>

<span data-ttu-id="db1dc-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-272">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-273">From `Keywords_denmark_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-275">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-276">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="db1dc-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-278">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-278">tax number</span></span>
  
<span data-ttu-id="db1dc-279">申告</span><span class="sxs-lookup"><span data-stu-id="db1dc-279">tax</span></span>
  
<span data-ttu-id="db1dc-280">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-280">tax id</span></span>
  
<span data-ttu-id="db1dc-281">cpr 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-281">cpr number</span></span>
  
<span data-ttu-id="db1dc-282">cpr#</span><span class="sxs-lookup"><span data-stu-id="db1dc-282">cpr#</span></span>
  
<span data-ttu-id="db1dc-283">nummer の sk</span><span class="sxs-lookup"><span data-stu-id="db1dc-283">skat nummer</span></span>
  
<span data-ttu-id="db1dc-284">id の sk</span><span class="sxs-lookup"><span data-stu-id="db1dc-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="db1dc-285">エストニア</span><span class="sxs-lookup"><span data-stu-id="db1dc-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-286">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-286">Format</span></span>

<span data-ttu-id="db1dc-287">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-288">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-288">Pattern</span></span>

<span data-ttu-id="db1dc-289">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-289">11 digits:</span></span>
  
-  <span data-ttu-id="db1dc-290">性別と世紀に対応する1桁の数字。奇数は男性を表し、偶数の場合は1、2は19世紀に対しては女性を示します。20世紀に3、4世紀。21世紀の場合は5、6。</span><span class="sxs-lookup"><span data-stu-id="db1dc-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="db1dc-291">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="db1dc-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="db1dc-292">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="db1dc-293">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="db1dc-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-294">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-294">Checksum</span></span>

<span data-ttu-id="db1dc-295">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-296">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-296">Definition</span></span>

<span data-ttu-id="db1dc-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-298">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-299">From `Keywords_estonia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-301">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-302">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="db1dc-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-304">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-304">tax number</span></span>
  
<span data-ttu-id="db1dc-305">申告</span><span class="sxs-lookup"><span data-stu-id="db1dc-305">tax</span></span>
  
<span data-ttu-id="db1dc-306">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-306">tax id</span></span>
  
<span data-ttu-id="db1dc-307">個人コード</span><span class="sxs-lookup"><span data-stu-id="db1dc-307">personal code</span></span>
  
<span data-ttu-id="db1dc-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-308">maksunumber</span></span>
  
<span data-ttu-id="db1dc-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="db1dc-309">maksu id</span></span>
  
<span data-ttu-id="db1dc-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="db1dc-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="db1dc-311">フィンランド</span><span class="sxs-lookup"><span data-stu-id="db1dc-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-312">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-312">Format</span></span>

<span data-ttu-id="db1dc-313">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="db1dc-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-314">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-314">Pattern</span></span>

<span data-ttu-id="db1dc-315">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="db1dc-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="db1dc-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-316">Six digits</span></span>
    
- <span data-ttu-id="db1dc-317">プラス記号、マイナス記号、または文字 "A" (大文字小文字を区別しない) の1つ。プラス記号を1800-1899 の間に置きます。マイナス記号は、1900-1999 の間に出生することを意味2000します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="db1dc-318">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-318">Three digits</span></span>
    
- <span data-ttu-id="db1dc-319">1つの文字または1つの番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-320">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-320">Checksum</span></span>

<span data-ttu-id="db1dc-321">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-322">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-322">Definition</span></span>

<span data-ttu-id="db1dc-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-324">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-325">From `Keywords_finland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-327">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-328">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="db1dc-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-330">identification number</span><span class="sxs-lookup"><span data-stu-id="db1dc-330">identification number</span></span>
  
<span data-ttu-id="db1dc-331">個人 id</span><span class="sxs-lookup"><span data-stu-id="db1dc-331">personal id</span></span>
  
<span data-ttu-id="db1dc-332">id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-332">identity number</span></span>
  
<span data-ttu-id="db1dc-333">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-333">finnish national id number</span></span>
  
<span data-ttu-id="db1dc-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-334">personalidnumber#</span></span>
  
<span data-ttu-id="db1dc-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="db1dc-335">national identification number</span></span>
  
<span data-ttu-id="db1dc-336">id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-336">id number</span></span>
  
<span data-ttu-id="db1dc-337">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-337">national id no.</span></span>
  
<span data-ttu-id="db1dc-338">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-338">national id number</span></span>
  
<span data-ttu-id="db1dc-339">id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-339">id no</span></span>
  
<span data-ttu-id="db1dc-340">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="db1dc-340">tunnistenumero</span></span>
  
<span data-ttu-id="db1dc-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="db1dc-341">henkilötunnus</span></span>
  
<span data-ttu-id="db1dc-342">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="db1dc-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="db1dc-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="db1dc-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="db1dc-344">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="db1dc-344">identiteetti numero</span></span>
  
<span data-ttu-id="db1dc-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="db1dc-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="db1dc-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="db1dc-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="db1dc-347">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="db1dc-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="db1dc-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="db1dc-348">tunnusnumero</span></span>
  
<span data-ttu-id="db1dc-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="db1dc-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="db1dc-350">フランス</span><span class="sxs-lookup"><span data-stu-id="db1dc-350">France</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-351">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-351">Format</span></span>

<span data-ttu-id="db1dc-352">各ユーザーの13桁の数字、およびエンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-353">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-353">Pattern</span></span>

<span data-ttu-id="db1dc-354">個人の場合は13桁。</span><span class="sxs-lookup"><span data-stu-id="db1dc-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="db1dc-355">0、1、2、または3である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="db1dc-356">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-356">12 digits</span></span>
    
<span data-ttu-id="db1dc-357">エンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-358">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-358">Checksum</span></span>

<span data-ttu-id="db1dc-359">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-360">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-360">Definition</span></span>

<span data-ttu-id="db1dc-361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-362">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-363">From `Keywords_france_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-365">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-366">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="db1dc-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-368">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-368">tax identification number</span></span>
  
<span data-ttu-id="db1dc-369">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-369">tax number</span></span>
  
<span data-ttu-id="db1dc-370">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-370">tax id</span></span>
  
<span data-ttu-id="db1dc-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="db1dc-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="db1dc-372">ドイツ</span><span class="sxs-lookup"><span data-stu-id="db1dc-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-373">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-373">Format</span></span>

<span data-ttu-id="db1dc-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-375">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-375">Pattern</span></span>

<span data-ttu-id="db1dc-376">11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-376">11 digits :</span></span>
  
-  <span data-ttu-id="db1dc-377">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-377">Ten digits</span></span> 
    
- <span data-ttu-id="db1dc-378">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="db1dc-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-379">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-379">Checksum</span></span>

<span data-ttu-id="db1dc-380">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-381">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-381">Definition</span></span>

<span data-ttu-id="db1dc-382">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-383">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-384">From `Keywords_germany_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-386">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="db1dc-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-389">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-389">tax number</span></span>
  
<span data-ttu-id="db1dc-390">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-390">tax no.</span></span>
  
<span data-ttu-id="db1dc-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-391">taxno#</span></span>
  
<span data-ttu-id="db1dc-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-392">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-393">taxnumber</span></span>
  
<span data-ttu-id="db1dc-394">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-394">tax id</span></span>
  
<span data-ttu-id="db1dc-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-395">taxid#</span></span>
  
<span data-ttu-id="db1dc-396">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-396">tax identification number</span></span>
  
<span data-ttu-id="db1dc-397">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-397">tax identification no.</span></span>
  
<span data-ttu-id="db1dc-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-398">steuernummer</span></span>
  
<span data-ttu-id="db1dc-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="db1dc-399">steuer id</span></span>
  
<span data-ttu-id="db1dc-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="db1dc-401">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="db1dc-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-402">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-402">Format</span></span>

<span data-ttu-id="db1dc-403">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-404">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-404">Pattern</span></span>

<span data-ttu-id="db1dc-405">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-406">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-406">Checksum</span></span>

<span data-ttu-id="db1dc-407">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-408">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-408">Definition</span></span>

<span data-ttu-id="db1dc-409">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-410">正規表現`Regex_greece_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-411">From `Keywords_greece_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db1dc-412">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="db1dc-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-414">afm</span><span class="sxs-lookup"><span data-stu-id="db1dc-414">afm</span></span>
  
<span data-ttu-id="db1dc-415">は</span><span class="sxs-lookup"><span data-stu-id="db1dc-415">tin</span></span>
  
<span data-ttu-id="db1dc-416">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-416">tax id no.</span></span>
  
<span data-ttu-id="db1dc-417">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-417">tax id no</span></span>
  
<span data-ttu-id="db1dc-418">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-418">tax identification number</span></span>
  
<span data-ttu-id="db1dc-419">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-419">tax registry number</span></span>
  
<span data-ttu-id="db1dc-420">納税レジストリ番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-420">tax registry no.</span></span>
  
<span data-ttu-id="db1dc-421">afm#</span><span class="sxs-lookup"><span data-stu-id="db1dc-421">afm#</span></span>
  
<span data-ttu-id="db1dc-422">は#</span><span class="sxs-lookup"><span data-stu-id="db1dc-422">tin#</span></span>
  
<span data-ttu-id="db1dc-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-423">taxidno#</span></span>
  
<span data-ttu-id="db1dc-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-424">taxregistryno#</span></span>
  
<span data-ttu-id="db1dc-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="db1dc-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="db1dc-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="db1dc-426">aφμ</span></span>
  
<span data-ttu-id="db1dc-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="db1dc-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="db1dc-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="db1dc-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="db1dc-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="db1dc-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="db1dc-430">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="db1dc-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-431">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-431">Format</span></span>

<span data-ttu-id="db1dc-432">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-433">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-433">Pattern</span></span>

<span data-ttu-id="db1dc-434">10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-434">Ten digits:</span></span>
  
-  <span data-ttu-id="db1dc-435">"8" である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="db1dc-436">日付01/01/1867 と個人の誕生日との間の日数に対応する5桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="db1dc-437">同じ日に生まれた個人を区別する機会によって生成された番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="db1dc-438">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="db1dc-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-439">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-439">Checksum</span></span>

<span data-ttu-id="db1dc-440">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-441">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-441">Definition</span></span>

<span data-ttu-id="db1dc-442">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-443">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-444">From `Keywords_hungary_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-446">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-447">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="db1dc-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-449">ハンガリーの税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="db1dc-450">ハンガリー tin</span><span class="sxs-lookup"><span data-stu-id="db1dc-450">hungarian tin</span></span>
  
<span data-ttu-id="db1dc-451">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-451">tax id number</span></span>
  
<span data-ttu-id="db1dc-452">vat 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-452">vat number</span></span>
  
<span data-ttu-id="db1dc-453">税務当局番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-453">tax authority no</span></span>
  
<span data-ttu-id="db1dc-454">課税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-454">tax id tax identity number</span></span>
  
<span data-ttu-id="db1dc-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-455">taxidnumber#</span></span>
  
<span data-ttu-id="db1dc-456">は#</span><span class="sxs-lookup"><span data-stu-id="db1dc-456">tin#</span></span>
  
<span data-ttu-id="db1dc-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="db1dc-457">hungatiantin#</span></span>
  
<span data-ttu-id="db1dc-458">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-458">tax identification no</span></span>
  
<span data-ttu-id="db1dc-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-459">taxidno#</span></span>
  
<span data-ttu-id="db1dc-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="db1dc-460">adóazonosító szám</span></span>
  
<span data-ttu-id="db1dc-461">adószám</span><span class="sxs-lookup"><span data-stu-id="db1dc-461">adószám</span></span>
  
<span data-ttu-id="db1dc-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="db1dc-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="db1dc-463">アイルランド</span><span class="sxs-lookup"><span data-stu-id="db1dc-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-464">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-464">Format</span></span>

<span data-ttu-id="db1dc-465">7桁の数字の後にスペースまたは区切り文字を含まない文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-466">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-466">Pattern</span></span>

<span data-ttu-id="db1dc-467">7桁の数字の後に、文字を続けます。</span><span class="sxs-lookup"><span data-stu-id="db1dc-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="db1dc-468">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="db1dc-468">Seven digits</span></span> 
    
- <span data-ttu-id="db1dc-469">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="db1dc-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-470">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-470">Checksum</span></span>

<span data-ttu-id="db1dc-471">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-472">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-472">Definition</span></span>

<span data-ttu-id="db1dc-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-474">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-475">From `Keywords_ireland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-476">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-477">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="db1dc-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-480">パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="db1dc-480">public service no</span></span>
  
<span data-ttu-id="db1dc-481">個人用パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="db1dc-481">personal public service no</span></span>
  
<span data-ttu-id="db1dc-482">pps no</span><span class="sxs-lookup"><span data-stu-id="db1dc-482">pps no</span></span>
  
<span data-ttu-id="db1dc-483">個人サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="db1dc-483">personal service no</span></span>
  
<span data-ttu-id="db1dc-484">pps サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="db1dc-484">pps service no</span></span>
  
<span data-ttu-id="db1dc-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-485">ppsno#</span></span>
  
<span data-ttu-id="db1dc-486">アイルランド語 (pps)</span><span class="sxs-lookup"><span data-stu-id="db1dc-486">irish pps no</span></span>
  
<span data-ttu-id="db1dc-487">publicserviceno ありません#</span><span class="sxs-lookup"><span data-stu-id="db1dc-487">publicserviceno#</span></span>
  
<span data-ttu-id="db1dc-488">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-488">personal public service number</span></span>
  
<span data-ttu-id="db1dc-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="db1dc-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="db1dc-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="db1dc-490">pps uimh</span></span>
  
<span data-ttu-id="db1dc-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="db1dc-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="db1dc-492">イタリア</span><span class="sxs-lookup"><span data-stu-id="db1dc-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-493">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-493">Format</span></span>

<span data-ttu-id="db1dc-494">指定したパターンの16桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-495">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-495">Pattern</span></span>

<span data-ttu-id="db1dc-496">16桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="db1dc-497">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="db1dc-498">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="db1dc-499">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="db1dc-500">誕生日に対応する1桁の数字。文字はアルファベット順に使用されますが、A から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は A と10月は R)。</span><span class="sxs-lookup"><span data-stu-id="db1dc-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="db1dc-501">誕生日に対応する2桁の数字。40が男性と区別するために女性の誕生日に追加されます。</span><span class="sxs-lookup"><span data-stu-id="db1dc-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="db1dc-502">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字。国全体のコードが外国の国に使用されます。</span><span class="sxs-lookup"><span data-stu-id="db1dc-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="db1dc-503">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="db1dc-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-504">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-504">Checksum</span></span>

<span data-ttu-id="db1dc-505">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-506">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-506">Definition</span></span>

<span data-ttu-id="db1dc-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-508">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-509">From `Keywords_italy_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-511">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-512">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="db1dc-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-514">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-514">tax number</span></span>
  
<span data-ttu-id="db1dc-515">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-515">tax no.</span></span>
  
<span data-ttu-id="db1dc-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-516">taxno#</span></span>
  
<span data-ttu-id="db1dc-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-517">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-518">taxnumber</span></span>
  
<span data-ttu-id="db1dc-519">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-519">tax id</span></span>
  
<span data-ttu-id="db1dc-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-520">taxid#</span></span>
  
<span data-ttu-id="db1dc-521">会計コード</span><span class="sxs-lookup"><span data-stu-id="db1dc-521">fiscal code</span></span>
  
<span data-ttu-id="db1dc-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="db1dc-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="db1dc-523">ラトビア</span><span class="sxs-lookup"><span data-stu-id="db1dc-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-524">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-524">Format</span></span>

<span data-ttu-id="db1dc-525">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-526">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-526">Pattern</span></span>

<span data-ttu-id="db1dc-527">指定したパターンの11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="db1dc-528">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="db1dc-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="db1dc-529">"0" が19世紀に対応する1桁の数字、"1" は20世紀に、"2" は21世紀に対応します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="db1dc-530">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-531">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-531">Checksum</span></span>

<span data-ttu-id="db1dc-532">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-533">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-533">Definition</span></span>

<span data-ttu-id="db1dc-534">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-535">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-536">From `Keywords_latvia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-537">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-538">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-539">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="db1dc-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-541">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-541">tax number</span></span>
  
<span data-ttu-id="db1dc-542">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-542">tax no.</span></span>
  
<span data-ttu-id="db1dc-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-543">taxno#</span></span>
  
<span data-ttu-id="db1dc-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-544">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-545">taxnumber</span></span>
  
<span data-ttu-id="db1dc-546">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-546">tax id</span></span>
  
<span data-ttu-id="db1dc-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-547">taxid#</span></span>
  
<span data-ttu-id="db1dc-548">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-548">tax identification number</span></span>
  
<span data-ttu-id="db1dc-549">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-549">tax identification no.</span></span>
  
<span data-ttu-id="db1dc-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="db1dc-550">nodokļa numurs</span></span>
  
<span data-ttu-id="db1dc-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="db1dc-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="db1dc-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="db1dc-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="db1dc-553">リトアニア</span><span class="sxs-lookup"><span data-stu-id="db1dc-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-554">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-554">Format</span></span>

<span data-ttu-id="db1dc-555">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="db1dc-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-556">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-556">Pattern</span></span>

<span data-ttu-id="db1dc-557">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-558">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-558">Checksum</span></span>

<span data-ttu-id="db1dc-559">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-560">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-560">Definition</span></span>

<span data-ttu-id="db1dc-561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-562">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-563">From `Keywords_lithuania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-564">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-565">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="db1dc-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-568">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-568">tax number</span></span>
  
<span data-ttu-id="db1dc-569">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-569">tax no.</span></span>
  
<span data-ttu-id="db1dc-570">課税番号#</span><span class="sxs-lookup"><span data-stu-id="db1dc-570">tax no#</span></span>
  
<span data-ttu-id="db1dc-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-571">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-572">taxnumber</span></span>
  
<span data-ttu-id="db1dc-573">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-573">tax id</span></span>
  
<span data-ttu-id="db1dc-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-574">taxid#</span></span>
  
<span data-ttu-id="db1dc-575">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-575">tax identification number</span></span>
  
<span data-ttu-id="db1dc-576">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-576">tax identification no.</span></span>
  
<span data-ttu-id="db1dc-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="db1dc-577">mokesčių id</span></span>
  
<span data-ttu-id="db1dc-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="db1dc-578">mokesčių numeris</span></span>
  
<span data-ttu-id="db1dc-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="db1dc-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="db1dc-580">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="db1dc-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-581">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-581">Format</span></span>

<span data-ttu-id="db1dc-582">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-583">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-583">Pattern</span></span>

<span data-ttu-id="db1dc-584">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-584">13 digits:</span></span>
  
-  <span data-ttu-id="db1dc-585">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-585">11 digits</span></span> 
    
- <span data-ttu-id="db1dc-586">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="db1dc-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-587">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-587">Checksum</span></span>

<span data-ttu-id="db1dc-588">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-589">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-589">Definition</span></span>

<span data-ttu-id="db1dc-590">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-591">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-592">From `Keywords_luxemburg_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-593">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-594">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-595">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="db1dc-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-597">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-597">tax number</span></span>
  
<span data-ttu-id="db1dc-598">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-598">tax no.</span></span>
  
<span data-ttu-id="db1dc-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-599">taxno#</span></span>
  
<span data-ttu-id="db1dc-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-600">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-601">taxnumber</span></span>
  
<span data-ttu-id="db1dc-602">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-602">tax id</span></span>
  
<span data-ttu-id="db1dc-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-603">taxid#</span></span>
  
<span data-ttu-id="db1dc-604">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-604">tax identification number</span></span>
  
<span data-ttu-id="db1dc-605">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-605">tax identification no.</span></span>
  
<span data-ttu-id="db1dc-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-606">steuernummer</span></span>
  
<span data-ttu-id="db1dc-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="db1dc-607">steuer id</span></span>
  
<span data-ttu-id="db1dc-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="db1dc-609">マルタ</span><span class="sxs-lookup"><span data-stu-id="db1dc-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-610">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-610">Format</span></span>

<span data-ttu-id="db1dc-611">マルタ nationals の場合: 7 桁の数字と、指定したパターンの1文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="db1dc-612">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-613">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-613">Pattern</span></span>

<span data-ttu-id="db1dc-614">マルタ nationals: 7 桁と1文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="db1dc-615">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="db1dc-615">Seven digits</span></span> 
    
- <span data-ttu-id="db1dc-616">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="db1dc-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="db1dc-617">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="db1dc-618">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="db1dc-619">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-619">Checksum</span></span>

<span data-ttu-id="db1dc-620">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-621">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-621">Definition</span></span>

<span data-ttu-id="db1dc-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-623">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-624">From `Keywords_malta_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-626">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-627">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="db1dc-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-629">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-629">tax number</span></span>
  
<span data-ttu-id="db1dc-630">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-630">tax no.</span></span>
  
<span data-ttu-id="db1dc-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-631">taxno#</span></span>
  
<span data-ttu-id="db1dc-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-632">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-633">taxnumber</span></span>
  
<span data-ttu-id="db1dc-634">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-634">tax id</span></span>
  
<span data-ttu-id="db1dc-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-635">taxid#</span></span>
  
<span data-ttu-id="db1dc-636">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-636">tax identification number</span></span>
  
<span data-ttu-id="db1dc-637">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-637">tax identification no.</span></span>
  
<span data-ttu-id="db1dc-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="db1dc-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="db1dc-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="db1dc-639">id tat-taxxa</span></span>
  
<span data-ttu-id="db1dc-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="db1dc-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="db1dc-641">オランダ</span><span class="sxs-lookup"><span data-stu-id="db1dc-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-642">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-642">Format</span></span>

<span data-ttu-id="db1dc-643">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-644">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-644">Pattern</span></span>

<span data-ttu-id="db1dc-645">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="db1dc-646">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-646">Checksum</span></span>

<span data-ttu-id="db1dc-647">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-648">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-648">Definition</span></span>

<span data-ttu-id="db1dc-649">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-650">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-651">From `Keywords_netherlands_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-652">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-653">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-654">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="db1dc-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-656">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="db1dc-657">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="db1dc-657">netherlands tax identification</span></span>
  
<span data-ttu-id="db1dc-658">netherland の税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="db1dc-659">netherland の税 id</span><span class="sxs-lookup"><span data-stu-id="db1dc-659">netherland's tax identification</span></span>
  
<span data-ttu-id="db1dc-660">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-660">tax identification number</span></span>
  
<span data-ttu-id="db1dc-661">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-661">dutch tax id</span></span>
  
<span data-ttu-id="db1dc-662">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-662">dutch tax identification number</span></span>
  
<span data-ttu-id="db1dc-663">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-663">tax id</span></span>
  
<span data-ttu-id="db1dc-664">納税者番号#</span><span class="sxs-lookup"><span data-stu-id="db1dc-664">tax id#</span></span>
  
<span data-ttu-id="db1dc-665">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-665">tax number</span></span>
  
<span data-ttu-id="db1dc-666">課税番号#</span><span class="sxs-lookup"><span data-stu-id="db1dc-666">tax no#</span></span>
  
<span data-ttu-id="db1dc-667">申告#</span><span class="sxs-lookup"><span data-stu-id="db1dc-667">tax#</span></span>
  
<span data-ttu-id="db1dc-668">は</span><span class="sxs-lookup"><span data-stu-id="db1dc-668">tin</span></span>
  
<span data-ttu-id="db1dc-669">は#</span><span class="sxs-lookup"><span data-stu-id="db1dc-669">tin#</span></span>
  
<span data-ttu-id="db1dc-670">オランダ tin</span><span class="sxs-lookup"><span data-stu-id="db1dc-670">netherlands tin</span></span>
  
<span data-ttu-id="db1dc-671">netherland の tin</span><span class="sxs-lookup"><span data-stu-id="db1dc-671">netherland's tin</span></span>
  
<span data-ttu-id="db1dc-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="db1dc-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="db1dc-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="db1dc-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="db1dc-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="db1dc-675">nederlands belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="db1dc-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="db1dc-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="db1dc-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="db1dc-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-678">btw nummer</span></span>
  
<span data-ttu-id="db1dc-679">nederlandse belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="db1dc-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="db1dc-680">ポーランド</span><span class="sxs-lookup"><span data-stu-id="db1dc-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-681">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-681">Format</span></span>

<span data-ttu-id="db1dc-682">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-683">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-683">Pattern</span></span>

<span data-ttu-id="db1dc-684">11桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-685">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-685">Checksum</span></span>

<span data-ttu-id="db1dc-686">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-687">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-687">Definition</span></span>

<span data-ttu-id="db1dc-688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-689">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-690">From `Keywords_poland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-691">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-692">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-693">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="db1dc-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-695">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-695">tax number</span></span>
  
<span data-ttu-id="db1dc-696">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-696">tax no.</span></span>
  
<span data-ttu-id="db1dc-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-697">taxno#</span></span>
  
<span data-ttu-id="db1dc-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-698">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-699">taxnumber</span></span>
  
<span data-ttu-id="db1dc-700">nip</span><span class="sxs-lookup"><span data-stu-id="db1dc-700">nip</span></span>
  
<span data-ttu-id="db1dc-701">nip#</span><span class="sxs-lookup"><span data-stu-id="db1dc-701">nip#</span></span>
  
<span data-ttu-id="db1dc-702">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-702">tax id</span></span>
  
<span data-ttu-id="db1dc-703">納税者番号#</span><span class="sxs-lookup"><span data-stu-id="db1dc-703">tax id#</span></span>
  
<span data-ttu-id="db1dc-704">nip id</span><span class="sxs-lookup"><span data-stu-id="db1dc-704">nip id</span></span>
  
<span data-ttu-id="db1dc-705">nip id#</span><span class="sxs-lookup"><span data-stu-id="db1dc-705">nip id#</span></span>
  
<span data-ttu-id="db1dc-706">税識別番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-706">tax identification number</span></span>
  
<span data-ttu-id="db1dc-707">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-707">tax identification no.</span></span>
  
<span data-ttu-id="db1dc-708">vat 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-708">vat number</span></span>
  
<span data-ttu-id="db1dc-709">vat 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-709">vat no.</span></span>
  
<span data-ttu-id="db1dc-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-710">vatno#</span></span>
  
<span data-ttu-id="db1dc-711">vat id</span><span class="sxs-lookup"><span data-stu-id="db1dc-711">vat id</span></span>
  
<span data-ttu-id="db1dc-712">vat id#</span><span class="sxs-lookup"><span data-stu-id="db1dc-712">vat id#</span></span>
  
<span data-ttu-id="db1dc-713">特定 identyfikacji podat・ wewej</span><span class="sxs-lookup"><span data-stu-id="db1dc-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="db1dc-714">polski 特定 identyfikacji podat・ wej</span><span class="sxs-lookup"><span data-stu-id="db1dc-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="db1dc-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="db1dc-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="db1dc-716">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="db1dc-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-717">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-717">Format</span></span>

<span data-ttu-id="db1dc-718">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-719">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-719">Pattern</span></span>

<span data-ttu-id="db1dc-720">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-721">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-721">Checksum</span></span>

<span data-ttu-id="db1dc-722">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-723">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-723">Definition</span></span>

<span data-ttu-id="db1dc-724">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-725">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-726">From `Keywords_portugal_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-728">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-729">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="db1dc-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-731">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-731">tax number</span></span>
  
<span data-ttu-id="db1dc-732">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-732">tax no.</span></span>
  
<span data-ttu-id="db1dc-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-733">taxno#</span></span>
  
<span data-ttu-id="db1dc-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="db1dc-734">taxnumber#</span></span>
  
<span data-ttu-id="db1dc-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="db1dc-735">taxnumber</span></span>
  
<span data-ttu-id="db1dc-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="db1dc-736">nif</span></span>
  
<span data-ttu-id="db1dc-737">\n\n#</span><span class="sxs-lookup"><span data-stu-id="db1dc-737">nif#</span></span>
  
<span data-ttu-id="db1dc-738">numero 会計</span><span class="sxs-lookup"><span data-stu-id="db1dc-738">numero fiscal</span></span>
  
<span data-ttu-id="db1dc-739">número de identificação 会計</span><span class="sxs-lookup"><span data-stu-id="db1dc-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="db1dc-740">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="db1dc-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-741">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-741">Format</span></span>

<span data-ttu-id="db1dc-742">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-743">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-743">Pattern</span></span>

<span data-ttu-id="db1dc-744">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-745">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-745">Checksum</span></span>

<span data-ttu-id="db1dc-746">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-747">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-747">Definition</span></span>

<span data-ttu-id="db1dc-748">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-749">正規表現`Regex_romania_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-750">From `Keywords_romania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db1dc-751">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="db1dc-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-753">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-753">tax id</span></span>
  
<span data-ttu-id="db1dc-754">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-754">tax id number</span></span>
  
<span data-ttu-id="db1dc-755">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-755">tax file no</span></span>
  
<span data-ttu-id="db1dc-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="db1dc-756">tax file number</span></span>
  
<span data-ttu-id="db1dc-757">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-757">tax no</span></span>
  
<span data-ttu-id="db1dc-758">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-758">tax number</span></span>
  
<span data-ttu-id="db1dc-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-759">taxid#</span></span>
  
<span data-ttu-id="db1dc-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-760">taxno#</span></span>
  
<span data-ttu-id="db1dc-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="db1dc-761">id-ul taxei</span></span>
  
<span data-ttu-id="db1dc-762">numărul de 識別子は fiscală</span><span class="sxs-lookup"><span data-stu-id="db1dc-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="db1dc-763">スロバキア</span><span class="sxs-lookup"><span data-stu-id="db1dc-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-764">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-764">Format</span></span>

<span data-ttu-id="db1dc-765">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-766">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-766">Pattern</span></span>

<span data-ttu-id="db1dc-767">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-768">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-768">Checksum</span></span>

<span data-ttu-id="db1dc-769">該当なし</span><span class="sxs-lookup"><span data-stu-id="db1dc-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-770">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-770">Definition</span></span>

<span data-ttu-id="db1dc-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-772">正規表現`Regex_slovakia_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-773">From `Keywords_slovakia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db1dc-774">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="db1dc-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-776">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-776">tax id</span></span>
  
<span data-ttu-id="db1dc-777">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-777">tax id number</span></span>
  
<span data-ttu-id="db1dc-778">tin id</span><span class="sxs-lookup"><span data-stu-id="db1dc-778">tin id</span></span>
  
<span data-ttu-id="db1dc-779">tin no</span><span class="sxs-lookup"><span data-stu-id="db1dc-779">tin no</span></span>
  
<span data-ttu-id="db1dc-780">スロバキア tin id</span><span class="sxs-lookup"><span data-stu-id="db1dc-780">slovakian tin id</span></span>
  
<span data-ttu-id="db1dc-781">は</span><span class="sxs-lookup"><span data-stu-id="db1dc-781">tin</span></span>
  
<span data-ttu-id="db1dc-782">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-782">tax file no</span></span>
  
<span data-ttu-id="db1dc-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="db1dc-783">tax file number</span></span>
  
<span data-ttu-id="db1dc-784">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-784">tax no</span></span>
  
<span data-ttu-id="db1dc-785">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-785">tax number</span></span>
  
<span data-ttu-id="db1dc-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-786">taxid#</span></span>
  
<span data-ttu-id="db1dc-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-787">taxno#</span></span>
  
<span data-ttu-id="db1dc-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="db1dc-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="db1dc-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="db1dc-789">daňové číslo</span></span>
  
<span data-ttu-id="db1dc-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="db1dc-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="db1dc-791">スロベニア</span><span class="sxs-lookup"><span data-stu-id="db1dc-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-792">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-792">Format</span></span>

<span data-ttu-id="db1dc-793">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-794">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-794">Pattern</span></span>

<span data-ttu-id="db1dc-795">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-796">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-796">Checksum</span></span>

<span data-ttu-id="db1dc-797">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-798">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-798">Definition</span></span>

<span data-ttu-id="db1dc-799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-800">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-801">From `Keywords_slovenia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-803">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-804">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="db1dc-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-806">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-806">tax id</span></span>
  
<span data-ttu-id="db1dc-807">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-807">tax id number</span></span>
  
<span data-ttu-id="db1dc-808">tin id</span><span class="sxs-lookup"><span data-stu-id="db1dc-808">tin id</span></span>
  
<span data-ttu-id="db1dc-809">tin no</span><span class="sxs-lookup"><span data-stu-id="db1dc-809">tin no</span></span>
  
<span data-ttu-id="db1dc-810">スロベニア tin id</span><span class="sxs-lookup"><span data-stu-id="db1dc-810">slovenian tin id</span></span>
  
<span data-ttu-id="db1dc-811">は</span><span class="sxs-lookup"><span data-stu-id="db1dc-811">tin</span></span>
  
<span data-ttu-id="db1dc-812">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-812">tax file no</span></span>
  
<span data-ttu-id="db1dc-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="db1dc-813">tax file number</span></span>
  
<span data-ttu-id="db1dc-814">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-814">tax no</span></span>
  
<span data-ttu-id="db1dc-815">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-815">tax number</span></span>
  
<span data-ttu-id="db1dc-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-816">taxid#</span></span>
  
<span data-ttu-id="db1dc-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-817">taxno#</span></span>
  
<span data-ttu-id="db1dc-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="db1dc-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="db1dc-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="db1dc-819">davčna številka</span></span>
  
<span data-ttu-id="db1dc-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="db1dc-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="db1dc-821">スペイン</span><span class="sxs-lookup"><span data-stu-id="db1dc-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-822">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-822">Format</span></span>

<span data-ttu-id="db1dc-823">7桁または8桁の数字と、指定したパターンの1文字または2文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-824">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-824">Pattern</span></span>

<span data-ttu-id="db1dc-825">スペインの国民 Id カードを持つスペインの自然の人物:</span><span class="sxs-lookup"><span data-stu-id="db1dc-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="db1dc-826">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-826">Eight digits</span></span> 
    
- <span data-ttu-id="db1dc-827">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="db1dc-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="db1dc-828">スペインの国民 Id カードを持たない非常駐 Spaniards</span><span class="sxs-lookup"><span data-stu-id="db1dc-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="db1dc-829">1つの大文字の "L" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="db1dc-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="db1dc-830">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="db1dc-830">Seven digits</span></span>
    
- <span data-ttu-id="db1dc-831">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="db1dc-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="db1dc-832">Spaniards は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="db1dc-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="db1dc-833">1つの大文字の "K" (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="db1dc-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="db1dc-834">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="db1dc-834">Seven digits</span></span> 
    
- <span data-ttu-id="db1dc-835">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="db1dc-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="db1dc-836">Foreigner の Id 番号を持つ Foreigners</span><span class="sxs-lookup"><span data-stu-id="db1dc-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="db1dc-837">"X"、"Y"、または "Z" (大文字と小文字を区別) の1つの大文字</span><span class="sxs-lookup"><span data-stu-id="db1dc-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="db1dc-838">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="db1dc-838">Seven digits</span></span>
    
- <span data-ttu-id="db1dc-839">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="db1dc-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="db1dc-840">Foreigner の識別番号のない Foreigners</span><span class="sxs-lookup"><span data-stu-id="db1dc-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="db1dc-841">1つの大文字の "M" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="db1dc-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="db1dc-842">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="db1dc-842">Seven digits</span></span>
    
- <span data-ttu-id="db1dc-843">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="db1dc-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="db1dc-844">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-844">Checksum</span></span>

<span data-ttu-id="db1dc-845">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-846">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-846">Definition</span></span>

<span data-ttu-id="db1dc-847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-848">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-849">From `Keywords_spain_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-851">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-852">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="db1dc-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-854">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-854">tax id</span></span>
  
<span data-ttu-id="db1dc-855">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-855">tax id number</span></span>
  
<span data-ttu-id="db1dc-856">cif id</span><span class="sxs-lookup"><span data-stu-id="db1dc-856">cif id</span></span>
  
<span data-ttu-id="db1dc-857">cif 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-857">cif no</span></span>
  
<span data-ttu-id="db1dc-858">スペインの cif id</span><span class="sxs-lookup"><span data-stu-id="db1dc-858">spanish cif id</span></span>
  
<span data-ttu-id="db1dc-859">cif</span><span class="sxs-lookup"><span data-stu-id="db1dc-859">cif</span></span>
  
<span data-ttu-id="db1dc-860">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-860">tax file no</span></span>
  
<span data-ttu-id="db1dc-861">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-861">spanish cif number</span></span>
  
<span data-ttu-id="db1dc-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="db1dc-862">tax file number</span></span>
  
<span data-ttu-id="db1dc-863">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-863">spanish cif no</span></span>
  
<span data-ttu-id="db1dc-864">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-864">tax no</span></span>
  
<span data-ttu-id="db1dc-865">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-865">tax number</span></span>
  
<span data-ttu-id="db1dc-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-866">taxid#</span></span>
  
<span data-ttu-id="db1dc-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-867">taxno#</span></span>
  
<span data-ttu-id="db1dc-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-868">cifid#</span></span>
  
<span data-ttu-id="db1dc-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-869">spanishcifid#</span></span>
  
<span data-ttu-id="db1dc-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="db1dc-870">spanishcifno#</span></span>
  
<span data-ttu-id="db1dc-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="db1dc-871">número de contribuyente</span></span>
  
<span data-ttu-id="db1dc-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="db1dc-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="db1dc-873">número de identificación 会計</span><span class="sxs-lookup"><span data-stu-id="db1dc-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="db1dc-874">cif número</span><span class="sxs-lookup"><span data-stu-id="db1dc-874">cif número</span></span>
  
<span data-ttu-id="db1dc-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="db1dc-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="db1dc-876">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="db1dc-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-877">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-877">Format</span></span>

<span data-ttu-id="db1dc-878">指定したパターンの10桁の数字と記号</span><span class="sxs-lookup"><span data-stu-id="db1dc-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-879">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-879">Pattern</span></span>

<span data-ttu-id="db1dc-880">10桁の数字と記号:</span><span class="sxs-lookup"><span data-stu-id="db1dc-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="db1dc-881">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="db1dc-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="db1dc-882">プラス記号、マイナス記号、または円記号</span><span class="sxs-lookup"><span data-stu-id="db1dc-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="db1dc-883">識別番号を一意にするための3桁の数字:</span><span class="sxs-lookup"><span data-stu-id="db1dc-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="db1dc-884">1990より前に発行された番号については、7桁目と8桁目の数字は、誕生日または外国出身の人物を識別します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="db1dc-885">9桁の数字は、男性に対して、または女性に対して、性別を示します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="db1dc-886">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="db1dc-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db1dc-887">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-887">Checksum</span></span>

<span data-ttu-id="db1dc-888">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-889">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-889">Definition</span></span>

<span data-ttu-id="db1dc-890">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-891">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-892">From `Keywords_sweden_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="db1dc-893">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-894">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="db1dc-895">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="db1dc-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-897">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-897">tax id</span></span>
  
<span data-ttu-id="db1dc-898">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-898">tax id no.</span></span>
  
<span data-ttu-id="db1dc-899">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-899">tax id number</span></span>
  
<span data-ttu-id="db1dc-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="db1dc-900">tax identification</span></span>
  
<span data-ttu-id="db1dc-901">税の識別#</span><span class="sxs-lookup"><span data-stu-id="db1dc-901">tax identification#</span></span>
  
<span data-ttu-id="db1dc-902">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-902">tax no.</span></span>
  
<span data-ttu-id="db1dc-903">申告#</span><span class="sxs-lookup"><span data-stu-id="db1dc-903">tax#</span></span>
  
<span data-ttu-id="db1dc-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-904">taxid#</span></span>
  
<span data-ttu-id="db1dc-905">税ファイル</span><span class="sxs-lookup"><span data-stu-id="db1dc-905">tax file</span></span>
  
<span data-ttu-id="db1dc-906">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-906">tax file no.</span></span>
  
<span data-ttu-id="db1dc-907">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-907">personal id number</span></span>
  
<span data-ttu-id="db1dc-908">skatt id の nummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-908">skatt id nummer</span></span>
  
<span data-ttu-id="db1dc-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="db1dc-909">skatt identifikation</span></span>
  
<span data-ttu-id="db1dc-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="db1dc-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="db1dc-911">佐賀</span><span class="sxs-lookup"><span data-stu-id="db1dc-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="db1dc-912">Format</span><span class="sxs-lookup"><span data-stu-id="db1dc-912">Format</span></span>

<span data-ttu-id="db1dc-913">Unique 納税リファレンス (UTR): スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="db1dc-914">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="db1dc-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="db1dc-915">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db1dc-916">パターン</span><span class="sxs-lookup"><span data-stu-id="db1dc-916">Pattern</span></span>

<span data-ttu-id="db1dc-917">Unique 納税リファレンス (UTR):10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="db1dc-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="db1dc-918">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="db1dc-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="db1dc-919">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db1dc-920">チェックサム</span><span class="sxs-lookup"><span data-stu-id="db1dc-920">Checksum</span></span>

<span data-ttu-id="db1dc-921">はい</span><span class="sxs-lookup"><span data-stu-id="db1dc-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="db1dc-922">定義</span><span class="sxs-lookup"><span data-stu-id="db1dc-922">Definition</span></span>

<span data-ttu-id="db1dc-923">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db1dc-924">関数`Func_uk_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="db1dc-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db1dc-925">From `Keywords_uk_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="db1dc-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db1dc-926">キーワード</span><span class="sxs-lookup"><span data-stu-id="db1dc-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="db1dc-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="db1dc-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="db1dc-928">tax id</span><span class="sxs-lookup"><span data-stu-id="db1dc-928">tax id</span></span>
  
<span data-ttu-id="db1dc-929">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-929">tax id no.</span></span>
  
<span data-ttu-id="db1dc-930">納税者番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-930">tax id number</span></span>
  
<span data-ttu-id="db1dc-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="db1dc-931">tax identification</span></span>
  
<span data-ttu-id="db1dc-932">税の識別#</span><span class="sxs-lookup"><span data-stu-id="db1dc-932">tax identification#</span></span>
  
<span data-ttu-id="db1dc-933">課税番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-933">tax no.</span></span>
  
<span data-ttu-id="db1dc-934">申告#</span><span class="sxs-lookup"><span data-stu-id="db1dc-934">tax#</span></span>
  
<span data-ttu-id="db1dc-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="db1dc-935">taxid#</span></span>
  
<span data-ttu-id="db1dc-936">税ファイル</span><span class="sxs-lookup"><span data-stu-id="db1dc-936">tax file</span></span>
  
<span data-ttu-id="db1dc-937">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="db1dc-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db1dc-938">関連項目</span><span class="sxs-lookup"><span data-stu-id="db1dc-938">See also</span></span>

[<span data-ttu-id="db1dc-939">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="db1dc-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

