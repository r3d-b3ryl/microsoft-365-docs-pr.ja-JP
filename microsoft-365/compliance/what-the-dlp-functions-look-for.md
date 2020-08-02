---
title: データ損失防止 (DLP) 関数の検索対象
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
description: データ損失防止 (DLP) 関数の検索方法について説明します。
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536312"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="121ee-103">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="121ee-103">What the DLP functions look for</span></span>

<span data-ttu-id="121ee-104">データ損失防止 (DLP) には、クレジットカード番号、EU デビットカード番号などの機密情報の種類が含まれています。これは、DLP ポリシーで使用する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="121ee-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="121ee-105">これらの機密情報の種類では、特定のパターンが検索され、適切な書式設定とチェックサムを適用し、関連するキーワードまたはその他の情報を検索することによって、corroborate します。</span><span class="sxs-lookup"><span data-stu-id="121ee-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="121ee-106">この機能の一部は、内部機能によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="121ee-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="121ee-107">たとえば、クレジットカード番号の機密情報の種類では、有効期限として書式設定された日付を検索するために関数を使用しています。これは、corroborate がクレジットカード番号であることを示すために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="121ee-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="121ee-108">この記事では、定義済みの機密情報の種類のしくみを理解するために役立つ関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="121ee-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="121ee-109">詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="121ee-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="121ee-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="121ee-110">Func_us_date</span></span>

<span data-ttu-id="121ee-111">この関数は、米国でよく使用される形式の日付を検索します。これには、"月/日/年"、"月-日-年"、"月間年月日" の形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="121ee-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="121ee-112">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="121ee-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="121ee-113">例:</span><span class="sxs-lookup"><span data-stu-id="121ee-113">Examples:</span></span>
  
- <span data-ttu-id="121ee-114">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="121ee-114">December 2, 2016</span></span>
    
- <span data-ttu-id="121ee-115">2016年12月2</span><span class="sxs-lookup"><span data-stu-id="121ee-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="121ee-116">02 2016 年12月</span><span class="sxs-lookup"><span data-stu-id="121ee-116">dec 02 2016</span></span>
    
- <span data-ttu-id="121ee-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="121ee-117">12/2/2016</span></span>
    
- <span data-ttu-id="121ee-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="121ee-118">12/02/16</span></span>
    
- <span data-ttu-id="121ee-119">2-2016 年12月</span><span class="sxs-lookup"><span data-stu-id="121ee-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="121ee-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="121ee-120">12-2-16</span></span>
    
<span data-ttu-id="121ee-121">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="121ee-121">Accepted month names:</span></span>
  
- <span data-ttu-id="121ee-122">English</span><span class="sxs-lookup"><span data-stu-id="121ee-122">English</span></span>
    
  - <span data-ttu-id="121ee-123">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="121ee-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="121ee-124">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="121ee-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="121ee-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="121ee-125">Func_eu_date</span></span>

<span data-ttu-id="121ee-126">この関数は、E.U. でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="121ee-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="121ee-127">(米国以外の場所) ("day/月/年"、"日-月"、"月の年" など)。</span><span class="sxs-lookup"><span data-stu-id="121ee-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="121ee-128">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="121ee-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="121ee-129">例:</span><span class="sxs-lookup"><span data-stu-id="121ee-129">Examples:</span></span>
  
- <span data-ttu-id="121ee-130">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="121ee-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="121ee-131">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="121ee-131">02 dec 2016</span></span>
    
- <span data-ttu-id="121ee-132">2月16時</span><span class="sxs-lookup"><span data-stu-id="121ee-132">2 Dec 16</span></span>
    
- <span data-ttu-id="121ee-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="121ee-133">2/12/2016</span></span>
    
- <span data-ttu-id="121ee-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="121ee-134">02/12/16</span></span>
    
- <span data-ttu-id="121ee-135">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="121ee-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="121ee-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="121ee-136">2-12-16</span></span>
    
<span data-ttu-id="121ee-137">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="121ee-137">Accepted month names:</span></span>
  
