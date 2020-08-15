---
title: PowerShell を使用して Microsoft 365 サービスへのアクセスを無効にする
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: この記事では、PowerShell を使用してユーザーの Microsoft 365 サービスへのアクセスを無効にする方法について説明します。
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691844"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="b7a7c-103">PowerShell を使用して Microsoft 365 サービスへのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="b7a7c-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="b7a7c-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="b7a7c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b7a7c-105">Microsoft 365 アカウントにライセンスプランのライセンスが割り当てられている場合、Microsoft 365 サービスはそのライセンスからユーザーが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="b7a7c-106">ただし、ユーザーがアクセスできる Microsoft 365 サービスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="b7a7c-107">たとえば、ライセンスで SharePoint Online サービスへのアクセスが許可されている場合でも、アクセスを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="b7a7c-108">PowerShell を使用して、次のような特定のライセンスプランで任意の数のサービスへのアクセスを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="b7a7c-109">個々のアカウント。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-109">An individual account.</span></span>
- <span data-ttu-id="b7a7c-110">アカウントのグループ。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-110">A group of accounts.</span></span>
- <span data-ttu-id="b7a7c-111">組織内のすべてのアカウント。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="b7a7c-112">Microsoft 365 service の依存関係によって、他のサービスに依存している場合に、指定されたサービスを無効にすることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b7a7c-113">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="b7a7c-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b7a7c-114">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="b7a7c-115">次に、このコマンドを使用して、使用可能なライセンスプラン (AccountSkuIds とも呼ばれます) を表示します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="b7a7c-116">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="b7a7c-117">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="b7a7c-118">詳細については、「 [PowerShell を使用してライセンスとサービスを表示](view-licenses-and-services-with-microsoft-365-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="b7a7c-119">このトピックの手順の前と後の結果を確認するには、「 [PowerShell を使用してアカウントのライセンスとサービスの詳細を表示](view-account-license-and-service-details-with-microsoft-365-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="b7a7c-120">このトピックで説明されている手順を自動化する PowerShell スクリプトが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="b7a7c-121">具体的には、このスクリプトを使用すると、Sway を含む Microsoft 365 組織のサービスを表示したり、無効にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="b7a7c-122">詳細については、「 [PowerShell を使用して Sway へのアクセスを無効](disable-access-to-sway-with-microsoft-365-powershell.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="b7a7c-123">特定のライセンスプランの特定のユーザーに対して特定の Microsoft 365 サービスを無効にする</span><span class="sxs-lookup"><span data-stu-id="b7a7c-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="b7a7c-124">特定のライセンスプランについて、ユーザーに対して特定の Microsoft 365 サービスのセットを無効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="b7a7c-125">手順 1: 次の構文を使用して、ライセンスプランで不要なサービスを特定します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="b7a7c-126">次の例では、という名前のライセンスプラン (office 365 Enterprise E3) で Office および SharePoint Online サービスを無効にする **Licenseoptions** オブジェクトを作成し `litwareinc:ENTERPRISEPACK` ます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="b7a7c-127">手順 2: 1 人以上のユーザーの手順1の **Licenseoptions** オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="b7a7c-128">サービスが無効になっている新しいアカウントを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="b7a7c-129">次の例では、ライセンスを割り当て、手順1で説明されているサービスを無効にする Allie Bellew の新しいアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="b7a7c-130">Microsoft 365 の PowerShell でユーザーアカウントを作成する方法の詳細については、「 [powershell を使用してユーザーアカウントを作成](create-user-accounts-with-microsoft-365-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="b7a7c-131">ライセンスを付与された既存のユーザー用のサービスを無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="b7a7c-132">この例では、ユーザー BelindaN@litwareinc.com に対してサービスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="b7a7c-133">既存のライセンスを持つすべてのユーザーについて、手順1で説明されているサービスを無効にするには、 **get-msolaccountsku** コマンドレット ( **LITWAREINC: enterprisepack**など) の表示から Microsoft 365 プランの名前を指定し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="b7a7c-134">_All_パラメーターを使用せずに**get-msoluser**コマンドレットを使用すると、最初の500ユーザーアカウントのみが返されます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="b7a7c-135">既存のユーザーのグループに対してサービスを無効にするには、次のいずれかの方法を使用して、ユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="b7a7c-136">**方法1既存のアカウント属性に基づいてアカウントをフィルター処理する**</span><span class="sxs-lookup"><span data-stu-id="b7a7c-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="b7a7c-137">この設定を行うには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="b7a7c-138">次の例では、米国内の販売部門のユーザーのサービスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="b7a7c-139">**方法 2: 特定のアカウントの一覧を使用する**</span><span class="sxs-lookup"><span data-stu-id="b7a7c-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="b7a7c-140">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="b7a7c-141">次のように各行に 1 つのアカウントが含まれるテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="b7a7c-142">この例では、テキストファイルは C: \\ My Documents \\Accounts.txt です。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="b7a7c-143">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="b7a7c-144">複数のライセンスプランのサービスへのアクセスを無効にする場合は、ライセンスプランごとに上記の手順を繰り返し、以下のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="b7a7c-145">ユーザーアカウントにはライセンスプランが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="b7a7c-146">無効化するサービスは、ライセンスプランで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="b7a7c-147">ユーザーがライセンスプランに割り当てている間に Microsoft 365 サービスを無効にするには、「 [ユーザーのライセンスの割り当て中にサービスへのアクセスを無効](disable-access-to-services-while-assigning-user-licenses.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="b7a7c-148">ライセンスプランのすべてのサービスをユーザーアカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="b7a7c-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="b7a7c-149">サービスが無効になっているユーザーアカウントの場合は、次のコマンドを使用して、特定のライセンスプランのすべてのサービスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7a7c-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="b7a7c-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b7a7c-150">Related topic</span></span>

[<span data-ttu-id="b7a7c-151">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="b7a7c-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b7a7c-152">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="b7a7c-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b7a7c-153">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b7a7c-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
