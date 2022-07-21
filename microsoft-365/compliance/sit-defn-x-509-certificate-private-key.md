---
title: X.509 証明書秘密キー エンティティ定義 (プレビュー)
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
description: X.509 証明書秘密キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: bdf6666060e62312ecfaa260ea2521161e2db7a6
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950545"
---
# <a name="x509-certificate-private-key-preview"></a>X.509 証明書秘密キー (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される最大 20,000 文字の組み合わせ。

or

大文字、スペース、ダッシュで構成される最大 40 文字の組み合わせ。

## <a name="pattern"></a>パターン

最大 20,000 文字の組み合わせ:
 
- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)

最大 2 つの等号 (==)

例:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

or

5 ダッシュ (-)

最大 30 文字の組み合わせ:

- A から Z (大文字と小文字が区別されます) 
- スペース
- 5 ダッシュ (-)

例:

`-----BEGIN PRIVATE KEY-----`


## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、[SSL 証明書](/azure/key-vault/certificate-scenarios)のプライベート コンポーネントとして使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた文字列リテラルのパターン。
- 証明書秘密キー ヘッダーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII

### <a name="keyword_certificateprivatekeyheader"></a>Keyword_CertificatePrivateKeyHeader:

- キー