- <span data-ttu-id="121ee-138">English</span><span class="sxs-lookup"><span data-stu-id="121ee-138">English</span></span>
    
  - <span data-ttu-id="121ee-139">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="121ee-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="121ee-140">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="121ee-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="121ee-141">オランダ語</span><span class="sxs-lookup"><span data-stu-id="121ee-141">Dutch</span></span>
    
  - <span data-ttu-id="121ee-142">januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="121ee-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="121ee-143">1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)</span><span class="sxs-lookup"><span data-stu-id="121ee-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="121ee-144">フランス語</span><span class="sxs-lookup"><span data-stu-id="121ee-144">French</span></span>
    
  - <span data-ttu-id="121ee-145">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="121ee-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="121ee-146">janv.</span><span class="sxs-lookup"><span data-stu-id="121ee-146">janv.</span></span> <span data-ttu-id="121ee-147">févr.</span><span class="sxs-lookup"><span data-stu-id="121ee-147">févr.</span></span> <span data-ttu-id="121ee-148">mars avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="121ee-148">mars avril mai juin juil.</span></span> <span data-ttu-id="121ee-149">août 9 月</span><span class="sxs-lookup"><span data-stu-id="121ee-149">août sept.</span></span> <span data-ttu-id="121ee-150">oct.</span><span class="sxs-lookup"><span data-stu-id="121ee-150">oct.</span></span> <span data-ttu-id="121ee-151">年11月.</span><span class="sxs-lookup"><span data-stu-id="121ee-151">nov.</span></span> <span data-ttu-id="121ee-152">déc.</span><span class="sxs-lookup"><span data-stu-id="121ee-152">déc.</span></span>
    
- <span data-ttu-id="121ee-153">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="121ee-153">German</span></span>
    
  - <span data-ttu-id="121ee-154">jänuar、februar、märz、エイプリル、mai、juni juli、8月、9月、oktober、11月、dezember</span><span class="sxs-lookup"><span data-stu-id="121ee-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="121ee-155">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="121ee-155">Jan./Jän.</span></span> <span data-ttu-id="121ee-156">März Mai Juni Juli 年8月9日。</span><span class="sxs-lookup"><span data-stu-id="121ee-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="121ee-157">11月. Dez。</span><span class="sxs-lookup"><span data-stu-id="121ee-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="121ee-158">イタリア語</span><span class="sxs-lookup"><span data-stu-id="121ee-158">Italian</span></span>
    
  - <span data-ttu-id="121ee-159">gennaio、febbraio、marzo、aprile、maggio、gifeno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="121ee-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="121ee-160">genn。</span><span class="sxs-lookup"><span data-stu-id="121ee-160">genn.</span></span> <span data-ttu-id="121ee-161">febbr。</span><span class="sxs-lookup"><span data-stu-id="121ee-161">febbr.</span></span> <span data-ttu-id="121ee-162">年.</span><span class="sxs-lookup"><span data-stu-id="121ee-162">mar.</span></span> <span data-ttu-id="121ee-163">4.</span><span class="sxs-lookup"><span data-stu-id="121ee-163">apr.</span></span> <span data-ttu-id="121ee-164">magg</span><span class="sxs-lookup"><span data-stu-id="121ee-164">magg.</span></span> <span data-ttu-id="121ee-165">giluglio ag はありません。</span><span class="sxs-lookup"><span data-stu-id="121ee-165">giugno luglio ag.</span></span> <span data-ttu-id="121ee-166">設定.</span><span class="sxs-lookup"><span data-stu-id="121ee-166">sett.</span></span> <span data-ttu-id="121ee-167">ott。</span><span class="sxs-lookup"><span data-stu-id="121ee-167">ott.</span></span> <span data-ttu-id="121ee-168">年11月.</span><span class="sxs-lookup"><span data-stu-id="121ee-168">nov.</span></span> <span data-ttu-id="121ee-169">.dic.</span><span class="sxs-lookup"><span data-stu-id="121ee-169">dic.</span></span>
    
