---
title: Azure DocumentDB 認証キー エンティティ定義
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
description: Azure DocumentDB 認証キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: e499d185b0a1752960f71f659a212aa0422154f4
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995987"
---
# <a name="azure-documentdb-auth-key"></a>Azure DocumentDB の認証キー

## <a name="format"></a>フォーマット

文字列 `DocumentDb` の後に、次のパターンで説明されている文字と文字列が続きます。

## <a name="pattern"></a>パターン

- 文字列 `DocumentDb`
- 3 ~ 200 の小文字、または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 記号より大きい (>)、等号 (=)、引用符 (")、またはアポストロフィ (')
- 86 個の小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ
- 2 つの等号 (=)

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `CEP_Regex_AzureDocumentDBAuthKey` は、パターンに一致するコンテンツを検索します。
- 正規表現 `CEP_CommonExampleKeywords` では、パターンに一致するコンテンツが見つかりません。

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

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
