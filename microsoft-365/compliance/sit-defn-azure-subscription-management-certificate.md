---
title: Azure サブスクリプション管理証明書エンティティ定義 (プレビュー)
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
description: Azure サブスクリプション管理証明書の機密情報の種類エンティティ定義。
ms.openlocfilehash: 7ce7b09fdeae6f9622a3aac4f92beb446715f8df
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995677"
---
# <a name="azure-subscription-management-certificate-preview"></a>Azure サブスクリプション管理証明書 (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される最大 20,000 文字の組み合わせ。

## <a name="pattern"></a>パターン

最大 20,000 文字の組み合わせ:
 
- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/) またはプラス記号 (+)
- 最大 2 つの等号 (==)

例:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、Azure によって提供される [クラシック デプロイ モデル](/azure/azure-resource-manager/management/deployment-models) で認証するために使用されるセキュリティ情報と一致するように設計されています。 Visual Studio や Azure SDK などの多くのプログラムとツールは、これらの証明書を使用して、さまざまな [Azure サービス](/azure/azure-api-management-certs)の構成とデプロイを自動化します。 

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた文字列リテラルのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII
