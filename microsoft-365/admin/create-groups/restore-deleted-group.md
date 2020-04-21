---
title: 削除されたグループを復元する
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 削除された Microsoft 365 グループを復元する方法について説明します。
ms.openlocfilehash: a0e7aef090528b3fa183fe08f9c4d06c86f94a10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630033"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="d5914-103">削除されたグループを復元する</span><span class="sxs-lookup"><span data-stu-id="d5914-103">Restore a deleted Group</span></span>

<span data-ttu-id="d5914-104">グループを削除した場合、既定では30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="d5914-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="d5914-105">この30日の期間は、引き続きグループを復元できるため、"ソフト削除" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d5914-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d5914-106">30日後、グループとそれに関連するコンテンツは完全に削除され、復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5914-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d5914-107">グループを復元すると、次のコンテンツが復元されます。</span><span class="sxs-lookup"><span data-stu-id="d5914-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="d5914-108">Azure Active Directory (AD) Microsoft 365 グループオブジェクト、プロパティ、およびメンバー。</span><span class="sxs-lookup"><span data-stu-id="d5914-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="d5914-109">グループの電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="d5914-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="d5914-110">Exchange Online の共有の受信トレイと予定表。</span><span class="sxs-lookup"><span data-stu-id="d5914-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="d5914-111">SharePoint Online チームサイトとファイル。</span><span class="sxs-lookup"><span data-stu-id="d5914-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="d5914-112">OneNote ノートブック</span><span class="sxs-lookup"><span data-stu-id="d5914-112">OneNote notebook</span></span>
    
- <span data-ttu-id="d5914-113">Planner</span><span class="sxs-lookup"><span data-stu-id="d5914-113">Planner</span></span>
    
- <span data-ttu-id="d5914-114">Teams</span><span class="sxs-lookup"><span data-stu-id="d5914-114">Teams</span></span>

- <span data-ttu-id="d5914-115">Yammer グループとグループのコンテンツ (Yammer から Microsoft 365 グループが作成されている場合)</span><span class="sxs-lookup"><span data-stu-id="d5914-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="d5914-116">Outlook を使用して自分が所有するグループを復元する</span><span class="sxs-lookup"><span data-stu-id="d5914-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="d5914-117">Microsoft 365 グループの所有者である場合は、次の手順に従ってグループを自分の Outlook で復元できます。</span><span class="sxs-lookup"><span data-stu-id="d5914-117">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="d5914-118">[[削除さ](https://outlook.office.com/people/group/deleted)れたグループ] ページで、[**グループ**] ノードの下の [**グループの管理**] オプションを選択し、[**削除済み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5914-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="d5914-119">復元するグループの横にある [**復元**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5914-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="d5914-120">削除されたグループがここに表示されない場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d5914-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d5914-121">Microsoft 365 管理センターでグループを復元する</span><span class="sxs-lookup"><span data-stu-id="d5914-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="d5914-122">グローバル管理者またはグループ管理者の場合は、次のように、削除されたグループを Microsoft 365 管理センターで復元できます。</span><span class="sxs-lookup"><span data-stu-id="d5914-122">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="d5914-123">[管理センター](https://admin.microsoft.com)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d5914-123">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d5914-124">[**グループ**] を展開し、[**削除済みグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5914-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="d5914-125">復元するグループを選択し、[**グループの復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5914-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="d5914-126">Microsoft 365 グループを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="d5914-126">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="d5914-127">場合によっては、30日間のソフト削除期間が経過するのを待たずに、グループを完全に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5914-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="d5914-128">それを行うには、PowerShell を起動し、次のコマンドを実行して、グループのオブジェクト ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="d5914-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="d5914-129">完全に削除するグループまたはグループのオブジェクト ID を書き留めておきます。</span><span class="sxs-lookup"><span data-stu-id="d5914-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d5914-130">グループを削除すると、グループとそのデータが永久に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d5914-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="d5914-131">グループを削除するには、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5914-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="d5914-p103">グループが正常に削除されたことを確認するには、 *Get AzureADMSDeletedGroup*  コマンドレットをもう一度実行して、グループが論理的に削除されたグループの一覧に表示されなくなったことを確認します。グループとそのすべてのデータが完全に削除されるまで 24 時間ほどかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5914-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="d5914-134">Microsoft 365 グループに関する質問</span><span class="sxs-lookup"><span data-stu-id="d5914-134">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="d5914-135">Microsoft[技術コミュニティ](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)にアクセスして、microsoft 365 グループに関する質問を投稿し、会話に参加してください。</span><span class="sxs-lookup"><span data-stu-id="d5914-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="d5914-136">関連記事</span><span class="sxs-lookup"><span data-stu-id="d5914-136">Related articles</span></span>

[<span data-ttu-id="d5914-137">PowerShell を使用して Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="d5914-137">Manage Microsoft 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="d5914-138">Remove-UnifiedGroup コマンドレットを使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="d5914-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="d5914-139">グループに接続されたチーム サイトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="d5914-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="d5914-140">Outlook でグループを削除する</span><span class="sxs-lookup"><span data-stu-id="d5914-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
