---
title: Microsoft 365 エンタープライズ テスト環境のライセンスとグループのメンバーシップを自動化します。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 エンタープライズ テスト環境では、グループ ベースのライセンスと動的グループのメンバーシップを構成します。
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869387"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="21c7d-103">Microsoft 365 エンタープライズ テスト環境のライセンスとグループのメンバーシップを自動化します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="21c7d-p101">グループ ベース ライセンスを自動的に割り当てるか、グループ メンバーシップに基づいてユーザー アカウントのライセンスを削除します。動的グループのメンバーシップを追加または部門や国などのユーザー アカウントのプロパティに基づいて、グループにメンバーを削除します。この資料は、Microsoft 365 エンタープライズ テスト環境の両方のデモンストレーションする手順を示します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="21c7d-107">Microsoft 365 エンタープライズ テスト環境での自動ライセンスおよび動的グループのメンバーシップを設定するのには 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="21c7d-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="21c7d-108">Microsoft 365 エンタープライズ テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="21c7d-109">構成し、動的グループのメンバーシップおよび自動ライセンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="21c7d-111">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="21c7d-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="21c7d-112">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="21c7d-113">最小要件で軽量な方法で自動化されたライセンスとグループのメンバーシップをテストする場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="21c7d-114">シミュレートされた企業で自動化されたライセンスとグループのメンバーシップをテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="21c7d-p102">ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="21c7d-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="21c7d-117">フェーズ 2: を構成して、動的グループのメンバーシップおよびライセンスの自動テスト</span><span class="sxs-lookup"><span data-stu-id="21c7d-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="21c7d-118">最初に、新しいセールス ・ グループを作成し、部門の売り上げ高に設定を持つユーザー アカウントを Sales グループに自動的に追加できるように、動的グループのメンバーシップの規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="21c7d-119">Office 365 ポータルにサインインして、インターネット ブラウザーのプライベート インスタンスを使用すると、 [https://portal.office.com](https://portal.office.com) 、Office 365 の E5 の試用版サブスクリプションのグローバル管理者アカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="21c7d-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="21c7d-120">Azure ポータルには、ブラウザーの別のタブ、[ [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="21c7d-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="21c7d-121">Azure portal で **[Azure Active Directory] > [ユーザーとグループ] > [すべてのグループ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="21c7d-122">**グループのすべて**のブレードでは、**新しいグループ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="21c7d-123">**グループの種類**では、 **Office 365**を選択します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="21c7d-124">**グループ名**、**売り上げ高**を入力します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="21c7d-125">**メンバーシップの種類**] では、**動的なユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="21c7d-126">**[動的クエリの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="21c7d-127">**[ユーザーを追加する場所]** で、**[部署]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="21c7d-128">次のフィールドで、**[等しい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="21c7d-129">次のフィールドでは、**売り上げ高**を入力します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="21c7d-130">**[クエリの追加]** をクリックしてから、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="21c7d-131">**グループ**と**グループのすべてのグループ**のブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="21c7d-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="21c7d-132">次に、Office 365 の E5 とエンタープライズ モビリティとセキュリティ E5 ライセンスのメンバーが自動的に割り当てられるように、セールス ・ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="21c7d-133">Azure Active Directory の**概要**のブレードでをクリックして**ライセンス > すべての製品**。</span><span class="sxs-lookup"><span data-stu-id="21c7d-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="21c7d-134">一覧で、 **[Enterprise Mobility + Security E5]** と **[Office 365 Enterprise E5]** を選択し、 **[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="21c7d-135">**ライセンスの割り当て**のブレードでは、**ユーザーとグループ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="21c7d-136">グループの一覧では、 **Sales**グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="21c7d-137">**[選択]** をクリックし、 **[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="21c7d-138">ブラウザーの [Azure Portal] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="21c7d-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="21c7d-139">次に、動的グループのメンバーシップと 4 のユーザー アカウントの自動ライセンスの取得をテストします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="21c7d-140">**Microsoft Office ホーム**] タブからお使いのブラウザーで、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="21c7d-141">**Office 管理者センター** ] タブで、**アクティブなユーザー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="21c7d-142">[**アクティブ ユーザ**] ページでは、 **4 のユーザー**アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="21c7d-143">**ユーザー 4**ウィンドウで、**製品のライセンス**の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="21c7d-144">**製品ライセンス**] ウィンドウで、[**エンタープライズ モビリティ + E5 のセキュリティ**を有効にするクリックし、 **Office 365 エンタープライズ E5**ライセンス オフ、**を保存 > 閉じる**。</span><span class="sxs-lookup"><span data-stu-id="21c7d-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="21c7d-145">4 のユーザー アカウントのプロパティ] では、製品のライセンスが割り当てられていないと、グループ メンバーシップがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="21c7d-146">**連絡先情報**の**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="21c7d-147">**については連絡先の編集**ウィンドウで、**連絡先情報**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c7d-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="21c7d-148">[**部門**] フィールドで、**販売**を入力し] をクリックし、**を保存 > 閉じる**。</span><span class="sxs-lookup"><span data-stu-id="21c7d-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="21c7d-149">、数分待ってから、定期的に 4 のユーザー アカウント] ウィンドウの右上の更新アイコンをクリックします.</span><span class="sxs-lookup"><span data-stu-id="21c7d-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="21c7d-150">時刻が表示します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-150">In time you should see the:</span></span>

- <span data-ttu-id="21c7d-151">**グループ メンバーシップ**プロパティが、**セールス**・ グループを使用して更新します。</span><span class="sxs-lookup"><span data-stu-id="21c7d-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="21c7d-152">**エンタープライズ モビリティおよびセキュリティ E5**と**Office 365 のエンタープライズ E5**のライセンスを更新する**製品のライセンス**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="21c7d-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="21c7d-153">情報と動的グループのメンバーシップと実稼働環境での自動ライセンス展開へのリンクの識別段階では、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21c7d-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="21c7d-154">自動ライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="21c7d-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="21c7d-155">動的グループ メンバーシップをセットアップする</span><span class="sxs-lookup"><span data-stu-id="21c7d-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="21c7d-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="21c7d-156">Next step</span></span>

<span data-ttu-id="21c7d-157">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="21c7d-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="21c7d-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="21c7d-158">See also</span></span>

[<span data-ttu-id="21c7d-159">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="21c7d-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="21c7d-160">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="21c7d-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="21c7d-161">Microsoft 365 エンタープライズ展開</span><span class="sxs-lookup"><span data-stu-id="21c7d-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="21c7d-162">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="21c7d-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
