---
title: Microsoft Defender for Endpoint イベントをストレージ アカウントにストリーミングする
description: Microsoft Defender for Endpoint を構成して、高度なハンティング イベントをストレージ アカウントにストリーミングする方法について説明します。
keywords: raw data export, Streaming API, API, Event Hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: 19fe0c9c3dc6f2e4226a4aa9a6cd983bc95bae3a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688791"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="735c8-104">Microsoft Defender for Endpoint を構成して、高度なハンティング イベントをストレージ アカウントにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="735c8-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="735c8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="735c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="735c8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="735c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="735c8-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="735c8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="735c8-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="735c8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="735c8-109">開始する前に:</span><span class="sxs-lookup"><span data-stu-id="735c8-109">Before you begin:</span></span>

1. <span data-ttu-id="735c8-110">テナントに [ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-account-overview) を作成します。</span><span class="sxs-lookup"><span data-stu-id="735c8-110">Create a [Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="735c8-111">Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] >[リソース プロバイダー> **Microsoft.insights >に登録** する] に移動します。</span><span class="sxs-lookup"><span data-stu-id="735c8-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="735c8-112">生データ ストリーミングを有効にする:</span><span class="sxs-lookup"><span data-stu-id="735c8-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="735c8-113">[Microsoft Defender for Endpoint ポータルに](https://securitycenter.windows.com)***グローバル** 管理者 _ または _* セキュリティ管理者 \*\*_としてログイン_ します。</span><span class="sxs-lookup"><span data-stu-id="735c8-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="735c8-114">Microsoft Defender [セキュリティ センターの [データエクスポート設定]](https://securitycenter.windows.com/interoperability/dataexport) ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="735c8-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="735c8-115">[データエクスポート **設定の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="735c8-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="735c8-116">新しい設定の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="735c8-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="735c8-117">[イベント **を Azure Storage に転送する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="735c8-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="735c8-118">ストレージ アカウント **リソース ID を入力します**。</span><span class="sxs-lookup"><span data-stu-id="735c8-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="735c8-119">ストレージ アカウント リソース **ID** を取得するには [、Azure portal](https://ms.portal.azure.com/) の [ストレージ アカウント] ページに移動し、[> プロパティ] タブ> [ストレージ アカウント リソース ID] の下のテキストを **コピーします**。</span><span class="sxs-lookup"><span data-stu-id="735c8-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![イベント ハブ リソース ID1 のイメージ](images/storage-account-resource-id.png)

7. <span data-ttu-id="735c8-121">ストリーミングするイベントを選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="735c8-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="735c8-122">ストレージ アカウント内のイベントのスキーマを次に示します。</span><span class="sxs-lookup"><span data-stu-id="735c8-122">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="735c8-123">BLOB コンテナーは、イベントの種類ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="735c8-123">A blob container will be created for each event type:</span></span> 

  ![イベント ハブ リソース ID2 のイメージ](images/storage-account-event-schema.png)

- <span data-ttu-id="735c8-125">BLOB 内の各行のスキーマは、次の JSON です。</span><span class="sxs-lookup"><span data-stu-id="735c8-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="735c8-126">各 BLOB には複数の行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="735c8-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="735c8-127">各行には、イベント名、Defender for Endpoint がイベントを受信した時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが "properties" と呼ばれるプロパティで含まれる。</span><span class="sxs-lookup"><span data-stu-id="735c8-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="735c8-128">Microsoft Defender for Endpoint イベントのスキーマの詳細については、「Advanced Hunting [overview」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="735c8-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="735c8-129">Advanced Hunting では **、DeviceInfo** テーブルに **MachineGroup** という名前の列が含まれるので、デバイスのグループが含まれる。</span><span class="sxs-lookup"><span data-stu-id="735c8-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="735c8-130">ここでは、すべてのイベントもこの列で装飾されます。</span><span class="sxs-lookup"><span data-stu-id="735c8-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="735c8-131">詳細については [、「デバイス グループ](machine-groups.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="735c8-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="735c8-132">データ型マッピング:</span><span class="sxs-lookup"><span data-stu-id="735c8-132">Data types mapping:</span></span>

<span data-ttu-id="735c8-133">イベント プロパティのデータ型を取得するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="735c8-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="735c8-134">Microsoft Defender セキュリティ センター [にログインし、[](https://securitycenter.windows.com) 高度な検索] [ページに移動します](https://securitycenter.windows.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="735c8-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="735c8-135">次のクエリを実行して、各イベントのデータ型マッピングを取得します。</span><span class="sxs-lookup"><span data-stu-id="735c8-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="735c8-136">デバイス情報イベントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="735c8-136">Here is an example for Device Info event:</span></span> 

  ![イベント ハブ リソース ID3 のイメージ](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="735c8-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="735c8-138">Related topics</span></span>
- [<span data-ttu-id="735c8-139">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="735c8-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="735c8-140">エンドポイント ストリーミング API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="735c8-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="735c8-141">Microsoft Defender for Endpoint イベントを Azure ストレージ アカウントにストリーミングする</span><span class="sxs-lookup"><span data-stu-id="735c8-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="735c8-142">Azure ストレージ アカウントのドキュメント</span><span class="sxs-lookup"><span data-stu-id="735c8-142">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
