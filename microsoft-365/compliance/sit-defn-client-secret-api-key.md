---
title: クライアント シークレット/API キー エンティティ定義 (プレビュー)
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
description: クライアント シークレット/API キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: 25bd50de2193abaa926d09475cc9ff537432fc62
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950612"
---
# <a name="client-secret--api-key-preview"></a>クライアント シークレット/API キー (プレビュー)

## <a name="format"></a>フォーマット

OAuth 2.0 プロトコルで使用されるクライアント シークレットまたは更新トークン。

or

文字、数字、特殊文字で構成される 24 文字の組み合わせ。

or

文字と数字で構成される 32 文字の組み合わせ。

or

文字と数字で構成される 40 文字の組み合わせ。

or

文字、数字、特殊文字で構成される 44 文字の組み合わせ。

or

文字、数字、特殊文字で構成される 56 文字の組み合わせ

or

文字、数字、特殊文字で構成される 88 文字の組み合わせ。


## <a name="pattern"></a>パターン

次に示す、さまざまなクライアント シークレットまたは更新トークンの形式を示します。
 
`ClientSecret:********` <br>
`AppSecret=********` <br>
`ConsumerKey:=********` <br>
`Refresh_Token:********` <br>

or

22 文字の組み合わせ:
 
- a-z (大文字と小文字は区別されません)
- 数字、スラッシュ、またはプラス記号
- 2 つの等号 (=) で終わる

例:

`abcdefgh0123456789/+AB==`

or

32 文字の組み合わせ:

- a-f または A-F (大文字と小文字が区別されます)
- または 0 から 9

例:

`abcdef0123456789abcdef0123456789`

or

40 文字の組み合わせ:

- a-f または A-F (大文字と小文字が区別されます)

or

- 0-9

例:

`abcdef0123456789abcdef0123456789abcdef01`

or

43 文字の組み合わせ:
 
- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)
- 等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

or

54 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/) またはプラス記号 (+)
- 2 つの等号 (==) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOP==`

or

86 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/) またはプラス記号 (+)
- 2 つの等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`


## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、実行時にアクセス トークン [と交換する OAuth アプリケーションと承認サーバー](/azure/active-directory/develop/active-directory-how-applications-are-added) にのみ知られているセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- クライアント シークレット コンテキストのパターン。
- Base64 でエンコードされた 128 ビットの対称キーのパターン。
- 128 ビットの対称キーでエンコードされた 16 進数のパターン。
- 160 ビットの対称キーでエンコードされた 16 進数のパターン。
- Base64 でエンコードされた 256 ビットの対称キーのパターン。
- Base64 でエンコードされた 320 ビットの対称キーのパターン。
- Base64 でエンコードされた 512 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName、Id、AccountName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_clientsecretcontext"></a>Keyword_ClientSecretContext:

- 秘密
- token
- auth
- Securestring
- キー

### <a name="keyword_symmetrickey128"></a>Keyword_SymmetricKey128:

- 秘密
- キー
- password
- Pw

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

- dapi
- キー
- 秘密
- token
- password
- Pw

### <a name="keyword_symmetrickey160hex"></a>Keyword_SymmetricKey160Hex:

- token

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey320"></a>Keyword_SymmetricKey320:

- code=
- キー

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
