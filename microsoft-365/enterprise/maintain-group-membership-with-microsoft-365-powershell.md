---
title: PowerShell を使用してセキュリティ グループ メンバーシップを維持する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell を使用してグループ内のメンバーシップを維持するMicrosoft 365します。
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909576"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="a0173-103">PowerShell を使用してセキュリティ グループ メンバーシップを維持する</span><span class="sxs-lookup"><span data-stu-id="a0173-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="a0173-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="a0173-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a0173-105">PowerShell を管理センター Microsoft 365代わりに使用して、Microsoft 365のセキュリティ グループ メンバーシップを維持Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a0173-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="a0173-106">[管理センターでグループ Microsoft 365メンバーシップを維持](../admin/create-groups/add-or-remove-members-from-groups.md)するMicrosoft 365について学習します。</span><span class="sxs-lookup"><span data-stu-id="a0173-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="a0173-107">その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="a0173-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a0173-108">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="a0173-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="a0173-109">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="a0173-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="a0173-110">グループのメンバーとしてユーザー アカウントを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="a0173-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="a0173-111">**UPN** でユーザー アカウントを追加するには、ユーザー アカウントのユーザー プリンシパル名 (UPN) (例: belindan@contoso.com) とセキュリティ グループの表示名を入力し、"<" 文字と ">" 文字を削除し、PowerShell ウィンドウまたは PowerShell 統合スクリプト環境 (ISE) でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a0173-112">表示名でユーザー アカウントを追加するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a0173-113">**UPN** でユーザー アカウントを削除するには、ユーザー アカウント UPN (例: belindan@contoso.com) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a0173-114">表示名でユーザー アカウントを削除するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="a0173-115">グループのメンバーとしてグループを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="a0173-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="a0173-116">セキュリティ グループには、他のグループをメンバーとして含めできます。</span><span class="sxs-lookup"><span data-stu-id="a0173-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="a0173-117">Microsoft 365グループは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a0173-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="a0173-118">このセクションには、セキュリティ グループのグループのみを追加または削除する PowerShell コマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0173-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="a0173-119">グループを表示名で追加するには、追加するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a0173-120">**グループ** を表示名で削除するには、削除するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a0173-121">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="a0173-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a0173-122">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a0173-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="a0173-123">グループのメンバーとしてユーザー アカウントを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="a0173-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="a0173-124">**UPN** でユーザー アカウントを追加するには、ユーザー アカウントのユーザー プリンシパル名 (UPN) (例: belindan@contoso.com) とグループ表示名を入力し、"<" 文字と ">" 文字を削除し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a0173-125">表示名でユーザー アカウントを追加するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a0173-126">**UPN** でユーザー アカウントを削除するには、ユーザー アカウント UPN (例: belindan@contoso.com) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a0173-127">表示名でユーザー アカウントを削除するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="a0173-128">グループのメンバーとしてグループを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="a0173-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="a0173-129">セキュリティ グループには、他のグループをメンバーとして含めできます。</span><span class="sxs-lookup"><span data-stu-id="a0173-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="a0173-130">Microsoft 365グループは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a0173-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="a0173-131">このセクションには、セキュリティ グループのグループのみを追加または削除する PowerShell コマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0173-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="a0173-132">グループを表示名で追加するには、追加するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="a0173-133">**グループ** を表示名で削除するには、削除するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0173-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="a0173-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0173-134">See also</span></span>

[<span data-ttu-id="a0173-135">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="a0173-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a0173-136">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="a0173-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a0173-137">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="a0173-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)