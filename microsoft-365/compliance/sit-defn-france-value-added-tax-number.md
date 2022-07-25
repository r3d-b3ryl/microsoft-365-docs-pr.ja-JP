---
title: フランスの付加価値税番号エンティティ定義
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
description: フランスの付加価値税番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 782030e563b59540b721ecfd40ee7470a2aaaa87
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996642"
---
# <a name="france-value-added-tax-number"></a>フランスの付加価値税番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

13 文字の英数字パターン

## <a name="pattern"></a>パターン

13 文字の英数字パターン:

- 2 文字 - FR (大文字と小文字を区別しない)
- 省略可能なスペースまたはハイフン
- 2 つの文字または数字
- 省略可能なスペース、ドット、ハイフン、またはコンマ
- 3 桁
- 省略可能なスペース、ドット、ハイフン、またはコンマ
- 3 桁
- 省略可能なスペース、ドット、ハイフン、またはコンマ
- 3 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_france_value_added_tax_number` がパターンに一致するコンテンツを検出した。
- `Keywords_france_value_added_tax_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_france_value_added_tax_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>キーワード

### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- vat 番号
- vat no
- Vat#
- 付加価値税
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur atétée
- taxe sur la valeur atétée
- n° tva
- numéro de tva
- numéro d'identification siren