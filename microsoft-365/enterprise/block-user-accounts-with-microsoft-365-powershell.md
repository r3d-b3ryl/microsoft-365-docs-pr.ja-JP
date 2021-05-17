---
title: PowerShell Microsoft 365ユーザー アカウントをブロックする
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: PowerShell を使用して、アカウントへのアクセスをブロックおよびブロック解除するMicrosoft 365方法。
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754682"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="6b6fd-103">PowerShell Microsoft 365ユーザー アカウントをブロックする</span><span class="sxs-lookup"><span data-stu-id="6b6fd-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="6b6fd-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="6b6fd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6b6fd-105">Microsoft 365 アカウントへのアクセスをブロックすると、だれもがアカウントを使用してサインインし、組織のサービスとデータにアクセスMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="6b6fd-106">PowerShell を使用して、個々のユーザー アカウントまたは複数のユーザー アカウントへのアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6b6fd-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="6b6fd-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6b6fd-108">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="6b6fd-109">個々のユーザー アカウントへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="6b6fd-109">Block access to individual user accounts</span></span>

<span data-ttu-id="6b6fd-110">次の構文を使用して、個々のユーザー アカウントをブロックします。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="6b6fd-111">*Set-AzureAD* コマンドレットの **-ObjectID** パラメーターは、アカウントサインイン名 (ユーザー プリンシパル名とも呼ばれる) またはアカウントのオブジェクト ID を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="6b6fd-112">次の使用例は、ユーザー アカウントへの *アクセスをブロック* fabricec@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="6b6fd-113">このユーザー アカウントのブロックを解除するには、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="6b6fd-114">ユーザーの表示名に基づいてユーザー アカウント UPN を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="6b6fd-115">次の使用例は、ユーザー  *Caleb Sills のユーザー アカウント UPN を表示します*。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6b6fd-116">ユーザーの表示名に基づいてアカウントをブロックするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="6b6fd-117">ユーザー アカウントのブロックされた状態を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="6b6fd-118">複数のユーザー アカウントをブロックする</span><span class="sxs-lookup"><span data-stu-id="6b6fd-118">Block multiple user accounts</span></span>

<span data-ttu-id="6b6fd-119">複数のユーザー アカウントのアクセスをブロックするには、次のように各行に 1 つのアカウント サインイン名を含むテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="6b6fd-120">次のコマンドでは、テキスト ファイルの例は *C:\My Documents\Accounts.txtです*。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="6b6fd-121">このファイル名をテキスト ファイルのパスとファイル名に置き換える。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="6b6fd-122">テキスト ファイルに記載されているアカウントへのアクセスをブロックするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="6b6fd-123">テキスト ファイルに一覧表示されているアカウントのブロックを解除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6b6fd-124">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="6b6fd-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6b6fd-125">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="6b6fd-126">個々のユーザー アカウントをブロックする</span><span class="sxs-lookup"><span data-stu-id="6b6fd-126">Block individual user accounts</span></span>

<span data-ttu-id="6b6fd-127">個々のユーザー アカウントのアクセスをブロックするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="6b6fd-128">PowerShell Core では、Msol を名前に含Microsoft Azure Active DirectoryモジュールWindows PowerShellコマンドレットのモジュール *モジュールは* サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="6b6fd-129">これらのコマンドレットは、次の手順で実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="6b6fd-130">この例では、ユーザー アカウント *fabricec \@* へのアクセスをブロック litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="6b6fd-131">ユーザー アカウントのブロックを解除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="6b6fd-132">ユーザー アカウントのブロックされた状態を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="6b6fd-133">複数のユーザー アカウントのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="6b6fd-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="6b6fd-134">最初に、次のように各行に 1 つのアカウントを含むテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="6b6fd-135">次のコマンドでは、テキスト ファイルの例は *C:\My Documents\Accounts.txtです*。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="6b6fd-136">このファイル名をテキスト ファイルのパスとファイル名に置き換える。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="6b6fd-137">テキスト ファイルに一覧表示されているアカウントのアクセスをブロックするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="6b6fd-138">テキスト ファイルに記載されているアカウントへのアクセスのブロックを解除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b6fd-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="6b6fd-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b6fd-139">See also</span></span>

[<span data-ttu-id="6b6fd-140">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="6b6fd-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6b6fd-141">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="6b6fd-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6b6fd-142">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6b6fd-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
