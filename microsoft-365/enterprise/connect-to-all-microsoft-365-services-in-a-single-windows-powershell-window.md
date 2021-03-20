---
title: 単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
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
ms.openlocfilehash: 18ff8e1789242b4dde3b4b31aaccf2462e4c5d74
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905130"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="85e07-103">単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="85e07-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="85e07-104">PowerShell を使用して Microsoft 365 を管理する場合は、同時に複数の PowerShell セッションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="85e07-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="85e07-105">ユーザー アカウント、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams、セキュリティ &amp; コンプライアンス センターを管理するために、異なる PowerShell ウィンドウが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="85e07-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="85e07-106">このシナリオでは、サービス間管理のためにウィンドウ間でデータを交換できないため、Microsoft 365 の管理に最適な状況ではありません。</span><span class="sxs-lookup"><span data-stu-id="85e07-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="85e07-107">この記事では、Microsoft 365 アカウント、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams、セキュリティ &amp; コンプライアンス センターを管理する PowerShell の単一のインスタンスを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85e07-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="85e07-108">この記事には現在、ワールドワイド (+ GCC) クラウドに接続するコマンドのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="85e07-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="85e07-109">メモでは、他の Microsoft 365 クラウドへの接続に関する記事へのリンクを提供しています。</span><span class="sxs-lookup"><span data-stu-id="85e07-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="85e07-110">開始する前に</span><span class="sxs-lookup"><span data-stu-id="85e07-110">Before you begin</span></span>

