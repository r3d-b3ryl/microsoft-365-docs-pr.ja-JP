---
title: Azure AD クライアント アクセス トークン エンティティ定義 (プレビュー)
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
description: Azure AD クライアント アクセス トークンの機密情報の種類エンティティ定義。
ms.openlocfilehash: a59848511cde3778c373f55c18e794e81db1f80e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996142"
---
# <a name="azure-ad-client-access-token-preview"></a>Azure AD クライアント アクセス トークン (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される最大 10,000 文字の組み合わせ。

or

OAuth2.0 プロトコルで使用されるクライアント シークレットまたは更新トークン。

or

文字、数字、特殊文字で構成される最大 1,000 文字の組み合わせ。

## <a name="pattern"></a>パターン

次の任意の組み合わせ:
 
- 最大 10,000 
- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)
- 最大 2 個
- 等号 (=)

例:

`"VersionProfile": null, "TokenCache": { "CacheData": 
"AgAAAAIAAACZAWh0dHBzOi8vbG9naW4ubWljcm9zb2`

or

バリアント クライアント シークレットや更新トークンの形式 (例: <br> 
`ClientSecret:********` <br>
`AppSecret=********` <br>
`ConsumerKey:=********` <br>
`Refresh_Token:********` <br>

or

3 文字: eyJ (大文字と小文字が区別されます)

And

で構成される最大 1,000 文字の組み合わせ

- a-z (大文字と小文字は区別されません)
- 0-9
- ダッシュ (-)
- 下線 (_)
- またはドット (.)

例:

`eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ing0Nzh4eU9wbHNNMUg3TlhrN1N4MTd4MXVwYyIsImtpZCI6Ing0Nzh4`



## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、 [Azure Active Directory B2C (Azure AD B2C](/azure/active-directory-b2c/active-directory-b2c-access-tokens) ) で Azure リソースに付与されたアクセス許可を識別するために使用できるクレームを含むセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Azure PowerShell トークン キャッシュのパターン
- クライアント シークレット コンテキストのパターン
- Json Web トークンのパターン
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン
- モックアップ値、やり直し、プレースホルダーのパターン
- ボキャブラリの辞書

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。



## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickeycontextinxml"></a>Keyword_SymmetricKeyContextInXml:

- tokencache

### <a name="keyword_clientsecretcontext"></a>Keyword_ClientSecretContext:

- 秘密
- token
- auth
- Securestring
- キー

### <a name="keyword_jsonwebtoken"></a>Keyword_JsonWebToken:

- eyJ

