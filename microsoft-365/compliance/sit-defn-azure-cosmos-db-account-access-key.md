---
title: Azure COSMOS DB アカウント アクセス キー エンティティ定義 (プレビュー)
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
description: Azure COSMOS DB アカウント アクセス キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: 7912a02ea7b041603955ab4d88fe00966ae9cf94
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996037"
---
# <a name="azure-cosmos-db-account-access-key-preview"></a>Azure COSMOS DB アカウント アクセス キー (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 88 文字の組み合わせ。

## <a name="pattern"></a>パターン

次で構成される 86 文字の任意の組み合わせ。

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

この SIT は、 [Azure COSMOS Database](/azure/cosmos-db/secure-access-to-data) アカウントの管理リソースへのアクセスを提供するために使用されるセキュリティ情報と一致するように設計されています。

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた 512 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName、Id、AccountName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
