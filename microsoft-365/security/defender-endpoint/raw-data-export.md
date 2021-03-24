---
title: エンドポイント イベントの Microsoft Defender のストリーム
description: 高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングするように Microsoft Defender ATP を構成する方法について説明します。
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063844"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="65788-104">Raw Data Streaming API</span><span class="sxs-lookup"><span data-stu-id="65788-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65788-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="65788-105">**Applies to:**</span></span>
- [<span data-ttu-id="65788-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="65788-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="65788-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="65788-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="65788-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="65788-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="65788-109">高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="65788-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="65788-110">Defender for Endpoint では、高度な[](advanced-hunting-overview.md)ハンティングを通じて使用可能なすべてのイベントを[イベント](https://docs.microsoft.com/azure/event-hubs/)ハブや Azure ストレージ アカウント[にストリーミングできます](https://docs.microsoft.com/azure/event-hubs/)。</span><span class="sxs-lookup"><span data-stu-id="65788-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="65788-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="65788-111">In this section</span></span>

<span data-ttu-id="65788-112">トピック</span><span class="sxs-lookup"><span data-stu-id="65788-112">Topic</span></span> | <span data-ttu-id="65788-113">説明</span><span class="sxs-lookup"><span data-stu-id="65788-113">Description</span></span>
:---|:---
[<span data-ttu-id="65788-114">エンドポイント イベントの Microsoft Defender を Azure イベント ハブにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="65788-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="65788-115">テナントでストリーミング API を有効にし、Defender for Endpoint を構成して高度なハンティングを [イベント](advanced-hunting-overview.md) ハブにストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65788-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="65788-116">エンドポイントイベントの Defender を Azure ストレージ アカウントにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="65788-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="65788-117">テナントでストリーミング API を有効にし、Defender for Endpoint を構成して Azure ストレージ アカウントに [高度](advanced-hunting-overview.md) なハンティングをストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65788-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="65788-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="65788-118">Related topics</span></span>
- [<span data-ttu-id="65788-119">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="65788-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65788-120">Azure Event Hubs のドキュメント</span><span class="sxs-lookup"><span data-stu-id="65788-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="65788-121">Azure ストレージ アカウントのドキュメント</span><span class="sxs-lookup"><span data-stu-id="65788-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
