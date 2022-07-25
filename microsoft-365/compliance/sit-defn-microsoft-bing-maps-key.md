---
title: Microsoft Bing マップ キー エンティティ定義 (プレビュー)
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
description: Microsoft Bingでは、キーの機密情報の種類のエンティティ定義がマップされます。
ms.openlocfilehash: 6f25ec9716be33a0e2bbe404f12742dddad89250
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950820"
---
# <a name="microsoft-bing-maps-key-preview"></a>Microsoft Bing マップ キー (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 64 文字の組み合わせ。

## <a name="pattern"></a>パターン

64 文字の組み合わせ:

- a-z (大文字と小文字は区別されません)
- 0-9
- 下線 (_) またはハイフン (-)

例:

`abcdefghijklmnopqrstuvwxyz0123456789-_ABCDEabcdefghijklmnopqrstu`

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、[Bing地図 API](/bingmaps/getting-started/bing-maps-dev-center-help/getting-a-bing-maps-key) の呼び出しに使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Base64 URL でエンコードされた 384 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey384url"></a>Keyword_SymmetricKey384Url:

- virtualearth
- api/maps
- キー