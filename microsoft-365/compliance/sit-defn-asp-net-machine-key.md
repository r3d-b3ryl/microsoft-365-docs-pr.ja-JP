---
title: ASP.NET マシン キー エンティティ定義 (プレビュー)
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
description: マシン キーの機密情報の種類エンティティ定義を ASP.NET します。
ms.openlocfilehash: 23dc07febc51425fb9b7f79d851848e00d5d974d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996967"
---
# <a name="aspnet-machine-key-preview"></a>ASP.NET マシン キー (プレビュー)

## <a name="format"></a>フォーマット

XML 構成の対称キー。

## <a name="pattern"></a>パターン

XML のさまざまな対称キー形式。たとえば、次のようになります。

```xml
<machineKey decryptionKey="******** </br> 
<machineKey validationKey="********
```
## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義


この SIT は、ASP.NET フォーム認証でデータを暗号化またはハッシュし、状態 [を](/dotnet/api/system.web.security.machinekey?view=netframework-4.8) 表示するために使用されるセキュリティ情報と一致するように設計されています。 

いくつかの主なリソースが使用されます。

- xml ファイル内の対称キー コンテキストのパターン。
- CredentialName、CredentialFeatures、AccountIdentityName、AccountIdentityValue、ResourceType、ResourceName のパターン。

パターンは、実際の資格情報と妥当な信頼度を一致するように設計されています。 パターンは、例として書式設定された資格情報と一致しません。 実際のシークレット値が表示される位置のモックアップ値、編集された値、プレースホルダー (資格情報の種類や使用状況の説明など) は一致しません。


## <a name="keywords"></a>キーワード

### <a name="keyword_symmetrickeycontextinxml"></a>Keyword_SymmetricKeyContextInXml:

- password
- キー
- Connectionstring

