---
title: Microsoft 365 エンタープライズテスト環境多要素認証
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: Microsoft 365 エンタープライズテスト環境でスマートフォンに送信されるテキストメッセージを使用して、多要素認証を構成します。
ms.openlocfilehash: e26fb7470e01397266f5f424ee45941a79a2940c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819378"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="26c64-103">Microsoft 365 Enterprise テスト環境用の多要素認証</span><span class="sxs-lookup"><span data-stu-id="26c64-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="26c64-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="26c64-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="26c64-105">サブスクリプションに対して Azure AD テナントを使用する Microsoft 365 または任意のサービスまたはアプリケーションにサインインするための追加のセキュリティレベルについては、Azure 多要素認証を有効にすることができます。これには、アカウントを確認するために、ユーザー名とパスワードだけを必要とします。</span><span class="sxs-lookup"><span data-stu-id="26c64-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="26c64-106">多要素認証を使用する場合、ユーザーは電話での通話を承認する必要があり、テキストメッセージで送信された検証コードを入力するか、またはパスワードを正しく入力した後にスマートフォンでアプリによる認証を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c64-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="26c64-107">この第 2 の認証要素が満たされた後でのみ、ユーザーはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="26c64-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="26c64-108">この記事では、特定のユーザーアカウントに対してテキストメッセージベースの認証を有効にし、テストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26c64-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="26c64-109">Microsoft 365 エンタープライズテスト環境のアカウントに対して多要素認証をセットアップするには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="26c64-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="26c64-110">Microsoft 365 Enterprise のテスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="26c64-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="26c64-111">User 2 アカウントに対して、多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="26c64-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="26c64-112">条件付きアクセスポリシーを使用して多要素認証を有効にしてテストします (オプション)。</span><span class="sxs-lookup"><span data-stu-id="26c64-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="26c64-114">Microsoft 365 Enterprise のテストラボガイドスタックにあるすべての記事へのビジュアルマップの[テストラボガイドスタック](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)に移動します。</span><span class="sxs-lookup"><span data-stu-id="26c64-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="26c64-115">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="26c64-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="26c64-116">最小要件での軽量な方法で多要素認証をテストする場合は、「[ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="26c64-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="26c64-117">シミュレートされたエンタープライズで多要素認証をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="26c64-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="26c64-118">多要素認証をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="26c64-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="26c64-119">この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。</span><span class="sxs-lookup"><span data-stu-id="26c64-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="26c64-120">フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="26c64-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="26c64-121">次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="26c64-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="26c64-122">ブラウザーのプライベートインスタンスを個別に開き、Microsoft 365 管理センター () に移動して、 [https://portal.microsoft.com](https://portal.microsoft.com) 全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="26c64-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="26c64-123">左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="26c64-124">[アクティブなユーザー] ウィンドウで、[**多要素認証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="26c64-125">リストで、 **User 2**アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="26c64-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="26c64-126">**User 2** セクションで、**[クイック操作]** の **[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="26c64-127">**[多要素認証を有効にする方法の概要]** ダイアログ ボックスで、**[Multi-Factor Auth を有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="26c64-128">[**更新が成功しまし**た] ダイアログボックスで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="26c64-129">[ **Microsoft 365 管理センター** ] タブで、右上の [ユーザーアカウント] アイコンをクリックし、[**サインアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="26c64-130">ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26c64-130">Close your browser instance.</span></span>
   
<span data-ttu-id="26c64-131">次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。</span><span class="sxs-lookup"><span data-stu-id="26c64-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="26c64-132">ブラウザーの新しいプライベートインスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="26c64-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="26c64-133">Office 365 ポータル () に移動 [https://portal.office.com](https://portal.office.com) し、User 2 のアカウント名とパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="26c64-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="26c64-134">サインインした後、詳細についてはアカウントをセットアップするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26c64-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="26c64-135">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="26c64-136">**[追加のセキュリティ確認]** ページで、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="26c64-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="26c64-137">国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="26c64-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="26c64-138">テキスト メッセージを受信するスマート フォンの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="26c64-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="26c64-139">[**メソッド**] の [**テキストメッセージでコードを送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="26c64-140">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="26c64-141">スマート フォンで受信したテキスト メッセージに記載されている確認コードを入力して、**[確認]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="26c64-142">[**手順 3: 既存のアプリケーションを使用**したままにする] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="26c64-p104">User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。元のパスワードと、新しいパスワードを 2 回入力して、**[パスワードを更新してサインイン]** をクリックします。新しいパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="26c64-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="26c64-146">ブラウザーの [ **Microsoft Office Home** ] タブに、ユーザー2の office ポータルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26c64-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="26c64-147">フェーズ 3: 条件付きアクセスポリシーを使用して多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="26c64-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="26c64-148">*このフェーズは、Microsoft 365 エンタープライズテスト環境に対してのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="26c64-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="26c64-149">このフェーズでは、グループと条件付きアクセスポリシーを使用して、User 3 アカウントに対して多要素認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="26c64-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="26c64-150">次に、MFAUsers という名前の新しいグループを作成し、そのグループに User 3 アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="26c64-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="26c64-151">[ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションの [**グループ**] をクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="26c64-152">[**グループの追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="26c64-153">[**グループの種類を選択**してください] ウィンドウで、[**セキュリティ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="26c64-154">[**基本の設定**] ウィンドウで、[**グループの作成**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="26c64-155">[**グループの追加の確認と完了**] ウィンドウで、「 **mfausers**」と入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="26c64-156">グループの一覧で、[ **Mfausers** ] グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="26c64-157">[ **Mfausers** ] ウィンドウで、[**メンバー**] をクリックし、[**すべて表示**] をクリックして、[メンバーの管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="26c64-158">[ **Mfausers** ] ウィンドウで、[**メンバーの追加**] をクリックし、 **User 3**のアカウントを選択してから、[保存] をクリック **> 閉じる > close**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="26c64-159">次に、MFAUsers グループのメンバーに対して多要素認証を必要とする条件付きアクセスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="26c64-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="26c64-160">ブラウザーの新しいタブで、に移動 [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="26c64-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="26c64-161">[ **Azure Active Directory > セキュリティ > 条件付きアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="26c64-162">[**条件付きアクセス–ポリシー** ] ウィンドウで、[**新しいポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="26c64-163">**新しい**ウィンドウで、[**名前**] に**ユーザーアカウントの MFA**を入力します。</span><span class="sxs-lookup"><span data-stu-id="26c64-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="26c64-164">[**割り当て**] セクションで、[**ユーザーとグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="26c64-165">[**ユーザーとグループ**] ウィンドウの [**含める**] タブで、[ユーザーとグループの > 選択] をクリックし **> 選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="26c64-166">[**選択**] ウィンドウで、[ **mfausers** ] グループをクリックし、[ **> の完了] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="26c64-167">**新しい**ウィンドウの [**アクセス制御**] セクションで、[**付与**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="26c64-168">[**付与**] ウィンドウで、[**多要素認証を必要とする**] をクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="26c64-169">**新しい**ウィンドウで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c64-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="26c64-170">**Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26c64-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="26c64-171">このポリシーをテストするには、サインアウトして、User 3 アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="26c64-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="26c64-172">MFA の構成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26c64-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="26c64-173">これは、MFAUsers ポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="26c64-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="26c64-174">運用環境で多要素認証を展開するための情報とリンクについては、Id フェーズで[多要素認証](identity-secure-user-sign-ins.md#identity-mfa)手順を設定するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c64-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="26c64-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="26c64-175">Next step</span></span>

<span data-ttu-id="26c64-176">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="26c64-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="26c64-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="26c64-177">See also</span></span>

[<span data-ttu-id="26c64-178">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="26c64-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="26c64-179">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="26c64-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="26c64-180">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="26c64-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="26c64-181">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="26c64-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
