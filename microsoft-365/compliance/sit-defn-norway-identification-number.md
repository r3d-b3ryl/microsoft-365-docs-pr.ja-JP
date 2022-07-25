---
title: ノルウェー ID 番号エンティティ定義
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
description: ノルウェー識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 9edce24b1fef475ce30b50d3703214d4388a1338
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997492"
---
# <a name="norway-identification-number"></a>ノルウェーの識別番号

## <a name="format"></a>フォーマット

11 桁の数字

## <a name="pattern"></a>パターン

11 桁の数字:

- DDMMYY 形式の 6 桁 (生年月日)
- 3 桁の個人番号
- 2 つのチェック 数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_norway_id_number` がパターンに一致するコンテンツを検出した。
- `Keyword_norway_id_number` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_norway_id_number` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- 識別
- Personnummer
- Fødselsnummer