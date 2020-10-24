---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントを表示する
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: PowerShell を使用して、Microsoft 365 ユーザーアカウントをさまざまな方法で表示、一覧表示、または表示する方法について説明します。
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754074"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="f4ead-103">PowerShell を使用して Microsoft 365 ユーザーアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="f4ead-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="f4ead-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f4ead-105">Microsoft 365 管理センターを使用して、Microsoft 365 テナントのアカウントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="f4ead-106">Microsoft 365 の PowerShell は、これを可能にしますが、その他の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f4ead-107">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="f4ead-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f4ead-108">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="f4ead-109">すべてのアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-109">View all accounts</span></span>

<span data-ttu-id="f4ead-110">ユーザーアカウントの完全な一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="f4ead-111">次のような情報が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="f4ead-112">特定のアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-112">View a specific account</span></span>

<span data-ttu-id="f4ead-113">特定のユーザーアカウントを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="f4ead-114">ユーザーアカウントのサインインアカウント名を入力します。これは、ユーザープリンシパル名 (UPN) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="f4ead-115">"<" および ">" 文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="f4ead-116">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="f4ead-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="f4ead-117">特定のアカウントの追加のプロパティ値を表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-117">View additional property values for a specific account</span></span>

<span data-ttu-id="f4ead-118">既定では、 **set-azureaduser** コマンドレットでは、アカウントの *ObjectID*、 *DisplayName*、および *UserPrincipalName* のプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="f4ead-119">表示するプロパティをより詳細に選択するには、 **Select** コマンドレットを **set-azureaduser** コマンドレットと組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="f4ead-120">2つのコマンドレットを組み合わせるには、"pipe" 文字 ("|") を使用します。これは、1つのコマンドの結果を取得して次のコマンドに送信するために、Azure Active Directory PowerShell に対してグラフを表示するように指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f4ead-121">次に、すべてのユーザーアカウントの *DisplayName*、 *Department*、および使用 *場所* を表示するコマンドの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="f4ead-122">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f4ead-123">ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信します ( **|** )。</span><span class="sxs-lookup"><span data-stu-id="f4ead-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="f4ead-124">ユーザーアカウント名、部署、および使用場所のみを表示します (**DisplayName、department、および使用場所を選択し**ます)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="f4ead-125">特定のユーザーアカウントのすべてのプロパティを表示するには、 **Select** コマンドレットとワイルドカード文字 (\*) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="f4ead-126">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="f4ead-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f4ead-127">別の例として、次のコマンドを実行して、特定のユーザーアカウントの有効な状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="f4ead-128">アカウントの同期状態を表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-128">View account synchronization status</span></span>

<span data-ttu-id="f4ead-129">ユーザーアカウントには2つのソースがあります。</span><span class="sxs-lookup"><span data-stu-id="f4ead-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="f4ead-130">Windows Server Active Directory (AD)。これは、オンプレミス AD からクラウドに同期するアカウントです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="f4ead-131">Azure Active Directory (Azure AD) AD アカウント。クラウドに直接作成されます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="f4ead-132">次のコマンドは、 *Dirsyncenabled* 属性が *True*に設定されているすべてのユーザーを取得するように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="f4ead-133">これを使用して、オンプレミスの AD から同期しているアカウントを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="f4ead-134">次のコマンドは、 *Dirsyncenabled* 属性が *False*に設定されているすべてのユーザーを取得するように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="f4ead-135">これを使用して、クラウド専用のアカウントを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="f4ead-136">共通プロパティに基づいてアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-136">View accounts based on a common property</span></span>

