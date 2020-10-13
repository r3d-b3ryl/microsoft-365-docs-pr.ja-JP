---
title: Microsoft Threat Protection でインシデントを管理する
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント、インシデント、警告、関連付けられた警告、割り当て、更新、状態、管理、分類、microsoft、365、m365
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
ms.openlocfilehash: c599343233e7e29589bc4e3d1cda01da505b16f1
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430563"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="25ab3-104">Microsoft Threat Protection でインシデントを管理する</span><span class="sxs-lookup"><span data-stu-id="25ab3-104">Manage incidents in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="25ab3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="25ab3-105">**Applies to:**</span></span>
- <span data-ttu-id="25ab3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="25ab3-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="25ab3-107">インシデントの管理は、脅威を封じ込めて対処する上でとても重要です。</span><span class="sxs-lookup"><span data-stu-id="25ab3-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="25ab3-108">Microsoft Threat Protection では、デバイス、ユーザー、およびメールボックスにおけるインシデントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="25ab3-109">インシデントを管理するには、**インシデント キュー**からインシデントを選択します。</span><span class="sxs-lookup"><span data-stu-id="25ab3-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="25ab3-110">インシデントの名前を編集し、インシデントを解決し、インシデントの分類と判定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="25ab3-111">インシデントを自分に割り当てたり、インシデント タグやコメントを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="25ab3-112">調査中にあるインシデントから別のインシデントに警告を移動する場合は、この操作は [Alerts (警告)] タブで行うこともできます。こうすることで、関連するすべての警告が含まれた大規模なインシデントまたは小規模なインシデントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="25ab3-113">インシデント名を編集する</span><span class="sxs-lookup"><span data-stu-id="25ab3-113">Edit incident name</span></span>
<span data-ttu-id="25ab3-114">インシデントには、影響を受けたエンドポイント数、影響を受けたユーザー、検出ソースまたはカテゴリなどのアラート属性に基づいて、自動的に名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="25ab3-115">これにより、インシデントの範囲をすばやく理解することができます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="25ab3-116">例: 複数の*ソースによって報告された複数のエンドポイントのマルチステージインシデント*。</span><span class="sxs-lookup"><span data-stu-id="25ab3-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="25ab3-117">インシデント名は、組織での命名規則に準拠するよう変更できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="25ab3-118">自動インシデントの名前付け機能を展開する前に存在していたインシデントは、その名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="25ab3-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="25ab3-119">インシデントを割り当てる</span><span class="sxs-lookup"><span data-stu-id="25ab3-119">Assign incidents</span></span>
<span data-ttu-id="25ab3-120">インシデントがまだ割り当てられていない場合、[**Assign to me (自分に割り当て)**] を選択してインシデントを自分に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="25ab3-121">これにより、インシデントの所有権だけでなくそのインシデントと関連するすべての警告の所有権が自分に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="25ab3-122">状態と分類を設定する</span><span class="sxs-lookup"><span data-stu-id="25ab3-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="25ab3-123">インシデントの状態</span><span class="sxs-lookup"><span data-stu-id="25ab3-123">Incident status</span></span>
<span data-ttu-id="25ab3-124">インシデントは、調査の進捗に合わせて状態を変更することにより、**Active (アクティブ)** または **Resolved (解決済み)** に分類できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="25ab3-125">こうすることで、チームでのインシデントへの対応方法を整理して管理できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="25ab3-126">たとえば、組織の SOC アナリストは、当日の緊急の **Active (アクティブ)** インシデントを確認して、調査のためにそれらを自分に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="25ab3-127">また、インシデントが修復された場合は、SOC アナリストはインシデントを **Resolved (解決済み)** と設定することができます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="25ab3-128">インシデントを解決すると、インシデントに含まれているすべての警告が、まだ開かれているものも含めて自動的に閉じられます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="25ab3-129">分類と判定</span><span class="sxs-lookup"><span data-stu-id="25ab3-129">Classification and determination</span></span>
<span data-ttu-id="25ab3-130">分類を設定しないことも、インシデントが真または偽であると指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="25ab3-131">こうすることで、チームにはインシデントの傾向が示され、チームの学習につながります。</span><span class="sxs-lookup"><span data-stu-id="25ab3-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="25ab3-132">コメントを追加する</span><span class="sxs-lookup"><span data-stu-id="25ab3-132">Add comments</span></span>
<span data-ttu-id="25ab3-133">警告にはコメントを追加することができ、インシデントに関する過去のイベントを表示して、以前に行われた変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="25ab3-134">警告に変更またはコメントが加えられるたびに、[Comments and history (コメントと履歴)] セクションに記録されます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="25ab3-135">追加されたコメントは直ちにウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="25ab3-136">インシデント タグを追加する</span><span class="sxs-lookup"><span data-stu-id="25ab3-136">Add incident tags</span></span>
<span data-ttu-id="25ab3-137">共通した特徴を持つインシデントのグループにフラグを設定するなどの目的に、カスタム タグをインシデントに追加できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="25ab3-138">こうすることで、特定のタグを含むすべてのインシデントのインシデント キューを後からフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="25ab3-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
