---
title: Microsoft 365 Defender のカスタム検出の概要
description: 高度な検索を使用してカスタム検出を作成し、アラートを生成する方法を理解する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928810"
---
# <a name="custom-detections-overview"></a>カスタム検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

カスタム検出を使用すると、侵害の疑いのあるアクティビティや正しく構成されていないエンドポイントなど、さまざまなイベントやシステム状態を事前に監視して対応できます。 これは、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールによって可能になります。

カスタム検出は高度な検索 [に](advanced-hunting-overview.md)対応します。強力で柔軟なクエリ言語が提供され、ネットワークから広範なイベントおよびシステム情報を扱います。 一致する場合は常に、一定の間隔で実行し、アラートを生成し、対応アクションを実行する設定を行うことができます。

カスタム検出では、次の機能が提供されます。
- 高度な検索クエリから構築されたルールベースの検出に関するアラート
- 自動応答アクション

## <a name="related-topic"></a>関連トピック
- [カスタム検出ルールの作成と管理](custom-detection-rules.md)
- [高度な検出の概要](advanced-hunting-overview.md)
