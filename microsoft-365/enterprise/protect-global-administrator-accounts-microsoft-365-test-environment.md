---
title: エンタープライズテスト環境の Microsoft 365 で全体管理者アカウントを保護する
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
description: 次の手順を使用して、エンタープライズテスト環境の Microsoft 365 のグローバル管理者アカウントを保護します。
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695184"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9316f-103">エンタープライズテスト環境の Microsoft 365 で全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="9316f-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9316f-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="9316f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="9316f-105">組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。</span><span class="sxs-lookup"><span data-stu-id="9316f-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="9316f-106">この記事では、Azure Active Directory (Azure AD) 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9316f-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="9316f-107">エンタープライズテスト環境では、Microsoft 365 のグローバル管理者アカウントを保護するには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="9316f-107">There are two phases to protecting global administrator accounts in your Microsoft 365 for enterprise test environment:</span></span>

1.  <span data-ttu-id="9316f-108">エンタープライズテスト環境用の Microsoft 365 を作成します。</span><span class="sxs-lookup"><span data-stu-id="9316f-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="9316f-109">専用のグローバル管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="9316f-109">Protect your dedicated global administrator account.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9316f-111">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9316f-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9316f-112">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="9316f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9316f-113">最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="9316f-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9316f-114">シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9316f-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9316f-115">グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9316f-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="9316f-116">グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="9316f-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="9316f-117">フェーズ 2: 条件付きアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="9316f-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="9316f-118">最初に、専用のグローバル管理者として新しいユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9316f-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="9316f-119">別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9316f-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="9316f-120">[ **ユーザー > アクティブユーザー**] をクリックし、[ **ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="9316f-121">[**ユーザーの追加**] ウィンドウで、[**名前**]、[**表示名**]、および [ユーザー**名**] に**DedicatedAdmin**入力します。</span><span class="sxs-lookup"><span data-stu-id="9316f-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="9316f-122">[ **パスワード**] をクリックし、[ **パスワードの作成を許可**する] をクリックして、強力なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="9316f-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="9316f-123">この新しいアカウントのパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="9316f-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="9316f-124">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-124">Click **Next**.</span></span>
6. <span data-ttu-id="9316f-125">[ **製品ライセンスの割り当て** ] ウィンドウで、[ **Microsoft 365 E5**] を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="9316f-126">[ **オプションの設定** ] ウィンドウで、[ **役割**] をクリックし、[ **管理センター** ] [アクセス] および [ **グローバル管理者**] を選択します。[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="9316f-127">[ **ほぼ完了** ] ウィンドウで、[ **追加の完了**] をクリックし、[ **閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="9316f-128">次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="9316f-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="9316f-129">[ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションの [ **グループ** ] をクリックし、[ **グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="9316f-130">[ **グループの追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="9316f-131">[ **グループの種類を選択** してください] ウィンドウで、[ **セキュリティ**] を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="9316f-132">[ **基本の設定** ] ウィンドウで、[ **グループの作成**] をクリックし、[ **閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="9316f-133">[ **グループの追加の確認と完了** ] ウィンドウで、「 **globaladmins**」と入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="9316f-134">グループの一覧で、[ **Globaladmins** ] グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="9316f-135">[ **Globaladmins** ] ウィンドウで、[ **メンバー**] をクリックし、[ **すべて表示**] をクリックして、[メンバーの管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="9316f-136">[ **Globaladmins** ] ウィンドウで、[ **メンバーの追加**] をクリックし、 **DedicatedAdmin** アカウントとグローバル管理者アカウントを選択して、[保存] をクリックし **> 閉じる**] を > します。</span><span class="sxs-lookup"><span data-stu-id="9316f-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="9316f-137">次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが中または高の場合は認証を拒否します。</span><span class="sxs-lookup"><span data-stu-id="9316f-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="9316f-138">この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9316f-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="9316f-139">ブラウザーの新しいタブで、に移動 [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="9316f-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="9316f-140">[ **Azure Active Directory > セキュリティ > 条件付きアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="9316f-141">[ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **ベースラインポリシー: 管理者に MFA を必須にする (プレビュー)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="9316f-142">[ **基準ポリシー** ] ウィンドウで、[ **直ちにポリシーを使用 > 保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="9316f-143">この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="9316f-144">[ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **新しいポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="9316f-145">**新しい**ウィンドウで、[**名前**] に「**グローバル管理者**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9316f-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="9316f-146">[ **割り当て** ] セクションで、[ **ユーザーとグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="9316f-147">[**ユーザーとグループ**] ウィンドウの [**含める**] タブで、[ユーザーとグループの > 選択] をクリックし **> 選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="9316f-148">[ **選択** ] ウィンドウで、[ **globaladmins** ] グループをクリックし、[ **> の完了] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="9316f-149">[ **割り当て** ] セクションで、[ **条件**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="9316f-150">[**条件**] ウィンドウで、 **[サインインリスク**] をクリックし、[**構成**] で [**はい**] をクリックして、[**高**と**中**] をクリックし、[**選択**して**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="9316f-151">**新しい**ウィンドウの [**アクセス制御**] セクションで、[**付与**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="9316f-152">[ **付与** ] ウィンドウで、[ **アクセスをブロック**] をクリックし、[ **選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="9316f-153">**新しい**ウィンドウで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9316f-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="9316f-154">**Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9316f-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="9316f-155">最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="9316f-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="9316f-156">MFA の構成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9316f-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="9316f-157">これは、最初のポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="9316f-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="9316f-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="9316f-158">Next step</span></span>

<span data-ttu-id="9316f-159">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="9316f-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9316f-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="9316f-160">See also</span></span>

[<span data-ttu-id="9316f-161">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="9316f-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="9316f-162">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="9316f-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9316f-163">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="9316f-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9316f-164">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9316f-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
