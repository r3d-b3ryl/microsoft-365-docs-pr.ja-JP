---
title: ハンガリーの個人識別番号エンティティ定義
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
description: ハンガリーの個人識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: ee3a22ffccdf9110d36e49013bfed912b2d2319b
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367271"
---
# <a name="hungary-personal-identification-number"></a>ハンガリーの個人識別番号

## <a name="format"></a>フォーマット

11 桁の数字

## <a name="pattern"></a>パターン

11 桁の数字:

- 性別に対応する 1 桁、男性の場合は 1 桁、女性の場合は 2 桁です。 1900 年より前に生まれた市民や、二重市民権を持つ市民の場合は、他の番号も可能です。
- 生年月日に対応する 6 桁の数字 (YYMMDD)
- シリアル番号に対応する 3 桁の数字
- 1 つのチェック ディジット

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_hungary_eu_national_id_card` がパターンに一致するコンテンツを検出した。
- `Keywords_hungary_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_hungary_eu_national_id_card` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id 番号
- identification number
- sz ig
- Sz。 Ig。
- sz.ig.
- személyazonosító izezolvány
- személyi tigzolvány