---
title: Google API キー エンティティ定義 (プレビュー)
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
description: Google API キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: 5aef61e28dee6624620d1f254434fb860f28f1af
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996567"
---
# <a name="google-api-key-preview"></a>Google API キー (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 39 文字の組み合わせ。

## <a name="pattern"></a>パターン

トークン プレフィックス (大文字と小文字が区別されます) 'AIza'

35 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- ダッシュ (-)
- 下線 (_) または下位スラッシュ (\)

例:

`AIzaefgh0123456789_-ABCDEFGHIJKLMNOPQRS`

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、クォータと課金のために API 要求をプロジェクトに関連付けるために使用されるプリンシパルなしで [Google REST API クライアント](https://cloud.google.com/docs/authentication/api-keys) を識別する単純な暗号化された文字列として使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた 210 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey210"></a>Keyword_SymmetricKey210:

- AIza
