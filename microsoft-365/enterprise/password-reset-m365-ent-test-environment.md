---
title: Microsoft 365 テスト環境のパスワードのリセット
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワードのリセットを構成してテストします。'
ms.openlocfilehash: 96a8b03ca978ac2b2174742c0208444d853ba7c9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632889"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ed73c-103">Microsoft 365 テスト環境のパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="ed73c-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ed73c-104">*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="ed73c-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ed73c-105">Azure Active Directory (Azure AD) のセルフサービスによるパスワードのリセット (SSPR) によって、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="ed73c-106">この記事では、Microsoft 365 テスト環境でパスワードの構成およびリセットを行う方法を、次の 3 つのフェーズに分けて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.    <span data-ttu-id="ed73c-107">Microsoft 365 Enterprise のテスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="ed73c-108">パスワード ライトバックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-108">Enable password writeback.</span></span>
3.    <span data-ttu-id="ed73c-109">User 3 アカウントのパスワードのリセットを構成してテストする。</span><span class="sxs-lookup"><span data-stu-id="ed73c-109">Configure and test password reset for the User 3 account.</span></span>
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ed73c-111">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ed73c-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ed73c-112">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="ed73c-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ed73c-p101">まず、「[パスワード ハッシュの同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ed73c-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="ed73c-116">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="ed73c-117">Microsoft 365 E5 または Office 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="ed73c-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="ed73c-118">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="ed73c-119">Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="ed73c-120">フェーズ 2: パスワード ライトバックの有効化</span><span class="sxs-lookup"><span data-stu-id="ed73c-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="ed73c-121">[フェーズ 2 のパスワード ライトバックのテスト ラボ ガイド](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ed73c-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="ed73c-122">パスワード リセットを使用するには、パスワード ライトバックを有効にしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ed73c-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="ed73c-123">フェーズ 3: パスワードのリセットを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="ed73c-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="ed73c-124">このフェーズでは、グループ メンバーシップとして、Azure AD テナントでパスワードのリセットを構成し、それが機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="ed73c-125">最初に、特定の Azure AD グループ内のアカウントのパスワードのリセットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="ed73c-126">ブラウザーのプライベート インスタンスから [https://portal.azure.com](https://portal.azure.com) を開き、全体管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="ed73c-127">Azure portal で **[Azure Active Directory] > [グループ] > [新しいグループ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="ed73c-128">**[グループの種類]** を **[セキュリティ]**、**[グループ名]** を **[PWReset]**、**[メンバーシップの種類]** を **[割り当て済み]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="ed73c-129">**[メンバー]** をクリックし**ユーザー 3** を見つけて選択し、**[選択]** をクリックしてから **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="ed73c-130">**[グループ]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="ed73c-131">[Azure Active Directory] ウィンドウで、左側のナビゲーションにある **[パスワードのリセット]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="ed73c-132">**[パスワードのリセット - プロパティ]** ページの **[セルフサービスによるパスワードのリセットの有効化]** オプションで **[選択済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="ed73c-133">**[グループの選択]** をクリックして **[PWReset]** グループを選択し、**[選択] > [保存]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="ed73c-134">プライベート ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-134">Close the private browser instance.</span></span>

<span data-ttu-id="ed73c-135">次に、User 3 アカウントのパスワード リセットをテストします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="ed73c-136">新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/ssprsetup](https://aka.ms/ssprsetup) を参照します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="ed73c-137">User 3 アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="ed73c-138">**[必要な詳細情報]** で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="ed73c-139">**[アカウントにアクセスできるようにする]** の認証用電話を携帯電話番号に設定し、認証用メールを仕事用や個人用メール アカウントに設定します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-139">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="ed73c-140">認証用の電話とメールに問題がなければ、**[問題ありません]** をクリックして、ブラウザーのプライベート インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="ed73c-141">新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/sspr](https://aka.ms/sspr) に移動します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="ed73c-142">User 3 アカウント名を入力し、CAPTCHA に表示された文字を入力してから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="ed73c-p102">**[認証手順 1]** で、**[連絡用メール アドレスにメールする]** をクリックし、**[メール]** をクリックします。メールを受信したら、認証コードを入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="ed73c-145">**[アカウントに戻る]** で User 3 アカウントの新しいパスワードを入力し、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="ed73c-146">変更された User 3 アカウントのパスワードをメモし、安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="ed73c-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="ed73c-147">同じブラウザの別のタブで[https://portal.office.com](https://portal.office.com)に移動し、ユーザー 3 アカウント名およびその新しいパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ed73c-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="ed73c-148">**[Microsoft Office Home]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="ed73c-149">実稼働環境でのパスワードのリセットの構成に関する情報およびリンクについては、ID フェーズの手順、「[パスワードのリセットを簡素化する](identity-secure-your-passwords.md#identity-pw-reset)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed73c-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="ed73c-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="ed73c-150">Next step</span></span>

<span data-ttu-id="ed73c-151">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="ed73c-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed73c-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed73c-152">See also</span></span>

[<span data-ttu-id="ed73c-153">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="ed73c-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ed73c-154">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="ed73c-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ed73c-155">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="ed73c-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
