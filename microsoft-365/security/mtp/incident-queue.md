---
title: Microsoft 365 Defender でインシデントの優先度を設定する
description: Microsoft 365 Defender でインシデントキューからインシデントの優先順位を設定する方法について説明します。
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4369d51ed740af652be632ba0b8752c708d6c719
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877221"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="d10c6-104">Microsoft 365 Defender でインシデントの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="d10c6-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d10c6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d10c6-105">**Applies to:**</span></span>
- <span data-ttu-id="d10c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d10c6-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d10c6-107">Microsoft 365 Defender は、関連付け分析を適用し、さまざまな製品からのすべての関連アラートと調査を1つのインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="d10c6-108">また、microsoft 365 Defender は、Microsoft 365 Defender が不動産および製品スイート全体で使用するエンドツーエンドの可視性を与えられた悪意のあるアクティビティに対して、固有のアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="d10c6-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="d10c6-109">これにより、Microsoft 365 Defender narrates によって、より広範な攻撃ストーリーが実現されます。これにより、セキュリティ運用アナリストは、組織全体にわたる複雑な脅威を理解し、扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="d10c6-110">**インシデント キュー** には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="d10c6-111">これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![インシデント キューの画像](../../media/incidents-queue.png) 

<span data-ttu-id="d10c6-113">既定では、Microsoft 365 セキュリティセンターのキューには過去30日間に表示されたインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="d10c6-114">最新のインシデントは、リストの先頭に表示されるので、最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="d10c6-115">インシデントキューは、インシデントまたは含まれているエンティティのさまざまな特性を表示できる、カスタマイズ可能な列を公開します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="d10c6-116">これにより、処理するインシデントの優先度設定に関する情報による判断を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="d10c6-117">わかりやすくするために、自動インシデントの名前付けは、影響を受けるエンドポイント数、影響を受けたユーザー、検出ソース、カテゴリなどのアラート属性に基づいてインシデント名を生成します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="d10c6-118">これにより、インシデントの範囲をすばやく理解することができます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="d10c6-119">例: 複数の *ソースによって報告された複数のエンドポイントのマルチステージインシデント* 。</span><span class="sxs-lookup"><span data-stu-id="d10c6-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="d10c6-120">自動インシデントの名前の公開前に存在していたインシデントは、名前が変更されません。</span><span class="sxs-lookup"><span data-stu-id="d10c6-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="d10c6-121">また、インシデントキューは、複数のフィルターオプションを公開すると、使用している環境内の既存のすべてのインシデントをさまざまな方法で実行したり、特定のシナリオや脅威に集中することができます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="d10c6-122">インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="d10c6-123">利用可能なフィルター</span><span class="sxs-lookup"><span data-stu-id="d10c6-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="d10c6-124">割り当て先</span><span class="sxs-lookup"><span data-stu-id="d10c6-124">Assigned to</span></span>
<span data-ttu-id="d10c6-125">自分に割り当てられた通知または自動化によって処理された通知を表示するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="d10c6-126">Categories</span><span class="sxs-lookup"><span data-stu-id="d10c6-126">Categories</span></span>
<span data-ttu-id="d10c6-127">表示される特定の戦術、手法、または攻撃コンポーネントに重点を置くカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="d10c6-128">分類</span><span class="sxs-lookup"><span data-stu-id="d10c6-128">Classification</span></span>
<span data-ttu-id="d10c6-129">関連するアラートの分類のセットに基づいてインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="d10c6-130">値には、true alerts、false alerts、未設定のいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="d10c6-131">データの機密性</span><span class="sxs-lookup"><span data-stu-id="d10c6-131">Data sensitivity</span></span>
<span data-ttu-id="d10c6-132">一部の攻撃では、機密データや貴重なデータを排除することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d10c6-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="d10c6-133">機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="d10c6-134">Microsoft Information Protection が有効になっている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="d10c6-135">デバイスグループ</span><span class="sxs-lookup"><span data-stu-id="d10c6-135">Device group</span></span>
<span data-ttu-id="d10c6-136">定義済みのデバイスグループでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="d10c6-137">調査の状態</span><span class="sxs-lookup"><span data-stu-id="d10c6-137">Investigation state</span></span>
<span data-ttu-id="d10c6-138">自動調査の状態によってインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="d10c6-139">複数のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="d10c6-139">Multiple categories</span></span> 
<span data-ttu-id="d10c6-140">複数の分類項目にマップされているインシデントのみを表示するように選択すると、それにより損害が発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="d10c6-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="d10c6-141">複数のサービス ソース</span><span class="sxs-lookup"><span data-stu-id="d10c6-141">Multiple service sources</span></span> 
<span data-ttu-id="d10c6-142">フィルターを適用すると、さまざまなソースからのアラートを含むインシデントのみが表示されます (エンドポイントの Microsoft Defender、Microsoft Cloud App Security、Microsoft defender for Identity、microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="d10c6-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="d10c6-143">OS プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d10c6-143">OS platform</span></span>
<span data-ttu-id="d10c6-144">インシデントキュービューをオペレーティングシステムごとに制限します。</span><span class="sxs-lookup"><span data-stu-id="d10c6-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="d10c6-145">サービス ソース</span><span class="sxs-lookup"><span data-stu-id="d10c6-145">Service sources</span></span>
<span data-ttu-id="d10c6-146">特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="d10c6-147">重要度</span><span class="sxs-lookup"><span data-stu-id="d10c6-147">Severity</span></span>
<span data-ttu-id="d10c6-148">インシデントの重要度は、資産に対する影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="d10c6-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="d10c6-149">重要度が高くなるほど、影響が大きくなり、通常は最も近い注意が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d10c6-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="d10c6-150">状態</span><span class="sxs-lookup"><span data-stu-id="d10c6-150">Status</span></span>
<span data-ttu-id="d10c6-151">状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d10c6-152">現在、分類、デバイスグループ、調査状態、OS プラットフォームの各フィルターは、パブリックプレビューでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-152">The Classification, Device group, Investigation state, and OS platform filters are currently only available in public preview.</span></span>


## <a name="next-steps"></a><span data-ttu-id="d10c6-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="d10c6-153">Next steps</span></span>
<span data-ttu-id="d10c6-154">どのインシデントが最も重要かを判断したら、インシデントについてさらに調査を進めます。</span><span class="sxs-lookup"><span data-stu-id="d10c6-154">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="d10c6-155">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="d10c6-155">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="d10c6-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="d10c6-156">See also</span></span>
- [<span data-ttu-id="d10c6-157">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="d10c6-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d10c6-158">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="d10c6-158">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d10c6-159">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="d10c6-159">Manage incidents</span></span>](manage-incidents.md)
