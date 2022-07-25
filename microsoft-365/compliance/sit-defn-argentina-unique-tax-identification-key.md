---
title: アルゼンチン固有の税識別キー (CUIT/CUIL) エンティティ定義
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
description: アルゼンチン固有の税識別キー (CUIT/CUIL) の機密情報の種類エンティティ定義。
ms.openlocfilehash: d38cb0a972add240087c816399abf30d3d9ef670
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996977"
---
# <a name="argentina-unique-tax-identification-key-cuitcuil"></a>アルゼンチン固有の税識別キー (CUIT/CUIL)

## <a name="format"></a>フォーマット

ダッシュ付き 11 桁

## <a name="pattern"></a>パターン

ダッシュを含む 11 桁の数字:

- 20、23、24、27、30、33、または 34 の 2 桁の数字
- ハイフン (-)
- 8 桁
- ハイフン (-)
- 1 つのチェック ディジット

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_Argentina_Unique_Tax_Key` がパターンに一致するコンテンツを検出した。
- `Keyword_Argentina_Unique_Tax_Key` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_Argentina_Unique_Tax_Key` がパターンに一致するコンテンツを検出した。

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- 労働識別の一意のコード
- Clave Única de Identificación Tributaria
- 一意の労働識別コード
- CUIL
- 一意の税識別キー
- 一意の労働識別キー
- 労働識別の一意のキー
- 一意の作業識別コード
- 一意の作業コード識別
- 一意の作業識別キー
- 作業識別の一意のキー
- 税識別の一意のコード
- 税識別の一意のキー
- 一意の労働識別コード
- 一意の労働コード識別
- 一意の労働識別キー
- 労働識別の一意のキー
- tax ID
- taxID#
- taxId
- taxidnumber
- 税番号
- tax no
- 税#
- 税#
- 納税者 ID
- 納税者番号
- taxpayer no
- 納税 者#
- 納税 者#
- tax identity
- tax identification
- Número de Identificación Fiscal
- número de contribuyente