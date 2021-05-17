---
title: Microsoft Viva Topics でトピックのアクセス許可を管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: トピックのアクセス許可を管理する方法については、「Microsoft Viva Topics」を参照してください。
ms.openlocfilehash: 6592103526a86671a3ff42c698c1243f63be7fef
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107393"
---
# <a name="manage-topic-permissions-in-microsoft-viva-topics"></a><span data-ttu-id="e1c0f-103">Microsoft Viva Topics でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="e1c0f-103">Manage topic permissions in Microsoft Viva Topics</span></span>

<span data-ttu-id="e1c0f-104">トピックのアクセス許可の設定は、管理センター Microsoft 365[管理できます](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-104">You can manage topic permissions settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="e1c0f-105">これらのタスクを実行するには、グローバル管理者SharePoint管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

<span data-ttu-id="e1c0f-106">トピックのアクセス許可の設定では、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-106">With topic permissions settings you can choose:</span></span>

- <span data-ttu-id="e1c0f-107">トピックを作成および編集できるユーザー: 検出中に見つからなかった新しいトピックを作成するか、既存のトピックの詳細を編集します。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-107">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic details.</span></span>
- <span data-ttu-id="e1c0f-108">トピックを管理できるユーザー: トピック管理センターにアクセスし、トピックに関するフィードバックを表示し、ライフサイクルを通じてトピックを移動します。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-108">Which users can manage topics: Access the topic management center and view feedback on topics as well as move topics through the lifecycle.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="e1c0f-109">トピックの管理設定にアクセスするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-109">To access topics management settings:</span></span>

1. <span data-ttu-id="e1c0f-110">管理センターでMicrosoft 365をクリックし、[組織 **設定]\*\*\*\*をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-110">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="e1c0f-111">[サービス] **タブで** 、[トピック エクスペリエンス] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-111">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Connectを知る](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="e1c0f-113">[トピックの **アクセス許可] タブを選択** します。各設定の詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-113">Select the **Topic permissions** tab. See the following sections for information about each setting.</span></span>

    ![ナレッジ ネットワーク設定](../media/knowledge-network-settings-topic-permissions.png) 

## <a name="change-who-has-permissions-to-update-topic-details"></a><span data-ttu-id="e1c0f-115">トピックの詳細を更新するアクセス許可を持つユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="e1c0f-115">Change who has permissions to update topic details</span></span>

<span data-ttu-id="e1c0f-116">トピックを作成および編集するアクセス許可を持つユーザーを更新するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-116">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="e1c0f-117">[トピックの **アクセス許可] タブ** の [トピックWho編集できる]**の下** にある [編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-117">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span>
2. <span data-ttu-id="e1c0f-118">[トピックを **Who編集できる] ページ** で、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-118">On the **Who can create and edit topics** page, you can select:</span></span>
    - <span data-ttu-id="e1c0f-119">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="e1c0f-119">**Everyone in your organization**</span></span>
    - <span data-ttu-id="e1c0f-120">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="e1c0f-120">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="e1c0f-121">**だれも**</span><span class="sxs-lookup"><span data-stu-id="e1c0f-121">**No one**</span></span>

    ![トピックの作成と編集](../media/k-manage-who-can-create-and-edit.png)  

3. <span data-ttu-id="e1c0f-123">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-123">Select **Save**.</span></span>

<span data-ttu-id="e1c0f-124">トピックを管理するアクセス許可を持つユーザーを更新するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-124">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="e1c0f-125">[トピックの **アクセス許可] タブ** の [トピックWho **管理できる] の下にある [** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-125">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span>
2. <span data-ttu-id="e1c0f-126">[トピックWho **管理できる] ページで**、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-126">On the **Who can manage topics** page, you can select:</span></span>
    - <span data-ttu-id="e1c0f-127">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="e1c0f-127">**Everyone in your organization**</span></span>
    - <span data-ttu-id="e1c0f-128">**選択したユーザーまたはセキュリティ グループ**</span><span class="sxs-lookup"><span data-stu-id="e1c0f-128">**Selected people or security groups**</span></span>

    ![トピックを管理する](../media/k-manage-who-can-manage-topics.png)  

3. <span data-ttu-id="e1c0f-130">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c0f-130">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1c0f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1c0f-131">See also</span></span>

[<span data-ttu-id="e1c0f-132">Microsoft Viva Topics でトピックの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="e1c0f-132">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="e1c0f-133">Microsoft Viva Topics でのトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="e1c0f-133">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="e1c0f-134">Microsoft Viva Topics でトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="e1c0f-134">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)
