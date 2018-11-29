---
title: Microsoft 365 テスト環境でのパススルー認証
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: '要約: Microsoft 365 テスト環境でパススルー認証を構成します。'
ms.openlocfilehash: 26222f04617999104a1ad010eb189a0c01370a6d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869193"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cb6e9-103">Microsoft 365 テスト環境でのパススルー認証</span><span class="sxs-lookup"><span data-stu-id="cb6e9-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cb6e9-p101">Microsoft のクラウド ベースのサービスとアプリケーションへの認証のためにオンプレミスの Windows Server Active Directory (AD) インフラストラクチャを直接使用する場合は、組織はパススルー認証を使用してそれを行うことができます。この記事では、Microsoft 365 テスト環境でパススルー認証を構成し、以下のような構成を作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p101">Organizations that want to directly use their on-premises Windows Server Active Directory (AD) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication. This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="cb6e9-107">このテスト環境は、次に示す 2 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-107">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="cb6e9-108">パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="cb6e9-109">APP1 で、パススルー認証用の Azure AD Connect を構成する。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-109">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cb6e9-111">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cb6e9-112">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="cb6e9-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cb6e9-p102">「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="cb6e9-116">この構成は、次の内容で構成されます:</span><span class="sxs-lookup"><span data-stu-id="cb6e9-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="cb6e9-117">Office 365 E5 および EMS E5 試用版または永続的なサブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-117">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="cb6e9-p103">インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、TESTLAB Windows Server AD ドメインを定期的に Office 365 および EMS E5 サブスクリプションの Azure AD テナントに同期します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="cb6e9-120">フェーズ 2: APP1 で、パススルー認証用の Azure AD Connect を構成します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-120">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="cb6e9-121">このフェーズでは、パススルー認証の使用に向けて Azure AD Connect を APP1 で構成し、正常な動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-121">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="cb6e9-122">APP1 上で Azure AD Connect を構成する</span><span class="sxs-lookup"><span data-stu-id="cb6e9-122">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="cb6e9-123">[Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="cb6e9-124">APP1 のデスクトップで、Azure AD Connect を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="cb6e9-125">**[ようこそ]** ページで、**[構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-125">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="cb6e9-126">[追加のタスク] ページで、[**ユーザー サインインの変更**]、[**次へ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-126">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="cb6e9-127">**[Azure AD に接続]** ページで、全体管理者の資格情報を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="cb6e9-128">**[ユーザー サインイン**] ページで、[**パススルー認証**] をクリックした後に [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-128">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="cb6e9-129">**[構成の準備完了]** ページで、**[構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-129">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="cb6e9-130">**[構成が完了しました]** ページで、**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-130">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="cb6e9-p104">Azure ポータルの左側のウィンドウで、**[Azure Active Directory]、[Azure AD Connect]** の順でクリックします。**パススルー認証**機能が**有効**と表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="cb6e9-p105">[**パススルー認証**] をクリックします。[**パススルー認証**] ウィンドウには、認証エージェントがインストールされているサーバーの一覧が表示されます。一覧の中に APP1 が表示されているはずです。[**パススルー認証**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="cb6e9-137">次に、User1 アカウントの ユーザー名である user1@testlab./\<お客様のパブリック ドメイン名> で Office 365 サブスクリプションにサインインできることをテストします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-137">Next, test the ability to sign in to your Office 365 subscription with the user1@testlab.\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="cb6e9-138">APP1 から、Office 365 のサインアウトを実行します。その後で、別のアカウントを指定して再度サインインします。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-138">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="cb6e9-p106">ユーザー名とパスワードの入力を求めるダイアログが表示されたら、user1@testlab.\<お客様のパブリック ドメイン名> と User1 のパスワードを指定します。User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p106">When prompted for a user name and password, specify user1@testlab.\<your public domain> and the User1 password. You should successfully sign in as User1.</span></span>

<span data-ttu-id="cb6e9-p107">User1 には、TESTLAB Windows Server AD ドメインに対するドメイン管理者アクセス許可がありますが、Office 365 全体管理者ではない点に注意してください。そのため、[**管理者**] アイコンがオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p107">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="cb6e9-143">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-143">Here is your resulting configuration:</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="cb6e9-145">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-145">This configuration consists of:</span></span>

- <span data-ttu-id="cb6e9-146">DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Office 365 E5 および EMS E5 試用版サブスクリプションまたは永続サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-146">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="cb6e9-p108">インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、Office 365 および EMS E5 サブスクリプションの Azure AD テナントからのパススルー認証要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="next-step"></a><span data-ttu-id="cb6e9-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="cb6e9-149">Next step</span></span>

<span data-ttu-id="cb6e9-150">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="cb6e9-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb6e9-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb6e9-151">See also</span></span>

[<span data-ttu-id="cb6e9-152">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="cb6e9-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cb6e9-153">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="cb6e9-153">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cb6e9-154">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="cb6e9-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


