---
title: ストリーム Microsoft Defender for Endpoint イベント
description: Advanced Hunting イベントを Event Hubs または Azure ストレージ アカウントにストリーミングするMicrosoft Defender for Endpointを構成する方法について説明します
keywords: 生データのエクスポート, ストリーミング API, API, Event Hubs, Azure Storage, ストレージ アカウント, Advanced Hunting, 生データ共有
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 94a815a6fc734c8e8e310a17f2e73931f4ffab5c
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300408"
---
# <a name="raw-data-streaming-api"></a>Raw Data Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>高度なハンティング イベントを Event Hubs または Azure ストレージ アカウントにストリーミングする

Microsoft Defender for Endpointでは、[Advanced Hunting](../defender/advanced-hunting-overview.md) を介して [Event Hubs](/azure/event-hubs/) または [Azure ストレージ アカウント](/azure/storage/common/storage-account-overview)に対して利用できるストリーミング イベントがサポートされます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4ga]

## <a name="in-this-section"></a>このセクションの内容

トピック|説明
:---|:---
[Microsoft Defender for Endpoint イベントをAzure Event Hubsにストリーミングする](raw-data-export-event-hub.md)|テナントでストリーミング API を有効にし、 [Advanced Hunting](advanced-hunting-overview.md) を Event Hubs にストリーミングするように Defender for Endpoint を構成する方法について説明します。
[Azure ストレージ アカウントへの Stream Defender for Endpoint イベント](raw-data-export-storage.md)|テナントでストリーミング API を有効にし、 [Advanced Hunting](advanced-hunting-overview.md) を Azure ストレージ アカウントにストリーミングするように Defender for Endpoint を構成する方法について説明します。

## <a name="related-topics"></a>関連項目

- [高度なハンティングの概要](advanced-hunting-overview.md)
- [Azure Event Hubsドキュメント](/azure/event-hubs/)
- [Azure Storage アカウントのドキュメント](/azure/storage/common/storage-account-overview)