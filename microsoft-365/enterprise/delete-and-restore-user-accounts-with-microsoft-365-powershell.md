---
title: PowerShell を使用して Microsoft 365 ユーザー アカウントを削除する
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: PowerShell でさまざまなモジュールを使用して Microsoft 365 ユーザー アカウントを削除する方法について説明します。
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919142"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="d51a0-103">PowerShell を使用して Microsoft 365 ユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="d51a0-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="d51a0-104">PowerShell for Microsoft 365 を使用すると、ユーザー アカウントを削除および復元できます。</span><span class="sxs-lookup"><span data-stu-id="d51a0-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="d51a0-105">Microsoft 365 管理 [センターを](../admin/add-users/restore-user.md) 使用してユーザー アカウントを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-105">Learn how to [restore a user account](../admin/add-users/restore-user.md) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="d51a0-106">その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="d51a0-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d51a0-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="d51a0-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d51a0-108">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="d51a0-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="d51a0-109">接続後、次の構文を使用して個々のユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="d51a0-110">次の使用例は、ユーザー アカウント *fabricec を削除 \@ litwareinc.com。*</span><span class="sxs-lookup"><span data-stu-id="d51a0-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="d51a0-111">**Remove-AzureADUser** コマンドレットの *-ObjectID* パラメーターは、アカウントのサインイン名 (ユーザー プリンシパル名またはアカウントのオブジェクト ID とも呼ばれる) を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="d51a0-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="d51a0-112">ユーザーの名前に基づいてアカウント名を表示するには、以下のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="d51a0-113">次の使用例は、ユーザー *Caleb Sills のアカウント名を表示します*。</span><span class="sxs-lookup"><span data-stu-id="d51a0-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="d51a0-114">ユーザーの表示名に基づいてアカウントを削除するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d51a0-115">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="d51a0-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d51a0-116">Microsoft Azure Active Directory モジュールを使用してユーザー アカウントを削除Windows PowerShellアカウントは完全に削除されません。</span><span class="sxs-lookup"><span data-stu-id="d51a0-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="d51a0-117">削除されたユーザー アカウントは 30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="d51a0-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="d51a0-118">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d51a0-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="d51a0-119">ユーザー アカウントを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="d51a0-120">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d51a0-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="d51a0-121">これらのコマンドレットは、Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="d51a0-122">次の使用例は、ユーザー アカウントを *削除 BelindaN@litwareinc.com。*</span><span class="sxs-lookup"><span data-stu-id="d51a0-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="d51a0-123">削除されたユーザー アカウントを 30 日間の猶予期間内に復元するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="d51a0-124">次の使用例は、削除されたアカウント BelindaN を復元 *\@ litwareinc.com。*</span><span class="sxs-lookup"><span data-stu-id="d51a0-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="d51a0-125">復元できる削除されたユーザーの一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="d51a0-126">ユーザー アカウントの元のユーザー プリンシパル名を別のアカウントで使用する場合は _、UserPrincipalName_ ではなく _NewUserPrincipalName_ パラメーターを使用して、ユーザー アカウントを復元するときに別のユーザー プリンシパル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d51a0-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="d51a0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d51a0-127">See also</span></span>

[<span data-ttu-id="d51a0-128">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="d51a0-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d51a0-129">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="d51a0-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d51a0-130">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="d51a0-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)