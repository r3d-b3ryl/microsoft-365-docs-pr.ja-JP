---
title: Microsoft 365 管理センターでセキュリティ グループを作成、編集、削除する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: セキュリティ グループの作成、編集、削除について説明します。
ms.openlocfilehash: 03e391727f9a61b1fc8e819e92d5a119017c38e0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579340"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7e05b-103">Microsoft 365 管理センターでセキュリティ グループを作成、編集、削除する</span><span class="sxs-lookup"><span data-stu-id="7e05b-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="7e05b-104">[Microsoft 365 **グループ** ] ページで、SharePoint Online と CRM Online で同じアクセス許可を割り当てるのに使用できるユーザー アカウントのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="7e05b-105">たとえば、管理者は、特定のユーザー グループに対して SharePoint サイトへのアクセス権を付与するセキュリティ グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="7e05b-106">セキュリティ グループを作成、編集、または削除できるのは、グローバル管理者とユーザー管理の管理者だけです。詳細については、「[管理者ロールの割り当て](../add-users/assign-admin-roles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e05b-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="7e05b-107">他に、メールの送信やユーザー グループにアクセス許可を割り当てるために使用できる [Exchange Online グループと SharePoint Online グループ](#groups-in-exchange-online-and-sharepoint-online)と、ユーザーに権限を付与し、サイトとサイト コレクションへのアクセスを許可する [Exchange Online グループと SharePoint Online グループ](#groups-in-exchange-online-and-sharepoint-online)があります。</span><span class="sxs-lookup"><span data-stu-id="7e05b-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="7e05b-108">サイト メールボックスを使用しますか?</span><span class="sxs-lookup"><span data-stu-id="7e05b-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="7e05b-109">個別ではなくセキュリティ グループを使用して SharePoint に追加されたすべてのユーザーは、SharePoint からのみサイト メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="7e05b-110">これらのユーザーは、Outlook からサイト メールボックスにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7e05b-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="7e05b-111">詳細については、「サイト メールボックスの [代わりに Microsoft 365 グループを使用する」を参照してください](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)。</span><span class="sxs-lookup"><span data-stu-id="7e05b-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="7e05b-112">管理センターでセキュリティ グループを管理する</span><span class="sxs-lookup"><span data-stu-id="7e05b-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="7e05b-113">セキュリティ グループを追加する</span><span class="sxs-lookup"><span data-stu-id="7e05b-113">Add a security group</span></span>

