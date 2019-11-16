---
title: Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Intune デバイスコンプライアンスポリシーを Microsoft 365 Enterprise テスト環境に追加します。
ms.openlocfilehash: 6f37a898461ea67bc2927fcbac1a0f1b15adb036
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672563"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="5899e-103">Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="5899e-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="5899e-104">*このテストラボガイドは、Microsoft 365 エンタープライズテスト環境でのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="5899e-104">*This Test Lab Guide can be only used with a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="5899e-105">この記事の手順に従って、Intune デバイスコンプライアンスポリシーを Microsoft 365 Enterprise テスト環境に追加します。</span><span class="sxs-lookup"><span data-stu-id="5899e-105">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5899e-107">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5899e-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="5899e-108">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="5899e-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="5899e-109">最低限の要件を使用して、柔軟な方法で MAM ポリシーを構成する場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="5899e-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5899e-110">シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5899e-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5899e-111">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5899e-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5899e-112">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="5899e-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="5899e-113">フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5899e-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="5899e-114">このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5899e-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="5899e-115">Office 365 ポータル ([https://portal.office.com](https://portal.office.com)) に移動し、全体管理者アカウントを使用して office 365 テストラボサブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5899e-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="5899e-116">ブラウザーの新しいタブで、Azure portal を開き[https://portal.azure.com](https://portal.azure.com)ます。</span><span class="sxs-lookup"><span data-stu-id="5899e-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="5899e-117">ブラウザーの [Azure portal] タブで、ナビゲーションウィンドウの [すべての**サービス**] をクリックし、「 **intune**」と入力して、[ **intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-117">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="5899e-118">**Microsoft Intune**ブレードで [**デバイス管理**] が有効になっていないことが表示された場合は、そのメッセージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-118">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="5899e-119">[**モバイルデバイス管理機関**] ブレードで、[ **Intune MDM 機関**] をクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-119">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="5899e-120">ブラウザーのタブを更新します。</span><span class="sxs-lookup"><span data-stu-id="5899e-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="5899e-121">左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="5899e-122">[**グループ-すべてのグループ**] ブレードで、[ **+ 新しいグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-122">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="5899e-123">**グループ**ブレードで、[ **Office 365** ] または [グループの種類に対して**セキュリティ**を**設定しますか?**] で、[管理された**Windows 10 デバイスのユーザー** **名**] を入力し、[**メンバーシップの種類**] で [**割り当て済み**] を選択し、[**作成**] をクリック</span><span class="sxs-lookup"><span data-stu-id="5899e-123">On the **Group** blade, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="5899e-124">**[グループ]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5899e-124">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="5899e-125">[ **Groups-すべてのグループ**] ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5899e-125">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="5899e-126">**Microsoft Intune**ブレードの [**クイックタスク**] リストで、[**コンプライアンスポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-126">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="5899e-127">**[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-127">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="5899e-128">[**ポリシーの作成**] ブレードの [**名前**] で、「 **Windows 10**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5899e-128">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="5899e-129">[**プラットフォーム**] で、[ **windows 10 以降**] を選択し、 **windows 10 コンプライアンスポリシー**ブレードで [ **OK** ] をクリックして、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-129">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="5899e-130">**Windows 10**ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5899e-130">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="5899e-131">[**コンプライアンスポリシープロファイル**] ブレードで、 **Windows 10**のポリシー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-131">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="5899e-132">**Windows 10**ブレードで、[**割り当て**] をクリックし、[**含めるグループの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-132">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="5899e-133">[ブレード**を含めるグループの選択**] で、[管理された**Windows 10 デバイスユーザー** ] グループをクリックし、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-133">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="5899e-134">[**保存**] をクリックし、[ **Windows 10 割り当て**] ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5899e-134">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="5899e-135">**[コンプライアンス ポリシー プロファイル]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5899e-135">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="5899e-136">**Microsoft Intune**ブレードで、左側のナビゲーションの [**クライアントアプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-136">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="5899e-137">**クライアントアプリ**ブレードで、[**アプリ**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-137">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="5899e-138">[**アプリの追加**] ブレードで、[**アプリの種類**] を選択し、[ **Office 365 スイート**] の下の [ **Windows 10** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5899e-138">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="5899e-139">[**アプリスイートの構成**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-139">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="5899e-140">[**アプリスイートの情報**] をクリックし、[**スイート名**] に「 **windows 10 用 Office**アプリ」、「 **Suite Description**の**windows 10 用 Office アプリ**」と入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-140">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="5899e-141">[**アプリスイートの設定**] をクリックし、 **[更新チャネル**の**半期**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-141">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="5899e-142">[**アプリの追加**] ブレードで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5899e-142">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="5899e-143">これで、選択したアプリを**windows 10**デバイスコンプライアンスポリシーと、管理された**windows 10 デバイスユーザー**グループのメンバーに対してテストするためのデバイスコンプライアンスポリシーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="5899e-143">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="5899e-144">グループの種類として Office 365 を選択すると、追加のリソースが作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5899e-144">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="5899e-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="5899e-145">Next step</span></span>

<span data-ttu-id="5899e-146">テスト環境での[モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5899e-146">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5899e-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="5899e-147">See also</span></span>

<span data-ttu-id="5899e-148">[Microsoft 365 Enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="5899e-148">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="5899e-149">Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="5899e-149">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="5899e-150">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="5899e-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5899e-151">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="5899e-151">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
