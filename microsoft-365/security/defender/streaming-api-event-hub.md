---
title: Defender Microsoft 365 Azure イベント ハブにストリーム配信する
description: 詳細ハンティング イベントをイベント Microsoft 365にストリームする Defender を構成する方法について学習します。
keywords: raw data export, Streaming API, API, Azure Event Hub, Azure Storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: c62f175fc8227f64b9f18de78a2a793b2201691c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782371"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a><span data-ttu-id="74715-104">Azure イベント Microsoft 365高度なハンティング イベントをストリーミングするように Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="74715-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74715-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="74715-105">**Applies to:**</span></span>
- [<span data-ttu-id="74715-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74715-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="74715-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="74715-107">Before you begin</span></span>

1. <span data-ttu-id="74715-108">テナントに [イベント ハブ](/azure/event-hubs/) を作成します。</span><span class="sxs-lookup"><span data-stu-id="74715-108">Create an [Event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="74715-109">Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] >[サブスクリプション>プロバイダー> **Microsoft.Insights** に登録する] に移動します。</span><span class="sxs-lookup"><span data-stu-id="74715-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="74715-110">イベント ハブ名前空間を作成し、[イベント ハブ] **>[** 追加] に移動し、予想される負荷に適した価格レベル、スループット単位、自動インフレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="74715-110">Create an Event Hub Namespace, go to **Event Hub > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="74715-111">詳細については、「価格 - イベント ハブ[」を参照|Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="74715-111">For more information, see [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

### <a name="add-contributor-permissions"></a><span data-ttu-id="74715-112">共同作成者のアクセス許可を追加する</span><span class="sxs-lookup"><span data-stu-id="74715-112">Add contributor permissions</span></span> 
<span data-ttu-id="74715-113">Event Hub 名前空間を作成したら、App Registration Service Principal を Reader、Azure Event Hub Data Receiver、および投稿者として Microsoft 365 Defender にログインするユーザーを追加する必要があります (これは、リソース グループまたはサブスクリプション レベルでも実行できます)。</span><span class="sxs-lookup"><span data-stu-id="74715-113">Once the Event Hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hub Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> 

<span data-ttu-id="74715-114">[役割の **割り当て] > [追加と確認]** >アクセス制御 (IAM) のイベント ハブ名前空間 **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="74715-114">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignments**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="74715-115">生データ ストリーミングを有効にする</span><span class="sxs-lookup"><span data-stu-id="74715-115">Enable raw data streaming</span></span>

1. <span data-ttu-id="74715-116">Defender セキュリティ センター [にMicrosoft 365 \*](https://security.microsoft.com) **グローバル** 管理者 _ または _\* セキュリティ管理者 \*\*_としてログイン_ します。</span><span class="sxs-lookup"><span data-stu-id="74715-116">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="74715-117">[ストリーミング [API の設定] ページに移動します](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。</span><span class="sxs-lookup"><span data-stu-id="74715-117">Go to the [Streaming API settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="74715-118">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74715-118">Click on **Add**.</span></span>

4. <span data-ttu-id="74715-119">新しい設定の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="74715-119">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="74715-120">[イベント **を Azure Event Hub に転送する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="74715-120">Choose **Forward events to Azure Event Hub**.</span></span>

6. <span data-ttu-id="74715-121">イベント データを 1 つのイベント ハブにエクスポートするか、イベント ハブ名前空間内の別のイベント ハブに各イベント テーブルをエクスポートするか選択できます。</span><span class="sxs-lookup"><span data-stu-id="74715-121">You can select if you want to export the event data to a single Event Hub, or to export each event table to a different event hub in your Event Hub namespace.</span></span> 

7. <span data-ttu-id="74715-122">イベント データを 1 つのイベント ハブにエクスポートするには、イベント ハブ名とイベント ハブ **リソース ID を入力します**。</span><span class="sxs-lookup"><span data-stu-id="74715-122">To export the event data to a single Event Hub, enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="74715-123">Event Hub リソース **ID を取得するには**、[Azure プロパティ] タブの [[Azure](https://ms.portal.azure.com/)Event Hub 名前空間] ページに移動し> [リソース ID] の下のテキストを  >  **コピーします**。</span><span class="sxs-lookup"><span data-stu-id="74715-123">To get your **Event Hub resource ID**, go to your Azure Event Hub namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![イベント ハブ リソース Id1 のイメージ](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="74715-125">ストリーミングするイベントを選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="74715-125">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hub"></a><span data-ttu-id="74715-126">Azure Event Hub のイベントのスキーマ</span><span class="sxs-lookup"><span data-stu-id="74715-126">The schema of the events in Azure Event Hub</span></span>

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="74715-127">Azure Event Hub の各イベント ハブ メッセージには、レコードの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="74715-127">Each Event Hub message in Azure Event Hub contains list of records.</span></span>

- <span data-ttu-id="74715-128">各レコードには、イベント名、Microsoft 365 Defender がイベントを受け取った時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが **"properties"** というプロパティで含まれる。</span><span class="sxs-lookup"><span data-stu-id="74715-128">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="74715-129">Defender イベントのスキーマの詳細についてはMicrosoft 365高度なハンティング[の概要を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="74715-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="74715-130">Advanced Hunting では **、DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。</span><span class="sxs-lookup"><span data-stu-id="74715-130">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="74715-131">ここでは、すべてのイベントもこの列で装飾されます。</span><span class="sxs-lookup"><span data-stu-id="74715-131">Here every event will be decorated with this column as well.</span></span> 




## <a name="data-types-mapping"></a><span data-ttu-id="74715-132">データ型マッピング</span><span class="sxs-lookup"><span data-stu-id="74715-132">Data types mapping</span></span>

<span data-ttu-id="74715-133">イベント プロパティのデータ型を取得するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="74715-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="74715-134">セキュリティ センターにMicrosoft 365[し、[](https://security.microsoft.com)高度な検索][ページに移動します](https://security.microsoft.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="74715-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="74715-135">次のクエリを実行して、各イベントのデータ型マッピングを取得します。</span><span class="sxs-lookup"><span data-stu-id="74715-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="74715-136">デバイス情報イベントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74715-136">Here is an example for Device Info event:</span></span> 

  ![イベント ハブ リソース Id2 のイメージ](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="74715-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="74715-138">Related topics</span></span>
- [<span data-ttu-id="74715-139">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="74715-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="74715-140">Microsoft 365Defender ストリーミング API</span><span class="sxs-lookup"><span data-stu-id="74715-140">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="74715-141">Defender Microsoft 365を Azure ストレージ アカウントにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="74715-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="74715-142">Azure Event Hub のドキュメント</span><span class="sxs-lookup"><span data-stu-id="74715-142">Azure Event Hub documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="74715-143">接続の問題のトラブルシューティング - Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="74715-143">Troubleshoot connectivity issues - Azure Event Hub</span></span>](/azure/event-hubs/troubleshooting-guide)
