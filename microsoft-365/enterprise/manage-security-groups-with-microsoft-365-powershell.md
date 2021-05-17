---
title: PowerShell を使用してセキュリティ グループを管理する
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
description: PowerShell を使用してセキュリティ グループを管理する方法について説明します。
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909504"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="aece6-103">PowerShell を使用してセキュリティ グループを管理する</span><span class="sxs-lookup"><span data-stu-id="aece6-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="aece6-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="aece6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="aece6-105">PowerShell を使用して、Microsoft 365管理センターの代わりにMicrosoft 365グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="aece6-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="aece6-106">この記事では、設定の一覧、作成、変更、およびセキュリティ グループの削除について説明します。</span><span class="sxs-lookup"><span data-stu-id="aece6-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="aece6-107">この記事のコマンド ブロックで変数値を指定する必要がある場合は、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="aece6-108">コマンド ブロックをクリップボードにコピーし、コマンド ブロックメモ帳 PowerShell 統合スクリプト環境 (ISE) に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="aece6-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="aece6-109">変数の値を入力し、"<" 文字と ">" 文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="aece6-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="aece6-110">PowerShell ウィンドウまたは PowerShell ISE でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aece6-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="aece6-111">「セキュリティ [グループ メンバーシップを維持して PowerShell](maintain-group-membership-with-microsoft-365-powershell.md) でグループ メンバーシップを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aece6-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="aece6-112">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="aece6-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="aece6-113">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="aece6-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="aece6-114">グループを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="aece6-114">List your groups</span></span>

<span data-ttu-id="aece6-115">このコマンドを使用して、すべてのグループを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="aece6-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="aece6-116">特定のグループの設定を表示名で表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="aece6-117">新しいグループを作成する</span><span class="sxs-lookup"><span data-stu-id="aece6-117">Create a new group</span></span>

<span data-ttu-id="aece6-118">新しいセキュリティ グループを作成するには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="aece6-119">グループの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="aece6-119">Change the settings on a group</span></span>

<span data-ttu-id="aece6-120">これらのコマンドを使用して、グループの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="aece6-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="aece6-121">次に [、Set-AzureADGroup の記事を使用](/powershell/module/azuread/set-azureadgroup) して、設定を変更する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="aece6-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="aece6-122">セキュリティ グループを削除する</span><span class="sxs-lookup"><span data-stu-id="aece6-122">Remove a security group</span></span>

<span data-ttu-id="aece6-123">セキュリティ グループを削除するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="aece6-124">セキュリティ グループの所有者を管理する</span><span class="sxs-lookup"><span data-stu-id="aece6-124">Manage the owners of a security group</span></span>

<span data-ttu-id="aece6-125">セキュリティ グループの現在の所有者を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="aece6-126">次のコマンドを使用して、セキュリティ グループの現在の所有者にユーザー プリンシパル名 **(UPN)** でユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="aece6-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="aece6-127">これらのコマンドを使用して、ユーザー アカウントを表示名でセキュリティ **グループの** 現在の所有者に追加します。</span><span class="sxs-lookup"><span data-stu-id="aece6-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="aece6-128">これらのコマンドを使用して **、UPN** によってセキュリティ グループの現在の所有者に対してユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="aece6-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="aece6-129">次のコマンドを使用して、セキュリティ グループの現在の所有者に **表示名で** ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="aece6-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="aece6-130">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="aece6-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="aece6-131">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aece6-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="aece6-132">グループを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="aece6-132">List your groups</span></span>

<span data-ttu-id="aece6-133">このコマンドを使用して、すべてのグループを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="aece6-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="aece6-134">特定のグループの設定を表示名で表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="aece6-135">新しいグループを作成する</span><span class="sxs-lookup"><span data-stu-id="aece6-135">Create a new group</span></span>

<span data-ttu-id="aece6-136">新しいセキュリティ グループを作成するには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="aece6-137">グループの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="aece6-137">Change the settings on a group</span></span>

<span data-ttu-id="aece6-138">これらのコマンドを使用して、グループの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="aece6-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="aece6-139">次に [、Set-MsolGroup の記事を使用](/powershell/module/msonline/set-msolgroup) して、設定を変更する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="aece6-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="aece6-140">セキュリティ グループを削除する</span><span class="sxs-lookup"><span data-stu-id="aece6-140">Remove a security group</span></span>

<span data-ttu-id="aece6-141">セキュリティ グループを削除するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aece6-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="aece6-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="aece6-142">See also</span></span>

[<span data-ttu-id="aece6-143">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="aece6-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="aece6-144">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="aece6-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="aece6-145">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="aece6-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)