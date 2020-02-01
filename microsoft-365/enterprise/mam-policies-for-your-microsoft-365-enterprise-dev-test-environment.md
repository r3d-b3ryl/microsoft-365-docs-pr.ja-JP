---
title: Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー
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
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Intune デバイスコンプライアンスポリシーを Microsoft 365 Enterprise テスト環境に追加します。
ms.openlocfilehash: f5d258dd9b4e0ff8799534cce64818a7fdaf663e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600904"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="dc284-103">Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="dc284-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="dc284-104">*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="dc284-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="dc284-105">この記事の手順に従って、Windows 10 デバイスおよび Office 365 ProPlus の Intune デバイスコンプライアンスポリシーを Microsoft 365 エンタープライズテスト環境に追加します。</span><span class="sxs-lookup"><span data-stu-id="dc284-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Office 365 ProPlus to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="dc284-107">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dc284-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="dc284-108">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="dc284-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="dc284-109">最低限の要件を使用して、柔軟な方法で MAM ポリシーを構成する場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="dc284-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="dc284-110">シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dc284-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc284-111">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc284-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="dc284-112">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="dc284-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="dc284-113">フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="dc284-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="dc284-114">このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc284-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="dc284-115">Office 365 ポータル ([https://portal.office.com](https://portal.office.com)) に移動し、全体管理者アカウントを使用して office 365 テストラボサブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc284-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="dc284-116">ブラウザーの新しいタブで、Azure portal を開き[https://portal.azure.com](https://portal.azure.com)ます。</span><span class="sxs-lookup"><span data-stu-id="dc284-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="dc284-117">ブラウザーの [Azure ポータル] タブで、検索ボックスに「 **intune** 」と入力し、[ **intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="dc284-118">[デバイス管理] が [**現在有効になってい**ません] というメッセージが [ **Microsoft Intune** ] ウィンドウに表示される場合は、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="dc284-119">[**モバイルデバイス管理機関**] ウィンドウで、[ **Intune MDM authority**] をクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="dc284-120">ブラウザーのタブを更新します。</span><span class="sxs-lookup"><span data-stu-id="dc284-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="dc284-121">左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="dc284-122">[**グループ-すべてのグループ**] ウィンドウで、[ **+ 新しいグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="dc284-123">**グループ**ウィンドウで、[ **Office 365**または [**グループの種類]** の**セキュリティ**] を選択し、[管理された**Windows 10 デバイスのユーザー** **名**] を入力し、[**メンバーシップの種類**] で [**割り当て済み**] を選択して、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="dc284-124">[ **Microsoft Intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="dc284-125">[ **Microsoft Intune** ] ウィンドウの [**クイックタスク**] リストで、[**コンプライアンスポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="dc284-126">[**コンプライアンスポリシープロファイル**] ウィンドウで、[**ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="dc284-127">[**ポリシーの作成**] ウィンドウの [**名前**] で、「 **Windows 10**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="dc284-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="dc284-128">[**プラットフォーム**] で、[ **windows 10 以降**] を選択し、[ **windows 10 コンプライアンスポリシー** ] ウィンドウで [ **OK]** をクリックして、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="dc284-129">[**コンプライアンスポリシープロファイル**] をクリックし、[ **Windows 10** ] ポリシー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="dc284-130">**Windows 10**ウィンドウで、[**割り当て**] をクリックし、[**含めるグループの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="dc284-131">[**含めるグループの選択**] ウィンドウで、[管理された**Windows 10 デバイスユーザー** ] グループをクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="dc284-132">[**保存**] をクリックし、[ **Microsoft Intune-概要**] をクリックして、左側のナビゲーションで [**クライアントアプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="dc284-133">[**クライアントアプリ**] ウィンドウで、[**アプリ**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="dc284-134">[**アプリの追加**] ウィンドウで、[**アプリの種類**] を選択し、[ **Office 365 スイート**] の下の [ **Windows 10** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc284-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="dc284-135">[**アプリの追加**] ウィンドウで、[**アプリスイートの情報**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc284-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="dc284-136">**アプリスイートの情報**ウィンドウで、「 **Office 365 ProPlus** In **suite Name** and **suite Description**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="dc284-136">In the **App Suite Information** pane, type **Office 365 ProPlus** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="dc284-137">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-137">Click OK.</span></span>

19. <span data-ttu-id="dc284-138">[**アプリの追加**] ウィンドウで、[**アプリスイートの構成**] を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="dc284-139">[**アプリの追加**] ウィンドウで、[**アプリスイートの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc284-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="dc284-140">[**チャネルの更新**] で、[**半期**] を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-140">For **Update Channel**, select **Semi-Annual**, and then click **OK**.</span></span>

22. <span data-ttu-id="dc284-141">[**アプリの追加**] ウィンドウで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc284-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="dc284-142">これで、選択したアプリを**windows 10**デバイスコンプライアンスポリシーと、管理された**windows 10 デバイスユーザー**グループのメンバーに対してテストするためのデバイスコンプライアンスポリシーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="dc284-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="dc284-143">グループの種類として Office 365 を選択すると、追加のリソースが作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc284-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="dc284-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="dc284-144">Next step</span></span>

<span data-ttu-id="dc284-145">テスト環境での[モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc284-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc284-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc284-146">See also</span></span>

<span data-ttu-id="dc284-147">[Microsoft 365 Enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="dc284-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="dc284-148">Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="dc284-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="dc284-149">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="dc284-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="dc284-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="dc284-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
