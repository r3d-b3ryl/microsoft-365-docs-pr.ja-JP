---
title: ギリシャの国民 ID カード エンティティ定義
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
description: ギリシャの国民 ID カードの機密情報の種類エンティティ定義。
ms.openlocfilehash: 731adcfee8c2464bd45e9324e8305a4cc813d7eb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995467"
---
# <a name="greece-national-id-card"></a>ギリシャの国民識別カード

## <a name="format"></a>フォーマット

7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ

## <a name="pattern"></a>パターン

7 桁の文字と数字 (従来の形式):

- 1 桁の文字 (ギリシャ語のアルファベット文字) 
- ハイフン 1 つ 
- 6 桁の数字

8 桁の文字と数字 (現在の形式):

- ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 
- ハイフン 1 つ 
- 6 桁の数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_greece_id_card` は、パターンに一致するコンテンツを検索します。
- `Keyword_greece_id_card` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 正規表現 `Regex_greece_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- ギリシャ語 ID
- ギリシャ語の国民 ID
- ギリシャ語の個人 ID カード
- ギリシャのポリシー ID
- Identity card
- Tautotita
- ταυτότητα
- ταυτότητας