---
title: Microsoft Threat Protection のインシデントを調査する
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 95934d9884328d4311abbd0f29b96e46e0c06894
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087636"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="8ce33-104">Microsoft Threat Protection のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="8ce33-104">Incidents overview in Microsoft Threat Protection</span></span>

<span data-ttu-id="8ce33-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8ce33-105">**Applies to:**</span></span>
- <span data-ttu-id="8ce33-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8ce33-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8ce33-107">すべてのインシデントの基本はアラートです。</span><span class="sxs-lookup"><span data-stu-id="8ce33-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="8ce33-108">アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="8ce33-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="8ce33-109">個々のアラートは、個々のイベントまたはエンティティで何が起こっているかについての貴重なヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="8ce33-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="8ce33-110">ただし、攻撃は通常、さまざまな攻撃ベクトルを使用して侵害を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ce33-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="8ce33-111">個々のヒントを組み合わせることは、困難で時間のかかる作業です。</span><span class="sxs-lookup"><span data-stu-id="8ce33-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="8ce33-112">Microsoft Threat Protection は、個々のアラートを集めて全容を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="8ce33-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="8ce33-113">次のエンティティでの悪意のあるイベントは、Microsoft 365 セキュリティ センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ce33-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="8ce33-114">デバイス</span><span class="sxs-lookup"><span data-stu-id="8ce33-114">Devices</span></span>
- <span data-ttu-id="8ce33-115">ユーザー</span><span class="sxs-lookup"><span data-stu-id="8ce33-115">Users</span></span>
- <span data-ttu-id="8ce33-116">メールボックス</span><span class="sxs-lookup"><span data-stu-id="8ce33-116">Mailboxes</span></span>

<span data-ttu-id="8ce33-117">大規模な攻撃の一部である特性を示す疑わしいイベントがインシデントに集計されます。</span><span class="sxs-lookup"><span data-stu-id="8ce33-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="8ce33-118">攻撃が開始された場所や、攻撃の範囲を正確に把握できるその他の詳細情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="8ce33-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="8ce33-119">このプラットフォームは、セキュリティの防御側に正しいビジュアルとデータ表現を提供し、複雑なエンティティ間の脅威を理解し、対処できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ce33-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="8ce33-120">攻撃の範囲を把握できるだけでなく、インシデントを阻止するための戦術的な手順を実行できるサービスも利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ce33-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8ce33-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ce33-121">Related topics</span></span>
- [<span data-ttu-id="8ce33-122">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="8ce33-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="8ce33-123">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="8ce33-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="8ce33-124">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="8ce33-124">Manage incidents</span></span>](manage-incidents.md)
