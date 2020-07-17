---
title: DLP 関数の検索対象
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 定義済みの機密情報の種類がどのように機能するかを理解するために、データ損失防止 (DLP) 関数がどのような意味を持つかを説明します。
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819277"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="9ddf8-103">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="9ddf8-103">What the DLP functions look for</span></span>

<span data-ttu-id="9ddf8-104">データ損失防止 (DLP) には、クレジットカード番号、EU デビットカード番号などの機密情報の種類が含まれています。これは、DLP ポリシーで使用する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-104">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="9ddf8-105">これらの機密情報の種類では、特定のパターンが検索され、適切な書式設定とチェックサムを適用し、関連するキーワードまたはその他の情報を検索することによって、corroborate します。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="9ddf8-106">この機能の一部は、内部機能によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="9ddf8-107">たとえば、クレジットカード番号の機密情報の種類では、有効期限として書式設定された日付を検索するために関数を使用しています。これは、corroborate がクレジットカード番号であることを示すために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="9ddf8-108">このトピックでは、定義済みの機密情報の種類がどのように機能するかを理解するために、これらの関数がどのようなものかを説明します。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="9ddf8-109">詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="9ddf8-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="9ddf8-110">Func_us_date</span></span>

<span data-ttu-id="9ddf8-111">この関数は、米国でよく使用される形式の日付を検索します。これには、"月/日/年"、"月-日-年"、"月間年月日" の形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="9ddf8-112">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="9ddf8-113">例:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-113">Examples:</span></span>
  
- <span data-ttu-id="9ddf8-114">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="9ddf8-114">December 2, 2016</span></span>
    
- <span data-ttu-id="9ddf8-115">2016年12月2</span><span class="sxs-lookup"><span data-stu-id="9ddf8-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="9ddf8-116">02 2016 年12月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-116">dec 02 2016</span></span>
    
- <span data-ttu-id="9ddf8-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-117">12/2/2016</span></span>
    
- <span data-ttu-id="9ddf8-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-118">12/02/16</span></span>
    
- <span data-ttu-id="9ddf8-119">2-2016 年12月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="9ddf8-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-120">12-2-16</span></span>
    
<span data-ttu-id="9ddf8-121">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-121">Accepted month names:</span></span>
  
- <span data-ttu-id="9ddf8-122">English</span><span class="sxs-lookup"><span data-stu-id="9ddf8-122">English</span></span>
    
  - <span data-ttu-id="9ddf8-123">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9ddf8-124">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="9ddf8-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="9ddf8-125">Func_eu_date</span></span>

<span data-ttu-id="9ddf8-126">この関数は、E.U. でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="9ddf8-127">(米国以外の場所)。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-127">(and most places outside the U.S.).</span></span> <span data-ttu-id="9ddf8-128">これには、"日/月/年"、"年月日"、"day month" の形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-128">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="9ddf8-129">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-129">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="9ddf8-130">例:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-130">Examples:</span></span>
  
- <span data-ttu-id="9ddf8-131">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="9ddf8-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="9ddf8-132">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-132">02 dec 2016</span></span>
    
- <span data-ttu-id="9ddf8-133">2月16時</span><span class="sxs-lookup"><span data-stu-id="9ddf8-133">2 Dec 16</span></span>
    
- <span data-ttu-id="9ddf8-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-134">2/12/2016</span></span>
    
- <span data-ttu-id="9ddf8-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-135">02/12/16</span></span>
    
- <span data-ttu-id="9ddf8-136">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="9ddf8-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="9ddf8-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-137">2-12-16</span></span>
    
<span data-ttu-id="9ddf8-138">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-138">Accepted month names:</span></span>
  
- <span data-ttu-id="9ddf8-139">English</span><span class="sxs-lookup"><span data-stu-id="9ddf8-139">English</span></span>
    
  - <span data-ttu-id="9ddf8-140">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9ddf8-141">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="9ddf8-142">オランダ語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-142">Dutch</span></span>
    
  - <span data-ttu-id="9ddf8-143">januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="9ddf8-144">1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)</span><span class="sxs-lookup"><span data-stu-id="9ddf8-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="9ddf8-145">フランス語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-145">French</span></span>
    
  - <span data-ttu-id="9ddf8-146">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="9ddf8-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="9ddf8-147">janv.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-147">janv.</span></span> <span data-ttu-id="9ddf8-148">févr.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-148">févr.</span></span> <span data-ttu-id="9ddf8-149">mars avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-149">mars avril mai juin juil.</span></span> <span data-ttu-id="9ddf8-150">août 9 月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-150">août sept.</span></span> <span data-ttu-id="9ddf8-151">oct.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-151">oct.</span></span> <span data-ttu-id="9ddf8-152">年11月.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-152">nov.</span></span> <span data-ttu-id="9ddf8-153">déc.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-153">déc.</span></span>
    
