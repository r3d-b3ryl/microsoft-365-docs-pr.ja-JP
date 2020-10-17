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
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487608"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5a2c1-103">Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5a2c1-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5a2c1-104">*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="5a2c1-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5a2c1-p101">Azure AD のシームレスなシングル Sign-On (シームレスな SSO) は、ユーザーが自分の組織のネットワークに接続されている Pc またはデバイスにいるときに、自動的にサインインします。Azure AD のシームレスな SSO を使用すると、ユーザーは追加のオンプレミスコンポーネントを必要とせずに、クラウドベースのアプリケーションに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-p101">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="5a2c1-107">この記事では、Azure AD シームレス SSO 用に Microsoft 365 テスト環境を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="5a2c1-108">Azure AD のシームレスな SSO を設定するには、次の2つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="5a2c1-109">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="5a2c1-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="5a2c1-110">フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する</span><span class="sxs-lookup"><span data-stu-id="5a2c1-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="5a2c1-112">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5a2c1-113">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="5a2c1-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5a2c1-114">「 [Microsoft 365 のパスワードハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="5a2c1-115">結果の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-115">Your resulting configuration looks like this:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="5a2c1-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="5a2c1-118">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="5a2c1-119">インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="5a2c1-120">Azure AD Connect は、Outlook で実行され、TESTLAB Active Directory ドメインサービス (AD DS) ドメインと Microsoft 365 サブスクリプションの Azure AD テナントを定期的に同期します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="5a2c1-121">フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する</span><span class="sxs-lookup"><span data-stu-id="5a2c1-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="5a2c1-122">このフェーズでは、Azure AD シームレス SSO 用に Azure AD Connect を構成し、正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="5a2c1-123">APP1 上で Azure AD Connect を構成する</span><span class="sxs-lookup"><span data-stu-id="5a2c1-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="5a2c1-124">[Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="5a2c1-125">元のデスクトップで、Azure AD Connect を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="5a2c1-126">[ **ようこそ] ページ**で、[ **構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="5a2c1-127">[ **追加のタスク** ] ページで、[ユーザーの **サインインを変更**する] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="5a2c1-128">[ **AZURE AD に接続** ] ページで、全体管理者アカウントの資格情報を入力し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="5a2c1-129">[ **ユーザーサインイン** ] ページで、[ **シングルサイン**オンを有効にする] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="5a2c1-130">[ **シングルサインオンを有効にする** ] ページで、[ **資格情報の入力**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="5a2c1-131">[ **Windows セキュリティ** ] ダイアログボックスで、 **user1** と user1 アカウントのパスワードを入力し、[ **OK**] を選択して、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="5a2c1-132">[ **構成の準備完了** ] ページで、[ **構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="5a2c1-133">[ **構成の完了** ] ページで、[ **終了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="5a2c1-134">Azure portal の左側のウィンドウで、[azure **Active Directory**  >  **azure AD Connect**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="5a2c1-135">**シームレスなシングルサインオン**機能が**有効**として表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="5a2c1-136">次に、user1@testlab を使用してサブスクリプションにサインインできることをテストし <strong>ます。</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="5a2c1-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="5a2c1-137">を使用してサブスクリプションにサインインする機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="5a2c1-138">[すべて] の Internet Explorer で、[設定] アイコンを選択し、[ **インターネットオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="5a2c1-139">[ **インターネットオプション**] で、[ **セキュリティ** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="5a2c1-140">[ **ローカルイントラネット**] を選択し、[ **サイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="5a2c1-141">[ **ローカルイントラネット**] で、[ **詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="5a2c1-142">[**この web サイトをゾーンに追加する**] で、「 **https:<span>/</span>autologon.microsoftazuread-sso.com**」と入力し、[**追加**] [  >  **Close**  >  **ok**  >  **ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-142">In **Add this website to the zone**, enter **https<span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="5a2c1-143">サインアウトして、再度サインインします。その際に、別のアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="5a2c1-144">サインインするように求めるメッセージが表示されたら、user1@testlab を指定し <strong>ます。</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="5a2c1-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="5a2c1-145">名前を入力し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-145">name, and then select **Next**.</span></span> <span data-ttu-id="5a2c1-146">パスワードの入力を求められることなく、User1 として正常にサインインできるはずです。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="5a2c1-147">サインインできた場合、Azure AD シームレス SSO が機能していることになります。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="5a2c1-148">User1 には TESTLAB AD DS ドメインに対するドメイン管理者のアクセス許可がありますが、Azure AD のグローバル管理者ではないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="5a2c1-149">そのため、**[管理者]** アイコンはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="5a2c1-150">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-150">Here is your resulting configuration:</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="5a2c1-152">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-152">This configuration consists of:</span></span>

- <span data-ttu-id="5a2c1-153">DNS ドメインのテストラボでの Microsoft 365 E5 試用版または有料サブスクリプション。\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="5a2c1-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="5a2c1-154">が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-154">registered.</span></span>
- <span data-ttu-id="5a2c1-155">インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="5a2c1-156">Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="5a2c1-157">Azure AD のシームレスな SSO が有効になっているので、シミュレートされたイントラネット上のコンピューターは、ユーザーアカウントのパスワードを指定せずに Microsoft 365 cloud リソースにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="5a2c1-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="5a2c1-158">Next step</span></span>

<span data-ttu-id="5a2c1-159">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="5a2c1-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a2c1-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a2c1-160">See also</span></span>

[<span data-ttu-id="5a2c1-161">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="5a2c1-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5a2c1-162">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="5a2c1-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5a2c1-163">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a2c1-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
