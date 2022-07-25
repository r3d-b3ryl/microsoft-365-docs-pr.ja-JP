---
title: Azure SQL接続文字列エンティティ定義 (プレビュー)
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
description: 接続文字列の機密情報の種類エンティティ定義をAzure SQLします。
ms.openlocfilehash: 7091c50d96f22370358f5743a3992a10025ea29f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996302"
---
# <a name="azure-sql-connection-string-preview"></a>Azure SQL接続文字列 (プレビュー)

## <a name="format"></a>フォーマット

最大 20,000 文字の文字、数字、特殊文字の組み合わせ。

or

一般的な認証プロセスで使用されるユーザー名とパスワードのペア。


## <a name="pattern"></a>パターン

次で構成される最大 20,000 文字の任意の組み合わせ。

- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)
- 最大 2 個
- 等号 (=)

例: 

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

or

バリアントのユーザー名とパスワードの形式(例:

`username=...;password=********;` <br>
`user id=...;password=********;` <br>
`uid=...;pwd=********;` <br>
`DB_USER=...;DB_PASS=********;` <br>
`Service Account=...;Password=********;` <br>


## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、[Azure SQL データベース](/azure/sql-database/sql-database-aad-authentication-configure)への接続に使用されるセキュリティ情報と一致するように設計されています。

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた文字列リテラルのパターン。
- プレーンテキストのユーザー名とパスワードのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII

### <a name="keyword_logincredentials"></a>Keyword_LoginCredentials:

- password
- Pw
- DB_
