---
title: フィンランドのヨーロッパの医療保険番号エンティティ定義
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
description: フィンランドのヨーロッパの医療保険番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 799f664f03f91fa35c01cc87701046faddab5dde
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367381"
---
# <a name="finland-european-health-insurance-number"></a>フィンランドの欧州健康保険番号

## <a name="format"></a>フォーマット

20 桁の数字

## <a name="pattern"></a>パターン

20 桁の数字:

- 10 桁 - 8024680246
- 省略可能なスペースまたはハイフン
- 10 桁の数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_Finland_European_Health_Insurance_Number` は、パターンに一致するコンテンツを検索します。
- `Keyword_Finland_European_Health_Insurance_Number` のキーワードを検出した。

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- Ehic#
- Ehic
- finlandehicnumber#
- fizk sjukförsäkkingskort
- 正常性カード
- 健康保険証
- 医療保険番号
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkkingskort
- suomen sairausvakuutuskortti
- terveyskortti
