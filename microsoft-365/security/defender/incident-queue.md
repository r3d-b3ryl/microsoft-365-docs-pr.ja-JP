---
title: Defender でのインシデントのMicrosoft 365する
description: Defender のインシデント キューからインシデントをフィルター処理するMicrosoft 365する
keywords: インシデント、キュー、概要、デバイス、ID、ユーザー、メールボックス、電子メール、インシデント、分析、応答
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 47d066fa20abe963f7afaa3b88cecc96fa6e87fc
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259591"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="43631-104">Defender でのインシデントのMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="43631-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="43631-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="43631-105">**Applies to:**</span></span>
- <span data-ttu-id="43631-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43631-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="43631-107">Microsoft 365Defender は相関分析を適用し、関連するアラートと、さまざまな製品からの自動調査をインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="43631-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="43631-108">Microsoft 365また、defender は、Microsoft 365 Defender が製品のスイート全体で持っているエンドツーエンドの可視性を考えると、悪意のあるアクティビティとしてのみ識別できるアクティビティに対する一意のアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="43631-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="43631-109">このビューは、セキュリティ アナリストに広範な攻撃ストーリーを提供し、組織全体の複雑な脅威をよりよく理解し、対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43631-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="43631-110">インシデント **キューには、** デバイス、ユーザー、メールボックス間で作成されたインシデントのコレクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43631-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="43631-111">これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="43631-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="43631-112">インシデント キューにアクセスするには、インシデント & > セキュリティ センター (security.microsoft.com) のクイック 起動時にインシデント Microsoft 365アラート[を表示します](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="43631-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="43631-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43631-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例":::

<span data-ttu-id="43631-115">[ **最新のインシデントと** 通知] セクションには、過去 24 時間に受信したアラートとインシデントが作成された数のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43631-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="43631-116">既定では、セキュリティ センター内のインシデント キュー Microsoft 365過去 6 か月間に発生したインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43631-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="43631-117">最新のインシデントはリストの一番上にあるので、最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="43631-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="43631-118">インシデント キューには、インシデントの異なる特性や影響を受けたエンティティを表示できるカスタマイズ可能な列 ([列の選択] を選択) があります。</span><span class="sxs-lookup"><span data-stu-id="43631-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="43631-119">これにより、分析のためのインシデントの事前設定に関する情報に基づいた意思決定を行う際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43631-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="43631-120">一目で見える表示を追加するために、インシデントの自動名前付けにより、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいてインシデント名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="43631-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="43631-121">これにより、インシデントの範囲をすばやく理解できます。</span><span class="sxs-lookup"><span data-stu-id="43631-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="43631-122">たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*</span><span class="sxs-lookup"><span data-stu-id="43631-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="43631-123">自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前は変更されません。</span><span class="sxs-lookup"><span data-stu-id="43631-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="43631-124">インシデント キューでは、複数のフィルター オプションも公開されます。適用すると、環境内のすべての既存のインシデントの広範なスイープを実行したり、特定のシナリオや脅威に集中することができます。</span><span class="sxs-lookup"><span data-stu-id="43631-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="43631-125">インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="43631-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="43631-126">利用可能なフィルター</span><span class="sxs-lookup"><span data-stu-id="43631-126">Available filters</span></span>

<span data-ttu-id="43631-127">既定のインシデント キューから [フィルター] を **選択して** [フィルター] ウィンドウを表示し、そこからフィルター処理されたインシデントのセットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="43631-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="43631-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43631-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="インシデント キューのフィルター ウィンドウの例":::

<span data-ttu-id="43631-130">次の表に、使用可能なフィルター名を示します。</span><span class="sxs-lookup"><span data-stu-id="43631-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="43631-131">フィルター名</span><span class="sxs-lookup"><span data-stu-id="43631-131">Filter name</span></span> | <span data-ttu-id="43631-132">説明</span><span class="sxs-lookup"><span data-stu-id="43631-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="43631-133">割り当て先</span><span class="sxs-lookup"><span data-stu-id="43631-133">Assigned to</span></span> | <span data-ttu-id="43631-134">自分に割り当てられているアラート、または自動化によって処理されたアラートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="43631-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="43631-135">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="43631-135">Categories</span></span> | <span data-ttu-id="43631-136">カテゴリを選択して、見られる特定の戦術、テクニック、または攻撃コンポーネントに焦点を当てる。</span><span class="sxs-lookup"><span data-stu-id="43631-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="43631-137">分類</span><span class="sxs-lookup"><span data-stu-id="43631-137">Classification</span></span> | <span data-ttu-id="43631-138">関連するアラートの一連の分類に基づいてインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="43631-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="43631-139">値には、true アラート、false アラート、または設定されていないが含まれます。</span><span class="sxs-lookup"><span data-stu-id="43631-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="43631-140">データの機密性</span><span class="sxs-lookup"><span data-stu-id="43631-140">Data sensitivity</span></span> | <span data-ttu-id="43631-141">一部の攻撃では、機密データや貴重なデータを排除することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="43631-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="43631-142">機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="43631-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="43631-143">Microsoft Information Protection が有効になっている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="43631-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="43631-144">デバイス グループ</span><span class="sxs-lookup"><span data-stu-id="43631-144">Device group</span></span> | <span data-ttu-id="43631-145">定義済みのデバイス グループでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="43631-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="43631-146">調査の状態</span><span class="sxs-lookup"><span data-stu-id="43631-146">Investigation state</span></span> | <span data-ttu-id="43631-147">自動調査の状態によってインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="43631-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="43631-148">複数のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="43631-148">Multiple categories</span></span> | <span data-ttu-id="43631-149">複数のカテゴリにマップされたインシデントのみを表示し、より多くの損害を引き起こす可能性がある場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="43631-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="43631-150">複数のサービス ソース</span><span class="sxs-lookup"><span data-stu-id="43631-150">Multiple service sources</span></span>  | <span data-ttu-id="43631-151">フィルターを適用して、さまざまなソースからの通知を含むインシデントのみを表示します (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="43631-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="43631-152">OS プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="43631-152">OS platform</span></span> | <span data-ttu-id="43631-153">オペレーティング システムによってインシデント キュー ビューを制限します。</span><span class="sxs-lookup"><span data-stu-id="43631-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="43631-154">サービス ソース</span><span class="sxs-lookup"><span data-stu-id="43631-154">Service sources</span></span> | <span data-ttu-id="43631-155">特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="43631-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="43631-156">重要度</span><span class="sxs-lookup"><span data-stu-id="43631-156">Severity</span></span> | <span data-ttu-id="43631-157">インシデントの重大度は、資産に与える影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="43631-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="43631-158">重大度が高いほど、影響は大きく、通常は最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="43631-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="43631-159">状態</span><span class="sxs-lookup"><span data-stu-id="43631-159">Status</span></span> | <span data-ttu-id="43631-160">状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="43631-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="43631-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="43631-161">Next step</span></span>

<span data-ttu-id="43631-162">優先度が最も高いインシデントを決定した後、それを選択して分析を開始 [します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="43631-162">After you've determined which incident requires the highest priority, select it and begin your [analysis](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="43631-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="43631-163">See also</span></span>
- [<span data-ttu-id="43631-164">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="43631-164">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="43631-165">インシデントを分析する</span><span class="sxs-lookup"><span data-stu-id="43631-165">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="43631-166">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="43631-166">Manage incidents</span></span>](manage-incidents.md)
