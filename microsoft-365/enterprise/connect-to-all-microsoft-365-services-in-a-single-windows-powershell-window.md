---
title: 単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: '概要: 単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続します。'
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307627"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="918d3-103">単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="918d3-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="918d3-104">PowerShell を使用して Microsoft 365 を管理する場合は、ユーザー アカウントの管理、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams、セキュリティ&amp;コンプライアンス センターに対応する別の PowerShell ウィンドウで複数の PowerShell セッションを同時に開くことができます。</span><span class="sxs-lookup"><span data-stu-id="918d3-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="918d3-105">サービス間管理のためにウィンドウ間でデータを交換できないため、これは Microsoft 365 の管理に最適な状況ではありません。</span><span class="sxs-lookup"><span data-stu-id="918d3-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="918d3-106">このトピックでは、Microsoft 365 アカウント、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams、セキュリティ&amp;コンプライアンス センターを管理する PowerShell の単一のインスタンスを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="918d3-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="918d3-107">この記事には現在、ワールドワイド (+ GCC) クラウドに接続するコマンドのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="918d3-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="918d3-108">メモでは、他の Microsoft 365 クラウドへの接続に関する情報が掲載されている記事へのリンクを提供しています。</span><span class="sxs-lookup"><span data-stu-id="918d3-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="918d3-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="918d3-109">Before you begin</span></span>

<span data-ttu-id="918d3-110">PowerShell の単一のインスタンスからすべての Microsoft 365 を管理する前に、次の前提条件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="918d3-111">これらの手順に使用する Microsoft 365 の職場または学校のアカウントは、Microsoft 365 管理者ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="918d3-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="918d3-112">詳細については、[「管理者の役割について」](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="918d3-113">これは Microsoft 365向け PowerShell の要件であり、他のすべての Microsoft 365 サービスについては必ずしも当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="918d3-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="918d3-114">次の Windows の 64 ビット バージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="918d3-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="918d3-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="918d3-115">Windows 10</span></span>
    
  - <span data-ttu-id="918d3-116">Windows 8.1 または Windows 8</span><span class="sxs-lookup"><span data-stu-id="918d3-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="918d3-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="918d3-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="918d3-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="918d3-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="918d3-119">Windows Server 2012 R2 または Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="918d3-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="918d3-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="918d3-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="918d3-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="918d3-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="918d3-122">\*Microsoft .NET Framework 4.5.*x* をインストールしてから、Windows Management Framework 3.0 または Windows Management Framework 4.0 のどちらかをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="918d3-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="918d3-123">詳細については、「[.NET Framework のインストール](https://go.microsoft.com/fwlink/p/?LinkId=257868)」と、「[Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757)」または「[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="918d3-124">Skype for Business Online モジュール、および Microsoft 365 モジュールの要件のため、64 ビット バージョンの Windows を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="918d3-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="918d3-125">Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online、および Teams に必要なモジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="918d3-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="918d3-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="918d3-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="918d3-127">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="918d3-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="918d3-128">Skype for Business Online、PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="918d3-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="918d3-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="918d3-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="918d3-130">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="918d3-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="918d3-131">Skype for Business Online やセキュリティ&amp;コンプライアンス センターに対して署名付きスクリプトを実行するよう PowerShell を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="918d3-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="918d3-132">そのためには、管理者特権の PowerShell セッション (**[管理者として実行]** を選択して開く PowerShell ウィンドウ) で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="918d3-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="918d3-133">パスワードだけを使用する場合の接続手順</span><span class="sxs-lookup"><span data-stu-id="918d3-133">Connection steps when using just a password</span></span>

