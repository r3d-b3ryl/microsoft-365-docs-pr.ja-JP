---
title: チリ ID カード番号エンティティ定義
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
description: チリ ID カード番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 1ec3b90d52d5404bf49a343cba7fb2c7f5464870
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996592"
---
# <a name="chile-identity-card-number"></a>チリの身分証明書番号

## <a name="format"></a>フォーマット

7 ~ 8 桁の数字に区切り記号を加えたチェック の数字または文字

## <a name="pattern"></a>パターン

7 ~ 8 桁の数字と区切り記号:

- 1 ~ 2 桁
- 省略可能な期間
- 3 桁
- 省略可能な期間
- 3 桁
- ダッシュ
- チェック 桁である 1 桁または 1 文字 (大文字と小文字は区別されません)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_chile_id_card` がパターンに一致するコンテンツを検出した。
- `Keyword_chile_id_card` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_chile_id_card` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- 実行
- マンネリ
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- 実行#
- マンネリ#
- nationaluniqueroleID#
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- チリの ID 番号。
- チリの ID 番号
- チリの ID#
- 一意の税レジストリ
- 一意の支流ロール
- 一意の税ロール
- 一意の支流番号
- 一意の国番号
- 一意の国の役割
- 国内固有の役割
- チリ ID 番号。
- チリ ID 番号
- チリ ID#
- R.U.T
- R.U.N