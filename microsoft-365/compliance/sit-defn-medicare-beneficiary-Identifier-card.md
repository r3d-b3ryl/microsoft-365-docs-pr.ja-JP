---
title: Medicare の受益者識別子 (MBI) カード エンティティ定義
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
description: Medicare の受益者識別子 (MBI) カードの機密情報の種類エンティティ定義。
ms.openlocfilehash: 601c34adcb0f9b19ab2c23a3df7d1c574cdd5031
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950828"
---
# <a name="medicare-beneficiary-identifier-mbi-card"></a>Medicare の受益者識別子 (MBI) カード

## <a name="format"></a>フォーマット

11 文字の英数字パターン

## <a name="pattern"></a>パターン

- 1 から 9 までの 1 桁
- S、L、O、I、B、Z を除く 1 文字
- S、L、O、I、B、Z を除く 1 桁または 1 文字
- 1 桁
- オプションのハイフン
- S、L、O、I、B、Z を除く 1 文字
- S、L、O、I、B、Z を除く 1 桁または 1 文字
- 1 桁
- オプションのハイフン
- S、L、O、I、B、Z を除く 2 文字
- 2 桁の数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_mbi_card` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_mbi_card` 見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- 正規表現 `Regex_mbi_card` は、パターンに一致するコンテンツを検索します。

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi#
- medicare の受益者#
- medicare の受益者識別子
- medicare の受益者なし
- medicare の受益者番号
- medicare の受益者#