---
title: オーストリアの社会保障番号エンティティ定義
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
description: オーストリアの社会保障番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 24b909e2b45bce3db5c4b4cfd1e0d3cf3d74296c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996577"
---
# <a name="austria-social-security-number"></a>オーストリアの社会保障番号

## <a name="format"></a>フォーマット

指定した形式の 10 桁

## <a name="pattern"></a>パターン

10 桁の数字:

- シリアル番号に対応する 3 桁の数字
- 1 つのチェック ディジット
- 生年月日に対応する 6 桁の数字 (DDMMYY)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_austria_eu_ssn_or_equivalent` がパターンに一致するコンテンツを検出した。
- キーワードが `Keywords_austria_eu_ssn_or_equivalent` 見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_austria_eu_ssn_or_equivalent` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- オーストリア ssn
- ehic 番号
- ehic no
- 保険コード
- insurancecode#
- 保険番号
- 保険なし
- krankenkassennummer
- krank
- socialsecurityno
- socialsecurityno#
- 社会保障なし
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer#
- soziale sicherheitkein
- sozialesicherheitkein#
- Ssn#
- Ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje