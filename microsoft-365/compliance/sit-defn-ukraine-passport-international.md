---
title: ウクライナパスポートの国際エンティティ定義
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
description: ウクライナパスポートの国際機密情報の種類エンティティ定義。
ms.openlocfilehash: a383fea21990437199287f3e212debe8530d1521
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67370191"
---
# <a name="ukraine-passport-international"></a>ウクライナのパスポート国際番号

## <a name="format"></a>フォーマット

8 文字の英数字パターン

## <a name="pattern"></a>パターン

8 文字の英数字パターン:

- 2 つの文字または数字
- 6 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_Ukraine_Passport_International` は、パターンに一致するコンテンツを検索します。
- `Keyword_Ukraine_Passport_International` のキーワードを検出した。

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- ウクライナのパスポート
- passport number
- passport no
- паспорт України
- номер паспорта
