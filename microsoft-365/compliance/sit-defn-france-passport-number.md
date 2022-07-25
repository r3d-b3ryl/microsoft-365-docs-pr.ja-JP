---
title: フランスのパスポート番号エンティティ定義
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
description: フランスのパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: f358edd8955b17e89354af536381327957eb38bc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997532"
---
# <a name="france-passport-number"></a>フランスのパスポート番号

このエンティティは、EU Passport Number の機密情報の種類で使用できます。 スタンドアロンの機密情報の種類エンティティとしても使用できます。

## <a name="format"></a>フォーマット

9 桁の数字と文字

## <a name="pattern"></a>パターン

9 桁の数字と文字:

- 2 桁の数字
- 2 文字 (大文字と小文字は区別されません)
- 5 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_fr_passport` がパターンに一致するコンテンツを検出した。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_france_eu_passport_number` つかりました。
- 正規表現 `Regex_eu_passport_date3` が DD MM YYYY 形式で日付を検索するか、キーワード `Keywords_eu_passport_date` が見つかりました

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_fr_passport` がパターンに一致するコンテンツを検出した。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_france_eu_passport_number` つかりました。

```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport#
- passeport#
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport のデカルト
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付