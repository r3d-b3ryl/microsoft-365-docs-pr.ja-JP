---
title: ロシアパスポート番号の国際エンティティ定義
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
description: ロシアパスポート番号の国際機密情報型エンティティ定義。
ms.openlocfilehash: 4f8c581dccac25d3c7f402e2d273037918c05868
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367425"
---
# <a name="russia-passport-number-international"></a>ロシアの国際パスポート番号

## <a name="format"></a>フォーマット

9 桁の数字

## <a name="pattern"></a>パターン

9 桁の数字:

- 2 桁の数字
- 省略可能なスペースまたはハイフン
- 7 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_Russian_Passport_Number_International` は、パターンに一致するコンテンツを検索します。
- `Keyword_Russian_Passport_Number` のキーワードを検出した。

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- passport no
- パスポート#
- パスポート ID
- passportno#
- passportnumber#
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#