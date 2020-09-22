---
title: '[ハント] を使用してエンティティに関する関連情報を取得する'
description: 高度な検索を使用して、エンティティまたはイベントに関する関連情報をすばやくクエリできるようにするために、[ハントの開始] ツールを使用する方法について説明します。
keywords: 高度な検索、インシデント、ピボット、エンティティ、go ハント、関連イベント、脅威の探し、サイバー脅威の検索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 496deff5d2fda47b7ffac4bc87e98bf28e90ea50
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196967"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="3f1a5-104">ゴーハントを使用してエンティティまたはイベントの情報をすばやく探します。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3f1a5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3f1a5-105">**Applies to:**</span></span>
- <span data-ttu-id="3f1a5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3f1a5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3f1a5-107">*[ハントハント*] アクションを使用すると、強力なクエリベースの[高度な](advanced-hunting-overview.md)検索機能を使用して、イベントやさまざまなエンティティの種類をすばやく調査できます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="3f1a5-108">この操作により、選択したイベントまたはエンティティに関する関連情報を検索する高度な検索クエリが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="3f1a5-109">イベントまたはエンティティの詳細が表示されている場合は、セキュリティセンターのさまざまなセクションで [ *ハントの移動* ] アクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="3f1a5-110">たとえば、 *[ハント* ] を使用するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="3f1a5-111">[ [インシデント] ページ](investigate-incidents.md#incident-overview)では、インシデントに関連付けられているユーザー、デバイス、およびその他の多くのエンティティに関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="3f1a5-112">エンティティを選択すると、その entitity に対して実行できるさまざまなアクションに加えて、追加の情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="3f1a5-113">次の例では、メールボックスが選択されており、メールボックスの詳細と、メールボックスに関する詳細情報を確認するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![メールボックスの詳細が表示された状態の [ハント] オプションを含む画像](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="3f1a5-115">[インシデント] ページでは、[証拠] タブの下にあるエンティティのリストにアクセスすることもできます。これらのエンティティのいずれかを選択すると、そのエンティティに関する情報をすばやく確認するオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![[証拠] タブの [ハントハント] オプションが選択されたファイルを示す画像](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="3f1a5-117">デバイスのタイムラインを表示しているときに、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="3f1a5-118">イベントを選択すると、高度な検索で他の関連イベントを確認するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Go ハントオプションを含むイベントの詳細を示す画像](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="3f1a5-120">エンティティまたはイベントのどちらを選択したかによって、**関連イベントの** **[ハント**の表示] または [ハント] を選択すると、さまざまなクエリが渡されます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="3f1a5-121">エンティティ情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="3f1a5-121">Query for entity information</span></span>
<span data-ttu-id="3f1a5-122">*[ハント*] を使用して、ユーザー、デバイス、またはその他の種類のエンティティに関する情報をクエリに対して実行する場合、クエリはそのエンティティに関連するすべてのイベントについてすべての関連するスキーマテーブルをチェックします。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="3f1a5-123">結果を管理可能な状態に保つために、このクエリは、エンティティに関連し、インシデントに関連付けられている過去30日間の最初のアクティビティと同じ期間に限定されます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="3f1a5-124">デバイスに対する go ハントクエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="3f1a5-125">サポートされるエンティティの種類</span><span class="sxs-lookup"><span data-stu-id="3f1a5-125">Supported entity types</span></span>
<span data-ttu-id="3f1a5-126">次のいずれかのエンティティの種類を選択した後、 *[ハント* ] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="3f1a5-127">ファイル</span><span class="sxs-lookup"><span data-stu-id="3f1a5-127">Files</span></span>
- <span data-ttu-id="3f1a5-128">メール</span><span class="sxs-lookup"><span data-stu-id="3f1a5-128">Emails</span></span>
- <span data-ttu-id="3f1a5-129">電子メールクラスター</span><span class="sxs-lookup"><span data-stu-id="3f1a5-129">Email clusters</span></span>
- <span data-ttu-id="3f1a5-130">メールボックス</span><span class="sxs-lookup"><span data-stu-id="3f1a5-130">Mailboxes</span></span>
- <span data-ttu-id="3f1a5-131">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3f1a5-131">Users</span></span>
- <span data-ttu-id="3f1a5-132">デバイス</span><span class="sxs-lookup"><span data-stu-id="3f1a5-132">Devices</span></span>
- <span data-ttu-id="3f1a5-133">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f1a5-133">IP addresses</span></span>
- <span data-ttu-id="3f1a5-134">URL</span><span class="sxs-lookup"><span data-stu-id="3f1a5-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="3f1a5-135">イベント情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="3f1a5-135">Query for event information</span></span>
<span data-ttu-id="3f1a5-136">*[ハント*] を使用して、タイムラインイベントに関する情報をクエリに対して実行すると、選択したイベントの時間の前後にある他のイベントに関する関連するすべてのスキーマテーブルが照会によってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="3f1a5-137">たとえば、次のクエリは、同じデバイス上で同じ期間に発生したさまざまなスキーマテーブルのイベントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="3f1a5-138">クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="3f1a5-138">Adjust the query</span></span>
<span data-ttu-id="3f1a5-139">[クエリ言語](advanced-hunting-query-language.md)に関するいくつかの知識があれば、クエリを任意のユーザー設定に変更できます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="3f1a5-140">たとえば、タイムウィンドウのサイズを決定するこの行を調整できます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="3f1a5-141">クエリを変更して関連性の高い結果を得るだけでなく、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="3f1a5-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="3f1a5-142">結果をグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="3f1a5-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="3f1a5-143">カスタム検出ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="3f1a5-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="3f1a5-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f1a5-144">Related topics</span></span>
- [<span data-ttu-id="3f1a5-145">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="3f1a5-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3f1a5-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3f1a5-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3f1a5-147">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="3f1a5-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3f1a5-148">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="3f1a5-148">Custom detection rules</span></span>](custom-detection-rules.md)
