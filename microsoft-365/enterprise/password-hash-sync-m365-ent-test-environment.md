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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワード ハッシュ同期とサインインを構成して実例を示します。'
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819390"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="76150-103">Microsoft 365 テスト環境のパスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="76150-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="76150-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="76150-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="76150-105">多くの組織では、Azure AD Connect とパスワード ハッシュ同期を使用して、オンプレミスの Active Directory Domain Services (AD DS) フォレスト内のアカウント セットを、Microsoft 365 サブスクリプションの Azure AD テナント内のアカウント セットに同期します。</span><span class="sxs-lookup"><span data-stu-id="76150-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="76150-106">この記事では、Microsoft 365 のテスト環境にパスワード ハッシュ同期を追加する方法について説明します。最終的な構成は、次のとおりになります。</span><span class="sxs-lookup"><span data-stu-id="76150-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="76150-108">このテスト環境は、次に示す 2 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="76150-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="76150-109">Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する。</span><span class="sxs-lookup"><span data-stu-id="76150-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="76150-110">APP1 に Azure AD Connect をインストールして構成する。</span><span class="sxs-lookup"><span data-stu-id="76150-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="76150-111">Microsoft 365 Enterprise のテスト ラボ ガイド スタック内のすべての記事のビジュアル マップについては、「[Microsoft 365 Enterprise のテスト ラボ ガイド スタック](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)」にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="76150-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="76150-112">フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="76150-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="76150-113">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="76150-113">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="76150-114">Here is your resulting configuration.</span><span class="sxs-lookup"><span data-stu-id="76150-114">Here is your resulting configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="76150-116">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="76150-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="76150-117">Microsoft 365 E5 または Office 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="76150-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="76150-118">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワーク内の仮想マシン DC1、APP1、CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="76150-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="76150-119">DC1 は、testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="76150-119">DC1 is a domain controller for the testlab.\<your public domain name></span></span> <span data-ttu-id="76150-120">AD DS ドメインのドメイン コントローラーです。</span><span class="sxs-lookup"><span data-stu-id="76150-120">AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="76150-121">フェーズ 2: testlab ドメインを作成および登録する</span><span class="sxs-lookup"><span data-stu-id="76150-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="76150-122">このフェーズでは、パブリック DNS ドメインを追加して、そのドメインをサブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="76150-122">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="76150-123">最初に、パブリック DNS 登録プロバイダーと協力して、現在のドメイン名に基づいて新しいパブリック DNS ドメイン名を作成し、サブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="76150-123">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="76150-124">**testlab.**\<your public domain> という名前の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76150-124">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="76150-125">たとえば、パブリック ドメイン名が **<span>contoso</span>.com** である場合は、パブリック ドメイン名 **<span>testlab</span>.contoso.com** を追加します。</span><span class="sxs-lookup"><span data-stu-id="76150-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="76150-126">次に、ドメイン登録プロセスを経て、**testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="76150-126">Next, you add the **testlab.**\<your public domain></span></span> <span data-ttu-id="76150-127">ドメインを Microsoft 365 または Office 365 の試用版または有料のサブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="76150-127">domain to your Microsoft 365 or Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="76150-128">このときに、他の DNS レコードも **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="76150-128">This consists of adding additional DNS records to the **testlab.**\<your public domain></span></span> <span data-ttu-id="76150-129">ドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="76150-129">domain.</span></span> <span data-ttu-id="76150-130">詳細については、「[Office 365 にドメインを追加する](https://docs.microsoft.com/office365/admin/setup/add-domain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76150-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span></span> 

<span data-ttu-id="76150-131">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="76150-131">Here is your resulting configuration.</span></span>
  
