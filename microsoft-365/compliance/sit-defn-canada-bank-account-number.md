---
title: カナダの銀行口座番号エンティティ定義
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
description: カナダの銀行口座番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: c7008b17ff532a55dfefc079a07fc8e95f789b04
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996672"
---
# <a name="canada-bank-account-number"></a>カナダの銀行口座番号

## <a name="format"></a>フォーマット

7 または 12 桁

## <a name="pattern"></a>パターン

カナダ銀行口座番号は 7 桁または 12 桁です。

カナダの銀行口座転送番号は次のとおりです。

- 5 桁
- ハイフン
- 3 桁の OR
- ゼロ "0"
- 8 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_canada_bank_account_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_canada_bank_account_number` のキーワードを検出した。
- 正規表現 `Regex_canada_bank_account_transit_number` は、パターンに一致するコンテンツを検索します。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_canada_bank_account_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_canada_bank_account_number` のキーワードを検出した。

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit