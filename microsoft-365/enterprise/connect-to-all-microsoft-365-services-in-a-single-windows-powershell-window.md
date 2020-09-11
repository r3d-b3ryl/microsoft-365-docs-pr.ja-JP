---
title: 単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
ms.openlocfilehash: 08d2f4c6ce67aa9fea196d56b2eb5f36a36d7943
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430048"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="6230b-103">単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="6230b-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="6230b-104">PowerShell を使用して Microsoft 365 を管理する場合は、ユーザー アカウントの管理、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams、セキュリティ&amp;コンプライアンス センターに対応する別の PowerShell ウィンドウで複数の PowerShell セッションを同時に開くことができます。</span><span class="sxs-lookup"><span data-stu-id="6230b-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="6230b-105">サービス間管理のためにウィンドウ間でデータを交換できないため、これは Microsoft 365 の管理に最適な状況ではありません。</span><span class="sxs-lookup"><span data-stu-id="6230b-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="6230b-106">このトピックでは、Microsoft 365 アカウント、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams、セキュリティ&amp;コンプライアンス センターを管理する PowerShell の単一のインスタンスを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6230b-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="6230b-107">この記事には現在、ワールドワイド (+ GCC) クラウドに接続するコマンドのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="6230b-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="6230b-108">メモでは、他の Microsoft 365 クラウドへの接続に関する情報が掲載されている記事へのリンクを提供しています。</span><span class="sxs-lookup"><span data-stu-id="6230b-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="6230b-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="6230b-109">Before you begin</span></span>

<span data-ttu-id="6230b-110">PowerShell の単一のインスタンスからすべての Microsoft 365 を管理する前に、次の前提条件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="6230b-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="6230b-111">これらの手順に使用する Microsoft 365 の職場または学校のアカウントは、Microsoft 365 管理者ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6230b-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="6230b-112">詳細については、[「管理者の役割について」](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6230b-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="6230b-113">これは Microsoft 365向け PowerShell の要件であり、他のすべての Microsoft 365 サービスについては必ずしも当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="6230b-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="6230b-114">次の Windows の 64 ビット バージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6230b-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="6230b-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6230b-115">Windows 10</span></span>
    
  - <span data-ttu-id="6230b-116">Windows 8.1 または Windows 8</span><span class="sxs-lookup"><span data-stu-id="6230b-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="6230b-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6230b-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="6230b-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6230b-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="6230b-119">Windows Server 2012 R2 または Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6230b-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="6230b-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="6230b-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="6230b-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="6230b-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="6230b-122">\*Microsoft .NET Framework 4.5.*x* をインストールしてから、Windows Management Framework 3.0 または Windows Management Framework 4.0 のどちらかをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6230b-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="6230b-123">詳細については、「[.NET Framework のインストール](https://go.microsoft.com/fwlink/p/?LinkId=257868)」と、「[Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757)」または「[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6230b-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="6230b-124">Skype for Business Online モジュール、および Microsoft 365 モジュールの要件のため、64 ビット バージョンの Windows を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6230b-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="6230b-125">Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online、および Teams に必要なモジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6230b-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="6230b-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="6230b-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="6230b-127">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="6230b-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="6230b-128">Skype for Business Online、PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="6230b-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="6230b-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="6230b-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="6230b-130">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="6230b-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="6230b-131">Skype for Business Online やセキュリティ&amp;コンプライアンス センターに対して署名付きスクリプトを実行するよう PowerShell を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6230b-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="6230b-132">そのためには、管理者特権の PowerShell セッション (**[管理者として実行]** を選択して開く PowerShell ウィンドウ) で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6230b-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="6230b-133">Exchange Online およびセキュリティ &amp; コンプライアンス センターと Exchange Online PowerShell V2 モジュール</span><span class="sxs-lookup"><span data-stu-id="6230b-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="6230b-134">この記事では、Exchange Online PowerShell V2 モジュールを使用して、Exchange Online とセキュリティ &amp; コンプライアンス センターの両方に接続します。</span><span class="sxs-lookup"><span data-stu-id="6230b-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="6230b-135">ただし、現時点では、**同じ PowerShell ウィンドウで** Exchange Online とセキュリティ &amp; コンプライアンス センターの両方に接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="6230b-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="6230b-136">したがって、複数の Microsoft 365 サービスの PowerShell ウィンドウを構成する場合は、Exchange Online *または*セキュリティ &amp; コンプライアンス センターとの接続を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6230b-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="6230b-137">パスワードだけを使用する場合の接続手順</span><span class="sxs-lookup"><span data-stu-id="6230b-137">Connection steps when using just a password</span></span>

