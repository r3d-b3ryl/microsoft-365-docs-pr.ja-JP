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
ms.technology: m365d
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929284"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="61e0e-104">Microsoft 365 Defender のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="61e0e-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="61e0e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="61e0e-105">**Applies to:**</span></span>
- <span data-ttu-id="61e0e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61e0e-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="61e0e-107">Microsoft 365 Defender を体験したい場合</span><span class="sxs-lookup"><span data-stu-id="61e0e-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="61e0e-108">ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="61e0e-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="61e0e-109">インシデントは、関連するアラートに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="61e0e-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="61e0e-110">アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="61e0e-111">個々のアラートは、攻撃が続く場合の貴重な手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="61e0e-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="61e0e-112">ただし、攻撃は通常、侵害を実行するためにさまざまなベクトルと手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="61e0e-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="61e0e-113">個々の手がかりを組み合わせてまとめる作業は、困難で時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61e0e-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="61e0e-114">この短いビデオでは、Microsoft 365 Defender のインシデントの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="61e0e-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="61e0e-115">インシデントとは、攻撃のストーリーを構成する関連付けされたアラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="61e0e-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="61e0e-116">ネットワーク内の異なるデバイス、ユーザー、およびメールボックス エンティティで検出された悪意のあるイベントと疑わしいイベントは、Microsoft 365 Defender によって自動的に集約されます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="61e0e-117">関連するアラートをインシデントにグループ化すると、セキュリティ防御側は攻撃の包括的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="61e0e-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="61e0e-118">たとえば、セキュリティ防御側は、攻撃の開始場所、使用された方法、および攻撃がネットワークにどこまで進むかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="61e0e-119">また、影響を受けたデバイス、ユーザー、メールボックスの数、影響の重大さ、影響を受けたエンティティに関するその他の詳細など、攻撃の範囲を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="61e0e-120">有効にした場合、Microsoft 365 Defender は自動化と人工知能を通じて個々のアラートを自動的に調査して解決できます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="61e0e-121">セキュリティ防御側は、インシデント ビューから直接攻撃を解決するための追加の修復手順を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="61e0e-122">過去 30 日間のインシデントがインシデント キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="61e0e-123">ここから、セキュリティの防御側は、リスク レベルなどの要因に基づいて、どのインシデントに優先順位を付ける必要があるのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="61e0e-124">セキュリティ防御側は、インシデントの名前を変更したり、インシデントを個々のアナリストに割り当て、インシデントにタグを分類したり、インシデントにタグを追加したりして、より優れたカスタマイズされたインシデント管理エクスペリエンスを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="61e0e-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="61e0e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="61e0e-125">See also</span></span>
- [<span data-ttu-id="61e0e-126">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="61e0e-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="61e0e-127">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="61e0e-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="61e0e-128">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="61e0e-128">Manage incidents</span></span>](manage-incidents.md)
