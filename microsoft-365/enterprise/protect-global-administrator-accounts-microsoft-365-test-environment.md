---
title: Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 次の手順を使用して、Microsoft 365 Enterprise テスト環境の全体管理者アカウントを保護します。
ms.openlocfilehash: 89985f99f5471aab87189e78035062add2c6bad9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673333"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a16b0-103">Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="a16b0-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a16b0-104">*このテストラボガイドは、Microsoft 365 エンタープライズテスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="a16b0-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a16b0-105">組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。</span><span class="sxs-lookup"><span data-stu-id="a16b0-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="a16b0-106">この記事では、Azure Active Directory (Azure AD) 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="a16b0-107">Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護するには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="a16b0-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="a16b0-108">Microsoft 365 Enterprise のテスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="a16b0-109">専用のグローバル管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-109">Protect your dedicated global administrator account.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a16b0-111">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a16b0-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a16b0-112">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="a16b0-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a16b0-113">最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a16b0-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a16b0-114">シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="a16b0-115">グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a16b0-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="a16b0-116">グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="a16b0-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="a16b0-117">フェーズ 2: 条件付きアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a16b0-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="a16b0-118">最初に、専用のグローバル管理者として新しいユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="a16b0-119">別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。</span><span class="sxs-lookup"><span data-stu-id="a16b0-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="a16b0-120">[**アクティブなユーザー**] で、[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="a16b0-121">[**新しいユーザー** ] ページで、[**名前**]、[**表示名**]、および [**ユーザー名**] に**DedicatedAdmin**入力します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="a16b0-122">[**パスワード**] をクリックし、[**パスワードの作成を許可**する] をクリックして、強力なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="a16b0-123">この新しいアカウントのパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="a16b0-124">**[このユーザーが最初にサインインしたときにパスワードを変更するのをクリアする**。</span><span class="sxs-lookup"><span data-stu-id="a16b0-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="a16b0-125">[**ロール**] をクリックし、[**全体管理者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="a16b0-126">[**製品ライセンス**] をクリックし、 **Enterprise Mobility + Security e5**および**Office 365 enterprise e5 ライセンス**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-126">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="a16b0-127">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-127">Click **Add**.</span></span>
9. <span data-ttu-id="a16b0-128">[**ユーザーが追加されました] ページ**で、[**電子メールでパスワードを送信**する] をオフにして、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="a16b0-129">次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="a16b0-130">**Microsoft 365 管理センター**のタブで、左側のナビゲーションの [グループ] アイコンをクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="a16b0-131">[**グループの追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="a16b0-132">[**新しいグループ**] ページで、「 **globaladmins**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="a16b0-133">[**所有者の選択**] をクリックし、全体管理者アカウントをクリックしてから、[**追加 > 閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="a16b0-134">グループの一覧で、[ **Globaladmins** ] グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="a16b0-135">[ **Globaladmins** ] ページで、[**メンバーの編集**] をクリックし、[**メンバーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="a16b0-136">一覧で、 **DedicatedAdmin**アカウントをクリックし、[保存] をクリックして **> 閉じる > > 管理センターを閉じ**ます。</span><span class="sxs-lookup"><span data-stu-id="a16b0-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="a16b0-137">次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが中または高の場合は認証を拒否します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="a16b0-138">この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16b0-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="a16b0-139">ブラウザーの新しいタブで、に[https://portal.azure.com](https://portal.azure.com)移動します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a16b0-140">[ **Azure Active Directory > 条件付きアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="a16b0-141">[**条件付きアクセス–ポリシー** ] ブレードで、[**ベースラインポリシー: 管理者に MFA を必須とする (プレビュー)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="a16b0-142">[**基準ポリシー...**</span><span class="sxs-lookup"><span data-stu-id="a16b0-142">On the **Baseline policies…**</span></span> <span data-ttu-id="a16b0-143">ブレードで、[**今すぐポリシーを使用 > 保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="a16b0-144">この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="a16b0-145">[**条件付きアクセス–ポリシー** ] ブレードで、[**新しいポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="a16b0-146">**新しい**ブレードで、[**名前**] に「 **Global administrators** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="a16b0-147">[**割り当て**] セクションで、[**ユーザーとグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="a16b0-148">[**ユーザーとグループ**] ブレードの [**含める**] タブで、[ユーザーとグループの**選択 > ユーザーとグループの選択] > 選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="a16b0-149">**[選択]** ブレードで、[ **globaladmins] > [> 完了] を選択**します。</span><span class="sxs-lookup"><span data-stu-id="a16b0-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="a16b0-150">[**割り当て**] セクションで、[**条件**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="a16b0-151">[**条件**] ブレードで、 **[サインインリスク**] をクリックし、[**構成**] で [**はい**] をクリックして、[**高**と**中**] をクリックし、[**選択**して**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="a16b0-152">**新しい**ブレードの [**アクセス制御**] セクションで、[**付与**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="a16b0-153">[**許可**] ブレードで、[**アクセスのブロック**] をクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="a16b0-154">**新しい**ブレードで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="a16b0-155">**Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a16b0-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="a16b0-156">最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="a16b0-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="a16b0-157">ユーザーアカウントで MFA を構成するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a16b0-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="a16b0-158">これは、最初のポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a16b0-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="a16b0-159">運用の全体管理者アカウントを保護するための情報とリンクについては、Id フェーズの[グローバル管理者アカウントの保護](identity-create-protect-global-admins.md#identity-global-admin)の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a16b0-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a16b0-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="a16b0-160">Next step</span></span>

<span data-ttu-id="a16b0-161">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="a16b0-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a16b0-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="a16b0-162">See also</span></span>

[<span data-ttu-id="a16b0-163">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="a16b0-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a16b0-164">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="a16b0-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a16b0-165">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="a16b0-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a16b0-166">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="a16b0-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