<span data-ttu-id="6230b-138">ここでは、サインインにパスワードだけを使用する場合に、単一の PowerShell ウィンドウ内ですべてのサービスに接続するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="6230b-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="6230b-139">Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="6230b-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="6230b-140">次のコマンドを実行し、Microsoft 365職場または学校のアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6230b-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="6230b-141">次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールを使用して Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="6230b-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="6230b-142">または、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールを使用する場合、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6230b-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="6230b-143">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6230b-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6230b-144">これらのコマンドレットを引き続き使用するには、PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6230b-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="6230b-145">次のコマンドを実行して、SharePoint Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="6230b-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="6230b-146">ドメインの組織名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6230b-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="6230b-147">たとえば、"litwareinc.onmicrosoft.com" の場合、組織名の値は "litwareinc" です。</span><span class="sxs-lookup"><span data-stu-id="6230b-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="6230b-p109">次のコマンドを実行して、Skype for Business Online に接続します。初めて接続する場合、`WSMan NetworkDelayms` の値を増やすようにという警告が出ますが、無視してください。</span><span class="sxs-lookup"><span data-stu-id="6230b-p109">Run these commands to connect to Skype for Business Online. A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="6230b-150">次のコマンドを実行して、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="6230b-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="6230b-151">全世界以外の Exchange Online for Microsoft 365 クラウドに接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6230b-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="6230b-152">あるいは、次のコマンドを実行して、セキュリティ &amp; コンプライアンス センター に接続します。</span><span class="sxs-lookup"><span data-stu-id="6230b-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="6230b-153">Microsoft 365 クラウド向けセキュリティ &amp; コンプライアンス センターに接続するには、[「セキュリティ/コンプライアンス センター PowerShell に接続する」](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6230b-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="6230b-154">次のコマンドを実行して、Teams PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="6230b-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="6230b-155">全世界以外の Microsoft Teams クラウドに接続する方法については、[「Connect-MicrosoftTeams」](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6230b-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6230b-156">Graph 用 Azure Active Directory PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="6230b-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6230b-157">以下は、Graph 用 Azure Active Directory PowerShell モジュールを使用する場合の、単一のブロック内の*セキュリティ &amp; コンプライアンス センターを除く*すべてのサービスのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="6230b-158">ドメイン ホストの名前を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="6230b-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="6230b-159">以下は、Graph 用 Azure Active Directory PowerShell モジュールを使用する場合の、単一のブロック内の *Exchange Online を除く*すべてのサービスのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="6230b-160">ドメイン ホストの名前とサインインの UPN を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="6230b-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="6230b-161">Windows PowerShell 用 Microsoft Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="6230b-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="6230b-162">以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する場合の、単一のブロック内の*セキュリティ &amp; コンプライアンス センターを除く*すべてのサービスのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="6230b-163">ドメイン ホストの名前を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="6230b-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="6230b-164">以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する場合の、単一のブロック内の *Exchange Online を除く*すべてのサービスのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="6230b-165">ドメイン ホストの名前とサインインの UPN を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="6230b-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="6230b-166">多要素認証を使用する場合の接続手順</span><span class="sxs-lookup"><span data-stu-id="6230b-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6230b-167">Graph 用 Azure Active Directory PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="6230b-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6230b-168">以下は、Graph 用 Azure Active Directory PowerShell モジュールを使用した多要素認証を使用して、*セキュリティ &amp; コンプライアンス センターを除く*複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="6230b-169">以下は、Graph 用 Azure Active Directory PowerShell モジュールを使用した多要素認証を使用して、*Exchange Online を除く*複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="6230b-170">Windows PowerShell 用 Microsoft Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="6230b-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="6230b-171">以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用した多要素認証を使用して、*セキュリティ &amp; コンプライアンス センターを除く*複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="6230b-172">以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用した多要素認証を使用して、*Exchange Online を除く*複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6230b-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="6230b-173">PowerShell ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="6230b-173">Close the PowerShell window</span></span>

<span data-ttu-id="6230b-174">PowerShell ウィンドウを閉じる準備が整った段階で次のコマンドを実行し、Skype for Business Online、および Teams に対するアクティブなセッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="6230b-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="6230b-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="6230b-175">See also</span></span>

- [<span data-ttu-id="6230b-176">PowerShell を使用して Microsoft 365 に接続する</span><span class="sxs-lookup"><span data-stu-id="6230b-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="6230b-177">PowerShell を使用して SharePoint Online を管理する</span><span class="sxs-lookup"><span data-stu-id="6230b-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="6230b-178">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="6230b-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
