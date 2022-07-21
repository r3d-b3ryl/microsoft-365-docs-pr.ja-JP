---
title: オーストリア付加価値税エンティティ定義
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
description: オーストリアの付加価値税の機密情報の種類エンティティ定義。
ms.openlocfilehash: b4d6841e857d81c42255eec1184e51623f78059f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950684"
---
# <a name="austria-value-added-tax"></a>オーストリア付加価値税

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

11 文字の英数字パターン

## <a name="pattern"></a>パターン

11 文字の英数字パターン:

- A または a
- T または t
- 省略可能な領域
- U または u
- 省略可能な領域
- 2 桁または 3 桁
- 省略可能な領域
- 4 桁
- 省略可能な領域
- 1 桁または 2 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- この関数Func_Austria_Value_Added_Tax、パターンに一致するコンテンツを検索します。
- Keyword_Austria_Value_Added_Taxのキーワードが見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- この関数Func_Austria_Value_Added_Tax、パターンに一致するコンテンツを検索します。

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>キーワード

### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- vat 番号
- Vat#
- オーストリアの vat 番号
- vat no.
- vatno#
- 付加価値税番号
- オーストリアの vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- vat 識別番号
- atu 番号
- uid 番号