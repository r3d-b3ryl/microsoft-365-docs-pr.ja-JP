---
title: Microsoft Threat Protection のインシデントを調査する
description: デバイス、ユーザー、メールボックス全体で発生したインシデントを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 989184c5dd8af6aafc525100e34e0172d96adcfe
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911326"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="301e2-104">Microsoft Threat Protection のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="301e2-104">Incidents overview in Microsoft Threat Protection</span></span>

<span data-ttu-id="301e2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="301e2-105">**Applies to:**</span></span>
- <span data-ttu-id="301e2-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="301e2-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="301e2-107">すべてのインシデントの基本はアラートです。</span><span class="sxs-lookup"><span data-stu-id="301e2-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="301e2-108">アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="301e2-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="301e2-109">個々のアラートは、個々のイベントまたはエンティティで何が起こっているかについての貴重なヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="301e2-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="301e2-110">ただし、攻撃は通常、さまざまな攻撃ベクトルを使用して侵害を実行します。</span><span class="sxs-lookup"><span data-stu-id="301e2-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="301e2-111">個々のヒントを組み合わせることは、困難で時間のかかる作業です。</span><span class="sxs-lookup"><span data-stu-id="301e2-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="301e2-112">Microsoft Threat Protection は、個々のアラートを集めて全容を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="301e2-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="301e2-113">次のエンティティでの悪意のあるイベントは、Microsoft 365 セキュリティ センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="301e2-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="301e2-114">デバイス</span><span class="sxs-lookup"><span data-stu-id="301e2-114">Devices</span></span>
- <span data-ttu-id="301e2-115">ユーザー</span><span class="sxs-lookup"><span data-stu-id="301e2-115">Users</span></span>
- <span data-ttu-id="301e2-116">メールボックス</span><span class="sxs-lookup"><span data-stu-id="301e2-116">Mailboxes</span></span>

<span data-ttu-id="301e2-117">大規模な攻撃の一部である特性を示す疑わしいイベントがインシデントに集計されます。</span><span class="sxs-lookup"><span data-stu-id="301e2-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="301e2-118">攻撃が開始された場所や、攻撃の範囲を正確に把握できるその他の詳細情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="301e2-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="301e2-119">このプラットフォームは、セキュリティの防御側に正しいビジュアルとデータ表現を提供し、複雑なエンティティ間の脅威を理解し、対処できるようにします。</span><span class="sxs-lookup"><span data-stu-id="301e2-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="301e2-120">攻撃の範囲を把握できるだけでなく、インシデントを阻止するための戦術的な手順を実行できるサービスも利用できます。</span><span class="sxs-lookup"><span data-stu-id="301e2-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="301e2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="301e2-121">Related topics</span></span>
- [<span data-ttu-id="301e2-122">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="301e2-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="301e2-123">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="301e2-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="301e2-124">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="301e2-124">Manage incidents</span></span>](manage-incidents.md)