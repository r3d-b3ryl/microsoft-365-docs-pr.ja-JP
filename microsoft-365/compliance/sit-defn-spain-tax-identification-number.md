---
title: スペインの税識別番号エンティティ定義
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
description: スペインの税識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: de7075c6ff81c97537b9f7145fd269a671b8e1dc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997072"
---
# <a name="spain-tax-identification-number"></a>スペインの納税者番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

指定したパターンの 7 桁または 8 桁の数字と 1 文字または 2 文字

## <a name="pattern"></a>パターン

スペイン国民識別カードを持つスペインの自然人:

- 8 桁
- 大文字 1 文字 (大文字と小文字が区別されます)

スペイン国民証を持たない非居住者のスペイン人

- 大文字 "L" (大文字と小文字が区別されます)
- 7 桁
- 大文字 1 文字 (大文字と小文字が区別されます)

スペイン国民証を持たない 14 歳未満のスペイン居住者:

- 1 文字の大文字 "K" (大文字と小文字が区別されます)
- 7 桁
- 大文字 1 文字 (大文字と小文字が区別されます)

外国籍の方の識別番号

- "X"、"Y"、または "Z" である 1 つの大文字 (大文字と小文字が区別されます)
- 7 桁
- 大文字 1 文字 (大文字と小文字が区別されます)

外国籍の方の識別番号がない場合

- "M" である 1 文字の大文字 (大文字と小文字が区別されます)
- 7 桁
- 大文字 1 文字 (大文字と小文字が区別されます)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_spain_eu_tax_file_number` または `Func_spain_eu_DL_and_NI_number_citizen` パターンに一致するコンテンツを検索します。
- `Keywords_spain_eu_tax_file_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_spain_eu_tax_file_number` または `Func_spain_eu_DL_and_NI_number_citizen` パターンに一致するコンテンツを検索します。

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- Cif
- cifid#
- cifnúmero#
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid#
- spanishcifid
- spanishcifno#
- spanishcifno
- tax file no
- tax file number
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