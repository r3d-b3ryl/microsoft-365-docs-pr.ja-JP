---
title: エンタープライズ テスト環境用に、Microsoft 365管理者アカウントを保護する
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
description: 次の手順を使用して、エンタープライズ テスト環境用にMicrosoft 365管理者アカウントを保護します。
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918884"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="04be5-103">エンタープライズ テスト環境用に、Microsoft 365管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="04be5-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="04be5-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="04be5-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="04be5-105">管理者アカウントを可能な限り安全に管理することで、組織に対するデジタル攻撃を防止できます。</span><span class="sxs-lookup"><span data-stu-id="04be5-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="04be5-106">この記事では、グローバル管理者アカウントを保護Azure Active Directory (Azure AD) 条件付きアクセス ポリシーを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04be5-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="04be5-107">エンタープライズ テスト環境用にMicrosoft 365管理者アカウントを保護するには、次の 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="04be5-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="04be5-108">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="04be5-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="04be5-109">フェーズ 2: 条件付きアクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="04be5-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="04be5-111">エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="04be5-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="04be5-112">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="04be5-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="04be5-113">最小要件でグローバル管理者アカウント保護を軽量な方法でテストする場合は、「Lightweight base [configuration」の手順に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="04be5-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="04be5-114">シミュレートされたエンタープライズでグローバル管理者アカウント保護をテストする場合は、「パススルー認証」の [手順に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="04be5-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="04be5-115">グローバル管理者アカウント保護のテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) のディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="04be5-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="04be5-116">ここでは、グローバル管理者アカウント保護をテストし、一般的な組織を表す環境でテストを行うオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="04be5-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="04be5-117">フェーズ 2: 条件付きアクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="04be5-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="04be5-118">最初に、専用のグローバル管理者として新しいユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="04be5-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="04be5-119">別のタブで、管理センター Microsoft 365[開きます](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="04be5-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="04be5-120">[ユーザー **の**  >  **アクティブなユーザー]** を選択し、[ユーザー **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="04be5-121">[ユーザーの **追加] ウィンドウ** で、[名]、[表示名]、および [ユーザー名] ボックスに **「DedicatedAdmin」\*\*\*\*と** 入力します。</span><span class="sxs-lookup"><span data-stu-id="04be5-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="04be5-122">[ **パスワード] を** 選択 **し、[パスワードを作成する**] を選択し、強力なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="04be5-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="04be5-123">この新しいアカウントのパスワードを安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="04be5-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="04be5-124">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04be5-124">Select **Next**.</span></span>
6. <span data-ttu-id="04be5-125">[製品ライセンス **の割り当て**] ウィンドウで、[ライセンスの割 **り当て] Microsoft 365 E5** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="04be5-126">[オプションの **設定] ウィンドウで**、[役割管理センター **アクセス**  >  **グローバル** 管理者  >  **次へ] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="04be5-127">[ほぼ **完了] ウィンドウで、[** 追加の完了] を選択し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="04be5-128">次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="04be5-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="04be5-129">[管理 **センター Microsoft 365] タブで**、左側のナビゲーション **で**[グループ] を選択し、[グループ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="04be5-130">[グループ **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="04be5-131">[グループの **種類の選択] ウィンドウで** 、[セキュリティ] **を選択** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="04be5-132">[基本 **の設定] ウィンドウで、[グループの作成** ] を選択 **し**、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="04be5-133">[グループの **確認と追加の完了] ウィンドウで\*\*\*\*、「GlobalAdmins」と入力** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="04be5-134">グループの一覧で **、GlobalAdmins グループを選択** します。</span><span class="sxs-lookup"><span data-stu-id="04be5-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="04be5-135">**[GlobalAdmins]** ウィンドウで [**メンバー]** を選択し、[すべて表示] を選択 **してメンバーを管理します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="04be5-136">**[GlobalAdmins]** ウィンドウで、[メンバーの追加] を選択し **、DedicatedAdmin** アカウントとグローバル管理者アカウントを選択し、[閉じる保存]  >  **を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="04be5-137">次に、グローバル管理者アカウントに多要素認証を必要とする条件付きアクセス ポリシーを作成し、サインイン リスクが中程度または高い場合は認証を拒否します。</span><span class="sxs-lookup"><span data-stu-id="04be5-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="04be5-138">この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04be5-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="04be5-139">ブラウザーの新しいタブで、 に移動します [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="04be5-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="04be5-140">[セキュリティ **Azure Active Directory**  >  **アクセス]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="04be5-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="04be5-141">[条件付き **アクセス - ポリシー] ウィンドウで、[** 基準計画ポリシー: 管理者に MFA を **要求する (プレビュー) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="04be5-142">[基準計画 **ポリシー] ウィンドウで** 、[ポリシーを **すぐに使用する] を選択>保存します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="04be5-143">この 2 つ目のポリシーは、サインイン リスクが中程度または高の場合に、グローバル管理者アカウント認証へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="04be5-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="04be5-144">[条件付き **アクセス - ポリシー] ウィンドウで、[** 新しいポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="04be5-145">[新しい **] ウィンドウで**、[名前]**に「グローバル管理者」と\*\*\*\*入力します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="04be5-146">[割り **当て] セクションで** 、[ユーザーと **グループ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="04be5-147">[ユーザーと **グループ] ウィンドウ** の [含める]**タブ** で、[ユーザーとグループの選択] [ユーザーと **グループ**  >  **の選択] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="04be5-148">[選択 **] ウィンドウで\*\*\*\*[GlobalAdmins] グループを選択** し、[完了] を **選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="04be5-149">[割り **当て] セクションで** 、[条件] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="04be5-150">[条件 **] ウィンドウで**、[サインイン **リスク]** を選択し、[構成]で **[** はい] を選択し、[高] と [中] を選択し、[選択] と [完了]**を選択\*\*\*\*します**。 </span><span class="sxs-lookup"><span data-stu-id="04be5-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="04be5-151">[新しい **] ウィンドウの** [アクセス制御] セクション **で、[** 許可] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="04be5-152">[アクセス許可 **] ウィンドウで** 、[アクセス **をブロック** する] を選択し、[選択] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="04be5-153">[新しい **] ウィンドウで**、[ポリシーの有効化 **] で [オン\*\*\*\*] を** 選択し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04be5-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="04be5-154">Azure portal **を閉じて** Microsoft 365 **管理センター タブを開** きます。</span><span class="sxs-lookup"><span data-stu-id="04be5-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="04be5-155">最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="04be5-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="04be5-156">MFA の構成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04be5-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="04be5-157">これは、最初のポリシーが適用されているのを示しています。</span><span class="sxs-lookup"><span data-stu-id="04be5-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="04be5-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="04be5-158">Next step</span></span>

<span data-ttu-id="04be5-159">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="04be5-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="04be5-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="04be5-160">See also</span></span>

[<span data-ttu-id="04be5-161">ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="04be5-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="04be5-162">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="04be5-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="04be5-163">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="04be5-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="04be5-164">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="04be5-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)