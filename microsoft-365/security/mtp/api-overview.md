---
title: Microsoft 365 Defender API の概要
description: Microsoft 365 Defender で利用可能な API について説明します。
keywords: api, apis, 概要, インシデント, インシデント, 脅威の検出, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931004"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Microsoft 365 Defender API の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender は、統合対応プラットフォームの上に構築されています。

Microsoft 365 Defender API を使用して、共有インシデントと高度なハンティング テーブルに基づいてワークフローを自動化します。

- **[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃の全範囲と影響を受けたすべての資産をグループ化することで、重要な機能に重点を置きます。

- **[製品間](api-advanced-hunting.md)** の脅威の検出 - セキュリティ チームの組織の知識を活用して、侵害の兆候を探します。独自のカスタム クエリを作成して、複数の保護製品にわたって収集された生データをふるい分けします。

これらの Microsoft 365 Defender 固有の API と共に、他[](api-articles.md)の各セキュリティ製品は、独自の機能を活用するのに役立つ追加の API を公開します。

## <a name="learn-more"></a>詳細情報

| **API にアクセスする方法を理解する** |
|-|
| [API クォータとライセンスについて](api-terms.md) |
| [Microsoft 365 Defender API へのアクセス](api-access.md) |
| **アプリのビルド** |
| ["Hello world" アプリを作成する](api-hello-world.md) |
| [ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md) |
| [ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する](api-create-app-web.md) |
| [マルチテナント パートナーが Microsoft 365 Defender API にアクセスできるアプリを作成する](api-partner-access.md) |
| **アプリのトラブルシューティングと保守** |
| [API のエラー コードについて](api-error-codes.md) |
| [Azure Key Vault を使用してアプリのシークレットを管理する](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [ユーザー サインイン用の OAuth 2.0 承認を実装する](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
