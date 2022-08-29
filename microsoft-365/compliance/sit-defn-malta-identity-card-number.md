---
title: マルタ ID カード番号エンティティ定義
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
description: マルタ ID カード番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 1ce156644ad4b9625a6eb1257ba54534e2d2bab0
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368077"
---
# <a name="malta-identity-card-number"></a>マルタの身分証明書番号

## <a name="format"></a>フォーマット

7 桁の数字の後に 1 文字が続く

## <a name="pattern"></a>パターン

7 桁の数字の後に 1 文字が続きます。

- 7 桁
- "M、G、A、P、L、H、B、Z" の 1 文字 (大文字と小文字を区別しない)

## <a name="checksum"></a>チェックサム

対象外

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_malta_eu_national_id_card` がパターンに一致するコンテンツを検出した。
- `Keywords_malta_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、低い信頼度でそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_malta_eu_national_id_card` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- 市民サービス番号
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人用数値コード
- 一意の識別番号
- 一意の ID 番号
- uniqueidentityno#