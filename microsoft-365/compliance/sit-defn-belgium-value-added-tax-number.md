---
title: ベルギーの付加価値税番号エンティティ定義
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
description: ベルギーの付加価値税番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: c1099e69636f9b3dd0fdc5250df47f57506176fd
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367359"
---
# <a name="belgium-value-added-tax-number"></a>ベルギーの付加価値税番号

## <a name="format"></a>フォーマット

12 文字の英数字パターン

## <a name="pattern"></a>パターン

12 文字の英数字パターン:

- 文字 B または b
- 文字 E または e
- 数字 0
- 1 から 9 までの数字
- 省略可能なドットまたはハイフンまたはスペース
- 4 桁の数字
- 省略可能なドットまたはハイフンまたはスペース
- 4 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_belgium_value_added_tax_number` がパターンに一致するコンテンツを検出した。
- `Keywords_belgium_value_added_tax_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_belgium_value_added_tax_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
## <a name="keywords"></a>キーワード

### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- vat 番号
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- ところで
- ところで#
- Vat#
