---
title: エンタープライズテスト環境の多要素認証のための Microsoft 365
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
description: エンタープライズテスト環境の Microsoft 365 で、スマートフォンに送信されるテキストメッセージを使用して、多要素認証を構成します。
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558444"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="24b87-103">Microsoft 365 for enterprise テスト環境での多要素認証</span><span class="sxs-lookup"><span data-stu-id="24b87-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="24b87-104">*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="24b87-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="24b87-105">サブスクリプションに対して Azure AD テナントを使用する Microsoft 365 またはサービスまたはアプリケーションにサインインするための追加のセキュリティレベルについては、Azure AD 多要素認証を有効にすることができます。これには、アカウントを確認するために、ユーザー名とパスワードだけを必要とします。</span><span class="sxs-lookup"><span data-stu-id="24b87-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="24b87-106">多要素認証を使用する場合、ユーザーは電話での通話を承認する必要があり、テキストメッセージで送信された検証コードを入力するか、またはパスワードを正しく入力した後にスマートフォンでアプリによる認証を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24b87-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="24b87-107">この2番目の認証要因が満たされた後にのみ、サインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="24b87-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="24b87-108">この記事では、特定のユーザーアカウントに対してテキストメッセージベースの認証を有効にし、テストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24b87-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="24b87-109">Microsoft 365 のアカウントに多要素認証を設定するエンタープライズテスト環境には、2つのフェーズと3番目のフェーズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24b87-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="24b87-110">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="24b87-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="24b87-111">フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="24b87-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="24b87-112">フェーズ 3: 条件付きアクセスポリシーを使用して多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="24b87-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="24b87-114">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24b87-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="24b87-115">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="24b87-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="24b87-116">最小要件での軽量な方法で多要素認証をテストする場合は、「 [ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="24b87-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="24b87-117">シミュレートされたエンタープライズで多要素認証をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="24b87-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="24b87-118">多要素認証をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="24b87-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="24b87-119">この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。</span><span class="sxs-lookup"><span data-stu-id="24b87-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="24b87-120">フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="24b87-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="24b87-121">次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="24b87-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="24b87-122">ブラウザーのプライベートインスタンスを個別に開き、Microsoft 365 管理センター () に移動して、 [https://portal.microsoft.com](https://portal.microsoft.com) 全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="24b87-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="24b87-123">左側のナビゲーションで、[**ユーザー**  >  の **アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="24b87-124">[アクティブなユーザー] ウィンドウで、[ **多要素認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="24b87-125">リストで、 **User 2** アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="24b87-126">[ **User 2** ] セクションの [ **クイック操作**] で、[ **有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="24b87-127">[ **多要素認証を有効に** する] ダイアログボックスで、[ **多要素認証を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="24b87-128">[ **更新が成功しまし** た] ダイアログボックスで、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="24b87-129">[ **Microsoft 365 管理センター** ] タブで、右上の [ユーザーアカウント] アイコンを選択し、[ **サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="24b87-130">ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="24b87-130">Close your browser instance.</span></span>
   
<span data-ttu-id="24b87-131">次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。</span><span class="sxs-lookup"><span data-stu-id="24b87-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="24b87-132">ブラウザーの新しいプライベートインスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="24b87-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="24b87-133">[Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、User 2 のアカウント名とパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="24b87-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="24b87-134">サインインした後、詳細についてはアカウントをセットアップするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24b87-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="24b87-135">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="24b87-136">**[追加のセキュリティ確認]** ページで、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="24b87-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="24b87-137">国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="24b87-138">テキストメッセージを受信するスマートフォンの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="24b87-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="24b87-139">[ **メソッド**] で、[ **テキストメッセージでコードを送信する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="24b87-140">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="24b87-141">スマートフォンで受信したテキストメッセージの確認コードを入力して、[ **確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="24b87-142">[ **手順 3: 既存のアプリケーションを使用** したままにする] ページで、[ **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="24b87-143">User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。</span><span class="sxs-lookup"><span data-stu-id="24b87-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="24b87-144">元のパスワードと新しいパスワードを2回入力し、[ **Update password**] を選び、[サインイン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="24b87-145">新しいパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="24b87-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="24b87-146">ブラウザーの [ **Microsoft Office Home** ] タブに、ユーザー2の office ポータルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24b87-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="24b87-147">フェーズ 3: 条件付きアクセスポリシーを使用して多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="24b87-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="24b87-148">*このフェーズは、Microsoft 365 for enterprise テスト環境に対してのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="24b87-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="24b87-149">このフェーズでは、グループと条件付きアクセスポリシーを使用して、User 3 アカウントに対して多要素認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="24b87-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="24b87-150">次に、MFAUsers という名前の新しいグループを作成し、そのグループに User 3 アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="24b87-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="24b87-151">[ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションで [ **グループ** ] を選択し、[ **グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="24b87-152">[ **グループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="24b87-153">[ **グループの種類を選択** してください] ウィンドウで、[ **セキュリティ**] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="24b87-154">[ **基本の設定** ] ウィンドウで、[ **グループの作成**] を選択し、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="24b87-155">[ **グループの追加の確認と完了** ] ウィンドウで、[ **mfausers**] と入力し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="24b87-156">グループの一覧で、[ **Mfausers** ] グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="24b87-157">[ **Mfausers** ] ウィンドウで、[ **メンバー**] を選択し、[ **すべて表示**] を選択して、[メンバーの管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24b87-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="24b87-158">[ **Mfausers** ] ウィンドウで、[**メンバーの追加**] を選択し、 **User 3** のアカウントを選択してから、[**保存** して閉じる] を選択し  >  **Close**  >  **Close** ます。</span><span class="sxs-lookup"><span data-stu-id="24b87-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="24b87-159">次に、MFAUsers グループのメンバーに対して多要素認証を必要とする条件付きアクセスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="24b87-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="24b87-160">ブラウザーの新しいタブで、に移動 [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="24b87-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="24b87-161">[ **Azure Active Directory**  >  **セキュリティ**  >  **条件付きアクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="24b87-162">[ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **新しいポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="24b87-163">**新しい** ウィンドウで、[**名前**] ボックスに「**ユーザーアカウントの MFA** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="24b87-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="24b87-164">[ **割り当て** ] セクションで、[ **ユーザーとグループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="24b87-165">[**ユーザーとグループ**] ウィンドウの [**包含**] タブで、[ユーザーとグループの **選択**] の [ユーザーとグループの選択] を選択し  >  **Users and groups**  >  **Select** ます。</span><span class="sxs-lookup"><span data-stu-id="24b87-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="24b87-166">**[選択**] ウィンドウで、[ **mfausers** ] グループを選択し、[完了 **]** を選択し  >  **Done** ます。</span><span class="sxs-lookup"><span data-stu-id="24b87-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="24b87-167">[**新規**] ウィンドウの [**アクセス制御**] セクションで、[**付与**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="24b87-168">[ **付与** ] ウィンドウで、[ **多要素認証を必要とする**] を選択してから、[ **選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24b87-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="24b87-169">[**新規**] ウィンドウで、[**有効なポリシー**] の [オン] を選択し、[**作成**] を選択します。 **On**</span><span class="sxs-lookup"><span data-stu-id="24b87-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="24b87-170">**Azure portal** および **Microsoft 365 管理センター** のタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="24b87-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="24b87-171">このポリシーをテストするには、サインアウトして、User 3 アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="24b87-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="24b87-172">MFA の構成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24b87-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="24b87-173">これは、MFAUsers ポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="24b87-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="24b87-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="24b87-174">Next step</span></span>

<span data-ttu-id="24b87-175">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="24b87-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="24b87-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="24b87-176">See also</span></span>

[<span data-ttu-id="24b87-177">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="24b87-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="24b87-178">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="24b87-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="24b87-179">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="24b87-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="24b87-180">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24b87-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
