---
title: アイルランドのパスポート番号エンティティ定義
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
description: アイルランドのパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 5924b689096896e6d09cecca0c022c05972dedef
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996917"
---
# <a name="ireland-passport-number"></a>アイルランドのパスポート番号

## <a name="format"></a>フォーマット

2 文字または数字の後に 7 桁の数字 (スペースまたは区切り記号なし)

### <a name="pattern"></a>パターン

2 文字または数字の後に 7 桁の数字が続きます。

- 2 桁の数字または文字 (大文字と小文字は区別されません)
- 7 桁の数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_ireland_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_ireland_eu_passport_number` つかりました。
- 正規表現 `Regex_ireland_eu_passport_date` は、DD MMM/MMM YYYY (例 - 01 BEA/MAY 1988) 形式で日付を検索するか、キーワード `Keywords_eu_passport_date` が見つかりました

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_ireland_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_ireland_eu_passport_number` つかりました。

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

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

### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhirphas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付