---
title: iOS 用 Microsoft Defender ATP のアプリベースの展開
ms.reviewer: ''
description: アプリを使用して iOS 用 Microsoft Defender ATP を展開する方法について説明します。
keywords: microsoft、Defender、atp、ios、アプリ、インストール、展開、アンインストール、Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c94c6839c17b3bbb432cef12fe58723d0cc2ecff
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587241"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="5e49a-104">Microsoft Defender for Endpoint for iOS の展開</span><span class="sxs-lookup"><span data-stu-id="5e49a-104">Deploy Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5e49a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5e49a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5e49a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5e49a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5e49a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e49a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5e49a-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5e49a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5e49a-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="5e49a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="5e49a-110">このトピックでは、Intune ポータル サイト登録デバイスでの IOS 用 Defender for Endpoint の展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="5e49a-111">Intune デバイスの登録の詳細については、「Intune に [iOS/iPadOS デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)。</span><span class="sxs-lookup"><span data-stu-id="5e49a-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5e49a-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="5e49a-112">Before you begin</span></span>

- <span data-ttu-id="5e49a-113">Microsoft Endpoint Manager 管理センター [へのアクセス権を持っている必要があります](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="5e49a-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="5e49a-114">ユーザーに対して iOS 登録が行われたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="5e49a-115">IOS 用 Defender for Endpoint を使用するには、Defender for Endpoint ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e49a-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="5e49a-116">ライセンスの割 [り当て方法については、「ユーザー](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) にライセンスを割り当てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e49a-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="5e49a-117">iOS 用 Microsoft Defender ATP (Microsoft Defender for Endpoint) が Apple App [Store で利用可能になります](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="5e49a-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="5e49a-118">展開手順</span><span class="sxs-lookup"><span data-stu-id="5e49a-118">Deployment steps</span></span>

<span data-ttu-id="5e49a-119">Intune ポータル サイトを介して iOS 用 Defender for Endpoint を展開します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="5e49a-120">iOS ストア アプリの追加</span><span class="sxs-lookup"><span data-stu-id="5e49a-120">Add iOS store app</span></span>

1. <span data-ttu-id="5e49a-121">[Microsoft Endpoint manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)  ->  **アプリ] iOS/iPadOS [iOS** ストア アプリの追加] に移動し、[  ->    ->  選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-122">![Microsoft Endpoint Manager Admin Center1 のイメージ](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="5e49a-123">[アプリの追加] ページで、[アプリ ストアの検索] をクリック **し** 、検索バーに **「Microsoft Defender Endpoint」** と入力します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="5e49a-124">[検索結果] セクションで *、[Microsoft Defender Endpoint]* をクリックし、[選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="5e49a-125">[ **最小オペレーティング システム] として [iOS 11.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="5e49a-126">アプリに関する残りの情報を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="5e49a-127">[割り *当て] セクションで* 、[必須] **セクションに** 移動し、[グループの追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="5e49a-128">その後、IOS アプリの Defender for Endpoint をターゲットとするユーザー グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="5e49a-129">[選択 **] をクリック** し、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e49a-130">選択したユーザー グループは、Intune に登録されたユーザーで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e49a-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-131">![Microsoft Endpoint Manager Admin Center2 のイメージ](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="5e49a-132">[確認 *と作成] セクション* で、入力された情報が正しいか確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="5e49a-133">しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="5e49a-134">表示されるアプリ情報ページの [モニター]セクションで、[デバイスのインストール状態] を選択して、デバイスのインストールが正常に完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-135">![Microsoft Endpoint Manager Admin Center3 のイメージ](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="5e49a-136">オンボーディングとチェックの状態を完了する</span><span class="sxs-lookup"><span data-stu-id="5e49a-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="5e49a-137">デバイスに Defender for Endpoint for iOS がインストールされた後、アプリ アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![スマートフォンの説明が自動的に生成されるスクリーン ショット](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="5e49a-139">[Defender for Endpoint] アプリ アイコンをタップし、画面の指示に従ってオンボーディングの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="5e49a-140">詳細には、Defender for Endpoint for iOS に必要な iOS アクセス許可のエンド ユーザーによる承諾が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="5e49a-141">オンボードが成功すると、デバイスは Microsoft Defender セキュリティ センターの [デバイス] リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-142">![自動的に生成された携帯電話の説明のスクリーンショット](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="5e49a-143">監視モード用に Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="5e49a-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="5e49a-144">Microsoft Defender for Endpoint for iOS アプリは、これらの種類のデバイスでプラットフォームによって提供される管理機能の強化を考えると、監視対象の iOS/iPadOS デバイスに特化した機能を備えます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-144">The Microsoft Defender for Endpoint for iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="5e49a-145">これらの機能を利用するには、Defender for Endpoint アプリがデバイスが監視モードにあるかどうかが知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e49a-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="5e49a-146">Intune 経由で監視モードを構成する</span><span class="sxs-lookup"><span data-stu-id="5e49a-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="5e49a-147">Intune を使用すると、アプリ構成ポリシーを使用して Defender for iOS アプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5e49a-148">監視対象デバイスのこのアプリ構成ポリシーは、管理対象デバイスにのみ適用され、ベスト プラクティスとしてすべての管理対象 iOS デバイスを対象とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e49a-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="5e49a-149">Microsoft Endpoint [Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理センターにサインインし、[アプリ アプリ構成ポリシーの追加]  >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="5e49a-150">[管理対象デバイス **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-151">![Microsoft Endpoint Manager Admin Center4 のイメージ](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="5e49a-152">[アプリ構成 *ポリシーの作成] ページ* で、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="5e49a-153">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="5e49a-153">Policy Name</span></span>
    - <span data-ttu-id="5e49a-154">プラットフォーム: iOS/iPadOS を選択する</span><span class="sxs-lookup"><span data-stu-id="5e49a-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="5e49a-155">対象アプリ: リスト **から Microsoft Defender ATP** を選択する</span><span class="sxs-lookup"><span data-stu-id="5e49a-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-156">![Microsoft Endpoint Manager Admin Center5 のイメージ](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="5e49a-157">次の画面で、[構成デザイナー **を形式として使用** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="5e49a-158">次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-158">Specify the following property:</span></span>
    - <span data-ttu-id="5e49a-159">構成キー: issupervised</span><span class="sxs-lookup"><span data-stu-id="5e49a-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="5e49a-160">値の型:String</span><span class="sxs-lookup"><span data-stu-id="5e49a-160">Value type: String</span></span>
    - <span data-ttu-id="5e49a-161">構成値: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="5e49a-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-162">![Microsoft Endpoint Manager Admin Center6 のイメージ](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="5e49a-163">[次 **へ] を** クリックして [スコープ タグ **] ページを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="5e49a-164">スコープ タグはオプションです。</span><span class="sxs-lookup"><span data-stu-id="5e49a-164">Scope tags are optional.</span></span> <span data-ttu-id="5e49a-165">続行するには、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e49a-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="5e49a-166">[割り **当て] ページ** で、このプロファイルを受け取るグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="5e49a-167">このシナリオでは、すべてのデバイスをターゲットに設定するベスト **プラクティスです**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="5e49a-168">プロファイルの割り当ての詳細については、「Assign [user and device profiles」を参照してください](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="5e49a-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="5e49a-169">ユーザー グループに展開する場合、ユーザーはポリシーが適用される前にデバイスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e49a-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="5e49a-170">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e49a-170">Click **Next**.</span></span>

1. <span data-ttu-id="5e49a-171">[レビュー **と作成] ページ** で、完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="5e49a-172">新しいプロファイルが構成プロファイルの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="5e49a-173">次に、フィッシング対策機能を強化するには、監視対象の iOS デバイスにカスタム プロファイルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="5e49a-174">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5e49a-174">Follow the steps below:</span></span>
    - <span data-ttu-id="5e49a-175">構成プロファイルのダウンロード [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="5e49a-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="5e49a-176">[デバイス  ->  **] iOS/iPadOS**  ->  **構成プロファイルの [プロファイルの**  ->  **作成] に移動します。**</span><span class="sxs-lookup"><span data-stu-id="5e49a-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5e49a-177">![Microsoft Endpoint Manager Admin Center7 のイメージ](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="5e49a-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="5e49a-178">プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-178">Provide a name of the profile.</span></span> <span data-ttu-id="5e49a-179">構成プロファイル ファイルのインポートを求めるメッセージが表示されたら、上記でダウンロードしたファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="5e49a-180">[割 **り当て** ] セクションで、このプロファイルを適用するデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e49a-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="5e49a-181">ベスト プラクティスとして、これはすべての管理対象 iOS デバイスに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e49a-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="5e49a-182">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e49a-182">Click **Next**.</span></span>
    - <span data-ttu-id="5e49a-183">[レビュー **と作成] ページ** で、完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5e49a-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="5e49a-184">新しいプロファイルが構成プロファイルの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e49a-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e49a-185">次の手順</span><span class="sxs-lookup"><span data-stu-id="5e49a-185">Next Steps</span></span>

[<span data-ttu-id="5e49a-186">iOS 機能用に Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="5e49a-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
