---
title: エンドポイント インシデントの Microsoft Defender の管理
description: インシデントの割り当て、状態の更新、または分類の設定によってインシデントを管理します。
keywords: インシデント、管理、割り当て、状態、分類、真のアラート、誤ったアラート
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: abb538972b48f8790286c0a546eecdd69fc83fb5
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862141"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="c1e0f-104">エンドポイント インシデントの Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="c1e0f-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c1e0f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c1e0f-105">**Applies to:**</span></span>
- [<span data-ttu-id="c1e0f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c1e0f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c1e0f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1e0f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c1e0f-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="c1e0f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c1e0f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c1e0f-110">インシデントの管理は、すべてのサイバーセキュリティ操作の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="c1e0f-111">インシデントを管理するには、[インシデント] キューまたは [インシデント管理] ウィンドウからインシデント **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="c1e0f-112">インシデント キューからインシデントを選択すると、[インシデント管理]ウィンドウが表示されます。インシデントの詳細については、インシデント ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![インシデント管理ウィンドウのイメージ](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="c1e0f-114">インシデントを自分に割り当て、ステータスと分類を変更したり、名前を変更したり、コメントを付け、進捗状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="c1e0f-115">一目で見たインシデント名は、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="c1e0f-116">これにより、インシデントの範囲をすばやく理解できます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="c1e0f-117">たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*</span><span class="sxs-lookup"><span data-stu-id="c1e0f-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="c1e0f-118">自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![インシデントの詳細ページの画像](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="c1e0f-120">インシデントを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c1e0f-120">Assign incidents</span></span>
<span data-ttu-id="c1e0f-121">インシデントがまだ割り当てられていない場合は、[自分に割り当てる] を選択して、インシデントを自分に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="c1e0f-122">これにより、インシデントの所有権だけでなくそのインシデントと関連するすべての警告の所有権が自分に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="c1e0f-123">状態と分類を設定する</span><span class="sxs-lookup"><span data-stu-id="c1e0f-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="c1e0f-124">インシデントの状態</span><span class="sxs-lookup"><span data-stu-id="c1e0f-124">Incident status</span></span>
<span data-ttu-id="c1e0f-125">インシデントは、調査の進捗に合わせて状態を変更することにより、**Active (アクティブ)** または **Resolved (解決済み)** に分類できます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="c1e0f-126">こうすることで、チームでのインシデントへの対応方法を整理して管理できます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="c1e0f-127">たとえば、SoC アナリストは、その日の緊急 **の** アクティブ インシデントを確認し、調査のために自分に割り当てました。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="c1e0f-128">または、インシデントが修復された場合、SoC アナリストがインシデントを **解決** 済みとして設定する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="c1e0f-129">分類</span><span class="sxs-lookup"><span data-stu-id="c1e0f-129">Classification</span></span>
<span data-ttu-id="c1e0f-130">分類を設定しないことも、インシデントが真または偽であると指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="c1e0f-131">こうすることで、チームにはインシデントの傾向が示され、チームの学習につながります。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="c1e0f-132">コメントを追加する</span><span class="sxs-lookup"><span data-stu-id="c1e0f-132">Add comments</span></span>
<span data-ttu-id="c1e0f-133">警告にはコメントを追加することができ、インシデントに関する過去のイベントを表示して、以前に行われた変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="c1e0f-134">警告に変更またはコメントが加えられるたびに、[Comments and history (コメントと履歴)] セクションに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="c1e0f-135">追加されたコメントは直ちにウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1e0f-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="c1e0f-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1e0f-136">Related topics</span></span>
- [<span data-ttu-id="c1e0f-137">インシデント キュー</span><span class="sxs-lookup"><span data-stu-id="c1e0f-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="c1e0f-138">インシデント キューを表示および整理する</span><span class="sxs-lookup"><span data-stu-id="c1e0f-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="c1e0f-139">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="c1e0f-139">Investigate incidents</span></span>](investigate-incidents.md)