<span data-ttu-id="f4ead-137">表示するアカウントの一覧をより詳細に選択できるようにするには、 **set-azureaduser**コマンドレットと組み合わせて**Where**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="f4ead-138">2つのコマンドレットを組み合わせるには、"pipe" 文字 ("|") を使用します。これは、1つのコマンドの結果を取得して次のコマンドに送信するために、Azure Active Directory PowerShell に対してグラフを表示するように指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f4ead-139">次に示すのは、指定されていない使用場所を持つユーザーアカウントのみを表示するコマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="f4ead-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="f4ead-140">次のコマンドは、Azure Active Directory PowerShell を Graph に対して次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="f4ead-141">ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信します ( **|** )。</span><span class="sxs-lookup"><span data-stu-id="f4ead-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f4ead-142">使用できない場所が指定されているすべてのユーザーアカウントを検索し**ます (Where {$ \_ .の場合は、-eq $Null}**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="f4ead-143">中かっこの内側では、コマンドは、アクセス先ユーザーアカウントプロパティ (で使用するアカウントのセットのみを検索するように PowerShell に指示し\*\* $ \_ ます。\*\* は、無効な場所) を指定しません (**-eq $Null**)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="f4ead-144">使用 **場所** プロパティは、ユーザーアカウントに関連付けられている多くのプロパティのうちの1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="f4ead-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="f4ead-145">特定のユーザーアカウントのすべてのプロパティを表示するには、 **Select** コマンドレットとワイルドカード文字 (\*) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="f4ead-146">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="f4ead-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f4ead-147">たとえば、 **City** はユーザーアカウントプロパティの名前です。</span><span class="sxs-lookup"><span data-stu-id="f4ead-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="f4ead-148">London に居住しているユーザーのすべてのアカウントを一覧表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="f4ead-149">これらの例の **where** コマンドレットの構文は、 **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="f4ead-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="f4ead-150">[ユーザーアカウントのプロパティ名][比較演算子]金額 **}**. > [比較演算子] は、equals、 **-ne** for not equals、 **-lt** (より小さい、-gt (より大きい)、- **gt** (より大きい)、およびその他の場合に- **eq**を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="f4ead-151">[value] は通常、文字列 (一連の文字、数字、その他の文字)、数値、または **$Null** 指定なしの場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="f4ead-152">詳細については、「 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ead-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f4ead-153">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="f4ead-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f4ead-154">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="f4ead-155">すべてのアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-155">View all accounts</span></span>

<span data-ttu-id="f4ead-156">ユーザーアカウントの完全な一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="f4ead-157">PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f4ead-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f4ead-158">これらのコマンドレットを Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="f4ead-159">次のような情報が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="f4ead-160">**Get-MsolUser** コマンドレットには、表示するユーザー アカウントのセットをフィルターにかけるための一連のパラメーターもあります。</span><span class="sxs-lookup"><span data-stu-id="f4ead-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="f4ead-161">たとえば、ライセンスのないユーザー (Microsoft 365 に追加されていても、サービスのいずれかを使用するライセンスを持っていないユーザー) の一覧については、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="f4ead-162">次のような情報が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="f4ead-163">表示されるユーザーアカウントのセットをフィルター処理するための追加パラメーターの詳細については、「 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ead-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="f4ead-164">特定のアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-164">View a specific account</span></span>

<span data-ttu-id="f4ead-165">特定のユーザーアカウントを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="f4ead-166">ユーザーアカウントのサインイン名を入力します。これは、ユーザープリンシパル名 (UPN) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="f4ead-167">"<" および ">" 文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="f4ead-168">共通プロパティに基づいてアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-168">View accounts based on a common property</span></span>

<span data-ttu-id="f4ead-169">表示するアカウントの一覧をより詳細に選択できるようにするには、 **get-msoluser**コマンドレットと組み合わせて**Where**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="f4ead-170">2つのコマンドレットを組み合わせるには、"pipe" 文字 ("|") を使用します。これは、1つのコマンドの結果を受け取って次のコマンドに送信するように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f4ead-171">次に示すのは、指定されていない使用場所を持つユーザーアカウントのみを表示する例です。</span><span class="sxs-lookup"><span data-stu-id="f4ead-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="f4ead-172">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f4ead-173">ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。</span><span class="sxs-lookup"><span data-stu-id="f4ead-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f4ead-174">使用できない場所が指定されているすべてのユーザーアカウントを検索**します (Where {$ \_ .の場合は、-eq $Null}**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="f4ead-175">中かっこ内では、コマンドによって、アクセス先ユーザーアカウントプロパティ (で使用されるアカウントのセットのみを検索するように PowerShell に指示し\*\* $ \_ ます。\*\* は、無効な場所) を指定しません (**-eq $Null**)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="f4ead-176">次のような情報が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="f4ead-177">使用 *場所* プロパティは、ユーザーアカウントに関連付けられている多くのプロパティのうちの1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="f4ead-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="f4ead-178">ユーザーアカウントのすべてのプロパティを表示するには、 **Select** コマンドレットとワイルドカード文字 (\*) を使用して、特定のユーザーアカウントについてすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="f4ead-179">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="f4ead-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f4ead-180">たとえば、 *City* はユーザーアカウントプロパティの名前です。</span><span class="sxs-lookup"><span data-stu-id="f4ead-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="f4ead-181">London に居住しているユーザーのすべてのユーザーアカウントを一覧表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="f4ead-182">これらの例の **where** コマンドレットの構文は、 **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="f4ead-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="f4ead-183">[ユーザーアカウントのプロパティ名][比較演算子]金額 **}**.</span><span class="sxs-lookup"><span data-stu-id="f4ead-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="f4ead-184">[comparison operator] は **-eq** (等しい)、 **-ne** for not equals、 **-lt** (より小さい)、- **gt** (より大きい)、または他のものです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="f4ead-185">[value] は通常、文字列 (一連の文字、数字、その他の文字)、数値、または **$Null** 指定なしの場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="f4ead-186">詳細については、「 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ead-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="f4ead-187">ユーザーアカウントのブロックされた状態を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="f4ead-188">アカウントの追加のプロパティ値を表示する</span><span class="sxs-lookup"><span data-stu-id="f4ead-188">View additional property values for accounts</span></span>

