---
title: エンドポイントの検出および応答機能の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint のエンドポイント検出および応答機能について説明します。
keywords: エンドポイントの Microsoft Defender、エンドポイントの検出と応答、応答、検出、サイバーセキュリティ、保護
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
ms.openlocfilehash: b00bef611a3e4b33bf15a5366b09a96f68d4c1a2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933519"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="7158b-104">エンドポイントの検出と応答の概要</span><span class="sxs-lookup"><span data-stu-id="7158b-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7158b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7158b-105">**Applies to:**</span></span>
- [<span data-ttu-id="7158b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7158b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7158b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7158b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7158b-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="7158b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7158b-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7158b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7158b-110">Defender for Endpoint endpoint detection and response capabilitis provide advanced attack detections are near real-time and actionable.</span><span class="sxs-lookup"><span data-stu-id="7158b-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="7158b-111">セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="7158b-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="7158b-112">脅威が検出されると、システムでアラートが生成され、アナリストが調査します。</span><span class="sxs-lookup"><span data-stu-id="7158b-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="7158b-113">同じ攻撃技法のアラートや同じ攻撃者によるアラートは、_incident_ と呼ばれるエンティティに集約されます。</span><span class="sxs-lookup"><span data-stu-id="7158b-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="7158b-114">この方法でアラートを集約すると、アナリストは脅威への総合的な調査や対応が簡単にできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7158b-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="7158b-115">「侵害を想定する」という考え方にインスパイアされた Defender for Endpoint は、継続的に行動サイバー テレメトリを収集します。</span><span class="sxs-lookup"><span data-stu-id="7158b-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="7158b-116">これには、プロセス情報、ネットワーク活動、カーネルおよびメモリ マネージャーの詳細分析、ユーザー ログイン活動、レジストリとファイル システムの変更内容などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7158b-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="7158b-117">この情報は 6 か月間保存されるため、アナリストは攻撃の開始時点まで時間を遡ることができます。</span><span class="sxs-lookup"><span data-stu-id="7158b-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="7158b-118">そのアナリストは各種ビューをピボットして、複数のベクトルから調査に取り組むことができます。</span><span class="sxs-lookup"><span data-stu-id="7158b-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="7158b-119">対応機能により、影響を受けているエンティティに対策を講じることで、すばやく脅威に対処できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7158b-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7158b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7158b-120">Related topics</span></span>
- [<span data-ttu-id="7158b-121">セキュリティ運用ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="7158b-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="7158b-122">インシデント キュー</span><span class="sxs-lookup"><span data-stu-id="7158b-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="7158b-123">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="7158b-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="7158b-124">デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="7158b-124">Devices list</span></span>](machines-view-overview.md)

