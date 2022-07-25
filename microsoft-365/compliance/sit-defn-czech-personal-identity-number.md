---
title: チェコの個人 ID 番号エンティティ定義
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
description: チェコの個人 ID 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: a5c6156a2f84ff96025c3f73cf20dcbd201e90d3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997672"
---
# <a name="czech-personal-identity-number"></a>チェコの個人識別番号

## <a name="format"></a>フォーマット

省略可能なスラッシュ (古い形式) を持つ 9 桁の数字

10 桁の数字と省略可能なスラッシュ (新しい形式)

## <a name="pattern"></a>パターン

9 桁 (古い形式):

- 生年月日を表す 6 桁の数字
- 省略可能なスラッシュ
- 3 桁

10 桁 (新しい形式):

- 生年月日を表す 6 桁の数字
- 省略可能なスラッシュ
- 最後の数字がチェック 桁である 4 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_czech_id_card` がパターンに一致するコンテンツを検出した。
- `Keyword_czech_id_card` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_czech_id_card_new_format` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
## <a name="keywords"></a>キーワード

### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- 生年月日
- チェコ共和国 ID
- チェコ語#
- daňové číslo
- identifikační číslo
- id no
- ID 番号
- identityno#
- identityno
- 保険番号
- national identification number
- nationalnumber#
- 国内番号
- osobní číslo
- personalidnumber#
- 個人 ID 番号
- 暗証番号
- 個人番号
- Pid#
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- Ssn
- Ssn#
- social security number
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
- 一意の識別番号