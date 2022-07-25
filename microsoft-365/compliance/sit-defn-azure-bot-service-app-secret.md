---
title: Azure Bot Service アプリ シークレット エンティティ定義 (プレビュー)
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
description: Azure Bot Service アプリシークレットの機密情報の種類エンティティ定義。
ms.openlocfilehash: e8606c2baa3a788040bab972fd7c30613af48576
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996062"
---
# <a name="azure-bot-service-app-secret-preview"></a>Azure Bot Service アプリ シークレット (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される最大 40 文字の組み合わせ。

## <a name="pattern"></a>パターン

次で構成される最大 40 文字の組み合わせ。

- a-z (大文字と小文字は区別されません)
- 0-9
- ダッシュ (-)
- 下線 (_)
- dots (.) 
- またはチルダのアクセント (~)

例:

`abc7Q~defghijklmnopqrs0t123456789-_.~`

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

この SIT は、 [Azure Bot、WebChat チャネル、およびクライアント アプリケーション](/azure/bot-service/bot-builder-concept-authentication-types?view=azure-bot-service-4.0)間の安全な通信を確立するために使用されるセキュリティ情報と一致するように設計されています。  

いくつかの主なリソースが使用されます。

- 特定の形式のクライアント シークレットのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。


## <a name="keywords"></a>キーワード

### <a name="keyword_appsecret"></a>Keyword_AppSecret:

- 秘密
- password
- キー
