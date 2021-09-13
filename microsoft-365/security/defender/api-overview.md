---
title: API のMicrosoft 365 Defender概要
description: アプリ内で使用可能な API についてMicrosoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214614"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>API のMicrosoft 365 Defender概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft 365 Defenderは、統合対応プラットフォームの上に構築されています。

共有インシデントテーブルMicrosoft 365 Defender高度なハンティング テーブルに基づいてワークフローを自動化するには、次の API を使用します。

- **[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃スコープ全体と影響を受けたすべてのアセットをグループ化して、重要な機能に重点を置きます。

- **[製品間の](api-advanced-hunting.md)** 脅威の検出 - セキュリティ チームの組織の知識を活用して、複数の保護製品で収集された生データをふるいにかけ、独自のカスタム クエリを作成することで、侵害の兆候を探します。

ストリーミング API [を使用して](../defender-endpoint/raw-data-export.md) 、1 つのデータ ストリーム内で発生するインスタンスからのリアルタイム イベントとアラートを配信します。

これらの特定のMicrosoft 365 Defender API に加え、他の各セキュリティ製品は、独自の機能を利用するために追加の[API](api-articles.md)を公開します。

> [!NOTE]
> 統合ポータルへの移行は、Microsoft Defender for Endpoint API に基づく PowerBi ダッシュボードに影響を与える必要があります。 対話型ポータルの移行に関係なく、既存の API を引き続き操作できます。

## <a name="learn-more"></a>詳細情報

| **API にアクセスする方法を理解する** |
|-|
| [API クォータとライセンスの詳細](api-terms.md) |
| [API にMicrosoft 365 Defenderする](api-access.md) |
| **アプリのビルド** |
| ['Hello world' アプリを作成する](api-hello-world.md) |
| [ユーザーに代わって API にMicrosoft 365 Defenderするアプリを作成する](api-create-app-user-context.md) |
| [ユーザーなしでアプリを作成してMicrosoft 365 Defenderにアクセスする](api-create-app-web.md) |
| [複数テナントパートナーによる API へのアクセス権を持つアプリをMicrosoft 365 Defenderする](api-partner-access.md) |
| **アプリのトラブルシューティングと保守** |
| [API エラー コードについて](api-error-codes.md) |
| [Azure Key Vault を使用してアプリ内のシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [ユーザー サインインの OAuth 2.0 承認を実装する](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |