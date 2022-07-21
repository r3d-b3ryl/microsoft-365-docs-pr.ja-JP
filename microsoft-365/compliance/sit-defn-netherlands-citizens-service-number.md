---
title: オランダ市民サービス (BSN) 番号エンティティ定義
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
description: オランダ市民サービス (BSN) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 4a5ca70bbbffe2d89b2dd05bd51e3dcda525e6a3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950819"
---
# <a name="netherlands-citizens-service-bsn-number"></a>オランダ市民サービス (BSN) 番号

## <a name="format"></a>フォーマット

省略可能なスペースを含む 8 桁または 9 桁

## <a name="pattern"></a>パターン

8 から 9 桁:

- 3 桁
- スペース (省略可能)
- 3 桁
- スペース (省略可能)
- 2 から 3 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- パターンに一致する関数 `Func_netherlands_bsn finds` の内容。
- キーワードが `Keyword_netherlands_bsn` 見つかりました。
- チェックサムが渡される。

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- Bsn#
- Bsn
- burgerservicenummer
- 市民サービス番号
- ユーザー番号
- 個人番号
- 個人用数値コード
- person-related number
- persoonlijk nummer
- persoonlijke numerieke コード
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- social-fiscal number
- ソフィ
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- 一意の識別番号
- 一意の ID 番号
- uniqueidentityno#