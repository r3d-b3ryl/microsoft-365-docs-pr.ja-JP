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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778199"
---
# <a name="streaming-api"></a><span data-ttu-id="f9c0d-104">ストリーミング API</span><span class="sxs-lookup"><span data-stu-id="f9c0d-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f9c0d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f9c0d-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9c0d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9c0d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="f9c0d-107">高度なハンティング イベントをイベント ハブまたは Azure ストレージ アカウントにストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="f9c0d-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="f9c0d-108">Microsoft 365Defender は、高度なハンティング[](../defender/advanced-hunting-overview.md)を通じて使用可能[](/azure/event-hubs/)なすべてのイベントをイベント ハブや Azure ストレージ アカウント[にストリーミングできます](/azure/event-hubs/)。</span><span class="sxs-lookup"><span data-stu-id="f9c0d-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="f9c0d-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f9c0d-109">In this section</span></span>

<span data-ttu-id="f9c0d-110">トピック</span><span class="sxs-lookup"><span data-stu-id="f9c0d-110">Topic</span></span> | <span data-ttu-id="f9c0d-111">説明</span><span class="sxs-lookup"><span data-stu-id="f9c0d-111">Description</span></span>
:---|:---
[<span data-ttu-id="f9c0d-112">イベントを Azure イベント ハブにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="f9c0d-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="f9c0d-113">テナントでストリーミング API を有効にし、Microsoft 365 Defender を構成して高度[](../defender/advanced-hunting-overview.md)なハンティングをイベント ハブにストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9c0d-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="f9c0d-114">Azure ストレージ アカウントにイベントをストリーミングする</span><span class="sxs-lookup"><span data-stu-id="f9c0d-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="f9c0d-115">テナントでストリーミング API を有効にし、Microsoft 365 Defender を構成して[](../defender/advanced-hunting-overview.md)Azure ストレージ アカウントに高度なハンティングをストリーミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9c0d-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f9c0d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9c0d-116">Related topics</span></span>
- [<span data-ttu-id="f9c0d-117">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="f9c0d-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="f9c0d-118">Azure Event Hubs のドキュメント</span><span class="sxs-lookup"><span data-stu-id="f9c0d-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="f9c0d-119">Azure Storageアカウントのドキュメント</span><span class="sxs-lookup"><span data-stu-id="f9c0d-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
