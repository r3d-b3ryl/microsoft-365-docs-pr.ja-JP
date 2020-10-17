---
title: Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー
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
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境に Intune デバイスコンプライアンスポリシーを追加します。
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487414"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c2d79-103">Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="c2d79-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c2d79-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="c2d79-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c2d79-105">この記事では、Windows 10 365 デバイスの Intune デバイスコンプライアンスポリシーを Microsoft 365 for enterprise テスト環境に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="c2d79-106">Intune デバイスコンプライアンスポリシーを追加するには、次の2つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2d79-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="c2d79-107">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="c2d79-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="c2d79-108">フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c2d79-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c2d79-110">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2d79-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c2d79-111">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="c2d79-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c2d79-112">最小要件での軽量な方法で MAM ポリシーを構成する場合は、「 [簡易基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="c2d79-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c2d79-113">シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c2d79-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2d79-114">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2d79-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c2d79-115">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="c2d79-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="c2d79-116">フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c2d79-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="c2d79-117">このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="c2d79-118">[Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、グローバル管理者アカウントを使用して microsoft 365 テストラボサブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c2d79-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="c2d79-119">ブラウザーの新しいタブで、Azure portal を開き [https://portal.azure.com](https://portal.azure.com) ます。</span><span class="sxs-lookup"><span data-stu-id="c2d79-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="c2d79-120">Azure portal の検索ボックスに「 **intune**」と入力し、[ **intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="c2d79-121">[ **Microsoft Intune** ] ウィンドウに [**デバイス管理] がまだ有効になってい**ない場合は、そのメッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="c2d79-122">[ **モバイルデバイス管理機関** ] ウィンドウで、[ **Intune MDM authority**] を選択し、[ **選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="c2d79-123">ブラウザーのタブを更新します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="c2d79-124">左側のナビゲーションウィンドウで、[ **グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="c2d79-125">[ **グループ-すべてのグループ** ] ウィンドウで、[ **+ 新しいグループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="c2d79-126">**グループ**ウィンドウで、[ **Microsoft 365** ] または [**グループの種類**に対する**セキュリティ**] を選択し、[管理さ**れた** **Windows 10 デバイスのユーザー** **名**] を入力し、[**メンバーシップの種類**] で [割り当て済み] を選択して、[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="c2d79-127">[ **Microsoft Intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="c2d79-128">[ **Microsoft Intune** ] ウィンドウの [ **クイックタスク** ] リストで、[ **コンプライアンスポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="c2d79-129">[ **コンプライアンスポリシープロファイル** ] ウィンドウで、[ **ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="c2d79-130">[ **ポリシーの作成** ] ウィンドウの [ **名前**] で、 **Windows 10**と入力します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="c2d79-131">[**プラットフォーム**] で、[ **windows 10 以降**] を選択し、[ **windows 10 コンプライアンスポリシー** ] ウィンドウで [ **OK]** を選択して、[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="c2d79-132">[ **コンプライアンスポリシープロファイル**] を選択し、 **Windows 10** ポリシー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="c2d79-133">[ **Windows 10** ] ウィンドウで、[ **割り当て**] を選択し、[ **含めるグループの選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="c2d79-134">[ **含めるグループの選択** ] ウィンドウで、[管理された **Windows 10 デバイスユーザー** ] グループを選択し、[ **選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="c2d79-135">[ **保存**] を選択し、[ **Microsoft Intune-概要**] を選択してから、左側のナビゲーションで [ **クライアントアプリ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="c2d79-136">[ **クライアントアプリ** ] ウィンドウで、[ **アプリ**] を選択し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="c2d79-137">[**アプリの追加**] ウィンドウで、[**アプリの種類**] を選択し、 **Microsoft 365 スイート**の下の [ **Windows 10** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="c2d79-138">[ **アプリの追加** ] ウィンドウで、[ **アプリスイートの情報**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="c2d79-139">[**アプリスイートの情報**] ウィンドウで、 **Suite 名**と**スイートの説明**の両方に「**エンタープライズ向けの Microsoft 365 Apps** 」と入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="c2d79-140">[ **アプリの追加** ] ウィンドウで、[ **アプリスイートの構成**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="c2d79-141">[ **アプリの追加** ] ウィンドウで、[ **アプリスイートの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="c2d79-142">[ **チャネルの更新**] で、[ **半期エンタープライズ**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="c2d79-143">[ **アプリの追加** ] ウィンドウで、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="c2d79-144">これで、選択したアプリを **windows 10** デバイスコンプライアンスポリシーと、管理された **windows 10 デバイスユーザー** グループのメンバーに対してテストするためのデバイスコンプライアンスポリシーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="c2d79-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="c2d79-145">**Microsoft 365**をグループの種類として選択すると、追加のリソースが作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c2d79-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c2d79-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c2d79-146">Next step</span></span>

<span data-ttu-id="c2d79-147">テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2d79-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2d79-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2d79-148">See also</span></span>

<span data-ttu-id="c2d79-149">[Microsoft 365 for enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d79-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="c2d79-150">Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="c2d79-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="c2d79-151">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="c2d79-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c2d79-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="c2d79-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
