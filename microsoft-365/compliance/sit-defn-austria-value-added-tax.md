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
ms.openlocfilehash: 9ed66fd971857afad9cf5047643f60e58eb2e7f2
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368036"
---
# <a name="austria-value-added-tax"></a>オーストリアの付加価値税

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
- 4 桁の数字
- 省略可能な領域
- 1 桁または 2 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- この関数Func_Austria_Value_Added_Tax、パターンに一致するコンテンツを検索します。
- Keyword_Austria_Value_Added_Taxのキーワードが見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

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