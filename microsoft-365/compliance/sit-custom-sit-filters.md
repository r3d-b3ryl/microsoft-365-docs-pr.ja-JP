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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: この記事では、カスタム機密情報の種類にエンコードできるフィルターの一覧を示します。
ms.openlocfilehash: e5f3fb99ec4454410c3719dc3d76356e02f03573
ms.sourcegitcommit: 19e16b16f144159b55bb4c544403e3642b69e335
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62818230"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>カスタム機密情報の種類のフィルター リファレンス

Microsoft では、カスタム機密情報の種類 (SIT) を作成する際にフィルターなどのチェックを定義できます。

## <a name="list-of-supported-filters-and-use-cases"></a>サポートされているフィルターと使用例の一覧

### <a name="alldigitssame-exclude"></a>AllDigitsSame Exclude

説明: すべての数字が重複する数字 (111111111 または 111-111-111 など) の一致を除外できます。

フィルターの定義
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

エンティティ レベルでのルール パッケージでの使用
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

パターン レベルでのルール パッケージでの使用
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

説明: エンティティの開始文字を定義できます。 このバリエーションには、含めるおよび除外する 2 つのバリエーションがあります。

たとえば、次のようなリストで、0500、91、091、010 から始まる数値を除外します。

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

次の xml を使用できます。

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
たとえば、次のようなリストに 0500、91、091、0100 で始まる数値を含めるには、次のようにします。 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

次の xml を使用できます。

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

説明: エンティティの終了文字を定義できます。 

たとえば、次のようなリストで 0500,91,091,0100 で終わる数値を除外するには、次のようにします。

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

次の xml を使用できます。

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

たとえば、0500、91、091、0100 で終わる数値を次のようなリストに含めるには、次のようにします。

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

次の xml を使用できます。

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

説明: 特定の一致を禁止して、ルールをトリガーすることを禁止できます。 たとえば、有効なクレジット 4111111111111111一致の一覧から除外します。

たとえば、次のようなリストで、4111111111111111や3241891031113111クレジット カード番号を除外します。

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

次の xml を使用できます。

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

たとえば、次のようなクレジット カード番号を4111111111111111、3241891031113111に含めるには、次のようにします。

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

次の xml を使用できます。

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>TextMatchFilter プレフィックス

説明: 常に含めるか除外する前の文字を定義できます。 たとえば、クレジット カード番号の前に 'Order ID:' が付く場合は、有効な一致から一致を削除します。

たとえば、次のようなリストで、電話番号を持つ電話番号の出現を除外し、電話番号の前に文字列で呼び出します。

- 電話番号 091-8974-653278
- 電話 45-124576532-123
- 45-124576532-123

次の xml を使用できます。

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

たとえば、クレジット カード番号の前にクレジット  カードとカード **#** 文字列が含まれるオカレンスを次のようなリストに含めるには、次のようにします。

- クレジット カード 45-124576532-123 
- 45-124576532-123 (電話番号)

次の xml を使用できます。

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

### <a name="textmatchfilter-suffix"></a>TextMatchFilter サフィックス

説明: 常に含めるか除外する必要がある次の文字を定義できます。 たとえば、クレジット カード番号の後に '/xuid' が続く場合は、有効な一致から一致を削除します。

たとえば、次のようなリストに接尾辞として 4 桁のインスタンスが 5 つ追加されている場合は、上位の出現を除外します。

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

次の xml を使用できます。

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
たとえば、/ **xuidsuffix** が続く場合は、次のリストの出現を除外します。

- 1234-5678-9321 /xuid
- 1234-5678-9321

この xml を使用できます

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix">
    <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group>
  </Keyword>
```

たとえば、次のリストに 2 つのように、**cvv** が続く場合、または有効期限が切れた場合にのみ、オカレンスを含めるには、次の手順を実行します。

- 45-124576532-123 
- 45-124576532-123 cvv 966
- 45-124576532-123 有効期限 03/23

この xml を使用できます

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

## <a name="using-filters-in-rule-packages"></a>ルール パッケージでのフィルターの使用

フィルターは、SIT 全体またはパターンで定義できます。 コード スニペットの例を次に示します。 

### <a name="at-sensitive-information-type-level"></a>機密情報の種類レベル

Entity のフィルター - すべての子パターンをカバーします

フィルターは、 **そのエンティティ/** 機密型のパターンによって分類されるすべてのインスタンスに適用されます。

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>機密情報の種類レベルの個々のパターンで

パターン レベルでのみフィルターを適用します。

フィルターは、パターンに一致するインスタンスに適用されます。

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>機密情報の種類レベルと、そのエンティティのパターンの一部に対する追加のフィルター

Entity + パターンのフィルター

フィルターは、 **そのエンティティ/** 機密性の高い型のパターンによって分類されたすべてのインスタンスに適用されます。 パターン レベル フィルターは、そのパターンに一致するインスタンスをフィルター処理します。

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>詳細情報

- [データ損失防止について](dlp-learn-about-dlp.md)

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)

- [DLP 関数の検索対象](what-the-dlp-functions-look-for.md)
