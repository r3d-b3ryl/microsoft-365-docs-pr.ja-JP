---
title: Luxemburg passport number entity definition
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
description: Luxemburg passport number sensitive information type entity definition.
ms.openlocfilehash: dc7fc8c7e54f265e7c6f1584dafedd2ea61418b7
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996842"
---
# <a name="luxemburg-passport-number"></a>ルクセンブルクのパスポート番号

## <a name="format"></a>フォーマット

スペースまたは区切り記号のない 8 桁の数字または文字

## <a name="pattern"></a>パターン

8 桁の数字または文字 (大文字と小文字は区別されません)

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_luxemburg_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_luxemburg_eu_passport_number` つかりました。
- 正規表現 `Regex_eu_passport_date3` が DD MM YYYY 形式で日付を検索するか、キーワード `Keywords_eu_passport_date` が見つかりました

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_luxemburg_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_luxemburg_eu_passport_number` つかりました。

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
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

### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- ルクセンブルク パス
- ルクセンブルク passeport
- ルクセンブルクのパスポート
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- nr を渡す
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付