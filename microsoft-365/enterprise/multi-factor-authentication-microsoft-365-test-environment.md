---
title: Microsoft 365 Enterprise テスト環境用の多要素認証
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 エンタープライズテスト環境でスマートフォンに送信されるテキストメッセージを使用して、多要素認証を構成します。
ms.openlocfilehash: af4ae63f52fa74084dfddf0e6861c5ae3ba2aedb
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673263"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b7104-103">Microsoft 365 Enterprise テスト環境用の多要素認証</span><span class="sxs-lookup"><span data-stu-id="b7104-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b7104-104">*このテストラボガイドは、Microsoft 365 Enterprise と Office 365 のエンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="b7104-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b7104-105">Office 365 へのサインイン、または組織に対して Azure AD テナントを使用するサービスまたはアプリケーションに対して追加のセキュリティレベルを設定するには、Azure 多要素認証を有効にします。これには、ユーザー名とパスワードだけを使用して確認することができます。分割払.</span><span class="sxs-lookup"><span data-stu-id="b7104-105">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="b7104-106">多要素認証では、ユーザーは電話での通話を承認する必要があり、テキストメッセージで送信された検証コードを入力するか、またはパスワードを正しく入力した後にスマートフォンでアプリパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7104-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="b7104-107">この第 2 の認証要素が満たされた後でのみ、ユーザーはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="b7104-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="b7104-108">この記事では、特定のアカウントに対してテキストメッセージベースの認証を有効にし、テストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7104-108">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="b7104-109">Microsoft 365 エンタープライズテスト環境のアカウントに対して多要素認証をセットアップするには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="b7104-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="b7104-110">Microsoft 365 Enterprise のテスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="b7104-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="b7104-111">User 2 アカウントに対して、多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="b7104-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b7104-113">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b7104-113">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b7104-114">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="b7104-114">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b7104-115">最小要件での軽量な方法で多要素認証をテストする場合は、「[ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b7104-115">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b7104-116">シミュレートされたエンタープライズで多要素認証をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b7104-116">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7104-117">多要素認証をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7104-117">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b7104-118">この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。</span><span class="sxs-lookup"><span data-stu-id="b7104-118">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="b7104-119">フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="b7104-119">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="b7104-120">次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="b7104-120">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="b7104-121">ブラウザーのプライベートインスタンスを個別に開き、Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動して、全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="b7104-121">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="b7104-122">左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-122">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="b7104-123">[アクティブなユーザー] ウィンドウで、[ **More > 多要素認証のセットアップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
4. <span data-ttu-id="b7104-124">リストで、 **User 2**アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7104-124">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="b7104-125">**User 2** セクションで、**[クイック操作]** の **[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="b7104-126">**[多要素認証を有効にする方法の概要]** ダイアログ ボックスで、**[Multi-Factor Auth を有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="b7104-127">[**更新が成功しまし**た] ダイアログボックスで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="b7104-128">[ **Microsoft 365 管理センター** ] タブで、右上の [ユーザーアカウント] アイコンをクリックし、[**サインアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-128">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="b7104-129">ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b7104-129">Close your browser instance.</span></span>
   
<span data-ttu-id="b7104-130">次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。</span><span class="sxs-lookup"><span data-stu-id="b7104-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="b7104-131">ブラウザーの新しいプライベートインスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7104-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="b7104-132">Office 365 ポータル ([https://portal.office.com](https://portal.office.com)) に移動し、User 2 のアカウント名とパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b7104-132">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="b7104-133">サインインした後、詳細についてはアカウントをセットアップするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7104-133">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="b7104-134">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-134">Click **Next**.</span></span>
    
4. <span data-ttu-id="b7104-135">**[追加のセキュリティ確認]** ページで、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="b7104-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="b7104-136">国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7104-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="b7104-137">テキスト メッセージを受信するスマート フォンの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7104-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="b7104-138">[**メソッド**] の [**テキストメッセージでコードを送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="b7104-139">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="b7104-140">スマート フォンで受信したテキスト メッセージに記載されている確認コードを入力して、**[確認]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="b7104-141">**[手順 3: 既存のアプリケーションを使用し続ける]** ページで、User 2 アカウント用に表示されているアプリ パスワードを安全な場所に記録してから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7104-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="b7104-p104">User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。元のパスワードと、新しいパスワードを 2 回入力して、**[パスワードを更新してサインイン]** をクリックします。新しいパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="b7104-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="b7104-145">ブラウザーの [ **Microsoft Office Home** ] タブに、ユーザー2の office ポータルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7104-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="b7104-146">運用環境で多要素認証を展開するための情報とリンクについては、Id フェーズで[多要素認証](identity-secure-user-sign-ins.md#identity-mfa)手順を設定するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7104-146">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="b7104-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="b7104-147">Next step</span></span>

<span data-ttu-id="b7104-148">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="b7104-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7104-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7104-149">See also</span></span>

[<span data-ttu-id="b7104-150">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="b7104-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b7104-151">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="b7104-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b7104-152">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="b7104-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b7104-153">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="b7104-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
