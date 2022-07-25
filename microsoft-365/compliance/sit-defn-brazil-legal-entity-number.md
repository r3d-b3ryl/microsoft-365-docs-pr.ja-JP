---
title: ブラジル法人番号 (CNPJ) エンティティ定義
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
description: ブラジル法人番号 (CNPJ) の機密情報の種類エンティティ定義。
ms.openlocfilehash: a8cf09eb283cea08e72a5858e7bfd4752486a01e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997322"
---
# <a name="brazil-legal-entity-number-cnpj"></a>ブラジルの法人番号 (CNPJ)

## <a name="format"></a>フォーマット

登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字

## <a name="pattern"></a>パターン

14 桁の数字と区切り文字:

- 2 桁の数字
- 期間
- 3 桁
- 期間
- 3 桁 (最初の 8 桁は登録番号)
- スラッシュ
- 4 桁の分岐番号
- ハイフン
- チェックディジットである 2 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_brazil_cnpj` がパターンに一致するコンテンツを検出した。
- `Keyword_brazil_cnpj` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_brazil_cnpj` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ
- CNPJ/MF
- CNPJ-MF
- National Registry of Legal Entities
- Taxpayers Registry
- Legal entity
- Legal entities
- Registration Status
- Business
- 会社名
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Situação cadastral
- Inscrição
- Empresa