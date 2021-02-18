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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 分離した SharePoint Online チーム サイトの管理、新しいユーザーとグループの追加、ユーザーとグループの削除、カスタム アクセス許可を持つドキュメント サブフォルダーの作成を行います。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289523"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="85400-103">分離した SharePoint Online チーム サイトの管理</span><span class="sxs-lookup"><span data-stu-id="85400-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="85400-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="85400-104">**Applies to**</span></span>
- [<span data-ttu-id="85400-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="85400-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="85400-106">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="85400-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="85400-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="85400-107">SharePoint Online</span></span> 

 <span data-ttu-id="85400-108">**概要:** 以下の手順を使用して、分離した SharePoint Online チーム サイトを管理します。</span><span class="sxs-lookup"><span data-stu-id="85400-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="85400-109">この記事では、分離した SharePoint Online チーム サイトの一般的な管理操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="85400-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="85400-110">新しいユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-110">Add a new user</span></span>

<span data-ttu-id="85400-111">他のユーザーが新しいサイトに参加する場合は、サイトでの参加レベルを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85400-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="85400-112">管理:サイト管理者のアクセス グループに新しいユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="85400-113">アクティブ コラボレーション:サイト メンバーのアクセス グループにユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="85400-114">表示:サイト ビューアーのアクセス グループにユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="85400-115">Active Directory ドメイン サービス (AD DS) を使用してユーザー アカウントとグループを管理している場合は、通常の AD DS ユーザーおよびグループ管理手順を使用して適切なユーザーを適切なアクセス グループに追加し、サブスクリプションとの同期を待ちます。</span><span class="sxs-lookup"><span data-stu-id="85400-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="85400-116">Microsoft 365 を使用してユーザー アカウントとグループを管理している場合は、Microsoft 365 管理センターまたは Microsoft PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85400-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="85400-117">Microsoft 365 管理センターでは、ユーザー アカウント管理者または会社管理者の役割が割り当てられているユーザー アカウントでサインインし、グループを使用して適切なユーザーを適切なアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="85400-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="85400-118">PowerShell の場合は、 [最初に Graph 用 Azure Active Directory PowerShell モジュールを使用して接続します](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="85400-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="85400-119">ユーザー プリンシパル名 (UPN) を使ってユーザー アカウントをアクセス グループに追加するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="85400-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="85400-120">表示名を使ってユーザー アカウントをアクセス グループに追加するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="85400-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="85400-121">新しいグループを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-121">Add a new group</span></span>

<span data-ttu-id="85400-122">グループ全体にアクセスを追加するには、サイト内のグループのすべてのメンバーへの参加レベルを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85400-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="85400-123">管理:サイト管理者のアクセス グループにグループを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="85400-124">アクティブ コラボレーション:サイト メンバーのアクセス グループにグループを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="85400-125">表示:サイト ビューアーのアクセス グループにグループを追加する</span><span class="sxs-lookup"><span data-stu-id="85400-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="85400-126">AD DS を使用してユーザー アカウントとグループを管理している場合は、通常の AD DS ユーザーおよびグループ管理手順を使用して適切なグループを適切なグループに追加し、サブスクリプションとの同期を待ちます。</span><span class="sxs-lookup"><span data-stu-id="85400-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="85400-127">Office 365 を使用してユーザー アカウントとグループを管理している場合は、Microsoft 365 管理センターまたは PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85400-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="85400-128">Microsoft 365 管理センターでは、ユーザー アカウント管理者または会社管理者の役割が割り当てられているユーザー アカウントでサインインし、グループを使用して適切なグループを適切なアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="85400-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="85400-129">PowerShell の場合は、 [最初に Graph 用 Azure Active Directory PowerShell モジュールを使用して接続します](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="85400-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="85400-130">その後、次の PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="85400-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="85400-131">ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-131">Remove a user</span></span>

<span data-ttu-id="85400-132">他のユーザーのアクセスをサイトから削除する必要がある場合は、サイトでの参加に基づいてそのユーザーが現在メンバーになっているアクセス グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="85400-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="85400-133">管理:サイト管理者のアクセス グループからユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="85400-134">アクティブ コラボレーション:サイト メンバーのアクセス グループからユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="85400-135">表示:サイト ビューアーのアクセス グループからユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="85400-136">AD DS を使用してユーザー アカウントとグループを管理している場合は、通常の AD DS ユーザーおよびグループ管理手順を使用して適切なユーザーを適切なアクセス グループから削除し、サブスクリプションとの同期を待ちます。</span><span class="sxs-lookup"><span data-stu-id="85400-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="85400-137">Office 365 を使用してユーザー アカウントとグループを管理している場合は、Microsoft 365 管理センターまたは PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85400-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="85400-138">Microsoft 365 管理センターでは、ユーザー アカウント管理者または会社管理者の役割が割り当てられているユーザー アカウントでサインインし、グループを使用して適切なユーザーを適切なアクセス グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="85400-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="85400-139">PowerShell の場合は、 [最初に Graph 用 Azure Active Directory PowerShell モジュールを使用して接続します](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="85400-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="85400-140">UPN を使ってアクセス グループからユーザー アカウントを削除するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="85400-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="85400-141">表示名を使ってアクセス グループからユーザー アカウントを削除するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="85400-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="85400-142">グループを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-142">Remove a group</span></span>

<span data-ttu-id="85400-143">グループ全体のアクセスを削除する必要がある場合は、サイトでの参加に基づいてそのグループが現在メンバーになっているアクセス グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="85400-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="85400-144">管理:サイト管理者のアクセス グループからグループを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="85400-145">アクティブ コラボレーション:サイト メンバーのアクセス グループからグループを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="85400-146">表示:サイト ビューアーのアクセス グループからグループを削除する</span><span class="sxs-lookup"><span data-stu-id="85400-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="85400-147">Windows Server Active Directory を使用してユーザー アカウントとグループを管理している場合は、通常の AD DS ユーザーおよびグループ管理手順を使用して適切なアクセス グループから適切なグループを削除し、サブスクリプションとの同期を待ちます。</span><span class="sxs-lookup"><span data-stu-id="85400-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="85400-148">Office 365 を使用してユーザー アカウントとグループを管理している場合は、Microsoft 365 管理センターまたは PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85400-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="85400-149">Microsoft 365 管理センターでは、ユーザー アカウント管理者または会社管理者の役割が割り当てられているユーザー アカウントでサインインし、グループを使用して適切なアクセス グループから適切なグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="85400-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="85400-150">PowerShell の場合は、 [最初に Graph 用 Azure Active Directory PowerShell モジュールを使用して接続します](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="85400-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="85400-151">表示名を使用してアクセス グループからグループを削除するには、次の PowerShell コマンド ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="85400-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="85400-152">カスタムのアクセス許可を持つドキュメントのサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="85400-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="85400-p105">分離したサイト内で作業している人々のサブセットでは、コラボレーションするためにプライバシー性の高い場所が必要になることがあります。SharePoint Online サイトでは、サイトの [ドキュメント] フォルダーにサブフォルダーを作成し、カスタムのアクセス許可を割り当てることがことができます。アクセス許可を持たないユーザーはサブフォルダーを表示できません。</span><span class="sxs-lookup"><span data-stu-id="85400-p105">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="85400-156">カスタムのアクセス許可を持つドキュメントのサブフォルダーを作成するには、以下のことを行います。</span><span class="sxs-lookup"><span data-stu-id="85400-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="85400-157">サイトの管理者アクセス グループのメンバーであるアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="85400-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="85400-158">詳細については、「[一般法人向け Microsoft 365 にサインインする場所](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85400-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="85400-159">分離したチーム サイトに移動し、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="85400-160">カスタムのアクセス許可を持つサブフォルダーを格納するフォルダーをドキュメントのフォルダーの中で参照し、そのフォルダーを作成して開きます。</span><span class="sxs-lookup"><span data-stu-id="85400-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="85400-161">[ **共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-161">Click **Share**.</span></span>

5. <span data-ttu-id="85400-162">**[共有相手] > [詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="85400-163">**[アクセス許可の継承の中止]** をクリックしてから、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="85400-164">[ **共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-164">Click **Share**.</span></span>

8. <span data-ttu-id="85400-165">**[共有相手] > [詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="85400-166">**[アクセス許可を付与する] > [共有相手] > [詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="85400-167">On the permissions page, click **\<site name> Members in the list**.</span><span class="sxs-lookup"><span data-stu-id="85400-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="85400-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="85400-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="85400-169">特定のメンバーをこのサブフォルダーに追加するには、 **[新規] > [ユーザーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="85400-170">**[共有]** ダイアログ ボックスで、サブフォルダー内のファイルでコラボレーションできるユーザー アカウントの名前を入力してから、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85400-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="85400-171">Web ページを更新して新しい結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="85400-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="85400-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="85400-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="85400-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="85400-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="85400-174">ブラウザーで **[ユーザーとグループ]** タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="85400-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="85400-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="85400-175">See Also</span></span>

[<span data-ttu-id="85400-176">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="85400-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="85400-177">分離した SharePoint Online チーム サイトの設計</span><span class="sxs-lookup"><span data-stu-id="85400-177">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="85400-178">分離した SharePoint Online チーム サイトの展開</span><span class="sxs-lookup"><span data-stu-id="85400-178">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
