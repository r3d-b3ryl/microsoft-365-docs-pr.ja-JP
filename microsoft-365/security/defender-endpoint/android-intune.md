---
title: Microsoft Intune を使用して Android 用 Microsoft Defender ATP を展開する
description: Microsoft Intune を使用して Android 用 Microsoft Defender ATP を展開する方法について説明します。
keywords: microsoft、Defender、atp、android、インストール、展開、アンインストール、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e557f60346b2f68354df621b6e4812eac775d812
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165671"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-android-with-microsoft-intune"></a><span data-ttu-id="467b4-104">Microsoft Intune を使用して Microsoft Defender for Endpoint for Android を展開する</span><span class="sxs-lookup"><span data-stu-id="467b4-104">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="467b4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="467b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="467b4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="467b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="467b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="467b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="467b4-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="467b4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="467b4-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="467b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="467b4-110">Intune ポータル サイトに登録されているデバイスに Defender for Endpoint for Android を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="467b4-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="467b4-111">Intune デバイスの登録の詳細については、「デバイスの登録  [」を参照してください](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="467b4-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="467b4-112">**Android 用エンドポイントの Defender が Google Play で [利用できる](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="467b4-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="467b4-113">Intune から Google Play に接続して、デバイス管理者モードと Android Enterprise entrollment モード全体に Defender for Endpoint アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="467b4-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="467b4-114">アプリの更新は、Google Play 経由で自動的に行います。</span><span class="sxs-lookup"><span data-stu-id="467b4-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="467b4-115">デバイス管理者が登録したデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="467b4-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="467b4-116">**Intune ポータル サイトで Android 用 Defender for Endpoint を展開する - デバイス管理者が登録したデバイス**</span><span class="sxs-lookup"><span data-stu-id="467b4-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="467b4-117">Intune Company Portal - デバイス管理者が登録したデバイスに Defender for Endpoint for Android を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="467b4-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="467b4-118">Android ストア アプリとして追加する</span><span class="sxs-lookup"><span data-stu-id="467b4-118">Add as Android store app</span></span>

1. <span data-ttu-id="467b4-119">[Microsoft Endpoint Manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)アプリ] [Android アプリ] [Android ストア アプリの追加] に移動し、[ \>  \> **\>** 選択] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Android ストア アプリケーションを追加する Microsoft Endpoint Manager 管理センターのイメージ](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="467b4-121">[アプリの **追加] ページで** 、[アプリ情報] *セクションに次の情報* を入力します。</span><span class="sxs-lookup"><span data-stu-id="467b4-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="467b4-122">**名前**</span><span class="sxs-lookup"><span data-stu-id="467b4-122">**Name**</span></span> 
   - <span data-ttu-id="467b4-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="467b4-123">**Description**</span></span>
   - <span data-ttu-id="467b4-124">**Publisher** as Microsoft.</span><span class="sxs-lookup"><span data-stu-id="467b4-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="467b4-125">**アプリ ストア URL as** https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play ストア URL)</span><span class="sxs-lookup"><span data-stu-id="467b4-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="467b4-126">その他のフィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="467b4-126">Other fields are optional.</span></span> <span data-ttu-id="467b4-127">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-127">Select **Next**.</span></span>

   ![アプリ情報を追加する Microsoft Endpoint Manager 管理センターの画像](images/mda-addappinfo.png)

3. <span data-ttu-id="467b4-129">[割り *当て] セクション* で、[必須] セクションに移動 **し** 、[グループの追加] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="467b4-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="467b4-130">その後、Defender for Endpoint for Android アプリをターゲットとするユーザー グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="467b4-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="467b4-131">[選択 **] と [** 次へ] の順 **に選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="467b4-132">選択したユーザー グループは、Intune に登録されたユーザーで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="467b4-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Microsoft Endpoint Manager 管理センターで選択されたユーザー グループのイメージ](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="467b4-134">[レビュー **+ 作成] セクション** で、入力した情報が正しいか確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="467b4-135">しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Defender エンドポイント アプリの Microsoft Endpoint Manager 管理センター通知の画像](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="467b4-137">表示されるアプリ情報ページの [モニター]セクションで、[デバイスのインストール状態] を選択して、デバイスのインストールが正常に完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="467b4-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-138">![Microsoft Endpoint Manager Admin Center デバイスのインストールのイメージ](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="467b4-139">オンボーディングとチェックの状態を完了する</span><span class="sxs-lookup"><span data-stu-id="467b4-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="467b4-140">Defender for Endpoint for Android がデバイスにインストールされた後、アプリ アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![モバイル デバイスのアイコン](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="467b4-142">Microsoft Defender ATP アプリ アイコンをタップし、画面の指示に従ってアプリのオンボーディングを完了します。</span><span class="sxs-lookup"><span data-stu-id="467b4-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="467b4-143">詳細には、Defender for Endpoint for Android に必要な Android アクセス許可のエンド ユーザーによる承諾が含まれます。</span><span class="sxs-lookup"><span data-stu-id="467b4-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="467b4-144">オンボードが成功すると、デバイスは Microsoft Defender セキュリティ センターの [デバイス] リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Defender for Endpoint ポータルのデバイスのイメージ](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="467b4-146">Android Enterprise 登録済みデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="467b4-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="467b4-147">Defender for Endpoint for Android では、Android Enterprise 登録済みデバイスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="467b4-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="467b4-148">Intune でサポートされる登録オプションの詳細については、「登録オプション」 [を参照してください](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)。</span><span class="sxs-lookup"><span data-stu-id="467b4-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="467b4-149">**現在、仕事用プロファイルと企業所有の完全に管理されたユーザー デバイス登録を持つ個人所有のデバイスは、展開のためにサポートされています。**</span><span class="sxs-lookup"><span data-stu-id="467b4-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-for-android-as-a-managed-google-play-app"></a><span data-ttu-id="467b4-150">Microsoft Defender for Endpoint for Android を Managed Google Play アプリとして追加する</span><span class="sxs-lookup"><span data-stu-id="467b4-150">Add Microsoft Defender for Endpoint for Android as a Managed Google Play app</span></span>

<span data-ttu-id="467b4-151">管理された Google Play に Microsoft Defender for Endpoint アプリを追加するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="467b4-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="467b4-152">[Microsoft Endpoint Manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)アプリの Android アプリの追加] に移動 \>  \> **し、[\*\*\*\*管理された Google Play アプリ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-153">![Microsoft Endpoint Manager 管理センター管理 Google play の画像](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="467b4-154">その後読み込まれる管理された Google Play ページで、検索ボックスに移動し **、Microsoft Defender を参照します。**</span><span class="sxs-lookup"><span data-stu-id="467b4-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="467b4-155">検索では、Managed Google Play に Microsoft Defender for Endpoint アプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="467b4-156">アプリの検索結果から Microsoft Defender for Endpoint アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="467b4-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Microsoft Endpoint Manager 管理センターアプリ検索の画像](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="467b4-158">次に表示される [アプリの説明] ページで、Defender for Endpoint でアプリの詳細を確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="467b4-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="467b4-159">ページの情報を確認し、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-160">![Managed Google Play のスクリーンショット](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="467b4-161">Defender for Endpoint が動作するために取得するアクセス許可が表示されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="467b4-162">それらを確認し、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-162">Review them and then select **Approve**.</span></span>

    ![Defender for Endpoint プレビュー アプリ承認のスクリーンショット](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="467b4-164">[承認の設定] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="467b4-165">このページでは、Defender for Endpoint for Android が求める可能性がある新しいアプリのアクセス許可を処理するための基本設定が確認されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="467b4-166">選択肢を確認し、希望するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="467b4-167">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-167">Select **Done**.</span></span>

    <span data-ttu-id="467b4-168">既定では、[アプリが新しいアクセス許可を要求するときに承認済みの状態を維持する] を *選択します。*</span><span class="sxs-lookup"><span data-stu-id="467b4-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-169">![[通知のイメージ] タブ](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="467b4-170">アクセス許可処理の選択が行われたら、[同期] を **選択して** Microsoft Defender for Endpoint をアプリの一覧に同期します。</span><span class="sxs-lookup"><span data-stu-id="467b4-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-171">![同期ページのイメージ](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="467b4-172">同期は数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="467b4-172">The sync will complete in a few minutes.</span></span>

    ![Android アプリの画像](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="467b4-174">[Android アプリ **] 画面で** [更新] ボタンを選択すると、Microsoft Defender ATP がアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="467b4-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-175">![Android アプリの一覧の画像](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="467b4-176">Defender for Endpoint は、Intune 経由で管理対象デバイスのアプリ構成ポリシーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="467b4-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="467b4-177">この機能は、該当する Android アクセス許可を自動付与するために利用できます。そのため、エンド ユーザーは、これらのアクセス許可を受け入れる必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="467b4-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="467b4-178">[アプリ **] ページで** 、[アプリ構成ポリシー>に移動し、[> **デバイス>追加する] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Microsoft Endpoint Manager 管理センター Android 管理対象デバイスのイメージ](images/android-mem.png)

    1. <span data-ttu-id="467b4-180">[アプリ構成 **ポリシーの作成] ページ** で、次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="467b4-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="467b4-181">名前: Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="467b4-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="467b4-182">[ **プラットフォームとして Android Enterprise]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="467b4-183">[プロファイル **の種類] として [作業プロファイル** のみ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="467b4-184">[アプリ **の選択] を** クリックし **、[Microsoft Defender ATP] を選択** し **、[OK] を選択し、[次** へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="467b4-185">![アプリ構成ポリシーの作成ページのイメージ](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="467b4-186">[設定 **] ページで** 、[アクセス許可] セクションの [追加] をクリックして、サポートされているアクセス許可の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="467b4-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="467b4-187">[アクセス許可の追加] セクションで、次のアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="467b4-188">外部ストレージ (読み取り)</span><span class="sxs-lookup"><span data-stu-id="467b4-188">External storage (read)</span></span>
       - <span data-ttu-id="467b4-189">外部ストレージ (書き込み)</span><span class="sxs-lookup"><span data-stu-id="467b4-189">External storage (write)</span></span>

       <span data-ttu-id="467b4-190">次に **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="467b4-191">![Android 作成アプリ構成ポリシーのイメージ](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="467b4-192">これで、両方のアクセス許可が一覧表示され、[アクセス許可の状態] ドロップダウンで [自動入力] を選択し、[次へ] を選択して、両方を自動入力 **できます**。</span><span class="sxs-lookup"><span data-stu-id="467b4-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="467b4-193">![Android 自動付与アプリ構成ポリシーの作成のイメージ](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="467b4-194">[割 **り当て]** ページで、このアプリ構成ポリシーを割り当てるユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="467b4-195">[グループ **の選択] をクリック** して、該当するグループを含め、選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="467b4-196">ここで選択したグループは、通常、エンドポイント Android アプリ用 Microsoft Defender を割り当てるのと同じグループです。</span><span class="sxs-lookup"><span data-stu-id="467b4-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="467b4-197">![アプリ構成ポリシーの作成のイメージ](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="467b4-198">次に **表示される [確認と作成** ] ページで、すべての情報を確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="467b4-199">ストレージアクセス許可を自動指定する Defender for Endpoint のアプリ構成ポリシーが、選択したユーザー グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="467b4-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="467b4-200">![Android レビュー作成アプリ構成ポリシーのイメージ](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="467b4-201">[**プロパティの割り当ての** 編集] の一覧で [Microsoft Defender ATP \>  \> **アプリ] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![アプリの一覧の画像](images/mda-properties.png)


11. <span data-ttu-id="467b4-203">アプリを必須アプリとして *ユーザー* グループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="467b4-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="467b4-204">これは、ポータル サイトアプリ経由でデバイスを次回同期する際に、作業プロファイルに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="467b4-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="467b4-205">この割り当ては、[必須]セクション [グループの追加] に移動し、ユーザー グループを選択して [選択 \> ] をクリックすることで **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="467b4-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-206">![アプリケーションの編集ページのイメージ](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="467b4-207">[アプリケーション **の編集] ページ** で、上記で入力した情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="467b4-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="467b4-208">次に、[ **確認] + [保存] の** 順に選択し **、[保存] を** 再度選択して割り当てを開始します。</span><span class="sxs-lookup"><span data-stu-id="467b4-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="467b4-209">Always-on VPN の自動セットアップ</span><span class="sxs-lookup"><span data-stu-id="467b4-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="467b4-210">Defender for Endpoint は、Intune 経由で管理対象デバイスのデバイス構成ポリシーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="467b4-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="467b4-211">この機能は、Android Enterprise 登録済みデバイスでの **Always-on VPN** の自動セットアップに利用できます。そのため、エンド ユーザーはオンボーディング中に VPN サービスをセットアップする必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="467b4-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="467b4-212">[**デバイス]** で、[**構成プロファイル] [** プロファイル プラットフォームの  >    >    >  **作成] [Android Enterprise Select** Device **Restrictions]** を選択します。デバイス登録の種類に基づいて、次のいずれかの下に設定します。</span><span class="sxs-lookup"><span data-stu-id="467b4-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="467b4-213">**完全管理、専用、および作業Corporate-Ownedプロファイル**</span><span class="sxs-lookup"><span data-stu-id="467b4-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="467b4-214">**個人所有の作業プロファイル**</span><span class="sxs-lookup"><span data-stu-id="467b4-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="467b4-215">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-215">Select **Create**.</span></span>
 
   > ![デバイス構成プロファイルのイメージ作成](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="467b4-217">**構成設定** 構成プロファイル **を一** 意 **に識別するための名前** と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="467b4-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![デバイス構成プロファイルのイメージ 名前と説明](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="467b4-219">[接続 **] を選択し** 、VPN を構成します。</span><span class="sxs-lookup"><span data-stu-id="467b4-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="467b4-220">作業 **プロファイルで Always-on VPN** Setup a VPN クライアントを有効にして、可能な限り VPN に自動的に接続して再接続します。</span><span class="sxs-lookup"><span data-stu-id="467b4-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="467b4-221">特定のデバイス上の常時接続 VPN 用に構成できる VPN クライアントは 1 つのみです。そのため、1 つのデバイスに展開する常時接続 VPN ポリシーは 1 つ以下にしてください。</span><span class="sxs-lookup"><span data-stu-id="467b4-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="467b4-222">[VPN **クライアント** のカスタム] ドロップダウン リスト [カスタム VPN] を選択します。この場合、Web 保護機能を提供するために使用される Defender for Endpoint VPN です。</span><span class="sxs-lookup"><span data-stu-id="467b4-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="467b4-223">この VPN の自動セットアップを機能するには、Microsoft Defender ATP アプリをユーザーのデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="467b4-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="467b4-224">Google Play **ストアで** Microsoft Defender ATP アプリのパッケージ ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="467b4-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="467b4-225">Defender アプリの URL https://play.google.com/store/apps/details?id=com.microsoft.scmx の場合、パッケージ ID は **com.microsoft.scmx です**。</span><span class="sxs-lookup"><span data-stu-id="467b4-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="467b4-226">**ロックダウン モード** 構成されていません (既定)</span><span class="sxs-lookup"><span data-stu-id="467b4-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![デバイス構成プロファイルのイメージで Always-on VPN を有効にする](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="467b4-228">**割り当て**[割  **り当て]** ページで、このアプリ構成ポリシーを割り当てる   ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="467b4-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="467b4-229">[グループ **の選択]** をクリックして、該当するグループを含め、選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="467b4-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="467b4-230">ここで選択したグループは、通常、エンドポイント Android アプリ用 Microsoft Defender を割り当てるのと同じグループです。</span><span class="sxs-lookup"><span data-stu-id="467b4-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![デバイス構成プロファイル割り当てのイメージ](images/4autosetupofvpn.png)

5. <span data-ttu-id="467b4-232">次に **表示される [確認と作成** ] ページで、すべての情報を確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="467b4-233">これで、デバイス構成プロファイルが選択したユーザー グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="467b4-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![デバイス構成プロファイルのイメージ レビューと作成](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="467b4-235">オンボーディングとチェックの状態を完了する</span><span class="sxs-lookup"><span data-stu-id="467b4-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="467b4-236">[デバイスのインストール状態] をクリックして、Microsoft Defender for Endpoint for Android のインストール状態 **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-236">Confirm the installation status of Microsoft Defender for Endpoint for Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="467b4-237">デバイスがここに表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="467b4-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="467b4-238">![デバイスのインストール状態のイメージ](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="467b4-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="467b4-239">デバイスで、作業プロファイルにアクセスしてオンボーディングの状態を **検証できます**。</span><span class="sxs-lookup"><span data-stu-id="467b4-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="467b4-240">Defender for Endpoint が使用可能で、個人用所有のデバイスに仕事用プロファイルが登録 **されているのを確認します**。</span><span class="sxs-lookup"><span data-stu-id="467b4-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="467b4-241">企業所有の完全に管理されたユーザー デバイスに登録されている場合は、デバイス上に 1 つのプロファイルが作成され、Defender for Endpoint が使用可能なと確認できます。</span><span class="sxs-lookup"><span data-stu-id="467b4-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![モバイル デバイスのアプリのイメージ](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="467b4-243">アプリがインストールされると、アプリを開いてアクセス許可を受け入れ、オンボーディングが成功する必要があります。</span><span class="sxs-lookup"><span data-stu-id="467b4-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Microsoft Defender for Endpoint アプリを使用したモバイル デバイスのイメージ](images/mda-devicesafe.png)

4. <span data-ttu-id="467b4-245">この段階では、デバイスは Android 用 Defender for Endpoint に正常にオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="467b4-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="467b4-246">これを確認するには [、Microsoft Defender セキュリティ センターの](https://securitycenter.microsoft.com) [デバイス] ページに **移動** します。</span><span class="sxs-lookup"><span data-stu-id="467b4-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![エンドポイント ポータル用 Microsoft Defender のイメージ](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="467b4-248">関連項目</span><span class="sxs-lookup"><span data-stu-id="467b4-248">Related topics</span></span>
- [<span data-ttu-id="467b4-249">Android 用エンドポイント向け Microsoft Defender の概要</span><span class="sxs-lookup"><span data-stu-id="467b4-249">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="467b4-250">Android の機能用に Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="467b4-250">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)