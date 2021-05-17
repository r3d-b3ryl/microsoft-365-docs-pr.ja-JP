---
title: PowerShell Microsoft 365アカウントにライセンスを割り当てる
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
description: この記事では、PowerShell を使用してライセンスのないユーザーにライセンス Microsoft 365割り当てる方法について説明します。
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905466"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="e810f-103">PowerShell Microsoft 365アカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e810f-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="e810f-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="e810f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e810f-105">ユーザーは、アカウントにライセンス プランMicrosoft 365が割り当てられるまで、すべてのサービスを使用できません。</span><span class="sxs-lookup"><span data-stu-id="e810f-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="e810f-106">PowerShell を使用すると、ライセンスのないアカウントにライセンスをすばやく割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e810f-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="e810f-107">ユーザー アカウントには、最初に場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e810f-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="e810f-108">場所の指定は、管理センターで新しいユーザー アカウントを作成するMicrosoft 365[です](../admin/add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="e810f-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="e810f-109">オンプレミスの Active Directory ドメイン サービスから同期されたアカウントは、既定では場所が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="e810f-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="e810f-110">これらのアカウントの場所は、次の場所から構成できます。</span><span class="sxs-lookup"><span data-stu-id="e810f-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="e810f-111">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="e810f-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="e810f-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e810f-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="e810f-113">[Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Active **Directory Users**  >  **>** プロファイル連絡先>**国**  >    >  または地域)</span><span class="sxs-lookup"><span data-stu-id="e810f-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="e810f-114">[管理者センターでユーザー アカウントに](../admin/manage/assign-licenses-to-users.md)ライセンスを割り当てるMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="e810f-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="e810f-115">その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="e810f-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e810f-116">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="e810f-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e810f-117">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e810f-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="e810f-118">次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e810f-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="e810f-119">次に、ライセンスを追加するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e810f-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="e810f-120">次に、ユーザー アカウントに使用場所が割り当てられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="e810f-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="e810f-121">使用場所が割り当てられていない場合は、次のコマンドを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e810f-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="e810f-122">最後に、ユーザー サインイン名とライセンス プラン名を指定し、これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e810f-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e810f-123">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="e810f-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e810f-124">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e810f-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="e810f-125">このコマンドを実行して、利用可能なライセンス プランと、組織内の各プランで使用可能な `Get-MsolAccountSku` ライセンスの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="e810f-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="e810f-126">各プランで利用可能なライセンスの数は、 **ActiveUnits** - **WarningUnits** - **ConsumedUnits** です。</span><span class="sxs-lookup"><span data-stu-id="e810f-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="e810f-127">ライセンス プラン、ライセンス、およびサービスの詳細については、「PowerShell でライセンスとサービスを表示 [する」を参照してください](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="e810f-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="e810f-128">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e810f-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e810f-129">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e810f-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="e810f-130">組織内のライセンスのないアカウントを検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e810f-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="e810f-131">**UsageLocation** プロパティが有効な ISO 3166-1 α-2 の国コードに設定されているユーザー アカウントにのみライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e810f-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="e810f-132">たとえば、米国は US、フランスは FR です。</span><span class="sxs-lookup"><span data-stu-id="e810f-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="e810f-133">一部Microsoft 365一部のサービスは、一部の国では利用できません。</span><span class="sxs-lookup"><span data-stu-id="e810f-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="e810f-134">詳細については、「ライセンス制限 [について」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=691730)。</span><span class="sxs-lookup"><span data-stu-id="e810f-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="e810f-135">**UsageLocation** 値を持つアカウントを検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e810f-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="e810f-136">アカウントの **UsageLocation 値を** 設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e810f-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="e810f-137">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e810f-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="e810f-138">**-All** パラメーターなしで **Get-MsolUser** コマンドレットを使用する場合、最初の 500 個のアカウントだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="e810f-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="e810f-139">ユーザー アカウントへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="e810f-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="e810f-140">ユーザーにライセンスを割り当てるには、PowerShell で次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e810f-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="e810f-141">次の使用例は **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンスプランのライセンスを、ライセンスのないユーザーの belindan litwareinc.com に割り **\@ 当 litwareinc.com。**</span><span class="sxs-lookup"><span data-stu-id="e810f-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="e810f-142">ライセンスのないすべてのユーザーにライセンスを割り当てるには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e810f-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="e810f-143">複数のライセンスを同じライセンス プランのユーザーに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="e810f-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="e810f-144">十分な数の利用可能なライセンスをお持ちでない場合は、使用可能なライセンスがなくなるまで、ライセンスは **Get-MsolUser** コマンドレットによって返される順序でユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e810f-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="e810f-145">この例では **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランからすべてのライセンスのないユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e810f-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="e810f-146">次の使用例は、米国の Sales 部門のライセンスのないユーザーに同じライセンスを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="e810f-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e810f-147">PowerShell を使用して別のサブスクリプション (ライセンス プラン) にユーザーを移動Azure Active Directory PowerShell Graphします。</span><span class="sxs-lookup"><span data-stu-id="e810f-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e810f-148">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e810f-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="e810f-149">次に、サブスクリプションの切り替えに使用するユーザー アカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e810f-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="e810f-150">次に、このコマンドを使用してテナントのサブスクリプション (ライセンス プラン) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e810f-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="e810f-151">次に、これらのコマンドでユーザー アカウントが現在持っているサブスクリプションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e810f-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="e810f-152">ユーザーが現在持っているサブスクリプション (FROM サブスクリプション) と、ユーザーが移動するサブスクリプション (TO サブスクリプション) を識別します。</span><span class="sxs-lookup"><span data-stu-id="e810f-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="e810f-153">最後に、TO サブスクリプション名と FROM サブスクリプション名 (SKU パーツ番号) を指定し、これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e810f-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="e810f-154">これらのコマンドを使用して、ユーザー アカウントのサブスクリプションの変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e810f-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="e810f-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="e810f-155">See also</span></span>

[<span data-ttu-id="e810f-156">ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="e810f-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e810f-157">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="e810f-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e810f-158">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="e810f-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)