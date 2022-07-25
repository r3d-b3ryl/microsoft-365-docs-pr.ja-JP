---
title: 日本の居住カード番号エンティティ定義
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
description: 日本の居住カード番号の機密情報の種類のエンティティ定義。
ms.openlocfilehash: 512a20f00dd2ff77d2f88950d83b227a717c309e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997387"
---
# <a name="japan-residence-card-number"></a>日本の在留カード番号

## <a name="format"></a>フォーマット

12 文字と数字

## <a name="pattern"></a>パターン

12 文字と数字:

- 2 文字 (大文字と小文字は区別されません)
- 8 桁
- 2 文字 (大文字と小文字は区別されません)

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_jp_residence_card_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_jp_residence_card_number` のキーワードを検出した。

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- 居住カード番号
- 居住カードなし
- 居住カード#
- 在留カード番号
- 在留カード
- 在留番号