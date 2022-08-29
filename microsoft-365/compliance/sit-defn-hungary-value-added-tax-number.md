---
title: ハンガリーの付加価値税番号エンティティ定義
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: ハンガリーの付加価値税番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 7523bc370177884d058faad4b6313552e8ba3964
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367403"
---
# <a name="hungary-value-added-tax-number"></a>ハンガリーの付加価値税番号

## <a name="format"></a>フォーマット

10 文字の英数字パターン

## <a name="pattern"></a>パターン

10 文字の英数字パターン:

- 2 文字 - HU または hu
- 省略可能な領域
- 8 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_hungarian_value_added_tax_number` がパターンに一致するコンテンツを検出した。
- `Keywords_hungarian_value_added_tax_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_hungarian_value_added_tax_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- Vat
- 付加価値税番号
- Vat#
- vatno#
- ハンガリー語(ハンガリー語)#
- tax no.
- 付加価値税 áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám