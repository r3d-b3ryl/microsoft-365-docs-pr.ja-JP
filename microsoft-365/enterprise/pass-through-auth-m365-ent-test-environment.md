---
title: Microsoft 365 テスト環境でのパススルー認証
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
ms.assetid: ''
description: '要約: Microsoft 365 テスト環境でパススルー認証を構成します。'
ms.openlocfilehash: cdbb6927fb8ca0001e3089c7169ce9046208e8f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921530"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="20bc4-103">Microsoft 365 テスト環境でのパススルー認証</span><span class="sxs-lookup"><span data-stu-id="20bc4-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="20bc4-104">*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*</span><span class="sxs-lookup"><span data-stu-id="20bc4-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="20bc4-105">Microsoft のクラウド ベースのサービスとアプリケーションへの認証のためにオンプレミスの Active Directory Domain Services (AD DS) インフラストラクチャを直接使用する場合、組織はパススルー認証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="20bc4-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="20bc4-106">この記事では、Microsoft 365 テスト環境でパススルー認証を構成し、以下のような構成を作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="20bc4-108">このテスト環境は、次に示す 2 つのフェーズで設定します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="20bc4-109">パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。</span><span class="sxs-lookup"><span data-stu-id="20bc4-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="20bc4-110">APP1 で、パススルー認証用の Azure AD Connect を構成する。</span><span class="sxs-lookup"><span data-stu-id="20bc4-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="20bc4-112">[ここ](../downloads/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="20bc4-112">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="20bc4-113">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="20bc4-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="20bc4-p102">「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20bc4-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="20bc4-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="20bc4-118">Microsoft 365 E5または有料サブスクリプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="20bc4-119">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="20bc4-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="20bc4-120">Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに定期的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="20bc4-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="20bc4-121">フェーズ 2: APP1 で、パススルー認証用の Azure AD Connect を構成します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="20bc4-122">このフェーズでは、パススルー認証の使用に向けて Azure AD Connect を APP1 で構成し、正常な動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="20bc4-123">APP1 上で Azure AD Connect を構成する</span><span class="sxs-lookup"><span data-stu-id="20bc4-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="20bc4-124">[Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="20bc4-125">APP1 のデスクトップで、Azure AD Connect を実行します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="20bc4-126">**[ようこそ]** ページで、**[構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20bc4-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="20bc4-127">[追加のタスク] ページで、[**ユーザー サインインの変更**]、[**次へ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="20bc4-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="20bc4-128">**[Azure AD に接続]** ページで、全体管理者の資格情報を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20bc4-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="20bc4-129">**[ユーザー サインイン**] ページで、[**パススルー認証**] をクリックした後に [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20bc4-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="20bc4-130">**[構成の準備完了]** ページで、**[構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20bc4-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="20bc4-131">**[構成が完了しました]** ページで、**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20bc4-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="20bc4-p104">Azure ポータルの左側のウィンドウで、**[Azure Active Directory]、[Azure AD Connect]** の順でクリックします。**パススルー認証** 機能が **有効** と表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="20bc4-p105">[**パススルー認証**] をクリックします。[**パススルー認証**] ウィンドウには、認証エージェントがインストールされているサーバーの一覧が表示されます。一覧の中に APP1 が表示されているはずです。[**パススルー認証**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="20bc4-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="20bc4-138">次に、サブスクリプションにサインインする機能をテストし <strong>、user1@testlab。</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="20bc4-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="20bc4-139">を使用してサブスクリプションにサインインする機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="20bc4-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="20bc4-140">APP1 からサインアウトし、その後サインインし直しますが、そのときに別のアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="20bc4-141">ユーザー名とパスワードの入力を求めるダイアログが表示されたら、<strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="20bc4-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="20bc4-142">と User1 のパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-142">and the User1 password.</span></span> <span data-ttu-id="20bc4-143">User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="20bc4-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="20bc4-144">User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。</span><span class="sxs-lookup"><span data-stu-id="20bc4-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="20bc4-145">そのため、**[管理者]** アイコンはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="20bc4-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="20bc4-146">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-146">Here is your resulting configuration:</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="20bc4-148">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-148">This configuration consists of:</span></span>

- <span data-ttu-id="20bc4-149">テストMicrosoft 365 E5の試用版または有料サブスクリプションをDNS ドメインします。\<your domain name></span><span class="sxs-lookup"><span data-stu-id="20bc4-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="20bc4-150">が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="20bc4-150">registered.</span></span>
- <span data-ttu-id="20bc4-p110">インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントからのパススルー認証要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="20bc4-p110">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="20bc4-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="20bc4-153">Next step</span></span>

<span data-ttu-id="20bc4-154">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="20bc4-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="20bc4-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="20bc4-155">See also</span></span>

[<span data-ttu-id="20bc4-156">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="20bc4-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="20bc4-157">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="20bc4-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="20bc4-158">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="20bc4-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)