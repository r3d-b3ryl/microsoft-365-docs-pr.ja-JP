---
title: オーストラリアのビジネス番号エンティティ定義
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
description: オーストラリアのビジネス番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 656dbc0315b0b7b09b112bdd7e423bcdec64a165
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368479"
---
# <a name="australia-business-number"></a>オーストラリアの事業者番号

## <a name="format"></a>フォーマット

省略可能な区切り記号を含む 11 桁の数字

## <a name="pattern"></a>パターン

省略可能な区切り記号を含む 11 桁:

- 2 桁の数字
- オプションのハイフンまたはスペース
- 3 桁の数字
- オプションのハイフンまたはスペース
- 3 桁の数字
- オプションのハイフンまたはスペース
- 3 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- この関数Func_australian_business_number、パターンに一致するコンテンツを検索します。
- Keywords_australian_business_numberのキーワードが見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- この関数Func_australian_business_number、パターンに一致するコンテンツを検索します。

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>キーワード

### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- オーストラリアのビジネスなし
- 勤務先番号
- Abn#
- businessid#
- ビジネス ID
- Abn
- businessno#