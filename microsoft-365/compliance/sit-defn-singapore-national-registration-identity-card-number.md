---
title: シンガポール国登録 ID カード (NRIC) 番号エンティティ定義
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
description: シンガポール国内登録 ID カード (NRIC) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: b2dfa68f3d69134f7d4eca67648c64075b5d1c44
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996397"
---
# <a name="singapore-national-registration-identity-card-nric-number"></a>シンガポールの国民登録 ID カード (NRIC) 番号

## <a name="format"></a>フォーマット

9 文字と数字

## <a name="pattern"></a>パターン

- 9 文字と数字:

- 文字 "F"、"G"、"M"、"S"、または "T" (大文字と小文字は区別されません)
- 7 桁
- アルファベットチェックの数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_singapore_nric` は、パターンに一致するコンテンツを検索します。
- `Keyword_singapore_nric` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_singapore_nric` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card
- Identity Card Number
- NRIC
- IC
- Foreign Identification Number
- フィン
- 身份证
- 身份證