---
title: iOS での Microsoft Defender for Endpoint のアプリ ベースの展開
ms.reviewer: ''
description: アプリを使用して iOS に Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, app, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 6f2b9a1365a27bb7397aea51dcd5bc9e2631afe2
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624707"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="0280c-104">iOS での Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="0280c-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0280c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0280c-105">**Applies to:**</span></span>
- [<span data-ttu-id="0280c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0280c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0280c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0280c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0280c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="0280c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0280c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="0280c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0280c-110">このトピックでは、登録されているデバイス上の iOS での Defender for Endpoint の展開Intune ポータル サイト説明します。</span><span class="sxs-lookup"><span data-stu-id="0280c-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="0280c-111">Intune デバイスの登録の詳細については、「Intune に [iOS/iPadOS デバイスを登録する」を参照してください](/mem/intune/enrollment/ios-enroll)。</span><span class="sxs-lookup"><span data-stu-id="0280c-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0280c-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="0280c-112">Before you begin</span></span>

- <span data-ttu-id="0280c-113">Microsoft Endpoint Manager 管理センター [へのアクセス権を持っている必要があります](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="0280c-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="0280c-114">ユーザーに対して iOS 登録が行われたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0280c-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="0280c-115">iOS で Defender for Endpoint を使用するには、Defender for Endpoint ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280c-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="0280c-116">ライセンスの割 [り当て方法については、「ユーザー](/azure/active-directory/users-groups-roles/licensing-groups-assign) にライセンスを割り当てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0280c-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="0280c-117">iOS 上のエンドポイント用 Microsoft Defender が [Apple App Store で利用可能になります](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="0280c-117">Microsoft Defender for Endpoint on iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="0280c-118">展開手順</span><span class="sxs-lookup"><span data-stu-id="0280c-118">Deployment steps</span></span>

<span data-ttu-id="0280c-119">iOS 上の Defender for Endpoint を展開するには、Intune ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="0280c-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="0280c-120">iOS ストア アプリの追加</span><span class="sxs-lookup"><span data-stu-id="0280c-120">Add iOS store app</span></span>

1. <span data-ttu-id="0280c-121">[Microsoft Endpoint manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)  ->  **アプリ] iOS/iPadOS [iOS** ストア アプリの追加] に移動し、[  ->    ->  選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0280c-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-122">![管理センター 1 Microsoft エンドポイント マネージャーのイメージ](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="0280c-123">[アプリの追加] ページで、[アプリ ストアの検索] をクリック **し** 、検索バーに **「Microsoft Defender Endpoint」** と入力します。</span><span class="sxs-lookup"><span data-stu-id="0280c-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="0280c-124">[検索結果] セクションで *、[Microsoft Defender Endpoint]* をクリックし、[選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0280c-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="0280c-125">[ **最小オペレーティング システム] として [iOS 11.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0280c-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="0280c-126">アプリに関する残りの情報を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0280c-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="0280c-127">[割り *当て] セクションで* 、[必須] **セクションに** 移動し、[グループの追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="0280c-128">その後、iOS アプリで Defender for Endpoint をターゲットとするユーザー グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0280c-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="0280c-129">[選択 **] をクリック** し、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0280c-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0280c-130">選択したユーザー グループは、Intune に登録されたユーザーで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280c-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-131">![管理センター 2 Microsoft エンドポイント マネージャーのイメージ](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="0280c-132">[確認 *と作成] セクション* で、入力された情報が正しいか確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="0280c-133">しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0280c-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="0280c-134">表示されるアプリ情報ページの [モニター]セクションで、[デバイスのインストール状態] を選択して、デバイスのインストールが正常に完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="0280c-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-135">![管理センター 3 Microsoft エンドポイント マネージャーのイメージ](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="0280c-136">VPN プロファイルの自動オンボーディング (簡易オンボーディング)</span><span class="sxs-lookup"><span data-stu-id="0280c-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

> [!NOTE]
> <span data-ttu-id="0280c-137">VPN プロファイルの自動オンボーディングは現在プレビュー中であり、このセクションに記載されている手順は、商用リリース前に大幅に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0280c-137">Auto-onboarding of VPN profile is currently in preview and the steps mentioned in this section may be substantially modified before it's commercially released.</span></span>

<span data-ttu-id="0280c-138">管理者は VPN プロファイルの自動セットアップを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0280c-138">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="0280c-139">これにより、オンボーディング中にユーザーに設定せずに Defender for Endpoint VPN プロファイルが自動的にセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="0280c-139">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="0280c-140">Web Protection 機能を提供するために VPN が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280c-140">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0280c-141">これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="0280c-141">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="0280c-142">[Microsoft Endpoint manager 管理センターで、[デバイス](https://go.microsoft.com/fwlink/?linkid=2109431)構成プロファイル  ->  **の作成プロファイル**]  ->  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-142">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="0280c-143">**[iOS/iPadOS としてプラットフォーム] を選択し、[VPN** **としてプロファイルの種類**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-143">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="0280c-144">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0280c-144">Click **Create**.</span></span>
1. <span data-ttu-id="0280c-145">プロファイルの名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0280c-145">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="0280c-146">[ **接続の種類]** で [カスタム VPN] を選択し、[ **基本 VPN]** セクションで、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0280c-146">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="0280c-147">接続名 = エンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0280c-147">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="0280c-148">VPN サーバー のアドレス = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0280c-148">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="0280c-149">Auth メソッド = "ユーザー名とパスワード"</span><span class="sxs-lookup"><span data-stu-id="0280c-149">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="0280c-150">スプリット トンネリング = 無効</span><span class="sxs-lookup"><span data-stu-id="0280c-150">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="0280c-151">VPN 識別子 = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="0280c-151">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="0280c-152">キーと値のペアで、キー **AutoOnboard を入力し** 、値を True に設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-152">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="0280c-153">自動 VPN の種類 = オンデマンド VPN</span><span class="sxs-lookup"><span data-stu-id="0280c-153">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="0280c-154">[ **オンデマンド ルール** の **追加]** をクリックし、[次の操作を行う] **= [VPN** の確立] を選択します。[すべてのドメイン **] に制限します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-154">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![VPN プロファイル構成のスクリーン ショット](images/ios-deploy-8.png)

1. <span data-ttu-id="0280c-156">[次へ] をクリックし、対象ユーザーにプロファイルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="0280c-156">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="0280c-157">[確認 *と作成] セクション* で、入力された情報が正しいか確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-157">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0280c-158">オンボーディングとチェックの状態を完了する</span><span class="sxs-lookup"><span data-stu-id="0280c-158">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0280c-159">iOS の Defender for Endpoint がデバイスにインストールされた後、アプリ アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0280c-159">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![スマートフォンの説明が自動的に生成されるスクリーン ショット](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="0280c-161">[Defender for Endpoint] アプリ アイコンをタップし、画面の指示に従ってオンボーディングの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="0280c-161">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="0280c-162">詳細には、iOS 上の Defender for Endpoint で必要な iOS アクセス許可のエンド ユーザーによる承諾が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0280c-162">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="0280c-163">オンボードが正常に完了すると、デバイスはデバイス の [デバイス] リストに表示Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="0280c-163">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-164">![自動的に生成された携帯電話の説明のスクリーンショット](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-164">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="0280c-165">監視モード用に Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="0280c-165">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="0280c-166">Microsoft Defender for Endpoint on iOS アプリは、これらの種類のデバイスでプラットフォームによって提供される管理機能の強化を考えると、監視対象の iOS/iPadOS デバイスに特化した機能を備えます。</span><span class="sxs-lookup"><span data-stu-id="0280c-166">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="0280c-167">これらの機能を利用するには、Defender for Endpoint アプリがデバイスが監視モードにあるかどうかが知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280c-167">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="0280c-168">Intune 経由で監視モードを構成する</span><span class="sxs-lookup"><span data-stu-id="0280c-168">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="0280c-169">Intune を使用すると、アプリ構成ポリシーを使用して Defender for iOS アプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0280c-169">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0280c-170">監視対象デバイスのこのアプリ構成ポリシーは、管理対象デバイスにのみ適用され、ベスト プラクティスとしてすべての管理対象 iOS デバイスを対象とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280c-170">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="0280c-171">管理センターにサインインし [Microsoft エンドポイント マネージャーアプリ](https://go.microsoft.com/fwlink/?linkid=2109431)の構成ポリシー **[** 追加]  >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-171">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="0280c-172">[管理対象デバイス **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0280c-172">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-173">![管理センター Microsoft エンドポイント マネージャーのイメージ 4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-173">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="0280c-174">[アプリ構成 *ポリシーの作成] ページ* で、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0280c-174">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="0280c-175">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="0280c-175">Policy Name</span></span>
    - <span data-ttu-id="0280c-176">プラットフォーム: iOS/iPadOS を選択する</span><span class="sxs-lookup"><span data-stu-id="0280c-176">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="0280c-177">対象アプリ: リスト **Microsoft Defender ATP** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0280c-177">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-178">![管理センター Microsoft エンドポイント マネージャーの画像 5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-178">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="0280c-179">次の画面で、[構成デザイナー **を形式として使用** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0280c-179">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="0280c-180">次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280c-180">Specify the following property:</span></span>
    - <span data-ttu-id="0280c-181">構成キー: issupervised</span><span class="sxs-lookup"><span data-stu-id="0280c-181">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="0280c-182">値の型:String</span><span class="sxs-lookup"><span data-stu-id="0280c-182">Value type: String</span></span>
    - <span data-ttu-id="0280c-183">構成値: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="0280c-183">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-184">![管理センター 6 Microsoft エンドポイント マネージャーの画像](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-184">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="0280c-185">[次 **へ] を** クリックして [スコープ タグ **] ページを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="0280c-185">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="0280c-186">スコープ タグはオプションです。</span><span class="sxs-lookup"><span data-stu-id="0280c-186">Scope tags are optional.</span></span> <span data-ttu-id="0280c-187">続行するには、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0280c-187">Click **Next** to continue.</span></span>

1. <span data-ttu-id="0280c-188">[割り **当て] ページ** で、このプロファイルを受け取るグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0280c-188">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="0280c-189">このシナリオでは、すべてのデバイスをターゲットに設定するベスト **プラクティスです**。</span><span class="sxs-lookup"><span data-stu-id="0280c-189">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="0280c-190">プロファイルの割り当ての詳細については、「Assign [user and device profiles」を参照してください](/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="0280c-190">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="0280c-191">ユーザー グループに展開する場合、ユーザーはポリシーが適用される前にデバイスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280c-191">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="0280c-192">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0280c-192">Click **Next**.</span></span>

1. <span data-ttu-id="0280c-193">[レビュー **と作成] ページ** で、完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-193">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="0280c-194">新しいプロファイルが構成プロファイルの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0280c-194">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="0280c-195">次に、フィッシング対策機能を強化するには、監視対象の iOS デバイスにカスタム プロファイルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="0280c-195">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="0280c-196">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0280c-196">Follow the steps below:</span></span>
    - <span data-ttu-id="0280c-197">構成プロファイルのダウンロード [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="0280c-197">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="0280c-198">[デバイス  ->  **] iOS/iPadOS**  ->  **構成プロファイルの [プロファイルの**  ->  **作成] に移動します。**</span><span class="sxs-lookup"><span data-stu-id="0280c-198">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0280c-199">![管理センター 7 Microsoft エンドポイント マネージャーの画像](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="0280c-199">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="0280c-200">プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280c-200">Provide a name of the profile.</span></span> <span data-ttu-id="0280c-201">構成プロファイル ファイルのインポートを求めるメッセージが表示されたら、上記でダウンロードしたファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0280c-201">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="0280c-202">[割 **り当て** ] セクションで、このプロファイルを適用するデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0280c-202">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="0280c-203">ベスト プラクティスとして、これはすべての管理対象 iOS デバイスに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280c-203">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="0280c-204">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0280c-204">Click **Next**.</span></span>
    - <span data-ttu-id="0280c-205">[レビュー **と作成] ページ** で、完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0280c-205">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="0280c-206">新しいプロファイルが構成プロファイルの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0280c-206">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0280c-207">次の手順</span><span class="sxs-lookup"><span data-stu-id="0280c-207">Next Steps</span></span>

[<span data-ttu-id="0280c-208">iOS の機能でエンドポイント用 Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="0280c-208">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
