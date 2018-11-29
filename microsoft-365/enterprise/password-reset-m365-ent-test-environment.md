---
title: Microsoft 365 テスト環境のパスワードのリセット
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワードのリセットを構成してテストします。'
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869581"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bd4e6-103">Microsoft 365 テスト環境のパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="bd4e6-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bd4e6-104">Azure AD のセルフサービスによるパスワードのリセット (SSPR) によって、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="bd4e6-105">この記事では、Microsoft 365 テスト環境でパスワードの構成およびリセットを行う方法を、次の 2 つのフェーズに分けて説明します。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="bd4e6-106">パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-106">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="bd4e6-107">User 2 アカウントのパスワードのリセットを構成してテストする。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-107">Configure and test password reset for the User 2 account.</span></span>
    
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="bd4e6-109">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bd4e6-110">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="bd4e6-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bd4e6-p101">「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-p101">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="bd4e6-114">この構成は、次の内容で構成されます:</span><span class="sxs-lookup"><span data-stu-id="bd4e6-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="bd4e6-115">Office 365 E5 および EMS E5 試用版サブスクリプションまたは永続サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-115">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="bd4e6-116">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="bd4e6-117">Azure AD Connect が APP1 上で実行され、TESTLAB Windows Server AD ドメインが、Office 365 および EMS E5 サブスクリプションの Azure AD テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="bd4e6-118">フェーズ 2: パスワードのリセットを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="bd4e6-118">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="bd4e6-119">このフェーズでは、グループ メンバーシップとして、Azure AD テナントでパスワードのリセットを構成し、それが機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-119">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="bd4e6-120">最初に、特定の Azure AD グループ内のアカウントのパスワードのリセットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-120">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="bd4e6-121">ブラウザーのプライベート インスタンスから [https://portal.azure.com](https://portal.azure.com) を開き、全体管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-121">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="bd4e6-122">Azure portal で **[Azure Active Directory] > [グループ] > [新しいグループ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-122">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="bd4e6-p102">**[グループの種類]** を **[セキュリティ]**、**[グループ名]** を **[PWReset]**、**[メンバーシップの種類]** を **[割り当て済み]** に設定し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="bd4e6-125">リストの中から **[PWReset]** グループをクリックし、**[メンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-125">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="bd4e6-p103">**[メンバーの追加]** > **[User 2]** > **[選択** の順にクリックします。その後、**[PWReset]** ページおよび **[グループ]** ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="bd4e6-128">Azure Active Directory のページで、**[パスワードのリセット]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-128">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="bd4e6-129">**[プロパティ]** ページの、**[セルフサービスによるパスワードのリセットの有効化]** オプションで **[選択済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-129">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="bd4e6-130">**[グループの選択]** から **[PWReset]** をクリックし、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-130">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="bd4e6-131">プライベート ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-131">Close the private browser instance.</span></span>

<span data-ttu-id="bd4e6-132">次に、User 2 アカウントのパスワードのリセットをテストします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-132">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="bd4e6-133">新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/ssprsetup](https://aka.ms/ssprsetup) を参照します。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-133">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="bd4e6-134">User 2 アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-134">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="bd4e6-135">**[アカウントにアクセスできるようにする]** の認証用電話を携帯電話番号に設定し、認証用メールを仕事用や個人用メール アカウントに設定します。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-135">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="bd4e6-136">認証用の電話とメールに問題がなければ、**[問題ありません]** をクリックして、ブラウザーのプライベート インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-136">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="bd4e6-137">新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/sspr](https://aka.ms/sspr) に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-137">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="bd4e6-138">User 2 アカウントの資格情報でサインインして、CAPTCHA で示された文字を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-138">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="bd4e6-p104">**[認証手順 1]** で、**[連絡用メール アドレスにメールする]** をクリックし、**[メール]** をクリックします。メールを受信したら、認証コードを入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="bd4e6-p105">**[アカウントに戻る]** で、User 2 アカウントの新しいパスワードを入力し、**[終了]** をクリックします。User 2 アカウントの変更したパスワードのメモを取り、安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="bd4e6-p106">同じブラウザーの別のタブで [https://portal.office.com](https://portal.office.com) に移動し、User 2 アカウント名と新しいパスワードでサインインすると、**Office Home** のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-p106">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="bd4e6-145">実稼働環境でのパスワードのリセットの構成に関する情報およびリンクについては、ID フェーズの手順、「[パスワードのリセットを簡素化する](identity-password-reset.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-145">See the [Simplify password resets](identity-password-reset.md) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="bd4e6-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="bd4e6-146">Next step</span></span>

<span data-ttu-id="bd4e6-147">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="bd4e6-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd4e6-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd4e6-148">See also</span></span>

[<span data-ttu-id="bd4e6-149">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="bd4e6-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="bd4e6-150">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="bd4e6-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bd4e6-151">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="bd4e6-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
