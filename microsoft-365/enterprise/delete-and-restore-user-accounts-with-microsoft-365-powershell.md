---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントを削除する
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
description: PowerShell で各種モジュールを使用して、Microsoft 365 ユーザーアカウントを削除する方法について説明します。
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754542"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="735c0-103">PowerShell を使用して Microsoft 365 ユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="735c0-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="735c0-104">Microsoft 365 の PowerShell を使用して、ユーザーアカウントを削除および復元することができます。</span><span class="sxs-lookup"><span data-stu-id="735c0-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="735c0-105">Microsoft 365 管理センターを使用して [ユーザーアカウントを復元](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="735c0-105">Learn how to [restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="735c0-106">その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="735c0-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="735c0-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="735c0-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="735c0-108">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="735c0-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="735c0-109">接続した後、次の構文を使用して個々のユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="735c0-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="735c0-110">この例では、ユーザーアカウント *fabricec \@ litwareinc.com*を削除します。</span><span class="sxs-lookup"><span data-stu-id="735c0-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="735c0-111">**Set-azureaduser**コマンドレットの *-ObjectID*パラメーターは、アカウントのサインイン名 (ユーザープリンシパル名またはアカウントのオブジェクト ID とも呼ばれます) のいずれかを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="735c0-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="735c0-112">ユーザーの名前に基づいてアカウント名を表示するには、以下のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="735c0-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="735c0-113">次の使用例は、ユーザー *Caleb/ls*のアカウント名を表示します。</span><span class="sxs-lookup"><span data-stu-id="735c0-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="735c0-114">ユーザーの表示名に基づいてアカウントを削除するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="735c0-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="735c0-115">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="735c0-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="735c0-116">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用してユーザーアカウントを削除しても、そのアカウントは完全に削除されません。</span><span class="sxs-lookup"><span data-stu-id="735c0-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="735c0-117">削除されたユーザー アカウントは 30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="735c0-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="735c0-118">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="735c0-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="735c0-119">ユーザー アカウントを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="735c0-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="735c0-120">PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="735c0-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="735c0-121">これらのコマンドレットを Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="735c0-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="735c0-122">この例では、ユーザーアカウント *BelindaN@litwareinc.com*を削除します。</span><span class="sxs-lookup"><span data-stu-id="735c0-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="735c0-123">削除されたユーザー アカウントを 30 日間の猶予期間内に復元するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="735c0-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="735c0-124">この例では、削除されたアカウントの \* \@ litwareinc.com\*を復元します。</span><span class="sxs-lookup"><span data-stu-id="735c0-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="735c0-125">復元できる削除されたユーザーの一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="735c0-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="735c0-126">ユーザーアカウントの元のユーザープリンシパル名が別のアカウントで使用されている場合、ユーザーアカウントを復元するときに別のユーザープリンシパル名を指定するには、 _UserPrincipalName_の代わりに_newuserprincipalname_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="735c0-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="735c0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="735c0-127">See also</span></span>

[<span data-ttu-id="735c0-128">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="735c0-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="735c0-129">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="735c0-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="735c0-130">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="735c0-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
