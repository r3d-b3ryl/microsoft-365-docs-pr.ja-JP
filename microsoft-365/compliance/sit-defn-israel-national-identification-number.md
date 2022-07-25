---
title: イスラエルの国民識別番号エンティティ定義
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
description: イスラエルの国民識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 2c56afb1656f5fea682d165af563afd320d63039
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997597"
---
# <a name="israel-national-identification-number"></a>イスラエルの国民識別番号

## <a name="format"></a>フォーマット

9 桁

## <a name="pattern"></a>パターン

9 桁の連続する数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_israeli_national_id_number` がパターンに一致するコンテンツを検出した。
- `Keyword_Israel_National_ID` のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות
- מספר זיה וי
- מספר זיהוי ישר אלי
- זהותישר אלית
- هو ية اسرائيل ية عدد
- هوية إسرائ يلية
- رقم الهوية
- عدد هوية فريدة من نوعها
- idnumber#
- id 番号
- id no
- identitynumber#
- ID 番号
- identifieridentitynumber
- 個人用 ID
- 一意の ID