---
title: オランダのパスポート番号エンティティ定義
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
description: オランダのパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 3766db12bbef6576f7bfb5d81b23fe3745bf4aa5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996662"
---
# <a name="netherlands-passport-number"></a>オランダのパスポート番号

## <a name="format"></a>フォーマット

スペースまたは区切り記号のない 9 文字または数字

## <a name="pattern"></a>パターン

9 文字または数字

## <a name="checksum"></a>チェックサム

該当なし

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_netherlands_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_netherlands_eu_passport_number` つかりました。
- 正規表現 `Regex_netherlands_eu_passport_date` は、DD MMM/MMM YYYY 形式の日付を検索します (例 - 26 MAA/MAR 2012)

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_netherlands_eu_passport_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keywords_netherlands_eu_passport_number` つかりました。

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
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

### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr