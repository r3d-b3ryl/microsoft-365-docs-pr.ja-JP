---
title: Azure AD ユーザー資格情報エンティティ定義 (プレビュー)
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
description: Azure AD ユーザー資格情報の機密情報の種類エンティティ定義。
ms.openlocfilehash: 5b27f2a5c700770df65be74f0cebb23351de77bc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996122"
---
# <a name="azure-ad-user-credentials-preview"></a>Azure AD ユーザー資格情報 (プレビュー)

## <a name="format"></a>フォーマット

*.onmicrosoft.com ドメインに関連するペアのユーザー名とパスワード。

or

コード スニペットで使用されるプレーンテキスト パスワード。

or

XML 構成で使用されるプレーンテキスト パスワード。

## <a name="pattern"></a>パターン

次のようなさまざまなユーザー名とパスワードの形式。

`username=...password=********` <br>
`/user:.../pass:********` <br>
`SharePointOnlineAuthenticatedContext` <br>
`sign_in`<br>


or

コード スニペットのさまざまなパスワード形式。たとえば、次のようになります。

`new X509Certificates2( ...` <br>
`ConvertTo-SecureString -String ********...`<br>
`password = "********"...` <br>
`"password" : "********"...` <br>
`UserPasswordCredential( ...` <br>

or

XML のさまざまなパスワード形式は次のとおりです。


```xml
... <secret>********</secret> ...
... <password>********</password> ...
... <setting name="password" value="********" > ... 
... <setting name="password">********</setting> ... 
... <setting name="password"><value>********</value></setting> ... 
```


## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-reset-password-azure-portal) に対する認証に個々のユーザー パスワードとして使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Azure AD テナントのプレーンテキスト ユーザー名とパスワードのパターン。
- コード内のパスワード コンテキストのパターン。
- XML のパスワード コンテキストのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。


## <a name="keywords"></a>キーワード

### <a name="keyword_azureactivedirectorylogincredentials"></a>Keyword_AzureActiveDirectoryLoginCredentials:

- password
- Pw
- userpass
- 資格 情報
- cmdkey
- Authenti
- sign_in

### <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode:

- キー
- x509c
- 資格 情報
- password
- Pw
- Securestring

### <a name="keyword_passwordcontextinxml"></a>Keyword_PasswordContextInXml:

- userpass
- password
- Pw
- Connectionstring
- キー
- 資格 情報
- token
- Sas
- 秘密

