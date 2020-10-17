---
title: エンタープライズテスト環境の Microsoft 365 のライセンスとグループメンバーシップを自動化する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: エンタープライズテスト環境では、Microsoft 365 のグループベースのライセンスと動的なグループメンバーシップを構成します。
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487578"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8157b-103">エンタープライズテスト環境の Microsoft 365 のライセンスとグループメンバーシップを自動化する</span><span class="sxs-lookup"><span data-stu-id="8157b-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8157b-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="8157b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="8157b-105">グループベースのライセンスは、グループメンバーシップに基づいてユーザーアカウントのライセンスを自動的に割り当てるか削除します。</span><span class="sxs-lookup"><span data-stu-id="8157b-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="8157b-106">動的グループメンバーシップは、ユーザーアカウントのプロパティ ( **部署** 、 **国**など) に基づいてグループにメンバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="8157b-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="8157b-107">この記事では、Microsoft 365 for enterprise テスト環境におけるグループメンバーの追加と削除のデモンストレーションを行います。</span><span class="sxs-lookup"><span data-stu-id="8157b-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="8157b-108">Microsoft 365 for enterprise テスト環境での自動ライセンスと動的グループメンバーシップのセットアップには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="8157b-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="8157b-109">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="8157b-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="8157b-110">フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="8157b-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8157b-112">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8157b-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8157b-113">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="8157b-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8157b-114">最小要件での軽量な方法で、自動ライセンスおよびグループメンバーシップのみをテストする場合は、「 [ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8157b-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8157b-115">シミュレートされたエンタープライズで自動ライセンスおよびグループメンバーシップをテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8157b-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8157b-116">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8157b-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8157b-117">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="8157b-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="8157b-118">フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="8157b-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="8157b-119">最初に、sales という名前の新しいグループを作成し、そのグループメンバーシップのルールを追加して、 **Department** を **sales** に設定したユーザーアカウントが自動的に sales グループに参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8157b-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="8157b-120">インターネットブラウザーのプライベートインスタンスで、microsoft 365 E5 テストラボサブスクリプションの全体管理者アカウントを使用して、 [microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8157b-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="8157b-121">ブラウザーの別のタブで、Azure portal に移動 [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="8157b-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="8157b-122">Azure portal で、[検索] ボックスに「 **groups** 」と入力し、[ **グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="8157b-123">[ **すべてのグループ** ] ウィンドウで、[ **新しいグループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="8157b-124">[ **グループの種類**] で、[ **Microsoft 365**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="8157b-125">[ **グループ名**] に、「 **Sales**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8157b-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="8157b-126">[ **メンバーシップの種類**] で、[ **動的ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="8157b-127">[ **動的ユーザーメンバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="8157b-128">[ **動的メンバーシップの規則** ] ウィンドウで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8157b-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="8157b-129">**Department**プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-129">Select the **department** property.</span></span>
   - <span data-ttu-id="8157b-130">**Equals**演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="8157b-131">[ **値** ] ボックスに「 **Sales**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8157b-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="8157b-132">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-132">Select **Save**.</span></span>
11. <span data-ttu-id="8157b-133">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-133">Select **Create**.</span></span>

<span data-ttu-id="8157b-134">次に、メンバーに Microsoft 365 E5 ライセンスが自動的に割り当てられるように、Sales グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="8157b-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="8157b-135">[ **Sales** ] グループを選択し、[ **ライセンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="8157b-136">[ **ライセンスの割り当ての更新** ] ウィンドウで、[ **Microsoft 365 E5**] を選択し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="8157b-137">ブラウザーで、[Azure portal] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8157b-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="8157b-138">次に、ユーザー4アカウントの動的グループメンバーシップと自動ライセンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="8157b-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="8157b-139">ブラウザーの [ **Microsoft Office Home** ] タブで、[ **管理者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="8157b-140">[ **Microsoft 365 管理センター** ] タブで、[ **アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="8157b-141">[ **アクティブなユーザー** ] ページで、[ **User 4** ] アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="8157b-142">[ **User 4** ] ウィンドウで、[**製品ライセンス**] の [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="8157b-143">[**製品ライセンス**] ウィンドウで、 **Microsoft 365 E5**ライセンスを無効にしてから、[**保存**] [閉じる] を選択し  >  **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="8157b-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="8157b-144">User 4 アカウントの [プロパティ] で、製品ライセンスが割り当てられておらず、グループメンバーシップもないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8157b-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="8157b-145">**連絡先情報**の場合は、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="8157b-146">[ **連絡先情報の編集** ] ウィンドウで、[ **連絡先情報**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="8157b-147">[**部署**] ボックスに「 **Sales**」と入力し、[**保存**して閉じる] を選択し  >  **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="8157b-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="8157b-148">数分待ってから、ユーザー4のアカウントウィンドウの右上にある [ **更新** ] アイコンを定期的に選択します。</span><span class="sxs-lookup"><span data-stu-id="8157b-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="8157b-149">時間には、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="8157b-149">In time, you should see the:</span></span>

- <span data-ttu-id="8157b-150">**グループメンバーシップ** プロパティが **Sales** group で更新されました。</span><span class="sxs-lookup"><span data-stu-id="8157b-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="8157b-151">**製品ライセンス** プロパティは、 **Microsoft 365 E5** ライセンスで更新されました。</span><span class="sxs-lookup"><span data-stu-id="8157b-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="8157b-152">動的グループメンバーシップと自動ライセンスを運用環境に展開するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8157b-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="8157b-153">Azure Active Directory でのグループベースのライセンス</span><span class="sxs-lookup"><span data-stu-id="8157b-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="8157b-154">Azure Active Directory の動的グループ</span><span class="sxs-lookup"><span data-stu-id="8157b-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="8157b-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="8157b-155">Next step</span></span>

<span data-ttu-id="8157b-156">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="8157b-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8157b-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="8157b-157">See also</span></span>

[<span data-ttu-id="8157b-158">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="8157b-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="8157b-159">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="8157b-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8157b-160">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="8157b-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8157b-161">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8157b-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
