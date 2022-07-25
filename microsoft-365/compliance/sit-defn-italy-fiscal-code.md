---
title: イタリアの会計コード エンティティ定義
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
description: イタリアの会計コードの機密情報の種類エンティティ定義。
ms.openlocfilehash: 1a27af7f33aba799a37c64c37e53eef01555ec3c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997592"
---
# <a name="italy-fiscal-code"></a>イタリアの会計コード

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

指定したパターン内の文字と数字の 16 文字の組み合わせ

## <a name="pattern"></a>パターン

文字と数字の 16 文字の組み合わせ:

- ファミリ名の最初の 3 つの子音に対応する 3 文字
- 名の最初、3 番目、および 4 番目の子音に対応する 3 文字
- 誕生日年の最後の数字に対応する 2 桁の数字
- 誕生日の文字に対応する 1 文字です。アルファベット順に使用されますが、A から E、H、L、M、P、R から T の文字のみが使用されます (そのため、1 月は A、10 月は R)
- 性別を区別するために、誕生日の日に対応する 2 桁の数字、40 は女性の誕生日に追加されます
- 人が生まれた市区町村に固有の市外局番に対応する 4 桁の数字 (国全体のコードは、外部の国で使用されます)
- 1 つのパリティ 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_italy_eu_national_id_card` がパターンに一致するコンテンツを検出した。
- `Keywords_italy_eu_national_id_card` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_italy_eu_national_id_card` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- 会計コード
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- 個人証明書番号
- 個人用コード
- 個人用 ID コード
- 個人 ID 番号
- personalcodeno#
- 税コード
- tax id
- 税の識別番号なし
- 税識別番号
- 税 ID 番号
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