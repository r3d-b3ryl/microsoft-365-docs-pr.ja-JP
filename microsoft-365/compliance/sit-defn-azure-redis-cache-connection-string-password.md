---
title: Azure Redis cache 接続文字列のパスワード エンティティ定義 (プレビュー)
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
description: Azure Redis cache 接続文字列のパスワードの機密情報の種類エンティティ定義。
ms.openlocfilehash: 04d79512c7740401e81ba5089b57734d7f8f1961
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995922"
---
# <a name="azure-redis-cache-connection-string-password-preview"></a>Azure Redis cache 接続文字列パスワード (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される最大 20,000 文字の組み合わせ。

or

文字、数字、特殊文字で構成される 44 文字の組み合わせ。

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

次で構成される 43 文字の任意の組み合わせ。

- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)
- 等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、[Azure Cache for Redis サーバー](/azure/azure-cache-for-redis/)への接続に使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた文字列リテラルのパターン。
- Base64 でエンコードされた 256 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName、ID のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey
