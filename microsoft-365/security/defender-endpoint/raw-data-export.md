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
ms.openlocfilehash: f6a45629d610ea3cc3ca7d517021a215b72b1439
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688755"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="b829a-104">Raw Data Streaming API</span><span class="sxs-lookup"><span data-stu-id="b829a-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b829a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b829a-105">**Applies to:**</span></span>
- [<span data-ttu-id="b829a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b829a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="b829a-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b829a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b829a-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b829a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="b829a-109">高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="b829a-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="b829a-110">Defender for Endpoint では、高度な[](advanced-hunting-overview.md)ハンティングを通じて使用可能なすべてのイベントを[イベント](https://docs.microsoft.com/azure/event-hubs/)ハブや Azure ストレージ アカウント[にストリーミングできます](https://docs.microsoft.com/azure/event-hubs/)。</span><span class="sxs-lookup"><span data-stu-id="b829a-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="b829a-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b829a-111">In this section</span></span>

<span data-ttu-id="b829a-112">トピック</span><span class="sxs-lookup"><span data-stu-id="b829a-112">Topic</span></span> | <span data-ttu-id="b829a-113">説明</span><span class="sxs-lookup"><span data-stu-id="b829a-113">Description</span></span>
:---|:---
[<span data-ttu-id="b829a-114">エンドポイント イベントの Microsoft Defender を Azure イベント ハブにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="b829a-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="b829a-115">テナントでストリーミング API を有効にし、Defender for Endpoint を構成して高度なハンティングを [イベント](advanced-hunting-overview.md) ハブにストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b829a-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="b829a-116">エンドポイントイベントの Defender を Azure ストレージ アカウントにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="b829a-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="b829a-117">テナントでストリーミング API を有効にし、Defender for Endpoint を構成して Azure ストレージ アカウントに [高度](advanced-hunting-overview.md) なハンティングをストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b829a-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b829a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b829a-118">Related topics</span></span>
- [<span data-ttu-id="b829a-119">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="b829a-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b829a-120">Azure Event Hubs のドキュメント</span><span class="sxs-lookup"><span data-stu-id="b829a-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="b829a-121">Azure Storageアカウントのドキュメント</span><span class="sxs-lookup"><span data-stu-id="b829a-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
