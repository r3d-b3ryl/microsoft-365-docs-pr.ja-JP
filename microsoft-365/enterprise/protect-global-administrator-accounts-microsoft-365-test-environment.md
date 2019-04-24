---
title: Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 次の手順を使用して、Microsoft 365 Enterprise テスト環境の全体管理者アカウントを保護します。
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290860"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="336cb-103">Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="336cb-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="336cb-104">組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。</span><span class="sxs-lookup"><span data-stu-id="336cb-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="336cb-105">この記事では、Office 365 Cloud App Security および Azure AD 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="336cb-105">This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="336cb-106">Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護するには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="336cb-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="336cb-107">Microsoft 365 Enterprise テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="336cb-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="336cb-108">専用のグローバル管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="336cb-108">Protect your dedicated global administrator account.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="336cb-110">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="336cb-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

> [!NOTE]
> <span data-ttu-id="336cb-111">Microsoft 365 Enterprise テスト環境では、Office 365 および Enterprise Management + Security (EMS) の E5 バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="336cb-111">The Microsoft 365 Enterprise test environment uses E5 versions of Office 365 and Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="336cb-112">office 365 Cloud App Security 機能は、E5 バージョンの office 365 でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="336cb-112">The Office 365 Cloud App Security feature is only available in the E5 version Office 365.</span></span> 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="336cb-113">フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="336cb-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="336cb-114">最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="336cb-114">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="336cb-115">シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="336cb-115">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="336cb-116">グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="336cb-116">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="336cb-117">グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="336cb-117">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="336cb-118">フェーズ 2: Cloud App Security と条件付きアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="336cb-118">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="336cb-119">最初に、Office 365 Cloud App Security ポリシーを作成して、全体管理者アカウントアクティビティを監視し、グローバル管理者アカウントの電子メールアドレスに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="336cb-119">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="336cb-120">グローバル管理者アカウントを使用して、 [Office 365 Security & コンプライアンスポータル](https://protection.office.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="336cb-120">Sign in to the [Office 365 Security & Compliance portal](https://protection.office.com/) using your global administrator account.</span></span>
2. <span data-ttu-id="336cb-121">左側のナビゲーション ウィンドウで、 **[アラート] > [高度な警告の管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
3. <span data-ttu-id="336cb-122">**[高度な警告の管理]** ページで、 **[Office 365 Cloud App Security を有効にする]** をクリックし、 **[Office 365 Cloud App Security に移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
4. <span data-ttu-id="336cb-123">新しい **[ダッシュボード]** タブから **[制御] > [ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
5. <span data-ttu-id="336cb-124">**[ポリシー]** ページで、 **[ポリシーの作成]** をクリックし、次に **[アクティビティ ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
6. <span data-ttu-id="336cb-125">**[ポリシー名]** に「 **管理アクティビティ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="336cb-125">In **Policy name**, type **Administrative activity**.</span></span>
7. <span data-ttu-id="336cb-126">**[ポリシー重要度]** で、 **[高]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-126">In **Policy severity**, click **High**.</span></span>
8. <span data-ttu-id="336cb-127">**[カテゴリ]** で、 **[特権アカウント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-127">In **Category**, click **Privileged accounts**.</span></span>
9. <span data-ttu-id="336cb-128">**[ポリシーのフィルターの作成]** の **[以下のすべてに該当するアクティビティ]** で、 **[管理アクティビティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
10. <span data-ttu-id="336cb-p104">**[アラート]** で、 **[アラートを電子メールとして送信する]** をクリックします。 **[送信先]** に、全体管理者アカウントの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="336cb-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
11. <span data-ttu-id="336cb-131">ページの下部にある **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-131">At the bottom of the page, click **Create**.</span></span>
12. <span data-ttu-id="336cb-132">[**ダッシュボード**] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="336cb-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="336cb-133">次に、専用のグローバル管理者として新しいユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="336cb-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="336cb-134">別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。</span><span class="sxs-lookup"><span data-stu-id="336cb-134">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="336cb-135">[**アクティブなユーザー**] で、[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-135">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="336cb-136">[**新しいユーザー** ] ページで、[**名前**]、[**表示名**]、および [**ユーザー名**] に**DedicatedAdmin**入力します。</span><span class="sxs-lookup"><span data-stu-id="336cb-136">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="336cb-137">[**パスワード**] をクリックし、[**パスワードの作成を許可**する] をクリックして、強力なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="336cb-137">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="336cb-138">この新しいアカウントのパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="336cb-138">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="336cb-139">**[このユーザーが最初にサインインしたときにパスワードを変更するのをクリアする**。</span><span class="sxs-lookup"><span data-stu-id="336cb-139">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="336cb-140">[**ロール**] をクリックし、[**全体管理者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-140">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="336cb-141">[**製品ライセンス**] をクリックし、 **enterprise Mobility + Security e5**および**Office 365 enterprise e5 ライセンス**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="336cb-141">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="336cb-142">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-142">Click **Add**.</span></span>
9. <span data-ttu-id="336cb-143">[**ユーザーが追加されました] ページ**で、[**電子メールでパスワードを送信**する] をオフにして、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-143">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="336cb-144">次に、globaladmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="336cb-144">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="336cb-145">**Microsoft 365 管理センター**のタブで、左側のナビゲーションの [グループ] アイコンをクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-145">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="336cb-146">[**グループの追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-146">Click **Add a group**.</span></span>
3. <span data-ttu-id="336cb-147">[**新しいグループ**] ページで、「 **globaladmins**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="336cb-147">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="336cb-148">[**所有者の選択**] をクリックし、全体管理者アカウントをクリックしてから、[ **Add > Close**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-148">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="336cb-149">グループの一覧で、[ **globaladmins** ] グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-149">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="336cb-150">[ **globaladmins** ] ページで、[**メンバーの編集**] をクリックし、[**メンバーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-150">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="336cb-151">一覧で、 **DedicatedAdmin**アカウントをクリックし、[保存] をクリックします。 [ **> を閉じる > 閉じる > 管理センター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-151">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="336cb-152">次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが中または高の場合は認証を拒否します。</span><span class="sxs-lookup"><span data-stu-id="336cb-152">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="336cb-153">この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="336cb-153">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="336cb-154">ブラウザーの新しいタブで、に[https://portal.azure.com](https://portal.azure.com)移動します。</span><span class="sxs-lookup"><span data-stu-id="336cb-154">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="336cb-155">[ **Azure Active Directory > 条件付きアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-155">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="336cb-156">[**条件付きアクセス–ポリシー** ] ブレードで、[**ベースラインポリシー: 管理者に MFA を必須とする (プレビュー)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-156">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="336cb-157">[**基準ポリシー...**</span><span class="sxs-lookup"><span data-stu-id="336cb-157">On the **Baseline policies…**</span></span> <span data-ttu-id="336cb-158">ブレードで、[**すぐにポリシーを使用 > 保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-158">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="336cb-159">この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-159">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="336cb-160">[**条件付きアクセス–ポリシー** ] ブレードで、[**新しいポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-160">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="336cb-161">**新しい**ブレードで、[**名前**] に「 **Global administrators** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="336cb-161">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="336cb-162">[**割り当て**] セクションで、[**ユーザーとグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-162">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="336cb-163">[**ユーザーとグループ**] ブレードの [**含める**] タブで、[ユーザーとグループの選択] をクリックし、[ **> ユーザーとグループ > 選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-163">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="336cb-164">**[選択]** ブレードで、[ **globaladmins > select > Done**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-164">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="336cb-165">[**割り当て**] セクションで、[**条件**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-165">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="336cb-166">[**条件**] ブレードで、 **[サインインリスク**] をクリックし、[**構成**] で [**はい**] をクリックして、[**高**と**中**] をクリックし、[**選択**して**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-166">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="336cb-167">**新しい**ブレードの [**アクセス制御**] セクションで、[**付与**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-167">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="336cb-168">[**許可**] ブレードで、[**アクセスのブロック**] をクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-168">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="336cb-169">**新しい**ブレードで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="336cb-169">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="336cb-170">**Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="336cb-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="336cb-171">最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="336cb-171">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="336cb-172">ユーザーアカウントで MFA を構成するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="336cb-172">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="336cb-173">これは、最初のポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="336cb-173">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="336cb-174">運用の全体管理者アカウントを保護するための情報とリンクについては、id フェーズの[グローバル管理者アカウントの保護](identity-designate-protect-admin-accounts.md#identity-global-admin)の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="336cb-174">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="336cb-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="336cb-175">Next step</span></span>

<span data-ttu-id="336cb-176">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="336cb-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="336cb-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="336cb-177">See also</span></span>

[<span data-ttu-id="336cb-178">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="336cb-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="336cb-179">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="336cb-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="336cb-180">Microsoft 365 Enterprise 展開</span><span class="sxs-lookup"><span data-stu-id="336cb-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="336cb-181">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="336cb-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
