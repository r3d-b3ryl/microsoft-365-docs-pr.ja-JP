---
title: カナダの個人健康識別番号 (PHIN) エンティティ定義
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
description: カナダの個人の健康識別番号 (PHIN) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 0d2ac2f8deeb4cb9139d0ab66cb02bbd4bccd7c8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950413"
---
# <a name="canada-personal-health-identification-number-phin"></a>カナダの個人の健康識別番号 (PHIN)

## <a name="format"></a>フォーマット

9 桁

## <a name="pattern"></a>パターン

9 桁

## <a name="checksum"></a>チェックサム

不要

### <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- 正規表現 `Regex_canada_phin` は、パターンに一致するコンテンツを検索します。
- 少なくとも 2 つのキーワードが見`Keyword_canada_phin``Keyword_canada_provinces`つかりました。

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- ヌナブト 準 州
- ケベック
- Northwest Territories
- オンタリオ
- British Columbia
- アルバータ 州
- サスカチュワン
- マニトバ 州
- ユーコン
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- カナダ