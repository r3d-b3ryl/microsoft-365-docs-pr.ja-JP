---
title: スロベニア固有のマスター市民番号エンティティ定義
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
description: スロベニア固有のマスター 市民番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 23c484946c8e73e7f21b251aa35935dba37b110b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996542"
---
# <a name="slovenia-unique-master-citizen-number"></a>スロベニアの一意のマスター市民番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

スペースまたは区切り記号のない 13 桁

## <a name="pattern"></a>パターン

指定したパターンの 13 桁:

- "LLL" が生年月日の最後の 3 桁に対応する生年月日 (DDMMLLL) に対応する 7 桁
- 出生領域 "50" に対応する 2 桁の数字
- 同じ日に生まれた人の性別とシリアル番号の組み合わせに対応する 3 桁の数字。 男性は 000-499、女性は 500-999。
- 1 つのチェック ディジット

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_slovenia_eu_national_id_card` がパターンに一致するコンテンツを検出した。
- `Keywords_slovenia_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_slovenia_eu_national_id_card` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- Identity card
- nacionalna id
- nacionalni potni list
- national id
- osebna izkaznica
- osebni コダ
- osebni ne
- osebni številka
- 個人用コード
- 個人番号
- 個人用数値コード
- številka državljana
- 一意の市民番号
- 一意の ID 番号
- 一意の ID 番号
- 一意のマスター市民番号
- 一意の登録番号
- uniqueidentityno#
- uniqueidentityno#