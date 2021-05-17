---
title: Microsoft Defender for Endpoint のユーザー アカウントを調査する
description: 調査中に、侵害された資格情報や関連付けられたユーザー アカウントのピボットが発生する可能性があるユーザー アカウントを調査します。
keywords: 調査, アカウント, ユーザー, ユーザー エンティティ, アラート, Microsoft Defender for Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935067"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6b4b3-104">Microsoft Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="6b4b3-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6b4b3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6b4b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="6b4b3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b4b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6b4b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b4b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="6b4b3-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6b4b3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6b4b3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="6b4b3-110">ユーザー アカウント エンティティの調査</span><span class="sxs-lookup"><span data-stu-id="6b4b3-110">Investigate user account entities</span></span>

<span data-ttu-id="6b4b3-111">最もアクティブなアラートを持つユーザー アカウント (ダッシュボードに "危険にさらされているユーザー" と表示される) を特定し、侵害される可能性のある資格情報のケースを調査するか、関連付けられたユーザー アカウントでピボットを実行して、そのユーザー アカウントを持つデバイス間の横方向の移動の可能性を特定するアラートまたはデバイスを調査します。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="6b4b3-112">ユーザー アカウント情報は、次のビューで確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="6b4b3-113">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="6b4b3-113">Dashboard</span></span>
- <span data-ttu-id="6b4b3-114">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="6b4b3-114">Alert queue</span></span>
- <span data-ttu-id="6b4b3-115">[デバイスの詳細] ページ</span><span class="sxs-lookup"><span data-stu-id="6b4b3-115">Device details page</span></span>

<span data-ttu-id="6b4b3-116">クリック可能なユーザー アカウント リンクは、これらのビューで使用できます。このリンクを使用すると、ユーザー アカウントの詳細ページに移動し、ユーザー アカウントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="6b4b3-117">ユーザー アカウント エンティティを調査すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="6b4b3-118">ユーザー アカウントの詳細、Microsoft Defender for Identity アラート、ログオンしているデバイス、役割、ログオンの種類、その他の詳細</span><span class="sxs-lookup"><span data-stu-id="6b4b3-118">User account details, Microsoft Defender for Identity alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="6b4b3-119">インシデントとユーザーのデバイスの概要</span><span class="sxs-lookup"><span data-stu-id="6b4b3-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="6b4b3-120">このユーザーに関連するアラート</span><span class="sxs-lookup"><span data-stu-id="6b4b3-120">Alerts related to this user</span></span>
- <span data-ttu-id="6b4b3-121">組織内で観察される (ログオンしているデバイス)</span><span class="sxs-lookup"><span data-stu-id="6b4b3-121">Observed in organization (devices logged on to)</span></span>

