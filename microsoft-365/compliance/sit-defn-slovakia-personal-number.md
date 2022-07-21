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
ms.openlocfilehash: 4f923c714cf94543828d184164631d5e0c60e9e8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950402"
---
# <a name="slovakia-personal-number"></a>スロバキアの個人番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

省略可能な円記号を含む 9 桁または 10 桁

## <a name="pattern"></a>パターン

- 生年月日を表す 6 桁の数字
- 省略可能なスラッシュ (/)
- 3 桁
- 1 つのオプションのチェック 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- この関数 `Func_slovakia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_slovakia_eu_national_id_card` 見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- この関数 `Func_slovakia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

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