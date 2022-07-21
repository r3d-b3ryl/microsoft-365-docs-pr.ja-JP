---
title: フランスの国民 ID カード (CNI) エンティティ定義
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
description: フランスの国民 ID カード (CNI) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 35a6481e657d20a83ed1b80a6d06ad8ebf1c9cdf
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950883"
---
# <a name="france-national-id-card-cni"></a>フランスの国民 ID カード (CNI)

## <a name="format"></a>フォーマット

12 桁の数字

## <a name="pattern"></a>パターン

12 桁の数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 正規表現 `Regex_france_cni` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_france_eu_national_id_card` 見つかりました。

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- carte nationale d'identité
- carte nationale d'idenite no
- Cni#
- Cni
- compte bancaire
- national identification number
- 各国の ID
- nationalidno#
- numéro d'assurance maladie
- numéro de carte vitale