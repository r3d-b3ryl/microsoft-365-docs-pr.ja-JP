---
title: ハンガリー社会保障番号 (TAJ) エンティティ定義
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
description: ハンガリー社会保障番号 (TAJ) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 52821cda4b997567a66e2527653ed0a1341a378e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997042"
---
# <a name="hungary-social-security-number-taj"></a>ハンガリーの社会保障番号 (TAJ)

## <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

## <a name="pattern"></a>パターン

9 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_hungary_eu_ssn_or_equivalent` がパターンに一致するコンテンツを検出した。
- `Keywords_hungary_eu_ssn_or_equivalent` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_hungary_eu_ssn_or_equivalent` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- ハンガリーの社会保障番号
- social security number
- socialsecuritynumber#
- hssn#
- socialsecuritynno
- hssn
- タージ
- タージ#
- Ssn
- Ssn#
- 社会保障なし
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám