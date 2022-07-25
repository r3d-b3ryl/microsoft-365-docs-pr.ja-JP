---
title: ドイツ ID カード番号エンティティ定義
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
description: ドイツ ID カード番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 961dec17e4f68a1650cd0c4360ccf5244bef0062
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996252"
---
# <a name="germany-identity-card-number"></a>ドイツの身分証明書番号

## <a name="format"></a>フォーマット

2010 年 11 月 1 日以降: 9 文字から 11 文字、数字

1987 年 4 月 1 日から 2010 年 10 月 31 日まで: 10 桁

## <a name="pattern"></a>パターン

2010 年 11 月 1 日以降: 9 ~ 11 文字の英数字パターン
- 1 つの L、M、N、P、R、T、V、W、X、Y (大文字と小文字を区別しない)
- C、F、G、H、J、K、L、M、N、P、R、T、V、W、X、Y、Z の 8 桁または文字 (大文字と小文字は区別されません)
- オプションのチェック 桁
- 省略可能な d/D

1987 年 4 月 1 日から 2010 年 10 月 31 日まで:

- 10 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_german_id_card_with_check` がパターンに一致するコンテンツを検出した。
- `Keyword_germany_id_card` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_germany_id_card` は、パターンに一致するコンテンツを検索します (2010 より前に発行されたチェック 桁のない 9 文字、または 10 桁のパターンが発行された posy 2010)。
- `Keyword_germany_id_card` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_german_id_card_with_check` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
      <!-- Germany Identity Card Number -->
      <Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
         <IdMatch idRef="Regex_germany_id_card" />
         <Match idRef="Keyword_germany_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.4545.000">
          <Pattern confidenceLevel="85">
           <IdMatch idRef="Func_german_id_card_with_check" />
            <Match idRef="Keyword_germany_id_card" />
          </Pattern>
          <Pattern confidenceLevel="65">
           <IdMatch idRef="Func_german_id_card_with_check" />
          </Pattern>
        </Version>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- 識別
- identifikation
- identifiziemissionsnummer
- Identity card
- ID 番号
- id-nummer
- 個人用 ID
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer