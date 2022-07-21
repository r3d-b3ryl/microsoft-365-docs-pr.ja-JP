---
title: 米国社会保障番号 (SSN) エンティティ定義
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
description: 米国社会保障番号 (SSN) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 2644ff5be51d8316007d20ec3c8918ce0e2003c1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950555"
---
# <a name="us-social-security-number-ssn"></a>米国の社会保障番号 (SSN)

## <a name="format"></a>フォーマット

9 桁(書式設定または書式設定されていないパターンの場合があります)

> [!NOTE]
> 2011 年半ばより前に発行された場合、SSN には強力な書式設定があり、数値の特定の部分が有効な特定の範囲内に収まる必要があります (ただし、チェックサムはありません)。

## <a name="pattern"></a>パターン

4 つの関数は、4 つの異なるパターンで SAN を探します。

- `Func_ssn` ダッシュまたはスペース (ddd-dddd OR ddd dddd) で書式設定された 2011 年より前の強力な書式設定を持つ SSN を検索します。
- `Func_unformatted_ssn` 2011 より前の強力な書式を持つ SSN を検索します。これは、連続する 9 桁 (ddddddddd) として書式設定されていません。
- `Func_randomized_formatted_ssn` ダッシュまたはスペース (ddd-dd-dddd OR ddd dddd) で書式設定された 2011 年以降の SSN を検索します。
- `Func_randomized_unformatted_ssn` 9 桁の連続した数字 (ddddddddddd) として書式設定されていない 2011 年後の SSD を検索します。

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- この関数 `Func_ssn` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ssn` 見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- この関数 `Func_unformatted_ssn` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ssn` 見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_randomized_formatted_ssn` または `Func_randomized_unformatted_ssn` パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ssn` 見つかりました。

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_ssn"></a>Keyword_ssn

- SSA 番号
- social security number
- 社会保障#
- 社会保障#
- 社会保障なし
- Social Security#
- Soc Sec
- SSN
- SSN
- SSN#
- SS#
- SSID