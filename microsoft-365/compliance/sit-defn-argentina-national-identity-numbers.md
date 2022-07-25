---
title: アルゼンチン国民 ID (DNI) 番号エンティティ定義
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
description: アルゼンチンの国民 ID (DNI) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: f7a74b4f92cc23acf4c71320c06455fffcff378f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997012"
---
# <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民識別 (DNI) 番号

## <a name="format"></a>フォーマット

ピリオドの有無にかかわらず 8 桁の数字

## <a name="pattern"></a>パターン

8 桁の数字:

- 2 桁の数字
- 省略可能な期間
- 3 桁
- 省略可能な期間
- 3 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現Regex_argentina_national_idは、パターンに一致するコンテンツを検索します。
- Keyword_argentina_national_idのキーワードが見つかりました。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number
- cedula
- cédula
- Dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp