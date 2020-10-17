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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487460"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="79aa1-103">Microsoft 365 テスト環境のパスワード ハッシュ同期</span><span class="sxs-lookup"><span data-stu-id="79aa1-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="79aa1-104">*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="79aa1-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="79aa1-105">多くの組織では、Azure AD Connect とパスワード ハッシュ同期を使用して、オンプレミスの Active Directory Domain Services (AD DS) フォレスト内のアカウント セットを、Microsoft 365 サブスクリプションの Azure AD テナント内のアカウント セットに同期します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="79aa1-106">この記事では、パスワードハッシュの同期を Microsoft 365 テスト環境に追加する方法について説明します。この構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="79aa1-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="79aa1-108">このテスト環境のセットアップには、3つのフェーズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="79aa1-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="79aa1-109">フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="79aa1-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="79aa1-110">フェーズ 2: testlab ドメインを作成および登録する</span><span class="sxs-lookup"><span data-stu-id="79aa1-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="79aa1-111">フェーズ 3: APP1 に Azure AD Connect をインストールする</span><span class="sxs-lookup"><span data-stu-id="79aa1-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="79aa1-112">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79aa1-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="79aa1-113">フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="79aa1-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="79aa1-114">「 [Microsoft 365 のシミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="79aa1-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="79aa1-115">結果の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="79aa1-115">Your resulting configuration looks like this:</span></span>
  
