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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685560"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="753c2-103">エンタープライズテスト環境の Microsoft 365 のライセンスとグループメンバーシップを自動化する</span><span class="sxs-lookup"><span data-stu-id="753c2-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="753c2-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="753c2-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="753c2-105">グループベースのライセンスは、グループメンバーシップに基づいてユーザーアカウントのライセンスを自動的に割り当てるか削除します。</span><span class="sxs-lookup"><span data-stu-id="753c2-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="753c2-106">動的グループメンバーシップは、ユーザーアカウントのプロパティ (部署、国など) に基づいてグループにメンバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="753c2-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="753c2-107">この記事では、Microsoft 365 for enterprise テスト環境の両方のデモを行います。</span><span class="sxs-lookup"><span data-stu-id="753c2-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="753c2-108">エンタープライズテスト環境の Microsoft 365 で自動ライセンスと動的グループメンバーシップをセットアップするには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="753c2-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="753c2-109">エンタープライズテスト環境用の Microsoft 365 を作成します。</span><span class="sxs-lookup"><span data-stu-id="753c2-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="753c2-110">動的なグループメンバーシップおよび自動ライセンスを構成してテストします。</span><span class="sxs-lookup"><span data-stu-id="753c2-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="753c2-112">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="753c2-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="753c2-113">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="753c2-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="753c2-114">最小要件での軽量な方法で自動化されたライセンスとグループメンバーシップをテストする場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="753c2-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="753c2-115">シミュレートされたエンタープライズで自動ライセンスおよびグループメンバーシップをテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="753c2-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="753c2-116">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="753c2-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="753c2-117">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="753c2-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="753c2-118">フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="753c2-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="753c2-119">最初に、新しい Sales グループを作成し、そのグループメンバーシップのルールを追加して、Department を Sales に設定したユーザーアカウントが自動的に Sales グループに追加されるようにします。</span><span class="sxs-lookup"><span data-stu-id="753c2-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="753c2-120">インターネットブラウザーのプライベートインスタンスを使用して、microsoft 365 E5 テストラボサブスクリプションのグローバル管理者アカウントを使用して、 [microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="753c2-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="753c2-121">ブラウザーの別のタブで、Azure portal に移動 [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="753c2-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="753c2-122">Azure portal で、[検索] ボックスに「 **groups** 」と入力し、[ **グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="753c2-123">[ **すべてのグループ** ] ウィンドウで、[ **新しいグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="753c2-124">[ **グループの種類**] で、[ **Microsoft 365**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="753c2-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="753c2-125">[ **グループ名**] に「 **Sales**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="753c2-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="753c2-126">[ **メンバーシップの種類**] で、[ **動的ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="753c2-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="753c2-127">[ **動的ユーザーメンバー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="753c2-128">[ **動的メンバーシップの規則** ] ウィンドウで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="753c2-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="753c2-129">**Department**プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="753c2-129">Select the **department** property.</span></span>
   - <span data-ttu-id="753c2-130">**Equals**演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="753c2-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="753c2-131">[ **売上** の **値**を入力します。</span><span class="sxs-lookup"><span data-stu-id="753c2-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="753c2-132">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-132">Click **Save**.</span></span>
11. <span data-ttu-id="753c2-133">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-133">Click **Create**.</span></span>

<span data-ttu-id="753c2-134">次に、メンバーに Microsoft 365 E5 ライセンスが自動的に割り当てられるように、Sales グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="753c2-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="753c2-135">[ **Sales** ] グループをクリックし、[ **ライセンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="753c2-136">[ **ライセンスの割り当ての更新** ] ウィンドウで、[ **Microsoft 365 E5**] を選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="753c2-137">ブラウザーの [Azure Portal] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="753c2-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="753c2-138">次に、ユーザー4アカウントの動的グループメンバーシップと自動ライセンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="753c2-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="753c2-139">ブラウザーの [ **Microsoft Office Home** ] タブで、[ **管理者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="753c2-140">[ **Microsoft 365 管理センター** ] タブで、[ **アクティブなユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="753c2-141">[ **アクティブなユーザー** ] ページで、[ **User 4** ] アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="753c2-142">[ **User 4** ] ウィンドウで、[**製品ライセンス**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="753c2-143">[ **製品ライセンス** ] ウィンドウで、 **Microsoft 365 E5** ライセンスを無効にしてから、[ **保存 > 閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="753c2-144">User 4 アカウントの [プロパティ] で、製品ライセンスが割り当てられておらず、グループメンバーシップもないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="753c2-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="753c2-145">[**連絡先情報**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="753c2-146">[ **連絡先情報の編集** ] ウィンドウで、[ **連絡先情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="753c2-147">[ **部署** ] フィールドに「 **Sales**」と入力し、[ **保存 > 閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="753c2-148">数分待ってから、ユーザー4のアカウントウィンドウの右上にある [更新] アイコンを定期的にクリックします。</span><span class="sxs-lookup"><span data-stu-id="753c2-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="753c2-149">時間内に、次のように表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="753c2-149">In time you should see the:</span></span>

- <span data-ttu-id="753c2-150">**グループメンバーシップ** プロパティが **Sales** group で更新されました。</span><span class="sxs-lookup"><span data-stu-id="753c2-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="753c2-151">**製品ライセンス** プロパティは、 **Microsoft 365 E5** ライセンスで更新されました。</span><span class="sxs-lookup"><span data-stu-id="753c2-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="753c2-152">動的グループメンバーシップと自動ライセンスを運用環境に展開するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="753c2-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="753c2-153">リンクの未定</span><span class="sxs-lookup"><span data-stu-id="753c2-153">LINK TBD</span></span>
- <span data-ttu-id="753c2-154">リンクの未定</span><span class="sxs-lookup"><span data-stu-id="753c2-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="753c2-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="753c2-155">Next step</span></span>

<span data-ttu-id="753c2-156">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="753c2-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="753c2-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="753c2-157">See also</span></span>

[<span data-ttu-id="753c2-158">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="753c2-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="753c2-159">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="753c2-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="753c2-160">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="753c2-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="753c2-161">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="753c2-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