- <span data-ttu-id="9ddf8-154">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-154">German</span></span>
    
  - <span data-ttu-id="9ddf8-155">jänuar、februar、märz、エイプリル、mai、juni juli、8月、9月、oktober、11月、dezember</span><span class="sxs-lookup"><span data-stu-id="9ddf8-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="9ddf8-156">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-156">Jan./Jän.</span></span> <span data-ttu-id="9ddf8-157">März Mai Juni Juli 年8月9日。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="9ddf8-158">11月. Dez。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="9ddf8-159">イタリア語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-159">Italian</span></span>
    
  - <span data-ttu-id="9ddf8-160">gennaio、febbraio、marzo、aprile、maggio、gifeno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="9ddf8-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="9ddf8-161">genn。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-161">genn.</span></span> <span data-ttu-id="9ddf8-162">febbr。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-162">febbr.</span></span> <span data-ttu-id="9ddf8-163">年.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-163">mar.</span></span> <span data-ttu-id="9ddf8-164">4.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-164">apr.</span></span> <span data-ttu-id="9ddf8-165">magg</span><span class="sxs-lookup"><span data-stu-id="9ddf8-165">magg.</span></span> <span data-ttu-id="9ddf8-166">giluglio ag はありません。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-166">giugno luglio ag.</span></span> <span data-ttu-id="9ddf8-167">設定.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-167">sett.</span></span> <span data-ttu-id="9ddf8-168">ott。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-168">ott.</span></span> <span data-ttu-id="9ddf8-169">年11月.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-169">nov.</span></span> <span data-ttu-id="9ddf8-170">.dic.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-170">dic.</span></span>
    
- <span data-ttu-id="9ddf8-171">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-171">Portuguese</span></span>
    
  - <span data-ttu-id="9ddf8-172">ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="9ddf8-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="9ddf8-173">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="9ddf8-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="9ddf8-174">スペイン語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-174">Spanish</span></span>
    
  - <span data-ttu-id="9ddf8-175">enero、febrero、marzo、abril、ago、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="9ddf8-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="9ddf8-176">enero feb</span><span class="sxs-lookup"><span data-stu-id="9ddf8-176">enero feb.</span></span> <span data-ttu-id="9ddf8-177">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-177">marzo abr.</span></span> <span data-ttu-id="9ddf8-178">6月 o 日</span><span class="sxs-lookup"><span data-stu-id="9ddf8-178">mayo jun.</span></span> <span data-ttu-id="9ddf8-179">年.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-179">jul.</span></span> <span data-ttu-id="9ddf8-180">/set. 年9月.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-180">agosto sept./set.</span></span> <span data-ttu-id="9ddf8-181">oct.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-181">oct.</span></span> <span data-ttu-id="9ddf8-182">年11月.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-182">nov.</span></span> <span data-ttu-id="9ddf8-183">.dic.</span><span class="sxs-lookup"><span data-stu-id="9ddf8-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="9ddf8-184">Func_eu_date1 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="9ddf8-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="9ddf8-185">この関数は、上記の関数に含まれているポルトガル語の月の名前のみをサポートしているため、廃止されました `Func_eu_date` 。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="9ddf8-186">この関数は、ポルトガル語でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="9ddf8-187">この関数の形式は、使用されている `Func_eu_date` 言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="9ddf8-188">例:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-188">Examples:</span></span>
  
- <span data-ttu-id="9ddf8-189">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="9ddf8-190">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-190">02 dez 2016</span></span>
    
- <span data-ttu-id="9ddf8-191">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-191">2 Dez 16</span></span>
    
- <span data-ttu-id="9ddf8-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-192">2/12/2016</span></span>
    
- <span data-ttu-id="9ddf8-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-193">02/12/16</span></span>
    
- <span data-ttu-id="9ddf8-194">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="9ddf8-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-195">2-12-16</span></span>
    
<span data-ttu-id="9ddf8-196">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-196">Accepted month names:</span></span>
  
- <span data-ttu-id="9ddf8-197">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-197">Portuguese</span></span>
    
  - <span data-ttu-id="9ddf8-198">ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="9ddf8-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="9ddf8-199">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="9ddf8-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="9ddf8-200">Func_eu_date2 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="9ddf8-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="9ddf8-201">この関数は、上の関数に含まれるオランダ語の月の名前のみをサポートしているため、廃止されました `Func_eu_date` 。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="9ddf8-202">この関数は、オランダ語でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="9ddf8-203">この関数の形式は、使用されている `Func_eu_date` 言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="9ddf8-204">例:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-204">Examples:</span></span>
  