![シミュレートされたエンタープライズ基本構成](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="79aa1-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="79aa1-118">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="79aa1-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="79aa1-119">インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワーク内の DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="79aa1-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="79aa1-120">DC1 は、testlab のドメインコントローラー <ます。 *パブリックドメイン名*> AD DS ドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="79aa1-121">フェーズ 2: testlab ドメインを作成および登録する</span><span class="sxs-lookup"><span data-stu-id="79aa1-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="79aa1-122">このフェーズでは、パブリック DNS ドメインを追加し、サブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="79aa1-123">最初に、パブリック DNS 登録プロバイダと連携して、現在のドメイン名に基づいた新しいパブリック DNS ドメイン名を作成し、サブスクリプションに追加します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="79aa1-124">「Testlab」という名前を使用することをお勧め\**します。*パブリックドメイン\* > <\*\*。</span><span class="sxs-lookup"><span data-stu-id="79aa1-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="79aa1-125">たとえば、パブリックドメイン名が\*\* <span>contoso</span>.com**の場合は、パブリックドメイン名** <span>testlab</span>contoso.com\*\*を追加します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="79aa1-126">次に、ドメイン登録プロセスを実行して、Microsoft 365 試用版または有料版サブスクリプションに、 ***パブリックドメイン* > ドメイン <** を追加します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="79aa1-127">これは、他の DNS レコードを testlab に追加することで構成され**ます。*パブリックドメイン\* > ドメイン <*\* します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="79aa1-128">詳細については、「 [Microsoft 365 にドメインを追加する](../admin/setup/add-domain.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79aa1-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="79aa1-129">結果の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="79aa1-129">Your resulting configuration looks like this:</span></span>
  
![testlab ドメイン名の登録](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="79aa1-131">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-131">This configuration consists of:</span></span>

- <span data-ttu-id="79aa1-132">DNS domain testlab を使用した Microsoft 365 E5 試用版または有償版サブスクリプション <> 登録済みの *パブリックドメイン名* を指定します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="79aa1-133">インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="79aa1-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="79aa1-134">ここで、testlab <> の *パブリックドメイン名* が次のようになっていることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="79aa1-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="79aa1-135">パブリック DNS レコードによるサポート。</span><span class="sxs-lookup"><span data-stu-id="79aa1-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="79aa1-136">Microsoft 365 サブスクリプションに登録済み。</span><span class="sxs-lookup"><span data-stu-id="79aa1-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="79aa1-137">シミュレートされたイントラネット上の AD DS ドメイン。</span><span class="sxs-lookup"><span data-stu-id="79aa1-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="79aa1-138">フェーズ 3: APP1 に Azure AD Connect をインストールする</span><span class="sxs-lookup"><span data-stu-id="79aa1-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="79aa1-139">このフェーズでは、の Azure AD Connect ツールをインストールして構成し、正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="79aa1-140">最初に、Azure AD Connect をインストールして、[インストール] に構成します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="79aa1-141">[Azure portal](https://portal.azure.com) から、全体管理者アカウントでサインインします。その後、TESTLAB\\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="79aa1-142">APP1 のデスクトップから、管理者レベルの Windows PowerShell コマンド プロンプトを起動して、次に示すコマンドを実行して Internet Explorer セキュリティ強化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="79aa1-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="79aa1-143">タスクバーから [ **Internet Explorer** ] を選択し、に移動し [https://aka.ms/aadconnect](https://aka.ms/aadconnect) ます。</span><span class="sxs-lookup"><span data-stu-id="79aa1-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="79aa1-144">[Microsoft Azure Active Directory Connect] ページで、[ **ダウンロード**] を選択し、[ **実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="79aa1-145">[ **AZURE AD Connect へようこそ** ] ページで、[ **同意**します] を選択し、[ **続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="79aa1-146">[ **簡易設定** ] ページで、[ **エクスプレス設定を使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="79aa1-147">[ **AZURE AD に接続** ] ページで、[ **ユーザー名]** に全体管理者のアカウント名を入力し、[ **パスワード**] にパスワードを入力して、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="79aa1-148">[ **AD DS に接続**] ページで、[**ユーザー名]** に「 **testlab \\ User1** 」と入力し、[パスワード **] にパスワードを入力**して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="79aa1-149">[ **構成の準備完了** ] ページで、[ **インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="79aa1-150">[ **構成の完了** ] ページで、[ **終了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="79aa1-151">Internet Explorer で Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="79aa1-152">左側のナビゲーションウィンドウで、[ **ユーザー > アクティブユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="79aa1-153">**User1** という名前のアカウントを記録します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-153">Note the account named **User1**.</span></span> <span data-ttu-id="79aa1-154">これは TESTLAB AD DS ドメインからのアカウントであり、ディレクトリ同期が機能していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="79aa1-155">**User1**アカウントを選択し、[**ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="79aa1-156">[ **製品ライセンス**] で、場所 (必要な場合) を選択し、 **Office 365 e5** ライセンスを無効にしてから、 **Microsoft 365 E5** ライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="79aa1-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="79aa1-157">ページの下部にある [ **保存** ] を選択し、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="79aa1-158">次に、user1@testlab を使用してサブスクリプションにサインインできることをテスト\**します。*ドメイン名\* > \*\* user1 アカウントのユーザー名を <します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="79aa1-159">APP1 からサインアウトし、その後サインインし直しますが、そのときに別のアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="79aa1-160">ユーザー名とパスワードの入力を求められたら user1@testlab を指定し\**ます。*ドメイン名\* > \*\*と user1 のパスワードを <します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="79aa1-161">User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="79aa1-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="79aa1-162">User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。</span><span class="sxs-lookup"><span data-stu-id="79aa1-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="79aa1-163">そのため、**[管理者]** アイコンはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="79aa1-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="79aa1-164">結果の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="79aa1-164">Your resulting configuration looks like this:</span></span>

![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="79aa1-166">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="79aa1-167">DNS domain TESTLAB を使用した Microsoft 365 E5 または Office 365 E5 試用版または有料サブスクリプション。 <*ドメイン名*> 登録されています。</span><span class="sxs-lookup"><span data-stu-id="79aa1-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="79aa1-168">インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="79aa1-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="79aa1-169">Azure AD Connect は、Outlook で実行され、TESTLAB AD DS ドメインと Microsoft 365 サブスクリプションの Azure AD テナントを定期的に同期します。</span><span class="sxs-lookup"><span data-stu-id="79aa1-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="79aa1-170">TESTLAB AD DS ドメインの User1 アカウントは、Azure AD テナントと同期されています。</span><span class="sxs-lookup"><span data-stu-id="79aa1-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="79aa1-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="79aa1-171">Next step</span></span>

<span data-ttu-id="79aa1-172">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="79aa1-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="79aa1-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="79aa1-173">See also</span></span>

[<span data-ttu-id="79aa1-174">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="79aa1-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="79aa1-175">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="79aa1-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="79aa1-176">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="79aa1-176">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