<span data-ttu-id="918d3-134">ここでは、サインインにパスワードだけを使用する場合に、単一の PowerShell ウィンドウ内ですべてのサービスに接続するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="918d3-134">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="918d3-135">Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="918d3-135">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="918d3-136">次のコマンドを実行し、Microsoft 365職場または学校のアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="918d3-136">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="918d3-137">次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールを使用して Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="918d3-137">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="918d3-138">また、PowerShell モジュール用の Microsoft Azure Active Directory モジュールを使用する場合には、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="918d3-138">Alternately, if you are using the Microsoft Azure Active Directory Module for PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="918d3-139">PowerShell Core は、PowerShell モジュール用の Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="918d3-139">PowerShell Core does not support the Microsoft Azure Active Directory Module for PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="918d3-140">これらのコマンドレットを引き続き使用するには、PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="918d3-140">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="918d3-141">次のコマンドを実行して、SharePoint Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="918d3-141">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="918d3-142">ドメインの組織名を指定します。</span><span class="sxs-lookup"><span data-stu-id="918d3-142">Specify the organization name for your domain.</span></span> <span data-ttu-id="918d3-143">たとえば、"litwareinc.onmicrosoft.com" の場合、組織名の値は "litwareinc" です。</span><span class="sxs-lookup"><span data-stu-id="918d3-143">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="918d3-p108">次のコマンドを実行して、Skype for Business Online に接続します。初めて接続する場合、`WSMan NetworkDelayms` の値を増やすようにという警告が出ますが、無視してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-p108">Run these commands to connect to Skype for Business Online. A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="918d3-146">次のコマンドを実行して、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="918d3-146">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="918d3-147">全世界以外の Exchange Online for Microsoft 365 クラウドに接続するには、**-ExchangeEnvironmentName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="918d3-147">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="918d3-148">詳細については、[「Connect-ExchangeOnline」](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-148">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="918d3-149">次のコマンドを実行して、Teams PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="918d3-149">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="918d3-150">全世界以外の Microsoft Teams クラウドに接続する方法については、[「Connect-MicrosoftTeams」](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-150">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="918d3-151">次のコマンドを実行して、セキュリティ &amp; コンプライアンス センター に接続します。</span><span class="sxs-lookup"><span data-stu-id="918d3-151">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="918d3-152">Microsoft 365 クラウド向けセキュリティ &amp; コンプライアンス センターに接続するには、[「セキュリティ/コンプライアンス センター PowerShell に接続する」](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-152">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="918d3-153">Azure Active Directory PowerShell for Graph モジュールを使用しているときに、単一のブロック内のすべてのコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="918d3-153">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="918d3-154">ドメイン ホストの名前を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="918d3-154">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="918d3-155">または、PowerShell モジュール用の Microsoft Azure Active Directory モジュールを使用しているときに、ここには単一のブロック内のすべてのコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="918d3-155">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span> <span data-ttu-id="918d3-156">ドメイン ホストの名前を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="918d3-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="918d3-157">PowerShell ウィンドウを閉じる準備が整った段階で次のコマンドを実行し、Skype for Business Online、SharePoint Online、セキュリティ&amp;コンプライアンス センター、Teams に対するアクティブなセッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="918d3-157">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="918d3-158">多要素認証を使用する場合の接続手順</span><span class="sxs-lookup"><span data-stu-id="918d3-158">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="918d3-159">ここでは、Azure AD、SharePoint Online、Skype for Business、Exchange Online、および Azure Active Directory PowerShell for Graph モジュールを使用する単一のウィンドウ内で多要素認証を使用する Teams に接続するすべてのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="918d3-159">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="918d3-160">ユーザー アカウントのユーザー プリンシパル名 (UPN)、およびドメインのホスト名を指定し、一度にそれらを実行します。</span><span class="sxs-lookup"><span data-stu-id="918d3-160">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="918d3-161">また、ここには PowerShell モジュール用の Microsoft Azure Active Directory モジュールを使用する場合のすべてのコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="918d3-161">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="918d3-162">セキュリティ &amp; コンプライアンス センター向けに、多要素認証を使用して接続する方法は、[「多要素認証を使用してセキュリティ/コンプライアンス センター PowerShell に接続する」](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918d3-162">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="918d3-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="918d3-163">See also</span></span>

- [<span data-ttu-id="918d3-164">PowerShell を使用して Microsoft 365 に接続する</span><span class="sxs-lookup"><span data-stu-id="918d3-164">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="918d3-165">PowerShell を使用して SharePoint Online を管理する</span><span class="sxs-lookup"><span data-stu-id="918d3-165">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="918d3-166">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="918d3-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