![ユーザー アカウント エンティティの詳細ページのイメージ](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="6b4b3-123">ユーザーの詳細</span><span class="sxs-lookup"><span data-stu-id="6b4b3-123">User details</span></span>

<span data-ttu-id="6b4b3-124">左側の **[** ユーザーの詳細] ウィンドウには、関連する開いているインシデント、アクティブなアラート、SAM 名、SID、Microsoft Defender for Identity アラート、ユーザーがログオンしているデバイスの数、ユーザーが最初と最後に表示された時間、役割、ログオンの種類など、ユーザーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Microsoft Defender for Identity alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="6b4b3-125">有効にした統合機能に応じて、その他の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="6b4b3-126">たとえば、ビジネス統合のSkype有効にした場合は、ポータルからユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="6b4b3-127">**[Azure ATP アラート**] セクションには、Microsoft Defender for Identity 機能を有効にし、ユーザーに関連するアラートがある場合は、[Microsoft Defender for Identity] ページに移動するリンクが含まれている。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-127">The **Azure ATP alerts** section contains a link that will take you to the Microsoft Defender for Identity page, if you have enabled the Microsoft Defender for Identity feature, and there are alerts related to the user.</span></span> <span data-ttu-id="6b4b3-128">Microsoft Defender for Identity ページには、アラートに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-128">The Microsoft Defender for Identity page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="6b4b3-129">この機能を使用するには、Microsoft Defender for Identity と Defender for Endpoint の両方で統合を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-129">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="6b4b3-130">Defender for Endpoint では、高度な機能でこの機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="6b4b3-131">高度な機能を有効にする方法の詳細については、「高度な機能を有効 [にする」を参照してください](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="6b4b3-132">組織の概要、アラート、および監視は、ユーザー アカウントに関するさまざまな属性を表示するさまざまなタブです。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="6b4b3-133">概要</span><span class="sxs-lookup"><span data-stu-id="6b4b3-133">Overview</span></span>

<span data-ttu-id="6b4b3-134">[ **概要]** タブには、インシデントの詳細と、ユーザーがログオンしたデバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="6b4b3-135">これらを展開すると、各デバイスのログオン イベントの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="6b4b3-136">アラート</span><span class="sxs-lookup"><span data-stu-id="6b4b3-136">Alerts</span></span>

<span data-ttu-id="6b4b3-137">[ **アラート]** タブには、ユーザー アカウントに関連付けられているアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="6b4b3-138">このリストは、アラート キューのフィルター[](alerts-queue.md)処理されたビューであり、ユーザー コンテキストが選択されたユーザー アカウントであるアラート、最後のアクティビティが検出された日付、アラートの短い説明、アラートに関連付けられたデバイス、アラートの重大度、キュー内のアラートの状態、およびアラートが割り当てられているユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="6b4b3-139">組織内で観察される</span><span class="sxs-lookup"><span data-stu-id="6b4b3-139">Observed in organization</span></span>

<span data-ttu-id="6b4b3-140">[ **組織** で観察] タブを使用すると、日付範囲を指定して、このユーザーがログオンしているデバイスの一覧、これらの各デバイスで最も頻繁で最も頻繁にログオンしているユーザー アカウント、および各デバイスの総観測ユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="6b4b3-141">[組織で観察] テーブルでアイテムを選択すると、アイテムが展開され、デバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="6b4b3-142">アイテム内のリンクを直接選択すると、対応するページに移動します。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="6b4b3-143">特定のユーザー アカウントを検索する</span><span class="sxs-lookup"><span data-stu-id="6b4b3-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="6b4b3-144">[検索 **] バー** のドロップダウン **メニューから** [ユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="6b4b3-145">[検索] フィールドにユーザー アカウント **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="6b4b3-146">検索アイコンをクリックするか、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="6b4b3-147">クエリ テキストに一致するユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="6b4b3-148">ユーザー アカウントのドメインと名前、ユーザー アカウントが最後に表示された時間、および過去 30 日間にログオンしたデバイスの総数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="6b4b3-149">結果は、次の期間でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="6b4b3-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="6b4b3-150">1 日</span><span class="sxs-lookup"><span data-stu-id="6b4b3-150">1 day</span></span>
- <span data-ttu-id="6b4b3-151">3 日間</span><span class="sxs-lookup"><span data-stu-id="6b4b3-151">3 days</span></span>
- <span data-ttu-id="6b4b3-152">7 日間</span><span class="sxs-lookup"><span data-stu-id="6b4b3-152">7 days</span></span>
- <span data-ttu-id="6b4b3-153">30 日間</span><span class="sxs-lookup"><span data-stu-id="6b4b3-153">30 days</span></span>
- <span data-ttu-id="6b4b3-154">6 か月</span><span class="sxs-lookup"><span data-stu-id="6b4b3-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b4b3-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b4b3-155">Related topics</span></span>

- [<span data-ttu-id="6b4b3-156">Microsoft Defender for Endpoint Alerts キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="6b4b3-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="6b4b3-157">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="6b4b3-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="6b4b3-158">Microsoft Defender for Endpoint アラートの調査</span><span class="sxs-lookup"><span data-stu-id="6b4b3-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="6b4b3-159">Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="6b4b3-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="6b4b3-160">Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="6b4b3-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="6b4b3-161">Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="6b4b3-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="6b4b3-162">Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="6b4b3-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
