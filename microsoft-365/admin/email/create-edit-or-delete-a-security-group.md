---
title: Microsoft 365 管理センターでセキュリティ グループを作成、編集、削除する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: セキュリティ グループの作成、編集、削除について説明します。
ms.openlocfilehash: 26b431a65035f2546bb44af2ecf31bfd327e53b6
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255237"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ce953-103">Microsoft 365 管理センターでセキュリティ グループを作成、編集、削除する</span><span class="sxs-lookup"><span data-stu-id="ce953-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ce953-104">Office 365 の [**グループ**] ページでは、 SharePoint Online および CRM Online で同じ権限を割り当てるために使用できるユーザー アカウントのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce953-104">On the Office 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="ce953-105">たとえば、管理者は、特定のユーザー グループに対して SharePoint サイトへのアクセス権を付与するセキュリティ グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce953-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="ce953-106">セキュリティ グループを作成、編集、または削除できるのは、グローバル管理者とユーザー管理の管理者だけです。詳細については、「[管理者ロールの割り当て](../add-users/assign-admin-roles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce953-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="ce953-107">他に、メールの送信やユーザー グループにアクセス許可を割り当てるために使用できる [Exchange Online グループと SharePoint Online グループ](#groups-in-exchange-online-and-sharepoint-online)と、ユーザーに権限を付与し、サイトとサイト コレクションへのアクセスを許可する [Exchange Online グループと SharePoint Online グループ](#groups-in-exchange-online-and-sharepoint-online)があります。</span><span class="sxs-lookup"><span data-stu-id="ce953-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="ce953-108">サイト メールボックスを使用しますか?</span><span class="sxs-lookup"><span data-stu-id="ce953-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="ce953-109">個別ではなくセキュリティ グループを使用して SharePoint に追加されたすべてのユーザーは、SharePoint からのみサイト メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce953-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="ce953-110">これらのユーザーは、Outlook からサイト メールボックスにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ce953-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="ce953-111">詳細については、「[サイト メールボックスの代わりに Office 365 グループを使用する](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce953-111">For more information, see [Use Office 365 Groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="ce953-112">管理センターでセキュリティ グループを管理する</span><span class="sxs-lookup"><span data-stu-id="ce953-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="ce953-113">セキュリティ グループを追加する</span><span class="sxs-lookup"><span data-stu-id="ce953-113">Add a security group</span></span>

1. <span data-ttu-id="ce953-114">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce953-114">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="ce953-115">[**グループ**] ページで、[**グループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="ce953-116">[**グループの種類の選択**] ページで、[**セキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="ce953-117">手順に従って、グループの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="ce953-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="ce953-118">メンバーをセキュリティ グループに追加する</span><span class="sxs-lookup"><span data-stu-id="ce953-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ce953-119">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ce953-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="ce953-120">[**グループ**] ページでセキュリティ グループ名を選択し、[**メンバー**] タブで [**すべてのメンバーの表示と管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="ce953-121">グループ ウィンドウで、[**メンバーの追加**] を選択し、リストから人を選択するか、[**検索**] ボックスに追加する人の名前を入力して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="ce953-122">メンバーを削除するには、そのメンバー名の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ce953-123">[**グループ**] ページでセキュリティ グループ名を選択し、[**メンバー**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="ce953-124">グループ ウィンドウで、[**メンバーの追加**] を選択し、リストから人を選択するか、[**検索**] ボックスに追加する人の名前を入力して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="ce953-125">メンバーを削除するには、そのメンバー名の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="ce953-126">[**グループ**] ページでセキュリティ グループ名を選択し、[**メンバー**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="ce953-127">グループ ウィンドウで、[**メンバーの追加**] を選択し、リストから人を選択するか、[**検索**] ボックスに追加する人の名前を入力して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="ce953-128">メンバーを削除するには、そのメンバー名の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="ce953-129">セキュリティ グループを編集する</span><span class="sxs-lookup"><span data-stu-id="ce953-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ce953-130">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ce953-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="ce953-131">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce953-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="ce953-132">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="ce953-133">[設定] ウィンドウで、[**全般**] タブまたは [**メンバー**] タブを選択し、グループの詳細またはメンバーを編集します。</span><span class="sxs-lookup"><span data-stu-id="ce953-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ce953-134">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce953-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="ce953-135">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="ce953-136">[セキュリティ グループ] ウィンドウで、[**名前**] タブまたは [**メンバー**] タブの横にある [**編集**] を選択し、グループの詳細またはメンバーを編集します。</span><span class="sxs-lookup"><span data-stu-id="ce953-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="ce953-137">変更が完了したら、[**保存**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ce953-138">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce953-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="ce953-139">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="ce953-140">[セキュリティ グループ] ウィンドウで、[**名前**] タブまたは [**メンバー**] タブの横にある [**編集**] を選択し、グループの詳細またはメンバーを編集します。</span><span class="sxs-lookup"><span data-stu-id="ce953-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="ce953-141">変更が完了したら、[**保存**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-141">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="ce953-142">セキュリティ グループを削除する</span><span class="sxs-lookup"><span data-stu-id="ce953-142">Delete a security group</span></span>

1. <span data-ttu-id="ce953-143">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce953-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="ce953-144">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="ce953-145">[**グループの削除**] (ゴミ箱アイコン) を選択し、[**削除**] を選択して確認します。</span><span class="sxs-lookup"><span data-stu-id="ce953-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="ce953-146">グループが削除されたら、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="ce953-147">Exchange Online グループと SharePoint Online グループ</span><span class="sxs-lookup"><span data-stu-id="ce953-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="ce953-148">ユーザー グループを作成して全員にメールを同時に送信できるようにする場合は、Exchange 管理センターで [**管理**] \> [**Exchange**] \> [**宛先**] \> [**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce953-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="ce953-149">次に、[**新規**]、[![追加](../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)] の順に選択し、作成するグループの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce953-149">Next, select **New**![Add](../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="ce953-150">**配布グループ**: メッセージをユーザー グループに配布するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ce953-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="ce953-151">これは、*メールが有効な配布グループ* (Office 365 では*配布リスト*) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ce953-151">It's also called a  *mail-enabled distribution group*, or, in Office 365, a  *distribution list*.</span></span> <span data-ttu-id="ce953-152">詳細については、「[配布グループの管理](https://technet.microsoft.com/library/bb124513.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce953-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="ce953-153">**セキュリティ グループ**: メッセージをユーザー グループに配布する、またはリソースへのアクセス許可を付与するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ce953-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="ce953-154">このグループは、*メールが有効なセキュリティ グループ*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ce953-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="ce953-155">詳細については、「[メールが有効なセキュリティ グループの管理](https://technet.microsoft.com/library/bb123521.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce953-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="ce953-156">**動的配布グループ**: メッセージの送信時に、定義されたフィルターと条件に基づいて宛先リストが毎回再確認されるタイプの配布グループ。</span><span class="sxs-lookup"><span data-stu-id="ce953-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="ce953-157">詳細については、「[動的配布グループの管理](https://technet.microsoft.com/library/bb123722.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce953-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="ce953-p107">配布グループとメールが有効なセキュリティ グループを Exchange 管理センターで作成した後、それらの名前とユーザー リストが Office 365 の [ **セキュリティ グループ**] ページに表示されます。このグループは、どちらの場所でも削除できますが、編集は Exchange 管理センターでのみ実行できます。動的配布グループは、Office 365 の [ **セキュリティ グループ**] ページには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ce953-p107">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the Office 365 **Security groups** page. You can delete these groups in both locations, but you can edit them only in the Exchange admin center. Dynamic distribution groups don't show up on the Office 365 **Security groups** page.</span></span> 
  
 <span data-ttu-id="ce953-161">SharePoint グループは、サイト コレクションの作成時に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ce953-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="ce953-162">既定のグループは、SharePoint の既定のアクセス許可レベル (SharePoint ロールと呼ばれることもあります) を使用して、ユーザーに権限とアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="ce953-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="ce953-163">詳細については、「[SharePoint Online の既定の SharePoint グループ](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce953-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="ce953-164">セキュリティ グループは、SharePoint で作成したセキュリティ グループとどのように異なりますか?</span><span class="sxs-lookup"><span data-stu-id="ce953-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="ce953-165">セキュリティ グループは、SharePoint、Exchange、MDM、Windows などで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce953-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="ce953-166">SharePoint で作成したセキュリティ グループは、その SharePoint サイト コレクションでしか認識されません。</span><span class="sxs-lookup"><span data-stu-id="ce953-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="ce953-167">組織をセキュリティで保護するためにはセキュリティ グループを使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="ce953-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="ce953-p110">いいえ。これは、組織のセキュリティを管理できる方法の 1 つです。常にユーザーにはアクセス許可およびサイトへのアクセス権限を個別に付与することができます。ただし、セキュリティ グループを使用すれば、大規模なユーザー グループを容易に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ce953-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="ce953-172">セキュリティ グループにメールを送信できますか?</span><span class="sxs-lookup"><span data-stu-id="ce953-172">Can I send email to a security group?</span></span>

<span data-ttu-id="ce953-173">はい。</span><span class="sxs-lookup"><span data-stu-id="ce953-173">Yes.</span></span> <span data-ttu-id="ce953-174">ただし、メールおよびコラボレーション用にグループを使用する場合は、[Office 365 グループを作成する](../create-groups/create-groups.md)ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ce953-174">But if you want to use groups for email and collaboration, we recommend that you [create an Office 365 group](../create-groups/create-groups.md) instead.</span></span> 
  