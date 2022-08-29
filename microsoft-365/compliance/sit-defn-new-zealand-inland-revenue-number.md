---
title: ニュージーランド内陸部収益番号エンティティ定義
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
description: ニュージーランド内陸部収益番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 7df444660c59bd12526d979dd93d5313814083f3
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368063"
---
# <a name="new-zealand-inland-revenue-number"></a>ニュージーランドの内国歳入番号

## <a name="format"></a>フォーマット

省略可能な区切り記号を含む 8 桁または 9 桁

## <a name="pattern"></a>パターン

省略可能な区切り記号を含む 8 桁または 9 桁

- 2 桁または 3 桁
- 省略可能なスペースまたはハイフン
- 3 桁の数字
- 省略可能なスペースまたはハイフン
- 3 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_new_zealand_inland_revenue_number` がパターンに一致するコンテンツを検出した。
- `Keywords_new_zealand_inland_revenue_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_new_zealand_inland_revenue_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird no.
- ird no#
- nz ird
- ニュージーランド ird
- ird 番号
- 内陸部の収益番号