---
title: Microsoft の脅威保護のカスタム検出の概要
description: 高度な検索を使用してユーザー設定の検出を作成し、通知を生成する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498353"
---
# <a name="custom-detections-overview"></a>カスタム検出の概要

**適用対象:**
- Microsoft Threat Protection

カスタム検出を使用すると、疑いのある違反のアクティビティや不適切なエンドポイントを含む、さまざまなイベントやシステム状態を事前に監視して応答することができます。 これは、通知を自動的にトリガーするカスタマイズ可能な検出ルール、および応答アクションによって可能になります。

カスタム検出は[高度な](advanced-hunting-overview.md)検索を使用して動作します。これにより、さまざまなイベントおよびシステム情報をネットワークからカバーする強力で柔軟なクエリ言語が提供されます。 それらを定期的に実行するように設定して、一致するものがある場合は警告を生成し、応答アクションを実行することができます。

カスタム検出の提供:
- 高度な検索クエリから構築されたルールベースの検出に関する警告
- 自動応答アクション

## <a name="related-topic"></a>関連トピック
- [カスタム検出ルールを作成および管理する](custom-detection-rules.md)
- [高度な検出の概要](advanced-hunting-overview.md)