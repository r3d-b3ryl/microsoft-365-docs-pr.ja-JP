---
title: Azure Databricks 個人用アクセス トークン エンティティ定義 (プレビュー)
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
description: Azure Databricks 個人用アクセス トークンの機密情報の種類エンティティ定義。
ms.openlocfilehash: 9dfe6cb2616cc389cd122b4430c717bd099900f0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996017"
---
# <a name="azure-databricks-personal-access-token-preview"></a>Azure Databricks 個人用アクセス トークン (プレビュー) 

## <a name="format"></a>フォーマット

文字と数字で構成される 32 文字の組み合わせ。

## <a name="pattern"></a>パターン

以下で構成される 32 文字の組み合わせ。
 
- a-f または A-F (大文字と小文字が区別されます)
- または 0 から 9

例:

`abcdef0123456789abcdef0123456789`

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、 [Azure Databricks REST API](/azure/databricks/administration-guide/access-control/tokens) への認証に使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- 128 ビットの対称キーでエンコードされた 16 進数のパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。


## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

dapi キー シークレット トークンパスワード pw
