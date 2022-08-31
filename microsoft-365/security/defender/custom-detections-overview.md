---
title: Microsoft 365 Defenderでのカスタム検出の概要
description: 高度なハンティングを使用してカスタム検出を作成し、アラートを生成する方法を理解する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 5d369bbea463b758a4ce29cb16f66e52488039e1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67474646"
---
# <a name="custom-detections-overview"></a>カスタム検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

カスタム検出を使用すると、侵害の疑いのあるアクティビティや不適切な構成されたエンドポイントなど、さまざまなイベントやシステム状態を事前に監視して対応できます。 これは、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールによって可能になります。

カスタム検出は [高度なハンティング](advanced-hunting-overview.md)と連携し、ネットワークからの広範なイベント情報とシステム情報を網羅する強力で柔軟なクエリ言語を提供します。 一定の間隔で実行し、アラートを生成しながら一致するたびに応答アクションを実行するように設定できます。

カスタム検出では、次の機能が提供されます。
- 高度なハンティング クエリから構築されたルールベースの検出のアラート
- 自動応答アクション

## <a name="see-also"></a>関連項目
- [カスタム検出ルールの作成と管理](custom-detection-rules.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [高度なハンティング クエリをMicrosoft Defender for Endpointから移行する](advanced-hunting-migrate-from-mde.md)
