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
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487638"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e1008-103">エンタープライズテスト環境の Microsoft 365 で全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="e1008-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e1008-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="e1008-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e1008-105">組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。</span><span class="sxs-lookup"><span data-stu-id="e1008-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="e1008-106">この記事では、Azure Active Directory (Azure AD) 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1008-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="e1008-107">Microsoft 365 でのグローバル管理者アカウントの保護エンタープライズテスト環境では、次の2つのフェーズが必要になります。</span><span class="sxs-lookup"><span data-stu-id="e1008-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="e1008-108">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="e1008-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e1008-109">フェーズ 2: 条件付きアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="e1008-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e1008-111">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1008-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e1008-112">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="e1008-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e1008-113">最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「軽量な [基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="e1008-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e1008-114">シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1008-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1008-115">グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1008-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="e1008-116">グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="e1008-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="e1008-117">フェーズ 2: 条件付きアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="e1008-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="e1008-118">最初に、専用のグローバル管理者として新しいユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1008-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="e1008-119">別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。</span><span class="sxs-lookup"><span data-stu-id="e1008-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="e1008-120">[**ユーザー**のアクティブなユーザー] を選択し、[  >  **Active users\*\*\*\*ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="e1008-121">[**ユーザーの追加**] ウィンドウで、[**名**]、[**表示名**]、および [ユーザー**名**] ボックスに「 **DedicatedAdmin** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e1008-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="e1008-122">[ **パスワード**] を選択し、[ **パスワードの作成を許可**する] を選択し、強力なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e1008-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="e1008-123">この新しいアカウントのパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="e1008-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="e1008-124">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-124">Select **Next**.</span></span>
6. <span data-ttu-id="e1008-125">[ **製品ライセンスの割り当て** ] ウィンドウで、[ **Microsoft 365 E5**] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="e1008-126">[**オプションの設定**] ウィンドウで、[**ロール**  >  **管理センターアクセス**の  >  **グローバル管理者**] を選択し  >  **Next**ます。</span><span class="sxs-lookup"><span data-stu-id="e1008-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="e1008-127">[ **ほぼ完了** ] ウィンドウで、[ **追加の完了**] を選択し、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="e1008-128">次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e1008-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="e1008-129">[ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションで [ **グループ** ] を選択し、[ **グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="e1008-130">[ **グループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="e1008-131">[ **グループの種類を選択** してください] ウィンドウで、[ **セキュリティ**] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="e1008-132">[ **基本の設定** ] ウィンドウで、[ **グループの作成**] を選択し、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="e1008-133">[ **グループの追加の確認と完了** ] ウィンドウで、「 **globaladmins**」と入力してから、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="e1008-134">グループの一覧で、[ **Globaladmins** ] グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="e1008-135">[ **Globaladmins** ] ウィンドウで、[ **メンバー**] を選択し、[ **すべて表示**] を選択して、[メンバーの管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1008-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="e1008-136">[ **Globaladmins** ] ウィンドウで、[**メンバーの追加**] を選択し、 **DedicatedAdmin**アカウントとグローバル管理者アカウントを選択してから、[**保存**して閉じる] を選択し  >  **Close**  >  **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="e1008-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="e1008-137">次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが [中] または [高] の場合は認証を拒否します。</span><span class="sxs-lookup"><span data-stu-id="e1008-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="e1008-138">この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1008-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="e1008-139">ブラウザーの新しいタブで、に移動 [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="e1008-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="e1008-140">[ **Azure Active Directory**  >  **セキュリティ**] [  >  **条件付きアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1008-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="e1008-141">[ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **ベースラインポリシー: 管理者に MFA を必須にする (プレビュー)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="e1008-142">[ **基準ポリシー** ] ウィンドウで、[ **直ちにポリシーを使用 > 保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="e1008-143">この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="e1008-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="e1008-144">[ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **新しいポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="e1008-145">**新しい**ウィンドウで、[**名前**] に**全体管理者**を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1008-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="e1008-146">[ **割り当て** ] セクションで、[ **ユーザーとグループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="e1008-147">[**ユーザーとグループ**] ウィンドウの [**包含**] タブで、[ユーザーとグループの**選択**] の [ユーザーとグループの選択] を選択し  >  **Users and groups**  >  **Select**ます。</span><span class="sxs-lookup"><span data-stu-id="e1008-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="e1008-148">**[選択**] ウィンドウで、[ **globaladmins** ] グループを選択してから、[完了 **]** を選択し  >  **Done**ます。</span><span class="sxs-lookup"><span data-stu-id="e1008-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="e1008-149">[ **割り当て** ] セクションで、[ **条件**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="e1008-150">[**条件**] ウィンドウで、 **[サインインリスク**] を選択し、[**構成**] で [**はい**] を選択し、[**高**と**中**] を選択して、[**選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="e1008-151">[**新規**] ウィンドウの [**アクセス制御**] セクションで、[**付与**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="e1008-152">[ **付与** ] ウィンドウで、[ **アクセスのブロック**] を選択し、[ **選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1008-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="e1008-153">[**新規**] ウィンドウで、[**有効なポリシー**] の [オン] を選択し、[**作成**] を選択します。 **On**</span><span class="sxs-lookup"><span data-stu-id="e1008-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="e1008-154">**Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1008-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="e1008-155">最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e1008-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="e1008-156">MFA の構成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1008-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="e1008-157">これは、最初のポリシーが適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="e1008-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1008-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1008-158">Next step</span></span>

<span data-ttu-id="e1008-159">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="e1008-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1008-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1008-160">See also</span></span>

[<span data-ttu-id="e1008-161">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="e1008-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="e1008-162">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e1008-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e1008-163">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="e1008-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e1008-164">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1008-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
