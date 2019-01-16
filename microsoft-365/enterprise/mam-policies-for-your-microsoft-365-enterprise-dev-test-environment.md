---
title: Microsoft 365 企業のコンプライアンス ポリシーをデバイスのテスト環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Intune デバイス コンプライアンス ・ ポリシー、Microsoft 365 企業環境のテストを追加するのには、このテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869628"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="dcf5d-103">Microsoft 365 企業のコンプライアンス ポリシーをデバイスのテスト環境</span><span class="sxs-lookup"><span data-stu-id="dcf5d-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="dcf5d-104">この資料の手順についてで Microsoft 365 エンタープライズ テスト環境に Intune デバイスのコンプライアンス ・ ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="dcf5d-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="dcf5d-107">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="dcf5d-108">最小要件で軽量な方法で MAM のポリシーを構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="dcf5d-109">シミュレートされた企業で MAM のポリシーを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dcf5d-p101">ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="dcf5d-112">フェーズ 2: 10 の Windows のデバイスのデバイスのコンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="dcf5d-113">このフェーズでは、10 の Windows のデバイスのデバイスのコンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="dcf5d-114">Office のポータルに移動 ([https://office.com](https://office.com)) し、グローバル管理者アカウントを使用して、Office 365 の試用版サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="dcf5d-115">、お使いのブラウザーの新しいタブで開くには、Azure ポータル[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="dcf5d-116">ブラウザーのナビゲーション ウィンドウで [Azure ポータル] タブで**すべてのサービス**] をクリックし、入力**Intune**、 **Intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="dcf5d-p102">**Microsoft Intune**ブレードで**まだデバイスの管理を有効にしていない**メッセージが表示されたらをクリックします。**モバイル デバイスの管理機関**のブレードでは、 **Intune MDM 機関**をクリックし、し、[**選択**] をクリックします。[ブラウザー] タブを更新します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="dcf5d-120">左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="dcf5d-121">**グループのグループのすべての**ブレードでは、[ **+ 新しいグループ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="dcf5d-122">**グループ**・ ブレードの上の**Office 365**を選択**グループの種類ですか?** **Windows 10 の管理デバイスのユーザー** **名**、**メンバーシップの種類**、**割り当て**を選択して入力し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="dcf5d-123">**[グループ]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="dcf5d-124">**グループのグループのすべての**ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="dcf5d-125">**クイック タスク**の一覧で、 **Microsoft Intune**ブレードでは、**コンプライアンス ・ ポリシーを作成する**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="dcf5d-126">**[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="dcf5d-p103">**ポリシーの作成**・ ブレードの**名前**、 **Windows 10**を入力します。**プラットフォーム**では、 **10 とそれ以降の Windows**を選択、 **Windows 10 コンプライアンス ・ ポリシー** ・ ブレードの上の [ **OK** ] をクリックでし、[**作成**] をクリックします。**Windows 10**ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="dcf5d-130">**コンプライアンス ・ ポリシーのプロファイル**のブレードでは、 **10 の Windows**ポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="dcf5d-131">**Windows 10**ブレードは、**割り当て**をクリックし、**含めるグループを選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="dcf5d-132">**含めるグループを選択して**ブレードの**Windows 10 の管理デバイスのユーザー**グループをクリックし、**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="dcf5d-133">**保存**] をクリックして、 **Windows の 10 の割り当て**のブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="dcf5d-134">**[コンプライアンス ポリシー プロファイル]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="dcf5d-135">**Microsoft Intune**ブレードの左側のナビゲーションで [**クライアント アプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="dcf5d-136">**クライアント アプリケーション**のブレードでは、**アプリケーション**をクリックし、し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="dcf5d-137">**追加アプリケーション**のブレードでは、**アプリケーションの種類**を選択し、 **Office 365 製品ファミリ**では、 **Windows の 10**を選択し、します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="dcf5d-138">**アプリケーション スイートを構成する**をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="dcf5d-139">**アプリケーション スイートの情報**をクリックして**Office アプリケーションの Windows 10** [**スイート名**]**スイートの説明**では、 **Office アプリケーションの Windows 10**と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="dcf5d-140">**アプリケーション スイートの設定**] をクリックし、**更新チャネル**では、**半年**を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="dcf5d-141">**追加のアプリケーション**のブレードでは、[**追加**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="dcf5d-142">デバイス ・ コンプライアンス ・ ポリシーと**Windows 10**デバイスのコンプライアンス ・ ポリシーで選択したアプリケーションをテストするため、 **Windows 10 の管理デバイスのユーザー**グループのメンバーがあるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="dcf5d-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="dcf5d-143">Next step</span></span>

<span data-ttu-id="dcf5d-144">[モバイル デバイスの管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能が追加し、テスト環境での機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcf5d-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcf5d-145">See also</span></span>

<span data-ttu-id="dcf5d-146">[Microsoft 365 エンタープライズのテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)です。</span><span class="sxs-lookup"><span data-stu-id="dcf5d-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="dcf5d-147">Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="dcf5d-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="dcf5d-148">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="dcf5d-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="dcf5d-149">エンタープライズ モビリティとセキュリティ (EMS)</span><span class="sxs-lookup"><span data-stu-id="dcf5d-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
