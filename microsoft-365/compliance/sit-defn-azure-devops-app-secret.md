---
title: Azure DevOps アプリ シークレット エンティティ定義 (プレビュー)
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
description: Azure DevOps アプリシークレット機密情報の種類エンティティ定義。
ms.openlocfilehash: d689cb184cd329d1d5686a5dde486305b5375078
ms.sourcegitcommit: 771f7bbb241f910b3e16b4d1f9bbd9c0c8c6fa34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67309353"
---
# <a name="azure-devops-app-secret-preview"></a>Azure DevOps アプリ シークレット (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 52 文字の組み合わせ。

## <a name="pattern"></a>パターン

次で構成される 52 文字の任意の組み合わせ。
 
- a-z または A-Z (大文字と小文字が区別されます)
- または 2 から 7

例:

`abcdefghijklmnopqrstuvwxyz234567abcdefghijklmnopqrst`


## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、[Azure DevOps REST API アクセス](/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops)の Web アプリ ユーザーの認証に使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Base32 でエンコードされた 256 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリの辞書

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey256b32"></a>Keyword_SymmetricKey256B32:

- Pat
- token
- Ado
- Vsts
- azuredevops
- visualstudio.com
- dev.azure.com
