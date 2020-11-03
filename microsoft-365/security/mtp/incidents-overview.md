---
title: Microsoft 365 Defender のインシデントの概要
description: デバイス、ユーザー、メールボックス全体で発生したインシデントを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e5ac3e9a02c333d3168c328aa6ad5532c48af99e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846690"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="d8baa-104">Microsoft 365 Defender のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="d8baa-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d8baa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d8baa-105">**Applies to:**</span></span>
- <span data-ttu-id="d8baa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8baa-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d8baa-107">インシデントは、関連するアラートに基づいています。</span><span class="sxs-lookup"><span data-stu-id="d8baa-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="d8baa-108">アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="d8baa-109">個々のアラートは、進行中の攻撃に関する有益な手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="d8baa-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="d8baa-110">ただし、攻撃では通常、違反を実行するためのさまざまなベクターと手法が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="d8baa-111">Piecing 個別のヒントを一緒に使用することは困難で時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d8baa-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="d8baa-112">この短いビデオは、Microsoft 365 Defender のインシデントの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8baa-112">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="d8baa-113">インシデントとは、攻撃のストーリーを構成する、相互に関連する警告のコレクションのことです。</span><span class="sxs-lookup"><span data-stu-id="d8baa-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="d8baa-114">ネットワーク内のさまざまなデバイス、ユーザー、およびメールボックスエンティティで検出された悪意のあるイベントと疑わしいイベントは、Microsoft 365 Defender によって自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="d8baa-115">関連するアラートをインシデントにグループ化することにより、セキュリティ defenders が攻撃の包括的なビューになります。</span><span class="sxs-lookup"><span data-stu-id="d8baa-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="d8baa-116">たとえば、セキュリティ defenders は、攻撃がどこで開始されたか、どのような戦術を使用したか、およびその攻撃がネットワークにどのくらいの時間が経過したかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="d8baa-117">また、デバイス、ユーザー、メールボックスの数、影響の深刻度、影響を受けるエンティティに関するその他の詳細など、攻撃の範囲を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="d8baa-118">有効にした場合、Microsoft 365 Defender は自動化および人工知能によって個々の通知を自動的に調査および解決できます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-118">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="d8baa-119">セキュリティ defenders は、インシデントビューから直接攻撃を解決するために、追加の修復手順を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="d8baa-120">過去30日間のインシデントは、インシデントキューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="d8baa-121">ここから、セキュリティ defenders は、リスクレベルやその他の要因に基づいて、どのインシデントに優先度を設定する必要があるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="d8baa-122">セキュリティ defenders は、インシデントの名前を変更したり、インシデントに対して個別のアナリストに割り当てたり、インシデントにタグを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d8baa-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="d8baa-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8baa-123">See also</span></span>
- [<span data-ttu-id="d8baa-124">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="d8baa-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="d8baa-125">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="d8baa-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d8baa-126">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="d8baa-126">Manage incidents</span></span>](manage-incidents.md)
