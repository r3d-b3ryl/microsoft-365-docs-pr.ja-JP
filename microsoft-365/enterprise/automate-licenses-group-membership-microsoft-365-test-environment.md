---
title: エンタープライズ テスト環境向けライセンスとグループ Microsoft 365を自動化する
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
description: エンタープライズ テスト環境用に、グループ ベースのライセンスと動的Microsoft 365メンバーシップを構成します。
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905370"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b7b9e-103">エンタープライズ テスト環境向けライセンスとグループ Microsoft 365を自動化する</span><span class="sxs-lookup"><span data-stu-id="b7b9e-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b7b9e-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="b7b9e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b7b9e-105">グループ ベースのライセンスでは、グループ メンバーシップに基づいて、ユーザー アカウントのライセンスが自動的に割り当てまたは削除されます。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="b7b9e-106">動的グループ メンバーシップは、部署や国などのユーザー アカウントのプロパティに基づいて、グループにメンバー **を追加または** 削除 **します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="b7b9e-107">この記事では、エンタープライズ テスト環境でグループ メンバーを追加および削除するMicrosoft 365手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="b7b9e-108">エンタープライズ テスト環境用に自動ライセンスと動的グループ メンバーシップをMicrosoft 365には、次の 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="b7b9e-109">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="b7b9e-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="b7b9e-110">フェーズ 2: 動的グループ メンバーシップと自動ライセンスの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="b7b9e-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b7b9e-112">エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b7b9e-113">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="b7b9e-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b7b9e-114">最小限の要件で、自動ライセンスとグループ メンバーシップのみを軽量な方法でテストする場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b7b9e-115">シミュレートされたエンタープライズで自動ライセンスとグループ メンバーシップをテストする場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7b9e-116">ライセンスとグループ の自動メンバーシップをテストするには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b7b9e-117">ここではオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="b7b9e-118">フェーズ 2: 動的グループ メンバーシップと自動ライセンスの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="b7b9e-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="b7b9e-119">まず、Sales という名前の新しいグループを作成し、部署が Sales に設定されているユーザー アカウントが自動的に **Sales** グループに参加する動的グループ メンバーシップ ルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="b7b9e-120">インターネット ブラウザーのプライベート インスタンスで、Microsoft 365 テスト[](https://admin.microsoft.com)ラボ サブスクリプションのグローバル管理者アカウントMicrosoft 365 E5サインインします。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="b7b9e-121">ブラウザーの別のタブで、Azure portal に移動します [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="b7b9e-122">Azure portal で、検索ボックスに **グループ** を入力し、[グループ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="b7b9e-123">[すべてのグループ **] ウィンドウで** 、[新しいグループ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="b7b9e-124">[**グループの種類] で**、[グループ]**をMicrosoft 365** します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="b7b9e-125">[ **グループ名] に**「Sales」 **と入力します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="b7b9e-126">[ **メンバーシップの種類] で**、[動的ユーザー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="b7b9e-127">[動的 **ユーザー メンバー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="b7b9e-128">[動的メンバーシップ **ルール] ウィンドウで、次の操作を** 行います。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="b7b9e-129">部門プロパティ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-129">Select the **department** property.</span></span>
   - <span data-ttu-id="b7b9e-130">[等号 **] 演算子を選択** します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="b7b9e-131">[値] **ボックスに** 「Sales」と **入力します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="b7b9e-132">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-132">Select **Save**.</span></span>
11. <span data-ttu-id="b7b9e-133">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-133">Select **Create**.</span></span>

<span data-ttu-id="b7b9e-134">次に、メンバーにライセンスが自動的に割り当てMicrosoft 365 E5構成します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="b7b9e-135">[販売] **グループを選択** し、[ライセンス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="b7b9e-136">[ライセンスの **割り当ての更新] ウィンドウ** で、[Microsoft 365 E5]**を選択し、[** 保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="b7b9e-137">ブラウザーで、[Azure ポータル] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="b7b9e-138">次に、User 4 アカウントで動的グループ メンバーシップと自動ライセンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="b7b9e-139">ブラウザーの **[Microsoft Office] タブ** で、[管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="b7b9e-140">[管理センター **Microsoft 365] タブで**、[アクティブなユーザー]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="b7b9e-141">[アクティブ な **ユーザー] ページ** で、[ **ユーザー 4] アカウントを選択** します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="b7b9e-142">[ユーザー **4] ウィンドウで** 、[製品ライセンスの **編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="b7b9e-143">[製品ライセンス **] ウィンドウ** で、ライセンスを無効Microsoft 365 E5し、[閉 **じる** 保存]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="b7b9e-144">User 4 アカウントのプロパティで、製品ライセンスが割り当てられていないか、グループ メンバーシップが割り当てられていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="b7b9e-145">[ **連絡先情報] で、[** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="b7b9e-146">[連絡先情報 **の編集] ウィンドウで** 、[連絡先情報] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="b7b9e-147">[部署]**ボックスに\*\*\*\*「Sales」と入力し**、[閉じる保存]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="b7b9e-148">数分待ち、ユーザー 4 アカウントウィンドウの右上にある [更新] アイコンを定期的に選択します。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="b7b9e-149">時間内に、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-149">In time, you should see the:</span></span>

- <span data-ttu-id="b7b9e-150">**Sales グループで** 更新されたグループ メンバーシップ **プロパティ** 。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="b7b9e-151">**製品ライセンス** プロパティは、ライセンスライセンス **でMicrosoft 365 E5** されます。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="b7b9e-152">動的グループ メンバーシップと自動ライセンスを実稼働環境に展開するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="b7b9e-153">グループ ベースのライセンス Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7b9e-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="b7b9e-154">グループ内の動的Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7b9e-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="b7b9e-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="b7b9e-155">Next step</span></span>

<span data-ttu-id="b7b9e-156">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="b7b9e-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7b9e-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7b9e-157">See also</span></span>

[<span data-ttu-id="b7b9e-158">ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="b7b9e-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b7b9e-159">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="b7b9e-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b7b9e-160">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="b7b9e-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b7b9e-161">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="b7b9e-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)