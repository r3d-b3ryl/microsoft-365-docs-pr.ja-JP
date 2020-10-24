---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントを作成する
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell を使用して、個別または複数の Microsoft 365 ユーザーアカウントを作成する方法。
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754212"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="c0495-103">PowerShell を使用して Microsoft 365 ユーザーアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="c0495-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="c0495-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="c0495-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c0495-105">Microsoft 365 の PowerShell を使用すると、複数のアカウントを含むユーザーアカウントを効率的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="c0495-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="c0495-106">PowerShell でユーザーアカウントを作成する場合、特定のアカウントのプロパティが常に必要です。</span><span class="sxs-lookup"><span data-stu-id="c0495-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="c0495-107">その他のプロパティは必須ではありませんが、重要です。</span><span class="sxs-lookup"><span data-stu-id="c0495-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="c0495-108">次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0495-108">See the following table.</span></span>
  
|<span data-ttu-id="c0495-109">**プロパティ名**</span><span class="sxs-lookup"><span data-stu-id="c0495-109">**Property name**</span></span>|<span data-ttu-id="c0495-110">**必須**</span><span class="sxs-lookup"><span data-stu-id="c0495-110">**Required?**</span></span>|<span data-ttu-id="c0495-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="c0495-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0495-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="c0495-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="c0495-113">はい</span><span class="sxs-lookup"><span data-stu-id="c0495-113">Yes</span></span>  <br/> |<span data-ttu-id="c0495-114">これは、Microsoft 365 サービスで使用される表示名です。</span><span class="sxs-lookup"><span data-stu-id="c0495-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="c0495-115">たとえば、 *Caleb が ls*というようになります。</span><span class="sxs-lookup"><span data-stu-id="c0495-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="c0495-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="c0495-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="c0495-117">はい</span><span class="sxs-lookup"><span data-stu-id="c0495-117">Yes</span></span>  <br/> |<span data-ttu-id="c0495-118">これは、Microsoft 365 サービスへのサインインに使用されるアカウント名です。</span><span class="sxs-lookup"><span data-stu-id="c0495-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="c0495-119">たとえば、 *Calebs \@ contoso.onmicrosoft.com*などです。</span><span class="sxs-lookup"><span data-stu-id="c0495-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="c0495-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="c0495-120">**FirstName**</span></span> <br/> |<span data-ttu-id="c0495-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0495-121">No</span></span>  <br/> ||
|<span data-ttu-id="c0495-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="c0495-122">**LastName**</span></span> <br/> |<span data-ttu-id="c0495-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0495-123">No</span></span>  <br/> ||
|<span data-ttu-id="c0495-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="c0495-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="c0495-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0495-125">No</span></span>  <br/> |<span data-ttu-id="c0495-126">これは、使用可能なライセンスがユーザーアカウントに割り当てられているライセンスプラン (ライセンスプランまたは SKU とも呼ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="c0495-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="c0495-127">ライセンスでは、アカウントで利用できる Microsoft 365 サービスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="c0495-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="c0495-128">アカウントを作成するときに、ユーザーにライセンスを割り当てる必要はありませんが、そのアカウントには Microsoft 365 サービスにアクセスするためのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c0495-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="c0495-129">ユーザー アカウントにライセンスを割り当てる期間は作成後 30 日です。</span><span class="sxs-lookup"><span data-stu-id="c0495-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="c0495-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="c0495-130">**Password**</span></span> <br/> |<span data-ttu-id="c0495-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0495-131">No</span></span>  <br/> | <span data-ttu-id="c0495-132">パスワードを指定しない場合、ランダムなパスワードがユーザー アカウントに割り当てられ、パスワードはコマンドの結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0495-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="c0495-133">パスワードを指定する場合は、次の種類の 8 ~ 16 文字の ASCII テキスト文字である必要があります。小文字、大文字、数字、記号。</span><span class="sxs-lookup"><span data-stu-id="c0495-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="c0495-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="c0495-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="c0495-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0495-135">No</span></span>  <br/> |<span data-ttu-id="c0495-136">これは有効な ISO 3166-1 alpha 国コードです。</span><span class="sxs-lookup"><span data-stu-id="c0495-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="c0495-137">たとえば、米国 *の場合* は、フランスの *FR* の場合はというようになります。</span><span class="sxs-lookup"><span data-stu-id="c0495-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="c0495-138">一部の Microsoft 365 サービスは特定の国では利用できないため、この値を提供することは重要です。</span><span class="sxs-lookup"><span data-stu-id="c0495-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="c0495-139">アカウントでこの値が構成されていない限り、ユーザーアカウントにライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="c0495-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="c0495-140">詳細については、「 [ライセンス制限につい](https://go.microsoft.com/fwlink/p/?LinkId=691730)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0495-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="c0495-141">Microsoft 365 管理センターを使用して[ユーザーアカウントを作成する方法について説明](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)します。</span><span class="sxs-lookup"><span data-stu-id="c0495-141">[Learn how to create user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="c0495-142">その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0495-142">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c0495-143">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="c0495-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c0495-144">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="c0495-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="c0495-145">接続した後、次の構文を使用して個別のアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0495-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="c0495-146">この例では、US user *Caleb ls*のアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0495-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c0495-147">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="c0495-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c0495-148">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="c0495-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="c0495-149">個別のユーザー アカウントの作成</span><span class="sxs-lookup"><span data-stu-id="c0495-149">Create an individual user account</span></span>

<span data-ttu-id="c0495-150">個別のアカウントを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0495-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="c0495-151">PowerShell Core は、Windows PowerShell モジュールの Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c0495-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="c0495-152">これらのコマンドレットを Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="c0495-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="c0495-153">使用可能なライセンスのプラン名を一覧表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0495-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="c0495-154">この例では、US user *Caleb ls*のアカウントを作成し、 `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) ライセンスプランからライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c0495-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="c0495-155">複数のユーザー アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="c0495-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="c0495-p108">必要なユーザー アカウント情報を含むコンマ区切り (CSV) ファイルを作成します。例:</span><span class="sxs-lookup"><span data-stu-id="c0495-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="c0495-158">CSV ファイルの最初の行にある列の名前と順序は任意です。</span><span class="sxs-lookup"><span data-stu-id="c0495-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="c0495-159">ただし、他のファイル内のデータの順序が列名の順序と一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c0495-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="c0495-160">また、Microsoft 365 コマンドの PowerShell でパラメーター値の列名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0495-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="c0495-161">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c0495-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="c0495-162">この例では、ファイル *C:\My Documents\NewAccounts.csv* からユーザーアカウントを作成し、 *C:\My Documents\NewAccountResults.csv*という名前のファイルに結果を記録します。</span><span class="sxs-lookup"><span data-stu-id="c0495-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="c0495-163">出力ファイルで結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="c0495-163">Review the output file to see the results.</span></span> <span data-ttu-id="c0495-164">パスワードを指定していないため、Microsoft 365 によって生成されたランダムなパスワードが出力ファイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0495-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c0495-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0495-165">See also</span></span>

[<span data-ttu-id="c0495-166">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="c0495-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c0495-167">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="c0495-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c0495-168">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c0495-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
