---
title: Microsoft 365 エンタープライズ テスト環境でのグローバル管理者アカウントを保護します。
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
description: Microsoft 365 エンタープライズ テスト環境でのグローバル管理者アカウントを保護するためにこれらの手順を使用します。
ms.openlocfilehash: 4d444e217c5a232811701f6519c2eb3ebe86df70
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869022"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d95e0-103">Microsoft 365 エンタープライズ テスト環境でのグローバル管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d95e0-p101">管理者アカウントは、可能な限り保護することによって、組織のデジタルの攻撃を防ぐことができます。この資料では、グローバル管理者アカウントを保護するために Office 365 のクラウド アプリケーションのセキュリティと Azure AD の条件付きのアクセス ポリシーを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="d95e0-106">Microsoft 365 エンタープライズ テスト環境でのグローバル管理者アカウントを保護するための 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="d95e0-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="d95e0-107">Microsoft 365 エンタープライズ テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="d95e0-108">専用のグローバル管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-108">Protect your dedicated global administrator account.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d95e0-110">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d95e0-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d95e0-111">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d95e0-112">最小要件で軽量な方法でグローバル ・ アドミニストレータ ・ アカウントの保護をテストする場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d95e0-113">シミュレートされた企業内のグローバル ・ アドミニストレータ ・ アカウントの保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d95e0-p102">インターネットに接続されている保護は、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットのグローバル管理者アカウントをテストし、Windows サーバーの AD フォレストの場合、ディレクトリ同期。グローバル ・ アドミニストレータ ・ アカウントの保護をテストし、通常の組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="d95e0-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="d95e0-116">フェーズ 2: は、クラウド アプリケーションのセキュリティとアクセスの条件付きポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="d95e0-117">最初に、グローバル ・ アドミニストレータ ・ アカウント ・ アクティビティを監視し、グローバル ・ アドミニストレータ ・ アカウントの電子メール アドレスに通知を送信するのには、Office 365 のクラウド アプリケーションのセキュリティ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="d95e0-118">Office のポータルにサインインするのに[http://portal.office.com](http://portal.office.com)のグローバル管理者アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-118">Sign in to the Office portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="d95e0-p103">**管理者**のタイルをクリックします。**Office 管理者センター** ] タブで、クリックして**管理センター > セキュリティおよびコンプライアンスに関する**。</span><span class="sxs-lookup"><span data-stu-id="d95e0-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="d95e0-121">左側のナビゲーション ウィンドウで、 **[アラート] > [高度な警告の管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="d95e0-122">**[高度な警告の管理]** ページで、 **[Office 365 Cloud App Security を有効にする]** をクリックし、 **[Office 365 Cloud App Security に移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="d95e0-123">新しい **[ダッシュボード]** タブから **[制御] > [ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="d95e0-124">**[ポリシー]** ページで、 **[ポリシーの作成]** をクリックし、次に **[アクティビティ ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="d95e0-125">**[ポリシー名]** に「 **管理アクティビティ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="d95e0-126">**[ポリシー重要度]** で、 **[高]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="d95e0-127">**[カテゴリ]** で、 **[特権アカウント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="d95e0-128">**[ポリシーのフィルターの作成]** の **[以下のすべてに該当するアクティビティ]** で、 **[管理アクティビティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="d95e0-p104">**[アラート]** で、 **[アラートを電子メールとして送信する]** をクリックします。 **[送信先]** に、全体管理者アカウントの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="d95e0-131">ページの下部にある **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="d95e0-132">**ダッシュ ボード**] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d95e0-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="d95e0-133">次に、専用の大域管理者として、新しいユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="d95e0-134">**Office 管理者センター** ] タブで [**アクティブなユーザー\*\*\*\*ユーザーの追加**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="d95e0-135">[**新しいユーザー** ] ページでは、**姓**、**表示名**、および**ユーザー名**で**DedicatedAdmin**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="d95e0-p105">**パスワード**をクリックして**自分でパスワードを作成する**には、強力なパスワードを入力します。この新しいアカウントのパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="d95e0-138">**そのユーザーが初めてサインインするときにパスワードの変更**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="d95e0-139">**ロール**をクリックし、**グローバル ・ アドミニストレーター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="d95e0-140">**製品のライセンス**をクリックしを [**エンタープライズ モビリティとセキュリティの E5**と**Office 365 のエンタープライズ E5 のライセンス**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="d95e0-141">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-141">Click **Add**.</span></span>
8. <span data-ttu-id="d95e0-142">**ユーザーがページに追加された**、[**パスワードを電子メールで送信する**をオフにし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="d95e0-143">次に、GlobalAdmins という名前の新しいグループを作成し、DedicatedAdmin のアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="d95e0-144">**Office 管理者センター** ] タブで、[左側のナビゲーションでは、[グループ] アイコンをクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="d95e0-145">[**グループの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="d95e0-146">[**新しいグループ**] ページで、 **GlobalAdmins**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="d95e0-147">**所有者の選択**] をクリックし、グローバル管理者アカウントをクリック**追加 > 閉じる**。</span><span class="sxs-lookup"><span data-stu-id="d95e0-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="d95e0-148">グループの一覧では、 **GlobalAdmins**グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="d95e0-149">[ **GlobalAdmins** ] ページで、**メンバーの編集**] をクリックし、[**メンバーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="d95e0-150">一覧で、 **DedicatedAdmin**のアカウント] をクリックし、**を保存 > 閉じる > 閉じる > 管理センター**です。</span><span class="sxs-lookup"><span data-stu-id="d95e0-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="d95e0-151">次に、グローバル管理者アカウントに対してマルチファクター認証方法を必要として、サインインのリスクが中または高の場合、認証を拒否するのには、条件付きのアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="d95e0-152">この最初のポリシーでは、すべてのグローバル管理者アカウントが、MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d95e0-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="d95e0-153">お使いのブラウザーの新しいタブで「 [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="d95e0-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d95e0-154">クリックして**Azure Active Directory > 条件付きアクセス**です。</span><span class="sxs-lookup"><span data-stu-id="d95e0-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="d95e0-155">**条件付きアクセス ポリシー**のブレードでをクリックして**のベースライン ポリシー: 管理者 (プレビュー) の MFA を必要とする**。</span><span class="sxs-lookup"><span data-stu-id="d95e0-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="d95e0-p106">**ベースライン ポリシー**のブレードでをクリックして**ポリシーを使用して、すぐに > 保存**。</span><span class="sxs-lookup"><span data-stu-id="d95e0-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="d95e0-158">この 2 つ目ポリシー ブロックへのアクセスが中または高にサインインしているリスクのグローバル管理者アカウントの認証です。</span><span class="sxs-lookup"><span data-stu-id="d95e0-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="d95e0-159">**条件付きアクセス ポリシー**のブレードでは、**新しいポリシー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="d95e0-160">**新規**ブレードでは、**グローバル管理者\*\*\*\*名**で入力します。</span><span class="sxs-lookup"><span data-stu-id="d95e0-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="d95e0-161">[**割り当て**] セクションで、**ユーザーとグループ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="d95e0-162">**ユーザーとグループ**のブレードの [**挿入**] タブでをクリックして**ユーザーおよびグループを選択 > ユーザーとグループ > を選択して**。</span><span class="sxs-lookup"><span data-stu-id="d95e0-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="d95e0-163">ブレード**を選択して**をクリックして、 **GlobalAdmins > 選択 > 実行**。</span><span class="sxs-lookup"><span data-stu-id="d95e0-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="d95e0-164">[**割り当て**] セクションで [**条件**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="d95e0-165">**条件**ブレードの**リスクでサインイン**] をクリックして **[はい]** をクリックすると、**構成**の**高**、**中\*\*\*\*を選択**し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="d95e0-166">**新規**ブレードの [**アクセス制御**] セクションで、**許可**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="d95e0-167">**補助金**のブレードでは、**アクセスをブロックする**をクリックし、**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="d95e0-168">**新規**ブレードでの**ポリシーを有効にする**には、\*\*\*\* をクリックし、し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d95e0-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="d95e0-169">[ **Azure ポータル**および**Office 管理者センター** ] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d95e0-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="d95e0-p107">最初のポリシーをテストするには、サインアウトして、DedicatedAdmin のアカウントでサインインします。ユーザー アカウントの MFA を構成するのにはメッセージが表示する必要があります。これは、最初のポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d95e0-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="d95e0-173">情報と生産のグローバル管理者アカウントを保護するためのリンクの識別段階では、[グローバル管理者アカウントを保護する](identity-designate-protect-admin-accounts.md)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d95e0-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="d95e0-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="d95e0-174">Next step</span></span>

<span data-ttu-id="d95e0-175">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="d95e0-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d95e0-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="d95e0-176">See also</span></span>

[<span data-ttu-id="d95e0-177">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="d95e0-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="d95e0-178">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="d95e0-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d95e0-179">Microsoft 365 エンタープライズ展開</span><span class="sxs-lookup"><span data-stu-id="d95e0-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d95e0-180">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="d95e0-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
