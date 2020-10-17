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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワードのリセットを構成してテストします。'
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487426"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="72377-103">Microsoft 365 テスト環境のパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="72377-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="72377-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="72377-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="72377-105">Azure Active Directory (Azure AD) のセルフサービスによるパスワードのリセット (SSPR) によって、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="72377-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="72377-106">この記事では、Microsoft 365 テスト環境でパスワードのリセットを構成およびテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="72377-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="72377-107">SSPR のセットアップには、3つのフェーズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="72377-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="72377-108">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="72377-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="72377-109">フェーズ 2: パスワード ライトバックの有効化</span><span class="sxs-lookup"><span data-stu-id="72377-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="72377-110">フェーズ 3: パスワードのリセットを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="72377-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="72377-112">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72377-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="72377-113">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="72377-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="72377-114">最初に、「 [パスワードハッシュの同期](password-hash-sync-m365-ent-test-environment.md)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="72377-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="72377-115">結果の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="72377-115">Your resulting configuration looks like this:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="72377-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="72377-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="72377-118">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="72377-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="72377-119">インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="72377-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="72377-120">Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="72377-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="72377-121">フェーズ 2: パスワード ライトバックの有効化</span><span class="sxs-lookup"><span data-stu-id="72377-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="72377-122">[フェーズ 2 のパスワード ライトバックのテスト ラボ ガイド](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="72377-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="72377-123">パスワード リセットを使用するには、パスワード ライトバックを有効にしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="72377-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="72377-124">フェーズ 3: パスワードのリセットを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="72377-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="72377-125">このフェーズでは、グループメンバーシップを使用して Azure AD テナントのパスワードのリセットを構成し、正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="72377-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="72377-126">最初に、特定の Azure AD グループ内のアカウントのパスワードのリセットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="72377-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="72377-127">ブラウザーのプライベート インスタンスから [https://portal.azure.com](https://portal.azure.com) を開き、全体管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="72377-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="72377-128">Azure portal で、[ **azure Active Directory**  >  **グループ**の  >  **新規グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="72377-129">**[グループの種類]** を **[セキュリティ]**、**[グループ名]** を **[PWReset]**、**[メンバーシップの種類]** を **[割り当て済み]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="72377-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="72377-130">[ **メンバー**] を選択し、[ **ユーザー 3**] を見つけて選択し、[ **選択**] を選択して、[ **作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="72377-131">**[グループ]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="72377-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="72377-132">[Azure Active Directory] ウィンドウで、左側のナビゲーションの [ **パスワードのリセット** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="72377-133">**[パスワードのリセット - プロパティ]** ページの **[セルフサービスによるパスワードのリセットの有効化]** オプションで **[選択済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="72377-134">[**グループの選択**] を選択し、 **PWReset**グループを選択して、[保存 **]** を選択し  >  **Save**ます。</span><span class="sxs-lookup"><span data-stu-id="72377-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="72377-135">プライベート ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="72377-135">Close the private browser instance.</span></span>

<span data-ttu-id="72377-136">次に、ユーザー3アカウントのパスワードのリセットをテストします。</span><span class="sxs-lookup"><span data-stu-id="72377-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="72377-137">新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/ssprsetup](https://aka.ms/ssprsetup) を参照します。</span><span class="sxs-lookup"><span data-stu-id="72377-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="72377-138">User 3 アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="72377-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="72377-139">[ **詳細情報の入力**] で、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="72377-140">**[アカウントにアクセスできるようにする]** の認証用電話を携帯電話番号に設定し、認証用メールを仕事用や個人用メール アカウントに設定します。</span><span class="sxs-lookup"><span data-stu-id="72377-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="72377-141">両方が確認されたら、[ **良好**] を選択し、ブラウザーのプライベートインスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="72377-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="72377-142">新しいプライベートブラウザーインスタンスで、に移動し [https://aka.ms/sspr](https://aka.ms/sspr) ます。</span><span class="sxs-lookup"><span data-stu-id="72377-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="72377-143">User 3 のアカウント名を入力し、CAPTCHA の文字を入力して、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="72377-144">**確認手順 1**の場合は、[連絡用メールを**送信**する] を選択し、[**電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="72377-145">電子メールを受信したら、確認コードを入力して、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="72377-146">[ **アカウントに戻る**] で、User 3 アカウントの新しいパスワードを入力して、[ **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72377-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="72377-147">変更された User 3 アカウントのパスワードをメモし、安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="72377-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="72377-148">同じブラウザの別のタブで[https://portal.office.com](https://portal.office.com)に移動し、ユーザー 3 アカウント名およびその新しいパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="72377-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="72377-149">**[Microsoft Office Home]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72377-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="72377-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="72377-150">Next step</span></span>

<span data-ttu-id="72377-151">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="72377-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="72377-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="72377-152">See also</span></span>

[<span data-ttu-id="72377-153">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="72377-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="72377-154">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="72377-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="72377-155">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72377-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
