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
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357613"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="5330f-104">Microsoft 365 Defender のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="5330f-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5330f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5330f-105">**Applies to:**</span></span>
- <span data-ttu-id="5330f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5330f-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="5330f-107">Microsoft 365 Defender を利用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="5330f-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5330f-108">[ラボ環境で評価](https://aka.ms/mtp-trial-lab)することも、[運用環境でパイロットプロジェクトを実行](https://aka.ms/m365d-pilotplaybook)することもできます。</span><span class="sxs-lookup"><span data-stu-id="5330f-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="5330f-109">インシデントは、関連するアラートに基づいています。</span><span class="sxs-lookup"><span data-stu-id="5330f-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="5330f-110">アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="5330f-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="5330f-111">個々のアラートは、進行中の攻撃に関する有益な手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="5330f-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="5330f-112">ただし、攻撃では通常、違反を実行するためのさまざまなベクターと手法が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5330f-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="5330f-113">Piecing 個別のヒントを一緒に使用することは困難で時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5330f-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="5330f-114">この短いビデオは、Microsoft 365 Defender のインシデントの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="5330f-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="5330f-115">インシデントとは、攻撃のストーリーを構成する、相互に関連する警告のコレクションのことです。</span><span class="sxs-lookup"><span data-stu-id="5330f-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="5330f-116">ネットワーク内のさまざまなデバイス、ユーザー、およびメールボックスエンティティで検出された悪意のあるイベントと疑わしいイベントは、Microsoft 365 Defender によって自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="5330f-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="5330f-117">関連するアラートをインシデントにグループ化することにより、セキュリティ defenders が攻撃の包括的なビューになります。</span><span class="sxs-lookup"><span data-stu-id="5330f-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="5330f-118">たとえば、セキュリティ defenders は、攻撃がどこで開始されたか、どのような戦術を使用したか、およびその攻撃がネットワークにどのくらいの時間が経過したかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5330f-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="5330f-119">また、デバイス、ユーザー、メールボックスの数、影響の深刻度、影響を受けるエンティティに関するその他の詳細など、攻撃の範囲を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="5330f-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="5330f-120">有効にした場合、Microsoft 365 Defender は自動化および人工知能によって個々の通知を自動的に調査および解決できます。</span><span class="sxs-lookup"><span data-stu-id="5330f-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="5330f-121">セキュリティ defenders は、インシデントビューから直接攻撃を解決するために、追加の修復手順を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5330f-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="5330f-122">過去30日間のインシデントは、インシデントキューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5330f-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="5330f-123">ここから、セキュリティ defenders は、リスクレベルやその他の要因に基づいて、どのインシデントに優先度を設定する必要があるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5330f-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="5330f-124">セキュリティ defenders は、インシデントの名前を変更したり、インシデントに対して個別のアナリストに割り当てたり、インシデントにタグを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5330f-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="5330f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5330f-125">See also</span></span>
- [<span data-ttu-id="5330f-126">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="5330f-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="5330f-127">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="5330f-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5330f-128">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="5330f-128">Manage incidents</span></span>](manage-incidents.md)
