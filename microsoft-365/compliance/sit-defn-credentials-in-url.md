---
title: URL の Crednetial
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
description: URL 機密情報の種類エンティティ定義の資格情報。
ms.openlocfilehash: f7a363539ec9bdd7fa0ddaab30ac7e2d20afb69b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996497"
---
# <a name="credentials-in-url"></a>URL の資格情報

## <a name="format"></a>フォーマット

URL で使用されるユーザー名とパスワードのペア

or

スクリプトで使用されるプレーンテキスト パスワード

## <a name="pattern"></a>パターン

次のように、さまざまな URL のユーザー名とパスワードの形式。 

`https://username:********@contoso.com/...`
`ftp://username:********@contoso.com:20/...`

例えば： `https://myuser:mypassword@localhost`

or

スクリプト内のさまざまなパスワード形式。たとえば、次のようになります。 

`password = ********...`

例:

`password=ZYXWVU_1`

## <a name="checksum"></a>チェックサム

不要

## <a name="description"></a>説明

この SIT は、クライアントの検証または識別 [のユーザー ログイン プロセス](/azure/key-vault/quick-create-portal)を行うために URL のトークンとして使用されるセキュリティ情報と一致するように設計されています。 いくつかの主なリソースが使用されます。

- URL のユーザー ログイン資格情報のパターン。
- スクリプト内のパスワード コンテキストのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_logincredentialsinurl"></a>Keyword_LoginCredentialsInUrl

- ://

### <a name="keyword_passwordcontextinscript"></a>Keyword_PasswordContextInScript

- 秘密
- password
- Pw
