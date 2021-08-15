---
title: カスタム検出の概要 (Microsoft 365 Defender
description: 高度な検出を使用してカスタム検出を作成し、アラートを生成する方法を理解する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0cbc377a43d37031de024cba6000ab76f59dcfc3283391c1ae356da88d143de9
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53867645"
---
# <a name="custom-detections-overview"></a>カスタム検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

カスタム検出を使用すると、侵害の疑いのあるアクティビティや誤った構成されたエンドポイントなど、さまざまなイベントやシステム状態を事前に監視して対応できます。 これは、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールによって可能になります。

カスタム検出は高度な検索 [で](advanced-hunting-overview.md)機能します。これは、ネットワークからの広範なイベントおよびシステム情報をカバーする強力で柔軟なクエリ言語を提供します。 一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。

カスタム検出では、次の機能が提供されます。
- 高度な検索クエリから構築されたルールベースの検出に関するアラート
- 自動応答アクション

## <a name="see-also"></a>関連項目
- [カスタム検出ルールの作成と管理](custom-detection-rules.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint から高度なハンティング クエリを移行する](advanced-hunting-migrate-from-mde.md)
