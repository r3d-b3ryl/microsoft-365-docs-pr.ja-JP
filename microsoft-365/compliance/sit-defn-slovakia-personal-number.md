---
title: スロバキア個人番号エンティティ定義
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
description: スロバキアの個人番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 4e576d4b4ac1c65ca72e2955c7617fe7d2badd22
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367645"
---
# <a name="slovakia-personal-number"></a>スロバキアの個人番号

## <a name="format"></a>フォーマット

省略可能な円記号を含む 9 桁または 10 桁

## <a name="pattern"></a>パターン

- 生年月日を表す 6 桁の数字
- 省略可能なスラッシュ (/)
- 3 桁の数字
- 1 つのオプションのチェック 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_slovakia_eu_national_id_card` がパターンに一致するコンテンツを検出した。
- `Keywords_slovakia_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、低い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_slovakia_eu_national_id_card` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- 生年月日
- číslo národnej identifikačnej 台
- číslo občianského preu一
- daňové číslo
- id 番号
- id no
- identification number
- identifikačnáarta č
- identifikačné číslo
- ID カードなし
- ID カード番号
- národná identifikačná značka č
- 国内番号
- nationalnumber#
- nemzeti személyazonosító izezolvány
- personalidnumber#
- rč
- rodne cislo
- rodné číslo
- social security number
- Ssn#
- Ssn
- személyi tigzolvány szám
- személyi izezolvány száma
- személytigzolvány szám
- tax file no
- tax file number
- tax id
- 税の識別番号なし
- 税識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin ID
- tin no
- 錫#