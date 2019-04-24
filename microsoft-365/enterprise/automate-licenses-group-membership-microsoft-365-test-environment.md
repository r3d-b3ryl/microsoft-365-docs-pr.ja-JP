---
title: Microsoft 365 Enterprise テスト環境のライセンスとグループメンバーシップを自動化する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 Enterprise テスト環境で、グループベースのライセンスと動的なグループメンバーシップを構成します。
ms.openlocfilehash: 8ced249ee56e15c057001af60d790a8a4315dd17
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277245"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cc324-103">Microsoft 365 Enterprise テスト環境のライセンスとグループメンバーシップを自動化する</span><span class="sxs-lookup"><span data-stu-id="cc324-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cc324-104">グループベースのライセンスは、グループメンバーシップに基づいてユーザーアカウントのライセンスを自動的に割り当てるか削除します。</span><span class="sxs-lookup"><span data-stu-id="cc324-104">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="cc324-105">動的グループメンバーシップは、ユーザーアカウントのプロパティ (部署、国など) に基づいてグループにメンバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="cc324-105">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="cc324-106">この記事では、Microsoft 365 エンタープライズテスト環境の両方のデモを行います。</span><span class="sxs-lookup"><span data-stu-id="cc324-106">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="cc324-107">Microsoft 365 Enterprise テスト環境で自動ライセンスと動的グループメンバーシップをセットアップするには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="cc324-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="cc324-108">Microsoft 365 Enterprise テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="cc324-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="cc324-109">動的なグループメンバーシップおよび自動ライセンスを構成してテストします。</span><span class="sxs-lookup"><span data-stu-id="cc324-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cc324-111">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc324-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cc324-112">フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="cc324-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cc324-113">最小要件での軽量な方法で自動化されたライセンスとグループメンバーシップをテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="cc324-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cc324-114">シミュレートされたエンタープライズで自動ライセンスおよびグループメンバーシップをテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc324-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc324-115">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc324-115">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="cc324-116">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="cc324-116">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="cc324-117">フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする</span><span class="sxs-lookup"><span data-stu-id="cc324-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="cc324-118">最初に、新しい sales グループを作成し、そのグループメンバーシップのルールを追加して、Department を sales に設定したユーザーアカウントが自動的に sales グループに追加されるようにします。</span><span class="sxs-lookup"><span data-stu-id="cc324-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="cc324-119">インターネットブラウザーのプライベートインスタンスを使用して、office 365 E5 試用版サブスクリプション[https://office.com](https://office.com)のグローバル管理者アカウントを使用して office ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="cc324-119">Using a private instance of your Internet browser, sign in to the Office portal at [https://office.com](https://office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="cc324-120">ブラウザーの別のタブで、Azure portal に移動[https://portal.azure.com](https://portal.azure.com)します。</span><span class="sxs-lookup"><span data-stu-id="cc324-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="cc324-121">Azure portal で **[Azure Active Directory] > [ユーザーとグループ] > [すべてのグループ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="cc324-122">[**すべてのグループ**] ブレードで、[**新しいグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="cc324-123">[**グループの種類**] で、[ **Office 365**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc324-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="cc324-124">[**グループ名**] に「 **Sales**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cc324-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="cc324-125">[**メンバーシップの種類**] で、[**動的ユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc324-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="cc324-126">**[動的クエリの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="cc324-127">**[ユーザーを追加する場所]** で、**[部署]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc324-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="cc324-128">次のフィールドで、**[等しい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc324-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="cc324-129">次のフィールドで、「 **Sales**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cc324-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="cc324-130">**[クエリの追加]** をクリックしてから、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="cc324-131">[グループと**グループ-すべて**のグループ **]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cc324-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="cc324-132">次に、メンバーに Office 365 E5 および Enterprise Mobility + Security E5 ライセンスが自動的に割り当てられるように、Sales グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="cc324-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="cc324-133">Azure Active Directory の**概要**ブレードで、[ **Licenses > All products**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="cc324-134">一覧で、 **[Enterprise Mobility + Security E5]** と **[Office 365 Enterprise E5]** を選択し、 **[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="cc324-135">[**ライセンスの割り当て**] ブレードで、[**ユーザーとグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="cc324-136">グループの一覧で、[ **Sales** ] グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc324-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="cc324-137">**[選択]** をクリックし、 **[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="cc324-138">ブラウザーの [Azure Portal] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cc324-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="cc324-139">次に、ユーザー4アカウントの動的グループメンバーシップと自動ライセンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="cc324-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="cc324-140">ブラウザーの [ **Microsoft Office Home** ] タブで、[**管理者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="cc324-141">[ **Microsoft 365 管理センター** ] タブで、[**アクティブなユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-141">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="cc324-142">[**アクティブなユーザー** ] ページで、[ **User 4** ] アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="cc324-143">[ **User 4** ] ウィンドウで、[**製品ライセンス**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="cc324-144">[**製品ライセンス**] ウィンドウで、 **enterprise Mobility + Security e5**および**Office 365 Enterprise e5**ライセンスをオフにして、[ **Save > Close**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="cc324-145">User 4 アカウントの [プロパティ] で、製品ライセンスが割り当てられておらず、グループメンバーシップもないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc324-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="cc324-146">[**連絡先情報**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="cc324-147">[**連絡先情報の編集**] ウィンドウで、[**連絡先情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="cc324-148">[**部署**] フィールドに「 **Sales**」と入力し、[ **Save > Close**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="cc324-149">数分待ってから、ユーザー4のアカウントウィンドウの右上にある [更新] アイコンを定期的にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc324-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="cc324-150">時間内に、次のように表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="cc324-150">In time you should see the:</span></span>

- <span data-ttu-id="cc324-151">**グループメンバーシップ**プロパティが**Sales** group で更新されました。</span><span class="sxs-lookup"><span data-stu-id="cc324-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="cc324-152">**enterprise Mobility + Security e5**および**Office 365 enterprise e5**ライセンスで更新された**製品ライセンス**のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cc324-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="cc324-153">動的グループメンバーシップと自動ライセンスを運用環境に展開するための情報とリンクについては、id フェーズの以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc324-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="cc324-154">自動ライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="cc324-154">Set up automatic licensing</span></span>](identity-self-service-group-management.md#identity-group-license)
- [<span data-ttu-id="cc324-155">動的グループ メンバーシップをセットアップする</span><span class="sxs-lookup"><span data-stu-id="cc324-155">Set up dynamic group membership</span></span>](identity-self-service-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="cc324-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="cc324-156">Next step</span></span>

<span data-ttu-id="cc324-157">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="cc324-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc324-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc324-158">See also</span></span>

[<span data-ttu-id="cc324-159">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="cc324-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="cc324-160">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="cc324-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cc324-161">Microsoft 365 Enterprise 展開</span><span class="sxs-lookup"><span data-stu-id="cc324-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cc324-162">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="cc324-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
