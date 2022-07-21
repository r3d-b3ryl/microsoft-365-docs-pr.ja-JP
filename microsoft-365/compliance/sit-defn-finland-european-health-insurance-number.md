---
title: フィンランドのヨーロッパの医療保険番号エンティティ定義
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
description: フィンランドのヨーロッパの医療保険番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 200b580804d60ef3adfaeead21e7c3ab8d51f139
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950627"
---
# <a name="finland-european-health-insurance-number"></a>フィンランドのヨーロッパの医療保険番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

20 桁の数字

## <a name="pattern"></a>パターン

20 桁の数字:

- 10 桁 - 8024680246
- 省略可能なスペースまたはハイフン
- 10 桁の数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- 正規表現 `Regex_Finland_European_Health_Insurance_Number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_Finland_European_Health_Insurance_Number` 見つかりました。

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- Ehic#
- Ehic
- finlandehicnumber#
- fizk sjukförsäkkingskort
- 正常性カード
- 健康保険証
- 医療保険番号
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkkingskort
- suomen sairausvakuutuskortti
- terveyskortti
