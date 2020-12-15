---
title: Microsoft 365 でトピックのアクセス許可を管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 でトピックのアクセス許可を管理する方法について説明します。
ms.openlocfilehash: b42bcf25f7b7516fb2b8b6e6b052d94fa6c4ea94
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668301"
---
# <a name="manage-topic-permissions-in-microsoft-365"></a><span data-ttu-id="9d9d6-103">Microsoft 365 でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="9d9d6-103">Manage topic permissions in Microsoft 365</span></span>

<span data-ttu-id="9d9d6-104">トピックのアクセス許可の設定は [、Microsoft 365 管理センターで管理できます](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-104">You can manage topic permissions settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="9d9d6-105">これらのタスクを実行するには、全体管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

<span data-ttu-id="9d9d6-106">トピックのアクセス許可の設定では、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-106">With topic permissions settings you can choose:</span></span>

- <span data-ttu-id="9d9d6-107">トピックを作成および編集できるユーザー: 検出中に見つからなかった新しいトピックを作成するか、既存のトピックの詳細を編集します。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-107">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic details.</span></span>
- <span data-ttu-id="9d9d6-108">トピックを管理できるユーザー: トピック管理センターにアクセスし、トピックに関するフィードバックを表示し、ライフサイクルを通じてトピックを移動します。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-108">Which users can manage topics: Access the topic management center and view feedback on topics as well as move topics through the lifecycle.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="9d9d6-109">トピックの管理設定にアクセスするには:</span><span class="sxs-lookup"><span data-stu-id="9d9d6-109">To access topics management settings:</span></span>

1. <span data-ttu-id="9d9d6-110">Microsoft 365 管理センターで、[設定] をクリックし、[組織の設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-110">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="9d9d6-111">[サービス] **タブで** 、[ナレッジ ネットワーク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-111">On the **Services** tab, click **Knowledge network**.</span></span>

    ![ユーザーを知識に接続する](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="9d9d6-113">[トピックの **アクセス許可] タブを選択** します。各設定の詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-113">Select the **Topic permissions** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-permissions.png) 

## <a name="change-who-has-permissions-to-update-topic-details"></a><span data-ttu-id="9d9d6-115">トピックの詳細を更新するアクセス許可を持つユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="9d9d6-115">Change who has permissions to update topic details</span></span>

<span data-ttu-id="9d9d6-116">トピックを作成および編集する権限を持つユーザーを更新するには:</span><span class="sxs-lookup"><span data-stu-id="9d9d6-116">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="9d9d6-117">[トピックの **アクセス許可]** タブの [トピック **を** 作成および編集できるユーザー] で、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-117">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span>
2. <span data-ttu-id="9d9d6-118">[トピック **を作成および編集できるユーザー** ] ページで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-118">On the **Who can create and edit topics** page, you can select:</span></span>
    - <span data-ttu-id="9d9d6-119">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="9d9d6-119">**Everyone in your organization**</span></span>
    - <span data-ttu-id="9d9d6-120">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="9d9d6-120">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="9d9d6-121">**だれも**</span><span class="sxs-lookup"><span data-stu-id="9d9d6-121">**No one**</span></span>

    ![トピックの作成と編集](../media/k-manage-who-can-create-and-edit.png)  

3. <span data-ttu-id="9d9d6-123">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-123">Select **Save**.</span></span>

<span data-ttu-id="9d9d6-124">トピックを管理する権限を持つユーザーを更新するには:</span><span class="sxs-lookup"><span data-stu-id="9d9d6-124">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="9d9d6-125">[トピックの **アクセス許可]** タブの [トピック **を** 管理できるユーザー] で、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-125">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span>
2. <span data-ttu-id="9d9d6-126">[トピック **を管理できるユーザー] ページ** で、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-126">On the **Who can manage topics** page, you can select:</span></span>
    - <span data-ttu-id="9d9d6-127">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="9d9d6-127">**Everyone in your organization**</span></span>
    - <span data-ttu-id="9d9d6-128">**選択したユーザーまたはセキュリティ グループ**</span><span class="sxs-lookup"><span data-stu-id="9d9d6-128">**Selected people or security groups**</span></span>

    ![トピックを管理する](../media/k-manage-who-can-manage-topics.png)  

3. <span data-ttu-id="9d9d6-130">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-130">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d9d6-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d9d6-131">See also</span></span>

[<span data-ttu-id="9d9d6-132">Microsoft 365 でのトピック検出の管理</span><span class="sxs-lookup"><span data-stu-id="9d9d6-132">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="9d9d6-133">Microsoft 365 でトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="9d9d6-133">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="9d9d6-134">Microsoft 365 のトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="9d9d6-134">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
