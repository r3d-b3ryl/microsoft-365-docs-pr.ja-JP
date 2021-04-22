---
title: Microsoft Defender for Endpoint サービスのオフボード デバイス
description: Microsoft Defender for Endpoint サービスのオンボード Windows 10 デバイス、サーバー、Windows 以外のデバイス
keywords: offboarding, Microsoft Defender for Endpoint offboarding, offboarding
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934155"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="fbf08-104">Microsoft Defender for Endpoint サービスのオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="fbf08-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fbf08-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fbf08-105">**Applies to:**</span></span>
- [<span data-ttu-id="fbf08-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fbf08-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fbf08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbf08-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fbf08-108">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="fbf08-108">**Platforms**</span></span>
- <span data-ttu-id="fbf08-109">macOS</span><span class="sxs-lookup"><span data-stu-id="fbf08-109">macOS</span></span>
- <span data-ttu-id="fbf08-110">Linux</span><span class="sxs-lookup"><span data-stu-id="fbf08-110">Linux</span></span>
- <span data-ttu-id="fbf08-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fbf08-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="fbf08-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="fbf08-112">Windows Server 2016</span></span>

><span data-ttu-id="fbf08-113">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fbf08-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fbf08-114">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fbf08-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="fbf08-115">使用する展開方法に応じて、対応する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fbf08-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="fbf08-116">オフボード後、デバイスの状態 [は非アクティブ](fix-unhealthy-sensors.md#inactive-devices) 7 日に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="fbf08-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="fbf08-117">オフボードされたデバイスのデータ (タイムライン、アラート、脆弱性など) は、構成された保持期間が経過するまでポータル [に](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) 残ります。</span><span class="sxs-lookup"><span data-stu-id="fbf08-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="fbf08-118">デバイスのプロファイル (データなし) は、デバイス[](machines-view-overview.md)リストに 180 日間以上残ります。</span><span class="sxs-lookup"><span data-stu-id="fbf08-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="fbf08-119">さらに、過去 30 日間にアクティブではないデバイスは、組織の脅威と脆弱性管理の露出スコアと Microsoft Secure Score for Devices[](tvm-exposure-score.md)を反映するデータには考慮されません。</span><span class="sxs-lookup"><span data-stu-id="fbf08-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="fbf08-120">アクティブなデバイスのみを表示するには、正常性状態、[](machines-view-overview.md#health-state)デバイス タグ、または[コンピューター グループで](machine-tags.md)[フィルター処理できます](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="fbf08-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="fbf08-121">Windows 10 デバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="fbf08-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="fbf08-122">ローカル スクリプトを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="fbf08-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="fbf08-123">グループ ポリシーを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="fbf08-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="fbf08-124">モバイル デバイス管理ツールを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="fbf08-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="fbf08-125">オフボード サーバー</span><span class="sxs-lookup"><span data-stu-id="fbf08-125">Offboard Servers</span></span>
- [<span data-ttu-id="fbf08-126">オフボード サーバー</span><span class="sxs-lookup"><span data-stu-id="fbf08-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="fbf08-127">Windows 以外のオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="fbf08-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="fbf08-128">Windows 以外のオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="fbf08-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

