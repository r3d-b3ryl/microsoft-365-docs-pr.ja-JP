---
title: カナダの社会保険番号エンティティ定義
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
description: カナダの社会保険番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 9af5cc026da5ac6bd414ebd80ded934efb90effb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996712"
---
# <a name="canada-social-insurance-number"></a>カナダの社会保険番号

## <a name="format"></a>フォーマット

オプションのハイフンまたはスペースを含む 9 桁の数字

## <a name="pattern"></a>パターン

フォーマット：

- 3 桁
- ハイフンまたはスペース
- 3 桁
- ハイフンまたはスペース
- 3 桁

書式なし: 9 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。
- 次のパターンのうち少なくとも 2 つ:
    - `Keyword_sin` のキーワードを検出した。
    - `Keyword_sin_collaborative` のキーワードを検出した。
    - 関数 `Func_eu_date` は、適切な日付形式で日付を検索します。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。
- `Keyword_sin` のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_sin"></a>Keyword_sin

- sin
- social insurance
- numero d'assurance sociale
- 罪
- Ssn
- Ssn
- social security
- numero d'assurance social
- national identification number
- national id
- 罪#
- soc ins
- social ins

### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license
- drivers license
- driver's licence
- drivers licence
- DOB
- 誕生日
- Birthday
- Date of Birth