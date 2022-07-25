---
title: デンマークの個人識別番号エンティティ定義
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
description: デンマークの個人識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 8fbdd3fc2bd273b34fcf3625fa9f021d1f948358
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996747"
---
# <a name="denmark-personal-identification-number"></a>デンマークの個人識別番号

## <a name="format"></a>フォーマット

ハイフンを 1 つ含む 10 桁の数字

## <a name="pattern"></a>パターン

10 桁の数字:

- DDMMYY 形式の 6 桁 (生年月日)
- 省略可能なスペースまたはハイフン
- 最後の数字がチェック 桁である 4 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Func_denmark_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_denmark_id` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 正規表現 `Func_denmark_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- Cpr
- Cpr#
- gemissionheitskarte nummer
- gemissionheitsversicherungkarte nummer
- 正常性カード
- 健康保険証番号
- 医療保険番号
- identification number
- identifikationsnummer
- identifikationsnummer#
- ID 番号
- krankenkassennummer
- nationalid#
- nationalnumber#
- 国内番号
- personalidnumber#
- personalidentityno#
- 個人 ID 番号
- personnummer
- personnummer#
- reisekrankuvasicherungskartenummer
- rejsesygesikringskort
- Ssn
- Ssn#
- スケーティング ID
- スケーティング kode
- 滑り nummer
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- 税コード
- 旅行健康保険証
- uniqueidentityno#
- 税番号
- 税登録番号
- tax id
- 税識別番号
- taxid#
- taxnumber#
- tax no
- taxno#
- taxnumber
- 税の識別番号なし
- 錫#
- taxidno#
- taxidnumber#
- tax no#
- tin ID
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer