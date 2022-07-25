---
title: GitHub 個人用アクセス トークン エンティティ定義 (プレビュー)
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
description: GitHub 個人用アクセス トークンの機密情報の種類エンティティ定義。
ms.openlocfilehash: e1da4eaf09ef480ad29928d8066dc91612cf779e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996602"
---
# <a name="github-personal-access-token-preview"></a>GitHub 個人用アクセス トークン (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 40 文字の組み合わせ。

or

URL で使用されるユーザー名とパスワードのペア。

or

文字と数字で構成される 40 文字の組み合わせ。

## <a name="pattern"></a>パターン

- トークン プレフィックス (大文字と小文字が区別されます) 'ghp_'、'gho_'、'ghu_'、'ghs_'、または 'ghr_'
- 36 の任意の組み合わせ 
- a-z (大文字と小文字が区別されない) または 0 から 9

例:

`ghp_abcdefghijklmnopqrstuvwxyzABCD012345`

or

さまざまな URL のユーザー名とパスワードの形式を次に示します。
 
`https://username:********@contoso.com/` <br>

`ftp://username:********@contoso.com:20/`<br>


or

40 文字の組み合わせ:

- a-f または A-F (大文字と小文字が区別される) または 0 から 9

例:

`abcdef0123456789abcdef0123456789abcdef01`

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、 [GitHub API またはコマンド ライン](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)を使用する場合に GitHub に対する認証の代替パスワードとして使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- 識別可能な GitHub PAT のパターン。
- URL のユーザー ログイン資格情報のパターン。
- 160 ビットの対称キーでエンコードされた 16 進数のパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_githubpatidentifiablesecret"></a>Keyword_GitHubPatIdentifiableSecret:

- gh_

### <a name="keyword_logincredentialsinurl"></a>Keyword_LoginCredentialsInUrl:

- ://

### <a name="keyword_symmetrickey160hex"></a>Keyword_SymmetricKey160Hex:

- token
