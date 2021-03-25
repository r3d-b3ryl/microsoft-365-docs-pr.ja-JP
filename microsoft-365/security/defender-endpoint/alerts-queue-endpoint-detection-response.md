---
title: Microsoft Defender セキュリティ センターのアラート キュー
ms.reviewer: ''
description: Microsoft Defender セキュリティ センターで表示されるアラートを表示および管理する
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
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067403"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="f2afa-103">Microsoft Defender セキュリティ センターのアラート キュー</span><span class="sxs-lookup"><span data-stu-id="f2afa-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2afa-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f2afa-104">**Applies to:**</span></span>
- [<span data-ttu-id="f2afa-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f2afa-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="f2afa-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f2afa-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2afa-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f2afa-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f2afa-108">デバイス、ファイル、ユーザー アカウントなどのエンティティに見られる脅威を効果的に調査するために、キューを表示および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f2afa-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f2afa-109">In this section</span></span>
<span data-ttu-id="f2afa-110">トピック</span><span class="sxs-lookup"><span data-stu-id="f2afa-110">Topic</span></span> | <span data-ttu-id="f2afa-111">説明</span><span class="sxs-lookup"><span data-stu-id="f2afa-111">Description</span></span> 
:---|:---
[<span data-ttu-id="f2afa-112">アラート キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="f2afa-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="f2afa-113">ネットワークでフラグが設定されたアラートの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="f2afa-114">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="f2afa-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="f2afa-115">状態の変更、セキュリティ操作メンバーへの割り当て、アラートの履歴の確認などのアラートを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="f2afa-116">アラートを調査する</span><span class="sxs-lookup"><span data-stu-id="f2afa-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="f2afa-117">ネットワークに影響を与えるアラートを調査し、その意味と解決方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="f2afa-118">ファイルの調査</span><span class="sxs-lookup"><span data-stu-id="f2afa-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="f2afa-119">特定のアラート、動作、またはイベントに関連付けられたファイルの詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="f2afa-120">デバイスの調査</span><span class="sxs-lookup"><span data-stu-id="f2afa-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="f2afa-121">特定のアラート、動作、またはイベントに関連付けられているデバイスの詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="f2afa-122">IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="f2afa-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="f2afa-123">ネットワーク内のデバイスと外部インターネット プロトコル (IP) アドレス間の通信の可能性を調べる。</span><span class="sxs-lookup"><span data-stu-id="f2afa-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="f2afa-124">ドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="f2afa-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="f2afa-125">ネットワーク内のデバイスとサーバーが既知の悪意のあるドメインと通信している場合は、ドメインを調査します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="f2afa-126">ユーザー アカウントの調査</span><span class="sxs-lookup"><span data-stu-id="f2afa-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="f2afa-127">最もアクティブなアラートを使用してユーザー アカウントを特定し、潜在的に侵害された資格情報のケースを調査します。</span><span class="sxs-lookup"><span data-stu-id="f2afa-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  

