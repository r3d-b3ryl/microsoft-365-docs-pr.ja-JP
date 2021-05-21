---
title: Defender でインシデントをMicrosoft 365する
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント、インシデント、分析、応答、アラート、相関アラート、割り当て、更新、状態、管理、分類、microsoft、365、m365
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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594154"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="26b63-104">Defender でインシデントをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="26b63-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="26b63-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="26b63-105">**Applies to:**</span></span>
- <span data-ttu-id="26b63-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26b63-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="26b63-107">インシデント管理は、脅威を確実に含め、対処する上で重要です。</span><span class="sxs-lookup"><span data-stu-id="26b63-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="26b63-108">インシデント &**アラート>** インシデントを管理するには、Microsoft 365 セキュリティ センター (security.microsoft.com) を [security.microsoft.com。](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="26b63-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="26b63-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26b63-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例":::

<span data-ttu-id="26b63-111">インシデントを管理する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26b63-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="26b63-112">インシデント名を編集する</span><span class="sxs-lookup"><span data-stu-id="26b63-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="26b63-113">インシデント タグを追加する</span><span class="sxs-lookup"><span data-stu-id="26b63-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="26b63-114">インシデントを自分に割り当てる</span><span class="sxs-lookup"><span data-stu-id="26b63-114">Assign the incident to yourself</span></span>](#assign-incidents)
- [<span data-ttu-id="26b63-115">それらを解決する</span><span class="sxs-lookup"><span data-stu-id="26b63-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="26b63-116">分類と決定を設定する</span><span class="sxs-lookup"><span data-stu-id="26b63-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="26b63-117">コメントを追加する</span><span class="sxs-lookup"><span data-stu-id="26b63-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="26b63-118">インシデントを管理するには、[インシデントの **管理] ウィンドウ** でインシデントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="26b63-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26b63-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="インシデントの [インシデントの管理] ウィンドウの例":::

<span data-ttu-id="26b63-121">このウィンドウは、次の [インシデントの **管理** ] リンクから表示できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="26b63-122">インシデント キュー内のインシデントのプロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="26b63-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="26b63-123">**インシデントの** 概要ページ。</span><span class="sxs-lookup"><span data-stu-id="26b63-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="26b63-124">あるインシデントから別のインシデントにアラートを移動する場合は、[アラート] タブからアラートを移動して、関連するすべてのアラートを含む大きいインシデントまたは小規模インシデントを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="26b63-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="26b63-125">インシデント名を編集する</span><span class="sxs-lookup"><span data-stu-id="26b63-125">Edit the incident name</span></span>

<span data-ttu-id="26b63-126">Microsoft 365Defender は、影響を受けるエンドポイントの数、影響を受けるユーザー、検出ソース、カテゴリなどのアラート属性に基づいて名前を自動的に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="26b63-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="26b63-127">これにより、インシデントの範囲をすばやく理解できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="26b63-128">たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*</span><span class="sxs-lookup"><span data-stu-id="26b63-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="26b63-129">インシデント名は、[インシデントの管理] ウィンドウの **[インシデント名** ] フィールド **から編集** できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="26b63-130">自動インシデント名前付け機能のロールアウト前に存在していたインシデントは、その名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="26b63-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="26b63-131">インシデント タグを追加する</span><span class="sxs-lookup"><span data-stu-id="26b63-131">Add incident tags</span></span>

<span data-ttu-id="26b63-132">たとえば、共通の特性を持つインシデントのグループにフラグを設定する場合など、インシデントにカスタム タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="26b63-133">後で、特定のタグを含むすべてのインシデントに対してインシデント キューをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="26b63-134">入力を開始すると、選択したタグの一覧から選択できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="26b63-135">インシデントを割り当てる</span><span class="sxs-lookup"><span data-stu-id="26b63-135">Assign incidents</span></span>

<span data-ttu-id="26b63-136">インシデントを割り当てるには、[割り当て **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="26b63-136">To assign an incident, select **Assign to me**.</span></span> <span data-ttu-id="26b63-137">これにより、インシデントの所有権と、インシデントに関連付けられているすべてのアラートがユーザー アカウントに割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="26b63-137">Doing so assigns ownership of the incident and all the alerts associated with it to your user account.</span></span>

<span data-ttu-id="26b63-138">インシデント キューをフィルター処理することで、割り当てられたインシデントの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-138">You can get a list of incidents assigned to you by filtering the incident queue.</span></span> 

1. <span data-ttu-id="26b63-139">インシデント キューから、[フィルター] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="26b63-139">From the incident queue, select **Filters**.</span></span>
2. <span data-ttu-id="26b63-140">[インシデントの **割り当て** ] セクションで、[すべて選択] **をオフに** し、[割 **り当て済み] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="26b63-140">in the **Incident assignment** section, clear **Select all** and select **Assigned to me**.</span></span>
3. <span data-ttu-id="26b63-141">[適用 **] を** 選択し、[フィルター] ウィンドウ **を閉** じます。</span><span class="sxs-lookup"><span data-stu-id="26b63-141">Select **Apply**, and then close the **Filters** pane.</span></span>

<span data-ttu-id="26b63-142">その後、ブラウザーに結果の URL をブックマークとして保存し、割り当てられたインシデントの一覧をすばやく表示できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-142">You can then save the resulting URL in your browser as a bookmark to quickly see the list of incidents assigned to you.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="26b63-143">インシデントの解決</span><span class="sxs-lookup"><span data-stu-id="26b63-143">Resolve an incident</span></span>

<span data-ttu-id="26b63-144">インシデントが修復された場合は、[インシデントの解決] **を** 選択してトグルを右に移動します。</span><span class="sxs-lookup"><span data-stu-id="26b63-144">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="26b63-145">インシデントを解決すると、インシデントに関連するリンクされたアラートとアクティブなアラートもすべて解決されます。</span><span class="sxs-lookup"><span data-stu-id="26b63-145">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="26b63-146">解決されないインシデントは、Active として表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="26b63-146">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="26b63-147">分類と決定を設定する</span><span class="sxs-lookup"><span data-stu-id="26b63-147">Set the classification and determination</span></span>

<span data-ttu-id="26b63-148">インシデント分類は、分類フィールドから構成する、本当のアラートか誤ったアラートか **です** 。</span><span class="sxs-lookup"><span data-stu-id="26b63-148">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="26b63-149">それが本当の警告である場合は、[決定] フィールドで脅威の種類も **指定する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="26b63-149">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="26b63-150">脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-150">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="26b63-151">コメントを追加する</span><span class="sxs-lookup"><span data-stu-id="26b63-151">Add comments</span></span>

<span data-ttu-id="26b63-152">[コメント] フィールドを使用して、インシデントに複数のコメント **を追加** できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-152">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="26b63-153">各コメントは、インシデントの履歴イベントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="26b63-153">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="26b63-154">インシデントのコメントと履歴は、[概要] ページの[コメントと履歴] リンク **から確認** できます。</span><span class="sxs-lookup"><span data-stu-id="26b63-154">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="26b63-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="26b63-155">Next steps</span></span>

<span data-ttu-id="26b63-156">新しいインシデントについては、調査を開始 [します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="26b63-156">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="26b63-157">インプロセス インシデントの場合は、調査を続行 [します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="26b63-157">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="26b63-158">解決されたインシデントの場合は、インシデント後 [のレビューを実行します](first-incident-post.md)。</span><span class="sxs-lookup"><span data-stu-id="26b63-158">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26b63-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="26b63-159">See also</span></span>

- [<span data-ttu-id="26b63-160">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="26b63-160">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="26b63-161">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="26b63-161">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="26b63-162">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="26b63-162">Investigate incidents</span></span>](investigate-incidents.md)
