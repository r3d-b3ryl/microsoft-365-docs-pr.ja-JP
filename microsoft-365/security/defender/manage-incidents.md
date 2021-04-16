---
title: Microsoft 365 Defender でのインシデントの管理
description: 状態の割り当てと更新を行う方法について説明します。
keywords: インシデント、インシデント、警告、関連付けられた警告、割り当て、更新、状態、管理、分類、microsoft、365、m365
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
ms.openlocfilehash: da5a2190a53dfe7f8dd0cc3cf7b410af92ca4ec5
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861733"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="8cf21-104">Microsoft 365 Defender でのインシデントの管理</span><span class="sxs-lookup"><span data-stu-id="8cf21-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8cf21-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8cf21-105">**Applies to:**</span></span>
- <span data-ttu-id="8cf21-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cf21-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8cf21-107">インシデント管理は、脅威を確実に含め、対処する上で重要です。</span><span class="sxs-lookup"><span data-stu-id="8cf21-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="8cf21-108">Microsoft 365 セキュリティ センター (& >) のクイック 起動時に、インシデント とアラートのインシデントを[管理 security.microsoft.com。](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="8cf21-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="8cf21-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8cf21-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例":::

<span data-ttu-id="8cf21-111">インシデントを管理する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8cf21-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="8cf21-112">インシデント名を変更する</span><span class="sxs-lookup"><span data-stu-id="8cf21-112">Change the incident name</span></span>
- <span data-ttu-id="8cf21-113">インシデント タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf21-113">Add incident tags.</span></span>
- <span data-ttu-id="8cf21-114">インシデントをユーザー アカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="8cf21-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="8cf21-115">それらを解決する</span><span class="sxs-lookup"><span data-stu-id="8cf21-115">Resolve them</span></span> 
- <span data-ttu-id="8cf21-116">分類と決定を設定する</span><span class="sxs-lookup"><span data-stu-id="8cf21-116">Set its classification and determination</span></span>
- <span data-ttu-id="8cf21-117">コメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf21-117">Add comments.</span></span>

<span data-ttu-id="8cf21-118">インシデントを管理するには、[インシデントの **管理] ウィンドウ** でインシデントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="8cf21-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8cf21-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="インシデントの [インシデントの管理] ウィンドウの例":::

<span data-ttu-id="8cf21-121">このウィンドウは、次の [インシデントの **管理** ] リンクから表示できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="8cf21-122">インシデント キュー内のインシデントのプロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="8cf21-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="8cf21-123">**インシデントの** 概要ページ。</span><span class="sxs-lookup"><span data-stu-id="8cf21-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="8cf21-124">調査中に、あるインシデントから別のインシデントにアラートを移動する場合は、[アラート] タブからアラートを移動することもできます。これにより、関連するすべてのアラートを含む大小のインシデントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-124">In cases where, while investigating you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="8cf21-125">インシデント名を編集する</span><span class="sxs-lookup"><span data-stu-id="8cf21-125">Edit the incident name</span></span>

<span data-ttu-id="8cf21-126">Microsoft 365 Defender は、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて名前を自動的に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="8cf21-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="8cf21-127">これにより、インシデントの範囲をすばやく理解できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="8cf21-128">たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*</span><span class="sxs-lookup"><span data-stu-id="8cf21-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="8cf21-129">インシデント名は、[インシデントの管理] ウィンドウの **[インシデント名** ] フィールド **から編集** できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf21-130">自動インシデント名前付け機能のロールアウト前に存在していたインシデントは、その名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="8cf21-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="8cf21-131">インシデント タグを追加する</span><span class="sxs-lookup"><span data-stu-id="8cf21-131">Add incident tags</span></span>

<span data-ttu-id="8cf21-132">たとえば、共通の特性を持つインシデントのグループにフラグを設定する場合など、インシデントにカスタム タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="8cf21-133">後で、特定のタグを含むすべてのインシデントに対してインシデント キューをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="8cf21-134">入力を開始すると、選択したタグの一覧から選択できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="8cf21-135">インシデントを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8cf21-135">Assign incidents</span></span>

<span data-ttu-id="8cf21-136">インシデントがまだ割り当てられていない場合は、[割り当て] **を選択して** ユーザー アカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="8cf21-137">これにより、インシデントの所有権と、インシデントに関連付けられているすべてのアラートが割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="8cf21-138">インシデントの解決</span><span class="sxs-lookup"><span data-stu-id="8cf21-138">Resolve incident</span></span>

<span data-ttu-id="8cf21-139">インシデントが修復された場合は、[インシデントの解決] **を** 選択してトグルを右に移動します。</span><span class="sxs-lookup"><span data-stu-id="8cf21-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="8cf21-140">インシデントを解決すると、インシデントに関連するリンクされたアラートとアクティブなアラートもすべて解決されます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="8cf21-141">解決されないインシデントは、Active として表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="8cf21-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="8cf21-142">分類と決定を設定する</span><span class="sxs-lookup"><span data-stu-id="8cf21-142">Set the classification and determination</span></span>

<span data-ttu-id="8cf21-143">インシデント分類は、分類フィールドから構成する、本当のアラートか誤ったアラートか **です** 。</span><span class="sxs-lookup"><span data-stu-id="8cf21-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="8cf21-144">それが本当の警告である場合は、[決定] フィールドで脅威の種類も **指定する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="8cf21-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="8cf21-145">脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="8cf21-146">コメントを追加する</span><span class="sxs-lookup"><span data-stu-id="8cf21-146">Add comments</span></span>

<span data-ttu-id="8cf21-147">[コメント] フィールドを使用して、インシデントに複数のコメント **を追加** できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="8cf21-148">各コメントは、インシデントの履歴イベントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="8cf21-149">インシデントのコメントと履歴は、[概要] ページの[コメントと履歴] リンク **から確認** できます。</span><span class="sxs-lookup"><span data-stu-id="8cf21-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8cf21-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cf21-150">Related topics</span></span>

- [<span data-ttu-id="8cf21-151">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="8cf21-151">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8cf21-152">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="8cf21-152">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="8cf21-153">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="8cf21-153">Investigate incidents</span></span>](investigate-incidents.md)
