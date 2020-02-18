---
title: Microsoft 365 テスト環境のパスワード ハッシュ同期
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワード ハッシュ同期とサインインを構成して実例を示します。'
ms.openlocfilehash: a0a498aea84bacb61de257150801328834724981
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066395"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d0da3-103">Microsoft 365 テスト環境のパスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="d0da3-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d0da3-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="d0da3-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d0da3-105">多くの組織では、Azure AD Connect とパスワード ハッシュ同期を使用して、オンプレミスの Active Directory Domain Services (AD DS) フォレスト内のアカウント セットを、Microsoft 365 または Office 365 サブスクリプションの Azure AD テナント内のアカウント セットに同期します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 or Office 365 subscription.</span></span> <span data-ttu-id="d0da3-106">この記事では、Microsoft 365 のテスト環境にパスワード ハッシュ同期を追加する方法について説明します。最終的な構成は、次のとおりになります。</span><span class="sxs-lookup"><span data-stu-id="d0da3-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="d0da3-108">このテスト環境は、次に示す 2 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="d0da3-109">Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する。</span><span class="sxs-lookup"><span data-stu-id="d0da3-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="d0da3-110">APP1 に Azure AD Connect をインストールして構成する。</span><span class="sxs-lookup"><span data-stu-id="d0da3-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="d0da3-111">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d0da3-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="d0da3-112">フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="d0da3-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="d0da3-p102">「[Microsoft 365 用のシミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)」の手順を実行します。次に、最終的な構成を示します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="d0da3-116">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d0da3-117">Microsoft 365 E5 または Office 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="d0da3-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="d0da3-118">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワーク内の仮想マシン DC1、APP1、CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d0da3-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="d0da3-119">DC1 は、testlab.\<パブリック ドメイン名> AD DS ドメインのドメイン コントローラーです。</span><span class="sxs-lookup"><span data-stu-id="d0da3-119">DC1 is a domain controller for the testlab.\<your public domain name> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="d0da3-120">フェーズ 2: testlab ドメインを作成および登録する</span><span class="sxs-lookup"><span data-stu-id="d0da3-120">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="d0da3-121">このフェーズでは、パブリック DNS ドメインを追加して、そのドメインをサブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-121">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="d0da3-p104">まず、パブリック DNS 登録プロバイダーと協力して、現在のドメイン名に基づいた新しいパブリック DNS ドメイン名を作成し、それをサブスクリプションに追加します。**testlab.**\<自分のパブリック ドメイン> という名前を使用することをお勧めします。たとえば、パブリック ドメイン名が **<span>contoso</span>.com** である場合は、パブリック ドメイン名 **<span>testlab</span>.contoso.com** を追加します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="d0da3-125">次に、ドメイン登録プロセスの手順に従って、**testlab.**\<自分のパブリック ドメイン> ドメインを Microsoft 365 または Office 365 の試用版または有料のサブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-125">Next, you add the **testlab.**\<your public domain> domain to your Microsoft 365 or Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="d0da3-126">この際、他の DNS レコードも **testlab.**\<パブリック ドメイン> ドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-126">This consists of adding additional DNS records to the **testlab.**\<your public domain> domain.</span></span> <span data-ttu-id="d0da3-127">詳細については、「[Office 365 にドメインを追加する](https://docs.microsoft.com/office365/admin/setup/add-domain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0da3-127">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span></span> 

<span data-ttu-id="d0da3-128">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-128">Here is your resulting configuration.</span></span>
  
![testlab ドメイン名の登録](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="d0da3-130">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-130">This configuration consists of:</span></span>

- <span data-ttu-id="d0da3-131">DNS ドメイン testlab.\<パブリック ドメイン名> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="d0da3-131">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="d0da3-132">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d0da3-132">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="d0da3-133">この時点での testlab.\<パブリック ドメイン名> の状態に注目してください。</span><span class="sxs-lookup"><span data-stu-id="d0da3-133">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="d0da3-134">パブリック DNS レコードによるサポート。</span><span class="sxs-lookup"><span data-stu-id="d0da3-134">Supported by public DNS records.</span></span>
- <span data-ttu-id="d0da3-135">Microsoft 365 または Office 365 のサブスクリプションに登録済みです。</span><span class="sxs-lookup"><span data-stu-id="d0da3-135">Registered in your Microsoft 365 or Office 365 subscriptions.</span></span>
- <span data-ttu-id="d0da3-136">シミュレートされたイントラネット上の AD DS ドメイン。</span><span class="sxs-lookup"><span data-stu-id="d0da3-136">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="d0da3-137">フェーズ 3: APP1 に Azure AD Connect をインストールする</span><span class="sxs-lookup"><span data-stu-id="d0da3-137">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="d0da3-138">このフェーズでは、Azure AD Connect を APP1 にインストールして構成します。その後で、動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-138">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="d0da3-139">まず、APP1 上に Azure AD Connect をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-139">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="d0da3-140">[Azure portal](https://portal.azure.com) から、全体管理者アカウントでサインインします。その後、TESTLAB\\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-140">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="d0da3-141">APP1 のデスクトップから、管理者レベルの Windows PowerShell コマンド プロンプトを起動して、次に示すコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-141">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="d0da3-142">タスク バーで **[Internet Explorer]** をクリックし、[https://aka.ms/aadconnect](https://aka.ms/aadconnect)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-142">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="d0da3-143">[Microsoft Azure Active Directory Connect] ページで、**[ダウンロード]** をクリックして、**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-143">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="d0da3-144">**[Azure AD Connect へようこそ]** ページで、**[同意する]** をクリックして、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-144">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="d0da3-145">**[簡単設定]** ページで、**[簡単設定を使う]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-145">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="d0da3-146">**[Azure AD に接続]** ページで、**[ユーザー名]** に全体管理者のアカウント名、**[パスワード]** にそのパスワードを入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-146">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d0da3-147">**[AD DS に接続]** ページで、**[ユーザー名]** に「**TESTLAB\\User1**」と入力し、**[パスワード]** にそのパスワードを入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-147">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="d0da3-148">**[構成の準備完了]** ページで、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-148">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="d0da3-149">**[構成が完了しました]** ページで、**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-149">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="d0da3-150">Internet Explorer で Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-150">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="d0da3-151">左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-151">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="d0da3-152">**User1** という名前のアカウントを記録します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-152">Note the account named **User1**.</span></span> <span data-ttu-id="d0da3-153">これは TESTLAB AD DS ドメインからのアカウントであり、ディレクトリ同期が機能していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-153">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="d0da3-154">**User1** アカウントをクリックして、**[ライセンスとアプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-154">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="d0da3-155">**[製品ライセンス]** で、必要に応じて場所を選択し、**Office 365 E5** ライセンスを無効にして、**Microsoft 365 E5** ライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-155">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="d0da3-156">ページの下側にある **[保存]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-156">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="d0da3-157">次に、User1 アカウントのユーザー名である <strong>user1@testlab.</strong>\<自分のドメイン名> を使用して、サブスクリプションにサインインする機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="d0da3-157">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="d0da3-158">APP1 から、サインアウトして、サインインし直しますが、その際に別のアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-158">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="d0da3-p107">ユーザー名とパスワードの入力を求めるダイアログが表示されたら、<strong>user1@testlab.</strong>\<お客様のドメイン名> と User1 のパスワードを指定します。User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="d0da3-p107">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="d0da3-161">User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。</span><span class="sxs-lookup"><span data-stu-id="d0da3-161">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="d0da3-162">そのため、**[管理者]** アイコンはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0da3-162">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="d0da3-163">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-163">Here is your resulting configuration.</span></span>

![パスワード ハッシュ同期テスト環境があるシミュレートされたエンタープライズ](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="d0da3-165">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="d0da3-165">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d0da3-166">DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="d0da3-166">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="d0da3-167">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d0da3-167">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="d0da3-168">Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 または Office 365 サブスクリプションの Azure AD テナントに定期的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="d0da3-168">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>
- <span data-ttu-id="d0da3-169">TESTLAB AD DS ドメインの User1 アカウントは、Azure AD テナントと同期されています。</span><span class="sxs-lookup"><span data-stu-id="d0da3-169">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="d0da3-170">次の手順</span><span class="sxs-lookup"><span data-stu-id="d0da3-170">Next step</span></span>

<span data-ttu-id="d0da3-171">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="d0da3-171">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0da3-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0da3-172">See also</span></span>

[<span data-ttu-id="d0da3-173">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="d0da3-173">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d0da3-174">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="d0da3-174">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d0da3-175">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="d0da3-175">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


