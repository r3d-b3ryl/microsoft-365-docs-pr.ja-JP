---
title: ポルトガルのパスポート番号エンティティ定義
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
description: ポルトガルパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 523f6c74b3d7f2fed31caf2982f37cbfa4b4a006
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950676"
---
# <a name="portugal-passport-number"></a>ポルトガルのパスポート番号

## <a name="format"></a>フォーマット

1 文字の後に 6 桁の数字 (スペースまたは区切り記号なし)

## <a name="pattern"></a>パターン

1 文字の後に 6 桁の数字が続きます。

- 1 文字 (大文字と小文字は区別されません)
- 6 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_portugal_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_portugal_eu_passport_number` つかりました。
- 正規表現 `Regex_eu_passport_date1` が DD.MM.YYYY 形式で日付を検索するか、キーワード `Keywords_eu_passport_date` が見つかりました

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- 正規表現 `Regex_portugal_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_portugal_eu_passport_number` つかりました。

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
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

### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- ポルトガル語のパスポート
- ポルトガル語 passeport
- ポルトガル語 passaporte
- passaporte nº
- passeport nº
- números de passaporte
- ポルトガル語のパスポート
- número passaporte
- números passaporte

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付