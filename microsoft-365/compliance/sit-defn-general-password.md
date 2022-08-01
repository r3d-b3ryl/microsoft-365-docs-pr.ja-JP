---
title: 一般的なパスワード エンティティ定義 (プレビュー)
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
description: 一般的なパスワードの機密情報の種類エンティティ定義。
ms.openlocfilehash: ea800d6798a2068eb90ff02e1550e48606e7b1ea
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995492"
---
# <a name="general-password-preview"></a>一般的なパスワード (プレビュー)

## <a name="format"></a>フォーマット

最大 20,000 文字の文字、数字、特殊文字の組み合わせ。

or

コマンド ラインで使用されるサインイン資格情報

or

コード スニペットで使用されるプレーンテキスト パスワード

or

スクリプトで使用されるプレーンテキスト パスワード

or

XML 構成で使用されるプレーンテキスト パスワード

or

文字、数字、特殊文字で構成される 24 文字の組み合わせ。

or

文字と数字で構成される 32 文字の組み合わせ。

or

文字、数字、特殊文字で構成される 32 文字の組み合わせ。

or

文字、数字、特殊文字で構成される 44 文字の組み合わせ。

or

文字、数字、特殊文字の 88 文字の組み合わせ。

## <a name="pattern"></a>パターン

次で構成される最大 20,000 文字の任意の組み合わせ。

- a-z (大文字と小文字を区別しない)
- 0-9
- スラッシュ (/) またはプラス記号 (+)
- 最大 2 つの等号 (=)

例:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

or

次に示すように、さまざまなコマンド ライン サインイン資格情報の形式を指定します。 

`-u username:********`

または

`-u username -p ********`

または

`/f ... /p ********`

または

`-Password ********`

または

`-U username%********`

または

`-secrets:********`

例:

`zDbg.DataPuller.exe -secrets:eyJ`

or

コード スニペットのさまざまなパスワード形式。たとえば、次のようになります。

`new X509Certificates2(`

または

`ConvertTo-SecureString -String ********`

または

`password = "********"`

または

`"password" : "********"`

または

`UserPasswordCredential(`

例:

`password = "ZYXWVU_1";`

or

スクリプト内のさまざまなパスワード形式。たとえば、次のようになります。

`password = ********`

例:

`password=ZYXWVU_1`

or

XML のさまざまなパスワード形式は次のとおりです。

```xml
<secret>********</secret>
<password>********</password>
<setting name="password" value="********" >
<setting name="password">********</setting>
<setting name="password"><value>********</value></setting>
```

例:

`<secret>ZYXWVU_1</secret>`

or

次で構成される 22 文字の任意の組み合わせ。

- a-z (大文字と小文字を区別しない)
- 数字、スラッシュ、またはプラス記号
- 2 つの等号 (=) で終わる

例:

`abcdefgh0123456789/+AB==`

or

次で構成される 32 文字の任意の組み合わせ。

- a-f または A-F (大文字と小文字が区別される) または 0 から 9

例:

`abcdef0123456789abcdef0123456789`

or

次で構成される 32 文字の任意の組み合わせ。

- a-z (大文字と小文字を区別しない)
- 0-9
- スラッシュ (/) またはプラス記号 (+)

例:

`abcdefghijklmnopqr0123456789/+AB`

or

次で構成される 43 文字の任意の組み合わせ。

- a-z (大文字と小文字を区別しない)
- 0-9
- スラッシュ (/) またはプラス記号 (+)
- 等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

or

次で構成される 86 文字の任意の組み合わせ。

- a-z (大文字と小文字を区別しない)
- 0-9
- スラッシュ (/) またはプラス記号 (+)
- 2 つの等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>チェックサム

はい

## <a name="description"></a>説明

この SIT は、一般的なサインイン プロセスの [ユーザー ログイン プロセス](/azure/key-vault/quick-create-portal)で使用されるユーザー名とパスワードのようなセキュリティ情報と一致するように設計されています。 いくつかの主なリソースが使用されます。

- Base64 でエンコードされた文字列リテラルのパターン。
- コマンド ラインのパスワード コンテキストのパターン。
- コード内のパスワード コンテキストのパターン。
- スクリプト内のパスワード コンテキストのパターン。
- XML のパスワード コンテキストのパターン。
- Base64 でエンコードされた 128 ビットの対称キーのパターン。
- 16 進数でエンコードされた 128 ビットの対称キーのパターン。
- Base64 でエンコードされた 192 ビットの対称キーのパターン。
- Base64 でエンコードされた 256 ビットの対称キーのパターン。
- Base64 でエンコードされた 512 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName、ID、AccountName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリ語の辞書。


パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral

- MII

### <a name="keyword_passwordcontextincmdline"></a>Keyword_PasswordContextInCmdLine

- Certutil
- zdbg
- 秘密
- VSTS_TOKEN
- カール
- PowerShell
- ps1
- -u
- Smc
- AutoLogon
- Ldifde
- Rclone
- --env
- Signtool
- winexe
- ネット

## <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode

- キー
- x509c
- 資格 情報
- password
- Pw
- Securestring

### <a name="keyword_passwordcontextinscript"></a>Keyword_PasswordContextInScript

- 秘密
- password
- Pw

### <a name="keyword_passwordcontextinxml"></a>Keyword_PasswordContextInXml

- userpass
- password
- Pw
- Connectionstring
- キー
- 資格 情報
- token
- Sas
- 秘密

### <a name="keyword_symmetrickey128"></a>Keyword_SymmetricKey128

- 秘密
- キー
- password
- Pw

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex

- dapi
- キー
- 秘密
- token
- password
- Pw

### <a name="keyword_symmetrickey192"></a>Keyword_SymmetricKey192

- password
- -p
- azurecr

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512

- SharedAccessKey
- AccountKey
