---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントに役割を割り当てる
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
description: この記事では、Microsoft 365 の PowerShell を使用して、ユーザーアカウントに管理者の役割を割り当てる方法について説明します。
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754200"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="60170-103">PowerShell を使用して Microsoft 365 ユーザーアカウントに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="60170-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="60170-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="60170-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="60170-105">Microsoft 365 の PowerShell を使用して、ユーザーアカウントに役割を簡単に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="60170-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="60170-106">Microsoft 365 管理センターで  [管理者の役割](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) をユーザーアカウントに割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="60170-106">Learn how to  [assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="60170-107">その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60170-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="60170-108">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="60170-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="60170-109">最初に、全体管理者アカウントを使用し [て、Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="60170-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="60170-110">次に、役割に追加するユーザーアカウントのサインイン名を指定します (例: fredsm \@ contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="60170-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="60170-111">これは、ユーザープリンシパル名 (UPN) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="60170-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="60170-112">次に、ロールの名前を決めます。</span><span class="sxs-lookup"><span data-stu-id="60170-112">Next, determine the name of the role.</span></span> <span data-ttu-id="60170-113">「 [Azure Active Directory の管理者役割のアクセス許可」を](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)参照してください。</span><span class="sxs-lookup"><span data-stu-id="60170-113">See [administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="60170-114">この記事のメモに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60170-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="60170-115">Azure Active Directory (Azure AD) PowerShell では、一部の役割名が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60170-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="60170-116">たとえば、Microsoft 365 管理センターの *Sharepoint 管理者* の役割は、Azure AD PowerShell の *Sharepoint サービス管理者* です。</span><span class="sxs-lookup"><span data-stu-id="60170-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="60170-117">次に、サインイン名とロール名を入力して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="60170-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
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

<span data-ttu-id="60170-118">次に、SharePoint サービス管理者の役割を *ベルギーの \@ contoso.com* アカウントに割り当てる、完成したコマンドセットの例を示します。</span><span class="sxs-lookup"><span data-stu-id="60170-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
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

<span data-ttu-id="60170-119">特定の管理者の役割についてユーザー名の一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60170-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="60170-120">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="60170-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="60170-121">最初に、全体管理者アカウントを使用し [て、Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="60170-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="60170-122">単一ロールの変更の場合</span><span class="sxs-lookup"><span data-stu-id="60170-122">For a single role change</span></span>

<span data-ttu-id="60170-123">ユーザーアカウントを指定する最も一般的な方法は、表示名または電子メール名 (サインイン名またはユーザープリンシパル名 (UPN) とも呼ばれる) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="60170-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="60170-124">ユーザーアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="60170-124">Display names of user accounts</span></span>

<span data-ttu-id="60170-125">ユーザーアカウントの表示名を使用して作業している場合は、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="60170-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="60170-126">構成するユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="60170-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="60170-127">ユーザー アカウントを指定するには、その表示名を判別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60170-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="60170-128">アカウントの完全な一覧を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60170-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="60170-129">このコマンドにより、ユーザー アカウントの表示名の一覧が、表示名順に並び替えられて、一度に 1 画面ずつ示されます。</span><span class="sxs-lookup"><span data-stu-id="60170-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="60170-130">**Where** コマンドレットを使用すると、一覧をフィルター処理して、出力するセットを小さくできます。</span><span class="sxs-lookup"><span data-stu-id="60170-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="60170-131">次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="60170-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="60170-132">PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="60170-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="60170-133">これらのコマンドレットを Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="60170-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="60170-134">このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="60170-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="60170-135">割り当てる役割</span><span class="sxs-lookup"><span data-stu-id="60170-135">The role you want to assign</span></span>
    
    <span data-ttu-id="60170-136">ユーザーアカウントに割り当てることができる利用可能な管理者の役割の一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60170-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="60170-137">アカウントの表示名と役割の名前を特定したら、次のコマンドを使用してアカウントに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="60170-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="60170-138">コマンドをメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="60170-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="60170-139">*$DispName*変数と *$roleName*変数については、説明テキストをその値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="60170-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="60170-140">文字を削除 \< and > しますが、引用符はそのままにします。</span><span class="sxs-lookup"><span data-stu-id="60170-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="60170-141">変更した行を Windows PowerShell 用 Microsoft Azure Active Directory モジュールウィンドウに貼り付けて、それらを実行します。</span><span class="sxs-lookup"><span data-stu-id="60170-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="60170-142">または、Windows PowerShell 統合スクリプト環境 (ISE) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="60170-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="60170-143">次に、完了したコマンドセットの例を示します。</span><span class="sxs-lookup"><span data-stu-id="60170-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="60170-144">ユーザーアカウントのサインイン名</span><span class="sxs-lookup"><span data-stu-id="60170-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="60170-145">ユーザーアカウントのサインイン名または Upn を使用して作業している場合は、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="60170-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="60170-146">ユーザーアカウントの UPN</span><span class="sxs-lookup"><span data-stu-id="60170-146">The user account's UPN</span></span>
    
    <span data-ttu-id="60170-147">UPN がわからない場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60170-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="60170-148">このコマンドは、UPN で並べ替えて、一度に1画面ずつ、ユーザーアカウントの UPN を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="60170-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="60170-149">**Where**コマンドレットを使用して、リストにフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="60170-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="60170-150">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="60170-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="60170-151">このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="60170-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="60170-152">割り当てる役割</span><span class="sxs-lookup"><span data-stu-id="60170-152">The role you want to assign</span></span>
    
    <span data-ttu-id="60170-153">ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60170-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="60170-154">アカウントの UPN と役割の名前を取得したら、次のコマンドを使用してアカウントに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="60170-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="60170-155">コマンドをコピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="60170-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="60170-156">**$UpnName**と **$roleName**変数の場合。</span><span class="sxs-lookup"><span data-stu-id="60170-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="60170-157">説明テキストをその値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="60170-157">Replace the description text with their values.</span></span> <span data-ttu-id="60170-158">文字を削除 \< and > しますが、引用符はそのままにします。</span><span class="sxs-lookup"><span data-stu-id="60170-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="60170-159">変更した行を Windows PowerShell 用 Microsoft Azure Active Directory モジュールウィンドウに貼り付けて、それらを実行します。</span><span class="sxs-lookup"><span data-stu-id="60170-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="60170-160">または、Windows PowerShell ISE を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="60170-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="60170-161">次に、完了したコマンドセットの例を示します。</span><span class="sxs-lookup"><span data-stu-id="60170-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="60170-162">複数の役割の変更</span><span class="sxs-lookup"><span data-stu-id="60170-162">Multiple role changes</span></span>

<span data-ttu-id="60170-163">複数の役割の変更については、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="60170-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="60170-164">構成するユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="60170-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="60170-165">前のセクションの方法を使用して、表示名または Upn のセットを収集できます。</span><span class="sxs-lookup"><span data-stu-id="60170-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="60170-166">各ユーザー アカウントに割り当てるロール。</span><span class="sxs-lookup"><span data-stu-id="60170-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="60170-167">ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60170-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="60170-168">次に、[表示名] または [UPN] および [役割名] フィールドを含むコンマ区切り値 (CSV) テキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="60170-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="60170-169">この操作は、Microsoft Excel で簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="60170-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="60170-170">表示名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="60170-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="60170-171">その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="60170-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="60170-172">次に、Upn の例を示します。</span><span class="sxs-lookup"><span data-stu-id="60170-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="60170-173">その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="60170-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="60170-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="60170-174">See also</span></span>

- [<span data-ttu-id="60170-175">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="60170-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="60170-176">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="60170-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="60170-177">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="60170-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
