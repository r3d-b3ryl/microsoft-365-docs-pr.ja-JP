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
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753245"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="3e428-103">削除された Microsoft 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="3e428-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="3e428-104">グループを削除した場合、既定では30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="3e428-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="3e428-105">この30日の期間は、引き続きグループを復元できるため、"ソフト削除" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="3e428-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="3e428-106">30日後、グループとそれに関連するコンテンツは完全に削除され、復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e428-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="3e428-107">グループを復元すると、次のコンテンツが復元されます。</span><span class="sxs-lookup"><span data-stu-id="3e428-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="3e428-108">Azure Active Directory (AD) Microsoft 365 グループオブジェクト、プロパティ、およびメンバー。</span><span class="sxs-lookup"><span data-stu-id="3e428-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="3e428-109">グループの電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="3e428-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="3e428-110">Exchange Online の共有の受信トレイと予定表。</span><span class="sxs-lookup"><span data-stu-id="3e428-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="3e428-111">SharePoint Online チームサイトとファイル。</span><span class="sxs-lookup"><span data-stu-id="3e428-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="3e428-112">OneNote ノートブック</span><span class="sxs-lookup"><span data-stu-id="3e428-112">OneNote notebook</span></span>
    
- <span data-ttu-id="3e428-113">Planner</span><span class="sxs-lookup"><span data-stu-id="3e428-113">Planner</span></span>
    
- <span data-ttu-id="3e428-114">Teams</span><span class="sxs-lookup"><span data-stu-id="3e428-114">Teams</span></span>

- <span data-ttu-id="3e428-115">Yammer グループとグループのコンテンツ (Yammer から Microsoft 365 グループが作成されている場合)</span><span class="sxs-lookup"><span data-stu-id="3e428-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="3e428-116">この記事では、Microsoft 365 グループのみを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e428-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="3e428-117">他のすべてのグループは、削除された後に復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e428-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="3e428-118">グループを復元する</span><span class="sxs-lookup"><span data-stu-id="3e428-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="3e428-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="3e428-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="3e428-120">Microsoft 365 グループの所有者である場合は、次の手順に従って、そのグループを web 上の Outlook で自分で復元することができます。</span><span class="sxs-lookup"><span data-stu-id="3e428-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="3e428-121">[[削除さ](https://outlook.office.com/people/group/deleted)れたグループ] ページで、[**グループ**] ノードの下の [**グループの管理**] オプションを選択し、[**削除済み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e428-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="3e428-122">復元するグループの横にある [ **復元** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e428-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="3e428-123">削除されたグループがここに表示されない場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="3e428-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="3e428-124">管理センター</span><span class="sxs-lookup"><span data-stu-id="3e428-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="3e428-125">グローバル管理者またはグループ管理者の場合は、次のように、削除されたグループを Microsoft 365 管理センターで復元できます。</span><span class="sxs-lookup"><span data-stu-id="3e428-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="3e428-126">[管理センター](https://admin.microsoft.com)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3e428-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="3e428-127">[ **グループ**] を展開し、[ **削除済みグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e428-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="3e428-128">復元するグループを選択し、[ **グループの復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e428-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="3e428-129">場合によっては、グループとそのすべてのデータが復元されるまでに24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3e428-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="3e428-130">Microsoft 365 グループに関する質問</span><span class="sxs-lookup"><span data-stu-id="3e428-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="3e428-131">Microsoft [技術コミュニティ](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) にアクセスして、microsoft 365 グループに関する質問を投稿し、会話に参加してください。</span><span class="sxs-lookup"><span data-stu-id="3e428-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="3e428-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="3e428-132">Related articles</span></span>

[<span data-ttu-id="3e428-133">PowerShell を使用して Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="3e428-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="3e428-134">Remove-UnifiedGroup コマンドレットを使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="3e428-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="3e428-135">グループに接続されたチーム サイトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="3e428-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="3e428-136">Outlook でグループを削除する</span><span class="sxs-lookup"><span data-stu-id="3e428-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
