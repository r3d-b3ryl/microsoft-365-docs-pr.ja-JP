---
title: Go Hunt を使用してエンティティに関する関連情報を取得する
description: 高度な検索を使用してエンティティまたはイベントに関する関連情報をすばやく照会するために、移動ハント ツールを使用する方法について学習します。
keywords: 高度な捜索、インシデント、ピボット、エンティティ、移動ハント、関連イベント、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929507"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="f5f70-104">Go Hunt を使用してエンティティまたはイベント情報をすばやく検索する</span><span class="sxs-lookup"><span data-stu-id="f5f70-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5f70-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f5f70-105">**Applies to:**</span></span>
- <span data-ttu-id="f5f70-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5f70-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f5f70-107">Go *Hunt アクションを使用* すると、強力なクエリ ベースの高度なハンティング機能を使用して、イベントやさまざまなエンティティの種類をすばやく [調査](advanced-hunting-overview.md) できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="f5f70-108">このアクションは、高度な検索クエリを自動的に実行して、選択したイベントまたはエンティティに関する関連情報を検索します。</span><span class="sxs-lookup"><span data-stu-id="f5f70-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="f5f70-109">Go *Hunt* アクションは、イベントまたはエンティティの詳細が表示されるたびに、セキュリティ センターのさまざまなセクションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="f5f70-110">たとえば、次のセクションの *go ハント* を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="f5f70-111">インシデント ページ [では、](investigate-incidents.md#incident-overview)ユーザー、デバイス、およびインシデントに関連付けられている他の多くのエンティティに関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="f5f70-112">エンティティを選択すると、追加情報と、そのエンティティに対して実行できるさまざまなアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="f5f70-113">次の例では、メールボックスが選択され、メールボックスに関する詳細と、メールボックスに関する詳細を検索するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![移動ハント オプションを使用したメールボックスの詳細を示す画像](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="f5f70-115">インシデント ページでは、[エビデンス] タブの下にあるエンティティの一覧にアクセスすることもできます。これらのエンティティの 1 つを選択すると、そのエンティティに関する情報をすばやく検索できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![[エビデンス] タブの [Go Hunt] オプションを使用して選択したファイルを示す画像](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="f5f70-117">デバイスのタイムラインを表示する場合は、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="f5f70-118">イベントを選択すると、高度な検索で他の関連するイベントを探すオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Go Hunt オプションを使用したイベントの詳細を示す画像](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="f5f70-120">関連する **イベントの検索\*\*\*\*またはハント** を選択すると、エンティティまたはイベントが選択されたかどうかに応じて、異なるクエリが渡されます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="f5f70-121">エンティティ情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="f5f70-121">Query for entity information</span></span>
<span data-ttu-id="f5f70-122">ユーザー、 *デバイス、その* 他の種類のエンティティに関する情報を検索するために移動ハントを使用する場合、クエリは関連するすべてのスキーマ テーブルで、そのエンティティに関連するすべてのイベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="f5f70-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="f5f70-123">結果を管理可能な状態に保つために、クエリの対象範囲は、エンティティを含み、インシデントに関連付けられた過去 30 日間の最初のアクティビティと同じ時間です。</span><span class="sxs-lookup"><span data-stu-id="f5f70-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="f5f70-124">デバイスの Go ハント クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f5f70-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="f5f70-125">サポートされるエンティティの種類</span><span class="sxs-lookup"><span data-stu-id="f5f70-125">Supported entity types</span></span>
<span data-ttu-id="f5f70-126">次のエンティティ *の種類を選択* した後で、移動ハントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="f5f70-127">ファイル</span><span class="sxs-lookup"><span data-stu-id="f5f70-127">Files</span></span>
- <span data-ttu-id="f5f70-128">メール</span><span class="sxs-lookup"><span data-stu-id="f5f70-128">Emails</span></span>
- <span data-ttu-id="f5f70-129">メール クラスター</span><span class="sxs-lookup"><span data-stu-id="f5f70-129">Email clusters</span></span>
- <span data-ttu-id="f5f70-130">メールボックス</span><span class="sxs-lookup"><span data-stu-id="f5f70-130">Mailboxes</span></span>
- <span data-ttu-id="f5f70-131">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f5f70-131">Users</span></span>
- <span data-ttu-id="f5f70-132">デバイス</span><span class="sxs-lookup"><span data-stu-id="f5f70-132">Devices</span></span>
- <span data-ttu-id="f5f70-133">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f5f70-133">IP addresses</span></span>
- <span data-ttu-id="f5f70-134">URL</span><span class="sxs-lookup"><span data-stu-id="f5f70-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="f5f70-135">イベント情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="f5f70-135">Query for event information</span></span>
<span data-ttu-id="f5f70-136">タイムライン イベント *に関する* 情報を検索するために移動ハントを使用する場合、クエリは、選択したイベントの時刻に関連するすべてのスキーマ テーブルで他のイベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="f5f70-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="f5f70-137">たとえば、次のクエリは、同じデバイスで同じ期間に発生したさまざまなスキーマ テーブルのイベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f5f70-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="f5f70-138">クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="f5f70-138">Adjust the query</span></span>
<span data-ttu-id="f5f70-139">クエリ言語に関する知識 [がある](advanced-hunting-query-language.md)場合は、クエリを好みに合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="f5f70-140">たとえば、この行を調整して、タイム ウィンドウのサイズを決定できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="f5f70-141">より関連性の高い結果を得るクエリを変更する以外に、次の方法も実行できます。</span><span class="sxs-lookup"><span data-stu-id="f5f70-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="f5f70-142">結果をグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="f5f70-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="f5f70-143">カスタム検出ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="f5f70-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="f5f70-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5f70-144">Related topics</span></span>
- [<span data-ttu-id="f5f70-145">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="f5f70-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5f70-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f5f70-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f5f70-147">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="f5f70-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="f5f70-148">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="f5f70-148">Custom detection rules</span></span>](custom-detection-rules.md)
