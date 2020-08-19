---
title: Microsoft Threat Protection のインシデントに優先順位を付ける
description: Microsoft Threat Protection のインシデント キューからインシデントに優先順位を付ける方法の詳細
keywords: インシデント、キュー、概要、デバイス、ID、ユーザー、メールボックス、メール、インシデント
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
ms.openlocfilehash: a08ff27d6d33317df9bd4bf61c0c2ee4cf0ee14e
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797760"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="ef77c-104">Microsoft Threat Protection のインシデントに優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="ef77c-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="ef77c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ef77c-105">**Applies to:**</span></span>
- <span data-ttu-id="ef77c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ef77c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ef77c-107">Microsoft Threat Protection は、相関分析を適用し、さまざまな製品からのすべての関連する通知と調査を 1 つのインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="ef77c-108">また、Microsoft Threat Protection は、Microsoft Threat Protection が資産全体および製品スイート全体にわたってエンドツーエンドの可視性を備えているため、悪意があると識別できるアクティビティにのみ一意の警告をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ef77c-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="ef77c-109">そうすることで、Microsoft Threat Protection はより広範な攻撃事例を説明し、セキュリティ運用アナリストが組織全体の複雑な脅威を理解して対処できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ef77c-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="ef77c-110">**インシデント キュー**には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="ef77c-111">これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![インシデント キューの画像](../../media/incidents-queue.png) 

<span data-ttu-id="ef77c-113">既定では、Microsoft 365 セキュリティ センターのキューには過去 30 日間に発生したインシデントが表示され、最新のインシデントがリストの一番上に表示されるため、最新のインシデントを最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="ef77c-114">インシデント キューには、カスタマイズ可能な列が表示され、インシデントまたは含まれているエンティティのさまざまな特性を確認できます。これにより、処理するインシデントの優先順位付けに関する情報に基づいて意思決定ができます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="ef77c-115">わかりやすくするために、自動インシデントの名前付けは、影響を受けるエンドポイント数、影響を受けるユーザー、検出ソースまたはカテゴリなどのアラート属性に基づいて、インシデント名を生成します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="ef77c-116">これにより、インシデントの範囲をすばやく理解することができます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="ef77c-117">例: 複数の*ソースによって報告された複数のエンドポイントのマルチステージインシデント*。</span><span class="sxs-lookup"><span data-stu-id="ef77c-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="ef77c-118">自動インシデントの名前の公開前に存在していたインシデントは、名前が変更されません。</span><span class="sxs-lookup"><span data-stu-id="ef77c-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="ef77c-119">また、インシデント キューには複数のフィルター処理オプションも表示されます。このオプションを適用すると、環境内の既存のすべてのインシデントを幅広く一括処理したり、特定のシナリオまたは脅威に焦点を当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="ef77c-120">インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="ef77c-121">利用可能なフィルター</span><span class="sxs-lookup"><span data-stu-id="ef77c-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="ef77c-122">状態</span><span class="sxs-lookup"><span data-stu-id="ef77c-122">Status</span></span>
<span data-ttu-id="ef77c-123">状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="ef77c-124">重要度</span><span class="sxs-lookup"><span data-stu-id="ef77c-124">Severity</span></span>
<span data-ttu-id="ef77c-125">インシデントの重大度は、資産に与える影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="ef77c-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="ef77c-126">重大度が高いほど影響が大きく、通常は最も迅速な対応が必要になります。</span><span class="sxs-lookup"><span data-stu-id="ef77c-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="ef77c-127">割り当て先 (所有者)</span><span class="sxs-lookup"><span data-stu-id="ef77c-127">Assigned to (owner)</span></span>
<span data-ttu-id="ef77c-128">ユーザー割り当てられているものまたは自分に割り当てられているものを選択することで、リストをフィルター処理することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="ef77c-129">複数のアラート</span><span class="sxs-lookup"><span data-stu-id="ef77c-129">Multiple alerts</span></span> 
<span data-ttu-id="ef77c-130">複数のアラートを含むインシデントのみを表示するには、フィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="ef77c-131">これは、攻撃がキル チェーンでより複雑または進行していることを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef77c-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="ef77c-132">複数のサービス ソース</span><span class="sxs-lookup"><span data-stu-id="ef77c-132">Multiple service sources</span></span> 
<span data-ttu-id="ef77c-133">さまざまなソース (Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP、Office 365 ATP) からのアラートを含むインシデントのみを表示するようにフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="ef77c-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="ef77c-134">サービス ソース</span><span class="sxs-lookup"><span data-stu-id="ef77c-134">Service sources</span></span>
<span data-ttu-id="ef77c-135">特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="ef77c-136">複数のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="ef77c-136">Multiple categories</span></span> 
<span data-ttu-id="ef77c-137">キル チェーンの複数のカテゴリにマッピングされたインシデントのみを表示できます。この場合、より多くの損害を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef77c-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="ef77c-138">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ef77c-138">Categories</span></span>
<span data-ttu-id="ef77c-139">キル チェーンの特定の手順に焦点を当てる特定のカテゴリを選択する</span><span class="sxs-lookup"><span data-stu-id="ef77c-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="ef77c-140">データの機密性</span><span class="sxs-lookup"><span data-stu-id="ef77c-140">Data sensitivity</span></span>
<span data-ttu-id="ef77c-141">一部の攻撃では、機密データや貴重なデータを排除することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ef77c-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="ef77c-142">機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="ef77c-143">Microsoft Information Protection が有効になっている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="ef77c-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="ef77c-144">Next steps</span></span>
<span data-ttu-id="ef77c-145">どのインシデントが最も重要かを判断したら、インシデントについてさらに調査を進めます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="ef77c-146">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="ef77c-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="ef77c-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef77c-147">Related topics</span></span>
- [<span data-ttu-id="ef77c-148">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="ef77c-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ef77c-149">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="ef77c-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="ef77c-150">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="ef77c-150">Manage incidents</span></span>](manage-incidents.md)
