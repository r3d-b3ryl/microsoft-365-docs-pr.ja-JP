---
title: Microsoft 365 Defender API の概要
description: Microsoft 365 Defenderで使用可能な API について説明します
keywords: api, apis, 概要, インシデント, インシデント, 脅威の捜索, Microsoft 365 Defender
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
ms.custom: api
ms.openlocfilehash: ec4a497fd0ee428fbc664ae064ec95f74fcdce85
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172417"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Microsoft 365 Defender API の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft 365 Defenderは、統合対応プラットフォームの上に構築されています。

Microsoft 365 Defender API を使用して、共有インシデントテーブルと高度なハンティング テーブルに基づいてワークフローを自動化します。

- **[組み合わされたインシデント キュー](api-incident.md)** - インシデント API の下で、完全な攻撃範囲と影響を受けたすべての資産をグループ化することで、重要な内容に焦点を当てます。

- **[製品間の脅威の捜索](api-advanced-hunting.md)** - セキュリティ チームの組織の知識を活用して、侵害の兆候を探します。独自のカスタム クエリを作成して、複数の保護製品にわたって収集された生データを選別します。

- **[イベント ストリーミング API](streaming-api.md)** - 1 つのデータ ストリームで発生したイベントとアラートをリアルタイムで送信します。

これらのMicrosoft 365 Defender固有の API と共に、他の各セキュリティ製品は、独自の機能を活用するために役立つ[追加の API を](api-articles.md)公開します。

> [!NOTE]
> 統合ポータルへの移行は、Microsoft Defender for Endpoint API に基づいて PowerBi ダッシュボードに影響を与えるべきではありません。 対話型ポータルの切り替えに関係なく、既存の API を引き続き操作できます。

## <a name="learn-more"></a>詳細情報

| **API にアクセスする方法を理解する** |
|-|
| [API クォータとライセンスについて学習する](api-terms.md) |
| [Microsoft 365 Defender API にアクセスする](api-access.md) |
| **アプリのビルド** |
| ["Hello world" アプリを作成する](api-hello-world.md) |
| [ユーザーの代わりにMicrosoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md) |
| [ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する](api-create-app-web.md) |
| [Microsoft 365 Defender API へのマルチテナント パートナー アクセス権を持つアプリを作成する](api-partner-access.md) |
| **アプリのトラブルシューティングと保守** |
| [API エラー コードについて](api-error-codes.md) |
| [Azure Key Vaultを使用してアプリ内のシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [ユーザー サインイン用に OAuth 2.0 承認を実装する](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
