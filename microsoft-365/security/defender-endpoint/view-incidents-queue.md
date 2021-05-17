---
title: インシデント キューを表示および整理する
ms.reviewer: ''
description: インシデントの一覧を参照し、フィルターを適用してリストを制限し、より集中したビューを取得する方法について学習します。
keywords: ビュー、整理、インシデント、集計、調査、キュー、ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499932"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="7cd00-104">Microsoft Defender for Endpoint Incidents キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="7cd00-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7cd00-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7cd00-105">**Applies to:**</span></span>
- [<span data-ttu-id="7cd00-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7cd00-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7cd00-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cd00-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7cd00-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7cd00-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7cd00-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7cd00-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="7cd00-110">インシデント **キューには、** ネットワーク内のデバイスからフラグが設定されたインシデントのコレクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="7cd00-111">これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="7cd00-112">既定では、キューには過去 30 日間に発生したインシデントが表示され、最新のインシデントがリストの上部に表示され、最新のインシデントを最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="7cd00-113">インシデント キュー ビューをカスタマイズするために選択できるオプションは複数あります。</span><span class="sxs-lookup"><span data-stu-id="7cd00-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="7cd00-114">上部のナビゲーションでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-114">On the top navigation you can:</span></span>
- <span data-ttu-id="7cd00-115">列をカスタマイズして列を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="7cd00-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="7cd00-116">ページごとに表示するアイテムの数を変更する</span><span class="sxs-lookup"><span data-stu-id="7cd00-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="7cd00-117">ページごとに表示するアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="7cd00-117">Select the items to show per page</span></span>
- <span data-ttu-id="7cd00-118">割り当てるインシデントをバッチ選択する</span><span class="sxs-lookup"><span data-stu-id="7cd00-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="7cd00-119">ページ間の移動</span><span class="sxs-lookup"><span data-stu-id="7cd00-119">Navigate between pages</span></span>
- <span data-ttu-id="7cd00-120">フィルターの適用</span><span class="sxs-lookup"><span data-stu-id="7cd00-120">Apply filters</span></span>

![インシデント キューの画像](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="7cd00-122">インシデント キューの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="7cd00-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="7cd00-123">次のフィルターを適用して、インシデントの一覧を制限し、より集中したビューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="7cd00-124">重要度</span><span class="sxs-lookup"><span data-stu-id="7cd00-124">Severity</span></span>

<span data-ttu-id="7cd00-125">インシデントの重大度</span><span class="sxs-lookup"><span data-stu-id="7cd00-125">Incident severity</span></span> | <span data-ttu-id="7cd00-126">説明</span><span class="sxs-lookup"><span data-stu-id="7cd00-126">Description</span></span>
:---|:---
<span data-ttu-id="7cd00-127">高い</span><span class="sxs-lookup"><span data-stu-id="7cd00-127">High</span></span> </br><span data-ttu-id="7cd00-128">(赤)</span><span class="sxs-lookup"><span data-stu-id="7cd00-128">(Red)</span></span> | <span data-ttu-id="7cd00-129">多くの場合、高度な永続的な脅威 (APT) に関連付けられている脅威。</span><span class="sxs-lookup"><span data-stu-id="7cd00-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="7cd00-130">これらのインシデントは、デバイスに与える損害の重大度が高いリスクを示しています。</span><span class="sxs-lookup"><span data-stu-id="7cd00-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="7cd00-131">中</span><span class="sxs-lookup"><span data-stu-id="7cd00-131">Medium</span></span> </br><span data-ttu-id="7cd00-132">(オレンジ)</span><span class="sxs-lookup"><span data-stu-id="7cd00-132">(Orange)</span></span> | <span data-ttu-id="7cd00-133">異常なレジストリ変更、疑わしいファイルの実行、攻撃段階の一般的な動作など、組織でまれに観察される脅威。</span><span class="sxs-lookup"><span data-stu-id="7cd00-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="7cd00-134">低い</span><span class="sxs-lookup"><span data-stu-id="7cd00-134">Low</span></span> </br><span data-ttu-id="7cd00-135">(黄色)</span><span class="sxs-lookup"><span data-stu-id="7cd00-135">(Yellow)</span></span> | <span data-ttu-id="7cd00-136">組織を標的とする高度な脅威を必ずしも示すわけではない、一般的なマルウェアやハッキング ツールに関連する脅威。</span><span class="sxs-lookup"><span data-stu-id="7cd00-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="7cd00-137">情報</span><span class="sxs-lookup"><span data-stu-id="7cd00-137">Informational</span></span> </br><span data-ttu-id="7cd00-138">(灰色)</span><span class="sxs-lookup"><span data-stu-id="7cd00-138">(Grey)</span></span> | <span data-ttu-id="7cd00-139">情報インシデントはネットワークに悪影響を及ぼすとは見なされませんが、追跡しておいた方が良い場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cd00-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="7cd00-140">割り当て先</span><span class="sxs-lookup"><span data-stu-id="7cd00-140">Assigned to</span></span>
<span data-ttu-id="7cd00-141">ユーザー割り当てられているものまたは自分に割り当てられているものを選択することで、リストをフィルター処理することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="7cd00-142">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="7cd00-142">Category</span></span>
<span data-ttu-id="7cd00-143">インシデントは、サイバーセキュリティキル チェーンが含むステージの説明に基づいて分類されます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="7cd00-144">このビューは、脅威アナリストがコンテキストに基づいて展開する優先度、緊急性、対応する対応戦略を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="7cd00-145">状態</span><span class="sxs-lookup"><span data-stu-id="7cd00-145">Status</span></span>
<span data-ttu-id="7cd00-146">状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="7cd00-147">データの機密性</span><span class="sxs-lookup"><span data-stu-id="7cd00-147">Data sensitivity</span></span>
<span data-ttu-id="7cd00-148">このフィルターを使用して、感度ラベルを含むインシデントを表示します。</span><span class="sxs-lookup"><span data-stu-id="7cd00-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="7cd00-149">インシデントの名前付け</span><span class="sxs-lookup"><span data-stu-id="7cd00-149">Incident naming</span></span>

<span data-ttu-id="7cd00-150">インシデントの範囲を一目で把握するために、インシデント名は、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="7cd00-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="7cd00-151">たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*</span><span class="sxs-lookup"><span data-stu-id="7cd00-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="7cd00-152">自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="7cd00-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="7cd00-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cd00-153">See also</span></span>
- [<span data-ttu-id="7cd00-154">インシデント キュー</span><span class="sxs-lookup"><span data-stu-id="7cd00-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="7cd00-155">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="7cd00-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="7cd00-156">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="7cd00-156">Investigate incidents</span></span>](investigate-incidents.md)

