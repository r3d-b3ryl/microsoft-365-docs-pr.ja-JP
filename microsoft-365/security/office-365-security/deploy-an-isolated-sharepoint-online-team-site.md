---
title: 分離した SharePoint Online チーム サイトの展開
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: このステップ バイ ステップ展開ガイドを使用して、SharePoint Online の独立したチーム サイトを Microsoft Office 365 で作成および構成します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d226a545c3f8dc274f02e5d54d39739fe5d981ea
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288349"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="4c4c2-103">分離した SharePoint Online チーム サイトの展開</span><span class="sxs-lookup"><span data-stu-id="4c4c2-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4c4c2-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4c4c2-104">**Applies to**</span></span>
- [<span data-ttu-id="4c4c2-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="4c4c2-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4c4c2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c4c2-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="4c4c2-107">**概要:** ステップごとの手順を使用して、分離した新しい SharePoint Online チーム サイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="4c4c2-p101">この記事は、分離した SharePoint Online チーム サイトを Microsoft Office 365 で作成および構成するためのステップごとの展開ガイドです。これらの手順は、アクセス レベルごとに 1 つの Azure Active Directory (AD) ベースのアクセス グループが含まれる、3 つの既定の SharePoint グループとそれに対応するアクセス許可レベルの使用を前提としています。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-p101">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="4c4c2-110">フェーズ 1:チーム サイト アクセス グループの作成と設定</span><span class="sxs-lookup"><span data-stu-id="4c4c2-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="4c4c2-111">このフェーズでは、3 つの既定の SharePoint グループに対して 3 つの Azure AD ベースのアクセス グループを作成し、それらに適切なユーザー アカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="4c4c2-p102">次の手順は、すべての必要なユーザー アカウントが既に存在し、適切なライセンスが割り当てられていることを前提としています。そうでない場合は、それらを追加して、手順 1 に進む前にライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-p102">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="4c4c2-114">手順 1:サイトの SharePoint Online 管理者を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4c4c2-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="4c4c2-115">分離したチーム サイトの SharePoint Online 管理者に対応するユーザー アカウントのセットを決定します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="4c4c2-116">Microsoft 365 を使用してユーザー アカウントとグループを管理し、Windows PowerShell を使用する場合は、ユーザー プリンシパル名 (UPN) の一覧 (UPN: belindan@contoso.com など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="4c4c2-117">手順 2: サイトのメンバーを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4c4c2-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="4c4c2-118">分離したチーム サイトのメンバーに対応するユーザー アカウントのセットを決定します。メンバーはサイト内に格納されているリソースで共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="4c4c2-119">Microsoft 365 を使用してユーザー アカウントとグループを管理し、PowerShell を使用する場合は、UPN の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="4c4c2-120">サイト メンバーが数多く存在する場合は、UPN の一覧をテキスト ファイルに格納し、PowerShell コマンドを 1 回実行することですべて追加できます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="4c4c2-121">手順 3:サイトのビューアーを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4c4c2-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="4c4c2-122">分離したチーム サイトのビューアーに対応するユーザー アカウントのセットを決定します。ビューアーは、サイトに格納されているリソースを表示できますが、リソースを変更したり、そのコンテンツで直接共同作業を行ったりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="4c4c2-123">Microsoft 365 を使用してユーザー アカウントとグループを管理し、PowerShell を使用する場合は、UPN の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="4c4c2-124">サイト メンバーが数多く存在する場合は、UPN の一覧をテキスト ファイルに格納し、PowerShell コマンドを 1 回実行することですべて追加できます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="4c4c2-125">サイトのビューアーには、経営幹部、弁護士、または部門間の利害関係者などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="4c4c2-126">手順 4:Azure AD でサイト用の 3 つのアクセス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="4c4c2-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="4c4c2-127">Azure AD で次のアクセス グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="4c4c2-128">サイト管理者 (手順 1 のリストが含まれます)</span><span class="sxs-lookup"><span data-stu-id="4c4c2-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="4c4c2-129">サイト メンバー (手順 2 のリストが含まれます)</span><span class="sxs-lookup"><span data-stu-id="4c4c2-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="4c4c2-130">サイト ビューアー (手順 3 のリストが含まれます)</span><span class="sxs-lookup"><span data-stu-id="4c4c2-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="4c4c2-131">お使いのブラウザーで、Azure Portal (<https://portal.azure.com>) に移動し、ユーザー管理の管理者または会社管理者のロールに割り当てられたアカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="4c4c2-132">Azure Portal で **[Azure Active Directory] > [グループ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="4c4c2-133">**[グループ] - [すべてのグループ]** ブレードで、**[+ 新しいグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="4c4c2-134">[新しい **グループ] ブレードで、次の設定を** 行います。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="4c4c2-135">**[グループの種類]** で **[セキュリティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="4c4c2-136">**[名前]** にグループ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="4c4c2-137">**[グループの説明]** にグループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="4c4c2-138">**[メンバーシップの種類]** で **[割り当て済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="4c4c2-139">**[作成]** をクリックして、 **[グループ]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="4c4c2-140">追加グループについて手順 3 から 5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="4c4c2-141">Office の機能を有効にできるグループを作成するには、Azure Portal を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="4c4c2-142">SharePoint Online の分離サイトが後で Azure Information Protection ラベルを持つ高機密サイトとして構成され、ファイルを暗号化し、特定のグループにアクセス許可を割り当てる場合、許可されたグループは Office 機能を有効にした上で作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="4c4c2-143">Azure AD グループが作成された後は、その Office の機能の設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="4c4c2-144">これで 3 つのサイトのアクセス グループの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-144">Here is your resulting configuration with the three site access groups.</span></span>

![独立した SharePoint Online サイトの展開用の 3 つのアクセス グループ。](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="4c4c2-p106">手順 5:アクセス グループにユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="4c4c2-p106">Step 5. Add the user accounts to the access groups</span></span>

<span data-ttu-id="4c4c2-148">この手順では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-148">In this step, do the following:</span></span>

1. <span data-ttu-id="4c4c2-149">手順 1 のユーザーの一覧をサイト管理者アクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="4c4c2-150">手順 2 のユーザーの一覧をサイト メンバーのアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="4c4c2-151">手順 3 のユーザーの一覧をサイト閲覧者のアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="4c4c2-152">Active Directory ドメイン サービス (AD DS) を使用してユーザー アカウントとグループを管理している場合は、通常の AD DS ユーザーおよびグループ管理手順を使用して適切なアクセス グループにユーザーを追加し、Microsoft 365 サブスクリプションとの同期を待ちます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="4c4c2-153">Office 365 を使用してユーザー アカウントとグループを管理している場合は、Microsoft 365 管理センターまたは PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="4c4c2-154">すべてのアクセス グループに重複するグループ名がある場合は、Microsoft 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="4c4c2-155">Microsoft 365 管理センターでは、ユーザー アカウント管理者または会社管理者の役割が割り当てられているユーザー アカウントでサインインし、グループを使用して適切なユーザー アカウントとグループを適切なアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="4c4c2-156">PowerShell の場合は、 [最初に Graph 用 Azure Active Directory PowerShell モジュールを使用して接続します](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="4c4c2-157">次に、以下のコマンド ブロックを使用して、個々のユーザー アカウントをアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="4c4c2-158">いずれかのアクセス グループのユーザー アカウントの UPN をテキスト ファイルに格納した場合は、次の PowerShell コマンド ブロックを使用して、それらすべてのユーザー アカウントを一度に追加します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="4c4c2-159">PowerShell の場合、次のコマンド ブロックを使用して、個々のグループをアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="4c4c2-160">次のような結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-160">The results should be the following:</span></span>

- <span data-ttu-id="4c4c2-161">サイト管理者の Azure AD グループには、サイト管理者のユーザー アカウントまたはグループが含まれる</span><span class="sxs-lookup"><span data-stu-id="4c4c2-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="4c4c2-162">サイト メンバーの Azure AD グループには、サイト メンバーのユーザー アカウントまたはグループが含まれる</span><span class="sxs-lookup"><span data-stu-id="4c4c2-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="4c4c2-163">サイト ビューアーの Azure AD グループには、サイトのコンテンツを表示できるユーザー アカウントまたはグループのみが含まれる</span><span class="sxs-lookup"><span data-stu-id="4c4c2-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="4c4c2-164">Microsoft 365 管理センターまたは次の PowerShell コマンド ブロックを使用して、各アクセス グループのグループ メンバーの一覧を検証します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="4c4c2-165">以下に示すのが、でき上がった構成で、この構成にはユーザー アカウントとグループが設定された3 つのサイトのアクセス グループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![ユーザー アカウントが設定された 3 つのアクセス グループ。](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="4c4c2-167">フェーズ 2:分離したチーム サイトを作成し構成する</span><span class="sxs-lookup"><span data-stu-id="4c4c2-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="4c4c2-168">このフェーズでは、分離した SharePoint Online サイトを作成し、新しい Azure AD ベースのアクセス グループを使用するために既定の SharePoint Online アクセス許可レベルのアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="4c4c2-169">既定では、新しいチーム サイトには Microsoft 365 グループと他の関連リソースが含まれますが、この場合は、Microsoft 365 グループなしでチーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="4c4c2-170">これにより、SharePoint を通じてアクセス許可を完全に維持できます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="4c4c2-171">最初に、次の手順で SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="4c4c2-172">SharePoint Online チーム サイト (SharePoint Online 管理者) の管理にも使用されるアカウントを使用して、Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="4c4c2-173">詳細については、「[一般法人向け Office 365 にサインインする場所](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4c4c2-174">Microsoft 365 管理センターの[管理センター] で **、[SharePoint] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="4c4c2-175">SharePoint 管理センターで、[サイト] **を展開し** 、[アクティブなサイト] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="4c4c2-176">[作成 **] を** クリックし、[その他のオプション] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="4c4c2-177">[テンプレートの **選択] ボックスの一覧** で、[チーム サイト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="4c4c2-178">**[サイト名]** にチーム サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="4c4c2-179">プライマリ **管理者で**、ログインに使用するアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="4c4c2-180">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-180">Click **Finish**.</span></span>

<span data-ttu-id="4c4c2-181">次に、新しい SharePoint Online チーム サイトから、アクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="4c4c2-182">ツールバーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="4c4c2-183">[ **サイトの共有] で**、[メンバー **が共有する方法の変更] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="4c4c2-184">Choose the **Only site owners can share files, folders, and the site**.</span><span class="sxs-lookup"><span data-stu-id="4c4c2-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="4c4c2-185">[ **アクセス要求を許可する] を [オフ]** に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="4c4c2-186">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-186">Click **Save**.</span></span>

6. <span data-ttu-id="4c4c2-187">[アクセス許可 **] ウィンドウで、[** 高度なアクセス許可 **の設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="4c4c2-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span><span class="sxs-lookup"><span data-stu-id="4c4c2-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="4c4c2-189">**[ユーザーとグループ]** で、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="4c4c2-190">**[共有]** ダイアログ ボックスで、サイト メンバーのアクセス グループの名前を入力し、それを選択してから、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="4c4c2-191">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="4c4c2-192">Click **\<site name> Owners** in the list.</span><span class="sxs-lookup"><span data-stu-id="4c4c2-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="4c4c2-193">**[ユーザーとグループ]** で、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="4c4c2-194">**[共有]** ダイアログ ボックスで、サイト管理者のアクセス グループの名前を入力し、それを選択してから、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="4c4c2-195">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="4c4c2-196">Click **\<site name> Visitors** in the list.</span><span class="sxs-lookup"><span data-stu-id="4c4c2-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="4c4c2-197">**[ユーザーとグループ]** で、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="4c4c2-198">**[共有]** ダイアログ ボックスで、サイト ビューアーのアクセス グループの名前を入力し、それを選択してから、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="4c4c2-199">ブラウザーの **[アクセス権]** タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="4c4c2-200">これらのアクセス権の設定の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="4c4c2-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span><span class="sxs-lookup"><span data-stu-id="4c4c2-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="4c4c2-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span><span class="sxs-lookup"><span data-stu-id="4c4c2-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="4c4c2-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span><span class="sxs-lookup"><span data-stu-id="4c4c2-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="4c4c2-204">メンバーが他のメンバーを招待したり、メンバー以外のユーザーがアクセス権を要求したりする機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="4c4c2-205">以下に示すのができ上がった構成で、この構成にはユーザー アカウントと Azure AD グループが設定された 3 つのアクセス グループを使用するように構成されたサイト用の 3 つの SharePoint グループ含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![アクセス グループおよびユーザー アカウントが設定された、独立した SharePoint Online サイトの最終的な構成。](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="4c4c2-207">いずれかのアクセス グループのグループ メンバーシップを介して、サイトのメンバーとともにサイトのリソースを使用して共同作業を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="4c4c2-208">次の手順</span><span class="sxs-lookup"><span data-stu-id="4c4c2-208">Next step</span></span>

<span data-ttu-id="4c4c2-209">サイト アクセス グループ メンバーシップを変更したり、カスタム アクセス許可を持つドキュメント フォルダーを作成したりする必要がある場合は、「[分離した SharePoint Online チーム サイトの管理](manage-an-isolated-sharepoint-online-team-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c4c2-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c4c2-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c4c2-210">See Also</span></span>

[<span data-ttu-id="4c4c2-211">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="4c4c2-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="4c4c2-212">分離した SharePoint Online チーム サイトの設計</span><span class="sxs-lookup"><span data-stu-id="4c4c2-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="4c4c2-213">分離した SharePoint Online チーム サイトの管理</span><span class="sxs-lookup"><span data-stu-id="4c4c2-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
