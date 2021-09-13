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
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192561"
---
# <a name="custom-detections-overview"></a>カスタム検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

カスタム検出を使用すると、侵害の疑いのあるアクティビティや誤った構成されたエンドポイントなど、さまざまなイベントやシステム状態を事前に監視して対応できます。 これは、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールによって可能になります。

カスタム検出は高度な検索 [で](advanced-hunting-overview.md)機能します。これは、ネットワークからの広範なイベントおよびシステム情報をカバーする強力で柔軟なクエリ言語を提供します。 一定の間隔で実行し、アラートを生成しながら一致するたびに応答アクションを実行するように設定できます。

カスタム検出では、次の機能が提供されます。
- 高度な検索クエリから構築されたルールベースの検出に関するアラート
- 自動応答アクション

## <a name="see-also"></a>関連項目
- [カスタム検出ルールの作成と管理](custom-detection-rules.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint から高度なハンティング クエリを移行する](advanced-hunting-migrate-from-mde.md)
