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
# <a name="streaming-api"></a><span data-ttu-id="791d3-104">ストリーミング API</span><span class="sxs-lookup"><span data-stu-id="791d3-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="791d3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="791d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="791d3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="791d3-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="791d3-107">高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="791d3-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="791d3-108">Microsoft 365Defender は、高度なハン[ティングを通](../defender/advanced-hunting-overview.md)じてイベント[ハブや](/azure/event-hubs/)Azure ストレージ アカウントへの[ストリーミング イベントをサポートしています](/azure/event-hubs/)。</span><span class="sxs-lookup"><span data-stu-id="791d3-108">Microsoft 365 Defender supports streaming events through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="791d3-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="791d3-109">In this section</span></span>

<span data-ttu-id="791d3-110">トピック</span><span class="sxs-lookup"><span data-stu-id="791d3-110">Topic</span></span> | <span data-ttu-id="791d3-111">説明</span><span class="sxs-lookup"><span data-stu-id="791d3-111">Description</span></span>
:---|:---
[<span data-ttu-id="791d3-112">イベントを Azure イベント ハブにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="791d3-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="791d3-113">テナントでストリーミング API を有効にし、Microsoft 365 Defender を構成して高度[](../defender/advanced-hunting-overview.md)なハンティングをイベント ハブにストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="791d3-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="791d3-114">Azure ストレージ アカウントにイベントをストリーミングする</span><span class="sxs-lookup"><span data-stu-id="791d3-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="791d3-115">テナントでストリーミング API を有効にし、Microsoft 365 Defender を構成して[](advanced-hunting-overview.md)Azure ストレージ アカウントに高度なハンティングをストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="791d3-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="791d3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="791d3-116">Related topics</span></span>
- [<span data-ttu-id="791d3-117">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="791d3-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="791d3-118">Azure Event Hubs のドキュメント</span><span class="sxs-lookup"><span data-stu-id="791d3-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="791d3-119">Azure Storageアカウントのドキュメント</span><span class="sxs-lookup"><span data-stu-id="791d3-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
