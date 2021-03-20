---
title: 削除された Microsoft 365 グループを復元する
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 削除された Microsoft 365 グループを復元する方法について説明します。
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910548"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="dbef9-103">削除された Microsoft 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="dbef9-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="dbef9-104">グループを削除した場合、既定では 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="dbef9-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="dbef9-105">この 30 日間の期間は、グループを復元することができますので、"soft-delete" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="dbef9-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="dbef9-106">30 日後、グループとその関連コンテンツは完全に削除され、復元できません。</span><span class="sxs-lookup"><span data-stu-id="dbef9-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="dbef9-107">グループを復元すると、次のコンテンツが復元されます。</span><span class="sxs-lookup"><span data-stu-id="dbef9-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="dbef9-108">Azure Active Directory (AD) Microsoft 365 Groups オブジェクト、プロパティ、およびメンバー。</span><span class="sxs-lookup"><span data-stu-id="dbef9-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="dbef9-109">グループの電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="dbef9-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="dbef9-110">Exchange Online 共有受信トレイと予定表。</span><span class="sxs-lookup"><span data-stu-id="dbef9-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="dbef9-111">SharePoint Online チーム サイトとファイル。</span><span class="sxs-lookup"><span data-stu-id="dbef9-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="dbef9-112">OneNote ノートブック</span><span class="sxs-lookup"><span data-stu-id="dbef9-112">OneNote notebook</span></span>
    
- <span data-ttu-id="dbef9-113">Planner</span><span class="sxs-lookup"><span data-stu-id="dbef9-113">Planner</span></span>
    
- <span data-ttu-id="dbef9-114">Teams</span><span class="sxs-lookup"><span data-stu-id="dbef9-114">Teams</span></span>

- <span data-ttu-id="dbef9-115">Yammerグループおよびグループ コンテンツ (Microsoft 365 グループがグループから作成されたYammer)</span><span class="sxs-lookup"><span data-stu-id="dbef9-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="dbef9-116">この記事では、Microsoft 365 グループのみを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbef9-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="dbef9-117">他のすべてのグループは、一度削除すると復元できません。</span><span class="sxs-lookup"><span data-stu-id="dbef9-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="dbef9-118">グループの復元</span><span class="sxs-lookup"><span data-stu-id="dbef9-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="dbef9-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="dbef9-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="dbef9-120">Microsoft 365 グループの所有者である場合は、次の手順に従って Outlook on the web でグループを自分で復元できます。</span><span class="sxs-lookup"><span data-stu-id="dbef9-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="dbef9-121">[削除された [グループ] ページで、[](https://outlook.office.com/people/group/deleted)グループ] ノードの **[** グループの管理] オプションを選択し、[削除済み]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dbef9-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="dbef9-122">復元するグループ **の** 横にある [復元] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef9-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="dbef9-123">削除されたグループがここに表示されない場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="dbef9-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="dbef9-124">管理センター</span><span class="sxs-lookup"><span data-stu-id="dbef9-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="dbef9-125">グローバル管理者またはグループ管理者の場合は、Microsoft 365 管理センターで削除されたグループを復元できます。</span><span class="sxs-lookup"><span data-stu-id="dbef9-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="dbef9-126">[管理センター](https://admin.microsoft.com)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dbef9-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="dbef9-127">[グループ **] を展開** し、[削除済 **みグループ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dbef9-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="dbef9-128">復元するグループを選択し、[グループの復元] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dbef9-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="dbef9-129">場合によっては、グループとそのすべてのデータが復元に 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbef9-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="dbef9-130">Microsoft 365 グループについて質問がありますか?</span><span class="sxs-lookup"><span data-stu-id="dbef9-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="dbef9-131">Microsoft Tech [Community にアクセスして質問](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) を投稿し、Microsoft 365 グループに関する会話に参加します。</span><span class="sxs-lookup"><span data-stu-id="dbef9-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="dbef9-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="dbef9-132">Related articles</span></span>

[<span data-ttu-id="dbef9-133">PowerShell を使用して Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="dbef9-133">Manage Microsoft 365 Groups with PowerShell</span></span>](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[<span data-ttu-id="dbef9-134">Remove-UnifiedGroup コマンドレットを使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="dbef9-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](/powershell/module/exchange/remove-unifiedgroup)
  
[<span data-ttu-id="dbef9-135">グループに接続されたチーム サイトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="dbef9-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="dbef9-136">Outlook でグループを削除する</span><span class="sxs-lookup"><span data-stu-id="dbef9-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)