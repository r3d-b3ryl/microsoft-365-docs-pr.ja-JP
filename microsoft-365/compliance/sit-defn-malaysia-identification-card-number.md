---
title: マレーシア ID カード番号エンティティ定義
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
description: マレーシア識別カード番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: ed233a9aa91c1c178644c4468271ee6839c55268
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996832"
---
# <a name="malaysia-identification-card-number"></a>マレーシアの識別カード番号

## <a name="format"></a>フォーマット

省略可能なハイフンを含む 12 桁の数字

## <a name="pattern"></a>パターン

12 桁の数字:

- YYMMDD 形式の 6 桁 (生年月日)
- ダッシュ (省略可能)
- 2 文字の出先コード
- ダッシュ (省略可能)
- ランダムな 3 桁の数字
- 1 桁の性別コード

## <a name="checksum"></a>チェックサム

不要

### <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_malaysia_id_card_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_malaysia_id_card_number` のキーワードを検出した。

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- デジタル アプリケーション カード
- i/c
- i/c no
- Ic
- ic no
- id card
- ID カード
- Identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan マレーシア
- Kp
- kp no
- Mykad
- mykas
- mykid
- mypr
- mytentera
- マレーシア ID カード
- マレーシアの ID カード
- nric
- 個人識別カード