---
title: オーストラリアのパスポート番号エンティティ定義
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
description: オーストラリアのパスポート番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 9f879dc2f071398f7c3ba49b7fcded8be220e07b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996147"
---
# <a name="australia-passport-number"></a>オーストラリアのパスポート番号

## <a name="format"></a>フォーマット

8 文字または 9 文字の英数字

## <a name="pattern"></a>パターン

- 1 文字 (N、E、D、F、A、C、U、X) の後に 7 桁または
- 2 文字 (PA、PB、PC、PD、PE、PF、PU、PW、PX、PZ) の後に 7 桁の数字が続きます。

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_australia_passport_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_australia_passport_number` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 正規表現 `Regex_australia_passport_number` は、パターンに一致するコンテンツを検索します。

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

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
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority