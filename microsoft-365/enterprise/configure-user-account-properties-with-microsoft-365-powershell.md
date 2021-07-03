---
title: PowerShell Microsoft 365ユーザー アカウントのプロパティを構成する
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
description: PowerShell を使用して、Microsoft 365テナント内の個々または複数のユーザー アカウントのプロパティMicrosoft 365します。
ms.openlocfilehash: aeb9b586c42a0bdfb8d69b8d297998fedc1124e6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286011"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="20ea9-103">PowerShell Microsoft 365ユーザー アカウントのプロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="20ea9-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="20ea9-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="20ea9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="20ea9-105">このプロパティを使用Microsoft 365 管理センターテナントのユーザー アカウントのプロパティをMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="20ea9-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="20ea9-106">PowerShell では、管理センターで実行できないその他の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="20ea9-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="20ea9-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="20ea9-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="20ea9-108">Graph モジュールの Azure Active Directory PowerShell でユーザー アカウントのプロパティを構成するには [**、Set-AzureADUser**](/powershell/module/azuread/set-azureaduser)コマンドレットを使用して、設定または変更するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="20ea9-109">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="20ea9-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="20ea9-110">特定のユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="20ea9-110">Change properties for a specific user account</span></span>

<span data-ttu-id="20ea9-111">-ObjectID パラメーターを使用してアカウント *を識別* し、追加のパラメーターを使用して特定のプロパティを設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="20ea9-112">最も一般的なパラメーターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="20ea9-113">-Department "<部署名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-113">-Department "\<department name>"</span></span>

- <span data-ttu-id="20ea9-114">-DisplayName "<完全なユーザー名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-114">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="20ea9-115">-FacsimilieTelephoneNumber "<FAX 番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>

- <span data-ttu-id="20ea9-116">-GivenName "<ユーザーの名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-116">-GivenName "\<user first name>"</span></span>

- <span data-ttu-id="20ea9-117">-Surname "<ユーザーの姓>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-117">-Surname "\<user last name>"</span></span>

- <span data-ttu-id="20ea9-118">-Mobile "<携帯電話番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-118">-Mobile "\<mobile phone number>"</span></span>

- <span data-ttu-id="20ea9-119">-JobTitle "<役職>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-119">-JobTitle "\<job title>"</span></span>

- <span data-ttu-id="20ea9-120">-PreferredLanguage "<言語>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-120">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="20ea9-121">-StreetAddress "<番地>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-121">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="20ea9-122">-City "<市区町村名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-122">-City "\<city name>"</span></span>

- <span data-ttu-id="20ea9-123">-State "<都道府県名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-123">-State "\<state name>"</span></span>

- <span data-ttu-id="20ea9-124">-PostalCode "<郵便番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-124">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="20ea9-125">-Country "<国名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-125">-Country "\<country name>"</span></span>

- <span data-ttu-id="20ea9-126">-TelephoneNumber "<勤務先電話番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-126">-TelephoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="20ea9-127">-UsageLocation \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="20ea9-127">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="20ea9-128">これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。</span><span class="sxs-lookup"><span data-stu-id="20ea9-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="20ea9-129">その他のパラメーターについては [、「Set-AzureADUser」を参照してください](/powershell/module/azuread/set-azureaduser)。</span><span class="sxs-lookup"><span data-stu-id="20ea9-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser).</span></span>

> [!NOTE]
> <span data-ttu-id="20ea9-130">ユーザー アカウントにライセンスを割り当てる前に、使用場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ea9-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>

<span data-ttu-id="20ea9-131">ユーザー アカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="20ea9-132">このコマンドは、PowerShell に次の指示を行います。</span><span class="sxs-lookup"><span data-stu-id="20ea9-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20ea9-133">ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-134">ユーザー プリンシパル名の一覧をアルファベット順に並べ替え (**Sort UserPrincipalName**) し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-135">各アカウントの [ユーザー プリンシパル名] プロパティ **([UserPrincipalName** の選択]) を表示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="20ea9-136">一度に 1 画面ずつ表示する (**More**)。</span><span class="sxs-lookup"><span data-stu-id="20ea9-136">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="20ea9-137">表示名 (名と名) に基づいてアカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="20ea9-138">変数を入力 *$userName、* 次の文字を削除 \< and > します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="20ea9-139">次の使用例は、表示名 *Caleb Sills* を持つユーザー アカウントのユーザー プリンシパル名を表示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="20ea9-140">*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="20ea9-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="20ea9-141">Belinda *Newman* の使用場所をフランスに設定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="20ea9-142">ただし、ユーザー プリンシパル名ではなく、表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="20ea9-143">すべてのユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="20ea9-143">Change properties for all user accounts</span></span>

<span data-ttu-id="20ea9-144">すべてのユーザーのプロパティを変更するには **、Get-AzureADUser** コマンドレットと **Set-AzureADUser** コマンドレットを組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="20ea9-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="20ea9-145">次の使用例は、すべてのユーザーの使用場所をフランスに変更 *します*。</span><span class="sxs-lookup"><span data-stu-id="20ea9-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="20ea9-146">このコマンドは、PowerShell に次の指示を行います。</span><span class="sxs-lookup"><span data-stu-id="20ea9-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20ea9-147">ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-148">ユーザーの場所をフランス **(Set-AzureADUser -UsageLocation "FR") に設定します**。</span><span class="sxs-lookup"><span data-stu-id="20ea9-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="20ea9-149">特定のユーザー アカウント セットのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="20ea9-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="20ea9-150">ユーザー アカウントの特定のセットのプロパティを変更するには **、Get-AzureADUser** コマンドレット **、Where** コマンドレット **、Set-AzureADUser** コマンドレットを組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="20ea9-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="20ea9-151">次の使用例は、経理部門のすべてのユーザーの使用場所をフランスに変更 *します*。</span><span class="sxs-lookup"><span data-stu-id="20ea9-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="20ea9-152">このコマンドは、PowerShell に次の指示を行います。</span><span class="sxs-lookup"><span data-stu-id="20ea9-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20ea9-153">ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>

1.  <span data-ttu-id="20ea9-154">Department プロパティが "Accounting"  **(Where {$_) に設定されているすべてのユーザー アカウントを検索します。Department -eq "Accounting"} )** をクリックし、結果の情報を次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-155">ユーザーの場所をフランス **(Set-AzureADUser -UsageLocation "FR") に設定します**。</span><span class="sxs-lookup"><span data-stu-id="20ea9-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="20ea9-156">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="20ea9-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="20ea9-157">Windows PowerShell 用の Microsoft Azure Active Directory モジュールを使用してユーザー アカウントのプロパティを構成するには **、Set-MsolUser** コマンドレットを使用して、設定または変更するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="20ea9-158">最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="20ea9-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
> [!NOTE]
> <span data-ttu-id="20ea9-159">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="20ea9-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="20ea9-160">これらのコマンドレットは、Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-160">Run these cmdlets from Windows PowerShell.</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="20ea9-161">特定のユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="20ea9-161">Change properties for a specific user account</span></span>

<span data-ttu-id="20ea9-162">特定のユーザー アカウントのプロパティを構成するには [**、Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) コマンドレットを使用し、設定または変更するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="20ea9-163">*-UserPrincipalName* パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="20ea9-164">最も一般的なパラメーターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="20ea9-165">-City "<市区町村名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-165">-City "\<city name>"</span></span>

- <span data-ttu-id="20ea9-166">-Country "<国名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-166">-Country "\<country name>"</span></span>

- <span data-ttu-id="20ea9-167">-Department "<部署名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-167">-Department "\<department name>"</span></span>

- <span data-ttu-id="20ea9-168">-DisplayName "<完全なユーザー名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-168">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="20ea9-169">-Fax "<fax 番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-169">-Fax "\<fax number>"</span></span>

- <span data-ttu-id="20ea9-170">-FirstName "<ユーザーの名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-170">-FirstName "\<user first name>"</span></span>

- <span data-ttu-id="20ea9-171">-LastName "<ユーザーの姓>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-171">-LastName "\<user last name>"</span></span>

- <span data-ttu-id="20ea9-172">-MobilePhone "<モバイル機器の番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-172">-MobilePhone "\<mobile phone number>"</span></span>

- <span data-ttu-id="20ea9-173">-Office "<事業所の場所>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-173">-Office "\<office location>"</span></span>

