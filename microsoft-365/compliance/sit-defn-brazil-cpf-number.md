---
title: ブラジル CPF 番号エンティティ定義
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
description: ブラジル CPF 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: b8164d44f20237b5eb74d45369f3bffbe1dc07e3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950485"
---
# <a name="brazil-cpf-number"></a>ブラジル CPF 番号

## <a name="format"></a>フォーマット

書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字

## <a name="pattern"></a>パターン

フォーマット：

- 3 桁
- 期間
- 3 桁
- 期間
- 3 桁
- ハイフン
- チェックディジットである 2 桁の数字

未フォーマット：

- 11 桁の数字 (最後の 2 桁はチェック ディジット)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- この関数 `Func_brazil_cpf` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_brazil_cpf` 見つかりました。
- チェックサムが渡される。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- この関数 `Func_brazil_cpf` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- 識別
- 登録
- 収益
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita