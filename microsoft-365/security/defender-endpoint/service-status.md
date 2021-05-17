---
title: Microsoft Defender for Endpoint サービスの正常性を確認する
description: Microsoft Defender for Endpoint Service の正常性を確認し、サービスに問題が発生していないかを確認し、解決された以前の問題を確認します。
keywords: ダッシュボード、サービス、問題、サービス正常性、現在の状態、状態履歴、影響の概要、予備的な根本原因、解決時間、解決時間、予想される解決時間
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
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687627"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="7e92e-104">Microsoft Defender for Endpoint サービスの正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="7e92e-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7e92e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7e92e-105">**Applies to:**</span></span>
- [<span data-ttu-id="7e92e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e92e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="7e92e-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="7e92e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7e92e-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7e92e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="7e92e-109">**サービス正常性は** 、Defender for Endpoint サービスの現在の状態に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e92e-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="7e92e-110">サービスの正常性が正常か、現在の問題が発生した場合に確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="7e92e-111">問題がある場合は、問題が検出された時期、根本的な予備的な原因、予想される解決時間などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="7e92e-112">また、解決された過去の問題に関する情報や、問題が解決された日時などの詳細も表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="7e92e-113">サービスに問題がない場合は、正常な状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="7e92e-114">サービス正常性の詳細を表示するには、セキュリティ操作ダッシュボードからタイルをクリックするか、ナビゲーション ウィンドウから[サービス正常性] メニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e92e-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="7e92e-115">[ **サービス正常性の詳細** ] ページには、次のタブがあります。</span><span class="sxs-lookup"><span data-stu-id="7e92e-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="7e92e-116">**現在の状態**</span><span class="sxs-lookup"><span data-stu-id="7e92e-116">**Current status**</span></span>
- <span data-ttu-id="7e92e-117">**状態履歴**</span><span class="sxs-lookup"><span data-stu-id="7e92e-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="7e92e-118">現在の状態</span><span class="sxs-lookup"><span data-stu-id="7e92e-118">Current status</span></span>
<span data-ttu-id="7e92e-119">[ **現在の状態]** タブには、Defender for Endpoint サービスの現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="7e92e-120">サービスがスムーズに実行されている場合は、正常なサービスの正常性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="7e92e-121">問題が見られる場合は、問題に関するより良い洞察を得るために、次のサービスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="7e92e-122">問題が検出された日時</span><span class="sxs-lookup"><span data-stu-id="7e92e-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="7e92e-123">問題の簡単な説明</span><span class="sxs-lookup"><span data-stu-id="7e92e-123">A short description of the issue</span></span>
- <span data-ttu-id="7e92e-124">更新時間</span><span class="sxs-lookup"><span data-stu-id="7e92e-124">Update time</span></span>
- <span data-ttu-id="7e92e-125">影響の概要</span><span class="sxs-lookup"><span data-stu-id="7e92e-125">Summary of impact</span></span>
- <span data-ttu-id="7e92e-126">予備的な根本原因</span><span class="sxs-lookup"><span data-stu-id="7e92e-126">Preliminary root cause</span></span>
- <span data-ttu-id="7e92e-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="7e92e-127">Next steps</span></span>
- <span data-ttu-id="7e92e-128">予想される解決時間</span><span class="sxs-lookup"><span data-stu-id="7e92e-128">Expected resolution time</span></span>

<span data-ttu-id="7e92e-129">問題の進行状況に関する更新プログラムは、問題が解決されるにつれてページに反映されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="7e92e-130">更新された推定解決時間や次の手順などの情報に関する更新プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="7e92e-131">問題が解決すると、[状態の履歴] タブに **記録** されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="7e92e-132">状態履歴</span><span class="sxs-lookup"><span data-stu-id="7e92e-132">Status history</span></span>
<span data-ttu-id="7e92e-133">[ **状態の履歴]** タブには、表示および解決されたすべての履歴問題が反映されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="7e92e-134">解決された問題の詳細と、解決中に含まれるその他の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e92e-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="7e92e-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7e92e-135">Related topic</span></span>
- [<span data-ttu-id="7e92e-136">セキュリティ操作ダッシュボードの表示</span><span class="sxs-lookup"><span data-stu-id="7e92e-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