<span data-ttu-id="f4ead-189">既定では、 **get-msoluser** コマンドレットでは、ユーザーアカウントの次の3つのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="f4ead-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f4ead-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="f4ead-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f4ead-191">DisplayName</span></span>
    
- <span data-ttu-id="f4ead-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="f4ead-192">isLicensed</span></span>
    
<span data-ttu-id="f4ead-193">ユーザーが機能する部署や、Microsoft 365 サービスを使用する国/地域など、追加のプロパティが必要な場合は、 **get-msoluser** を **Select** コマンドレットと組み合わせて実行し、ユーザーアカウントのプロパティの一覧を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="f4ead-194">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="f4ead-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="f4ead-195">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f4ead-196">ユーザーアカウントに関するすべての情報を取得し (**get-msoluser**)、次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="f4ead-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f4ead-197">ユーザーアカウント名、部署、および使用場所のみを表示します (**DisplayName、department、および使用場所を選択し**ます)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="f4ead-198">次のような情報が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="f4ead-199">**Select**コマンドレットを使用すると、表示するプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="f4ead-200">特定のユーザーアカウントのすべてのプロパティを表示するには、ワイルドカード文字 (\*) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="f4ead-201">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="f4ead-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f4ead-202">表示するアカウントのリストをより詳細に選択できるようにするには、 **Where** コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="f4ead-203">次に示すのは、指定されていない使用場所を持つユーザーアカウントのみを表示するコマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="f4ead-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="f4ead-204">次のコマンドは、PowerShell に次のように指示します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f4ead-205">ユーザーアカウントに関するすべての情報を取得し (**get-msoluser**)、次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="f4ead-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f4ead-206">使用できない場所が指定されているすべてのユーザーアカウントを検索**します (Where {$ \_ .[実行場所-eq $Null}**)] を指定して、結果の情報を次のコマンドに送信し **|** ます ()。</span><span class="sxs-lookup"><span data-stu-id="f4ead-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="f4ead-207">中かっこの内側では、コマンドは、アクセス先ユーザーアカウントプロパティ (で使用するアカウントのセットのみを検索するように PowerShell に指示し\*\* $ \_ ます。\*\* は、無効な場所) を指定しません (**-eq $Null**)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="f4ead-208">ユーザーアカウント名、部署、および使用場所のみを表示します (**DisplayName、department、および使用場所を選択し**ます)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="f4ead-209">次のような情報が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f4ead-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="f4ead-210">ディレクトリ同期を使用して Microsoft 365 ユーザーを作成および管理している場合は、Microsoft 365 ユーザーが射影されているローカルアカウントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="f4ead-211">次の例では、このことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f4ead-211">The following example assumes that:</span></span>

- <span data-ttu-id="f4ead-212">Azure AD Connect は、ObjectGUID の既定のソースアンカーを使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="f4ead-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="f4ead-213">(ソースアンカーの構成の詳細については、「 [AZURE AD Connect: デザインの概念](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="f4ead-214">PowerShell の Active Directory ドメインサービスモジュールがインストールされていること (「 [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f4ead-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="f4ead-215">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4ead-215">See also</span></span>

[<span data-ttu-id="f4ead-216">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="f4ead-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f4ead-217">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="f4ead-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f4ead-218">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="f4ead-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
