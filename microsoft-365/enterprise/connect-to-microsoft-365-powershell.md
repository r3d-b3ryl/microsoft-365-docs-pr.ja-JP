---
title: PowerShell を使用して Microsoft 365 に接続する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
ms.openlocfilehash: 6b8f98441c7d727984bde8775dea496a9324d50c
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053061"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="f0e99-103">PowerShell を使用して Microsoft 365 に接続する</span><span class="sxs-lookup"><span data-stu-id="f0e99-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="f0e99-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="f0e99-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f0e99-105">Microsoft 365 用 PowerShell では、コマンド ラインから Microsoft 365 の設定を管理することが可能です。</span><span class="sxs-lookup"><span data-stu-id="f0e99-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="f0e99-106">PowerShell への接続は、必要なソフトウェアをインストールして、Microsoft 365 の組織に接続するだけです。</span><span class="sxs-lookup"><span data-stu-id="f0e99-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="f0e99-107">Microsoft 365 および管理者のユーザー アカウント、グループ、ライセンスへの接続に使用可能な PowerShell モジュールには、次の 2 つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="f0e99-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="f0e99-108">コマンドレット名に *AzureAD* が含まれる Graph 用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e99-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="f0e99-109">コマンドレット名に *Msol* が含まれる Windows PowerShell 用 Microsoft Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="f0e99-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="f0e99-p102">現時点で、Graph 用 Azure Active Directory PowerShell モジュールは、ユーザー、グループ、およびライセンスの管理について Windows PowerShell 用 Microsoft Azure Active Directory モジュールの機能に完全に置き換わるものではありません。時には、両方のバージョンを使用する必要があります。同じコンピューターに両方のバージョンを安全にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-p102">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration. In some cases, you need to use both versions. You can safely install both versions on the same computer.</span></span>

>[!Note]
><span data-ttu-id="f0e99-113">また、Microsoft 365 管理センターで [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) と接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-113">You can also connect with the [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) from the Microsoft 365 admin center.</span></span>
>


## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0e99-114">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f0e99-114">What do you need to know before you begin?</span></span>


<span data-ttu-id="f0e99-115">**オペレーティング システム**</span><span class="sxs-lookup"><span data-stu-id="f0e99-115">**Operating system**</span></span>