- <span data-ttu-id="9ddf8-205">2 mei 2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="9ddf8-206">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-206">02 mei 2016</span></span>
    
- <span data-ttu-id="9ddf8-207">2 mei 16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-207">2 Mei 16</span></span>
    
- <span data-ttu-id="9ddf8-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-208">2/12/2016</span></span>
    
- <span data-ttu-id="9ddf8-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-209">02/12/16</span></span>
    
- <span data-ttu-id="9ddf8-210">2-mei-2016</span><span class="sxs-lookup"><span data-stu-id="9ddf8-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="9ddf8-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9ddf8-211">2-12-16</span></span>
    
<span data-ttu-id="9ddf8-212">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-212">Accepted month names:</span></span>
  
- <span data-ttu-id="9ddf8-213">オランダ語</span><span class="sxs-lookup"><span data-stu-id="9ddf8-213">Dutch</span></span>
    
  - <span data-ttu-id="9ddf8-214">januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="9ddf8-215">1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)</span><span class="sxs-lookup"><span data-stu-id="9ddf8-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="9ddf8-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="9ddf8-216">Func_expiration_date</span></span>

<span data-ttu-id="9ddf8-217">この関数は、クレジットカードとデビットカードでよく使用される形式の日付を検索します。これにより、月の代わりに日付が除外されます。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="9ddf8-218">この関数は、日付を "月/年"、"月-年"、"[月名] 年"、"月の省略名] 年" の形式で照合します。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="9ddf8-219">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="9ddf8-220">例:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-220">Examples:</span></span>
  
- <span data-ttu-id="9ddf8-221">MM/YY--たとえば、01/11 または1/11</span><span class="sxs-lookup"><span data-stu-id="9ddf8-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="9ddf8-222">MM/YYYY--たとえば、01/2011 または1/2011</span><span class="sxs-lookup"><span data-stu-id="9ddf8-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="9ddf8-223">MM-YY--たとえば、01-22 または1-11</span><span class="sxs-lookup"><span data-stu-id="9ddf8-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="9ddf8-224">MM-YYYY--たとえば、01-2000 または1-2000</span><span class="sxs-lookup"><span data-stu-id="9ddf8-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="9ddf8-225">次の形式では、YY または YYYY がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="9ddf8-226">月-YYYY--たとえば、のようになります。2010または2010または1月10日または1月10日</span><span class="sxs-lookup"><span data-stu-id="9ddf8-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="9ddf8-227">月 YYYY--たとえば、' january 2010 ' または ' Jan 2010 ' または ' Jan 10 ' または ' Jan 10 ' のようになります。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="9ddf8-228">月 Yyyy--たとえば、' january2010 ' または ' Jan2010 ' または ' january10 ' または ' Jan10 '</span><span class="sxs-lookup"><span data-stu-id="9ddf8-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="9ddf8-229">Month/YYYY--たとえば、' january/2010 '、' Jan/2010 '、' jan/10 '、または ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="9ddf8-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="9ddf8-230">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-230">Accepted month names:</span></span>
  
- <span data-ttu-id="9ddf8-231">English</span><span class="sxs-lookup"><span data-stu-id="9ddf8-231">English</span></span>
    
  - <span data-ttu-id="9ddf8-232">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="9ddf8-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9ddf8-233">1月2日から4月5日 (年7月)</span><span class="sxs-lookup"><span data-stu-id="9ddf8-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="9ddf8-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="9ddf8-234">Func_us_address</span></span>

<span data-ttu-id="9ddf8-235">この関数は、米国の都道府県名または郵便省略形の後に、郵便番号で使用されるのと同様に、有効な郵便番号を検索します。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-235">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="9ddf8-236">郵便番号は、米国の州名または略語に関連付けられている正しい zip コードのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-236">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="9ddf8-237">米国の都道府県名と郵便番号は、句読点または文字で区切ることはできません。</span><span class="sxs-lookup"><span data-stu-id="9ddf8-237">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="9ddf8-238">例:</span><span class="sxs-lookup"><span data-stu-id="9ddf8-238">Examples:</span></span>
  
- <span data-ttu-id="9ddf8-239">ワシントン98052</span><span class="sxs-lookup"><span data-stu-id="9ddf8-239">Washington 98052</span></span>
    
- <span data-ttu-id="9ddf8-240">ワシントン98052-9998</span><span class="sxs-lookup"><span data-stu-id="9ddf8-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="9ddf8-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="9ddf8-241">WA 98052</span></span>
    
- <span data-ttu-id="9ddf8-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="9ddf8-242">WA 98052-9998</span></span>
    

