---
title: ポーランドのパスポート番号エンティティ定義
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
description: ポーランドのパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 910084a1c4a2c97256a2045e25ac436c248899fd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997442"
---
# <a name="poland-passport-number"></a>ポーランドのパスポート番号

この機密情報の種類エンティティは、EU Passport Number の機密情報の種類に含まれています。 スタンドアロンの機密情報の種類エンティティとしても使用できます。

## <a name="format"></a>フォーマット

2 文字と 7 桁の数字

## <a name="pattern"></a>パターン

2 文字 (大文字と小文字は区別されません) の後に 7 桁の数字が続く

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_polish_passport_number_v2` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keyword_polish_national_passport_number` つかりました。
- `Keywords_eu_passport_date` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_polish_passport_number_v2` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。
- キーワードが `Keywords_eu_passport_number` 見つかったか、見 `Keyword_polish_national_passport_number` つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_polish_passport_number_v2` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
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

### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszport方
- numery paszportowe
- nr paszportu
- Nr。 paszportu
- nr paszportで
- n° passeport
- passeport n°

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付