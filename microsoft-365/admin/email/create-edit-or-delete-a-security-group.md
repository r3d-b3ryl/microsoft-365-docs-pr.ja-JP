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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: セキュリティ グループの作成、編集、削除について説明します。
ms.openlocfilehash: 525acc45b293563f58bb9aa12c40bec1438cb055
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393957"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1d933-103">Microsoft 365 管理センターでセキュリティ グループを作成、編集、削除する</span><span class="sxs-lookup"><span data-stu-id="1d933-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1d933-104">[グループ **Microsoft 365]** ページで、オンラインおよび CRM Online で同じアクセス許可を割り当てるのに使用できるユーザー アカウントのSharePoint作成できます。</span><span class="sxs-lookup"><span data-stu-id="1d933-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="1d933-105">たとえば、管理者は、特定のユーザー グループに対して SharePoint サイトへのアクセス権を付与するセキュリティ グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1d933-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="1d933-106">セキュリティ グループを作成、編集、または削除できるのは、グローバル管理者とユーザー管理の管理者だけです。詳細については、「[管理者ロールの割り当て](../add-users/assign-admin-roles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d933-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="1d933-107">他に、メールの送信やユーザー グループにアクセス許可を割り当てるために使用できる [Exchange Online グループと SharePoint Online グループ](#groups-in-exchange-online-and-sharepoint-online)と、ユーザーに権限を付与し、サイトとサイト コレクションへのアクセスを許可する [Exchange Online グループと SharePoint Online グループ](#groups-in-exchange-online-and-sharepoint-online)があります。</span><span class="sxs-lookup"><span data-stu-id="1d933-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="1d933-108">サイト メールボックスを使用しますか?</span><span class="sxs-lookup"><span data-stu-id="1d933-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="1d933-109">個別ではなくセキュリティ グループを使用して SharePoint に追加されたすべてのユーザーは、SharePoint からのみサイト メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d933-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="1d933-110">これらのユーザーは、Outlook からサイト メールボックスにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1d933-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="1d933-111">詳細については、「サイト メールボックス[の代わりにMicrosoft 365グループを使用する」を参照してください](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)。</span><span class="sxs-lookup"><span data-stu-id="1d933-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="1d933-112">管理センターでセキュリティ グループを管理する</span><span class="sxs-lookup"><span data-stu-id="1d933-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="1d933-113">セキュリティ グループを追加する</span><span class="sxs-lookup"><span data-stu-id="1d933-113">Add a security group</span></span>

