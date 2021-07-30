---
title: エンドポイント イベントの Microsoft Defender のストリーム
description: 高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングするように Microsoft Defender for Endpoint を構成する方法について説明します。
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
ms.custom: api
ms.openlocfilehash: 43d1e11ebea2933f8a101b640690f44089e2087d
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53649836"
---
# <a name="raw-data-streaming-api"></a>Raw Data Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングする

Microsoft Defender for Endpoint は[](../defender/advanced-hunting-overview.md)、高度なハン[](/azure/event-hubs/)ティングを通じてイベント ハブや Azure ストレージ アカウントに利用可能な[ストリーミング イベントをサポートしています](/azure/storage/common/storage-account-overview)。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4ga]

## <a name="in-this-section"></a>このセクションの内容

トピック|説明
:---|:---
[エンドポイント イベントの Microsoft Defender を Azure イベント ハブにストリーミングする](raw-data-export-event-hub.md)|テナントでストリーミング API を有効にし、Defender for Endpoint を構成して高度なハンティングを [イベント](advanced-hunting-overview.md) ハブにストリーミングする方法について説明します。
[エンドポイントイベントの Defender を Azure ストレージ アカウントにストリーミングする](raw-data-export-storage.md)|テナントでストリーミング API を有効にし、Defender for Endpoint を構成して Azure ストレージ アカウントに [高度](advanced-hunting-overview.md) なハンティングをストリーミングする方法について説明します。

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [Azure Event Hubs のドキュメント](/azure/event-hubs/)
- [Azure Storageアカウントのドキュメント](/azure/storage/common/storage-account-overview)