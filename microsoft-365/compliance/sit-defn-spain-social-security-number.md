---
title: スペイン社会保障番号 (SSN) エンティティ定義
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
description: スペインの社会保障番号 (SSN) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 4a531f0548aba2caa330423d493cf8e524c4ed73
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996787"
---
# <a name="spain-social-security-number-ssn"></a>スペインの社会保障番号 (SSN)

## <a name="format"></a>フォーマット

11 ～ 12 桁の数字

## <a name="pattern"></a>パターン

11 ~ 12 桁:

- 2 桁の数字
- スラッシュ (省略可能)
- 7 ~ 8 桁
- スラッシュ (省略可能)
- 2 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_spanish_social_security_number` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。
    - `Keywords_spain_eu_ssn_or_equivalent` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_spanish_social_security_number` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- Ssn
- Ssn#
- socialsecurityno
- 社会保障なし
- social security number
- número de la seguridad social