---
title: Amazon S3 クライアント シークレット アクセス キー エンティティ定義 (プレビュー)
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
description: Amazon S3 クライアント シークレット アクセス キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: c3026beae856097e221063732f65b805a3fd05c2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995842"
---
# <a name="amazon-s3-client-secret-access-key-preview"></a>Amazon S3 クライアント シークレット アクセス キー (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 40 文字の組み合わせ。 

## <a name="pattern"></a>パターン

13 桁の数字:

以下で構成される 40 文字の組み合わせ。 

- a-z (大文字と小文字を区別しない) 
- 0-9 
- スラッシュ (/) またはプラス記号 (+) 

例: 

`abcdefghijklmnopqrst0123456789/+ABCDEFGH`

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、[Amazon Web Services](/toolkit-for-eclipse/v1/user-guide/setup-credentials.html) へのアクセスに使用されるセキュリティ情報と一致するように設計されています。


いくつかの主なリソースが使用されます。 
 
- Base64 でエンコードされた 240 ビットの対称キーのパターン。 
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。 
- モックアップ値、やり直し、プレースホルダーのパターン。 
- ボキャブラリ語の辞書。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。 

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey240"></a>Keyword_SymmetricKey240: 

- 秘密 
- キー 