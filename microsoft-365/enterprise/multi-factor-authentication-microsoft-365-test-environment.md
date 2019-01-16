---
title: Microsoft 365 エンタープライズの複数要素の認証はテスト環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 エンタープライズ テスト環境でスマート フォンに送信されるテキスト メッセージを使用して複数要素の認証を構成します。
ms.openlocfilehash: 353f09253794670e8107e084acb3a01cd309fd60
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869001"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="09c08-103">Microsoft 365 エンタープライズの複数要素の認証はテスト環境</span><span class="sxs-lookup"><span data-stu-id="09c08-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="09c08-p101">Office 365 または組織の Azure AD テナントを使用するアプリケーションやサービスへのサインインのセキュリティのレベル、だけで複数のユーザー名とパスワードを確認する必要がありますが、Azure の多要素認証を有効にできます、アカウントです。多要素認証は、ユーザーは、確認の電話、テキスト メッセージで送信された確認コードを入力、または自分のパスワードを正しく入力した後、スマート フォンのアプリのパスワードを指定する必要があります。この 2 番目の認証要素が満たされた後にのみ、サインインできます。</span><span class="sxs-lookup"><span data-stu-id="09c08-p101">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account. With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords. They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="09c08-107">この資料では、有効にして、特定のアカウントのテキスト メッセージ ベースの認証をテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09c08-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="09c08-108">Microsoft 365 エンタープライズ テスト環境でアカウントを複数要素の認証を設定するのには 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="09c08-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="09c08-109">Microsoft 365 エンタープライズ テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="09c08-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="09c08-110">User 2 アカウントに対して、多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="09c08-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="09c08-112">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="09c08-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="09c08-113">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="09c08-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="09c08-114">最小要件で軽量な方法で複数要素の認証をテストする場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="09c08-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="09c08-115">シミュレートされた企業内の複数要素の認証をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="09c08-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="09c08-p102">多要素認証のテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。提供されてここでは、オプション多要素認証をテストし、一般的な組織を表す環境で試すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="09c08-p102">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="09c08-118">フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="09c08-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="09c08-119">次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="09c08-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="09c08-120">ブラウザーのインスタンスを個別に秘密を開き、Office のポータルに移動 ([https://office.com](https://office.com))、し、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="09c08-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="09c08-121">ポータルのメイン ページで、**[管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="09c08-122">左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="09c08-123">ユーザーのアクティブなウィンドウをクリックして**より > 多要素認証の設定**。</span><span class="sxs-lookup"><span data-stu-id="09c08-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="09c08-124">の一覧では、 **2 のユーザー**アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="09c08-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="09c08-125">**User 2** セクションで、**[クイック操作]** の **[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="09c08-126">**[多要素認証を有効にする方法の概要]** ダイアログ ボックスで、**[Multi-Factor Auth を有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="09c08-127">**正常な更新**] ダイアログ ボックスで [**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="09c08-128">**[Microsoft Office Home]** タブで、右上部分にあるユーザー アカウントのアイコンをクリックし、**[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="09c08-129">ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="09c08-129">Close your browser instance.</span></span>
   
<span data-ttu-id="09c08-130">次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。</span><span class="sxs-lookup"><span data-stu-id="09c08-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="09c08-131">お使いのブラウザーの新しい、プライベート インスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="09c08-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="09c08-132">Office のポータルに移動 ([https://office.com](https://office.com)) と 2 のユーザー アカウントでサインイン (user2 @\<組織名 >. onmicrosoft.com) とパスワードです。</span><span class="sxs-lookup"><span data-stu-id="09c08-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="09c08-p103">サインイン後、詳細については、アカウントを設定するように求められます。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-p103">After signing in, you are prompted to set up the account for more information. Click **Next**.</span></span>
    
4. <span data-ttu-id="09c08-135">**[追加のセキュリティ確認]** ページで、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="09c08-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="09c08-136">国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="09c08-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="09c08-137">テキスト メッセージを受信するスマート フォンの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="09c08-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="09c08-138">**メソッド**では、**コード、テキスト メッセージを送信してもらう**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="09c08-139">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="09c08-140">スマート フォンで受信したテキスト メッセージに記載されている確認コードを入力して、**[確認]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="09c08-141">**[手順 3: 既存のアプリケーションを使用し続ける]** ページで、User 2 アカウント用に表示されているアプリ パスワードを安全な場所に記録してから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c08-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="09c08-p104">User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。元のパスワードと、新しいパスワードを 2 回入力して、**[パスワードを更新してサインイン]** をクリックします。新しいパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="09c08-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="09c08-145">お使いのブラウザーの [ **Microsoft Office のホーム**] タブで、Office のポータルのユーザー 2 のはずです。</span><span class="sxs-lookup"><span data-stu-id="09c08-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="09c08-146">情報と実稼働環境での複数要素の認証を展開するリンクの識別段階では、[多要素認証のセットアップ](identity-multi-factor-authentication.md)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c08-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="09c08-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="09c08-147">Next step</span></span>

<span data-ttu-id="09c08-148">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="09c08-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="09c08-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="09c08-149">See also</span></span>

[<span data-ttu-id="09c08-150">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="09c08-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="09c08-151">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="09c08-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="09c08-152">Microsoft 365 エンタープライズ展開</span><span class="sxs-lookup"><span data-stu-id="09c08-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="09c08-153">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="09c08-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
