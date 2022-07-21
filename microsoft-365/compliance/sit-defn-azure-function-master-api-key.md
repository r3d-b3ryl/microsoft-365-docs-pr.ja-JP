---
title: Azure Function Master / API キー エンティティ定義 (プレビュー)
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
description: Azure Function Master/API キーの機密情報の種類エンティティ定義。
ms.openlocfilehash: 3a2fd12125d220bb0de3d0f4217ca6e11f58ea56
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950763"
---
# <a name="azure-function-master--api-key-preview"></a>Azure Function Master / API キー (プレビュー)  

## <a name="format"></a>フォーマット

文字、数字、特殊文字で構成される 56 文字の組み合わせ。

or

文字、数字、特殊文字で構成される最大 90 文字の組み合わせ。

## <a name="pattern"></a>パターン

以下で構成される 54 文字の任意の組み合わせ。

- a-z (大文字と小文字は区別されません)
- 0-9
- スラッシュ (/)
- またはプラス記号 (+)
- 2 つの等号 (=) で終わる

例:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOP==`

or

54 ~ 84 文字の組み合わせ。

- a-z (大文字と小文字は区別されません)
- 0-9
- またはパーセント記号 (%)
- サフィックス '%3d%3d' で終わる (大文字と小文字は区別されません)

例:

abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDEF0123456789%3D%3D


## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、承認レベルが匿名以外の値に設定されている場合に [Azure Function API](/azure/azure-functions/functions-how-to-use-azure-function-app-settings?tabs=portal) を要求するために使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Base64 でエンコードされた 320 ビットの対称キーのパターン。
- URL エンコードされた 320 ビットの対称キーのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。
- ボキャブラリのディクショナリ。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。


## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickey320"></a>Keyword_SymmetricKey320:

- code=
- キー

### <a name="keyword_symmetrickey320urlencoded"></a>Keyword_SymmetricKey320UrlEncoded:

- code=
- キー
