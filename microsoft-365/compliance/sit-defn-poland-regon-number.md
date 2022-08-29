---
title: ポーランド REGON 番号エンティティ定義
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
description: ポーランド REGON 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 7dbdd18de1f00383b3731c4715f4aec8d3c869ad
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369013"
---
# <a name="poland-regon-number"></a>ポーランドの REGON 番号

## <a name="format"></a>フォーマット

9 桁または 14 桁の数字

## <a name="pattern"></a>パターン

9 桁または 14 桁の数字:

- 9 桁または
- 9 桁
- ハイフン
- 5 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_polish_regon_number` がパターンに一致するコンテンツを検出した。
- `Keywords_polish_regon_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、低い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_polish_regon_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- 統計番号
- 統計 ID
- 統計なし
- regon 番号
- regonid#
- regonno#
- 会社 ID
- companyid#
- companyidno#
- numer statystyczny
- numeru regon
- numerstatystyczny#
- numeruregon#