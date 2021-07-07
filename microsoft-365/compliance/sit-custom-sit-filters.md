---
title: カスタム機密情報の種類フィルター リファレンス
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: この記事では、カスタム機密情報の種類にエンコードできるフィルターの一覧を示します。
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322971"
---
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="34925-103">カスタムの機密情報の種類フィルターリファレンス</span><span class="sxs-lookup"><span data-stu-id="34925-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="34925-104">Microsoft では、カスタム機密情報の種類 (SIT) を作成する際にフィルターや追加のチェックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="34925-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="34925-105">サポートされているフィルターと使用例の一覧</span><span class="sxs-lookup"><span data-stu-id="34925-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="34925-106">AllDigitsSame Exclude</span><span class="sxs-lookup"><span data-stu-id="34925-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="34925-107">説明: 111111111 や 111-111-111 など、すべての数字が重複する一致を除外できます。</span><span class="sxs-lookup"><span data-stu-id="34925-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="34925-108">フィルターの定義</span><span class="sxs-lookup"><span data-stu-id="34925-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="34925-109">エンティティ レベルでのルール パッケージでの使用</span><span class="sxs-lookup"><span data-stu-id="34925-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="34925-110">パターン レベルでのルール パッケージでの使用</span><span class="sxs-lookup"><span data-stu-id="34925-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="34925-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="34925-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="34925-112">説明: エンティティの開始文字を定義できます。</span><span class="sxs-lookup"><span data-stu-id="34925-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="34925-113">このバリエーションには、含めるおよび除外する 2 つのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="34925-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="34925-114">たとえば、次のようなリストで、0500、91、091、010 から始まる数値を除外します。</span><span class="sxs-lookup"><span data-stu-id="34925-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="34925-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="34925-115">0500-4500-027</span></span>
- <span data-ttu-id="34925-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="34925-116">91564721450</span></span>
- <span data-ttu-id="34925-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="34925-117">91-8523697410</span></span>
- <span data-ttu-id="34925-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="34925-118">700-8956-7844</span></span>
- <span data-ttu-id="34925-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="34925-119">1000-3265-9874</span></span>
- <span data-ttu-id="34925-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="34925-120">0100-7892-3012</span></span>

<span data-ttu-id="34925-121">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-121">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
<span data-ttu-id="34925-122">たとえば、次のようなリストに 0500、91、091、0100 で始まる数値を含めるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34925-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="34925-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="34925-123">0500-4500-027</span></span>
- <span data-ttu-id="34925-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="34925-124">91564721450</span></span>
- <span data-ttu-id="34925-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="34925-125">91-8523697410</span></span>
- <span data-ttu-id="34925-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="34925-126">700-8956-7844</span></span>
- <span data-ttu-id="34925-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="34925-127">1000-3265-9874</span></span>
- <span data-ttu-id="34925-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="34925-128">0100-7892-3012</span></span>

<span data-ttu-id="34925-129">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="34925-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="34925-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="34925-131">説明: エンティティの終了文字を定義できます。</span><span class="sxs-lookup"><span data-stu-id="34925-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="34925-132">たとえば、次のようなリストで 0500,91,091,0100 で終わる数値を除外するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34925-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="34925-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="34925-133">1234567891</span></span>
- <span data-ttu-id="34925-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="34925-134">1234-5678-0091</span></span>
- <span data-ttu-id="34925-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="34925-135">1234.4567.7091</span></span>
- <span data-ttu-id="34925-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="34925-136">1234-8091-4564</span></span>

<span data-ttu-id="34925-137">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-137">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="34925-138">たとえば、0500、91、091、0100 で終わる数値を次のようなリストに含めるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34925-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="34925-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="34925-139">1234567891</span></span>
- <span data-ttu-id="34925-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="34925-140">1234-5678-0091</span></span>
- <span data-ttu-id="34925-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="34925-141">1234.4567.7091</span></span>
- <span data-ttu-id="34925-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="34925-142">1234-8091-4564</span></span>

<span data-ttu-id="34925-143">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="34925-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="34925-144">TextMatchFilter Full</span></span>

<span data-ttu-id="34925-145">説明: 特定の一致を禁止して、ルールをトリガーすることを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="34925-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="34925-146">たとえば、有効なクレジット カード一致の一覧から 4111111111111 を除外します。</span><span class="sxs-lookup"><span data-stu-id="34925-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="34925-147">たとえば、次のようなリストで 41111111111111111 や 32418910311113111 のようなクレジット カード番号を除外するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34925-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="34925-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="34925-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="34925-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="34925-149">4111111111111111</span></span>
- <span data-ttu-id="34925-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="34925-150">3241891031113111</span></span>

<span data-ttu-id="34925-151">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-151">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="34925-152">たとえば、次のようなリストに 41111111111111111 や 32418910311113111 などのクレジット カード番号を含めるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34925-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="34925-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="34925-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="34925-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="34925-154">4111111111111111</span></span>
- <span data-ttu-id="34925-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="34925-155">3241891031113111</span></span>

<span data-ttu-id="34925-156">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="34925-157">TextMatchFilter プレフィックス</span><span class="sxs-lookup"><span data-stu-id="34925-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="34925-158">説明: 常に含めるか除外する前の文字を定義できます。</span><span class="sxs-lookup"><span data-stu-id="34925-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="34925-159">たとえば、クレジット カード番号の前に 'Order ID:' が付く場合は、有効な一致から一致を削除します。</span><span class="sxs-lookup"><span data-stu-id="34925-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="34925-160">たとえば、次のようなリストで、電話番号を持つ電話番号の出現を除外し、電話番号の前に文字列で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="34925-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="34925-161">電話番号 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="34925-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="34925-162">電話 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="34925-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="34925-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="34925-163">45-124576532-123</span></span>

<span data-ttu-id="34925-164">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-164">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="34925-165">たとえば、クレジット カード番号の前にクレジット カードとカード **#** 文字列が含まれるオカレンスを次のようなリストに含めるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34925-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="34925-166">クレジット カード 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="34925-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="34925-167">45-124576532-123 (電話番号)</span><span class="sxs-lookup"><span data-stu-id="34925-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="34925-168">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-168">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="34925-169">TextMatchFilter サフィックス</span><span class="sxs-lookup"><span data-stu-id="34925-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="34925-170">説明: 常に含めるか除外する必要がある次の文字を定義できます。</span><span class="sxs-lookup"><span data-stu-id="34925-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="34925-171">たとえば、クレジット カード番号の後に '/xuid' が続く場合は、有効な一致から一致を削除します。</span><span class="sxs-lookup"><span data-stu-id="34925-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="34925-172">たとえば、次のようなリストに接尾辞として 4 桁のインスタンスが 5 つ追加されている場合、上位の除外オカレンスが発生します。</span><span class="sxs-lookup"><span data-stu-id="34925-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="34925-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="34925-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="34925-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="34925-174">1234-5678-9321</span></span>

<span data-ttu-id="34925-175">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="34925-176">たとえば **、/xuidsuffix** が続く場合は、次のリストの出現を除外します。</span><span class="sxs-lookup"><span data-stu-id="34925-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="34925-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="34925-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="34925-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="34925-178">1234-5678-9321</span></span>

<span data-ttu-id="34925-179">この xml を使用できます</span><span class="sxs-lookup"><span data-stu-id="34925-179">you can use this xml</span></span>

<span data-ttu-id="34925-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="34925-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="34925-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="34925-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="34925-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="34925-182">/xuid</span></span></Term>
    <span data-ttu-id="34925-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="34925-183"></Group> </Keyword></span></span>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="34925-184">ルール パッケージでのフィルターの使用</span><span class="sxs-lookup"><span data-stu-id="34925-184">Using filters in rule packages</span></span>

<span data-ttu-id="34925-185">フィルターは、SIT 全体またはパターンで定義できます。</span><span class="sxs-lookup"><span data-stu-id="34925-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="34925-186">コード スニペットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34925-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="34925-187">機密情報の種類レベル</span><span class="sxs-lookup"><span data-stu-id="34925-187">At sensitive information type level</span></span>

<span data-ttu-id="34925-188">Entity のフィルター - すべての子パターンをカバーします</span><span class="sxs-lookup"><span data-stu-id="34925-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="34925-189">フィルターは、 **そのエンティティ/** 機密型のパターンによって分類されるすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="34925-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="34925-190">機密情報の種類レベルの個々のパターンで</span><span class="sxs-lookup"><span data-stu-id="34925-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="34925-191">パターン レベルでのみフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="34925-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="34925-192">フィルターは、パターンに一致するインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="34925-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="34925-193">機密情報の種類レベルと、そのエンティティのパターンの一部に対する追加のフィルター</span><span class="sxs-lookup"><span data-stu-id="34925-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="34925-194">Entity + パターンのフィルター</span><span class="sxs-lookup"><span data-stu-id="34925-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="34925-195">フィルターは、 **そのエンティティ/** 機密性の高い型のパターンによって分類されたすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="34925-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="34925-196">パターン レベル フィルターは、そのパターンに一致するインスタンスをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="34925-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="34925-197">詳細情報</span><span class="sxs-lookup"><span data-stu-id="34925-197">More information</span></span>

- [<span data-ttu-id="34925-198">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="34925-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="34925-199">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="34925-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="34925-200">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="34925-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
