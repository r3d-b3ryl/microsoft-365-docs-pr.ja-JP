---
title: ユーザー ログイン資格情報エンティティ定義 (プレビュー)
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
description: ユーザー ログイン資格情報の機密情報の種類エンティティ定義。
ms.openlocfilehash: d75fcb7069e8393b5b03ce08071057ff503a4bfb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995497"
---
# <a name="user-login-credentials-preview"></a>ユーザー ログイン資格情報 (プレビュー)

## <a name="format"></a>フォーマット

一般的な認証プロセスで使用されるペアのユーザー名とパスワード。

or

PuTTY 接続マネージャーで使用されるペアのユーザー名とパスワード。

or

コード スニペットで使用されるプレーンテキスト パスワード。

or

文字、数字、特殊文字で構成される 88 文字の組み合わせ。

## <a name="pattern"></a>パターン

次のようなさまざまなユーザー名とパスワードの形式。
 
`username=...;password=********;` <br>
`user id=...;password=********;` <br>
`uid=...;pwd=********;` <br>
`DB_USER=...;DB_PASS=********;` <br>
`Service Account=...;Password=********;` <br>

or

```xml
An XML element <login>
An embeded XML element <login>
Inner XML content
An embeded XML element </login>
An embeded XML element <password>
Inner XML content
An embeded XML element </password>
An XML element </login>
```

例えば

`<login> <login>ZYXWVU_1</login> <password>ZY…`

or

コード スニペットのさまざまなパスワード形式。たとえば、次のようになります。

`new X509Certificates2(` <br>
`ConvertTo-SecureString -String ********` <br>
`password = "********"` <br>
`"password" : "********"`<br>
`UserPasswordCredential(` <br>

or

86 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)
- 2 つの等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、一般的な [ユーザー ログイン プロセス](/azure/key-vault/quick-create-portal)で使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- プレーンテキストのユーザー名とパスワードのパターン。
- PuTTYcm データベース ファイルのプレーンテキスト ユーザー名とパスワードのパターン。
- コード内のパスワード コンテキストのパターン。
- Base64 でエンコードされた 512 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName、Id、AccountName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_logincredentials"></a>Keyword_LoginCredentials:

- password
- Pw
- DB_

### <a name="keyword_logincredentialsputty"></a>Keyword_LoginCredentialsPutty:

- ログイン

### <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode:

- キー
- x509c
- 資格 情報
- password
- Pw
- Securestring

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
