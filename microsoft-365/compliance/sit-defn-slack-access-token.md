---
title: Slack アクセス トークン エンティティ定義 (プレビュー)
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
description: Slack アクセス トークンの機密情報の種類エンティティ定義。
ms.openlocfilehash: 18e6654abe83bcbde40a832a74ec451c24f744b0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996817"
---
# <a name="slack-access-token-preview"></a>Slack アクセス トークン (プレビュー)

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される最大 34 文字の組み合わせ。

## <a name="pattern"></a>パターン

トークン プレフィックス (大文字と小文字が区別されます) 'xoxp-'、'xoxb-'、'xoxa-'、'xoxr-'、'xoxo-'、'xoxs-' または 'xoxe-'

最大 29 文字の組み合わせ:

- 29 a-z (大文字と小文字は区別されません)
- 0 ~ 9 またはハイフン (-)

例:

`xoxp-abcdef-abcdef-abcdef-abcdef` 

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、 [Slack プラットフォームの機能](https://api.slack.com/docs/token-type) (ボット トークン、ユーザー トークン、アプリ レベル のトークンなど) にアクセスするために使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Slack ユーザー/ボット/ワークスペース トークンのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_slacktokens"></a>Keyword_SlackTokens:

- Xox
