---
title: ブラジルの国民識別カード (RG) エンティティ定義
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
description: ブラジルの国民識別カード (RG) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 7f4fe7a0eda911639c0c7650d4ac71f07dfe4f3a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995572"
---
# <a name="brazil-national-identification-card-rg"></a>ブラジルの国民識別カード (RG)

## <a name="format"></a>フォーマット

Registro Geral (古い形式): 9 桁

Registro de Identidade (RIC) (新しい形式): 11 桁

### <a name="pattern"></a>パターン

Registro Geral (従来の形式):

- 2 桁の数字
- 期間
- 3 桁
- 期間
- 3 桁
- ハイフン
- チェック ディジットである 1 桁

Registro de Identidade (RIC) (新しい形式):

- 10 桁の数字
- ハイフン
- チェック ディジットである 1 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_brazil_rg` がパターンに一致するコンテンツを検出した。
- `Keyword_brazil_rg` のキーワードを検出した。
- チェックサムが渡される。

```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- Identity card
- national id
- número de rregistro
- registro de Iidentidade
- registro geral
- RG (このキーワードでは大文字と小文字が区別されます)
- RIC (このキーワードでは大文字と小文字が区別されます)