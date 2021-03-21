---
title: Microsoft 365 for enterprise test environment multi-factor authentication
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
description: エンタープライズ テスト環境向け Microsoft 365 のスマートフォンに送信されるテキスト メッセージを使用して、多要素認証を構成します。
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923758"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2961-103">エンタープライズ テスト環境向け Microsoft 365 の多要素認証</span><span class="sxs-lookup"><span data-stu-id="d2961-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2961-104">*このテスト ラボ ガイドは、Microsoft 365 for enterprise と 365 Enterprise テストOffice両方に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="d2961-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d2961-105">Microsoft 365 またはサブスクリプションに Azure AD テナントを使用するサービスまたはアプリケーションにサインインする追加のレベルのセキュリティについては、アカウントを確認するためにユーザー名とパスワード以上を必要とする Azure AD 多要素認証を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d2961-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="d2961-106">多要素認証では、ユーザーは、パスワードを正しく入力した後、電話を確認したり、テキスト メッセージで送信された検証コードを入力したり、スマートフォンでアプリで認証を確認したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2961-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="d2961-107">この 2 番目の認証要素が満たされた後にのみサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d2961-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="d2961-108">この記事では、特定のユーザー アカウントのテキスト メッセージ ベース認証を有効にしてテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2961-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="d2961-109">エンタープライズ テスト環境用に Microsoft 365 でアカウントの多要素認証を設定するには、2 つのフェーズと 3 番目のオプション フェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="d2961-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="d2961-110">フェーズ 1: エンタープライズ テスト環境向け Microsoft 365 を構築する</span><span class="sxs-lookup"><span data-stu-id="d2961-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d2961-111">フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="d2961-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="d2961-112">フェーズ 3: 条件付きアクセス ポリシーを使用して多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="d2961-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d2961-114">Microsoft 365 for enterprise Test Lab Guide スタックのすべての記事へのビジュアル マップについては [、「Microsoft 365 for enterprise Test Lab Guide Stack」を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="d2961-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2961-115">フェーズ 1: エンタープライズ テスト環境向け Microsoft 365 を構築する</span><span class="sxs-lookup"><span data-stu-id="d2961-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2961-116">最小要件で軽量な方法で多要素認証をテストする場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="d2961-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d2961-117">シミュレートされたエンタープライズで多要素認証をテストする場合は、「パススルー認証」の [手順に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="d2961-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2961-118">多要素認証のテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="d2961-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d2961-119">この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。</span><span class="sxs-lookup"><span data-stu-id="d2961-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="d2961-120">フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="d2961-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="d2961-121">次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。</span><span class="sxs-lookup"><span data-stu-id="d2961-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="d2961-122">ブラウザーの別のプライベート インスタンスを開き、Microsoft 365 管理センター ( ) に移動し、グローバル管理者アカウント [https://portal.microsoft.com](https://portal.microsoft.com) でサインインします。</span><span class="sxs-lookup"><span data-stu-id="d2961-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="d2961-123">左側のナビゲーションで、[ユーザーがアクティブな **ユーザー]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="d2961-124">[アクティブ ユーザー] ウィンドウで、[多要素認証] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="d2961-125">一覧で、[ユーザー **2] アカウントを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d2961-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="d2961-126">[ユーザー **2] セクションの** [クイック ステップ] **で**、[有効にする] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="d2961-127">[多 **要素認証の有効化について]** ダイアログ ボックスで、[多要素認証を有効 **にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="d2961-128">[成功した **更新プログラム] ダイアログ ボックス** で、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="d2961-129">**[Microsoft 365 管理** センター] タブで、右上のユーザー アカウント アイコンを選択し、[サインアウト]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="d2961-130">ブラウザー インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d2961-130">Close your browser instance.</span></span>
   
<span data-ttu-id="d2961-131">次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。</span><span class="sxs-lookup"><span data-stu-id="d2961-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="d2961-132">ブラウザーの新しいプライベート インスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2961-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="d2961-133">[Microsoft 365 管理センターに移動](https://admin.microsoft.com)し、User 2 アカウント名とパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="d2961-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="d2961-134">サインイン後、詳細については、アカウントのセットアップを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2961-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="d2961-135">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2961-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="d2961-136">**[追加のセキュリティ確認]** ページで、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="d2961-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="d2961-137">国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2961-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="d2961-138">テキスト メッセージを受信するスマートフォンの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2961-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="d2961-139">[ **メソッド] で**、[ **テキスト メッセージでコードを送信する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="d2961-140">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2961-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="d2961-141">スマートフォンで受信したテキスト メッセージから確認コードを入力し、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="d2961-142">[手順 **3: 既存のアプリケーションを** 保持する] ページで、[完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="d2961-143">User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。</span><span class="sxs-lookup"><span data-stu-id="d2961-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="d2961-144">元のパスワードと新しいパスワードを 2 回入力し、[パスワードの更新とサインイン **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="d2961-145">新しいパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="d2961-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="d2961-146">ブラウザーの [ホームOffice] タブにユーザー 2 Microsoft Office **ポータル** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2961-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="d2961-147">フェーズ 3: 条件付きアクセス ポリシーを使用して多要素認証を有効にしてテストする</span><span class="sxs-lookup"><span data-stu-id="d2961-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="d2961-148">*このフェーズは、エンタープライズ テスト環境用の Microsoft 365 でのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="d2961-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="d2961-149">このフェーズでは、グループと条件付きアクセス ポリシーを使用して、User 3 アカウントの多要素認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d2961-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="d2961-150">次に、MFAUsers という名前の新しいグループを作成し、ユーザー 3 アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2961-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="d2961-151">**[Microsoft 365 管理** センター]タブで、左側のナビゲーションで [グループ] を選択し、[グループ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="d2961-152">[グループ **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="d2961-153">[グループの **種類の選択] ウィンドウで** 、[セキュリティ] **を選択** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="d2961-154">[基本 **の設定] ウィンドウで、[グループの作成** ] を選択 **し**、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="d2961-155">[グループの **確認と追加の完了] ウィンドウで\*\*\*\*、「MFAUsers」** と入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="d2961-156">グループの一覧で **、MFAUsers グループを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d2961-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="d2961-157">**[MFAUsers] ウィンドウで[\*\*\*\*メンバー]** を選択し、[すべて表示] を選択して **メンバーを管理します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="d2961-158">**[MFAUsers] ウィンドウで、[** メンバーの追加]**を選択し**、[**ユーザー 3]** アカウントを選択し、[閉じる保存]  >  **を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="d2961-159">次に、MFAUsers グループのメンバーに多要素認証を要求する条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2961-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="d2961-160">ブラウザーの新しいタブで、 に移動します [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="d2961-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d2961-161">[Azure **Active Directory セキュリティ**  >  **の条件付**  >  **きアクセス] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="d2961-162">[条件付き **アクセス - ポリシー] ウィンドウで、[** 新しいポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="d2961-163">[新しい **] ウィンドウ** で、[名前] **ボックスにユーザー アカウント** の MFA と **入力** します。</span><span class="sxs-lookup"><span data-stu-id="d2961-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="d2961-164">[割り **当て] セクションで** 、[ユーザーと **グループ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="d2961-165">[ユーザーと **グループ] ウィンドウ** の [含める]**タブ** で、[ユーザーとグループの選択] [ユーザーと **グループ**  >  **の選択] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="d2961-166">[選択 **] ウィンドウで\*\*\*\*、[MFAUsers] グループを選択** し、[完了の選択]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="d2961-167">[新しい **] ウィンドウの** [アクセス制御] セクション **で、[** 許可] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="d2961-168">[付与 **] ウィンドウで** 、[多 **要素認証を要求** する] を選択し、[選択] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="d2961-169">[新しい **] ウィンドウで**、[ポリシーの有効化 **] で [オン\*\*\*\*] を** 選択し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d2961-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="d2961-170">Azure portal **タブと Microsoft** **365 管理センター タブを閉** じます。</span><span class="sxs-lookup"><span data-stu-id="d2961-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="d2961-171">このポリシーをテストするには、サインアウトして User 3 アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="d2961-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="d2961-172">MFA の構成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2961-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="d2961-173">これは、MFAUsers ポリシーが適用されているのを示しています。</span><span class="sxs-lookup"><span data-stu-id="d2961-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="d2961-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="d2961-174">Next step</span></span>

<span data-ttu-id="d2961-175">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="d2961-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2961-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2961-176">See also</span></span>

[<span data-ttu-id="d2961-177">ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="d2961-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="d2961-178">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="d2961-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d2961-179">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="d2961-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d2961-180">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="d2961-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)