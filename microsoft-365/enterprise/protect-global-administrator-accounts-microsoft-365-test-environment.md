---
title: Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する
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
description: 次の手順を使用して、Microsoft 365 Enterprise テスト環境の全体管理者アカウントを保護します。
ms.openlocfilehash: e33790d62adbac4f9b8d816041d28b9dfdf36095
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596744"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3813c-103">Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="3813c-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3813c-104">*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="3813c-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="3813c-105">組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。</span><span class="sxs-lookup"><span data-stu-id="3813c-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="3813c-106">この記事では、Azure Active Directory (Azure AD) 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3813c-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="3813c-107">Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護するには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="3813c-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="3813c-108">Microsoft 365 Enterprise のテスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="3813c-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="3813c-109">専用のグローバル管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="3813c-109">Protect your dedicated global administrator account.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3813c-111">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3813c-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3813c-112">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="3813c-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3813c-113">最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3813c-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3813c-114">シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3813c-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3813c-115">グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3813c-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3813c-116">グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="3813c-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="3813c-117">フェーズ 2: 条件付きアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="3813c-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="3813c-118">最初に、専用のグローバル管理者として新しいユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3813c-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="3813c-119">別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。</span><span class="sxs-lookup"><span data-stu-id="3813c-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="3813c-120">[**ユーザー > アクティブユーザー**] をクリックし、[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="3813c-121">[**ユーザーの追加**] ウィンドウで、[**名前**]、[**表示名**]、および [ユーザー**名**] に**DedicatedAdmin**入力します。</span><span class="sxs-lookup"><span data-stu-id="3813c-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="3813c-122">[**パスワード**] をクリックし、[**パスワードの作成を許可**する] をクリックして、強力なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="3813c-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="3813c-123">この新しいアカウントのパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="3813c-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="3813c-124">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-124">Click **Next**.</span></span>
6. <span data-ttu-id="3813c-125">[**製品ライセンスの割り当て**] ウィンドウで、[ **Microsoft 365 e5** ] または [ **Office 365 E5**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="3813c-126">[**オプションの設定**] ウィンドウで、[**役割**] をクリックし、[**管理センター** ] [アクセス] および [**グローバル管理者**] を選択します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="3813c-127">[**ほぼ完了**] ウィンドウで、[**追加の完了**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="3813c-128">次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3813c-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="3813c-129">[ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションの [**グループ**] をクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="3813c-130">[**グループの追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="3813c-131">[**グループの種類を選択**してください] ウィンドウで、[**セキュリティ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="3813c-132">[**基本の設定**] ウィンドウで、[**グループの作成**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="3813c-133">[**グループの追加の確認と完了**] ウィンドウで、「 **globaladmins**」と入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="3813c-134">グループの一覧で、[ **Globaladmins** ] グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="3813c-135">[ **Globaladmins** ] ウィンドウで、[**メンバー**] をクリックし、[**すべて表示**] をクリックして、[メンバーの管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="3813c-136">[ **Globaladmins** ] ウィンドウで、[**メンバーの追加**] をクリックし、 **DedicatedAdmin**アカウントとグローバル管理者アカウントを選択して、[保存] をクリックし **> 閉じる**] を > します。</span><span class="sxs-lookup"><span data-stu-id="3813c-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="3813c-137">次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが中または高の場合は認証を拒否します。</span><span class="sxs-lookup"><span data-stu-id="3813c-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="3813c-138">この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3813c-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="3813c-139">ブラウザーの新しいタブで、に[https://portal.azure.com](https://portal.azure.com)移動します。</span><span class="sxs-lookup"><span data-stu-id="3813c-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="3813c-140">[ **Azure Active Directory > セキュリティ > 条件付きアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="3813c-141">[**条件付きアクセス–ポリシー** ] ウィンドウで、[**ベースラインポリシー: 管理者に MFA を必須にする (プレビュー)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="3813c-142">[**基準ポリシー** ] ウィンドウで、[**直ちにポリシーを使用 > 保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="3813c-143">この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="3813c-144">[**条件付きアクセス–ポリシー** ] ウィンドウで、[**新しいポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="3813c-145">**新しい**ウィンドウで、[**名前**] に「**グローバル管理者**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3813c-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="3813c-146">[**割り当て**] セクションで、[**ユーザーとグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="3813c-147">[**ユーザーとグループ**] ウィンドウの [**含める**] タブで、[ユーザーとグループの > 選択] をクリックし **> 選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="3813c-148">[**選択**] ウィンドウで、[ **globaladmins** ] グループをクリックし、[ **> の完了] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="3813c-149">[**割り当て**] セクションで、[**条件**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="3813c-150">[**条件**] ウィンドウで、 **[サインインリスク**] をクリックし、[**構成**] で [**はい**] をクリックして、[**高**と**中**] をクリックし、[**選択**して**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="3813c-151">**新しい**ウィンドウの [**アクセス制御**] セクションで、[**付与**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="3813c-152">[**付与**] ウィンドウで、[**アクセスをブロック**] をクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="3813c-153">**新しい**ウィンドウで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3813c-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="3813c-154">**Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3813c-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="3813c-155">最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="3813c-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="3813c-156">MFA の構成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3813c-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="3813c-157">これは、最初のポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="3813c-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="3813c-158">運用の全体管理者アカウントを保護するための情報とリンクについては、Id フェーズの[グローバル管理者アカウントの保護](identity-create-protect-global-admins.md#identity-global-admin)の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3813c-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="3813c-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="3813c-159">Next step</span></span>

<span data-ttu-id="3813c-160">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="3813c-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3813c-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="3813c-161">See also</span></span>

[<span data-ttu-id="3813c-162">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="3813c-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="3813c-163">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="3813c-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3813c-164">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="3813c-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3813c-165">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="3813c-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
