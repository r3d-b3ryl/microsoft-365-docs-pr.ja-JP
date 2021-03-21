---
title: PowerShell で Microsoft 365 ライセンスとサービスを表示する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: PowerShell を使用して、Microsoft 365 組織で利用可能なライセンス プラン、サービス、ライセンスに関する情報を表示する方法について説明します。
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924638"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="4a4b6-103">PowerShell で Microsoft 365 ライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="4a4b6-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="4a4b6-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="4a4b6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4a4b6-105">すべての Microsoft 365 サブスクリプションは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="4a4b6-106">**ライセンス プラン** これらは、ライセンス プランまたは Microsoft 365 プランとも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="4a4b6-107">ライセンス プランは、ユーザーが利用できる Microsoft 365 サービスを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="4a4b6-108">Microsoft 365 サブスクリプションには、複数のライセンス プランが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="4a4b6-109">ライセンスプランの例は、Microsoft 365 E3 です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="4a4b6-110">**サービス** これらはサービス プランとも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="4a4b6-111">サービスは、Exchange Online および Microsoft 365 Apps for enterprise (以前は Office 365 ProPlus) など、各ライセンス プランで利用できる Microsoft 365 製品、機能です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="4a4b6-112">ユーザーは、さまざまなサービスへのアクセスを許可するさまざまなライセンス プランから割り当てられた複数のライセンスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="4a4b6-113">**ライセンス** 各ライセンスプランには、購入したライセンスの数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="4a4b6-114">ユーザーにライセンスを割り当て、ライセンス プランで定義されている Microsoft 365 サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="4a4b6-115">すべてのユーザー アカウントには、Microsoft 365 にログオンしてサービスを使用するために、1 つのライセンス プランから少なくとも 1 つのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="4a4b6-116">PowerShell for Microsoft 365 を使用すると、Microsoft 365 組織で利用可能なライセンス プラン、ライセンス、およびサービスの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="4a4b6-117">別の Office 365 サブスクリプションで利用可能な製品、機能、サービスについての詳細は、「[Office 365 プランのオプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4a4b6-118">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="4a4b6-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4a4b6-119">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="4a4b6-120">現在のライセンス プランと各プランで使用可能なライセンスに関する概要情報を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="4a4b6-121">結果には次の情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-121">The results contain:</span></span>
  
- <span data-ttu-id="4a4b6-122">**SkuPartNumber:** 組織で利用可能なライセンス プランを表示します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="4a4b6-123">たとえば `ENTERPRISEPACK` 、365 Enterprise E3 のライセンス Office名です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="4a4b6-124">**有効:** 特定のライセンス プランで購入したライセンスの数。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="4a4b6-125">**ConsumedUnits:** 特定のライセンス プランでユーザーに割り当てたライセンスの数。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="4a4b6-126">すべてのライセンス プランで利用できる Microsoft 365 サービスの詳細を表示するには、まずライセンス プランの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="4a4b6-127">次に、ライセンス プランの情報を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="4a4b6-128">次に、特定のライセンス プランでサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="4a4b6-129">\<index> は、コマンドの表示からライセンス プランの行番号を指定する整数で、1 を `Get-AzureADSubscribedSku | Select SkuPartNumber` 引いた値です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="4a4b6-130">たとえば、コマンドの表示が `Get-AzureADSubscribedSku | Select SkuPartNumber` 次の場合です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="4a4b6-131">次に、ENTERPRISEPREMIUM ライセンス プランのサービスを表示するコマンドは次のコマンドです。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="4a4b6-132">ENTERPRISEPREMIUM は 3 行目です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="4a4b6-133">したがって、インデックス値は (3 ~ 1)、または 2 です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="4a4b6-134">ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4a4b6-135">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="4a4b6-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4a4b6-136">まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="4a4b6-137">このトピックで説明されている手順を自動化する PowerShell スクリプトが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="4a4b6-138">具体的には、スクリプトを使用すると、Sway を含む Microsoft 365 組織のサービスを表示および無効化できます。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="4a4b6-139">詳細については [、「PowerShell を使用して Sway へのアクセスを無効にする」を参照してください](disable-access-to-sway-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="4a4b6-140">現在のライセンス プランと各プランで使用可能なライセンスに関する概要情報を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="4a4b6-141">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="4a4b6-142">これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="4a4b6-143">結果には次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="4a4b6-144">**AccountSkuId:** 構文を使用して、組織で利用可能なライセンス プランを表示します `<CompanyName>:<LicensingPlan>` 。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="4a4b6-145">_\<CompanyName>_ は、Microsoft 365 に登録するときに指定した値であり、組織で一意です。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="4a4b6-146">_\<LicensingPlan>_ の値は、すべてのユーザーに対して同じです。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="4a4b6-147">たとえば、値 `litwareinc:ENTERPRISEPACK` では、会社名が `litwareinc`、ライセンス プラン名が  `ENTERPRISEPACK` で、これが Office 365 Enterprise E3 のシステム名になります。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="4a4b6-148">**ActiveUnits:** 特定のライセンス プランで購入したライセンスの数。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="4a4b6-149">**WarningUnits:** 更新していないライセンス プランのライセンスの数。30 日の猶予期間を過ぎると有効期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="4a4b6-150">**ConsumedUnits:** 特定のライセンス プランでユーザーに割り当てたライセンスの数。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="4a4b6-151">すべてのライセンス プランで利用できる Microsoft 365 サービスの詳細を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="4a4b6-152">次の表に、最も一般的なサービスの Microsoft 365 サービス プランとその親しみ名を示します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="4a4b6-153">実際のサービス プランの一覧とは、異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="4a4b6-154">**サービス プラン**</span><span class="sxs-lookup"><span data-stu-id="4a4b6-154">**Service plan**</span></span>|<span data-ttu-id="4a4b6-155">**説明**</span><span class="sxs-lookup"><span data-stu-id="4a4b6-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="4a4b6-156">Sway</span><span class="sxs-lookup"><span data-stu-id="4a4b6-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="4a4b6-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a4b6-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="4a4b6-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="4a4b6-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="4a4b6-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="4a4b6-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="4a4b6-160">Microsoft 365 Apps for enterprise (以前は Office *365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="4a4b6-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="4a4b6-161">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4a4b6-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="4a4b6-162">Office</span><span class="sxs-lookup"><span data-stu-id="4a4b6-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="4a4b6-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4a4b6-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="4a4b6-164">Exchange Online プラン 2</span><span class="sxs-lookup"><span data-stu-id="4a4b6-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="4a4b6-165">ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="4a4b6-166">特定のライセンス プランで使用できる Microsoft 365 サービスの詳細を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="4a4b6-167">次の使用例は、litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンス プランで利用できるサービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="4a4b6-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="4a4b6-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a4b6-168">See also</span></span>

[<span data-ttu-id="4a4b6-169">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="4a4b6-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4a4b6-170">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="4a4b6-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4a4b6-171">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="4a4b6-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)