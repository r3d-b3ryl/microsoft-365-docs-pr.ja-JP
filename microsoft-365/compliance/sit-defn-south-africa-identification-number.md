---
title: 南アフリカ識別番号エンティティ定義
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
description: 南アフリカ識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 95fbf2baa8842f1654881d0435a0328b5593242a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996627"
---
# <a name="south-africa-identification-number"></a>南アフリカの識別番号

### <a name="format"></a>フォーマット

省略可能なスペースを含む 13 桁の数字

## <a name="pattern"></a>パターン

13 桁の数字:

- YYMMDD 形式の 6 桁 (生年月日)
- 4 桁
- 1 桁の市民権インジケーター
- 数字 "8" または "9"
- 1 桁(チェックサム の数字)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_south_africa_identification_number` がパターンに一致するコンテンツを検出した。
- `Keyword_south_africa_identification_number` のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- 識別