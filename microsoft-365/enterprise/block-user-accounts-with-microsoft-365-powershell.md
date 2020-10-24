---
title: Microsoft 365 のユーザーアカウントに PowerShell を使用することを禁止する
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
description: PowerShell を使用して、Microsoft 365 アカウントへのアクセスをブロックおよびブロック解除する方法について説明します。
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754682"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="92228-103">Microsoft 365 のユーザーアカウントに PowerShell を使用することを禁止する</span><span class="sxs-lookup"><span data-stu-id="92228-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="92228-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="92228-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="92228-105">Microsoft 365 アカウントへのアクセスをブロックする場合は、ユーザーがアカウントを使用して Microsoft 365 組織のサービスとデータにサインインしてアクセスするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="92228-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="92228-106">PowerShell を使用して、個別のまたは複数のユーザーアカウントへのアクセスをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="92228-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="92228-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="92228-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="92228-108">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="92228-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="92228-109">個別のユーザーアカウントへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="92228-109">Block access to individual user accounts</span></span>

<span data-ttu-id="92228-110">個々のユーザーアカウントをブロックするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="92228-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="92228-111">**AzureAD**コマンドレットの *-ObjectID*パラメーターは、アカウントのサインイン名 (ユーザープリンシパル名とも呼ばれる)、またはアカウントのオブジェクト ID のいずれかを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="92228-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="92228-112">この例では、ユーザーアカウント *fabricec@litwareinc.com*へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="92228-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="92228-113">このユーザー アカウントのブロックを解除するには、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92228-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="92228-114">ユーザーの表示名に基づいてユーザーアカウント UPN を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="92228-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="92228-115">この例では、ユーザー  *Caleb*のユーザーアカウント UPN を表示します。</span><span class="sxs-lookup"><span data-stu-id="92228-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="92228-116">ユーザーの表示名に基づいてアカウントをブロックするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="92228-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="92228-117">ユーザーアカウントのブロックされた状態を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="92228-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="92228-118">複数のユーザーアカウントをブロックする</span><span class="sxs-lookup"><span data-stu-id="92228-118">Block multiple user accounts</span></span>

<span data-ttu-id="92228-119">複数のユーザーアカウントのアクセスをブロックするには、次のように各行に1つのアカウントサインイン名を含むテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="92228-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="92228-120">次のコマンドでは、サンプルテキストファイルは *C:\My Documents\Accounts.txt*です。</span><span class="sxs-lookup"><span data-stu-id="92228-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="92228-121">このファイル名を、テキストファイルのパスとファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="92228-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="92228-122">テキスト ファイルに記載されているアカウントへのアクセスをブロックするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92228-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="92228-123">テキストファイルに記載されているアカウントのブロックを解除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92228-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="92228-124">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="92228-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="92228-125">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="92228-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="92228-126">個別のユーザーアカウントをブロックする</span><span class="sxs-lookup"><span data-stu-id="92228-126">Block individual user accounts</span></span>

<span data-ttu-id="92228-127">個別のユーザーアカウントのアクセスをブロックするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="92228-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="92228-128">PowerShell Core は、Windows PowerShell モジュールの Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="92228-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="92228-129">これらのコマンドレットは、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92228-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="92228-130">この例では、ユーザーアカウント *fabricec \@ litwareinc.com*へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="92228-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="92228-131">ユーザー アカウントのブロックを解除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92228-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="92228-132">ユーザーアカウントのブロック状態を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92228-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="92228-133">複数のユーザーアカウントのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="92228-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="92228-134">最初に、次のような各行に1つのアカウントを含むテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="92228-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="92228-135">次のコマンドでは、サンプルテキストファイルは *C:\My Documents\Accounts.txt*です。</span><span class="sxs-lookup"><span data-stu-id="92228-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="92228-136">このファイル名を、テキストファイルのパスとファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="92228-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="92228-137">テキストファイルに記載されているアカウントのアクセスをブロックするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92228-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="92228-138">テキスト ファイルに記載されているアカウントへのアクセスのブロックを解除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92228-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="92228-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="92228-139">See also</span></span>

[<span data-ttu-id="92228-140">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="92228-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="92228-141">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="92228-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="92228-142">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="92228-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
