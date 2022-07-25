---
title: Azure Bot Framework シークレット キー エンティティ定義 (プレビュー)
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
description: Azure Bot Framework シークレット キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: c436436b00dda8a5273939665920ef709ff164c5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996072"
---
# <a name="azure-bot-framework-secret-key-preview"></a>Azure Bot Framework シークレット キー (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 55 文字の組み合わせ。

or

文字、数字、特殊文字で構成される 63 文字の組み合わせ。

## <a name="pattern"></a>パターン

55 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- 下線 (_)
- またはドット (.)


`abcdefghijklmnopqrstuvwxyz.0123456789_ABCDEabcdefghijkl`

または 63 文字の場合

11 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- ダッシュ (-)
- または下線 (_)
- ドット

3 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- ダッシュ (-)
- または下線 (_)
- ドット

3 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- ダッシュ (-)
- または下線 (_)
- ドット

43 文字の組み合わせ

- a-z (大文字と小文字は区別されません)
- 0-9
- ダッシュ (-)
- または下線 (_)

例:

`abcdefghijk.lmn.opq.rstuvwxyz0123456789-_ABCDEFGHIJKLMNOPQRSTUV`


## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、[Azure Bot サービスから WebChat チャネル](/azure/bot-service/bot-service-channel-connect-webchat?view=azure-bot-service-4.0)に接続するために使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Base64 URL でエンコードされた 328 ビットの対称キーのパターン。
- Base64 URL でエンコードされた 360 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey328url"></a>Keyword_SymmetricKey328Url:

- botframework
- キー

### <a name="keyword_symmetrickey360url"></a>Keyword_SymmetricKey360Url:

- botframework
- キー
