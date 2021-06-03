---
title: Defender API Microsoft 365の概要
description: Defender で使用可能な API についてMicrosoft 365する
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
ms.openlocfilehash: b19a6072be5f97b90c117f053ccae4593587c43d
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730898"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Defender API Microsoft 365の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft 365Defender は統合対応プラットフォームの上に構築されています。

Defender API Microsoft 365使用して、共有インシデントテーブルと高度なハンティング テーブルに基づいてワークフローを自動化します。

- **[複合インシデント キュー](api-incident.md)** - インシデント API の下で、攻撃スコープ全体と影響を受けたすべてのアセットをグループ化して、重要な機能に重点を置きます。

- **[製品間の](api-advanced-hunting.md)** 脅威の検出 - セキュリティ チームの組織の知識を活用して、複数の保護製品で収集された生データをふるいにかけ、独自のカスタム クエリを作成することで、侵害の兆候を探します。

ストリーミング API [を使用して](../defender-endpoint/raw-data-export.md) 、1 つのデータ ストリーム内で発生するインスタンスからのリアルタイム イベントとアラートを配信します。


Defender 固有の API Microsoft 365に加え、他の各セキュリティ製品は、独自[](api-articles.md)の機能を利用するために追加の API を公開します。


> [!NOTE]
> 統合ポータルへの移行は、Microsoft Defender for Endpoint API に基づく PowerBi ダッシュボードに影響を与える必要があります。 対話型ポータルの移行に関係なく、既存の API を引き続き操作できます。


## <a name="learn-more"></a>詳細情報

| **API にアクセスする方法を理解する** |
|-|
| [API クォータとライセンスの詳細](api-terms.md) |
| [Defender API Microsoft 365アクセスする](api-access.md) |
| **アプリのビルド** |
| ['Hello world' アプリを作成する](api-hello-world.md) |
| [ユーザーに代わって Defender API Microsoft 365アクセスするアプリを作成する](api-create-app-user-context.md) |
| [ユーザーなしで Defender にアクセスMicrosoft 365アプリを作成する](api-create-app-web.md) |
| [複数テナントパートナーが Defender API にアクセスできるアプリMicrosoft 365作成する](api-partner-access.md) |
| **アプリのトラブルシューティングと保守** |
| [API エラー コードについて](api-error-codes.md) |
| [Azure Key Vault を使用してアプリ内のシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [ユーザー サインインの OAuth 2.0 承認を実装する](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |