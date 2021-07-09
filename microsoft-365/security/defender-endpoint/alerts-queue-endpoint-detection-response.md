---
title: アラート キュー (Microsoft 365 Defender
ms.reviewer: ''
description: ユーザーに表示される通知を表示および管理Microsoft 365 Defender
keywords: ''
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
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: ed65c836e74d5394d3b291ca3ebb5e781e37afa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339564"
---
# <a name="alerts-queue-in-microsoft-365-defender"></a><span data-ttu-id="2d24b-103">アラート キュー (Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d24b-103">Alerts queue in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d24b-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2d24b-104">**Applies to:**</span></span>
- [<span data-ttu-id="2d24b-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2d24b-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="2d24b-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="2d24b-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2d24b-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="2d24b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2d24b-108">デバイス、ファイル、ユーザー アカウントなどのエンティティに見られる脅威を効果的に調査するために、キューを表示および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2d24b-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2d24b-109">In this section</span></span>
<span data-ttu-id="2d24b-110">トピック</span><span class="sxs-lookup"><span data-stu-id="2d24b-110">Topic</span></span> | <span data-ttu-id="2d24b-111">説明</span><span class="sxs-lookup"><span data-stu-id="2d24b-111">Description</span></span> 
:---|:---
[<span data-ttu-id="2d24b-112">アラート キューを表示および整理する</span><span class="sxs-lookup"><span data-stu-id="2d24b-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="2d24b-113">ネットワークでフラグが設定されたアラートの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="2d24b-114">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="2d24b-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="2d24b-115">状態の変更、セキュリティ操作メンバーへの割り当て、アラートの履歴の確認などのアラートを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="2d24b-116">アラートの調査</span><span class="sxs-lookup"><span data-stu-id="2d24b-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="2d24b-117">ネットワークに影響を与えるアラートを調査し、その意味と解決方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="2d24b-118">ファイルの調査</span><span class="sxs-lookup"><span data-stu-id="2d24b-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="2d24b-119">特定のアラート、動作、またはイベントに関連付けられたファイルの詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="2d24b-120">デバイスの調査</span><span class="sxs-lookup"><span data-stu-id="2d24b-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="2d24b-121">特定のアラート、動作、またはイベントに関連付けられているデバイスの詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="2d24b-122">IP アドレスの調査</span><span class="sxs-lookup"><span data-stu-id="2d24b-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="2d24b-123">ネットワーク内のデバイスと外部インターネット プロトコル (IP) アドレス間の通信の可能性を調べる。</span><span class="sxs-lookup"><span data-stu-id="2d24b-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="2d24b-124">ドメインの調査</span><span class="sxs-lookup"><span data-stu-id="2d24b-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="2d24b-125">ネットワーク内のデバイスとサーバーが既知の悪意のあるドメインと通信している場合は、ドメインを調査します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="2d24b-126">ユーザー アカウントの調査</span><span class="sxs-lookup"><span data-stu-id="2d24b-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="2d24b-127">最もアクティブなアラートを使用してユーザー アカウントを特定し、潜在的に侵害された資格情報のケースを調査します。</span><span class="sxs-lookup"><span data-stu-id="2d24b-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


