---
title: エンドポイント イベントの Microsoft Defender を Azure イベント ハブにストリーミングする
description: 高度なハンティング イベントをイベント ハブにストリーミングするために Microsoft Defender ATP を構成する方法について説明します。
keywords: raw data export, Streaming API, API, Azure Event Hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: 231ba79e1d66eee263b6c1a4335f0a7b54eeb75d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063868"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="502d8-104">Azure イベント ハブに高度なハンティング イベントをストリーミングするように Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="502d8-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="502d8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="502d8-105">**Applies to:**</span></span>

- [<span data-ttu-id="502d8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="502d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="502d8-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="502d8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="502d8-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="502d8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="502d8-109">開始する前に:</span><span class="sxs-lookup"><span data-stu-id="502d8-109">Before you begin:</span></span>

1. <span data-ttu-id="502d8-110">テナントに [イベント ハブ](https://docs.microsoft.com/azure/event-hubs/) を作成します。</span><span class="sxs-lookup"><span data-stu-id="502d8-110">Create an [event hub](https://docs.microsoft.com/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="502d8-111">Azure テナントに [ログインし、[\*\*Subscriptions](https://ms.portal.azure.com/)> サブスクリプション >リソース プロバイダー> **Microsoft.insights** に登録する] に移動します。</span><span class="sxs-lookup"><span data-stu-id="502d8-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to **Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="502d8-112">生データ ストリーミングを有効にする:</span><span class="sxs-lookup"><span data-stu-id="502d8-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="502d8-113">[Microsoft Defender](https://securitycenter.windows.com)セキュリティ センターに ***グローバル** 管理者 _ または _* セキュリティ管理者 \*\*_としてログイン_ します。</span><span class="sxs-lookup"><span data-stu-id="502d8-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="502d8-114">Microsoft Defender セキュリティ [センターの [データエクスポート設定]](https://securitycenter.windows.com/interoperability/dataexport) ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="502d8-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="502d8-115">[データエクスポート **設定の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="502d8-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="502d8-116">新しい設定の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="502d8-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="502d8-117">[ **イベントを Azure イベント ハブに転送する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="502d8-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="502d8-118">イベント ハブ **名とイベント** ハブ **リソース ID を入力します**。</span><span class="sxs-lookup"><span data-stu-id="502d8-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="502d8-119">Event Hubs リソース ID を取得するには [、Azure](https://ms.portal.azure.com/) > プロパティ タブの Azure Event **Hubs** 名前空間ページに移動し、[リソース ID] >を **コピーします**。</span><span class="sxs-lookup"><span data-stu-id="502d8-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![イベント ハブ リソース Id1 のイメージ](images/event-hub-resource-id.png)

7. <span data-ttu-id="502d8-121">ストリーミングするイベントを選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="502d8-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="502d8-122">Azure Event Hubs のイベントのスキーマ:</span><span class="sxs-lookup"><span data-stu-id="502d8-122">The schema of the events in Azure Event Hubs:</span></span>

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="502d8-123">Azure Event Hubs の各イベント ハブ メッセージには、レコードの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="502d8-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="502d8-124">各レコードには、イベント名、Microsoft Defender for Endpoint がイベントを受信した時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが **"properties"** というプロパティで含まれる。</span><span class="sxs-lookup"><span data-stu-id="502d8-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="502d8-125">Microsoft Defender for Endpoint イベントのスキーマの詳細については、「Advanced Hunting [overview」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="502d8-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="502d8-126">Advanced Hunting では **、DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。</span><span class="sxs-lookup"><span data-stu-id="502d8-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="502d8-127">ここでは、すべてのイベントもこの列で装飾されます。</span><span class="sxs-lookup"><span data-stu-id="502d8-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="502d8-128">詳細については [、「デバイス グループ](machine-groups.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="502d8-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="502d8-129">データ型マッピング:</span><span class="sxs-lookup"><span data-stu-id="502d8-129">Data types mapping:</span></span>

<span data-ttu-id="502d8-130">イベント プロパティのデータ型を取得するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="502d8-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="502d8-131">Microsoft Defender セキュリティ センター [にログインし、[](https://securitycenter.windows.com) 高度な検索] [ページに移動します](https://securitycenter.windows.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="502d8-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="502d8-132">次のクエリを実行して、各イベントのデータ型マッピングを取得します。</span><span class="sxs-lookup"><span data-stu-id="502d8-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="502d8-133">デバイス情報イベントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="502d8-133">Here is an example for Device Info event:</span></span> 

  ![イベント ハブ リソース Id2 のイメージ](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="502d8-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="502d8-135">Related topics</span></span>
- [<span data-ttu-id="502d8-136">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="502d8-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="502d8-137">エンドポイント ストリーミング API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="502d8-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="502d8-138">Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="502d8-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="502d8-139">Azure Event Hubs のドキュメント</span><span class="sxs-lookup"><span data-stu-id="502d8-139">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="502d8-140">接続の問題のトラブルシューティング - Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="502d8-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
