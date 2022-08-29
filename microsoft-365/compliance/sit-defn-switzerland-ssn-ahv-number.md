---
title: スイス SSN AHV 番号エンティティ定義
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
description: スイス SSN AHV 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: d4f5971a1ee2d0dcf96ee023ff609ba70f6ec052
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368171"
---
# <a name="switzerland-ssn-ahv-number"></a>スイスの SSN AHV 番号

## <a name="format"></a>フォーマット

13 桁の数字

## <a name="pattern"></a>パターン

13 桁の数字:

- 3 桁の数字 - 756
- 省略可能なドット
- 4 桁の数字
- 省略可能なドット
- 4 桁の数字
- 省略可能なドット
- 2 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_swiss_social_security_number_ahv` がパターンに一致するコンテンツを検出した。
- `Keywords_swiss_social_security_number_ahv` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_swiss_social_security_number_ahv` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- Ssn
- pid
- 保険番号
- personalidno#
- social security number
- 個人 ID 番号
- 個人識別番号。
- insuranceno#
- uniqueidno#
- 一意の識別番号。
- avs 番号
- 個人 ID no versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- id personnelle id
- numéro de sécurité sociale