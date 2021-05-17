---
title: アラートに関連付けられた IP アドレスを調査する
description: 調査オプションを使用して、デバイスと外部 IP アドレス間の通信の可能性を調べる。
keywords: 調査、調査、IP アドレス、アラート、Microsoft Defender for Endpoint、外部 IP
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
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933831"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="a27a4-104">Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="a27a4-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a27a4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a27a4-105">**Applies to:**</span></span>
- [<span data-ttu-id="a27a4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a27a4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a27a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a27a4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a27a4-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a27a4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a27a4-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="a27a4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a27a4-110">デバイスと外部インターネット プロトコル (IP) アドレス間の通信の可能性を調べる。</span><span class="sxs-lookup"><span data-stu-id="a27a4-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="a27a4-111">Command and Control (C2) サーバーなど、疑わしいまたは既知の悪意のある IP アドレスと通信した組織内のすべてのデバイスを識別すると、侵害、関連ファイル、感染したデバイスの潜在的な範囲を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="a27a4-112">IP アドレス ビューでは、次のセクションから情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="a27a4-113">世界中の IP</span><span class="sxs-lookup"><span data-stu-id="a27a4-113">IP worldwide</span></span>
- <span data-ttu-id="a27a4-114">DNS 名の逆引き</span><span class="sxs-lookup"><span data-stu-id="a27a4-114">Reverse DNS names</span></span>
- <span data-ttu-id="a27a4-115">この IP に関連するアラート</span><span class="sxs-lookup"><span data-stu-id="a27a4-115">Alerts related to this IP</span></span>
- <span data-ttu-id="a27a4-116">組織内の IP</span><span class="sxs-lookup"><span data-stu-id="a27a4-116">IP in organization</span></span>
- <span data-ttu-id="a27a4-117">有病率</span><span class="sxs-lookup"><span data-stu-id="a27a4-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="a27a4-118">IP Worldwide および Reverse DNS 名</span><span class="sxs-lookup"><span data-stu-id="a27a4-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="a27a4-119">[IP アドレスの詳細] セクションには、その ASN やリバース DNS 名などの IP アドレスの属性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="a27a4-120">この IP に関連するアラート</span><span class="sxs-lookup"><span data-stu-id="a27a4-120">Alerts related to this IP</span></span>

<span data-ttu-id="a27a4-121">[ **この IP に関連するアラート** ] セクションには、IP に関連付けられているアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="a27a4-122">組織内の IP</span><span class="sxs-lookup"><span data-stu-id="a27a4-122">IP in organization</span></span>

<span data-ttu-id="a27a4-123">[ **組織内の IP]** セクションには、組織内の IP アドレスの普及率に関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="a27a4-124">有病率</span><span class="sxs-lookup"><span data-stu-id="a27a4-124">Prevalence</span></span>

<span data-ttu-id="a27a4-125">[ **有病率** ] セクションには、この IP アドレスに接続したデバイスの数と、IP が最初と最後に表示された時点が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="a27a4-126">このセクションの結果は、期間別にフィルター処理できます。既定の期間は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="a27a4-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="a27a4-127">IP を含む最新の観測デバイス</span><span class="sxs-lookup"><span data-stu-id="a27a4-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="a27a4-128">[IP **を含む最新** の観測デバイス] セクションには、IP アドレスで観測されたイベントと関連するアラートに関する時系列ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="a27a4-129">**外部 IP を調査します。**</span><span class="sxs-lookup"><span data-stu-id="a27a4-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="a27a4-130">[検索] バーの **ドロップダウン メニューから** **[IP]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a27a4-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="a27a4-131">[検索] フィールドに IP アドレス **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="a27a4-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="a27a4-132">検索アイコンをクリックするか、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="a27a4-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="a27a4-133">IP アドレスの詳細は、登録の詳細 (利用可能な場合)、リバース IP (ドメインなど)、この IP アドレスと通信した組織内のデバイスの普及率 (選択可能な期間中)、およびこの IP アドレスとの通信が観察された組織内のデバイスなど、表示されます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="a27a4-134">検索結果は、組織内のデバイスとの通信で観察された IP アドレスに対してのみ返されます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="a27a4-135">検索条件を定義するには、検索フィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a27a4-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="a27a4-136">タイムライン検索ボックスを使用して、IP アドレス、通信に関連付けられたファイル、および最後に観測された日付と通信している組織内のすべてのデバイスの表示結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="a27a4-137">デバイス名をクリックすると、そのデバイスのビューにアクセスし、報告されたアラート、動作、およびイベントを引き続き調査できます。</span><span class="sxs-lookup"><span data-stu-id="a27a4-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a27a4-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="a27a4-138">Related topics</span></span>

- [<span data-ttu-id="a27a4-139">Microsoft Defender for Endpoint Alerts キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="a27a4-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="a27a4-140">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="a27a4-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="a27a4-141">Microsoft Defender for Endpoint アラートの調査</span><span class="sxs-lookup"><span data-stu-id="a27a4-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="a27a4-142">Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="a27a4-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="a27a4-143">Microsoft Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="a27a4-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="a27a4-144">Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="a27a4-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="a27a4-145">Microsoft Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="a27a4-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
