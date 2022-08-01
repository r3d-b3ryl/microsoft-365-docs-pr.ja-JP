---
title: 英国 国民健康サービス番号エンティティ定義
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
description: 英国 national health service number sensitive information type entity definition.
ms.openlocfilehash: d636be281b1652934fa7b4b83b3a4b5da7794a09
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995687"
---
# <a name="uk-national-health-service-number"></a>英国 国民保健サービス番号

## <a name="format"></a>フォーマット

スペースで区切られた 10 ～ 17 桁の数字

## <a name="pattern"></a>パターン

10 ～ 17 桁の数字:

- 3 桁または 10 桁
- スペース
- 3 桁
- スペース
- 4 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_uk_nhs_number` がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - `Keyword_uk_nhs_number` のキーワードを検出した。
    - `Keyword_uk_nhs_number1` のキーワードを検出した。
    - `Keyword_uk_nhs_number_dob` のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service
- Nhs
- health services authority
- health authority

### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id
- patient identification
- patient no
- patient number

### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP
- DOB
- D.O.B
- Date of Birth
- Birth Date