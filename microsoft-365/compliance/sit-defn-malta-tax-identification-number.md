---
title: マルタの税識別番号エンティティ定義
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
description: マルタの税識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 5f77f6755ff69bf200a3999e684901bf39bdf6d9
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996222"
---
# <a name="malta-tax-identification-number"></a>マルタの納税者番号

## <a name="format"></a>フォーマット

モルテ語の国民の場合:

- 指定したパターンの 7 桁の数字と 1 文字

非モルテ語の国民およびモルテ語エンティティ:

- 9 桁

## <a name="pattern"></a>パターン

マルタ国民: 7 桁と 1 文字

- 7 桁
- 1 文字 (大文字と小文字は区別されません)

非モルテ語の国民とモルテ語エンティティ: 9 桁

- 9 桁

## <a name="checksum"></a>チェックサム

該当なし

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_malta_eu_tax_file_number`  または `Regex_malta_eu_tax_file_number_non_maltese_national` パターンに一致するコンテンツを検索します。
- `Keywords_malta_eu_tax_file_number` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 正規表現 `Regex_malta_eu_tax_file_number` または `Regex_malta_eu_tax_file_number_non_maltese_national` パターンに一致するコンテンツを検索します。

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- 市民サービス番号
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人用数値コード
- tax id
- 税の識別番号なし
- 税識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin ID
- tin no
- 錫#
- 一意の識別番号
- 一意の ID 番号
- uniqueidentityno#