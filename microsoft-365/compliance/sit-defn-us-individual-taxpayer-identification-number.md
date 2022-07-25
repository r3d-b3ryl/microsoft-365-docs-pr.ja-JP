---
title: 米国の個人納税者識別番号 (ITIN) エンティティ定義
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
description: 米国の個人納税者識別番号 (ITIN) の機密情報の種類エンティティ定義。
ms.openlocfilehash: c99635c29bb5b720ecc2d70577fe66d508ce9d9c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997327"
---
# <a name="us-individual-taxpayer-identification-number-itin"></a>米国の個人納税者識別番号 (ITIN)

## <a name="format"></a>フォーマット

"9" で始まり、4 桁目として "7" または "8" を含む 9 桁 (必要に応じてスペースまたはダッシュで書式設定)

## <a name="pattern"></a>パターン

フォーマット：

- 数字 "9"
- 2 桁の数字
- スペースまたはダッシュ
- "7" または "8"
- 数字
- スペース、またはダッシュ
- 4 桁

未フォーマット：

- 数字 "9"
- 2 桁の数字
- "7" または "8"
- 5 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_formatted_itin` がパターンに一致するコンテンツを検出した。
- `Keyword_itin` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_unformatted_itin` がパターンに一致するコンテンツを検出した。
- `Keyword_itin` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_formatted_itin` または `Func_unformatted_itin` パターンに一致するコンテンツを検索します。

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_itin"></a>Keyword_itin

- 納税 者
- tax id
- tax identification
- itin
- i.t.i.n.
- Ssn
- 錫
- social security
- tax payer
- itins
- taxid
- individual taxpayer