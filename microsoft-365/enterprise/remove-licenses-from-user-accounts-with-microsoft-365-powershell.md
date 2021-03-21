---
title: PowerShell を使用してユーザー アカウントから Microsoft 365 ライセンスを削除する
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: PowerShell を使用して、以前ユーザーに割り当てられた Microsoft 365 ライセンスを削除する方法について説明します。
ms.openlocfilehash: 9944d1ab056d109b6bf71a44fe01acef78ce1f14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920670"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="30cae-103">PowerShell を使用してユーザー アカウントから Microsoft 365 ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="30cae-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="30cae-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="30cae-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

>[!Note]
><span data-ttu-id="30cae-105">Microsoft 365 管理[センターを使用して](../admin/manage/remove-licenses-from-users.md)ユーザー アカウントからライセンスを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30cae-105">[Learn how to remove licenses from user accounts](../admin/manage/remove-licenses-from-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="30cae-106">その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="30cae-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="30cae-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="30cae-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="30cae-108">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="30cae-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="30cae-109">次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="30cae-109">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="30cae-110">次に、ライセンスを削除するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。</span><span class="sxs-lookup"><span data-stu-id="30cae-110">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="30cae-111">最後に、ユーザー サインインとライセンス プラン名を指定し、"<" 文字と ">" 文字を削除し、これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30cae-111">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="30cae-112">特定のユーザー アカウントのすべてのライセンスを削除するには、ユーザー サインイン名を指定し、"<" および ">" 文字を削除して、これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30cae-112">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="30cae-113">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="30cae-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="30cae-114">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="30cae-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="30cae-115">組織のライセンス プラン (**AccountSkuID**) 情報を表示する方法については、以下のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30cae-115">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="30cae-116">PowerShell でライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="30cae-116">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="30cae-117">PowerShell でアカウント ライセンスとサービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="30cae-117">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="30cae-118">_-All_ パラメーターなしで **Get-MsolUser** コマンドレットを使用する場合、最初の 500 個のアカウントだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="30cae-118">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="30cae-119">ユーザー アカウントからのライセンスの削除</span><span class="sxs-lookup"><span data-stu-id="30cae-119">Removing licenses from user accounts</span></span>

<span data-ttu-id="30cae-120">既存のユーザー アカウントからライセンスを削除するには、次の構文を使用します:</span><span class="sxs-lookup"><span data-stu-id="30cae-120">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="30cae-121">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="30cae-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="30cae-122">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30cae-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="30cae-123">この例では **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンスをユーザー アカウント から削除 BelindaN@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="30cae-123">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="30cae-124">コマンドレットを使用して `Set-MsolUserLicense` 、キャンセルされたライセンスからユーザーの割り当 *てを解除* することはできません。</span><span class="sxs-lookup"><span data-stu-id="30cae-124">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="30cae-125">これを Microsoft 365 管理センターのユーザー アカウントごとに個別に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="30cae-125">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="30cae-126">既存のライセンスユーザーのグループからすべてのライセンスを削除するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="30cae-126">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="30cae-127">**既存のアカウント属性に基づいてアカウントをフィルターする** これを行うには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="30cae-127">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="30cae-128">この例では、米国の Sales 部門のすべてのユーザー アカウントからすべてのライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="30cae-128">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="30cae-129">**特定のライセンスに特定のアカウントの一覧を使用する** これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="30cae-129">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="30cae-130">次のように各行に 1 つのアカウントが含まれるテキスト ファイルを作成し、保存します。</span><span class="sxs-lookup"><span data-stu-id="30cae-130">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="30cae-131">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="30cae-131">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="30cae-132">この例では、テキスト ファイル C:\My Documents\Accounts.txt で定義されているユーザー アカウントから **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="30cae-132">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="30cae-133">すべての既存のユーザー アカウントからすべてのライセンスを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="30cae-133">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="30cae-134">別の方法として、ユーザー アカウントを削除してライセンスを解放することもできます。</span><span class="sxs-lookup"><span data-stu-id="30cae-134">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="30cae-135">詳細については [、「PowerShell を使用してユーザー アカウントを削除して復元する」を参照してください](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="30cae-135">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30cae-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="30cae-136">See also</span></span>

[<span data-ttu-id="30cae-137">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="30cae-137">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="30cae-138">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="30cae-138">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="30cae-139">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="30cae-139">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)