![testlab ドメイン名の登録](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="76150-133">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="76150-133">This configuration consists of:</span></span>

- <span data-ttu-id="76150-134">DNS ドメイン testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="76150-134">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name></span></span> <span data-ttu-id="76150-135">が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="76150-135">registered.</span></span>
- <span data-ttu-id="76150-136">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="76150-136">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="76150-137">testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="76150-137">Notice how the testlab.\<your public domain name></span></span> <span data-ttu-id="76150-138">がどのようにして次のようになっているかについてご注意ください。</span><span class="sxs-lookup"><span data-stu-id="76150-138">is now:</span></span>

- <span data-ttu-id="76150-139">パブリック DNS レコードによるサポート。</span><span class="sxs-lookup"><span data-stu-id="76150-139">Supported by public DNS records.</span></span>
- <span data-ttu-id="76150-140">Microsoft 365 サブスクリプションに登録済み。</span><span class="sxs-lookup"><span data-stu-id="76150-140">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="76150-141">シミュレートされたイントラネット上の AD DS ドメイン。</span><span class="sxs-lookup"><span data-stu-id="76150-141">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="76150-142">フェーズ 3: APP1 に Azure AD Connect をインストールする</span><span class="sxs-lookup"><span data-stu-id="76150-142">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="76150-143">このフェーズでは、Azure AD Connect を APP1 にインストールして構成します。その後で、動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="76150-143">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="76150-144">まず、APP1 上に Azure AD Connect をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="76150-144">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="76150-145">[Azure portal](https://portal.azure.com) から、全体管理者アカウントでサインインします。その後、TESTLAB\\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="76150-145">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="76150-146">APP1 のデスクトップから、管理者レベルの Windows PowerShell コマンド プロンプトを起動して、次に示すコマンドを実行して Internet Explorer セキュリティ強化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="76150-146">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="76150-147">タスク バーで **[Internet Explorer]** をクリックし、[https://aka.ms/aadconnect](https://aka.ms/aadconnect)に移動します。</span><span class="sxs-lookup"><span data-stu-id="76150-147">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="76150-148">[Microsoft Azure Active Directory Connect] ページで、**[ダウンロード]** をクリックして、**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-148">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="76150-149">**[Azure AD Connect へようこそ]** ページで、**[同意する]** をクリックして、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-149">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="76150-150">**[簡単設定]** ページで、**[簡単設定を使う]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-150">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="76150-151">**[Azure AD に接続]** ページで、**[ユーザー名]** に全体管理者のアカウント名、**[パスワード]** にそのパスワードを入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-151">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="76150-152">**[AD DS に接続]** ページで、**[ユーザー名]** に「**TESTLAB\\User1**」と入力し、**[パスワード]** にそのパスワードを入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-152">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="76150-153">**[構成の準備完了]** ページで、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-153">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="76150-154">**[構成が完了しました]** ページで、**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-154">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="76150-155">Internet Explorer で Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="76150-155">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="76150-156">左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-156">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="76150-157">**User1** という名前のアカウントを記録します。</span><span class="sxs-lookup"><span data-stu-id="76150-157">Note the account named **User1**.</span></span> <span data-ttu-id="76150-158">これは TESTLAB AD DS ドメインからのアカウントであり、ディレクトリ同期が機能していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="76150-158">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="76150-159">**User1** アカウントをクリックして、**[ライセンスとアプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-159">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="76150-160">**[製品ライセンス]** で、必要に応じて場所を選択し、**Office 365 E5** ライセンスを無効にして、**Microsoft 365 E5** ライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="76150-160">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="76150-161">ページの下側にある **[保存]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76150-161">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="76150-162">次に、User1 アカウントのユーザー名である <strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="76150-162">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="76150-163">を使用してサブスクリプションにサインインする機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="76150-163">user name of the User1 account.</span></span>

1. <span data-ttu-id="76150-164">APP1 からサインアウトし、その後サインインし直しますが、そのときに別のアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="76150-164">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="76150-165">ユーザー名とパスワードの入力を求めるダイアログが表示されたら、<strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="76150-165">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="76150-166">と User1 のパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="76150-166">and the User1 password.</span></span> <span data-ttu-id="76150-167">User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="76150-167">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="76150-168">User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。</span><span class="sxs-lookup"><span data-stu-id="76150-168">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="76150-169">そのため、**[管理者]** アイコンはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="76150-169">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="76150-170">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="76150-170">Here is your resulting configuration.</span></span>

![パスワード ハッシュ同期テスト環境があるシミュレートされたエンタープライズ](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="76150-172">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="76150-172">This configuration consists of:</span></span> 
  
- <span data-ttu-id="76150-173">DNS ドメイン TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="76150-173">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="76150-174">が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="76150-174">registered.</span></span>
- <span data-ttu-id="76150-175">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="76150-175">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="76150-176">Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに定期的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="76150-176">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="76150-177">TESTLAB AD DS ドメインの User1 アカウントは、Azure AD テナントと同期されています。</span><span class="sxs-lookup"><span data-stu-id="76150-177">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="76150-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="76150-178">Next step</span></span>

<span data-ttu-id="76150-179">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="76150-179">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="76150-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="76150-180">See also</span></span>

[<span data-ttu-id="76150-181">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="76150-181">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="76150-182">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="76150-182">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="76150-183">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="76150-183">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


