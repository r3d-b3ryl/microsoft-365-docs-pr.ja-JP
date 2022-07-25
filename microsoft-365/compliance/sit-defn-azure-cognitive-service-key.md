---
title: Azure Cognitive Service キー エンティティ定義 (プレビュー)
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
description: Azure Cognitive Service キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: cf54aa6886aa6cfed9d7540ebc8e5756994d9efb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996477"
---
# <a name="azure-cognitive-service-key-preview"></a>Azure Cognitive Service キー (プレビュー)

## <a name="format"></a>フォーマット

文字と数字で構成される 32 文字の組み合わせ。

## <a name="pattern"></a>パターン

次で構成される 32 文字の任意の組み合わせ。
 
- a-f または A-F (大文字と小文字が区別されます)
- または 0 から 9

例:

`abcdef0123456789abcdef0123456789`

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、[Azure Cognitive Services](/azure/search/search-security-api-keys) への要求を認証するために使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- 128 ビットの対称キーでエンコードされた 16 進数のパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。
キーワード

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

- dapi
- キー
- 秘密
- token
- password
- Pw