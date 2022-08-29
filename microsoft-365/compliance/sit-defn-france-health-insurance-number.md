---
title: フランスの医療保険番号エンティティ定義
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
description: フランスの医療保険番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 34076914498182076196c6335980d9653ba9e1f9
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369971"
---
# <a name="france-health-insurance-number"></a>フランスの健康保険番号

## <a name="format"></a>フォーマット

21 桁の番号

## <a name="pattern"></a>パターン

21 桁の数字:

- 10 桁の数字
- 省略可能な領域
- 10 桁の数字
- 省略可能な領域
- 数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_France_Health_Insurance_Number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_France_Health_Insurance_Number` 見つかりました。

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>キーワード

### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- 保険証
- carte vitale
- carte d'assuré social