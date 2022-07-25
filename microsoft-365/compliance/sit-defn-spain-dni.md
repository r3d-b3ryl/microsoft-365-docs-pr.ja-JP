---
title: スペインの DNI エンティティ定義
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
description: スペインの DNI 機密情報の種類エンティティ定義。
ms.openlocfilehash: e18fbfdcaad30e94d9f8fbd239026c25bee04d78
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996177"
---
# <a name="spain-dni"></a>スペインの DNI

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

8 桁の数字の後に 1 文字が続く

## <a name="pattern"></a>パターン

7 桁の数字の後に 1 文字が続く

- 8 桁
- 省略可能なスペースまたはハイフン
- 1 つのチェック文字 (大文字と小文字は区別されません)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_spain_eu_DL_and_NI_number_citizen` または `Func_spain_eu_DL_and_NI_number_foreigner` パターンに一致するコンテンツを検索します。
- `Keywords_spain_eu_national_id_card"` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_spain_eu_DL_and_NI_number_citizen` または `Func_spain_eu_DL_and_NI_number_foreigner` パターンに一致するコンテンツを検索します。

```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- Dni#
- Dni
- dninúmero#
- documento nacional de identidad
- identidad único
- identidadúnico#
- 保険番号
- national identification number
- 各国の ID
- nationalid#
- nationalidno#
- Nie#
- Nie
- nienúmero#
- número de identificación
- número nacional identidad
- 暗証番号
- 個人 ID なし
- 一意の ID 番号
- Uniqueid#