1. <span data-ttu-id="7e05b-114">Microsoft 365 管理センターで、**[グループ]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">[グループ]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="7e05b-115">[**グループ**] ページで、[**グループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="7e05b-116">[**グループの種類の選択**] ページで、[**セキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="7e05b-117">手順に従って、グループの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="7e05b-118">メンバーをセキュリティ グループに追加する</span><span class="sxs-lookup"><span data-stu-id="7e05b-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="7e05b-119">[**グループ**] ページでセキュリティ グループ名を選択し、[**メンバー**] タブで [**すべてのメンバーの表示と管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="7e05b-120">グループ ウィンドウで、[**メンバーの追加**] を選択し、リストから人を選択するか、[**検索**] ボックスに追加する人の名前を入力して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="7e05b-121">メンバーを削除するには、そのメンバー名の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-121">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7e05b-122">[**グループ**] ページでセキュリティ グループ名を選択し、[**メンバー**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-122">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="7e05b-123">グループ ウィンドウで、[**メンバーの追加**] を選択し、リストから人を選択するか、[**検索**] ボックスに追加する人の名前を入力して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="7e05b-124">メンバーを削除するには、そのメンバー名の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="7e05b-125">[**グループ**] ページでセキュリティ グループ名を選択し、[**メンバー**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="7e05b-126">グループ ウィンドウで、[**メンバーの追加**] を選択し、リストから人を選択するか、[**検索**] ボックスに追加する人の名前を入力して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="7e05b-127">メンバーを削除するには、そのメンバー名の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-127">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="7e05b-128">セキュリティ グループを編集する</span><span class="sxs-lookup"><span data-stu-id="7e05b-128">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7e05b-129">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-129">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="7e05b-130">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-130">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="7e05b-131">[設定] ウィンドウで、[**全般**] タブまたは [**メンバー**] タブを選択し、グループの詳細またはメンバーを編集します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-131">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7e05b-132">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">で、[</a>グループ グループ] **ページ** \> **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="7e05b-133">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-133">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="7e05b-134">[セキュリティ グループ] ウィンドウで、[**名前**] タブまたは [**メンバー**] タブの横にある [**編集**] を選択し、グループの詳細またはメンバーを編集します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-134">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="7e05b-135">変更が完了したら、[**保存**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-135">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7e05b-136">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>グループ グループ] **ページ** \> **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-136">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="7e05b-137">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="7e05b-138">[セキュリティ グループ] ウィンドウで、[**名前**] タブまたは [**メンバー**] タブの横にある [**編集**] を選択し、グループの詳細またはメンバーを編集します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="7e05b-139">変更が完了したら、[**保存**] > [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-139">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="7e05b-140">セキュリティ グループを削除する</span><span class="sxs-lookup"><span data-stu-id="7e05b-140">Delete a security group</span></span>

1. <span data-ttu-id="7e05b-141">管理センターで、[**グループ**]  >  [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-141">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="7e05b-142">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-142">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="7e05b-143">[**グループの削除**] (ゴミ箱アイコン) を選択し、[**削除**] を選択して確認します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-143">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="7e05b-144">グループが削除されたら、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-144">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="7e05b-145">Exchange Online グループと SharePoint Online グループ</span><span class="sxs-lookup"><span data-stu-id="7e05b-145">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="7e05b-146">ユーザー グループを作成して全員にメールを同時に送信できるようにする場合は、Exchange 管理センターで [**管理**] \> [**Exchange**] \> [**宛先**] \> [**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-146">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="7e05b-147">次に、[**新規**]、[![追加](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)] の順に選択し、作成するグループの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-147">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="7e05b-148">**配布グループ**: メッセージをユーザー グループに配布するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-148">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="7e05b-149">また、メールが有効な配布 *グループ、または* 配布リストとも *呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="7e05b-149">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="7e05b-150">詳細については、「[配布グループの管理](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e05b-150">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="7e05b-151">**セキュリティ グループ**: メッセージをユーザー グループに配布する、またはリソースへのアクセス許可を付与するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-151">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="7e05b-152">このグループは、*メールが有効なセキュリティ グループ* とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-152">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="7e05b-153">詳細については、「[メールが有効なセキュリティ グループの管理](/Exchange/recipients/mail-enabled-security-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e05b-153">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="7e05b-154">**動的配布グループ**: メッセージの送信時に、定義されたフィルターと条件に基づいて宛先リストが毎回再確認されるタイプの配布グループ。</span><span class="sxs-lookup"><span data-stu-id="7e05b-154">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="7e05b-155">詳細については、「[動的配布グループの管理](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e05b-155">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="7e05b-156">Exchange 管理センターで配布グループとメールが有効なセキュリティ グループを作成すると、その名前とユーザー リストが [セキュリティ グループ **] ページに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-156">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="7e05b-157">このグループは、どちらの場所でも削除できますが、編集は Exchange 管理センターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-157">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="7e05b-158">動的配布グループは 、[セキュリティ グループ] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-158">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="7e05b-159">SharePoint グループは、サイト コレクションの作成時に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-159">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="7e05b-160">既定のグループは、SharePoint の既定のアクセス許可レベル (SharePoint ロールと呼ばれることもあります) を使用して、ユーザーに権限とアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="7e05b-160">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="7e05b-161">詳細については、「[SharePoint Online の既定の SharePoint グループ](/sharepoint/default-sharepoint-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e05b-161">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="7e05b-162">セキュリティ グループは、SharePoint で作成したセキュリティ グループとどのように異なりますか?</span><span class="sxs-lookup"><span data-stu-id="7e05b-162">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="7e05b-163">セキュリティ グループは、SharePoint、Exchange、MDM、Windows などで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-163">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="7e05b-164">SharePoint で作成したセキュリティ グループは、その SharePoint サイト コレクションでしか認識されません。</span><span class="sxs-lookup"><span data-stu-id="7e05b-164">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="7e05b-165">組織をセキュリティで保護するためにはセキュリティ グループを使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="7e05b-165">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="7e05b-p110">いいえ。これは、組織のセキュリティを管理できる方法の 1 つです。常にユーザーにはアクセス許可およびサイトへのアクセス権限を個別に付与することができます。ただし、セキュリティ グループを使用すれば、大規模なユーザー グループを容易に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7e05b-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="7e05b-170">セキュリティ グループにメールを送信できますか?</span><span class="sxs-lookup"><span data-stu-id="7e05b-170">Can I send email to a security group?</span></span>

<span data-ttu-id="7e05b-171">はい。</span><span class="sxs-lookup"><span data-stu-id="7e05b-171">Yes.</span></span> <span data-ttu-id="7e05b-172">ただし、メールとコラボレーションにグループを使用する場合は、代わりに [Microsoft 365](../create-groups/create-groups.md) グループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e05b-172">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
