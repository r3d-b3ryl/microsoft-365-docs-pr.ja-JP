---
title: イスラエルの銀行口座番号エンティティ定義
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
description: イスラエルの銀行口座番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: a68f90cd92432778d89d3f8494522a5ab2822d07
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997607"
---
# <a name="israel-bank-account-number"></a>イスラエルの銀行口座番号

## <a name="format"></a>フォーマット

13 桁の数字

## <a name="pattern"></a>パターン

フォーマット：

- 2 桁の数字
- ダッシュ
- 3 桁
- ダッシュ
- 8 桁

未フォーマット：

- 	13 桁の連続する数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_israel_bank_account_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_israel_bank_account_number` のキーワードを検出した。

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number
- Bank Account
- Account Number
- מספר חשבון בנק