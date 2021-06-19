---
title: ユーザー Microsoft 365 Defenderアカウントにイベントをストレージする
description: 詳細ハンティング イベントを Microsoft 365 Defenderアカウントにストリーミングする方法をストレージします。
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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028897"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="5808e-104">高度Microsoft 365 Defenderイベントを自分のアカウントにストリーミングするストレージ構成する</span><span class="sxs-lookup"><span data-stu-id="5808e-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5808e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5808e-105">**Applies to:**</span></span>
- [<span data-ttu-id="5808e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5808e-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="5808e-107">開始する前に:</span><span class="sxs-lookup"><span data-stu-id="5808e-107">Before you begin:</span></span>

1. <span data-ttu-id="5808e-108">テナントに[ストレージアカウント](/azure/storage/common/storage-account-overview)を作成します。</span><span class="sxs-lookup"><span data-stu-id="5808e-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="5808e-109">Azure テナントに [ログイン](https://ms.portal.azure.com/)し、[サブスクリプション] > サブスクリプション > リソース プロバイダー> **Microsoft.インサイト** に登録します。</span><span class="sxs-lookup"><span data-stu-id="5808e-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="5808e-110">生データ ストリーミングを有効にする:</span><span class="sxs-lookup"><span data-stu-id="5808e-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="5808e-111">セキュリティ センターに [Microsoft 365 Defender](https://security.microsoft.com) ***グローバル管理者** _ または _* セキュリティ管理者 \*\*_としてログイン_ します。</span><span class="sxs-lookup"><span data-stu-id="5808e-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="5808e-112">[データの[エクスポート設定] ページに移動](https://security.microsoft.com/settings/mtp_settings/raw_data_export)Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="5808e-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="5808e-113">[データエクスポート **設定の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5808e-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="5808e-114">新しい設定の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5808e-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="5808e-115">[**イベントを転送する] をAzure Storage** します。</span><span class="sxs-lookup"><span data-stu-id="5808e-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="5808e-116">アカウント リソース **ID ストレージ入力します**。</span><span class="sxs-lookup"><span data-stu-id="5808e-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="5808e-117">ストレージ アカウント リソース **ID を** 取得するには [、Azure portal](https://ms.portal.azure.com/) > プロパティ タブの ストレージ アカウント ページに移動し、> アカウント リソース ID の下のテキストストレージ **コピーします**。</span><span class="sxs-lookup"><span data-stu-id="5808e-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![イベント ハブ リソース ID1 のイメージ](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="5808e-119">ストリーミングするイベントを選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5808e-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="5808e-120">アカウント内のイベントのスキーマストレージします。</span><span class="sxs-lookup"><span data-stu-id="5808e-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="5808e-121">BLOB コンテナーは、イベントの種類ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="5808e-121">A blob container will be created for each event type:</span></span> 

  ![イベント ハブ リソース ID2 のイメージ](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="5808e-123">BLOB 内の各行のスキーマは、次の JSON です。</span><span class="sxs-lookup"><span data-stu-id="5808e-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="5808e-124">各 BLOB には複数の行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5808e-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="5808e-125">各行には、イベント名、Defender for Endpoint がイベントを受信した時刻、そのイベントが属するテナント (テナントからのみイベントを取得する)、および JSON 形式のイベントが "properties" と呼ばれるプロパティで含まれる。</span><span class="sxs-lookup"><span data-stu-id="5808e-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="5808e-126">イベントのスキーマの詳細については、「高度なMicrosoft 365 Defender概要[」を参照してください](../defender/advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5808e-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="5808e-127">データ型マッピング</span><span class="sxs-lookup"><span data-stu-id="5808e-127">Data types mapping</span></span>

<span data-ttu-id="5808e-128">イベント プロパティのデータ型を取得するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5808e-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="5808e-129">セキュリティ センターにMicrosoft 365[し、[](https://security.microsoft.com)高度な検索][ページに移動します](https://security.microsoft.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="5808e-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="5808e-130">次のクエリを実行して、各イベントのデータ型マッピングを取得します。</span><span class="sxs-lookup"><span data-stu-id="5808e-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="5808e-131">デバイス情報イベントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5808e-131">Here is an example for Device Info event:</span></span> 

  ![イベント ハブ リソース ID3 のイメージ](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="5808e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="5808e-133">Related topics</span></span>
- [<span data-ttu-id="5808e-134">高度なハンティングの概要</span><span class="sxs-lookup"><span data-stu-id="5808e-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="5808e-135">Microsoft 365 Defenderストリーミング API</span><span class="sxs-lookup"><span data-stu-id="5808e-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="5808e-136">Azure Microsoft 365 Defenderアカウントにイベントをストリーミングする</span><span class="sxs-lookup"><span data-stu-id="5808e-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="5808e-137">Azure Storageアカウントのドキュメント</span><span class="sxs-lookup"><span data-stu-id="5808e-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
