---
title: ラトビアの個人コード エンティティ定義
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
description: ラトビアの個人コードの機密情報の種類エンティティ定義。
ms.openlocfilehash: 16e736220fa402df6ebcb87e947e75090b4a0f57
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995409"
---
# <a name="latvia-personal-code"></a>ラトビアの個人コード

## <a name="format"></a>フォーマット

11 桁の数字とオプションのハイフン

## <a name="pattern"></a>パターン

古い形式

11 桁の数字とハイフン:

- 生年月日に対応する 6 桁の数字 (DDMMYY)
- ハイフン
- 生まれた世紀に対応する 1 桁 (19 世紀の場合は "0"、20 世紀の場合は "1"、21 世紀の場合は "2")
- ランダムに生成された 4 桁の数字

新しい形式

11 桁の数字

- 2 桁の "32"
- 9 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_latvia_eu_national_id_card` または正規表現 `Regex_latvia_eu_national_id_card_new_format` は、パターンに一致するコンテンツを検索します。
- `Keywords_latvia_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_latvia_eu_national_id_card` または正規表現 `Regex_latvia_eu_national_id_card_new_format` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

## <a name="keywords"></a>キーワード

### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- 管理番号
- alvas nē
- 生年月日
- 市民番号
- 市民番号
- 電子国勢調査番号
- 電子番号
- 会計コード
- 医療ユーザー番号
- Id#
- id-code
- identification number
- identifikācijas numurs
- id-number
- 個々の番号
- latvija alva
- nacionālais id
- national id
- 国別識別番号
- 国の ID 番号
- national insurance number
- 国民登録番号
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- 個人証明書番号
- 個人用コード
- 個人用 ID コード
- 個人 ID 番号
- 個人識別コード
- 個人識別子
- 個人 ID 番号
- 個人番号
- 個人用数値コード
- personalcodeno#
- personas kods
- 母集団識別コード
- パブリック サービス番号
- registration number
- 収益番号
- social insurance number
- social security number
- 州税コード
- tax file number
- tax id
- 税の識別番号なし
- 税識別番号
- tax no#
- tax no
- 税番号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin ID
- tin no
- 錫#
- 投票者の番号