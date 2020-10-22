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
ms.openlocfilehash: 1486c86172cd34e6e88f8cd02d003967518bcdb7
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655949"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="9d7b6-103">PowerShell を使用して Microsoft 365 ユーザーアカウントに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9d7b6-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="9d7b6-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="9d7b6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9d7b6-105">Microsoft 365 の PowerShell を使用して、管理者の役割をユーザーアカウントにすばやく簡単に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-105">You can quickly and easily assign admin roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="9d7b6-106">Microsoft 365 管理センターで[管理者の役割をユーザーアカウントに割り当てる方法について説明](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-106">[Learn how to assign admin roles to user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="9d7b6-107">その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9d7b6-108">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="9d7b6-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9d7b6-109">最初に、全体管理者アカウントを使用して [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="9d7b6-p102">次に、ロールに追加するユーザー アカウントのサインイン名を判別します (例: fredsm@contoso.com)。サインイン名はユーザー プリンシパル名 (UPN) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-p102">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com). This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="9d7b6-112">次に、管理者ロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-112">Next, determine the name of the admin role.</span></span> <span data-ttu-id="9d7b6-113">[Azure Active Directoryでこの管理者ロールのアクセス許可の一覧](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-113">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="9d7b6-114">この記事のメモに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="9d7b6-115">Azure AD PowerShellでは一部のロール名が異なります。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-115">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="9d7b6-116">たとえば、Microsoft 365管理センターの "SharePoint Administrator"ロールは、Azure AD PowerShellでは "SharePoint Service Administrator"という異なった名前がついています。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-116">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="9d7b6-117">次に、サインイン名とロール名を入力し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-117">Next, fill in the sign-in and role names and run these commands.</span></span>
  
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

<span data-ttu-id="9d7b6-118">以下は、SharePoint サービス管理者の役割を belindan@contoso.com アカウントに割り当てる、完成したコマンドセットの例です。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-118">Here is an example of a completed command set that assigns the SharePoint Service Administrator admin role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="9d7b6-119">特定の管理者の役割についてユーザー名の一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9d7b6-120">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="9d7b6-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9d7b6-121">最初に、全体管理者アカウントを使用して [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="9d7b6-122">単一ロールの変更の場合</span><span class="sxs-lookup"><span data-stu-id="9d7b6-122">For a single role change</span></span>

<span data-ttu-id="9d7b6-123">特定のユーザーアカウントの最も一般的な方法は、その表示名または電子メール名 (サインイン名またはユーザープリンシパル名 (UPN)) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-123">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="9d7b6-124">ユーザーアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="9d7b6-124">Display names of user accounts</span></span>

<span data-ttu-id="9d7b6-125">ユーザーアカウントの表示名の処理に使用する場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-125">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="9d7b6-126">構成するユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-126">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="9d7b6-p105">ユーザー アカウントを指定するには、その表示名を判別する必要があります。アカウントの完全な一覧を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-p105">To specify the user account, you must determine its Display Name. To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="9d7b6-p106">このコマンドにより、ユーザー アカウントの表示名の一覧が、表示名順に並び替えられて、一度に 1 画面ずつ示されます。 **Where** コマンドレットを使用すると、一覧をフィルター処理して、出力するセットを小さくできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-p106">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time. You can filter the list to a smaller set by using the **Where** cmdlet. Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="9d7b6-132">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-132">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9d7b6-133">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-133">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="9d7b6-134">このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="9d7b6-135">割り当てるロール。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-135">The role you want to assign.</span></span>
    
    <span data-ttu-id="9d7b6-136">ユーザーアカウントに割り当てることができる利用可能な管理者の役割の一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="9d7b6-137">アカウントの表示名と管理者の役割の名前を特定したら、次のコマンドを使用してアカウントに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-137">Once you have determined the Display Name of the account and the Name of the admin role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="9d7b6-138">コマンドをコピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-138">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="9d7b6-139">**$DispName**変数と **$roleName**変数については、説明テキストをその値に置き換え、 \< and > 文字を削除して、引用符のままにします。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-139">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="9d7b6-140">変更された行をコピーして、windows PowerShell 用 Windows Azure Active Directory モジュールウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-140">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="9d7b6-141">または、Windows PowerShell 統合スクリプト環境 (ISE) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-141">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="9d7b6-142">コマンド セットの完成例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-142">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="9d7b6-143">ユーザーアカウントのサインイン名</span><span class="sxs-lookup"><span data-stu-id="9d7b6-143">Sign-in names of user accounts</span></span>

<span data-ttu-id="9d7b6-144">ユーザーアカウントのサインイン名または Upn を使用する場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-144">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="9d7b6-145">ユーザーアカウントの UPN。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-145">The user account's UPN.</span></span>
    
    <span data-ttu-id="9d7b6-146">UPN がまだわからない場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-146">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="9d7b6-147">このコマンドは、UPN で並べ替えて、一度に1画面ずつ、ユーザーアカウントの UPN を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-147">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="9d7b6-148">**Where** コマンドレットを使用すると、一覧をフィルター処理して、出力するセットを小さくできます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-148">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="9d7b6-149">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-149">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="9d7b6-150">このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-150">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="9d7b6-151">割り当てるロール。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-151">The role you want to assign.</span></span>
    
    <span data-ttu-id="9d7b6-152">ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-152">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="9d7b6-153">アカウントの UPN と役割の名前を取得したら、次のコマンドを使用してアカウントに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-153">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="9d7b6-154">コマンドをコピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-154">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="9d7b6-155">**$UpnName**変数と **$roleName**変数については、説明テキストをその値に置き換え、 \< and > 文字を削除して、引用符のままにします。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-155">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="9d7b6-156">変更された行をコピーして、windows PowerShell 用 Windows Azure Active Directory モジュールウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-156">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="9d7b6-157">または、Windows PowerShell ISE を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-157">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="9d7b6-158">コマンド セットの完成例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-158">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="9d7b6-159">複数の役割の変更</span><span class="sxs-lookup"><span data-stu-id="9d7b6-159">Multiple role changes</span></span>

<span data-ttu-id="9d7b6-160">複数の役割の変更については、次のことを決定します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-160">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="9d7b6-161">構成するユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-161">Which user accounts that you want to configure.</span></span> <span data-ttu-id="9d7b6-162">前のセクションの方法を使用して、表示名または Upn のセットを収集できます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-162">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="9d7b6-163">各ユーザー アカウントに割り当てるロール。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-163">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="9d7b6-164">ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-164">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="9d7b6-165">次に、[表示名] または [UPN] および [役割名] フィールドを含むコンマ区切り値 (CSV) テキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-165">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="9d7b6-166">これは、Microsoft Excel で簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-166">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="9d7b6-167">表示名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-167">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="9d7b6-168">その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-168">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="9d7b6-169">次に、Upn の例を示します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-169">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="9d7b6-170">その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d7b6-170">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="9d7b6-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d7b6-171">See also</span></span>

- [<span data-ttu-id="9d7b6-172">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="9d7b6-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="9d7b6-173">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="9d7b6-173">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="9d7b6-174">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="9d7b6-174">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
