---
title: クロアチア ID カード番号エンティティ定義
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
description: クロアチア ID カード番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: c1a281af470557623e649f29c98594992848779d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997137"
---
# <a name="croatia-identity-card-number"></a>クロアチアの身分証明書番号

このエンティティは、EU 国民識別番号の機密情報の種類に含まれています。 スタンドアロンの機密情報の種類エンティティとして使用できます。

## <a name="format"></a>フォーマット

9 桁

## <a name="pattern"></a>パターン

9 桁の連続する数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_croatia_id_card` がパターンに一致するコンテンツを検出した。
- `Keyword_croatia_id_card` のキーワードを検出した。

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- マスター市民番号
- nacionalni identifikacijski broj
- national identification number
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 暗証番号
- クレッチニ broj
- クレッチニ identifikacijski broj
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