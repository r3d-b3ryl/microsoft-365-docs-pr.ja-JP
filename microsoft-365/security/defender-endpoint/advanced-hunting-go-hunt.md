---
title: go hunt を使用してエンティティに関する関連情報を取得する
description: 高度な検索を使用してエンティティまたはイベントに関する関連情報をすばやくクエリするために、移動ハント ツールを使用する方法について学習します。
keywords: 高度な狩猟、インシデント、ピボット、エンティティ、go hunt、関連イベント、脅威狩り、サイバー脅威狩り、検索、クエリ、テレメトリ、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-maave
author: martyav
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fe3c204fe49f008cf5d9dd18b5066fa91dc6196
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067955"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="3a25a-104">go hunt を使用してエンティティまたはイベント情報をすばやく検索する</span><span class="sxs-lookup"><span data-stu-id="3a25a-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3a25a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3a25a-105">**Applies to:**</span></span>
- [<span data-ttu-id="3a25a-106">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3a25a-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="3a25a-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3a25a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3a25a-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="3a25a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


<span data-ttu-id="3a25a-109">Go *Hunt アクションを使用* すると、強力なクエリ ベースの高度なハンティング機能を使用して、イベントやさまざまなエンティティの種類 [をすばやく調査](advanced-hunting-overview.md) できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-109">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="3a25a-110">このアクションでは、選択したイベントまたはエンティティに関する関連情報を検索する高度な検索クエリが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-110">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="3a25a-111">go *hunt アクション* は、イベントまたはエンティティの詳細が表示されるたびに、セキュリティ センターのさまざまなセクションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-111">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="3a25a-112">たとえば、次のセクション *から go hunt* を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-112">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="3a25a-113">インシデント ページ [では、](investigate-incidents.md)インシデントに関連付けられているユーザー、デバイス、その他多くのエンティティに関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-113">In the [incident page](investigate-incidents.md), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="3a25a-114">エンティティを選択すると、追加の情報と、そのエンティティに対して実行できるさまざまなアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-114">When you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="3a25a-115">次の例では、デバイスが選択され、デバイスの詳細と、デバイスの詳細を探すオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-115">In the example below, a device is selected, showing details about the device as well the option to hunt for more information about the device.</span></span>

    ![移動ハント オプションを使用してデバイスの詳細を示す画像](./images/go-hunt-device.png)

- <span data-ttu-id="3a25a-117">インシデント ページでは、[証拠] タブの下のエンティティの一覧にアクセスすることもできます。これらのエンティティのいずれかを選択すると、そのエンティティに関する情報をすばやく検索できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-117">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![[証拠] タブの [移動ハント] オプションを使用して選択した URL を示す画像](./images/go-hunt-evidence-url.png)

- <span data-ttu-id="3a25a-119">デバイスのタイムラインを表示する場合は、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-119">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="3a25a-120">イベントを選択すると、高度な検索で他の関連イベントを探すオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-120">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Go hunt オプションを使用してイベントの詳細を示す画像](./images/go-hunt-event.png)

<span data-ttu-id="3a25a-122">関連イベント **に対して** [Go hunt] または **[ハント** ] を選択すると、エンティティまたはイベントを選択したかどうかに応じて、さまざまなクエリが渡されます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-122">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="3a25a-123">エンティティ情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="3a25a-123">Query for entity information</span></span>

<span data-ttu-id="3a25a-124">ユーザー、 *デバイス、その* 他の種類のエンティティに関する情報を検索するために移動ハントを使用する場合、クエリは関連するすべてのスキーマ テーブルで、そのエンティティに関連するすべてのイベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="3a25a-124">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="3a25a-125">結果を管理可能に保つために、クエリの対象範囲は、エンティティを含み、インシデントに関連付けられた過去 30 日間の最も早いアクティビティと同じ期間です。</span><span class="sxs-lookup"><span data-stu-id="3a25a-125">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="3a25a-126">デバイスの移動ハント クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a25a-126">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```

### <a name="supported-entity-types"></a><span data-ttu-id="3a25a-127">サポートされているエンティティの種類</span><span class="sxs-lookup"><span data-stu-id="3a25a-127">Supported entity types</span></span>

<span data-ttu-id="3a25a-128">次のエンティティ *の種類を選択* した後で、go hunt を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-128">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="3a25a-129">Files</span><span class="sxs-lookup"><span data-stu-id="3a25a-129">Files</span></span>
- <span data-ttu-id="3a25a-130">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3a25a-130">Users</span></span>
- <span data-ttu-id="3a25a-131">デバイス</span><span class="sxs-lookup"><span data-stu-id="3a25a-131">Devices</span></span>
- <span data-ttu-id="3a25a-132">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3a25a-132">IP addresses</span></span>
- <span data-ttu-id="3a25a-133">URL</span><span class="sxs-lookup"><span data-stu-id="3a25a-133">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="3a25a-134">イベント情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="3a25a-134">Query for event information</span></span>

<span data-ttu-id="3a25a-135">go *hunt を使用して* タイムライン イベントに関する情報を照会する場合、クエリは、選択したイベントの時刻に関連するすべてのスキーマ テーブルで他のイベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="3a25a-135">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="3a25a-136">たとえば、次のクエリは、同じデバイスで同じ期間に発生したさまざまなスキーマ テーブルのイベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3a25a-136">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected RegistryValueSet event
let selectedEventTimestamp = datetime(2020-10-06T21:40:25.3466868Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "a305b52049c4658ec63ae8b55becfe5954c654a4"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="3a25a-137">クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="3a25a-137">Adjust the query</span></span>

<span data-ttu-id="3a25a-138">クエリ言語に関する知識 [がある](advanced-hunting-query-language.md)場合は、クエリを好みに合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-138">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="3a25a-139">たとえば、タイム ウィンドウのサイズを決定する次の行を調整できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-139">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="3a25a-140">より関連性の高い結果を得るクエリの変更に加えて、次の処理も実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a25a-140">In addition to modifying the query to get more relevant results, you can also:</span></span>

- [<span data-ttu-id="3a25a-141">結果をグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="3a25a-141">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="3a25a-142">カスタム検出ルールの作成</span><span class="sxs-lookup"><span data-stu-id="3a25a-142">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="3a25a-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a25a-143">Related topics</span></span>

- [<span data-ttu-id="3a25a-144">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="3a25a-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3a25a-145">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3a25a-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3a25a-146">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="3a25a-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3a25a-147">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="3a25a-147">Custom detection rules</span></span>](custom-detection-rules.md)
