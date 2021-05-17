---
title: Microsoft 365 テスト環境のパスワード ハッシュ同期
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワード ハッシュ同期とサインインを構成して実例を示します。'
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921506"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f5f58-103">Microsoft 365 テスト環境のパスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="f5f58-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f5f58-104">*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*</span><span class="sxs-lookup"><span data-stu-id="f5f58-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f5f58-105">多くの組織では、Azure AD Connect とパスワード ハッシュ同期を使用して、オンプレミスの Active Directory Domain Services (AD DS) フォレスト内のアカウント セットを、Microsoft 365 サブスクリプションの Azure AD テナント内のアカウント セットに同期します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="f5f58-106">この記事では、テスト環境にパスワード ハッシュ同期を追加する方法Microsoft 365説明します。この構成になります。</span><span class="sxs-lookup"><span data-stu-id="f5f58-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="f5f58-108">このテスト環境のセットアップには、次の 3 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="f5f58-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="f5f58-109">フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="f5f58-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="f5f58-110">フェーズ 2: testlab ドメインを作成および登録する</span><span class="sxs-lookup"><span data-stu-id="f5f58-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="f5f58-111">フェーズ 3: APP1 に Azure AD Connect をインストールする</span><span class="sxs-lookup"><span data-stu-id="f5f58-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="f5f58-112">エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="f5f58-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="f5f58-113">フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="f5f58-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="f5f58-114">シミュレーションされたエンタープライズ ベース構成[の手順に](simulated-ent-base-configuration-microsoft-365-enterprise.md)従って、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f5f58-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="f5f58-115">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5f58-115">Your resulting configuration looks like this:</span></span>
  
![シミュレートされたエンタープライズ基本構成](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="f5f58-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="f5f58-118">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="f5f58-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="f5f58-119">Azure 仮想ネットワーク内の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。</span><span class="sxs-lookup"><span data-stu-id="f5f58-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="f5f58-120">DC1 は、パブリック ドメイン名を DS ドメイン< testlab.> ADコントローラーです。</span><span class="sxs-lookup"><span data-stu-id="f5f58-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="f5f58-121">フェーズ 2: testlab ドメインを作成および登録する</span><span class="sxs-lookup"><span data-stu-id="f5f58-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="f5f58-122">このフェーズでは、パブリック DNS ドメインを追加し、サブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="f5f58-123">まず、パブリック DNS 登録プロバイダーと一緒に、現在のドメイン名に基DNS ドメイン新しいパブリック ドメイン名を作成し、サブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="f5f58-124">パブリック ドメインに \**testlab.<*を使用することをお勧めします\* >\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5f58-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="f5f58-125">たとえば、パブリック ドメイン名が **<span>contoso</span>.com** の場合は、パブリック ドメイン名 **<span>testlab</span>.contoso.com を追加します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="f5f58-126">次に、ドメイン登録プロセスを<して、パブリック ドメイン ドメインの **testlab.Microsoft 365 >** 試用版または有料サブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="f5f58-127">これは、パブリック ドメイン ドメインの **testlab.<DNS レコードを追加 *することで構成* >** されます。</span><span class="sxs-lookup"><span data-stu-id="f5f58-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="f5f58-128">詳細については、「Add [a domain to Microsoft 365」 を参照してください](../admin/setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="f5f58-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="f5f58-129">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5f58-129">Your resulting configuration looks like this:</span></span>
  
![testlab ドメイン名の登録](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="f5f58-131">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-131">This configuration consists of:</span></span>

- <span data-ttu-id="f5f58-132">testlab.Microsoft 365 E5の試用版または有料サブスクリプションDNS ドメイン、<ドメイン名が>されます。 </span><span class="sxs-lookup"><span data-stu-id="f5f58-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="f5f58-133">Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。</span><span class="sxs-lookup"><span data-stu-id="f5f58-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="f5f58-134">testlab.<*パブリック* ドメイン>に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5f58-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="f5f58-135">パブリック DNS レコードによるサポート。</span><span class="sxs-lookup"><span data-stu-id="f5f58-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="f5f58-136">Microsoft 365 サブスクリプションに登録済み。</span><span class="sxs-lookup"><span data-stu-id="f5f58-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="f5f58-137">シミュレートされたイントラネット上の AD DS ドメイン。</span><span class="sxs-lookup"><span data-stu-id="f5f58-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="f5f58-138">フェーズ 3: APP1 に Azure AD Connect をインストールする</span><span class="sxs-lookup"><span data-stu-id="f5f58-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="f5f58-139">このフェーズでは、APP1 に Azure AD Connectツールをインストールして構成し、動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="f5f58-140">最初に、APP1 に Azure AD Connectをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="f5f58-141">[Azure portal](https://portal.azure.com) から、全体管理者アカウントでサインインします。その後、TESTLAB\\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="f5f58-142">APP1 のデスクトップから、管理者レベルの Windows PowerShell コマンド プロンプトを起動して、次に示すコマンドを実行して Internet Explorer セキュリティ強化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f5f58-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="f5f58-143">タスク バーで 、[タスク バー] **をInternet Explorer** に移動します [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 。</span><span class="sxs-lookup"><span data-stu-id="f5f58-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="f5f58-144">[ファイルのMicrosoft Azure Active Directory Connect] ページで、[**ダウンロード] を選択し**、[実行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="f5f58-145">[Azure **へのようこそ] ページAD Connect** 同意する] を選択し、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="f5f58-146">[Express 設定]**ページで、[** 高速設定を **使用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="f5f58-147">[Azure **ConnectにAD]** ページで、[ユーザー名] にグローバル管理者アカウント名を入力し、[パスワード]にパスワードを入力し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="f5f58-148">[DS の **ConnectするADで**、[ユーザー名] に **「TESTLAB \\ User1」** と入力し、[パスワード] にパスワードを入力し、[次へ] を選択 **します**。 </span><span class="sxs-lookup"><span data-stu-id="f5f58-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="f5f58-149">[構成の **準備完了] ページで、[** インストール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="f5f58-150">[構成の **完了] ページで** 、[終了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="f5f58-151">Internet Explorer で Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="f5f58-152">左側のナビゲーション ウィンドウで、[アクティブ ユーザー] **を選択>選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="f5f58-153">**User1** という名前のアカウントを記録します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-153">Note the account named **User1**.</span></span> <span data-ttu-id="f5f58-154">これは TESTLAB AD DS ドメインからのアカウントであり、ディレクトリ同期が機能していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="f5f58-155">**[User1] アカウントを選択** し、[ライセンスとアプリ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="f5f58-156">[**製品ライセンス]** で、場所 (必要に応じて) を選択し **、E5** ライセンスOffice 365無効にしてから、ライセンスを有効 **Microsoft 365 E5します。**</span><span class="sxs-lookup"><span data-stu-id="f5f58-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="f5f58-157">ページ **の下部** にある [保存] を選択し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f58-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="f5f58-158">次に、User1 アカウントのドメイン名ユーザー名 **user1@testlab.< > を** 使用してサブスクリプションにサインインする機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="f5f58-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="f5f58-159">APP1 からサインアウトし、その後サインインし直しますが、そのときに別のアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="f5f58-160">ユーザー名とパスワードの入力を求めるメッセージが表示されたら、ドメイン **user1@testlab.< >** User1 パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="f5f58-161">User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="f5f58-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="f5f58-162">User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。</span><span class="sxs-lookup"><span data-stu-id="f5f58-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="f5f58-163">そのため、**[管理者]** アイコンはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="f5f58-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="f5f58-164">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5f58-164">Your resulting configuration looks like this:</span></span>

![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="f5f58-166">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="f5f58-167">Microsoft 365 E5、Office 365のドメイン名が登録されている E5 試用版または有料サブスクリプションDNS ドメイン TESTLAB.<を>します。 </span><span class="sxs-lookup"><span data-stu-id="f5f58-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="f5f58-168">Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。</span><span class="sxs-lookup"><span data-stu-id="f5f58-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="f5f58-169">AZURE AD Connect APP1 で実行され、TESTLAB AD DS ドメインを、ADサブスクリプションの Azure ADテナントにMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="f5f58-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="f5f58-170">TESTLAB AD DS ドメインの User1 アカウントは、Azure AD テナントと同期されています。</span><span class="sxs-lookup"><span data-stu-id="f5f58-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5f58-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="f5f58-171">Next step</span></span>

<span data-ttu-id="f5f58-172">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="f5f58-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5f58-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5f58-173">See also</span></span>

[<span data-ttu-id="f5f58-174">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="f5f58-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f5f58-175">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="f5f58-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f5f58-176">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="f5f58-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)