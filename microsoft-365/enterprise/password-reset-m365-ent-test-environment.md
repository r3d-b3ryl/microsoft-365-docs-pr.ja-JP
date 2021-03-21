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
ms.openlocfilehash: efcaaf9ed1873c0908bb0e64644b8e10de280a01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921494"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4680b-103">Microsoft 365 テスト環境のパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="4680b-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4680b-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境の Microsoft 365 でのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="4680b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4680b-105">Azure Active Directory (Azure AD) のセルフサービスによるパスワードのリセット (SSPR) によって、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="4680b-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="4680b-106">この記事では、Microsoft 365 テスト環境でパスワードのリセットを構成およびテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4680b-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="4680b-107">SSPR のセットアップには、次の 3 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="4680b-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="4680b-108">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="4680b-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="4680b-109">フェーズ 2: パスワード ライトバックの有効化</span><span class="sxs-lookup"><span data-stu-id="4680b-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="4680b-110">フェーズ 3: パスワードのリセットを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="4680b-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4680b-112">Microsoft 365 for enterprise Test Lab Guide スタックのすべての記事へのビジュアル マップについては [、「Microsoft 365 for enterprise Test Lab Guide Stack」を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="4680b-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4680b-113">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="4680b-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4680b-114">最初に、パスワード ハッシュ同期の手順 [に従います](password-hash-sync-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="4680b-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="4680b-115">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="4680b-115">Your resulting configuration looks like this:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="4680b-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="4680b-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="4680b-118">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="4680b-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="4680b-119">Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。</span><span class="sxs-lookup"><span data-stu-id="4680b-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="4680b-120">Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="4680b-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="4680b-121">フェーズ 2: パスワード ライトバックの有効化</span><span class="sxs-lookup"><span data-stu-id="4680b-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="4680b-122">[フェーズ 2 のパスワード ライトバックのテスト ラボ ガイド](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4680b-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="4680b-123">パスワード リセットを使用するには、パスワード ライトバックを有効にしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4680b-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="4680b-124">フェーズ 3: パスワードのリセットを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="4680b-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="4680b-125">このフェーズでは、グループ メンバーシップを使用して Azure ADテナントでパスワードのリセットを構成し、それが動作するように確認します。</span><span class="sxs-lookup"><span data-stu-id="4680b-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="4680b-126">最初に、特定の Azure AD グループ内のアカウントのパスワードのリセットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4680b-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="4680b-127">ブラウザーのプライベート インスタンスから [https://portal.azure.com](https://portal.azure.com) を開き、全体管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="4680b-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="4680b-128">Azure ポータルで、[Azure **Active Directory グループ]**  >  **[新しいグループ**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="4680b-129">**[グループの種類]** を **[セキュリティ]**、**[グループ名]** を **[PWReset]**、**[メンバーシップの種類]** を **[割り当て済み]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4680b-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="4680b-130">[ **メンバー] を** 選択し、[ **ユーザー 3] を** 見つけて選択し、[選択] **を選択し**、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="4680b-131">**[グループ]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4680b-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="4680b-132">[Azure Active Directory] ウィンドウで、左側 **のナビゲーションで [パスワード** のリセット] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4680b-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="4680b-133">**[パスワードのリセット - プロパティ]** ページの **[セルフサービスによるパスワードのリセットの有効化]** オプションで **[選択済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4680b-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="4680b-134">[**グループの選択]** を選択し **、PWReset グループを選択** し、[保存の選択]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="4680b-135">プライベート ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4680b-135">Close the private browser instance.</span></span>

<span data-ttu-id="4680b-136">次に、User 3 アカウントのパスワードリセットをテストします。</span><span class="sxs-lookup"><span data-stu-id="4680b-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="4680b-137">新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/ssprsetup](https://aka.ms/ssprsetup) を参照します。</span><span class="sxs-lookup"><span data-stu-id="4680b-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="4680b-138">User 3 アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="4680b-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="4680b-139">[必要 **な詳細] で、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="4680b-140">**[アカウントにアクセスできるようにする]** の認証用電話を携帯電話番号に設定し、認証用メールを仕事用や個人用メール アカウントに設定します。</span><span class="sxs-lookup"><span data-stu-id="4680b-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="4680b-141">両方が確認された後、[見栄えの良い] **を** 選択し、ブラウザーのプライベート インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4680b-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="4680b-142">新しいプライベート ブラウザー インスタンスで、 に移動します [https://aka.ms/sspr](https://aka.ms/sspr) 。</span><span class="sxs-lookup"><span data-stu-id="4680b-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="4680b-143">[ユーザー 3] アカウント名を入力し、CAPTCHA の文字を入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="4680b-144">検証 **手順 1 の場合は、[** 別 **のメールにメールを送信する**] を選択し、[メール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="4680b-145">電子メールを受信したら、確認コードを入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="4680b-146">[ **アカウントに戻る] で**、User 3 アカウントの新しいパスワードを入力し、[完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4680b-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="4680b-147">変更された User 3 アカウントのパスワードをメモし、安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="4680b-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="4680b-148">同じブラウザの別のタブで[https://portal.office.com](https://portal.office.com)に移動し、ユーザー 3 アカウント名およびその新しいパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="4680b-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="4680b-149">**[Microsoft Office Home]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4680b-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="4680b-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="4680b-150">Next step</span></span>

<span data-ttu-id="4680b-151">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="4680b-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4680b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="4680b-152">See also</span></span>

[<span data-ttu-id="4680b-153">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="4680b-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4680b-154">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="4680b-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4680b-155">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="4680b-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)