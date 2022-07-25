---
title: Azure IAAS データベース接続文字列とAzure SQL接続文字列エンティティ定義
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
description: Azure IAAS データベース接続文字列とAzure SQL接続文字列の機密情報の種類エンティティ定義。
ms.openlocfilehash: 894a849c318ad15ab9baac8343192428d633ce1b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996462"
---
# <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure の IAAS データベース接続文字列と Azure SQL の接続文字列

## <a name="format"></a>フォーマット

文字列、または文字列を含む、以下のパターンで説明されている文字と文字列`cloudapp.azure.net``database.windows.net``cloudapp.azure.com`の後に続く文字列。`pwd``Password` `password` `data source` `server``Server`

## <a name="pattern"></a>パターン

- 文字列 `Server`、 `server`、または `data source`
- 0 から 2 つの空白文字
- 等号 (=)
- 0 から 2 つの空白文字
- 1 から 200 の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "cloudapp.azure。<!--no-hyperlink-->com"、"cloudapp.azure。<!--no-hyperlink-->net"、または "database.windows.<!--no-hyperlink-->net"
- 1 から 300 の小文字、または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 `Password`、 `password`、または `pwd`
- 0 から 2 つの空白文字
- 等号 (=)
- 0 から 2 つの空白文字
- セミコロン (;)、引用符 (")、または apostrophe (') ではない 1 つ以上の文字
- セミコロン (;)、引用符 (")、または apostrophe (')

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `CEP_Regex_AzureConnectionString` は、パターンに一致するコンテンツを検索します。
- 正規表現 `CEP_CommonExampleKeywords` では、パターンに一致するコンテンツが見つかりません。

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します。

- Contoso
- Fabrikam
- Northwind
- サンド ボックス
- onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->ネット
