---
title: オランダの付加価値税番号エンティティ定義
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
description: オランダの付加価値税番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: eb1db00d5f34d7591cc7f9ff54cba917781d7884
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367667"
---
# <a name="netherlands-value-added-tax-number"></a>オランダ付加価値税番号

## <a name="format"></a>フォーマット

14 文字の英数字パターン

## <a name="pattern"></a>パターン

14 文字の英数字パターン:

- N または n
- L または l
- 省略可能なスペース、ドット、またはハイフン
- 9 桁
- 省略可能なスペース、ドット、またはハイフン
- B または b
- 2 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_netherlands_value_added_tax_number` がパターンに一致するコンテンツを検出した。
- `Keywords_netherlands_value_added_tax_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_netherlands_value_added_tax_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- vat 番号
- vat no
- Vat#
- wearde tafoege tax getal
- btw n・n・mer
- btw-nummer