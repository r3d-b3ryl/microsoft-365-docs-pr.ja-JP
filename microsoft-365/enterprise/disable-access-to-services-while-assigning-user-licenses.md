---
title: ユーザー ライセンスの割り当て中に Microsoft 365 サービスへのアクセスを無効にする
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: PowerShell for Microsoft 365 を使用して、ユーザー アカウントにライセンスを割り当て、特定のサービス プランを同時に無効にする方法について説明します。
ms.openlocfilehash: 7486968f6f4822047a1697ee1e05129277fd11a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929434"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="a8c6e-103">ユーザー ライセンスの割り当て中に Microsoft 365 サービスへのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="a8c6e-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="a8c6e-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="a8c6e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a8c6e-105">Microsoft 365 サブスクリプションには、個々のサービスのサービス プランが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="a8c6e-106">Microsoft 365 管理者は、多くの場合、ユーザーにライセンスを割り当てるときに特定のプランを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="a8c6e-107">この記事の手順では、Microsoft 365 ライセンスを割り当てながら、個々のユーザー アカウントまたは複数のユーザー アカウントに PowerShell を使用して特定のサービス プランを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a8c6e-108">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="a8c6e-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a8c6e-109">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="a8c6e-110">次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="a8c6e-111">次に、ライセンスを追加するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="a8c6e-112">次に、有効にするサービスの一覧をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="a8c6e-113">ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="a8c6e-114">以下のコマンド ブロックで、ユーザー アカウントのユーザー プリンシパル名、SKU パーツ番号、およびサービス プランの一覧を入力して、説明テキストと文字を有効にして削除 \< and > します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="a8c6e-115">次に、完成したコマンドを PowerShell コマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a8c6e-116">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="a8c6e-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a8c6e-117">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="a8c6e-118">次に、このコマンドを実行して現在のサブスクリプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="a8c6e-119">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="a8c6e-120">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="a8c6e-121">`Get-MsolAccountSku` コマンドの出力に関して次に説明します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="a8c6e-122">**AccountSkuId** は、次の形式で組織 \<OrganizationName> のサブスクリプション \<Subscription> です。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="a8c6e-123">これは、Microsoft 365 に登録するときに指定した値であり、組織 \<OrganizationName> に固有の値です。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="a8c6e-124">値 \<Subscription> は、特定のサブスクリプションの値です。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="a8c6e-125">たとえば、litwareinc:ENTERPRISEPACK の場合、組織名は litwareinc、サブスクリプション名は ENTERPRISEPACK (Office 365 Enterprise E3) です。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="a8c6e-126">**ActiveUnits** は、サブスクリプションで購入したライセンス数です。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="a8c6e-127">**WarningUnits** は、まだ更新しておらず、30 日の猶予期間を過ぎると有効期限切れになる、サブスクリプション内のライセンス数です。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="a8c6e-128">**ConsumedUnits** は、このサブスクリプションでユーザーに割り当てたライセンスの数です。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="a8c6e-129">ライセンスを取得するユーザーを含む Microsoft 365 サブスクリプションの AccountSkuId に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="a8c6e-130">また、割り当てるのに十分なライセンスが存在する **(ActiveUnits から ConsumedUnits** を減算する) **必要があります** 。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="a8c6e-131">次に、このコマンドを実行して、すべてのサブスクリプションで利用可能な Microsoft 365 サービス プランの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="a8c6e-132">このコマンドの出力に基づいて、ユーザーにライセンスを割り当てるときに無効にするサービス プランを判別します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="a8c6e-133">サービス プランとそれに対応する Microsoft 365 サービスの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="a8c6e-134">次の表に、最も一般的なサービスの Microsoft 365 サービス プランとその親しみ名を示します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="a8c6e-135">実際のサービス プランの一覧とは、異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="a8c6e-136">**サービス プラン**</span><span class="sxs-lookup"><span data-stu-id="a8c6e-136">**Service plan**</span></span>|<span data-ttu-id="a8c6e-137">**説明**</span><span class="sxs-lookup"><span data-stu-id="a8c6e-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="a8c6e-138">Sway</span><span class="sxs-lookup"><span data-stu-id="a8c6e-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="a8c6e-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8c6e-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="a8c6e-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="a8c6e-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="a8c6e-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="a8c6e-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="a8c6e-142">Microsoft 365 Apps for enterprise (以前は Office *365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="a8c6e-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="a8c6e-143">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a8c6e-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="a8c6e-144">Office</span><span class="sxs-lookup"><span data-stu-id="a8c6e-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="a8c6e-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a8c6e-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="a8c6e-146">Exchange Online プラン 2</span><span class="sxs-lookup"><span data-stu-id="a8c6e-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="a8c6e-147">ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="a8c6e-148">この時点で、AccountSkuId と無効にするサービス プランが決まったため、1 ユーザーまたは複数ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="a8c6e-149">単一ユーザーの場合</span><span class="sxs-lookup"><span data-stu-id="a8c6e-149">For a single user</span></span>

<span data-ttu-id="a8c6e-150">1 人のユーザーの場合は、ユーザー アカウントのユーザー プリンシパル名、AccountSkuId、およびサービス プランの一覧を入力して、説明テキストと文字を無効にして削除 \< and > します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="a8c6e-151">次に、完成したコマンドを PowerShell コマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="a8c6e-152">コマンド ブロックの例を以下に示します。アカウント名は belindan@contoso.com で、ライセンスは contoso:ENTERPRISEPACK であり、RMS_S_ENTERPRISE、SWAY、INTUNE_O365、YAMMER_ENTERPRISE の各サービス プランを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="a8c6e-153">複数ユーザーの場合</span><span class="sxs-lookup"><span data-stu-id="a8c6e-153">For multiple users</span></span>

<span data-ttu-id="a8c6e-p109">この管理タスクを複数ユーザーに実行するには、UserPrincipalName フィールドと UsageLocation フィールドが含まれるコンマ区切り値 (CSV) テキスト ファイルを作成します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-p109">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields. Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="a8c6e-156">その後、入力および出力の各 CSV ファイルの場所、アカウント SKU ID、無効にするサービス プランの一覧を入力し、完成したコマンドを PowerShell コマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

<span data-ttu-id="a8c6e-157">この PowerShell コマンド ブロックは以下の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="a8c6e-158">各ユーザーのユーザー プリンシパル名を表示します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="a8c6e-159">各ユーザーにカスタマイズされたライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="a8c6e-160">処理されたすべてのユーザーが含まれる CSV ファイルを作成し、そのライセンス状態を示します。</span><span class="sxs-lookup"><span data-stu-id="a8c6e-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a8c6e-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8c6e-161">See also</span></span>

[<span data-ttu-id="a8c6e-162">PowerShell を使用して Microsoft 365 サービスへのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="a8c6e-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a8c6e-163">PowerShell を使用して Sway へのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="a8c6e-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a8c6e-164">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="a8c6e-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a8c6e-165">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="a8c6e-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)