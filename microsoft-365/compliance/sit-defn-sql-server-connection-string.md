---
title: 接続文字列エンティティ定義SQL Server
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
description: 接続文字列の機密情報の種類エンティティ定義をSQL Serverします。
ms.openlocfilehash: 503b2bae244cec8de5da29228f6517433a162ca1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997062"
---
# <a name="sql-server-connection-string"></a>SQL Server の接続文字列

## <a name="format"></a>フォーマット

文字列 `User Id`、 `User ID`、 `uid`または `UserId` 後に、次のパターンで説明されている文字と文字列が続きます。

## <a name="pattern"></a>パターン

- 文字列`User Id`、、、`uid``User ID`、または`UserId`
- 1 から 200 の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列`Password`または`pwd`小文字の前にない場所`pwd`
- 等号 (=)
- ドル記号 ($)、パーセント記号 (%)、記号 (>)、記号 (@)、引用符 (")、セミコロン (;)、左中かっこ([)、左角かっこ ({) より大きい文字)
- セミコロン (;)、スラッシュ (/)、または引用符 (") ではない 7 ~ 128 文字の任意の組み合わせ
- セミコロン (;)または引用符 (")

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `CEP_Regex_SQLServerConnectionString` は、パターンに一致するコンテンツを検索します。
- キーワードが `CEP_GlobalFilter` 見つかりません。
- 正規表現 `CEP_PasswordPlaceHolder` では、パターンに一致するコンテンツが見つかりません。
- 正規表現 `CEP_CommonExampleKeywords` では、パターンに一致するコンテンツが見つかりません。

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- somepassword
- secretPassword
- サンプル

### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します。

- `Password` または `pwd` 0 から 2 のスペース、等号 (=)、0 から 2 のスペース、アスタリスク (*) -OR- が続きます。
- `Password` または `pwd` 次の順に実行します。
    - 等号 (=)
    - シンボル未満 (<)
    - 大文字または小文字、数字、アスタリスク (*)、ハイフン (-)、下線 (_)、または空白文字である 1 から 200 文字の任意の組み合わせ
    - シンボルより大きい (>)

### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

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