1. <span data-ttu-id="1d933-114">Microsoft 365 管理センターで、**[グループ]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">[グループ]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d933-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1d933-115">[**グループ**] ページで、[**グループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="1d933-116">[**グループの種類の選択**] ページで、[**セキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="1d933-117">手順に従って、グループの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="1d933-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="1d933-118">メンバーをセキュリティ グループに追加する</span><span class="sxs-lookup"><span data-stu-id="1d933-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="1d933-119">[**グループ**] ページでセキュリティ グループ名を選択し、[**メンバー**] タブで [**すべてのメンバーの表示と管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="1d933-120">グループ ウィンドウで、[**メンバーの追加**] を選択し、リストから人を選択するか、[**検索**] ボックスに追加する人の名前を入力して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="1d933-121">メンバーを削除するには、そのメンバー名の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="1d933-122">セキュリティ グループを編集する</span><span class="sxs-lookup"><span data-stu-id="1d933-122">Edit a security group</span></span>

1. <span data-ttu-id="1d933-123">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d933-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1d933-124">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1d933-125">[設定] ウィンドウで、[**全般**] タブまたは [**メンバー**] タブを選択し、グループの詳細またはメンバーを編集します。</span><span class="sxs-lookup"><span data-stu-id="1d933-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="1d933-126">セキュリティ グループを削除する</span><span class="sxs-lookup"><span data-stu-id="1d933-126">Delete a security group</span></span>

1. <span data-ttu-id="1d933-127">管理センターで、[**グループ**]  >  [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1d933-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="1d933-128">[**グループ**] ページで、グループ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1d933-129">[**グループの削除**] (ゴミ箱アイコン) を選択し、[**削除**] を選択して確認します。</span><span class="sxs-lookup"><span data-stu-id="1d933-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="1d933-130">グループが削除されたら、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="1d933-131">Exchange Online グループと SharePoint Online グループ</span><span class="sxs-lookup"><span data-stu-id="1d933-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="1d933-132">ユーザー グループを作成して全員にメールを同時に送信できるようにする場合は、Exchange 管理センターで [**管理**] \> [**Exchange**] \> [**宛先**] \> [**グループ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d933-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="1d933-133">次に、[**新規**]、[![追加](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)] の順に選択し、作成するグループの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d933-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="1d933-134">**配布グループ**: メッセージをユーザー グループに配布するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1d933-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="1d933-135">また、メールが有効な配布 *グループ、または* 配布リストとも *呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="1d933-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="1d933-136">詳細については、「[配布グループの管理](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d933-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="1d933-137">**セキュリティ グループ**: メッセージをユーザー グループに配布する、またはリソースへのアクセス許可を付与するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1d933-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="1d933-138">このグループは、*メールが有効なセキュリティ グループ* とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1d933-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="1d933-139">詳細については、「[メールが有効なセキュリティ グループの管理](/Exchange/recipients/mail-enabled-security-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d933-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="1d933-140">**動的配布グループ**: メッセージの送信時に、定義されたフィルターと条件に基づいて宛先リストが毎回再確認されるタイプの配布グループ。</span><span class="sxs-lookup"><span data-stu-id="1d933-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="1d933-141">詳細については、「[動的配布グループの管理](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d933-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="1d933-142">管理センターで配布グループとメールが有効なセキュリティ グループをExchange、その名前とユーザー リストが [セキュリティ グループ **] ページに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1d933-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="1d933-143">このグループは、どちらの場所でも削除できますが、編集は Exchange 管理センターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="1d933-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="1d933-144">動的配布グループは 、[セキュリティ グループ] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1d933-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="1d933-145">SharePoint グループは、サイト コレクションの作成時に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d933-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="1d933-146">既定のグループは、SharePoint の既定のアクセス許可レベル (SharePoint ロールと呼ばれることもあります) を使用して、ユーザーに権限とアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="1d933-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="1d933-147">詳細については、「[SharePoint Online の既定の SharePoint グループ](/sharepoint/default-sharepoint-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d933-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="1d933-148">セキュリティ グループは、SharePoint で作成したセキュリティ グループとどのように異なりますか?</span><span class="sxs-lookup"><span data-stu-id="1d933-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="1d933-149">セキュリティ グループは、SharePoint、Exchange、MDM、Windows などで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d933-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="1d933-150">SharePoint で作成したセキュリティ グループは、その SharePoint サイト コレクションでしか認識されません。</span><span class="sxs-lookup"><span data-stu-id="1d933-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="1d933-151">組織をセキュリティで保護するためにはセキュリティ グループを使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="1d933-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="1d933-p110">いいえ。これは、組織のセキュリティを管理できる方法の 1 つです。常にユーザーにはアクセス許可およびサイトへのアクセス権限を個別に付与することができます。ただし、セキュリティ グループを使用すれば、大規模なユーザー グループを容易に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="1d933-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="1d933-156">セキュリティ グループにメールを送信できますか?</span><span class="sxs-lookup"><span data-stu-id="1d933-156">Can I send email to a security group?</span></span>

<span data-ttu-id="1d933-157">はい。</span><span class="sxs-lookup"><span data-stu-id="1d933-157">Yes.</span></span> <span data-ttu-id="1d933-158">ただし、メールと共同作業にグループを使用する場合は、代わりにグループを作成[Microsoft 365](../create-groups/create-groups.md)勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d933-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

## <a name="related-content"></a><span data-ttu-id="1d933-159">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1d933-159">Related content</span></span>

<span data-ttu-id="1d933-160">[グループを作成するには、Microsoft 365 管理センター](../create-groups/create-groups.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="1d933-160">[Create a group in the Microsoft 365 admin center](../create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="1d933-161">[ユーザー Microsoft 365グループの説明](../create-groups/explain-groups-knowledge-worker.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="1d933-161">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
<span data-ttu-id="1d933-162">[グループを管理する (Microsoft 365 管理センター)](../create-groups/manage-groups.md)</span><span class="sxs-lookup"><span data-stu-id="1d933-162">[Manage a group in the Microsoft 365 admin center](../create-groups/manage-groups.md) (article)</span></span>