---
title: PowerShell を使用して Microsoft 365 に接続する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Microsoft 365 テナントに接続するには、Microsoft 365 用 PowerShell を使用して、コマンド ラインから管理センターのタスクを実行します。
ms.openlocfilehash: 33f9af45418ae8a1f126d2b321e7246201bd1f6e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002407"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="10c64-103">PowerShell を使用して Microsoft 365 に接続する</span><span class="sxs-lookup"><span data-stu-id="10c64-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="10c64-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="10c64-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="10c64-105">Microsoft 365 用 PowerShell では、コマンド ラインから Microsoft 365 の設定を管理することが可能です。</span><span class="sxs-lookup"><span data-stu-id="10c64-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="10c64-106">PowerShell への接続は、必要なソフトウェアをインストールして、Microsoft 365 の組織に接続するだけです。</span><span class="sxs-lookup"><span data-stu-id="10c64-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="10c64-107">Microsoft 365 および管理者のユーザー アカウント、グループ、ライセンスへの接続に使用可能な PowerShell モジュールには、次の 2 つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="10c64-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="10c64-108">コマンドレット名に *AzureAD* が含まれる Graph 用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="10c64-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="10c64-109">コマンドレット名に *Msol* が含まれる Windows PowerShell 用 Microsoft Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="10c64-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="10c64-110">現時点で、Graph 用 Azure Active Directory PowerShell モジュールは、ユーザー、グループ、およびライセンスの管理について Windows PowerShell 用 Microsoft Azure Active Directory モジュールの機能に完全に置き換わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="10c64-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="10c64-111">場合によっては、両方のバージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="10c64-112">両バージョンを同じコンピューターに安全にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="10c64-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="10c64-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="10c64-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="10c64-114">**オペレーティング システム**</span><span class="sxs-lookup"><span data-stu-id="10c64-114">**Operating system**</span></span>

