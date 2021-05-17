---
title: PowerShell を使用してユーザー Microsoft 365に役割を割り当てる
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: この記事では、管理者ロールをユーザー アカウントに割り当てるMicrosoft 365 PowerShell を使用する方法について説明します。
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905382"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="31635-103">PowerShell を使用して管理者の役割Microsoft 365ユーザー アカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="31635-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="31635-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="31635-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="31635-105">PowerShell を使用してユーザー アカウントに役割を簡単に割り当Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="31635-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="31635-106">管理者の役割を[管理センターで](../admin/add-users/assign-admin-roles.md)ユーザー アカウントに割り当てるMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="31635-106">Learn how to  [assign admin roles](../admin/add-users/assign-admin-roles.md) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="31635-107">その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="31635-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="31635-108">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="31635-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="31635-109">最初に、グローバル管理者アカウントを使用してテナント[にMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="31635-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="31635-110">次に、役割に追加するユーザー アカウントのサインイン名を特定します (例: fredsm \@ contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="31635-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="31635-111">これは、ユーザー プリンシパル名 (UPN) とも呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="31635-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="31635-112">次に、ロールの名前を決めます。</span><span class="sxs-lookup"><span data-stu-id="31635-112">Next, determine the name of the role.</span></span> <span data-ttu-id="31635-113">「[管理者ロールのアクセス許可」を参照Azure Active Directory。](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="31635-113">See [administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="31635-114">この記事のメモに注意してください。</span><span class="sxs-lookup"><span data-stu-id="31635-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="31635-115">一部の役割名は、Azure Active Directory (Azure AD) PowerShell で異なります。</span><span class="sxs-lookup"><span data-stu-id="31635-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="31635-116">たとえば、管理者センター SharePoint *管理者* ロールは、Azure Microsoft 365 PowerShell SharePointサービス管理者ADです。</span><span class="sxs-lookup"><span data-stu-id="31635-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="31635-117">次に、サインイン名と役割名を入力し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31635-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="31635-118">次に、サービス管理者の役割を *belindan \@* アカウントに割り当SharePoint完了したコマンド セット contoso.com 示します。</span><span class="sxs-lookup"><span data-stu-id="31635-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="31635-119">特定の管理者ロールのユーザー名の一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31635-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="31635-120">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="31635-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="31635-121">最初に、グローバル管理者アカウントを使用してテナント[にMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="31635-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="31635-122">単一ロールの変更の場合</span><span class="sxs-lookup"><span data-stu-id="31635-122">For a single role change</span></span>

<span data-ttu-id="31635-123">ユーザー アカウントを指定する最も一般的な方法は、表示名または電子メール名 (サインイン名またはユーザー プリンシパル名 (UPN) とも呼ばれる) を使用します。</span><span class="sxs-lookup"><span data-stu-id="31635-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="31635-124">ユーザー アカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="31635-124">Display names of user accounts</span></span>

<span data-ttu-id="31635-125">ユーザー アカウントの表示名の操作に使用する場合は、次の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="31635-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="31635-126">構成するユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="31635-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="31635-127">ユーザー アカウントを指定するには、その表示名を判別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31635-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="31635-128">アカウントの完全な一覧を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31635-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="31635-129">このコマンドにより、ユーザー アカウントの表示名の一覧が、表示名順に並び替えられて、一度に 1 画面ずつ示されます。</span><span class="sxs-lookup"><span data-stu-id="31635-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="31635-130">**Where** コマンドレットを使用すると、一覧をフィルター処理して、出力するセットを小さくできます。</span><span class="sxs-lookup"><span data-stu-id="31635-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="31635-131">次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="31635-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="31635-132">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="31635-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="31635-133">これらのコマンドレットは、Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="31635-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="31635-134">このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="31635-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="31635-135">割り当てる役割</span><span class="sxs-lookup"><span data-stu-id="31635-135">The role you want to assign</span></span>
    
    <span data-ttu-id="31635-136">ユーザー アカウントに割り当て可能な管理者ロールの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31635-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="31635-137">アカウントの表示名と役割の名前を確認した後、次のコマンドを使用して役割をアカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="31635-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="31635-138">コマンドを別のメモ帳。</span><span class="sxs-lookup"><span data-stu-id="31635-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="31635-139">変数と *$dispName* 変数 *$roleName、* 説明テキストを値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="31635-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="31635-140">文字を \< and > 削除しますが、二重引用符は保持します。</span><span class="sxs-lookup"><span data-stu-id="31635-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="31635-141">変更した行を [モジュール] ウィンドウMicrosoft Azure Active Directoryに貼りWindows PowerShellして実行します。</span><span class="sxs-lookup"><span data-stu-id="31635-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="31635-142">または、統合スクリプト環境 (ISE) Windows PowerShellを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="31635-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="31635-143">完了したコマンド セットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31635-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="31635-144">ユーザー アカウントのサインイン名</span><span class="sxs-lookup"><span data-stu-id="31635-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="31635-145">ユーザー アカウントのサインイン名または UPN の操作に使用する場合は、次の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="31635-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="31635-146">ユーザー アカウントの UPN</span><span class="sxs-lookup"><span data-stu-id="31635-146">The user account's UPN</span></span>
    
    <span data-ttu-id="31635-147">UPN が分からない場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31635-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="31635-148">このコマンドは、ユーザー アカウントの UPN を UPN で並べ替え、一度に 1 つの画面で一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="31635-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="31635-149">Where コマンドレットを使用 **して** リストをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="31635-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="31635-150">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="31635-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="31635-151">このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="31635-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="31635-152">割り当てる役割</span><span class="sxs-lookup"><span data-stu-id="31635-152">The role you want to assign</span></span>
    
    <span data-ttu-id="31635-153">ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31635-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="31635-154">アカウントの UPN と役割の名前を確認した後、次のコマンドを使用して役割をアカウントに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="31635-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="31635-155">コマンドをコピーし、コマンドに貼りメモ帳。</span><span class="sxs-lookup"><span data-stu-id="31635-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="31635-156">変数の **$upnName** 変数 **$roleName** します。</span><span class="sxs-lookup"><span data-stu-id="31635-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="31635-157">説明テキストを値に置き換える。</span><span class="sxs-lookup"><span data-stu-id="31635-157">Replace the description text with their values.</span></span> <span data-ttu-id="31635-158">文字を \< and > 削除しますが、二重引用符は保持します。</span><span class="sxs-lookup"><span data-stu-id="31635-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="31635-159">変更した行を [モジュール] ウィンドウMicrosoft Azure Active Directoryに貼りWindows PowerShell実行します。</span><span class="sxs-lookup"><span data-stu-id="31635-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="31635-160">または、ISE のWindows PowerShell使用できます。</span><span class="sxs-lookup"><span data-stu-id="31635-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="31635-161">完了したコマンド セットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31635-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="31635-162">複数の役割の変更</span><span class="sxs-lookup"><span data-stu-id="31635-162">Multiple role changes</span></span>

<span data-ttu-id="31635-163">複数の役割を変更する場合は、次の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="31635-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="31635-164">構成するユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="31635-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="31635-165">前のセクションのメソッドを使用して、表示名または UPN のセットを収集できます。</span><span class="sxs-lookup"><span data-stu-id="31635-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="31635-166">各ユーザー アカウントに割り当てるロール。</span><span class="sxs-lookup"><span data-stu-id="31635-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="31635-167">ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31635-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="31635-168">次に、表示名または UPN フィールドと役割名フィールドを持つコンマ区切り値 (CSV) テキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31635-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="31635-169">この操作は、次の手順で簡単Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="31635-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="31635-170">表示名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31635-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="31635-171">その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31635-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="31635-172">UPN の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31635-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="31635-173">その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31635-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="31635-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="31635-174">See also</span></span>

- [<span data-ttu-id="31635-175">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="31635-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="31635-176">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="31635-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="31635-177">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="31635-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)