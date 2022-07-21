---
title: メキシコ固有の母集団レジストリ コード (CURP) エンティティ定義
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
description: メキシコ一意の母集団レジストリ コード (CURP) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 806f7e9b0d2dd797b17ad848d160c6f74c04e1e2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950827"
---
# <a name="mexico-unique-population-registry-code-curp"></a>メキシコ固有の人口レジストリ コード (CURP)

## <a name="format"></a>フォーマット

18 文字の英数字パターン

## <a name="pattern"></a>パターン

- 4 文字 (大文字と小文字を区別しない)
- 有効な日付を示す 6 桁の数字
- 文字 - H/h または M/m
- 有効なメキシコの州コードを示す 2 文字
- 3 文字
- 1 文字または 1 桁
- 1 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- この関数 `Func_mexico_population_registry_code` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_mexico_population_registry_code` 見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- この関数 `Func_mexico_population_registry_code` は、パターンに一致するコンテンツを検索します。

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- 一意の母集団レジストリ コード
- 一意の母集団コード
- CURP
- 個人用 ID
- 一意な ID
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave personal Identidad
- personal Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad