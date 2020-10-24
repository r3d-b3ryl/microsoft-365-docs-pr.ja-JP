---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントのプロパティを構成する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Microsoft 365 の PowerShell を使用して、Microsoft 365 テナント内の個別のまたは複数のユーザーアカウントのプロパティを構成します。
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754330"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="19cd9-103">PowerShell を使用して Microsoft 365 ユーザーアカウントのプロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="19cd9-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="19cd9-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="19cd9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="19cd9-105">Microsoft 365 管理センターを使用して、Microsoft 365 テナントのユーザーアカウントのプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="19cd9-106">PowerShell では、これに加えて、管理センターでは実行できないその他のいくつかの操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="19cd9-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="19cd9-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="19cd9-108">Graph モジュールの Azure Active Directory PowerShell でユーザーアカウントのプロパティを構成するには、 [**set-azureaduser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) コマンドレットを使用して、設定または変更するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="19cd9-109">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="19cd9-110">特定のユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="19cd9-110">Change properties for a specific user account</span></span>

<span data-ttu-id="19cd9-111">*-ObjectID*パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="19cd9-112">最も一般的なパラメーターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="19cd9-113">-Department "<部署名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="19cd9-114">-DisplayName "<完全なユーザー名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="19cd9-115">-FacsimilieTelephoneNumber "<FAX 番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="19cd9-116">-GivenName "<ユーザーの名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="19cd9-117">-Surname "<ユーザーの姓>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="19cd9-118">-Mobile "<携帯電話番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="19cd9-119">-JobTitle "<役職>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="19cd9-120">-PreferredLanguage "<言語>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="19cd9-121">-StreetAddress "<番地>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="19cd9-122">-City "<市区町村名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="19cd9-123">-State "<都道府県名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="19cd9-124">-PostalCode "<郵便番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="19cd9-125">-Country "<国名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="19cd9-126">-TelephoneNumber "<勤務先電話番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="19cd9-127">-" \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="19cd9-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="19cd9-128">これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。</span><span class="sxs-lookup"><span data-stu-id="19cd9-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="19cd9-129">その他のパラメーターについては、「 [set-azureaduser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19cd9-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="19cd9-130">ユーザーアカウントにライセンスを割り当てるには、その前に、利用状況の場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="19cd9-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="19cd9-131">ユーザー アカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="19cd9-132">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="19cd9-133">ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信します ( **|** )。</span><span class="sxs-lookup"><span data-stu-id="19cd9-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-134">ユーザープリンシパル名のリストをアルファベット順に並べ替え (**UserPrincipalName を並べ替え**)、次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="19cd9-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-135">各アカウントのユーザープリンシパル名プロパティのみを表示します (**UserPrincipalName を選択**します)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="19cd9-136">一度に 1 画面ずつ表示する (**More**)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="19cd9-137">表示名 (姓と名) に基づいてアカウントのユーザープリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="19cd9-138">*$UserName*変数を入力し、次の文字を削除し \< and > ます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="19cd9-139">この例では、表示名が " *Caleb/ls*" であるユーザーアカウントのユーザープリンシパル名を表示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="19cd9-140">*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="19cd9-141">次の例では *、ベルギー*の使用場所をフランスに設定します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="19cd9-142">しかし、ユーザープリンシパル名ではなく、自分の表示名を指定しています。</span><span class="sxs-lookup"><span data-stu-id="19cd9-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="19cd9-143">すべてのユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="19cd9-143">Change properties for all user accounts</span></span>

<span data-ttu-id="19cd9-144">すべてのユーザーのプロパティを変更するには、 **set-azureaduser** コマンドレットと **set-azureaduser** コマンドレットの組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="19cd9-145">次の例では、すべてのユーザーの使用場所を *フランス*に変更します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="19cd9-146">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="19cd9-147">ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="19cd9-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-148">ユーザーの所在地をフランスに設定します (**set-azureaduser-@ location "FR"**)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="19cd9-149">特定のユーザー アカウント セットのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="19cd9-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="19cd9-150">特定のユーザーアカウントセットのプロパティを変更するには、 **set-azureaduser**、 **Where**、および **set-azureaduser** コマンドレットの組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="19cd9-151">次の例では、経理部門のすべてのユーザーの使用場所を *フランス*に変更します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="19cd9-152">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="19cd9-153">ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="19cd9-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="19cd9-154">*Department*プロパティが "Accounting" に設定されているすべてのユーザーアカウント (**Where {$ _) を検索します。Department-eq "Accounting"}**) を行い、結果の情報を次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="19cd9-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-155">ユーザーの所在地をフランスに設定します (**set-azureaduser-@ location "FR"**)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="19cd9-156">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="19cd9-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="19cd9-157">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用して、ユーザーアカウントのプロパティを構成するには、 **get-msoluser** コマンドレットを使用して、設定または変更するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="19cd9-158">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="19cd9-159">PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="19cd9-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="19cd9-160">これらのコマンドレットを Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="19cd9-161">特定のユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="19cd9-161">Change properties for a specific user account</span></span>

<span data-ttu-id="19cd9-162">特定のユーザーアカウントのプロパティを構成するには、 [**get-msoluser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) コマンドレットを使用して、設定または変更するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="19cd9-163">*-UserPrincipalName*パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="19cd9-164">最も一般的なパラメーターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="19cd9-165">-City "<市区町村名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="19cd9-166">-Country "<国名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="19cd9-167">-Department "<部署名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="19cd9-168">-DisplayName "<完全なユーザー名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="19cd9-169">-Fax "<fax 番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="19cd9-170">-FirstName "<ユーザーの名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="19cd9-171">-LastName "<ユーザーの姓>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="19cd9-172">-MobilePhone "<モバイル機器の番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="19cd9-173">-Office "<事業所の場所>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="19cd9-174">-PhoneNumber "<勤務先電話番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="19cd9-175">-PostalCode "<郵便番号>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="19cd9-176">-PreferredLanguage "<言語>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="19cd9-177">-State "<都道府県名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="19cd9-178">-StreetAddress "<番地>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="19cd9-179">-Title "<役職名>"</span><span class="sxs-lookup"><span data-stu-id="19cd9-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="19cd9-180">-" \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="19cd9-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="19cd9-181">これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。</span><span class="sxs-lookup"><span data-stu-id="19cd9-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="19cd9-182">その他のパラメーターについては、「 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19cd9-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="19cd9-183">すべてのユーザーのユーザープリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="19cd9-184">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="19cd9-185">ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。</span><span class="sxs-lookup"><span data-stu-id="19cd9-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-186">ユーザープリンシパル名のリストをアルファベット順に並べ替え (**UserPrincipalName を並べ替え**)、次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="19cd9-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-187">各アカウントのユーザープリンシパル名プロパティのみを表示します (**UserPrincipalName を選択**します)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="19cd9-188">一度に 1 画面ずつ表示する (**More**)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="19cd9-189">表示名 (姓と名) に基づいてアカウントのユーザープリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="19cd9-190">*$UserName*変数に入力し、文字を削除し \< and > ます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="19cd9-191">この例では、Caleb/Ls という名前のユーザーのユーザープリンシパル名を表示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="19cd9-192">*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="19cd9-193">次の例では、 *ベルギー*の使用場所を *フランス*に設定していますが、ユーザープリンシパル名ではなく、表示名を指定しています。</span><span class="sxs-lookup"><span data-stu-id="19cd9-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="19cd9-194">すべてのユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="19cd9-194">Change properties for all user accounts</span></span>

<span data-ttu-id="19cd9-195">すべてのユーザーのプロパティを変更するには、 **get-msoluser** コマンドレットと **get-msoluser** コマンドレットの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="19cd9-196">次の例では、すべてのユーザーの使用場所を *フランス*に変更します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="19cd9-197">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="19cd9-198">ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。</span><span class="sxs-lookup"><span data-stu-id="19cd9-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-199">ユーザーの所在地をフランスに設定します (**get-msoluser-@ location "FR"**)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="19cd9-200">特定のユーザー アカウント セットのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="19cd9-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="19cd9-201">特定のユーザーアカウントセットのプロパティを変更するには、 **get-msoluser**、 **Where**、および **get-msoluser** コマンドレットの組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="19cd9-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="19cd9-202">次の例では、経理部門のすべてのユーザーの使用場所を *フランス*に変更します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="19cd9-203">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="19cd9-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="19cd9-204">ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。</span><span class="sxs-lookup"><span data-stu-id="19cd9-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-205">*Department*プロパティが "Accounting" に設定されているすべてのユーザーアカウントを検索**します (Where {$ _)。Department-eq "Accounting"}**) を行い、結果の情報を次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="19cd9-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="19cd9-206">ユーザーの所在地をフランスに設定します (**get-msoluser-@ location "FR"**)。</span><span class="sxs-lookup"><span data-stu-id="19cd9-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="19cd9-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="19cd9-207">See also</span></span>

[<span data-ttu-id="19cd9-208">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="19cd9-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="19cd9-209">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="19cd9-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="19cd9-210">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="19cd9-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
