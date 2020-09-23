---
title: PowerShell を使用して Microsoft 365 グループメンバーシップを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
description: PowerShell を使用して Microsoft 365 グループのメンバーシップを管理する方法について説明します。
ms.openlocfilehash: 464ebcebe87fcd7ce081de85e75acf76cd6d5a46
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235632"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="b4fa2-103">PowerShell を使用して Microsoft 365 グループメンバーシップを管理する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="b4fa2-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="b4fa2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b4fa2-105">Microsoft 365 の PowerShell を microsoft 365 管理センターの代わりとして使用して、Microsoft 365 のグループメンバーシップを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

> [!TIP]
> <span data-ttu-id="b4fa2-106">ユーザーアカウントとグループ名を指定して、すぐに実行できる PowerShell コマンドを生成するには、この [グループメンテナンス Microsoft Excel ブック](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-106">To generate ready-to-run PowerShell commands by specifying user account and group names, use this [group maintenance Microsoft Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span></span> 

>[!Note]
><span data-ttu-id="b4fa2-107">Microsoft 365 グループメンバーシップを Microsoft 365 管理センターで[管理する方法について説明](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-107">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="b4fa2-108">その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-108">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b4fa2-109">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-109">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="b4fa2-110">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="b4fa2-111">ユーザーアカウントをグループのメンバーとして追加または削除する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-111">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="b4fa2-112">**Upn を使用してユーザーアカウントを追加するに**は、ユーザーアカウントのユーザープリンシパル名 (UPN) とグループ表示名を入力し、"<" と ">" 文字を削除して、これらのコマンドを powershell ウィンドウまたは Powershell 統合スクリプト環境 (ISE) で実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-112">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b4fa2-113">**表示名を使用してユーザーアカウントを追加するに**は、ユーザーアカウントの表示名 (例: ベルギー Inda newman) とグループの表示名を入力し、powershell ウィンドウまたは powershell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-113">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b4fa2-114">**UPN によってユーザーアカウントを削除するに**は、ユーザーアカウントの upn (例: belindan@contoso.com) とグループの表示名を入力し、powershell ウィンドウまたは powershell ISE で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-114">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b4fa2-115">**表示名を使用してユーザーアカウントを削除するに**は、ユーザーアカウントの表示名 (例: ベルギー Inda newman) とグループの表示名を入力し、powershell ウィンドウまたは powershell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-115">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="b4fa2-116">グループのメンバーとしてグループを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-116">Add or remove groups as members of a group</span></span>

<span data-ttu-id="b4fa2-117">セキュリティグループには、他のグループをメンバーとして含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-117">Security groups can contain other groups as members.</span></span> <span data-ttu-id="b4fa2-118">ただし、Microsoft 365 グループはできません。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-118">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="b4fa2-119">このセクションでは、セキュリティグループに対してのみグループを追加または削除するための PowerShell コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-119">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="b4fa2-120">**表示名でグループを追加するに**は、追加するグループの表示名と、メンバーグループを含むグループの表示名を入力して、powershell ウィンドウまたは powershell ISE で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-120">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b4fa2-121">**表示名によってグループを削除するに**は、削除するグループの表示名と、メンバーグループを含むグループの表示名を入力して、powershell ウィンドウまたは powershell ISE で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-121">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b4fa2-122">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-122">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b4fa2-123">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-123">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="b4fa2-124">ユーザーアカウントをグループのメンバーとして追加または削除する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-124">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="b4fa2-125">**Upn でユーザーアカウントを追加するに**は、ユーザーアカウントのユーザープリンシパル名 (UPN) (例: belindan@contoso.com) とグループの表示名を入力して、"<" と ">" 文字を削除し、これらのコマンドを powershell ウィンドウまたは powershell ISE で実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-125">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b4fa2-126">**表示名を使用してユーザーアカウントを追加するに**は、ユーザーアカウントの表示名 (例: ベルギー Inda newman) とグループの表示名を入力し、powershell ウィンドウまたは powershell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-126">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b4fa2-127">**UPN によってユーザーアカウントを削除するに**は、ユーザーアカウントの upn (例: belindan@contoso.com) とグループの表示名を入力し、powershell ウィンドウまたは powershell ISE で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-127">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b4fa2-128">**表示名を使用してユーザーアカウントを削除するに**は、ユーザーアカウントの表示名 (例: ベルギー Inda newman) とグループの表示名を入力し、powershell ウィンドウまたは powershell ISE でこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-128">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="b4fa2-129">グループのメンバーとしてグループを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-129">Add or remove groups as members of a group</span></span>

<span data-ttu-id="b4fa2-130">セキュリティグループには、他のグループをメンバーとして含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-130">Security groups can contain other groups as members.</span></span> <span data-ttu-id="b4fa2-131">ただし、Microsoft 365 グループはできません。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-131">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="b4fa2-132">このセクションでは、セキュリティグループに対してのみグループを追加または削除するための PowerShell コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-132">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="b4fa2-133">**表示名でグループを追加するに**は、追加するグループの表示名と、メンバーグループを含むグループの表示名を入力して、powershell ウィンドウまたは powershell ISE で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-133">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="b4fa2-134">**表示名によってグループを削除するに**は、削除するグループの表示名と、メンバーグループを含むグループの表示名を入力して、powershell ウィンドウまたは powershell ISE で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4fa2-134">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="b4fa2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4fa2-135">See also</span></span>

[<span data-ttu-id="b4fa2-136">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-136">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b4fa2-137">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-137">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b4fa2-138">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b4fa2-138">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

