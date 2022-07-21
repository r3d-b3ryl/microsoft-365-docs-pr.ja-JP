---
title: ポルトガル市民カード番号エンティティ定義
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
description: ポルトガル市民カード番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 95aa6f824de748dfc513ef5d509b6ae5e1c58119
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950700"
---
# <a name="portugal-citizen-card-number"></a>ポルトガル市民カード番号

## <a name="format"></a>フォーマット

8 桁

## <a name="pattern"></a>パターン

8 桁

## <a name="checksum"></a>チェックサム

いいえ

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_portugal_citizen_card` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_portugal_citizen_card` 見つかりました。

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- 市民カード
- ドキュメント番号
- documento de identificação
- id 番号
- id no
- identification number
- ID カードなし
- ID カード番号
- 国民 ID カード
- Nic
- número bi de ポルトガル
- número de identificação civil
- número de identificação fiscal
- número do documento
- ポルトガル bi 番号