---
title: Azure Publish setting password entity definition
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
description: Azure Publish setting password sensitive information type entity definition.
ms.openlocfilehash: 9cbca08dc1414241f494a415cf3aafea9e505a6e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995927"
---
# <a name="azure-publish-setting-password"></a>Azure の発行設定パスワード

### <a name="format"></a>フォーマット

文字列 `userpwd=` の後に英数字の文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 `userpwd=`
- 60 個の小文字または数字の任意の組み合わせ
- 引用符 (")

### <a name="checksum"></a>チェックサム

不要

### <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `CEP_Regex_AzurePublishSettingPasswords` は、パターンに一致するコンテンツを検索します。
- 正規表現 `CEP_CommonExampleKeywords` では、パターンに一致するコンテンツが見つかりません。

```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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