- <span data-ttu-id="20ea9-174">-PhoneNumber "<勤務先電話番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-174">-PhoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="20ea9-175">-PostalCode "<郵便番号>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-175">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="20ea9-176">-PreferredLanguage "<言語>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-176">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="20ea9-177">-State "<都道府県名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-177">-State "\<state name>"</span></span>

- <span data-ttu-id="20ea9-178">-StreetAddress "<番地>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-178">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="20ea9-179">-Title "<役職名>"</span><span class="sxs-lookup"><span data-stu-id="20ea9-179">-Title "\<title name>"</span></span>

- <span data-ttu-id="20ea9-180">-UsageLocation \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="20ea9-180">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="20ea9-181">これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。</span><span class="sxs-lookup"><span data-stu-id="20ea9-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="20ea9-182">その他のパラメーターについては [、「Set-MsolUser」を参照してください](/previous-versions/azure/dn194136(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="20ea9-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="20ea9-183">すべてのユーザーのユーザー プリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="20ea9-184">このコマンドは、PowerShell に次の指示を行います。</span><span class="sxs-lookup"><span data-stu-id="20ea9-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20ea9-185">ユーザー アカウント **(Get-MsolUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-186">ユーザー プリンシパル名の一覧をアルファベット順に並べ替え (**Sort UserPrincipalName**) し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-187">各アカウントの [ユーザー プリンシパル名] プロパティ **([UserPrincipalName** の選択]) を表示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="20ea9-188">一度に 1 画面ずつ表示する (**More**)。</span><span class="sxs-lookup"><span data-stu-id="20ea9-188">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="20ea9-189">表示名 (名と名) に基づいてアカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="20ea9-190">変数 *に$userNameし* 、文字を削除 \< and > します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="20ea9-191">次の使用例は、Caleb Sills という名前のユーザーのユーザー プリンシパル名を表示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="20ea9-192">*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="20ea9-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="20ea9-193">Belinda *Newman* の使用場所をフランスに設定し、ユーザープリンシパル名ではなく表示名を指定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="20ea9-194">すべてのユーザー アカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="20ea9-194">Change properties for all user accounts</span></span>

<span data-ttu-id="20ea9-195">すべてのユーザーのプロパティを変更するには **、Get-MsolUser** コマンドレットと **Set-MsolUser** コマンドレットを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="20ea9-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="20ea9-196">次の使用例は、すべてのユーザーの使用場所をフランスに変更 *します*。</span><span class="sxs-lookup"><span data-stu-id="20ea9-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="20ea9-197">このコマンドは、PowerShell に次の指示を行います。</span><span class="sxs-lookup"><span data-stu-id="20ea9-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20ea9-198">ユーザー アカウント **(Get-MsolUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-199">ユーザーの場所をフランス **(Set-MsolUser -UsageLocation "FR") に設定します**。</span><span class="sxs-lookup"><span data-stu-id="20ea9-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="20ea9-200">特定のユーザー アカウント セットのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="20ea9-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="20ea9-201">特定の一連のユーザー アカウントのプロパティを変更するには **、Get-MsolUser** コマンドレット **、Where** コマンドレット **、Set-MsolUser** コマンドレットを組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="20ea9-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="20ea9-202">次の使用例は、経理部門のすべてのユーザーの使用場所をフランスに変更 *します*。</span><span class="sxs-lookup"><span data-stu-id="20ea9-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="20ea9-203">このコマンドは、PowerShell に次の指示を行います。</span><span class="sxs-lookup"><span data-stu-id="20ea9-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="20ea9-204">ユーザー アカウント **(Get-MsolUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-205">Department プロパティが *"Accounting"* **(Where {$_) に設定されているすべてのユーザー アカウントを検索します。Department -eq "Accounting"}**) をクリックし、結果の情報を次のコマンド ( ) に送信します **|** 。</span><span class="sxs-lookup"><span data-stu-id="20ea9-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="20ea9-206">ユーザーの場所をフランス **(Set-MsolUser -UsageLocation "FR") に設定します**。</span><span class="sxs-lookup"><span data-stu-id="20ea9-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="20ea9-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="20ea9-207">See also</span></span>

[<span data-ttu-id="20ea9-208">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="20ea9-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="20ea9-209">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="20ea9-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="20ea9-210">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="20ea9-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
