---
title: Microsoft 365 Defender でのインシデントの優先順位付け
description: Microsoft 365 Defender のインシデント キューからインシデントをフィルター処理する方法について説明します。
keywords: インシデント、キュー、概要、デバイス、ID、ユーザー、メールボックス、メール、インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062020"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e51db-104">Microsoft 365 Defender でのインシデントの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="e51db-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e51db-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e51db-105">**Applies to:**</span></span>
- <span data-ttu-id="e51db-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e51db-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e51db-107">Microsoft 365 Defender は相関分析を適用し、異なる製品からのすべての関連するアラートと調査を 1 つのインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="e51db-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="e51db-108">また、Microsoft 365 Defender は、Microsoft 365 Defender が製品の全資産とスイート全体で持っているエンドツーエンドの可視性を考えると、悪意のあるものとしてのみ識別できるアクティビティに関する一意のアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="e51db-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="e51db-109">このビューは、セキュリティ運用アナリストに広範な攻撃ストーリーを提供し、組織全体の複雑な脅威をよりよく理解し、対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e51db-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="e51db-110">**インシデント キュー** には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e51db-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="e51db-111">これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![インシデント キューの画像](../../media/incidents-queue.png) 

<span data-ttu-id="e51db-113">既定では、Microsoft 365 セキュリティ センターのキューには、過去 30 日間に発生したインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e51db-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="e51db-114">最新のインシデントはリストの一番上にあるので、最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="e51db-115">インシデント キューはカスタマイズ可能な列を公開し、インシデントまたは含まれているエンティティの異なる特性を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="e51db-116">これにより、処理するインシデントの事前設定に関する情報に基づいた意思決定を行う際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e51db-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="e51db-117">一目で見える表示を追加するために、インシデントの自動名前付けにより、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいてインシデント名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e51db-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="e51db-118">これにより、インシデントの範囲をすばやく理解できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="e51db-119">たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*</span><span class="sxs-lookup"><span data-stu-id="e51db-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="e51db-120">自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前は変更されません。</span><span class="sxs-lookup"><span data-stu-id="e51db-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="e51db-121">インシデント キューでは、複数のフィルター オプションも公開されます。適用すると、環境内のすべての既存のインシデントの広範なスイープを実行したり、特定のシナリオや脅威に集中することができます。</span><span class="sxs-lookup"><span data-stu-id="e51db-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="e51db-122">インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="e51db-123">利用可能なフィルター</span><span class="sxs-lookup"><span data-stu-id="e51db-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="e51db-124">割り当て先</span><span class="sxs-lookup"><span data-stu-id="e51db-124">Assigned to</span></span>
<span data-ttu-id="e51db-125">自分に割り当てられているアラート、または自動化によって処理されたアラートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="e51db-126">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e51db-126">Categories</span></span>
<span data-ttu-id="e51db-127">カテゴリを選択して、見られる特定の戦術、テクニック、または攻撃コンポーネントに焦点を当てる。</span><span class="sxs-lookup"><span data-stu-id="e51db-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="e51db-128">分類</span><span class="sxs-lookup"><span data-stu-id="e51db-128">Classification</span></span>
<span data-ttu-id="e51db-129">関連するアラートの一連の分類に基づいてインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e51db-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="e51db-130">値には、true アラート、false アラート、または設定されていないが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e51db-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="e51db-131">データの機密性</span><span class="sxs-lookup"><span data-stu-id="e51db-131">Data sensitivity</span></span>
<span data-ttu-id="e51db-132">一部の攻撃では、機密データや貴重なデータを排除することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="e51db-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="e51db-133">機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e51db-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="e51db-134">Microsoft Information Protection が有効になっている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e51db-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="e51db-135">デバイス グループ</span><span class="sxs-lookup"><span data-stu-id="e51db-135">Device group</span></span>
<span data-ttu-id="e51db-136">定義済みのデバイス グループでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e51db-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="e51db-137">調査の状態</span><span class="sxs-lookup"><span data-stu-id="e51db-137">Investigation state</span></span>
<span data-ttu-id="e51db-138">自動調査の状態によってインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e51db-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="e51db-139">複数のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="e51db-139">Multiple categories</span></span> 
<span data-ttu-id="e51db-140">複数のカテゴリにマップされたインシデントのみを表示し、より多くの損害を引き起こす可能性がある場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="e51db-141">複数のサービス ソース</span><span class="sxs-lookup"><span data-stu-id="e51db-141">Multiple service sources</span></span> 
<span data-ttu-id="e51db-142">フィルターを適用して、さまざまなソースからの通知を含むインシデントのみを表示します (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="e51db-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="e51db-143">OS プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="e51db-143">OS platform</span></span>
<span data-ttu-id="e51db-144">オペレーティング システムによってインシデント キュー ビューを制限します。</span><span class="sxs-lookup"><span data-stu-id="e51db-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="e51db-145">サービス ソース</span><span class="sxs-lookup"><span data-stu-id="e51db-145">Service sources</span></span>
<span data-ttu-id="e51db-146">特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e51db-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="e51db-147">重要度</span><span class="sxs-lookup"><span data-stu-id="e51db-147">Severity</span></span>
<span data-ttu-id="e51db-148">インシデントの重大度は、資産に与える影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="e51db-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="e51db-149">重大度が高いほど、影響は大きく、通常は最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="e51db-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="e51db-150">状態</span><span class="sxs-lookup"><span data-stu-id="e51db-150">Status</span></span>
<span data-ttu-id="e51db-151">状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e51db-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="e51db-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="e51db-152">Next steps</span></span>
<span data-ttu-id="e51db-153">どのインシデントが最も重要かを判断したら、インシデントについてさらに調査を進めます。</span><span class="sxs-lookup"><span data-stu-id="e51db-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="e51db-154">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="e51db-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="e51db-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="e51db-155">See also</span></span>
- [<span data-ttu-id="e51db-156">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="e51db-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e51db-157">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="e51db-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="e51db-158">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="e51db-158">Manage incidents</span></span>](manage-incidents.md)
