---
title: Azure Service Bus 共有アクセス署名エンティティ定義 (プレビュー)
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
description: Azure Service Bus 共有アクセス署名の機密情報の種類エンティティ定義。
ms.openlocfilehash: f9464bb2700bc4e4e186d33e451a2b286acca54f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996317"
---
# <a name="azure-service-bus-shared-access-signature-preview"></a>Azure Service Bus 共有アクセス署名 (プレビュー)

## <a name="format"></a>フォーマット

パターンの一部ではない等号 (=) で終わる文字、数字、特殊文字で構成される 44 文字の組み合わせ。

or

パターンの一部ではない等号 (=) で終わる文字、数字、特殊文字で構成される最大 76 文字の組み合わせ。

## <a name="pattern"></a>パターン

次で構成される 43 文字の任意の組み合わせ。
 
- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)
- パターンの一部ではない等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

or

43 ~ 73 文字の任意の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- またはパーセント記号 (%)
- サフィックス '%3d' で終わる (大文字と小文字は区別されません)

例: 

`abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDE%3D`

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、特定の権限を持つ[Azure Service Bus リソース](/azure/service-bus-messaging/service-bus-authentication-and-authorization)へのアクセスをユーザーに付与するために使用されるセキュリティ情報と一致するように設計されています。

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた 256 ビットの対称キーのパターン。
- URL エンコードされた 256 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName、ID のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey256urlencoded"></a>Keyword_SymmetricKey256UrlEncoded:

- sig=
- キー
- token
- 秘密
- password
