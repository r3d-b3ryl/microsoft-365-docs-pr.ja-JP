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
ms.openlocfilehash: 5d3b238dc631086be26399e3adf6c4fa2ef0cf99
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995632"
---
# <a name="australia-business-number"></a>オーストラリアの事業者番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

省略可能な区切り記号を含む 11 桁の数字

## <a name="pattern"></a>パターン

省略可能な区切り記号を含む 11 桁:

- 2 桁の数字
- オプションのハイフンまたはスペース
- 3 桁
- オプションのハイフンまたはスペース
- 3 桁
- オプションのハイフンまたはスペース
- 3 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

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