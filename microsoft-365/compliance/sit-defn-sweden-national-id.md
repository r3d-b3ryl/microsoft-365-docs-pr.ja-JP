---
title: スウェーデンの国民 ID エンティティ定義
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
description: スウェーデン国内 ID の機密情報の種類エンティティ定義。
ms.openlocfilehash: 77d0fd72a4293bdc8cae0aa806899b30baa21ed8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997317"
---
# <a name="sweden-national-id"></a>スウェーデンの国民 ID

## <a name="format"></a>フォーマット

10 桁または 12 桁の数字とオプションの区切り記号 1 つ

## <a name="pattern"></a>パターン

10 桁または 12 桁の数字と省略可能な区切り記号:

- 2 桁 (省略可能)
- YYMMDD という日付形式の 6 桁の数字
- 区切り記号 "-" または "+" (省略可能)
- 4 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_swedish_national_identifier` がパターンに一致するコンテンツを検出した。
- キーワードが `Keywords_swedish_national_identifier` 見つかりました
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_swedish_national_identifier` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id 番号
- Id#
- id no
- identification number
- identifikationsnumret#
- identifikationsnumret
- identitetshandling
- ID ドキュメント
- id no
- ID 番号
- id-nummer
- 個人用 ID
- personnummer#
- personnummer
- skatteidentifikationsnummer