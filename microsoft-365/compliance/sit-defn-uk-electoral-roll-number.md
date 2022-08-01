---
title: 英国 electoral roll number entity definition
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
description: 英国 electoral roll number sensitive information type entity definition.
ms.openlocfilehash: d821878a155ec6c2393150265ddac1dc18fc5f10
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995692"
---
# <a name="uk-electoral-roll-number"></a>英国 選挙登録番号

## <a name="format"></a>フォーマット

2 文字の後に 1 ~ 4 桁の数字が続く

## <a name="pattern"></a>パターン

2 文字 (大文字と小文字は区別されません)、その後に 1 ~ 4 個の数字が続きます

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_uk_electoral` は、パターンに一致するコンテンツを検索します。
- `Keyword_uk_electoral` のキーワードを検出した。

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination
- nomination form
- electoral register
- electoral roll