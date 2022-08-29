---
title: ニュージーランドのソーシャル ウェルフェア番号エンティティ定義
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
description: ニュージーランドのソーシャル ウェルフェア番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 2bb68114bf2c6a175827f7ac33b48b8c1f240ba3
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368501"
---
# <a name="new-zealand-social-welfare-number"></a>ニュージーランドの社会福祉番号

## <a name="format"></a>フォーマット

9 桁

## <a name="pattern"></a>パターン

9 桁

- 3 桁の数字
- オプションのハイフン
- 3 桁の数字
- オプションのハイフン
- 3 桁の数字

## <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_newzealand_social_welfare_number` がパターンに一致するコンテンツを検出した。
- `Keywords_newzealand_social_welfare_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、低い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_newzealand_social_welfare_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- ソーシャル ウェルフェア#
- ソーシャル ウェルフェア#
- ソーシャル ウェルフェア No.
- 社会保障番号
- swn#