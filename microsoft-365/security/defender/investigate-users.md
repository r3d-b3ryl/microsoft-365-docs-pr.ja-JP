---
title: Microsoft 365 セキュリティ センターのユーザーを調査する
description: Microsoft 365 セキュリティ センターのユーザーを調査する
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、モニター、レポート、ID、データ、デバイス、アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: f48716ebd9e25d1f8b24d9276aaa5890a335a808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060726"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="12be2-104">Microsoft 365 セキュリティ センターのユーザーを調査する</span><span class="sxs-lookup"><span data-stu-id="12be2-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="12be2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="12be2-105">**Applies to:**</span></span>

- <span data-ttu-id="12be2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12be2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="12be2-107">調査の一環として、ユーザーが侵害されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12be2-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="12be2-108">Microsoft 365 セキュリティ センターのユーザー ページでは、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Cloud App Security の情報を組み合わせたもの (ライセンスに応じて異なる)。</span><span class="sxs-lookup"><span data-stu-id="12be2-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="12be2-109">このページは、ユーザーと潜在的なインシデントを調査する理想的な開始場所です。</span><span class="sxs-lookup"><span data-stu-id="12be2-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="12be2-110">![[ユーザー] ページ](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="12be2-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="12be2-111">このページには、ユーザーのセキュリティ リスクに固有の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="12be2-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="12be2-112">これには、リスクの評価に役立つスコア、ユーザーの全体的なリスクに寄与した最近のイベントやアラートなどです。</span><span class="sxs-lookup"><span data-stu-id="12be2-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="12be2-113">このページには、Microsoft 365 セキュリティ センターの複数の領域からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="12be2-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="12be2-114">このページには、[ユーザー] タブの特定のインシデントから **アクセス** できます。一部のアラートには、影響を受ける特定のアセットとしてユーザーが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="12be2-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="12be2-115">ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="12be2-115">You can also search for users.</span></span>  

<span data-ttu-id="12be2-116">ユーザーと潜在的なリスクを調査する方法の詳細については、この Cloud App Security チュートリアル [を参照してください](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)。</span><span class="sxs-lookup"><span data-stu-id="12be2-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="12be2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="12be2-117">Related topics</span></span>

- [<span data-ttu-id="12be2-118">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="12be2-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="12be2-119">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="12be2-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="12be2-120">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="12be2-120">Manage incidents</span></span>](manage-incidents.md)