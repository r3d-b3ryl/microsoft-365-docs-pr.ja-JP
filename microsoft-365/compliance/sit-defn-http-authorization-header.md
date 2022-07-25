---
title: Http 承認ヘッダー エンティティ定義 (プレビュー)
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
description: Http 承認ヘッダーの機密情報の種類エンティティ定義。
ms.openlocfilehash: b72934a88f85c0245320baa4b774d3c69196eb47
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997647"
---
# <a name="http-authorization-header-preview"></a>Http 承認ヘッダー (プレビュー)

## <a name="format"></a>フォーマット

HTTP 要求で使用される承認ヘッダー。

## <a name="pattern"></a>パターン

次のようなさまざまな認証ヘッダー形式:
 
`authorization: basic ********` <br>
`authorization: bearer ********` <br>
`authorization: digest ********` <br>
`authorization: negotiate ********` <br>

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

この SIT は、[認証と承認のために HTTP 要求](/dotnet/api/system.net.http.headers.httprequestheaders.authorization?view=netframework-4.8)のヘッダーで使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- Http 承認ヘッダーのパターン。
- CredentialName、CredentialFeatures、ResourceType のパターン。
- モックアップ値、やり直し、プレースホルダーのパターン。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。

## <a name="keywords"></a>キーワード

### <a name="keyword_httpauthorizationheader"></a>Keyword_HttpAuthorizationHeader:

- 承認

