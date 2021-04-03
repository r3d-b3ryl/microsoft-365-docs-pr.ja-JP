---
title: Microsoft Defender ATP でのカスタム検出の概要
ms.reviewer: ''
description: 高度な検出を使用してカスタム検出を作成し、アラートを生成する方法を理解する
keywords: カスタム検出、アラート、検出ルール、高度な狩猟、ハント、クエリ、応答アクション、間隔、mdatp、microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500648"
---
# <a name="custom-detections-overview"></a>カスタム検出の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


カスタム検出を使用すると、違反の疑いのあるアクティビティやデバイスの設定ミスなど、さまざまなイベントやシステム状態を事前に監視して対応できます。 これを行うには、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールを使用します。

カスタム検出は高度な検索 [で](advanced-hunting-overview.md)機能します。これは、ネットワークからの広範なイベントおよびシステム情報をカバーする強力で柔軟なクエリ言語を提供します。 一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。

カスタム検出では、次の機能が提供されます。
- 高度な検索クエリから構築されたルールベースの検出に関するアラート
- ファイルとデバイスに適用される自動応答アクション

## <a name="related-topics"></a>関連項目
- [検出ルールの作成](custom-detection-rules.md)
- [検出ルールの表示と管理](custom-detections-manage.md)
- [高度な追求の概要](advanced-hunting-overview.md)