<span data-ttu-id="10c64-115">64 ビット版の Windows を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="10c64-116">Microsoft PowerShell 用 Microsoft Azure Active Directory モジュール の 32 ビット 版のサポートは、2014 年で終了しました。</span><span class="sxs-lookup"><span data-stu-id="10c64-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="10c64-117">次の Windows のバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="10c64-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="10c64-118">Windows 10、Windows 8.1、Windows 8、または Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="10c64-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="10c64-119">Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="10c64-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="10c64-120">Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012、および Windows Server 2008 R2 SP1 の場合は、[Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="10c64-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="10c64-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="10c64-121">**PowerShell**</span></span>

- <span data-ttu-id="10c64-122">Graph 用 Azure Active Directory PowerShell モジュールでは、PowerShell バージョン 5.1 以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="10c64-123">Windows PowerShell 用 Microsoft Azure Active Directory モジュールでは、PowerShell バージョン 5.1 から PowerShell バージョン 6 までを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="10c64-124">PowerShell バージョン 7 は使用できません。</span><span class="sxs-lookup"><span data-stu-id="10c64-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="10c64-125">これらの手順は、Microsoft 365 の管理者の役割を持つユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="10c64-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="10c64-126">詳細については、[「管理者の役割について」](https://go.microsoft.com/fwlink/p/?LinkId=532367) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c64-126">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="10c64-127">Graph 用 Azure Active Directory PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="10c64-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="10c64-128">Graph 用 Azure Active Directory PowerShell モジュールのコマンドには、コマンドレット名に *AzureAD* が含まれます。</span><span class="sxs-lookup"><span data-stu-id="10c64-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="10c64-129">[Graph 用 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) モジュールか [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps) をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="10c64-129">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="10c64-130">Graph 用 Azure Active Directory PowerShell モジュールにおいて新しいコマンドレットを必要とするプロシージャについては、以下の手順に従い、モジュールをインストールし、Microsoft 365 サブスクリプションに接続します。</span><span class="sxs-lookup"><span data-stu-id="10c64-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="10c64-131">Windows のさまざまなバージョンに対するサポート情報については、「[Graph 用 Azure Active Directory PowerShell モジュール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c64-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="10c64-132">手順 1: 必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="10c64-132">Step 1: Install the required software</span></span>

<span data-ttu-id="10c64-133">これらの手順は、お使いのコンピューターで一度だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="10c64-134">ただし、定期的にソフトウェアを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="10c64-135">管理者特権で Windows PowerShell コマンド プロンプト ウィンドウを開きます (Windows PowerShell を管理者として実行)。</span><span class="sxs-lookup"><span data-stu-id="10c64-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="10c64-136">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="10c64-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="10c64-137">信頼されていないリポジトリからモジュールをインストールするようにメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="10c64-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="10c64-138">手順 2: Microsoft 365 サブスクリプション用の Azure AD に接続する</span><span class="sxs-lookup"><span data-stu-id="10c64-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="10c64-139">アカウント名とパスワードまたは多要素認証を使用して Microsoft 365 サブスクリプション用の Azure Active Directory (Azure AD) に接続するには、Windows PowerShell コマンド プロンプトから次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="10c64-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="10c64-140">(昇格する必要はありません。)</span><span class="sxs-lookup"><span data-stu-id="10c64-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="10c64-141">Office 365 のクラウド</span><span class="sxs-lookup"><span data-stu-id="10c64-141">Office 365 cloud</span></span> | <span data-ttu-id="10c64-142">コマンド</span><span class="sxs-lookup"><span data-stu-id="10c64-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="10c64-143">Office 365 ワールドワイド (+GCC)</span><span class="sxs-lookup"><span data-stu-id="10c64-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="10c64-144">21 Vianet が運営する Office 365</span><span class="sxs-lookup"><span data-stu-id="10c64-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="10c64-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="10c64-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="10c64-146">Office 365 U.S. Government DoD と Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="10c64-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="10c64-147">[**アカウントにサインイン**] ダイアログ ボックスで、Microsoft 365 の職場または学校のアカウントのユーザー名とパスワードを入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="10c64-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="10c64-148">多要素認証を使用している場合は、手順に従って確認コードなどの追加認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="10c64-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="10c64-149">接続後は、[Graph 用 Azure Active Directory PowerShell モジュール](https://docs.microsoft.com/powershell/module/azuread)のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="10c64-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="10c64-150">Windows PowerShell 用 Microsoft Azure Active Directory モジュールとの接続</span><span class="sxs-lookup"><span data-stu-id="10c64-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="10c64-151">Windows PowerShell 用 Microsoft Azure Active Directory モジュールには、コマンドレット名に *Msol* が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10c64-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="10c64-152">PowerShell バージョン 7 以降は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="10c64-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="10c64-153">PowerShell バージョン 7 以降では、Graph 用 Azure Active Directory PowerShell モジュールか Azure PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="10c64-154">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="10c64-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="10c64-155">これらのコマンドレットは、Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="10c64-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="10c64-156">手順 1: 必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="10c64-156">Step 1: Install the required software</span></span>

<span data-ttu-id="10c64-157">これらの手順は、お使いのコンピューターで一度だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="10c64-158">ただし、定期的にソフトウェアを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c64-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="10c64-159">Windows 10を実行中でない場合は、Microsoft Online Services サインイン アシスタントの 64 ビット版をインストールします: [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152)。</span><span class="sxs-lookup"><span data-stu-id="10c64-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="10c64-160">以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="10c64-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="10c64-161">管理者特権で Windows PowerShell コマンド プロンプトを開きます (Windows PowerShell を管理者として実行)。</span><span class="sxs-lookup"><span data-stu-id="10c64-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="10c64-162">**Install-Module MSOnline** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="10c64-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="10c64-163">NuGet プロバイダーをインストールするようにメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="10c64-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="10c64-164">PSGallery からモジュールをインストールするようにメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="10c64-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="10c64-165">手順 2: Microsoft 365 サブスクリプション用の Azure AD に接続する</span><span class="sxs-lookup"><span data-stu-id="10c64-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="10c64-166">アカウント名とパスワードまたは多要素認証を使用して Microsoft 365 サブスクリプション用の Azure AD に接続するには、Windows PowerShell コマンド プロンプトから次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="10c64-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="10c64-167">(昇格する必要はありません。)</span><span class="sxs-lookup"><span data-stu-id="10c64-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="10c64-168">Office 365 のクラウド</span><span class="sxs-lookup"><span data-stu-id="10c64-168">Office 365 cloud</span></span> | <span data-ttu-id="10c64-169">コマンド</span><span class="sxs-lookup"><span data-stu-id="10c64-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="10c64-170">Office 365 ワールドワイド (+GCC)</span><span class="sxs-lookup"><span data-stu-id="10c64-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="10c64-171">21 Vianet が運営する Office 365</span><span class="sxs-lookup"><span data-stu-id="10c64-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="10c64-172">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="10c64-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="10c64-173">Office 365 U.S. Government DoD と Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="10c64-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="10c64-174">[**アカウントにサインイン**] ダイアログ ボックスで、Microsoft 365 の職場または学校のアカウントのユーザー名とパスワードを入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="10c64-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="10c64-175">多要素認証を使用している場合は、手順に従って確認コードなどの追加認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="10c64-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="10c64-176">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="10c64-176">How do you know it worked?</span></span>

<span data-ttu-id="10c64-177">エラー メッセージが表示されなければ、正常に接続されています。</span><span class="sxs-lookup"><span data-stu-id="10c64-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="10c64-178">簡単に確かめるには、**Get-MsolUser** などの Microsoft 365 コマンドレットを実行して結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="10c64-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="10c64-179">エラー メッセージが表示される場合は、次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="10c64-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="10c64-180">**よくある原因は、正しくないパスワードです**。</span><span class="sxs-lookup"><span data-stu-id="10c64-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="10c64-181">[手順 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) をもう一度実行し、その際入力するユーザー名とパスワードには特に注意します。</span><span class="sxs-lookup"><span data-stu-id="10c64-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="10c64-182">**Windows PowerShell 用 Microsoft Azure Active Directory モジュールには、Microsoft .NET Framework 3.5 が必要です。お使いのコンピューターで* x* が有効になっています**。コンピューターにより新しいバージョンがインストールされている可能性があります (4 または 4.5.* x* など)。</span><span class="sxs-lookup"><span data-stu-id="10c64-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="10c64-183">ただし、以前の .NET Framework のバージョンとの下位互換性を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="10c64-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="10c64-184">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c64-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="10c64-185">Windows Server 2012 または Windows Server 2012 R2 の場合は、「[役割と機能の追加ウィザードを使用して .NET Framework 3.5 を有効にする](https://go.microsoft.com/fwlink/p/?LinkId=532368)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c64-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span></span>
    
  - <span data-ttu-id="10c64-186">Windows 7 または Windows Server 2008 R2 の場合は、「[Windows PowerShell 用 Azure Active Directory モジュールを開くことができない](https://go.microsoft.com/fwlink/p/?LinkId=532370)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c64-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span></span>

  - <span data-ttu-id="10c64-187">Windows 10、Windows 8.1、および Windows 8 の場合は、「[Windows 8、Windows 8.1、および Windows 10 への .NET Framework 3.5 のインストール](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c64-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="10c64-188">**お使いの Windows PowerShell 用 Microsoft Azure Active Directory モジュールのバージョンは期限切れの可能性があります。**</span><span class="sxs-lookup"><span data-stu-id="10c64-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="10c64-189">Microsoft 365用または PowerShell または Windows PowerShell 用 Microsoft Azure Active Directory モジュールで、次のコマンドを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="10c64-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="10c64-190">返されたバージョン番号が *1.0.8070.2* より小さい場合は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールをアンインストールして、上の[手順 1](#step-1-install-the-required-software) からインストールします。</span><span class="sxs-lookup"><span data-stu-id="10c64-190">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="10c64-191">**接続エラーが発生した場合** は、["Connect-MsolService: 例外がスローされました" というエラー](https://go.microsoft.com/fwlink/p/?LinkId=532377)に関するトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="10c64-191">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="10c64-192">**「Get-Item: パスが見つかりません」エラーが表示された場合** は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="10c64-192">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="10c64-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="10c64-193">See also</span></span>

- [<span data-ttu-id="10c64-194">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="10c64-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="10c64-195">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="10c64-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="10c64-196">単一の Windows PowerShell ウィンドウですべての Microsoft 365 サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="10c64-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
