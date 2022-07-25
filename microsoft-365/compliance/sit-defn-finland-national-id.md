---
title: フィンランドの国民 ID エンティティ定義
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
description: フィンランド国内 ID の機密情報の種類エンティティ定義。
ms.openlocfilehash: 7d196482051afb6a889d855c80616a4a15ce1df2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997382"
---
# <a name="finland-national-id"></a>フィンランドの国民 ID

## <a name="format"></a>フォーマット

6 桁と 1 世紀を示す文字と 3 桁の数字とチェック 桁

## <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。

- DDMMYY 形式の 6 桁 (生年月日)
- 世紀マーカー ('-'、'+' または 'a')
- 3 桁の個人識別番号
- チェック ディジットである数字または文字 (大文字と小文字を区別しない)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_finnish_national_id` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_finnish_national_id` 見つかりました
- チェックサムが渡される

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_finnish_national_id` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

- briantlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero#
- henkilötunnusnumero
- hetu
- id no
- id 番号
- identification number
- identiteetti numero
- ID 番号
- idnumber
- brianllinen henkilötunnus
- brianllisen henkilökortin
- 国民 ID カード
- national id no.
- 個人用 ID
- 個人 ID コード
- personalidnumber#
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
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
- tunnistenumero
- tunnus numero
- tunnuslく
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus