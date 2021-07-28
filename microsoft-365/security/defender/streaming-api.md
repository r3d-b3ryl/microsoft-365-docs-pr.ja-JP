---
title: ストリームMicrosoft 365 Defenderイベント
description: 高度なハンティング イベントMicrosoft 365 Defenderイベント ハブまたは Azure ストレージ アカウントにストリーミングするように構成する方法について説明します。
keywords: raw data export, streaming API, API, Event hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 431fd1271bf826ded53f88818741c5bbaa61e9b5
ms.sourcegitcommit: bef7bd019531317d083c1125f7d339750c450b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53588115"
---
# <a name="streaming-api"></a>ストリーミング API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングします。

Microsoft 365 Defenderは、高度なハン[ティングを](../defender/advanced-hunting-overview.md)通じてイベント[ハブや](/azure/event-hubs/)Azure ストレージ アカウントへのストリーミング[イベントをサポートします](/azure/event-hubs/)。

ストリーミング API の詳細Microsoft 365 Defenderビデオを参照[してください](https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga)。

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
:---|:---
[イベントを Azure イベント ハブにストリーミングする](streaming-api-event-hub.md)| テナントでストリーミング API を有効にし、高度なMicrosoft 365 Defenderをイベント ハブにストリーミングする方法[を](../defender/advanced-hunting-overview.md)構成する方法について説明します。
[Azure ストレージ アカウントにイベントをストリーミングする](streaming-api-storage.md)| テナントでストリーミング API を有効にし、高度なMicrosoft 365 Defenderを Azure[](advanced-hunting-overview.md)ストレージ アカウントにストリーミングするように構成する方法について説明します。


## <a name="related-topics"></a>関連項目
- [高度なハンティングの概要](../defender/advanced-hunting-overview.md)
- [Azure Event Hubs のドキュメント](/azure/event-hubs/)
- [Azure Storageアカウントのドキュメント](/azure/storage/common/storage-account-overview)
