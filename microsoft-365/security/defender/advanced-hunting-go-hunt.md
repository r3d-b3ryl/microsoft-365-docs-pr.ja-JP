---
title: go hunt を使用してエンティティに関する関連情報を取得する
description: 高度な検索を使用してエンティティまたはイベントに関する関連情報をすばやくクエリするために、移動ハント ツールを使用する方法について学習します。
keywords: 高度な狩猟、インシデント、ピボット、エンティティ、go hunt、関連イベント、脅威狩り、サイバー脅威狩り、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 242c15bdd2f28f7277b93781d521c5414b9e90cf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068331"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="95f35-104">go hunt を使用してエンティティまたはイベント情報をすばやく検索する</span><span class="sxs-lookup"><span data-stu-id="95f35-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="95f35-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="95f35-105">**Applies to:**</span></span>
- <span data-ttu-id="95f35-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95f35-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="95f35-107">Go *Hunt アクションを使用* すると、強力なクエリ ベースの高度なハンティング機能を使用して、イベントやさまざまなエンティティの種類 [をすばやく調査](advanced-hunting-overview.md) できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="95f35-108">このアクションでは、選択したイベントまたはエンティティに関する関連情報を検索する高度な検索クエリが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="95f35-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="95f35-109">go *hunt アクション* は、イベントまたはエンティティの詳細が表示されるたびに、セキュリティ センターのさまざまなセクションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="95f35-110">たとえば、次のセクション *から go hunt* を使用できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="95f35-111">インシデント ページ [では、](investigate-incidents.md#incident-overview)インシデントに関連付けられているユーザー、デバイス、その他多くのエンティティに関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="95f35-112">エンティティを選択すると、追加の情報と、そのエンティティに対して実行できるさまざまなアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95f35-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="95f35-113">次の例では、メールボックスが選択され、メールボックスに関する詳細と、メールボックスの詳細を検索するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95f35-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![移動ハント オプションを使用してメールボックスの詳細を示す画像](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="95f35-115">インシデント ページでは、[証拠] タブの下のエンティティの一覧にアクセスすることもできます。これらのエンティティのいずれかを選択すると、そのエンティティに関する情報をすばやく検索できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![[証拠] タブの [移動ハント] オプションを使用して選択したファイルを示す画像](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="95f35-117">デバイスのタイムラインを表示する場合は、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="95f35-118">イベントを選択すると、高度な検索で他の関連イベントを探すオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95f35-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Go hunt オプションを使用してイベントの詳細を示す画像](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="95f35-120">関連イベント **に対して** [Go hunt] または **[ハント** ] を選択すると、エンティティまたはイベントを選択したかどうかに応じて、さまざまなクエリが渡されます。</span><span class="sxs-lookup"><span data-stu-id="95f35-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="95f35-121">エンティティ情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="95f35-121">Query for entity information</span></span>
<span data-ttu-id="95f35-122">ユーザー、 *デバイス、その* 他の種類のエンティティに関する情報を検索するために移動ハントを使用する場合、クエリは関連するすべてのスキーマ テーブルで、そのエンティティに関連するすべてのイベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="95f35-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="95f35-123">結果を管理可能に保つために、クエリの対象範囲は、エンティティを含み、インシデントに関連付けられた過去 30 日間の最も早いアクティビティと同じ期間です。</span><span class="sxs-lookup"><span data-stu-id="95f35-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="95f35-124">デバイスの移動ハント クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="95f35-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="95f35-125">サポートされているエンティティの種類</span><span class="sxs-lookup"><span data-stu-id="95f35-125">Supported entity types</span></span>
<span data-ttu-id="95f35-126">次のエンティティ *の種類を選択* した後で、go hunt を使用できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="95f35-127">Files</span><span class="sxs-lookup"><span data-stu-id="95f35-127">Files</span></span>
- <span data-ttu-id="95f35-128">メール</span><span class="sxs-lookup"><span data-stu-id="95f35-128">Emails</span></span>
- <span data-ttu-id="95f35-129">電子メール クラスター</span><span class="sxs-lookup"><span data-stu-id="95f35-129">Email clusters</span></span>
- <span data-ttu-id="95f35-130">メールボックス</span><span class="sxs-lookup"><span data-stu-id="95f35-130">Mailboxes</span></span>
- <span data-ttu-id="95f35-131">ユーザー</span><span class="sxs-lookup"><span data-stu-id="95f35-131">Users</span></span>
- <span data-ttu-id="95f35-132">デバイス</span><span class="sxs-lookup"><span data-stu-id="95f35-132">Devices</span></span>
- <span data-ttu-id="95f35-133">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="95f35-133">IP addresses</span></span>
- <span data-ttu-id="95f35-134">URL</span><span class="sxs-lookup"><span data-stu-id="95f35-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="95f35-135">イベント情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="95f35-135">Query for event information</span></span>
<span data-ttu-id="95f35-136">go *hunt を使用して* タイムライン イベントに関する情報を照会する場合、クエリは、選択したイベントの時刻に関連するすべてのスキーマ テーブルで他のイベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="95f35-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="95f35-137">たとえば、次のクエリは、同じデバイスで同じ期間に発生したさまざまなスキーマ テーブルのイベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="95f35-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="95f35-138">クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="95f35-138">Adjust the query</span></span>
<span data-ttu-id="95f35-139">クエリ言語に関する知識 [がある](advanced-hunting-query-language.md)場合は、クエリを好みに合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="95f35-140">たとえば、タイム ウィンドウのサイズを決定する次の行を調整できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="95f35-141">より関連性の高い結果を得るクエリの変更に加えて、次の処理も実行できます。</span><span class="sxs-lookup"><span data-stu-id="95f35-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="95f35-142">結果をグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="95f35-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="95f35-143">カスタム検出ルールの作成</span><span class="sxs-lookup"><span data-stu-id="95f35-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="95f35-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="95f35-144">Related topics</span></span>
- [<span data-ttu-id="95f35-145">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="95f35-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="95f35-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="95f35-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="95f35-147">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="95f35-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="95f35-148">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="95f35-148">Custom detection rules</span></span>](custom-detection-rules.md)