<span data-ttu-id="f0e99-p103">64 ビット バージョンの Windows を使用する必要があります。Windows PowerShell 用の Microsoft Azure Active Directory モジュールの 32 ビット バージョンのサポートは 2014 年に終了しました。</span><span class="sxs-lookup"><span data-stu-id="f0e99-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="f0e99-118">次の Windows のバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="f0e99-119">Windows 10、Windows 8.1、Windows 8、または Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f0e99-119">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="f0e99-120">Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f0e99-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="f0e99-121">Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012、および Windows Server 2008 R2 SP1 の場合は、[Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0e99-121">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="f0e99-122">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f0e99-122">**PowerShell**</span></span>

- <span data-ttu-id="f0e99-123">Graph 用 Azure Active Directory PowerShell モジュールでは、PowerShell バージョン 5.1 以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e99-123">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="f0e99-p104">Windows PowerShell 用 Microsoft Azure Active Directory モジュールでは、PowerShell バージョン 5.1 から PowerShell バージョン 6 までを使用する必要があります。PowerShell バージョン 7 は使用できません。</span><span class="sxs-lookup"><span data-stu-id="f0e99-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="f0e99-126">これらの手順は、Microsoft 365 の管理者の役割を持つユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="f0e99-126">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="f0e99-127">詳細については、[「管理者の役割について」](../admin/add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-127">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f0e99-128">Graph 用 Azure Active Directory PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="f0e99-128">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f0e99-129">Graph 用 Azure Active Directory PowerShell モジュールのコマンドには、コマンドレット名に *AzureAD* が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-129">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="f0e99-130">[Graph 用 Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2) モジュールか [Azure PowerShell](/powershell/azure/install-az-ps) をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-130">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="f0e99-131">Graph 用 Azure Active Directory PowerShell モジュールにおいて新しいコマンドレットを必要とするプロシージャについては、以下の手順に従い、モジュールをインストールし、Microsoft 365 サブスクリプションに接続します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-131">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="f0e99-132">Windows のさまざまなバージョンに対するサポート情報については、「[Graph 用 Azure Active Directory PowerShell モジュール](/powershell/azure/active-directory/install-adv2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-132">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="f0e99-133">手順 1: 必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0e99-133">Step 1: Install the required software</span></span>

<span data-ttu-id="f0e99-134">これらの手順は、お使いのコンピューターで一度だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e99-134">These steps are required only one time on your computer.</span></span> <span data-ttu-id="f0e99-135">ただし、定期的にソフトウェアを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e99-135">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="f0e99-136">管理者特権で Windows PowerShell コマンド プロンプト ウィンドウを開きます (Windows PowerShell を管理者として実行)。</span><span class="sxs-lookup"><span data-stu-id="f0e99-136">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="f0e99-137">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-137">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="f0e99-138">既定では、PowerShell ギャラリー (PSGallery) は、**PowerShellGet** 用の信頼されたリポジトリとして構成されません。</span><span class="sxs-lookup"><span data-stu-id="f0e99-138">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="f0e99-139">初めて PSGallery を使用する場合は、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-139">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="f0e99-140">インストールを続行するには [**はい**] または [**すべてにはい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0e99-140">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="f0e99-141">手順 2: Microsoft 365 サブスクリプション用の Azure AD に接続する</span><span class="sxs-lookup"><span data-stu-id="f0e99-141">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="f0e99-p109">アカウント名とパスワードまたは多要素認証 (MFA) を使用して Microsoft 365 サブスクリプション用の Azure Active Directory (Azure AD) に接続するには、Windows PowerShell コマンド プロンプトから次のいずれかのコマンドを実行します (昇格する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f0e99-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="f0e99-144">Office 365 のクラウド</span><span class="sxs-lookup"><span data-stu-id="f0e99-144">Office 365 cloud</span></span> | <span data-ttu-id="f0e99-145">コマンド</span><span class="sxs-lookup"><span data-stu-id="f0e99-145">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="f0e99-146">Office 365 ワールドワイド (+GCC)</span><span class="sxs-lookup"><span data-stu-id="f0e99-146">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="f0e99-147">21 Vianet が運営する Office 365</span><span class="sxs-lookup"><span data-stu-id="f0e99-147">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="f0e99-148">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f0e99-148">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="f0e99-149">Office 365 U.S. Government DoD と Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="f0e99-149">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="f0e99-150">[**アカウントにサインイン**] ダイアログ ボックスで、Microsoft 365 の職場または学校のアカウントのユーザー名とパスワードを入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-150">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="f0e99-151">多要素認証を使用している場合は、手順に従って確認コードなどの追加認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-151">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="f0e99-152">接続後は、[Graph 用 Azure Active Directory PowerShell モジュール](/powershell/module/azuread)のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-152">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f0e99-153">Windows PowerShell 用 Microsoft Azure Active Directory モジュールとの接続</span><span class="sxs-lookup"><span data-stu-id="f0e99-153">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="f0e99-154">Windows PowerShell 用 Microsoft Azure Active Directory モジュールには、コマンドレット名に *Msol* が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0e99-154">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="f0e99-155">PowerShell バージョン 7 以降は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f0e99-155">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f0e99-156">PowerShell バージョン 7 以降では、Graph 用 Azure Active Directory PowerShell モジュールか Azure PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e99-156">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="f0e99-157">PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f0e99-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f0e99-158">これらのコマンドレットは、Windows PowerShell から実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-158">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="f0e99-159">手順 1: 必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0e99-159">Step 1: Install the required software</span></span>

<span data-ttu-id="f0e99-160">これらの手順は、お使いのコンピューターで一度だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e99-160">These steps are required only one time on your computer.</span></span> <span data-ttu-id="f0e99-161">ただし、定期的にソフトウェアを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e99-161">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="f0e99-162">Windows 10を実行中でない場合は、Microsoft Online Services サインイン アシスタントの 64 ビット版をインストールします: [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)。</span><span class="sxs-lookup"><span data-stu-id="f0e99-162">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="f0e99-163">以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0e99-163">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="f0e99-164">管理者特権で Windows PowerShell コマンド プロンプトを開きます (Windows PowerShell を管理者として実行)。</span><span class="sxs-lookup"><span data-stu-id="f0e99-164">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="f0e99-165">**Install-Module MSOnline** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-165">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="f0e99-166">NuGet プロバイダーをインストールするようにメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-166">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="f0e99-167">PSGallery からモジュールをインストールするようにメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-167">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="f0e99-168">手順 2: Microsoft 365 サブスクリプション用の Azure AD に接続する</span><span class="sxs-lookup"><span data-stu-id="f0e99-168">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="f0e99-p113">アカウント名とパスワードまたは多要素認証 (MFA) を使用して Microsoft 365 サブスクリプション用の Azure AD に接続するには、Windows PowerShell コマンド プロンプトから次のいずれかのコマンドを実行します (昇格する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f0e99-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="f0e99-171">Office 365 のクラウド</span><span class="sxs-lookup"><span data-stu-id="f0e99-171">Office 365 cloud</span></span> | <span data-ttu-id="f0e99-172">コマンド</span><span class="sxs-lookup"><span data-stu-id="f0e99-172">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="f0e99-173">Office 365 ワールドワイド (+GCC)</span><span class="sxs-lookup"><span data-stu-id="f0e99-173">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="f0e99-174">21 Vianet が運営する Office 365</span><span class="sxs-lookup"><span data-stu-id="f0e99-174">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="f0e99-175">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f0e99-175">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="f0e99-176">Office 365 U.S. Government DoD と Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="f0e99-176">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="f0e99-177">[**アカウントにサインイン**] ダイアログ ボックスで、Microsoft 365 の職場または学校のアカウントのユーザー名とパスワードを入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-177">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="f0e99-178">多要素認証を使用している場合は、手順に従って確認コードなどの追加認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-178">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="f0e99-179">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="f0e99-179">How do you know it worked?</span></span>

<span data-ttu-id="f0e99-180">エラー メッセージが表示されなければ、正常に接続されています。</span><span class="sxs-lookup"><span data-stu-id="f0e99-180">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="f0e99-181">簡単に確かめるには、**Get-MsolUser** などの Microsoft 365 コマンドレットを実行して結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-181">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="f0e99-182">エラー メッセージが表示される場合は、次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-182">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="f0e99-183">**よくある原因は、正しくないパスワードです**。</span><span class="sxs-lookup"><span data-stu-id="f0e99-183">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="f0e99-184">[手順 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) をもう一度実行し、その際入力するユーザー名とパスワードには特に注意します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-184">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="f0e99-185">**Windows PowerShell 用 Microsoft Azure Active Directory モジュールには、Microsoft .NET Framework 3.5 が必要です。お使いのコンピューターで* x* が有効になっています**。コンピューターにより新しいバージョンがインストールされている可能性があります (4 または 4.5.* x* など)。</span><span class="sxs-lookup"><span data-stu-id="f0e99-185">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="f0e99-186">ただし、以前の .NET Framework のバージョンとの下位互換性を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-186">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="f0e99-187">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-187">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="f0e99-188">Windows Server 2012 または Windows Server 2012 R2 の場合は、「[役割と機能の追加ウィザードを使用して .NET Framework 3.5 を有効にする](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-188">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="f0e99-189">Windows 7 または Windows Server 2008 R2 の場合は、「[Windows PowerShell 用 Azure Active Directory モジュールを開くことができない](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-189">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="f0e99-190">Windows 10、Windows 8.1、および Windows 8 の場合は、「[Windows 8、Windows 8.1、および Windows 10 への .NET Framework 3.5 のインストール](/dotnet/framework/install/dotnet-35-windows-10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-190">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="f0e99-191">**お使いの Windows PowerShell 用 Microsoft Azure Active Directory モジュールのバージョンは期限切れの可能性があります。**</span><span class="sxs-lookup"><span data-stu-id="f0e99-191">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="f0e99-192">Microsoft 365用または PowerShell または Windows PowerShell 用 Microsoft Azure Active Directory モジュールで、次のコマンドを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-192">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="f0e99-193">返されたバージョン番号が *1.0.8070.2* より小さい場合は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールをアンインストールして、上の [手順 1](#step-1-install-the-required-software) からインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0e99-193">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="f0e99-194">**接続エラーが発生した場合** は、["Connect-MsolService: 例外がスローされました" というエラー](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception)に関するトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-194">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="f0e99-195">**「Get-Item: パスが見つかりません」エラーが表示された場合** は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-195">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a><span data-ttu-id="f0e99-196">Azure Cloud Shell との接続</span><span class="sxs-lookup"><span data-stu-id="f0e99-196">Connect with the Azure Cloud Shell</span></span>

<span data-ttu-id="f0e99-197">Microsoft 365 管理センターで Azure Cloud Shell に接続して使用するには、タスク バーの右上にある PowerShell ウィンドウ アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-197">To connect with and use the Azure Cloud Shell from the Microsoft 365 admin center, select the PowerShell window icon from the upper-right corner of the task bar.</span></span> <span data-ttu-id="f0e99-198">**[Azure Cloud Shell へようこそ]** ウィンドウで、**PowerShell** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0e99-198">In the **Welcome to Azure Cloud Shell** pane, select **PowerShell**.</span></span>

<span data-ttu-id="f0e99-199">Microsoft 365 サブスクリプションに関連付けられた、組織のアクティブな Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="f0e99-199">You will need an active Azure subscription for your organization that is tied to your Microsoft 365 subscription.</span></span> <span data-ttu-id="f0e99-200">まだお持ちでない場合は、作成できます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-200">If you don't already have one, you can create one.</span></span> <span data-ttu-id="f0e99-201">Azure サブスクリプションを取得すると、PowerShell ウィンドウが開き、PowerShell のコマンドやスクリプトを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f0e99-201">Once you have an Azure subscription, a PowerShell window opens from which you can run PowerShell commands and scripts.</span></span>

<span data-ttu-id="f0e99-202">詳細については、「[Azure Cloud Shell](/azure/cloud-shell/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e99-202">For more information, see [Azure Cloud Shell](/azure/cloud-shell/overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0e99-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0e99-203">See also</span></span>

- [<span data-ttu-id="f0e99-204">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="f0e99-204">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f0e99-205">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="f0e99-205">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f0e99-206">単一の Windows PowerShell ウィンドウですべての Microsoft 365 サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="f0e99-206">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
