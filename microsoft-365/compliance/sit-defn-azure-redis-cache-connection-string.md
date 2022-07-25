---
title: Azure Redis cache 接続文字列エンティティ定義
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
description: Azure Redis cache 接続文字列の機密情報の種類エンティティ定義。
ms.openlocfilehash: f195440c1f93ec1818bf10e1c57cf391085cb733
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996762"
---
# <a name="azure-redis-cache-connection-string"></a>Azure Redis Cache の接続文字列

## <a name="format"></a>フォーマット

文字列 `redis.cache.windows.net` の後に、次のパターンで説明されている文字と文字列 (文字列 `password` や `pwd`文字列など) が続きます。

## <a name="pattern"></a>パターン

- 文字列 `redis.cache.windows.net`
- 1 から 200 の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 `password` または `pwd`
- 0 から 2 つの空白文字
- 等号 (=)
- 0 から 2 つの空白文字
- 小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) である 43 文字の任意の組み合わせ
- 等号 (=)

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `CEP_Regex_AzureRedisCacheConnectionString` は、パターンに一致するコンテンツを検索します。
- 正規表現 `CEP_CommonExampleKeywords` では、パターンに一致するコンテンツが見つかりません。

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
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
