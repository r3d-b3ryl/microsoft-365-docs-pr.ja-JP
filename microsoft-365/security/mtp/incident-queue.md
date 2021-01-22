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
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929296"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5732d-104">Microsoft 365 Defender でのインシデントの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="5732d-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5732d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5732d-105">**Applies to:**</span></span>
- <span data-ttu-id="5732d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5732d-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="5732d-107">Microsoft 365 Defender は相関関係分析を適用し、さまざまな製品からのすべての関連するアラートと調査を 1 つのインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="5732d-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="5732d-108">また、Microsoft 365 Defender は、Microsoft 365 Defender が製品の資産全体とスイート全体にわたって持っているエンドツーエンドの可視性を考えると、悪意のあるアクティビティとしてのみ識別できる固有のアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="5732d-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="5732d-109">このビューは、セキュリティ運用アナリストに広範な攻撃のストーリーを提供し、組織全体の複雑な脅威をよりよく理解し、対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5732d-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="5732d-110">**インシデント キュー** には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5732d-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="5732d-111">これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5732d-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![インシデント キューの画像](../../media/incidents-queue.png) 

<span data-ttu-id="5732d-113">既定では、Microsoft 365 セキュリティ センターのキューには、過去 30 日間に発生したインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5732d-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="5732d-114">最新のインシデントがリストの一番上にあるので、最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="5732d-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="5732d-115">インシデント キューはカスタマイズ可能な列を公開し、インシデントや含まれるエンティティの異なる特性を可視化できます。</span><span class="sxs-lookup"><span data-stu-id="5732d-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="5732d-116">これにより、処理するインシデントの事前設定に関する情報に基づいた決定を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5732d-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="5732d-117">インシデントの自動名前付けにより、一目で見える表示を追加できます。インシデントの名前は、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="5732d-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="5732d-118">これにより、インシデントの範囲をすばやく理解できます。</span><span class="sxs-lookup"><span data-stu-id="5732d-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="5732d-119">たとえば、複数 *のソースによって報告される複数のエンドポイントでの多段階インシデント。*</span><span class="sxs-lookup"><span data-stu-id="5732d-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="5732d-120">インシデントの自動名前付けのロールアウトの前に存在していたインシデントの名前は変更されません。</span><span class="sxs-lookup"><span data-stu-id="5732d-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="5732d-121">インシデント キューには、複数のフィルタリング オプションも公開されています。このオプションを適用すると、環境内のすべての既存のインシデントを広範囲に処理したり、特定のシナリオや脅威に集中することができます。</span><span class="sxs-lookup"><span data-stu-id="5732d-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="5732d-122">インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="5732d-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="5732d-123">利用可能なフィルター</span><span class="sxs-lookup"><span data-stu-id="5732d-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="5732d-124">割り当て先</span><span class="sxs-lookup"><span data-stu-id="5732d-124">Assigned to</span></span>
<span data-ttu-id="5732d-125">自分に割り当てられているアラートや、自動化によって処理されたアラートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5732d-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="5732d-126">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="5732d-126">Categories</span></span>
<span data-ttu-id="5732d-127">カテゴリを選択して、見られる特定の方法、手法、攻撃コンポーネントに焦点を当てる。</span><span class="sxs-lookup"><span data-stu-id="5732d-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="5732d-128">分類</span><span class="sxs-lookup"><span data-stu-id="5732d-128">Classification</span></span>
<span data-ttu-id="5732d-129">関連するアラートの一連の分類に基づいてインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5732d-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="5732d-130">値には、真のアラート、誤ったアラート、または設定されていないアラートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5732d-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="5732d-131">データの機密性</span><span class="sxs-lookup"><span data-stu-id="5732d-131">Data sensitivity</span></span>
<span data-ttu-id="5732d-132">一部の攻撃では、機密データや貴重なデータを排除することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="5732d-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="5732d-133">機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5732d-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="5732d-134">Microsoft Information Protection が有効になっている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5732d-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="5732d-135">デバイス グループ</span><span class="sxs-lookup"><span data-stu-id="5732d-135">Device group</span></span>
<span data-ttu-id="5732d-136">定義済みのデバイス グループでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5732d-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="5732d-137">調査の状態</span><span class="sxs-lookup"><span data-stu-id="5732d-137">Investigation state</span></span>
<span data-ttu-id="5732d-138">自動調査の状態でインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5732d-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="5732d-139">複数のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="5732d-139">Multiple categories</span></span> 
<span data-ttu-id="5732d-140">複数のカテゴリにマップされたインシデントのみを表示し、より多くの損害を引き起こす可能性がある場合を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5732d-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="5732d-141">複数のサービス ソース</span><span class="sxs-lookup"><span data-stu-id="5732d-141">Multiple service sources</span></span> 
<span data-ttu-id="5732d-142">さまざまなソース (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Id 用 Microsoft Defender、Microsoft Defender for Office 365) からのアラートを含むインシデントのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="5732d-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="5732d-143">OS プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="5732d-143">OS platform</span></span>
<span data-ttu-id="5732d-144">オペレーティング システムによってインシデント キュービューを制限します。</span><span class="sxs-lookup"><span data-stu-id="5732d-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="5732d-145">サービス ソース</span><span class="sxs-lookup"><span data-stu-id="5732d-145">Service sources</span></span>
<span data-ttu-id="5732d-146">特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5732d-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="5732d-147">重要度</span><span class="sxs-lookup"><span data-stu-id="5732d-147">Severity</span></span>
<span data-ttu-id="5732d-148">インシデントの重大度は、資産に与える影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="5732d-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="5732d-149">重大度が高いほど、影響は大きく、通常は最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="5732d-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="5732d-150">状態</span><span class="sxs-lookup"><span data-stu-id="5732d-150">Status</span></span>
<span data-ttu-id="5732d-151">状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5732d-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="5732d-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="5732d-152">Next steps</span></span>
<span data-ttu-id="5732d-153">どのインシデントが最も重要かを判断したら、インシデントについてさらに調査を進めます。</span><span class="sxs-lookup"><span data-stu-id="5732d-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="5732d-154">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="5732d-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="5732d-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="5732d-155">See also</span></span>
- [<span data-ttu-id="5732d-156">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="5732d-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5732d-157">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="5732d-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5732d-158">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="5732d-158">Manage incidents</span></span>](manage-incidents.md)
