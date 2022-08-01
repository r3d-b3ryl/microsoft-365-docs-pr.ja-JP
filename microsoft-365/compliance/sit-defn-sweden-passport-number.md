---
title: スウェーデンのパスポート番号エンティティ定義
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
description: スウェーデンのパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 497965aea803a162fc97bb64fa456191f8788aab
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995417"
---
# <a name="sweden-passport-number"></a>スウェーデンのパスポート番号

## <a name="format"></a>フォーマット

8 桁

## <a name="pattern"></a>パターン

8 桁の連続する数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現Regex_sweden_passport_numberは、パターンに一致するコンテンツを検索します。
- キーワードが見`Keywords_eu_passport_number``Keyword_sweden_passport`つかりました。
- 正規表現 `Regex_sweden_eu_passport_date` が DD MMM/MMM YY (01 JAN/JAN 12) 形式の日付を検索するか、キーワード `Keywords_eu_passport_date` が見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現Regex_sweden_passport_numberは、パターンに一致するコンテンツを検索します。
- キーワードが見`Keywords_eu_passport_number``Keyword_sweden_passport`つかりました。

```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
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

### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- 異星人登録カード
- g3 処理料金
- 複数のエントリ
- Numéro de passeport
- passeport n °
- passeport non
- passeport#
- passeport#
- passeportnon
- passeportn °
- passnummer
- nr を渡す
- シェンゲンビザ
- schengen のビザ
- 1 つのエントリ
- sverige pass
- visa requirements
- visa の処理
- visa の種類

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付