---
title: Defender イベントMicrosoft 365ストリームする
description: 詳細ハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリームするように Defender をMicrosoft 365する方法について説明します。
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
ms.openlocfilehash: 21a83c4876a90a231eb2a78d10a290be2dca2fa0
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782479"
---
# <a name="streaming-api"></a>ストリーミング API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングします。

Microsoft 365Defender は、高度なハン[ティングを通](../defender/advanced-hunting-overview.md)じてイベント[ハブや](/azure/event-hubs/)Azure ストレージ アカウントへの[ストリーミング イベントをサポートしています](/azure/event-hubs/)。



## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
:---|:---
[イベントを Azure イベント ハブにストリーミングする](streaming-api-event-hub.md)| テナントでストリーミング API を有効にし、Microsoft 365 Defender を構成して高度[](../defender/advanced-hunting-overview.md)なハンティングをイベント ハブにストリーミングする方法について説明します。
[Azure ストレージ アカウントにイベントをストリーミングする](streaming-api-storage.md)| テナントでストリーミング API を有効にし、Microsoft 365 Defender を構成して[](advanced-hunting-overview.md)Azure ストレージ アカウントに高度なハンティングをストリーミングする方法について説明します。


## <a name="related-topics"></a>関連項目
- [高度なハンティングの概要](../defender/advanced-hunting-overview.md)
- [Azure Event Hubs のドキュメント](/azure/event-hubs/)
- [Azure Storageアカウントのドキュメント](/azure/storage/common/storage-account-overview)
