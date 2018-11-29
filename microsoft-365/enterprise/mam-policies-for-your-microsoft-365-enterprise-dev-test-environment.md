---
title: Microsoft 365 Enterprise テスト環境の MAM のポリシー
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Intune モバイル アプリケーション管理 (MAM) ポリシー Microsoft 365 エンタープライズ環境のテストを追加するのにには、このテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869628"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="708fc-103">Microsoft 365 Enterprise テスト環境の MAM のポリシー</span><span class="sxs-lookup"><span data-stu-id="708fc-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="708fc-104">この資料の手順については、Microsoft 365 エンタープライズ Intune モバイル アプリケーション管理 (MAM) ポリシーのテスト環境を追加します。</span><span class="sxs-lookup"><span data-stu-id="708fc-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="708fc-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="708fc-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="708fc-107">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="708fc-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="708fc-108">最小要件で軽量な方法で MAM のポリシーを構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="708fc-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="708fc-109">シミュレートされた企業で MAM のポリシーを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="708fc-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="708fc-p101">ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="708fc-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="708fc-112">フェーズ 2:iOS デバイスと Android デバイス用の MAM ポリシーを作成し展開する</span><span class="sxs-lookup"><span data-stu-id="708fc-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="708fc-113">このフェーズでは、2 つの異なる MAM ポリシー (1 つは iOS デバイス用、もう 1 つは Android デバイス用) を作成し展開します。</span><span class="sxs-lookup"><span data-stu-id="708fc-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="708fc-114">Office 365 ポータルに移動 ([https://portal.office.com](https://portal.office.com)) し、グローバル管理者アカウントを使用して、Office 365 の試用版サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="708fc-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="708fc-115">、お使いのブラウザーの新しいタブで開くには、Azure ポータル[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="708fc-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="708fc-116">[Azure ポータル] タブで、Internet Explorer のナビゲーション ウィンドウで**すべてのサービス**] をクリックし、入力**Intune**、 **Intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="708fc-p102">**Microsoft Intune**ブレードで**まだデバイスの管理を有効にしていない**メッセージが表示されたらをクリックします。**モバイル デバイスの管理機関**のブレードでは、 **Intune MDM 機関**をクリックし、し、[**選択**] をクリックします。[ブラウザー] タブを更新します。</span><span class="sxs-lookup"><span data-stu-id="708fc-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="708fc-120">左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="708fc-121">**グループのグループのすべての**ブレードでは、[ **+ 新しいグループ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="708fc-122">**グループ**・ ブレードの上の**Office 365**を選択**グループの種類ですか?** **iOS デバイスのユーザーの管理\*\*\*\*名**、**メンバーシップの種類**、**割り当て**を選択して入力し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="708fc-123">**[グループ]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="708fc-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="708fc-124">**グループのグループのすべての**ブレードでは、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="708fc-125">**グループ**・ ブレードの上の**Office 365**を選択**グループの種類ですか?** **Android 管理デバイスのユーザー** **名**、**メンバーシップの種類**、**割り当て**を選択して入力し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="708fc-126">**グループのグループのすべての**ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="708fc-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="708fc-127">**[Intune]** ブレードの **[クイック タスク]** 一覧で、**[コンプライアンス ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="708fc-128">**[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="708fc-p103">**[ポリシーの作成]** ブレードの **[名前]** で、「**iOS**」と入力します。**[プラットフォーム]** で **[iOS]** を選択し、**[iOS コンプライアンス ポリシー]** ブレードで **[OK]** をクリックし、次いで **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="708fc-131">**[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="708fc-p104">**[ポリシーの作成]** ブレードの **[名前]** で、「**Android**」と入力します。**[プラットフォーム]** で **[Android]** を選択し、**[Android コンプライアンス ポリシー]** ブレードで **[OK]** をクリックし、次いで **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="708fc-134">**[コンプライアンス ポリシー プロファイル]** ブレードで、**Android** のポリシー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="708fc-135">**[Android - プロパティ]** ブレードの左側のナビゲーションで、**[割り当て]**、**[グループの選択]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="708fc-136">**[グループの選択]** ブレードで、**[管理された Android デバイス ユーザー]** グループをクリックし、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="708fc-137">**保存**] をクリックして、**アプリの割り当て**のブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="708fc-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="708fc-138">**[コンプライアンス ポリシー プロファイル]** ブレードで、**iOS** のポリシー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="708fc-139">**[iOS - プロパティ]** ブレードの左側のナビゲーションで、**[割り当て]**、**[グループの選択]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="708fc-140">**[グループの選択]** ブレードで、**[管理された iOS デバイス ユーザー]** グループをクリックし、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="708fc-141">**保存**] をクリックし、 **iOS の割り当て**のブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="708fc-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="708fc-142">**[コンプライアンス ポリシー プロファイル]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="708fc-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="708fc-143">**[Intune]** ブレードの左側のナビゲーションで、**[アプリの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="708fc-144">**[モバイル アプリ]** ブレードで、**[アプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="708fc-145">アプリの一覧で、**[PowerPoint]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="708fc-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="708fc-p105">**[PowerPoint の概要]** ブレードで、**[割り当て] > [グループの選択] > [iOS デバイスの管理] > [選択]** の順にクリックします。**[種類]** で、**[利用可能]** を選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="708fc-148">次のアプリケーションには、29 の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="708fc-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="708fc-149">Outlook for Android</span><span class="sxs-lookup"><span data-stu-id="708fc-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="708fc-150">Word for iOS</span><span class="sxs-lookup"><span data-stu-id="708fc-150">Word for iOS</span></span>
    
    - <span data-ttu-id="708fc-151">Excel for iOS</span><span class="sxs-lookup"><span data-stu-id="708fc-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="708fc-152">iOS 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="708fc-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="708fc-153">Microsoft Dynamics CRM on iPad for iOS</span><span class="sxs-lookup"><span data-stu-id="708fc-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="708fc-154">Microsoft Dynamics CRM on iPhone for iOS</span><span class="sxs-lookup"><span data-stu-id="708fc-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="708fc-155">電話用 Dynamics CRM for Android</span><span class="sxs-lookup"><span data-stu-id="708fc-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="708fc-156">タブレット用 Dynamics CRM for Android</span><span class="sxs-lookup"><span data-stu-id="708fc-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="708fc-157">Excel for Android</span><span class="sxs-lookup"><span data-stu-id="708fc-157">Excel for Android</span></span>
    
    - <span data-ttu-id="708fc-158">Word for Android</span><span class="sxs-lookup"><span data-stu-id="708fc-158">Word for Android</span></span>
    
    - <span data-ttu-id="708fc-159">OneNote for iOS</span><span class="sxs-lookup"><span data-stu-id="708fc-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="708fc-160">**[モバイル アプリ - アプリ]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="708fc-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="708fc-161">**[モバイル アプリ]** ブレードで、**[アプリ保護ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="708fc-162">**[アプリ保護ポリシー]** ブレードで、**[ポリシーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="708fc-163">**[ポリシーの追加]** ブレードで、「**iOS**」と入力して、**[必要なアプリの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="708fc-164">**[アプリ]** ブレードで、**[PowerPoint]**、**[Microsoft Dynamics CRM on iPhone]**、**[Excel]**、**[Microsoft Dynamics CRM on iPhone]**、**[Word]**、**[OneNote]**、**[Outlook]** をクリックし、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="708fc-165">**[ポリシーの追加]** ブレードで、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="708fc-166">**[アプリ保護ポリシー]** ブレードで、**[ポリシーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="708fc-167">**[ポリシーの追加]** ブレードで、「**Android**」と入力します。**[プラットフォーム]** で **[Android]** を選択して、**[必要なアプリの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="708fc-168">**[アプリ]** ブレードで、**[PowerPoint]**、**[タブレット用 Dynamics CRM]**、**[Excel]**、**[Word]**、**[Outlook]**、**[電話用 Dynamics CRM]** をクリックし、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="708fc-169">**[ポリシーの追加]** ブレードで、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="708fc-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="708fc-170">これで、2 つの MAM ポリシー (1 つは iOS デバイス用、もう 1 つは Android デバイス用) が設定され、選択されたアプリの設定をテストする用意ができました。</span><span class="sxs-lookup"><span data-stu-id="708fc-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="708fc-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="708fc-171">Next step</span></span>

<span data-ttu-id="708fc-172">[モバイル デバイスの管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能が追加し、テスト環境での機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="708fc-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="708fc-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="708fc-173">See also</span></span>

<span data-ttu-id="708fc-174">[Microsoft 365 エンタープライズのテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)です。</span><span class="sxs-lookup"><span data-stu-id="708fc-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="708fc-175">Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="708fc-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="708fc-176">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="708fc-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="708fc-177">エンタープライズ モビリティとセキュリティ (EMS)</span><span class="sxs-lookup"><span data-stu-id="708fc-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
