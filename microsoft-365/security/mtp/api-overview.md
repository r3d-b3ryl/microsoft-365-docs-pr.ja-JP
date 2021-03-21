---
title: Microsoft 365 Defender API の概要
description: Microsoft 365 Defender で使用可能な API について説明します。
keywords: api, apis, 概要, インシデント, インシデント, 脅威の検出, microsoft 365 defender
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
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922188"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Microsoft 365 Defender API の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft 365 Defender は、統合対応プラットフォームの上に構築されています。

Microsoft 365 Defender API を使用して、共有インシデントと高度なハンティング テーブルに基づいてワークフローを自動化します。

- **[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃スコープ全体と影響を受けたすべてのアセットをグループ化して、重要な機能に重点を置きます。

- **[製品間の](api-advanced-hunting.md)** 脅威の検出 - セキュリティ チームの組織の知識を活用して、複数の保護製品で収集された生データをふるいにかけ、独自のカスタム クエリを作成することで、侵害の兆候を探します。

これらの Microsoft 365 Defender 固有の API と共に、他[](api-articles.md)の各セキュリティ製品は、独自の機能を利用するために追加の API を公開します。

## <a name="learn-more"></a>詳細情報

| **API にアクセスする方法を理解する** |
|-|
| [API クォータとライセンスの詳細](api-terms.md) |
| [Microsoft 365 Defender API へのアクセス](api-access.md) |
| **アプリのビルド** |
| ['Hello world' アプリを作成する](api-hello-world.md) |
| [ユーザーに代わって Microsoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md) |
| [ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する](api-create-app-web.md) |
| [Microsoft 365 Defender API へのマルチテナント パートナー アクセスでアプリを作成する](api-partner-access.md) |
| **アプリのトラブルシューティングと保守** |
| [API エラー コードについて](api-error-codes.md) |
| [Azure Key Vault を使用してアプリ内のシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [ユーザー サインインの OAuth 2.0 承認を実装する](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |