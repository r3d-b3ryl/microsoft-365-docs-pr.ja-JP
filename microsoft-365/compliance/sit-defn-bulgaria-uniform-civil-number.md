---
title: ブルガリアの統一市民番号エンティティ定義
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
description: ブルガリアの一様な市民番号の機密情報の種類のエンティティ定義。
ms.openlocfilehash: f9e97c049cf20f3c804e0fbf0f12489e557ad9f1
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369676"
---
# <a name="bulgaria-uniform-civil-number"></a>ブルガリアの統一市民番号

## <a name="format"></a>フォーマット

スペースと区切り記号のない 10 桁

## <a name="pattern"></a>パターン

スペースと区切り記号のない 10 桁

- 生年月日に対応する 6 桁の数字 (YYMMDD)
- 生年月日に対応する 2 桁の数字
- 性別に対応する 1 桁: 男性の偶数桁と女性の奇数桁
- 1 つのチェック ディジット

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_bulgaria_eu_national_id_card` がパターンに一致するコンテンツを検出した。
- `Keywords_bulgaria_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_bulgaria_eu_national_id_card` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- Bnn#
- Bnn
- bucn#
- bucn
- edinen の
- egn#
- egn
- identification number
- national id
- 国内番号
- nationalnumber#
- nationalnumber
- 個人用 ID
- personal no
- 個人番号
- personalidnumber#
- social security number
- Ssn#
- Ssn
- uniform civil id
- uniform civil no
- 一様な市民番号
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 一意の市民権番号
- егн#
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ гранск id
- униформ граждански не
- униформ граждански номер
- униформранскиid#
- униформгражданскине.#