- <span data-ttu-id="121ee-170">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="121ee-170">Portuguese</span></span>
    
  - <span data-ttu-id="121ee-171">ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="121ee-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="121ee-172">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="121ee-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="121ee-173">スペイン語</span><span class="sxs-lookup"><span data-stu-id="121ee-173">Spanish</span></span>
    
  - <span data-ttu-id="121ee-174">enero、febrero、marzo、abril、ago、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="121ee-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="121ee-175">enero feb</span><span class="sxs-lookup"><span data-stu-id="121ee-175">enero feb.</span></span> <span data-ttu-id="121ee-176">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="121ee-176">marzo abr.</span></span> <span data-ttu-id="121ee-177">6月 o 日</span><span class="sxs-lookup"><span data-stu-id="121ee-177">mayo jun.</span></span> <span data-ttu-id="121ee-178">年.</span><span class="sxs-lookup"><span data-stu-id="121ee-178">jul.</span></span> <span data-ttu-id="121ee-179">/set. 年9月.</span><span class="sxs-lookup"><span data-stu-id="121ee-179">agosto sept./set.</span></span> <span data-ttu-id="121ee-180">oct.</span><span class="sxs-lookup"><span data-stu-id="121ee-180">oct.</span></span> <span data-ttu-id="121ee-181">年11月.</span><span class="sxs-lookup"><span data-stu-id="121ee-181">nov.</span></span> <span data-ttu-id="121ee-182">.dic.</span><span class="sxs-lookup"><span data-stu-id="121ee-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="121ee-183">Func_eu_date1 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="121ee-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="121ee-184">この関数は、上記の関数に含まれているポルトガル語の月の名前のみをサポートしているため、廃止されました `Func_eu_date` 。</span><span class="sxs-lookup"><span data-stu-id="121ee-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="121ee-185">この関数は、ポルトガル語でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="121ee-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="121ee-186">この関数の形式は、使用されている `Func_eu_date` 言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="121ee-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="121ee-187">例:</span><span class="sxs-lookup"><span data-stu-id="121ee-187">Examples:</span></span>
  
- <span data-ttu-id="121ee-188">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="121ee-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="121ee-189">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="121ee-189">02 dez 2016</span></span>
    
- <span data-ttu-id="121ee-190">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="121ee-190">2 Dez 16</span></span>
    
- <span data-ttu-id="121ee-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="121ee-191">2/12/2016</span></span>
    
- <span data-ttu-id="121ee-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="121ee-192">02/12/16</span></span>
    
- <span data-ttu-id="121ee-193">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="121ee-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="121ee-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="121ee-194">2-12-16</span></span>
    
<span data-ttu-id="121ee-195">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="121ee-195">Accepted month names:</span></span>
  
- <span data-ttu-id="121ee-196">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="121ee-196">Portuguese</span></span>
    
  - <span data-ttu-id="121ee-197">ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="121ee-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="121ee-198">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="121ee-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="121ee-199">Func_eu_date2 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="121ee-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="121ee-200">この関数は、上の関数に含まれるオランダ語の月の名前のみをサポートしているため、廃止されました `Func_eu_date` 。</span><span class="sxs-lookup"><span data-stu-id="121ee-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="121ee-201">この関数は、オランダ語でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="121ee-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="121ee-202">この関数の形式は、使用されている `Func_eu_date` 言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="121ee-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="121ee-203">例:</span><span class="sxs-lookup"><span data-stu-id="121ee-203">Examples:</span></span>
  
- <span data-ttu-id="121ee-204">2 mei 2016</span><span class="sxs-lookup"><span data-stu-id="121ee-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="121ee-205">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="121ee-205">02 mei 2016</span></span>
    
- <span data-ttu-id="121ee-206">2 mei 16</span><span class="sxs-lookup"><span data-stu-id="121ee-206">2 Mei 16</span></span>
    
- <span data-ttu-id="121ee-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="121ee-207">2/12/2016</span></span>
    
- <span data-ttu-id="121ee-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="121ee-208">02/12/16</span></span>
    
- <span data-ttu-id="121ee-209">2-mei-2016</span><span class="sxs-lookup"><span data-stu-id="121ee-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="121ee-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="121ee-210">2-12-16</span></span>
    
