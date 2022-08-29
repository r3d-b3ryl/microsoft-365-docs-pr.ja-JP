---
title: Luxemburg の国民識別番号 (自然人) エンティティ定義
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
description: Luxemburg の国民識別番号 (自然人) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 3640f35086c72262013ad3e25b5aec1bfe8b6fa3
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367227"
---
# <a name="luxemburg-national-identification-number-natural-persons"></a>ルクセンブルク国民識別番号 (国民)

## <a name="format"></a>フォーマット

スペースまたは区切り記号のない 13 桁の数字

## <a name="pattern"></a>パターン

13 桁の数字:

- 11 桁の数字
- 2 つのチェック 数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_luxemburg_eu_tax_file_number` がパターンに一致するコンテンツを検出した。
- `Keywords_luxemburg_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_luxemburg_eu_tax_file_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid#
- id personnelle
- idpersonnelle#
- idpersonnelle
- 個々のコード
- 個々の ID
- 個人識別
- 個々の ID
- numéro d'identification personnel
- 個人用 ID
- 個人識別
- 個人 ID
- personalidno#
- personalidnumber#
- persönliche identifikationsnummer
- 一意の ID
- 一意の ID
- uniqueidkey#