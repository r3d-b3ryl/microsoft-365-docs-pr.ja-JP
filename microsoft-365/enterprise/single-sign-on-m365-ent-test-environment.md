---
title: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン
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
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオンを構成してテストします。'
ms.openlocfilehash: 3ba229a62f66cad715f604bab91cd12032da7be8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685774"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="768c3-103">Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン</span><span class="sxs-lookup"><span data-stu-id="768c3-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="768c3-104">*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="768c3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="768c3-p101">Azure AD のシームレスなシングル サインオンは、ユーザーが組織のネットワークに接続されている PC またはデバイス上に存在するときに、自動的にサインインします。Azure AD シームレス SSO で、ユーザーはクラウド ベースのアプリケーションに簡単にアクセスできるようになります。アクセスする際、オンプレミスの追加コンポーネントは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="768c3-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="768c3-107">この記事では、Azure AD シームレス SSO 用の Microsoft 365 テスト環境を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="768c3-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="768c3-108">設定は 2 つのフェーズで行います。</span><span class="sxs-lookup"><span data-stu-id="768c3-108">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="768c3-109">パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。</span><span class="sxs-lookup"><span data-stu-id="768c3-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="768c3-110">Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する。</span><span class="sxs-lookup"><span data-stu-id="768c3-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="768c3-112">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="768c3-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="768c3-113">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="768c3-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="768c3-p102">「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="768c3-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="768c3-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="768c3-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="768c3-118">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="768c3-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="768c3-119">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="768c3-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="768c3-120">Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに定期的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="768c3-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="768c3-121">フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する</span><span class="sxs-lookup"><span data-stu-id="768c3-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="768c3-122">このフェーズでは、Azure AD シームレス SSO 用に Azure AD Connect を APP1 で構成し、正常な動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="768c3-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="768c3-123">APP1 上で Azure AD Connect を構成する</span><span class="sxs-lookup"><span data-stu-id="768c3-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="768c3-124">[Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="768c3-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="768c3-125">APP1 のデスクトップで、Azure AD Connect を実行します。</span><span class="sxs-lookup"><span data-stu-id="768c3-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="768c3-126">[**ようこそ**] ページで、[**構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="768c3-127">**[追加のタスク]** ページで、**[ユーザー サインインの変更]**、**[次へ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="768c3-128">**[Azure AD に接続]** ページで、グローバル管理者の資格情報を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="768c3-129">**[ユーザー サインイン]** ページで、**[シングル サインオンを有効にする]** を選び、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="768c3-130">**[シングル サインオンを有効にする]** ページで、**[資格情報を入力する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="768c3-p103">**[Windows セキュリティ]** ダイアログ ボックスで、**user1** と入力し、user1 アカウントのパスワードも入力します。入力後、**[OK]**、**[次へ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="768c3-133">**[構成の準備完了]** ページで、**[構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="768c3-134">**[構成が完了しました]** ページで、**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="768c3-p104">Azure portal の左側のウィンドウで、**[Azure Active Directory]、[Azure AD Connect]** の順にクリックします。**シームレスなシングル サインオン**機能が**有効**と表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="768c3-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="768c3-137">次に、user1@testlab を使用してサブスクリプションにサインインできることをテストし <strong>ます。</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="768c3-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="768c3-138">を使用してサブスクリプションにサインインする機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="768c3-138">user name of the User1 account.</span></span>

1. <span data-ttu-id="768c3-139">APP1 で Internet Explorer から [設定] アイコンをクリックし、**[インターネット オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-139">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="768c3-140">**[インターネット オプション]** で、**[セキュリティ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-140">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="768c3-141">**[ローカル イントラネット]** をクリックし、**[サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-141">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="768c3-142">**[ローカル イントラネット]** で、**[詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-142">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="768c3-143">**[この Web サイトをゾーンに追加する]** で、**https<span>://</span>autologon.microsoftazuread-sso.com** と入力し、**[追加]、[閉じる]、[OK]、[OK]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-143">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="768c3-144">サインアウトして、再度サインインします。その際に、別のアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="768c3-144">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="768c3-145">サインインするように求めるメッセージが表示されたら、user1@testlab を指定し <strong>ます。</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="768c3-145">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="768c3-146">名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="768c3-146">name, and then click **Next**.</span></span> <span data-ttu-id="768c3-147">パスワードの入力を求められることなく、User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="768c3-147">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="768c3-148">サインインできた場合、Azure AD シームレス SSO が機能していることになります。</span><span class="sxs-lookup"><span data-stu-id="768c3-148">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="768c3-149">User1 には TESTLAB AD DS ドメインに対するドメイン管理者のアクセス許可がありますが、Azure AD のグローバル管理者ではないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="768c3-149">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="768c3-150">そのため、**[管理者]** アイコンはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="768c3-150">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="768c3-151">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="768c3-151">Here is your resulting configuration:</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="768c3-153">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="768c3-153">This configuration consists of:</span></span>

- <span data-ttu-id="768c3-154">DNS ドメインのテストラボでの Microsoft 365 E5 試用版または有料サブスクリプション。\<your domain name></span><span class="sxs-lookup"><span data-stu-id="768c3-154">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="768c3-155">が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="768c3-155">registered.</span></span>
- <span data-ttu-id="768c3-156">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="768c3-156">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="768c3-157">Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。</span><span class="sxs-lookup"><span data-stu-id="768c3-157">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="768c3-158">Azure AD シームレス SSO が有効になっており、シミュレートされたイントラネット上のコンピューターは、ユーザー アカウントのパスワードを指定せずに Microsoft 365 のクラウド リソースにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="768c3-158">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="768c3-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="768c3-159">Next step</span></span>

<span data-ttu-id="768c3-160">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="768c3-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="768c3-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="768c3-161">See also</span></span>

[<span data-ttu-id="768c3-162">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="768c3-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="768c3-163">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="768c3-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="768c3-164">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="768c3-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