<span data-ttu-id="121ee-211">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="121ee-211">Accepted month names:</span></span>
  
- <span data-ttu-id="121ee-212">オランダ語</span><span class="sxs-lookup"><span data-stu-id="121ee-212">Dutch</span></span>
    
  - <span data-ttu-id="121ee-213">januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="121ee-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="121ee-214">jan 2 月9日9月 (9 月) (9 月7日)</span><span class="sxs-lookup"><span data-stu-id="121ee-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="121ee-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="121ee-215">Func_expiration_date</span></span>

<span data-ttu-id="121ee-216">この関数は、クレジットカードとデビットカードでよく使用される形式の日付を検索します。これにより、月の代わりに日付が除外されます。</span><span class="sxs-lookup"><span data-stu-id="121ee-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="121ee-217">この関数は、日付を "月/年"、"月-年"、"[月名] 年"、"月の省略名] 年" の形式で照合します。</span><span class="sxs-lookup"><span data-stu-id="121ee-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="121ee-218">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="121ee-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="121ee-219">例:</span><span class="sxs-lookup"><span data-stu-id="121ee-219">Examples:</span></span>
  
- <span data-ttu-id="121ee-220">MM/YY--たとえば、01/11 または1/11</span><span class="sxs-lookup"><span data-stu-id="121ee-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="121ee-221">MM/YYYY--たとえば、01/2011 または1/2011</span><span class="sxs-lookup"><span data-stu-id="121ee-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="121ee-222">MM-YY--たとえば、01-22 または1-11</span><span class="sxs-lookup"><span data-stu-id="121ee-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="121ee-223">MM-YYYY--たとえば、01-2000 または1-2000</span><span class="sxs-lookup"><span data-stu-id="121ee-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="121ee-224">次の形式では、YY または YYYY がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121ee-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="121ee-225">月--2010 または 2010 1 月-または Jan-10 または Jan-10 または1月10日</span><span class="sxs-lookup"><span data-stu-id="121ee-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="121ee-226">月 YYYY--たとえば、' january 2010 ' または ' Jan 2010 ' または ' Jan 10 ' または ' Jan 10 ' のようになります。</span><span class="sxs-lookup"><span data-stu-id="121ee-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="121ee-227">月 Yyyy--たとえば、' january2010 ' または ' Jan2010 ' または ' january10 ' または ' Jan10 '</span><span class="sxs-lookup"><span data-stu-id="121ee-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="121ee-228">Month/YYYY--たとえば、' january/2010 '、' Jan/2010 '、' jan/10 '、または ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="121ee-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="121ee-229">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="121ee-229">Accepted month names:</span></span>
  
- <span data-ttu-id="121ee-230">English</span><span class="sxs-lookup"><span data-stu-id="121ee-230">English</span></span>
    
  - <span data-ttu-id="121ee-231">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="121ee-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="121ee-232">1月2日から4月5日 (年7月)</span><span class="sxs-lookup"><span data-stu-id="121ee-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="121ee-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="121ee-233">Func_us_address</span></span>

<span data-ttu-id="121ee-234">この関数は、米国の都道府県名または郵便番号の後に有効な郵便番号を検索します。その後、郵便番号と同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="121ee-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="121ee-235">郵便番号は、米国の州名または略語に関連付けられている正しい zip コードのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="121ee-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="121ee-236">米国の都道府県名と郵便番号は、句読点または文字で区切ることはできません。</span><span class="sxs-lookup"><span data-stu-id="121ee-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="121ee-237">例:</span><span class="sxs-lookup"><span data-stu-id="121ee-237">Examples:</span></span>
  
- <span data-ttu-id="121ee-238">ワシントン98052</span><span class="sxs-lookup"><span data-stu-id="121ee-238">Washington 98052</span></span>
    
- <span data-ttu-id="121ee-239">ワシントン98052-9998</span><span class="sxs-lookup"><span data-stu-id="121ee-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="121ee-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="121ee-240">WA 98052</span></span>
    
- <span data-ttu-id="121ee-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="121ee-241">WA 98052-9998</span></span>
    