<span data-ttu-id="85e07-111">PowerShell の単一のインスタンスからすべての Microsoft 365 を管理する前に、次の前提条件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="85e07-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="85e07-112">Microsoft 365 の職場または学校のアカウントは、Microsoft 365 管理者ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e07-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="85e07-113">詳細については、[「管理者の役割について」](../admin/add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e07-113">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span> <span data-ttu-id="85e07-114">これは Microsoft 365向け PowerShell の要件ではあるものの、他のすべての Microsoft 365 サービスについては必ずしも当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="85e07-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="85e07-115">次の Windows の 64 ビット バージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="85e07-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="85e07-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="85e07-116">Windows 10</span></span>
    
  - <span data-ttu-id="85e07-117">Windows 8.1 または Windows 8</span><span class="sxs-lookup"><span data-stu-id="85e07-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="85e07-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="85e07-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="85e07-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="85e07-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="85e07-120">Windows Server 2012 R2 または Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="85e07-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="85e07-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="85e07-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="85e07-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="85e07-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="85e07-123">\*Microsoft .NET Framework 4.5 をインストールする必要があります。*x* と、Windows Management Framework 3.0 または4.0 です。</span><span class="sxs-lookup"><span data-stu-id="85e07-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="85e07-124">詳細については、 [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e07-124">For more information, see [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="85e07-125">Skype for Business Online モジュール、および Microsoft 365 モジュールの要件のため、64 ビット バージョンの Windows を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e07-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="85e07-126">Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online、および Teams に必要なモジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e07-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="85e07-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="85e07-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="85e07-128">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="85e07-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="85e07-129">Skype for Business Online、PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="85e07-129">Skype for Business Online, PowerShell Module</span></span>](/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="85e07-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="85e07-130">Exchange Online PowerShell V2</span></span>](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="85e07-131">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="85e07-131">Teams PowerShell Overview</span></span>](/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="85e07-132">Skype for Business Online やセキュリティ&amp;コンプライアンス センターに対して署名付きスクリプトを実行するよう PowerShell を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e07-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="85e07-133">管理者特権の PowerShell セッション (**管理者として実行** する PowerShell セッション) で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="85e07-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="85e07-134">パスワードだけを使用する場合の接続手順</span><span class="sxs-lookup"><span data-stu-id="85e07-134">Connection steps when using just a password</span></span>

<span data-ttu-id="85e07-135">サインインにパスワードだけを使用する場合に、単一の PowerShell ウィンドウ内ですべてのサービスに接続するための次のような手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="85e07-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="85e07-136">Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="85e07-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="85e07-137">次のコマンドを実行し、Microsoft 365職場または学校のアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="85e07-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="85e07-138">次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールを使用して Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="85e07-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="85e07-139">または、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールを使用する場合、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="85e07-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="85e07-140">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="85e07-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="85e07-141">これらのコマンドレットは、PowerShell から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e07-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="85e07-142">次のコマンドを実行して、SharePoint Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="85e07-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="85e07-143">ドメインの組織名を指定します。</span><span class="sxs-lookup"><span data-stu-id="85e07-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="85e07-144">たとえば、"litwareinc\.onmicrosoft.com" の場合、組織名の値は "litwareinc" です。</span><span class="sxs-lookup"><span data-stu-id="85e07-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="85e07-145">次のコマンドを実行して、Skype for Business Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="85e07-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="85e07-146">初めて接続したときには、`WSMan NetworkDelayms` 値の増加に関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="85e07-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="85e07-147">それは無視します。</span><span class="sxs-lookup"><span data-stu-id="85e07-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="85e07-148">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="85e07-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="85e07-149">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="85e07-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. <span data-ttu-id="85e07-150">次のコマンドを実行して、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="85e07-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="85e07-151">全世界以外の Exchange Online for Microsoft 365 クラウドに接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85e07-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="85e07-152">次のコマンドを実行して、セキュリティ &amp; コンプライアンス センター に接続します。</span><span class="sxs-lookup"><span data-stu-id="85e07-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="85e07-153">Microsoft 365 クラウド向けセキュリティ &amp; コンプライアンス センターに接続するには、[「セキュリティ/コンプライアンス センター PowerShell に接続する」](/powershell/exchange/connect-to-scc-powershell) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e07-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="85e07-154">次のコマンドを実行して、Teams PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="85e07-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="85e07-155">*全世界* 以外の Microsoft Teams クラウドに接続する方法については、[「Connect-MicrosoftTeams」](/powershell/module/teams/connect-microsoftteams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e07-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</span></span>
  



### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="85e07-156">Graph 用 Azure Active Directory PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="85e07-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="85e07-157">以下は、Graph 用 Azure Active Directory PowerShell モジュールを使用する場合の、単一のブロック内のすべてのサービスのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="85e07-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="85e07-158">ドメイン ホストの名前とサインインの UPN を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="85e07-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="85e07-159">Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="85e07-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="85e07-160">以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する場合の、単一のブロック内のすべてのサービスのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="85e07-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="85e07-161">ドメイン ホストの名前とサインインの UPN を指定してから、それらすべてを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="85e07-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="85e07-162">多要素認証を使用する場合の接続手順</span><span class="sxs-lookup"><span data-stu-id="85e07-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="85e07-163">Graph 用 Azure Active Directory PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="85e07-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="85e07-164">以下は、Graph モジュール用 Azure Active Directory PowerShell で多要素認証を使用する場合に、複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="85e07-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="85e07-165">Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="85e07-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="85e07-166">以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールで多要素認証を使用する場合に、複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。</span><span class="sxs-lookup"><span data-stu-id="85e07-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="85e07-167">PowerShell ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="85e07-167">Close the PowerShell window</span></span>

<span data-ttu-id="85e07-168">PowerShell ウィンドウを閉じるために、次のコマンドを実行して Skype for Business Online、および Teams に対するアクティブなセッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="85e07-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="85e07-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="85e07-169">See also</span></span>

- [<span data-ttu-id="85e07-170">PowerShell を使用して Microsoft 365 に接続する</span><span class="sxs-lookup"><span data-stu-id="85e07-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="85e07-171">PowerShell を使用して SharePoint Online を管理する</span><span class="sxs-lookup"><span data-stu-id="85e07-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="85e07-172">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="85e07-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)