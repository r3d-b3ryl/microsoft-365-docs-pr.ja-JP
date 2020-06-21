---
title: 分離した SharePoint Online チーム サイトの管理
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 分離した SharePoint Online チームサイトを管理し、新しいユーザーとグループを追加し、ユーザーとグループを削除し、カスタムアクセス許可を持つドキュメントサブフォルダーを作成します。
ms.openlocfilehash: 43329aa72b3729200007441ce73838a7d6a60f55
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755380"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="c352e-103">分離した SharePoint Online チーム サイトの管理</span><span class="sxs-lookup"><span data-stu-id="c352e-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="c352e-104">**概要:** 以下の手順を使用して、分離した SharePoint Online チーム サイトを管理します。</span><span class="sxs-lookup"><span data-stu-id="c352e-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="c352e-105">この記事では、分離した SharePoint Online チーム サイトの一般的な管理操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c352e-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="c352e-106">新しいユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-106">Add a new user</span></span>

<span data-ttu-id="c352e-107">他のユーザーが新しいサイトに参加する場合は、サイトでの参加レベルを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c352e-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="c352e-108">管理:サイト管理者のアクセス グループに新しいユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="c352e-109">アクティブ コラボレーション:サイト メンバーのアクセス グループにユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="c352e-110">表示:サイト ビューアーのアクセス グループにユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="c352e-111">Active Directory ドメインサービス (AD DS) を使用してユーザーアカウントとグループを管理している場合は、通常の AD DS のユーザーおよびグループ管理手順を使用して適切なアクセスグループに適切なユーザーを追加し、サブスクリプションとの同期を待機します。</span><span class="sxs-lookup"><span data-stu-id="c352e-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="c352e-112">Microsoft 365 を介してユーザーアカウントとグループを管理している場合は、Microsoft 365 管理センターまたは Microsoft PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c352e-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="c352e-113">Microsoft 365 管理センターの場合は、ユーザーアカウント管理者または会社の管理者の役割が割り当てられているユーザーアカウントでサインインし、グループを使用して適切なアクセスグループに適切なユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c352e-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="c352e-114">PowerShell の場合、まず、 [Azure Active Directory PowerShell For Graph モジュールに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="c352e-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="c352e-115">ユーザー プリンシパル名 (UPN) を使ってユーザー アカウントをアクセス グループに追加するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c352e-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="c352e-116">表示名を使ってユーザー アカウントをアクセス グループに追加するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c352e-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="c352e-117">新しいグループを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-117">Add a new group</span></span>

<span data-ttu-id="c352e-118">グループ全体にアクセスを追加するには、サイト内のグループのすべてのメンバーへの参加レベルを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c352e-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="c352e-119">管理:サイト管理者のアクセス グループにグループを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="c352e-120">アクティブ コラボレーション:サイト メンバーのアクセス グループにグループを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="c352e-121">表示:サイト ビューアーのアクセス グループにグループを追加する</span><span class="sxs-lookup"><span data-stu-id="c352e-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="c352e-122">AD DS を介してユーザーアカウントとグループを管理している場合は、通常の AD DS のユーザーおよびグループ管理手順を使用して適切なグループに適切なグループを追加し、サブスクリプションとの同期を待機します。</span><span class="sxs-lookup"><span data-stu-id="c352e-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="c352e-123">Office 365 を介してユーザーアカウントとグループを管理している場合は、Microsoft 365 管理センターまたは PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c352e-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="c352e-124">Microsoft 365 管理センターの場合は、ユーザーアカウント管理者または会社の管理者の役割が割り当てられているユーザーアカウントでサインインし、グループを使用して適切なアクセスグループに適切なグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="c352e-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="c352e-125">PowerShell の場合、まず、 [Azure Active Directory PowerShell For Graph モジュールに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="c352e-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="c352e-126">その後、次の PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c352e-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="c352e-127">ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-127">Remove a user</span></span>

<span data-ttu-id="c352e-128">他のユーザーのアクセスをサイトから削除する必要がある場合は、サイトでの参加に基づいてそのユーザーが現在メンバーになっているアクセス グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="c352e-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="c352e-129">管理:サイト管理者のアクセス グループからユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="c352e-130">アクティブ コラボレーション:サイト メンバーのアクセス グループからユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="c352e-131">表示:サイト ビューアーのアクセス グループからユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="c352e-132">AD DS を介してユーザーアカウントとグループを管理している場合は、通常の AD DS のユーザーおよびグループ管理手順を使用して適切なアクセスグループから適切なユーザーを削除し、サブスクリプションとの同期を待機します。</span><span class="sxs-lookup"><span data-stu-id="c352e-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="c352e-133">Office 365 を介してユーザーアカウントとグループを管理している場合は、Microsoft 365 管理センターまたは PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c352e-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="c352e-134">Microsoft 365 管理センターの場合は、ユーザーアカウント管理者または会社の管理者の役割が割り当てられているユーザーアカウントでサインインし、グループを使用して適切なアクセスグループから適切なユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c352e-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="c352e-135">PowerShell の場合、まず、 [Azure Active Directory PowerShell For Graph モジュールに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="c352e-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="c352e-136">UPN を使ってアクセス グループからユーザー アカウントを削除するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c352e-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="c352e-137">表示名を使ってアクセス グループからユーザー アカウントを削除するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c352e-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="c352e-138">グループを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-138">Remove a group</span></span>

<span data-ttu-id="c352e-139">グループ全体のアクセスを削除する必要がある場合は、サイトでの参加に基づいてそのグループが現在メンバーになっているアクセス グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="c352e-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="c352e-140">管理:サイト管理者のアクセス グループからグループを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="c352e-141">アクティブ コラボレーション:サイト メンバーのアクセス グループからグループを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="c352e-142">表示:サイト ビューアーのアクセス グループからグループを削除する</span><span class="sxs-lookup"><span data-stu-id="c352e-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="c352e-143">Windows Server Active Directory を使用してユーザーアカウントとグループを管理している場合は、通常の AD DS ユーザーおよびグループ管理手順を使用して適切なアクセスグループから適切なグループを削除し、サブスクリプションとの同期を待機します。</span><span class="sxs-lookup"><span data-stu-id="c352e-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="c352e-144">Office 365 を介してユーザーアカウントとグループを管理している場合は、Microsoft 365 管理センターまたは PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c352e-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="c352e-145">Microsoft 365 管理センターの場合は、ユーザーアカウント管理者または会社の管理者の役割が割り当てられているユーザーアカウントでサインインし、グループを使用して適切なアクセスグループから適切なグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="c352e-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="c352e-146">PowerShell の場合、まず、 [Azure Active Directory PowerShell For Graph モジュールに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="c352e-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="c352e-147">表示名を使用してアクセス グループからグループを削除するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c352e-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="c352e-148">カスタムのアクセス許可を持つドキュメントのサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c352e-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="c352e-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span><span class="sxs-lookup"><span data-stu-id="c352e-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="c352e-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span><span class="sxs-lookup"><span data-stu-id="c352e-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="c352e-151">Those without permissions will not see the subfolder.</span><span class="sxs-lookup"><span data-stu-id="c352e-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="c352e-152">カスタムのアクセス許可を持つドキュメントのサブフォルダーを作成するには、以下のことを行います。</span><span class="sxs-lookup"><span data-stu-id="c352e-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="c352e-153">サイトの管理者アクセスグループのメンバーであるアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c352e-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="c352e-154">詳細については、「[一般法人向け Microsoft 365 にサインインする場所](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c352e-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="c352e-155">分離したチーム サイトに移動し、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="c352e-156">カスタムのアクセス許可を持つサブフォルダーを格納するフォルダーをドキュメントのフォルダーの中で参照し、そのフォルダーを作成して開きます。</span><span class="sxs-lookup"><span data-stu-id="c352e-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="c352e-157">[ **共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="c352e-158">**[共有相手] > [詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="c352e-159">**[アクセス許可の継承の中止]** をクリックしてから、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="c352e-160">[ **共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="c352e-161">**[共有相手] > [詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="c352e-162">**[アクセス許可を付与する] > [共有相手] > [詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="c352e-163">On the permissions page, click **\<site name> Members in the list**.</span><span class="sxs-lookup"><span data-stu-id="c352e-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="c352e-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="c352e-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="c352e-165">特定のメンバーをこのサブフォルダーに追加するには、 **[新規] > [ユーザーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="c352e-166">**[共有]** ダイアログ ボックスで、サブフォルダー内のファイルでコラボレーションできるユーザー アカウントの名前を入力してから、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c352e-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="c352e-167">Web ページを更新して新しい結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c352e-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="c352e-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="c352e-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="c352e-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="c352e-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="c352e-170">ブラウザーで **[ユーザーとグループ]** タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c352e-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c352e-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="c352e-171">See Also</span></span>

[<span data-ttu-id="c352e-172">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="c352e-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="c352e-173">分離した SharePoint Online チーム サイトの設計</span><span class="sxs-lookup"><span data-stu-id="c352e-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="c352e-174">分離した SharePoint Online チーム サイトの展開</span><span class="sxs-lookup"><span data-stu-id="c352e-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



