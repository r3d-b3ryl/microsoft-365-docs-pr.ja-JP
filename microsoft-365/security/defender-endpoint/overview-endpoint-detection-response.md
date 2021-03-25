---
title: エンドポイントの検出および応答機能の概要
ms.reviewer: ''
description: Microsoft Defender ATP のエンドポイント検出および応答機能について説明します。
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
ms.technology: mde
ms.openlocfilehash: 858ea0f8d46ac2489dd6ef5c10caf2ce0879e4fb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068483"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="de1a0-103">エンドポイントの検出と応答の概要</span><span class="sxs-lookup"><span data-stu-id="de1a0-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="de1a0-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="de1a0-104">**Applies to:**</span></span>
- [<span data-ttu-id="de1a0-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de1a0-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="de1a0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de1a0-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="de1a0-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="de1a0-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="de1a0-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="de1a0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="de1a0-109">Defender for Endpoint endpoint detection and response capabilitis provide advanced attack detections are near real-time and actionable.</span><span class="sxs-lookup"><span data-stu-id="de1a0-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="de1a0-110">セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="de1a0-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="de1a0-111">脅威が検出されると、システムでアラートが生成され、アナリストが調査します。</span><span class="sxs-lookup"><span data-stu-id="de1a0-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="de1a0-112">同じ攻撃技法のアラートや同じ攻撃者によるアラートは、_incident_ と呼ばれるエンティティに集約されます。</span><span class="sxs-lookup"><span data-stu-id="de1a0-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="de1a0-113">この方法でアラートを集約すると、アナリストは脅威への総合的な調査や対応が簡単にできるようになります。</span><span class="sxs-lookup"><span data-stu-id="de1a0-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="de1a0-114">「侵害を想定する」という考え方にインスパイアされた Defender for Endpoint は、継続的に行動サイバー テレメトリを収集します。</span><span class="sxs-lookup"><span data-stu-id="de1a0-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="de1a0-115">これには、プロセス情報、ネットワーク活動、カーネルおよびメモリ マネージャーの詳細分析、ユーザー ログイン活動、レジストリとファイル システムの変更内容などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de1a0-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="de1a0-116">この情報は 6 か月間保存されるため、アナリストは攻撃の開始時点まで時間を遡ることができます。</span><span class="sxs-lookup"><span data-stu-id="de1a0-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="de1a0-117">そのアナリストは各種ビューをピボットして、複数のベクトルから調査に取り組むことができます。</span><span class="sxs-lookup"><span data-stu-id="de1a0-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="de1a0-118">対応機能により、影響を受けているエンティティに対策を講じることで、すばやく脅威に対処できるようになります。</span><span class="sxs-lookup"><span data-stu-id="de1a0-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="de1a0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="de1a0-119">Related topics</span></span>
- [<span data-ttu-id="de1a0-120">セキュリティ運用ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="de1a0-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="de1a0-121">インシデント キュー</span><span class="sxs-lookup"><span data-stu-id="de1a0-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="de1a0-122">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="de1a0-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="de1a0-123">デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="de1a0-123">Devices list</span></span>](machines-view-overview.md)

