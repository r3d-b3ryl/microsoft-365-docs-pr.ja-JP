---
title: PowerShell を使用してMicrosoft 365ライセンスをユーザー アカウントに割り当てる
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: この記事では、PowerShell を使用してライセンスを持たないユーザーにMicrosoft 365 ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572623"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="cefb8-103">PowerShell を使用してMicrosoft 365ライセンスをユーザー アカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="cefb8-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="cefb8-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="cefb8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cefb8-105">ユーザーは、ライセンス プランからライセンスが割り当てられるまで、Microsoft 365 サービスを使用できません。</span><span class="sxs-lookup"><span data-stu-id="cefb8-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="cefb8-106">PowerShell を使用すると、ライセンスをライセンスのないアカウントにすばやく割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="cefb8-107">ユーザー アカウントには、まず場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cefb8-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="cefb8-108">場所の指定は[、Microsoft 365管理センター](../admin/add-users/add-users.md)で新しいユーザー アカウントを作成する際に必要な部分です。</span><span class="sxs-lookup"><span data-stu-id="cefb8-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="cefb8-109">オンプレミスの Active Directory ドメイン サービスから同期されたアカウントには、既定では場所が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="cefb8-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="cefb8-110">これらのアカウントの場所は、次の場所から構成できます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="cefb8-111">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="cefb8-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="cefb8-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cefb8-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="cefb8-113">[Azure ポータル](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)(**ユーザー**  >  アカウント>ユーザー アカウント>**プロファイル**  >  **連絡先情報**  >  **国または地域**) 。</span><span class="sxs-lookup"><span data-stu-id="cefb8-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="cefb8-114">Microsoft 365管理センター[でユーザー アカウントにライセンスを割り当てる方法について説明](../admin/manage/assign-licenses-to-users.md)します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="cefb8-115">その他のリソースの一覧については、 [ユーザーとグループの管理 を](../admin/add-users/index.yml)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cefb8-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="cefb8-116">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="cefb8-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="cefb8-117">まず[、Microsoft 365のテナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="cefb8-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="cefb8-118">次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="cefb8-119">次に、ライセンスを追加するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="cefb8-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="cefb8-120">次に、ユーザー アカウントに使用場所が割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="cefb8-121">使用場所が割り当てられていない場合は、次のコマンドを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="cefb8-122">最後に、ユーザーサインイン名とライセンス プラン名を指定し、これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="cefb8-123">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="cefb8-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="cefb8-124">このモジュールの機能が新しい[Azure Active Directory の PowerShell](/powershell/azuread/v2/azureactivedirectory)モジュールで利用可能な場合は、このモジュールの非推奨Graph始めます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="cefb8-125">新しい PowerShell スクリプトを作成するお客様には、このモジュールではなく新しいモジュールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cefb8-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="cefb8-126">まず[、Microsoft 365のテナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cefb8-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="cefb8-127">`Get-MsolAccountSku`このコマンドを実行して、使用可能なライセンス プランと、組織の各プランで使用可能なライセンス数を表示します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="cefb8-128">各プランで利用可能なライセンスの数は、 **ActiveUnits** - **WarningUnits** - **ConsumedUnits** です。</span><span class="sxs-lookup"><span data-stu-id="cefb8-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="cefb8-129">ライセンス プラン、ライセンス、およびサービスの詳細については [、「PowerShell を使用してライセンスとサービスを表示](view-licenses-and-services-with-microsoft-365-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cefb8-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="cefb8-130">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cefb8-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="cefb8-131">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cefb8-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="cefb8-132">組織内のライセンスされていないアカウントを検索するには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="cefb8-133">ライセンスを割り当てるのは **、UsageLocation** プロパティが有効な ISO 3166-1 alpha-2 の国コードに設定されているユーザー アカウントに限られます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="cefb8-134">たとえば、米国は US、フランスは FR です。</span><span class="sxs-lookup"><span data-stu-id="cefb8-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="cefb8-135">一部のMicrosoft 365サービスは、一部の国では利用できません。</span><span class="sxs-lookup"><span data-stu-id="cefb8-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="cefb8-136">詳細については、「 [ライセンス制限について」](https://go.microsoft.com/fwlink/p/?LinkId=691730)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cefb8-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="cefb8-137">**[使用** 場所] の値がないアカウントを検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="cefb8-138">アカウントの **UsageLocation** 値を設定するには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="cefb8-139">例:</span><span class="sxs-lookup"><span data-stu-id="cefb8-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="cefb8-140">**-All** パラメーターなしで **Get-MsolUser** コマンドレットを使用する場合、最初の 500 個のアカウントだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="cefb8-141">ユーザー アカウントへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="cefb8-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="cefb8-142">ユーザーにライセンスを割り当てるには、PowerShell で次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="cefb8-143">この例では **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランからライセンスをライセンスのないユーザー **belindan \@ litwareinc.com** に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="cefb8-144">ライセンスをすべてのライセンスユーザーに割り当てるには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="cefb8-145">複数のライセンスを同じライセンス プランのユーザーに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="cefb8-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="cefb8-146">十分な数の利用可能なライセンスをお持ちでない場合は、使用可能なライセンスがなくなるまで、ライセンスは **Get-MsolUser** コマンドレットによって返される順序でユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="cefb8-147">この例では **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランのライセンスを、ライセンスを持つすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="cefb8-148">この例では、同じライセンスを米国の営業部門のライセンスのないユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="cefb8-149">Graph モジュールの PowerShell を Azure Active Directory使用して、別のサブスクリプション (ライセンス プラン) にユーザーを移動Graph</span><span class="sxs-lookup"><span data-stu-id="cefb8-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="cefb8-150">まず[、Microsoft 365のテナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="cefb8-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="cefb8-151">次に、サブスクリプションを切り替えるユーザー アカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="cefb8-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="cefb8-152">次に、このコマンドを使用して、テナントのサブスクリプション (ライセンス プラン) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="cefb8-153">次に、これらのコマンドを使用して、ユーザー アカウントが現在持っているサブスクリプションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="cefb8-154">ユーザーが現在持っているサブスクリプション (FROM サブスクリプション) とユーザーが移動しているサブスクリプション (TO サブスクリプション) を識別します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="cefb8-155">最後に、TO および FROM サブスクリプション名 (SKU の部品番号) を指定し、これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cefb8-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="cefb8-156">これらのコマンドを使用して、ユーザー アカウントのサブスクリプションの変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cefb8-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="cefb8-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="cefb8-157">See also</span></span>

[<span data-ttu-id="cefb8-158">ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="cefb8-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cefb8-159">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="cefb8-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cefb8-160">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="cefb8-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
