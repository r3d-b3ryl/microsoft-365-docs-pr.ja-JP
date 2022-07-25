---
title: ドイツのパスポート番号エンティティ定義
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
description: ドイツのパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 3e58ded04d1507903c890598a7f2c7d892ac45e7
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996707"
---
# <a name="germany-passport-number"></a>ドイツのパスポート番号

## <a name="format"></a>フォーマット

9 ~ 11 文字

## <a name="pattern"></a>パターン

- C、F、G、H、J、K の 1 文字 (大文字と小文字を区別しない)
- C、F、G、H、J、K、L、M、N、P、R、T、V、W、X、Y、Z の 8 桁または文字 (大文字と小文字は区別されません)
- オプションのチェック 桁
- 省略可能な d/D

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_german_passport_checksum` がパターンに一致するコンテンツを検出した。
- キーワードが `Keyword_german_passport` 見つかったか、見 `Keywords_eu_passport_number_common` つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- この関数 `Func_german_passport` は、9 文字パターンに一致するコンテンツを検索します (チェック ディジットと省略可能な d/D なし)。
- キーワードが `Keyword_german_passport` 見つかったか、見 `Keywords_eu_passport_number_common` つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_german_passport_checksum` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Version minEngineVersion="15.20.4570.0">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_german_passport_checksum" />
          <Any minMatches="1">
            <Match idRef="Keyword_german_passport" />
            <Match idRef="Keywords_eu_passport_number_common" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_german_passport_checksum" />
        </Pattern>
      </Version>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passeport no.
- passeport no

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