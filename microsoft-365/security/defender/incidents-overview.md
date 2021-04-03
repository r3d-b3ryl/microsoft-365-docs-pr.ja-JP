---
title: Microsoft 365 Defender のインシデントの概要
description: デバイス、ユーザー、メールボックス全体で発生したインシデントを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6dd13c5f83d05be3c77e5f84608fb6aa5172d9a4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500921"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="dce58-104">Microsoft 365 Defender のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="dce58-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dce58-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dce58-105">**Applies to:**</span></span>
- <span data-ttu-id="dce58-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dce58-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="dce58-107">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="dce58-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="dce58-108">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="dce58-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="dce58-109">インシデントは、関連するアラートに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="dce58-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="dce58-110">アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="dce58-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="dce58-111">個々のアラートは、オンナ攻撃に関する貴重な手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="dce58-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="dce58-112">ただし、攻撃は通常、侵害を実行するためにさまざまなベクトルと手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="dce58-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="dce58-113">個々の手がかりを一緒にまとめる作業は、困難で時間のかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dce58-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="dce58-114">この短いビデオでは、Microsoft 365 Defender でのインシデントの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="dce58-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="dce58-115">インシデントとは、攻撃のストーリーを構成する相関アラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="dce58-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="dce58-116">ネットワーク内の異なるデバイス、ユーザー、およびメールボックス エンティティで検出された悪意のあるイベントと疑わしいイベントは、Microsoft 365 Defender によって自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="dce58-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="dce58-117">関連するアラートをインシデントにグループ化すると、セキュリティ防御者は攻撃の包括的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="dce58-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="dce58-118">たとえば、セキュリティ防御者は、攻撃の開始場所、使用された戦術、およびネットワークへの攻撃の行方を確認できます。</span><span class="sxs-lookup"><span data-stu-id="dce58-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="dce58-119">また、影響を受けたデバイス、ユーザー、メールボックスの数、影響を受けた影響の大きさ、影響を受けるエンティティに関するその他の詳細など、攻撃の範囲を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="dce58-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="dce58-120">有効にした場合、Microsoft 365 Defender は自動化と人工知能を通じて個々のアラートを自動的に調査して解決できます。</span><span class="sxs-lookup"><span data-stu-id="dce58-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="dce58-121">セキュリティ防御側は、インシデント ビューから直接攻撃を解決するための追加の修復手順を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="dce58-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="dce58-122">過去 30 日間のインシデントがインシデント キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dce58-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="dce58-123">ここから、セキュリティディフェンダーは、リスク レベルや他の要因に基づいて、どのインシデントを優先順位付けする必要があるのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="dce58-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="dce58-124">セキュリティ防御者は、インシデントの名前を変更したり、個々のアナリストに割り当て、分類したり、インシデントにタグを追加したりして、よりカスタマイズされたインシデント管理エクスペリエンスを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="dce58-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="dce58-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="dce58-125">See also</span></span>
- [<span data-ttu-id="dce58-126">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="dce58-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="dce58-127">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="dce58-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="dce58-128">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="dce58-128">Manage incidents</span></span>](manage-incidents.md)