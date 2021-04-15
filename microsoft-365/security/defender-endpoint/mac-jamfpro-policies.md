---
title: Jamf Pro で Microsoft Defender ATP for macOS ポリシーをセットアップする
description: Jamf Pro で Microsoft Defender ATP for macOS ポリシーをセットアップする方法について説明します。
keywords: ポリシー, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 79f5837ae6bae6e6a9d952d90605f4cf7b31262e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765133"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="3b6d2-104">Jamf Pro の macOS ポリシーで Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="3b6d2-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3b6d2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-105">**Applies to:**</span></span>

- [<span data-ttu-id="3b6d2-106">Defender for Endpoint on Mac</span><span class="sxs-lookup"><span data-stu-id="3b6d2-106">Defender for Endpoint on Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="3b6d2-107">このページでは、Jamf Pro で macOS ポリシーを設定するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="3b6d2-108">次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="3b6d2-109">Microsoft Defender for Endpoint オンボーディング パッケージの取得</span><span class="sxs-lookup"><span data-stu-id="3b6d2-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="3b6d2-110">オンボーディング パッケージを使用して Jamf Pro で構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="3b6d2-111">エンドポイントの Microsoft Defender の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="3b6d2-112">Microsoft Defender for Endpoint 通知の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="3b6d2-113">Microsoft AutoUpdate (MAU) の構成</span><span class="sxs-lookup"><span data-stu-id="3b6d2-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="3b6d2-114">Microsoft Defender for Endpoint へのフル ディスク アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="3b6d2-115">Microsoft Defender for Endpoint のカーネル拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="3b6d2-116">エンドポイント用 Microsoft Defender のシステム拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="3b6d2-117">ネットワーク拡張機能の構成</span><span class="sxs-lookup"><span data-stu-id="3b6d2-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="3b6d2-118">macOS で Microsoft Defender for Endpoint でスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="3b6d2-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="3b6d2-119">macOS での Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="3b6d2-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="3b6d2-120">手順 1: Microsoft Defender for Endpoint オンボーディング パッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="3b6d2-121">[Microsoft Defender セキュリティ センターで、[](https://securitycenter.microsoft.com )オンボーディングの **設定] >移動します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="3b6d2-122">展開方法として、オペレーティング システムとして macOS、モバイル デバイス管理 / Microsoft Intune を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Microsoft Defender セキュリティ センターのイメージ](images/onboarding-macos.png)

3. <span data-ttu-id="3b6d2-124">[ **オンボード パッケージのダウンロード] (WindowsDefenderATPOnboardingPackage.zip)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="3b6d2-125">抽出 `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="3b6d2-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="3b6d2-126">ファイルを好みの場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="3b6d2-127">例: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="3b6d2-128">手順 2: オンボード パッケージを使用して Jamf Pro で構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="3b6d2-129">前のセクション `WindowsDefenderATPOnboarding.plist` からファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![WindowsDefenderATPOnboarding ファイルのイメージ](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="3b6d2-131">Jamf Pro ダッシュボードで、[新規] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![新しい Jamf Pro ダッシュボードの作成イメージ](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="3b6d2-133">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-133">Enter the following details:</span></span>

   <span data-ttu-id="3b6d2-134">**全般**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-134">**General**</span></span>
   - <span data-ttu-id="3b6d2-135">名前: macOS の MDATP オンボーディング</span><span class="sxs-lookup"><span data-stu-id="3b6d2-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="3b6d2-136">説明: mDATP EDR オンボーディング for macOS</span><span class="sxs-lookup"><span data-stu-id="3b6d2-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="3b6d2-137">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="3b6d2-137">Category: None</span></span>
   - <span data-ttu-id="3b6d2-138">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="3b6d2-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="3b6d2-139">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="3b6d2-139">Level: Computer Level</span></span>

4. <span data-ttu-id="3b6d2-140">[**アプリケーションの設定] &[構成] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![アプリの構成とカスタム設定のイメージ](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="3b6d2-142">[ファイル **のアップロード (PLIST ファイル) を選択し、[基本設定ドメイン]** **に次を** 入力します `com.microsoft.wdav.atp` 。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![jamfpro plist アップロード ファイルのイメージ](images/jamfpro-plist-upload.png)

    ![アップロード ファイル プロパティリスト ファイルのイメージ](images/jamfpro-plist-file.png)

7. <span data-ttu-id="3b6d2-145">[開 **く] を** 選択し、オンボーディング ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-145">Select **Open** and select the onboarding file.</span></span>

    ![オンボード ファイルのイメージ](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="3b6d2-147">[アップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-147">Select **Upload**.</span></span> 

    ![plist ファイルのアップロードのイメージ](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="3b6d2-149">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-149">Select the **Scope** tab.</span></span>

    ![[スコープのイメージ] タブ](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="3b6d2-151">ターゲット コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-151">Select the target computers.</span></span>

    ![ターゲット コンピューターのイメージ](images/jamfpro-target-computer.png)

    ![ターゲットのイメージ](images/jamfpro-targets.png) 

11. <span data-ttu-id="3b6d2-154">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-154">Select **Save**.</span></span>

    ![展開ターゲット コンピューターのイメージ](images/jamfpro-deployment-target.png)

    ![選択したターゲット コンピューターのイメージ](images/jamfpro-target-selected.png)

12. <span data-ttu-id="3b6d2-157">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-157">Select **Done**.</span></span>

    ![ターゲット グループ コンピューターのイメージ](images/jamfpro-target-group.png)

    ![構成プロファイルの一覧](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="3b6d2-160">手順 3: エンドポイントの Microsoft Defender の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="3b6d2-161">次の Microsoft Defender for Endpoint 構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="3b6d2-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="3b6d2-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="3b6d2-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="3b6d2-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="3b6d2-164">既定ではオンにされません。macOS 用にサードパーティの AV を実行する予定の場合は、 に設定します `true` 。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="3b6d2-165">除外</span><span class="sxs-lookup"><span data-stu-id="3b6d2-165">exclusions</span></span>
    - <span data-ttu-id="3b6d2-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="3b6d2-166">excludedPath</span></span>
    - <span data-ttu-id="3b6d2-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="3b6d2-167">excludedFileExtension</span></span>
    - <span data-ttu-id="3b6d2-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="3b6d2-168">excludedFileName</span></span>
    - <span data-ttu-id="3b6d2-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3b6d2-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="3b6d2-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="3b6d2-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="3b6d2-171">EICAR はサンプルに含め、概念実証を行う場合は、EICAR をテストする場合は特に削除してください。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="3b6d2-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="3b6d2-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="3b6d2-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="3b6d2-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="3b6d2-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="3b6d2-174">archive_bomb</span></span>
    - <span data-ttu-id="3b6d2-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="3b6d2-175">cloudService</span></span>
    - <span data-ttu-id="3b6d2-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="3b6d2-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="3b6d2-177">tags</span><span class="sxs-lookup"><span data-stu-id="3b6d2-177">tags</span></span>
    - <span data-ttu-id="3b6d2-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="3b6d2-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="3b6d2-179">詳細については [、「Jamf 構成プロファイルのプロパティ 一覧」を参照してください](mac-preferences.md#property-list-for-jamf-configuration-profile)。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="3b6d2-180">ファイルをとして保存します `MDATP_MDAV_configuration_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="3b6d2-181">Jamf Pro ダッシュボードで、[全般] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![新しい Jamf Pro ダッシュボードのイメージ](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="3b6d2-183">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-183">Enter the following details:</span></span>

    <span data-ttu-id="3b6d2-184">**全般**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-184">**General**</span></span>
    
    - <span data-ttu-id="3b6d2-185">名前: MDATP MDAV 構成設定</span><span class="sxs-lookup"><span data-stu-id="3b6d2-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="3b6d2-186">説明:\<blank\></span><span class="sxs-lookup"><span data-stu-id="3b6d2-186">Description:\<blank\></span></span>
    - <span data-ttu-id="3b6d2-187">カテゴリ: なし (既定)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-187">Category: None (default)</span></span>
    - <span data-ttu-id="3b6d2-188">配布方法: 自動インストール(既定)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="3b6d2-189">Level: Computer Level(default)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-189">Level: Computer Level(default)</span></span>

    ![MDATP MDAV 構成設定のイメージ](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="3b6d2-191">[**アプリケーションの設定] &[構成] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![アプリとカスタム設定のイメージ](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="3b6d2-193">[ファイル **のアップロード] (PLIST ファイル) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-193">Select **Upload File (PLIST file)**.</span></span>

    ![構成設定 plist ファイルのイメージ](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="3b6d2-195">[ **基本設定ドメイン] で、「PLIST** `com.microsoft.wdav` ファイルのアップロード  **」と入力し、[アップロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![構成設定の基本設定ドメインのイメージ](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="3b6d2-197">[ファイル **の選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-197">Select **Choose File**.</span></span>

    ![構成設定のイメージファイルを選択する](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="3b6d2-199">**[MDATP_MDAV_configuration_settings.plist] を選択し、[** 開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![mdatpmdav 構成設定のイメージ](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="3b6d2-201">[アップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-201">Select **Upload**.</span></span>

    ![構成設定のアップロードのイメージ](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![構成設定のアップロード イメージのイメージ](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="3b6d2-204">Intune ファイルをアップロードすると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="3b6d2-205">![構成設定 intune ファイルのアップロードのイメージ](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="3b6d2-206">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-206">Select **Save**.</span></span> 

    ![構成設定のイメージ 画像を保存する](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="3b6d2-208">ファイルがアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-208">The file is uploaded.</span></span>

    ![構成設定ファイルアップロード画像の画像](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![アップロードされた構成設定ファイルのイメージ](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="3b6d2-211">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-211">Select the **Scope** tab.</span></span>

    ![構成設定スコープのイメージ](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="3b6d2-213">**[Contoso's Machine Group] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="3b6d2-214">[追加 **] を** 選択し、[保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-214">Select **Add**, then select **Save**.</span></span>

    ![構成設定のイメージを追加する](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![構成設定の保存のイメージの追加](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="3b6d2-217">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-217">Select **Done**.</span></span> <span data-ttu-id="3b6d2-218">新しい構成プロファイルが **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-218">You'll see the new **Configuration profile**.</span></span>

    ![構成設定の構成プロファイル イメージのイメージ](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="3b6d2-220">手順 4: 通知の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="3b6d2-221">これらの手順は、macOS 10.15 (Catalina) 以降に適用できます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="3b6d2-222">Jamf Pro ダッシュボードで、[コンピューター] 、[ **構成** プロファイル **] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-222">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="3b6d2-223">[ **新規] を** クリックし、[オプション] に次の詳細を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-223">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="3b6d2-224">タブ **全般**:</span><span class="sxs-lookup"><span data-stu-id="3b6d2-224">Tab **General**:</span></span> 
        - <span data-ttu-id="3b6d2-225">**名前**: MDATP MDAV 通知の設定</span><span class="sxs-lookup"><span data-stu-id="3b6d2-225">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="3b6d2-226">**説明**: macOS 10.15 (Catalina) 以降</span><span class="sxs-lookup"><span data-stu-id="3b6d2-226">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="3b6d2-227">**カテゴリ**: なし *(既定)*</span><span class="sxs-lookup"><span data-stu-id="3b6d2-227">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="3b6d2-228">**配布方法**: 自動的にインストール *する (既定)*</span><span class="sxs-lookup"><span data-stu-id="3b6d2-228">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="3b6d2-229">**レベル**: コンピューター レベル *(既定)*</span><span class="sxs-lookup"><span data-stu-id="3b6d2-229">**Level**: Computer Level *(default)*</span></span>

        ![構成プロファイル設定 mdatpmdav のイメージ](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="3b6d2-231">[タブ **通知]** をクリック **し、[追加**] をクリックし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-231">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="3b6d2-232">**バンドル ID**: `com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-232">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="3b6d2-233">**重大な通知**: [無効にする] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-233">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="3b6d2-234">**通知**: [有効にする **] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-234">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="3b6d2-235">**バナー通知の種類**: [含める]**と [一時**]  *(既定) を選択します。*</span><span class="sxs-lookup"><span data-stu-id="3b6d2-235">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="3b6d2-236">**ロック画面の通知**: [非表示] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-236">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="3b6d2-237">**通知センターの通知**: [表示] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-237">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="3b6d2-238">**バッジ アプリのアイコン**: [表示] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-238">**Badge app icon**: Click **Display**</span></span>

        ![構成設定 mdatpmdav 通知トレイのイメージ](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="3b6d2-240">[タブ **通知]** の [ **もう 1** 回追加] をクリックし、[新しい通知の設定 **] まで下にスクロールします。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="3b6d2-241">**バンドル ID**: `com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-241">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="3b6d2-242">残りの設定を上記と同じ値に構成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-242">Configure the rest of the settings to the same values as above</span></span>

        ![構成設定 mdatpmdav 通知 mau のイメージ](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="3b6d2-244">通知構成が 2 つの 「テーブル」 に追加され、もう 1 つはバンドル ID : **com.microsoft.wdav.tray、** もう 1 つはバンドル **ID: com.microsoft.autoupdate2** です。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-244">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="3b6d2-245">要件ごとにアラート設定を構成することもできますが、バンドル ID は前の説明とまったく同じにする必要があります。Include **スイッチは** 通知に対して **[オン] にする** 必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-245">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="3b6d2-246">[スコープ] **タブを選択** し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-246">Select the **Scope** tab, then select **Add**.</span></span>

    ![構成設定スコープの追加のイメージ](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="3b6d2-248">**[Contoso's Machine Group] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-248">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="3b6d2-249">[追加 **] を** 選択し、[保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-249">Select **Add**, then select **Save**.</span></span>
    
    ![構成設定 contoso machine grp save のイメージ](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![構成設定のイメージの保存の追加](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="3b6d2-252">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-252">Select **Done**.</span></span> <span data-ttu-id="3b6d2-253">新しい構成プロファイルが **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-253">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="3b6d2-254">![構成設定完了 img のイメージ](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-254">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="3b6d2-255">手順 5: Microsoft AutoUpdate (MAU) を構成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-255">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="3b6d2-256">次の Microsoft Defender for Endpoint 構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-256">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="3b6d2-257">として保存します `MDATP_MDAV_MAU_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-257">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="3b6d2-258">Jamf Pro ダッシュボードで、[全般] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-258">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![構成設定の一般的なイメージのイメージ](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="3b6d2-260">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-260">Enter the following details:</span></span>

    <span data-ttu-id="3b6d2-261">**全般**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-261">**General**</span></span> 
    
    - <span data-ttu-id="3b6d2-262">名前: MDATP MDAV MAU の設定</span><span class="sxs-lookup"><span data-stu-id="3b6d2-262">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="3b6d2-263">説明: MacOS 用 MDATP の Microsoft AutoUpdate 設定</span><span class="sxs-lookup"><span data-stu-id="3b6d2-263">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="3b6d2-264">カテゴリ: なし (既定)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-264">Category: None (default)</span></span>
    - <span data-ttu-id="3b6d2-265">配布方法: 自動インストール(既定)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-265">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="3b6d2-266">Level: Computer Level(default)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-266">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="3b6d2-267">[**アプリケーションの設定] &[構成] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-267">In **Application & Custom Settings** select **Configure**.</span></span>

    ![構成設定アプリとカスタム設定のイメージ](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="3b6d2-269">[ファイル **のアップロード] (PLIST ファイル) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-269">Select **Upload File (PLIST file)**.</span></span>

    ![構成設定 plist のイメージ](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="3b6d2-271">[基本 **設定ドメイン]** に「:」 `com.microsoft.autoupdate2` と入力し **、[PLIST ファイルのアップロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-271">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![構成設定のプリフェッチ ドメインのイメージ](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="3b6d2-273">[ファイル **の選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-273">Select **Choose File**.</span></span>

    ![構成設定の選択ファイルのイメージ](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="3b6d2-275">**[MDATP_MDAV_MAU_settings.plist] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-275">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![構成設定 mdatpmdavmau 設定のイメージ](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="3b6d2-277">[アップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-277">Select **Upload**.</span></span>
    <span data-ttu-id="3b6d2-278">![構成設定 uplimage のイメージ](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-278">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![構成設定 uplimg のイメージ](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="3b6d2-280">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-280">Select **Save**.</span></span>

    ![構成設定 saveimg のイメージ](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="3b6d2-282">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-282">Select the **Scope** tab.</span></span>
   
     ![構成設定 scopetab のイメージ](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="3b6d2-284">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-284">Select **Add**.</span></span>
    
    ![構成設定 addimg1 のイメージ](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![構成設定 addimg2 のイメージ](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![構成設定 addimg3 のイメージ](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="3b6d2-288">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-288">Select **Done**.</span></span>
    
    ![構成設定 doneimage のイメージ](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="3b6d2-290">手順 6: エンドポイント用 Microsoft Defender へのフル ディスク アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-290">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="3b6d2-291">Jamf Pro ダッシュボードで、[構成プロファイル **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-291">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![構成設定構成プロファイルのイメージ](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="3b6d2-293">[+ **新規] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-293">Select **+ New**.</span></span> 

3. <span data-ttu-id="3b6d2-294">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-294">Enter the following details:</span></span>

    <span data-ttu-id="3b6d2-295">**全般**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-295">**General**</span></span> 
    - <span data-ttu-id="3b6d2-296">名前: MDATP MDAV - EDR および AV へのフル ディスク アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="3b6d2-297">説明: macOS Catalina 以降では、新しいプライバシー設定ポリシーコントロール</span><span class="sxs-lookup"><span data-stu-id="3b6d2-297">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="3b6d2-298">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="3b6d2-298">Category: None</span></span>
    - <span data-ttu-id="3b6d2-299">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="3b6d2-299">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="3b6d2-300">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="3b6d2-300">Level: Computer level</span></span>


    ![構成設定全般のイメージ](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="3b6d2-302">[ **プライバシー設定の構成] ポリシーコントロールで、[構成** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-302">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![構成のプライバシー ポリシー制御のイメージ](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="3b6d2-304">[ **プライバシー設定ポリシー制御] で、** 次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-304">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="3b6d2-305">識別子: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-305">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="3b6d2-306">識別子の種類: バンドル ID</span><span class="sxs-lookup"><span data-stu-id="3b6d2-306">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="3b6d2-307">コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-307">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![構成設定のプライバシー設定ポリシー制御の詳細のイメージ](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="3b6d2-309">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-309">Select **+ Add**.</span></span>

    ![構成設定のイメージ システム ポリシーのすべてのファイルを追加する](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="3b6d2-311">[アプリまたはサービス] で **、SystemPolicyAllFiles に設定する**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-311">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="3b6d2-312">[アクセス] の下: [許可] に **設定します。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-312">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="3b6d2-313">[ **保存]** を選択します (右下の保存は選択しない)。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-313">Select **Save** (not the one at the bottom right).</span></span>

    ![構成設定の保存イメージのイメージ](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="3b6d2-315">[アプリ アクセス `+` ] の横にある **記号をクリックして** 、新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-315">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![構成設定アプリアクセスのイメージ](images/tcc-add-entry.png)

9. <span data-ttu-id="3b6d2-317">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-317">Enter the following details:</span></span>

    - <span data-ttu-id="3b6d2-318">識別子: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-318">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="3b6d2-319">識別子の種類: バンドル ID</span><span class="sxs-lookup"><span data-stu-id="3b6d2-319">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="3b6d2-320">コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-320">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="3b6d2-321">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-321">Select **+ Add**.</span></span>

    ![構成設定 tcc epsext エントリのイメージ](images/tcc-epsext-entry.png)

    - <span data-ttu-id="3b6d2-323">[アプリまたはサービス] で **、SystemPolicyAllFiles に設定する**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-323">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="3b6d2-324">[アクセス] の下: [許可] に **設定します。**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-324">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="3b6d2-325">[ **保存]** を選択します (右下の保存は選択しない)。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-325">Select **Save** (not the one at the bottom right).</span></span>

    ![構成設定 tcc epsext image2 のイメージ](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="3b6d2-327">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-327">Select the **Scope** tab.</span></span>

    ![構成設定スコープのイメージ](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="3b6d2-329">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-329">Select **+ Add**.</span></span>

    ![構成設定のイメージ addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="3b6d2-331">[ **グループ名]** > [コンピューター グループ] **を** 選択> **Contoso の MachineGroup を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-331">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![構成設定 contoso machinegrp のイメージ](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="3b6d2-333">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-333">Select **Add**.</span></span> 

16. <span data-ttu-id="3b6d2-334">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-334">Select **Save**.</span></span> 
    
17. <span data-ttu-id="3b6d2-335">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-335">Select **Done**.</span></span>
    
    ![構成設定 donimg のイメージ](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![構成設定 donimg2 のイメージ](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="3b6d2-338">または、「Jamf Pro を使用したカスタム構成プロファイルの展開」の説明に従って [、fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) をダウンロードして JAMF 構成プロファイルに [アップロードできます|方法 2: Jamf Pro に構成プロファイルをアップロードします](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-338">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3b6d2-339">手順 7: Microsoft Defender for Endpoint のカーネル拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-339">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="3b6d2-340">Apple Silicon (M1) デバイスは KEXT をサポートしていない。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-340">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="3b6d2-341">KEXT ポリシーからなる構成プロファイルのインストールは、これらのデバイスで失敗します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-341">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="3b6d2-342">[構成プロファイル **] で、[+** 新規 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-342">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自動的に生成されたソーシャル メディア投稿の説明のスクリーンショット](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="3b6d2-344">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-344">Enter the following details:</span></span>

    <span data-ttu-id="3b6d2-345">**全般**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-345">**General**</span></span> 
    
    - <span data-ttu-id="3b6d2-346">名前: MDATP MDAV カーネル拡張機能</span><span class="sxs-lookup"><span data-stu-id="3b6d2-346">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="3b6d2-347">説明: MDATP カーネル拡張機能 (kext)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-347">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="3b6d2-348">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="3b6d2-348">Category: None</span></span>
    - <span data-ttu-id="3b6d2-349">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="3b6d2-349">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="3b6d2-350">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="3b6d2-350">Level: Computer Level</span></span>

    ![構成設定 mdatpmdav カーネルのイメージ](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="3b6d2-352">[承認済 **みカーネル拡張機能の構成] で、[構成** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-352">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![構成設定承認済みカーネル ext のイメージ](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="3b6d2-354">[ **承認済みカーネル拡張機能]** で、次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-354">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="3b6d2-355">表示名: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="3b6d2-355">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="3b6d2-356">チーム ID: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3b6d2-356">Team ID: UBF8T346G9</span></span>

    ![構成設定 appr カーネル拡張機能のイメージ](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="3b6d2-358">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-358">Select the **Scope** tab.</span></span>

    ![構成設定スコープ タブ img のイメージ](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="3b6d2-360">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-360">Select **+ Add**.</span></span>

7. <span data-ttu-id="3b6d2-361">[ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-361">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="3b6d2-362">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-362">Select **+ Add**.</span></span>

    ![構成設定のイメージにイメージを追加する](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="3b6d2-364">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-364">Select **Save**.</span></span>

    ![構成設定の saveimag のイメージ](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="3b6d2-366">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-366">Select **Done**.</span></span>

    ![doneimag の構成設定のイメージ](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="3b6d2-368">または、「Jamf Pro を使用したカスタム構成プロファイルの展開」の説明に従って [、kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) をダウンロードして JAMF 構成プロファイルにアップロード [できます|方法 2: Jamf Pro に構成プロファイルをアップロードします](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-368">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3b6d2-369">手順 8: エンドポイント用 Microsoft Defender のシステム拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-369">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="3b6d2-370">[構成プロファイル **] で、[+** 新規 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-370">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自動的に生成されたソーシャル メディア投稿の説明のスクリーンショット](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="3b6d2-372">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-372">Enter the following details:</span></span>

    <span data-ttu-id="3b6d2-373">**全般**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-373">**General**</span></span>
    
    - <span data-ttu-id="3b6d2-374">名前: MDATP MDAV システム拡張機能</span><span class="sxs-lookup"><span data-stu-id="3b6d2-374">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="3b6d2-375">説明: MDATP システム拡張機能</span><span class="sxs-lookup"><span data-stu-id="3b6d2-375">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="3b6d2-376">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="3b6d2-376">Category: None</span></span>
    - <span data-ttu-id="3b6d2-377">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="3b6d2-377">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="3b6d2-378">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="3b6d2-378">Level: Computer Level</span></span>

    ![構成設定 sysext new prof のイメージ](images/sysext-new-profile.png)

3. <span data-ttu-id="3b6d2-380">[ **システム拡張機能] で、[構成** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-380">In **System Extensions** select **Configure**.</span></span>

   ![構成設定 sysext config のイメージ](images/sysext-configure.png)

4. <span data-ttu-id="3b6d2-382">[System **Extensions] に次** の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-382">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="3b6d2-383">表示名: Microsoft Corp. System Extensions</span><span class="sxs-lookup"><span data-stu-id="3b6d2-383">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="3b6d2-384">システム拡張の種類: 許可されているシステム拡張機能</span><span class="sxs-lookup"><span data-stu-id="3b6d2-384">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="3b6d2-385">チーム識別子: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3b6d2-385">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="3b6d2-386">許可されるシステム拡張機能:</span><span class="sxs-lookup"><span data-stu-id="3b6d2-386">Allowed System Extensions:</span></span>
     - <span data-ttu-id="3b6d2-387">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-387">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="3b6d2-388">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-388">**com.microsoft.wdav.netext**</span></span>

    ![構成設定 sysextconfig2 のイメージ](images/sysext-configure2.png)

5. <span data-ttu-id="3b6d2-390">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-390">Select the **Scope** tab.</span></span>

    ![構成設定 scopeimage のイメージ](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="3b6d2-392">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-392">Select **+ Add**.</span></span>

7. <span data-ttu-id="3b6d2-393">[ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-393">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="3b6d2-394">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-394">Select **+ Add**.</span></span>

   ![構成設定 addima のイメージ](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="3b6d2-396">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-396">Select **Save**.</span></span>

   ![構成設定 sysext スコープのイメージ](images/sysext-scope.png)

10. <span data-ttu-id="3b6d2-398">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-398">Select **Done**.</span></span>

    ![構成設定 sysext-final のイメージ](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="3b6d2-400">手順 9: ネットワーク拡張機能を構成する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-400">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="3b6d2-401">エンドポイント検出および応答機能の一環として、macOS 上の Microsoft Defender for Endpoint はソケット トラフィックを検査し、この情報を Microsoft Defender セキュリティ センター ポータルに報告します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-401">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="3b6d2-402">次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-402">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="3b6d2-403">これらの手順は、macOS 10.15 (Catalina) 以降に適用できます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-403">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="3b6d2-404">Jamf Pro ダッシュボードで、[コンピューター] 、[ **構成** プロファイル **] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-404">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="3b6d2-405">[ **新規] を** クリックし、[オプション] に次の詳細を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-405">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="3b6d2-406">タブ **全般**:</span><span class="sxs-lookup"><span data-stu-id="3b6d2-406">Tab **General**:</span></span> 
        - <span data-ttu-id="3b6d2-407">**名前**: Microsoft Defender ATP ネットワーク拡張機能</span><span class="sxs-lookup"><span data-stu-id="3b6d2-407">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="3b6d2-408">**説明**: macOS 10.15 (Catalina) 以降</span><span class="sxs-lookup"><span data-stu-id="3b6d2-408">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="3b6d2-409">**カテゴリ**: なし *(既定)*</span><span class="sxs-lookup"><span data-stu-id="3b6d2-409">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="3b6d2-410">**配布方法**: 自動的にインストール *する (既定)*</span><span class="sxs-lookup"><span data-stu-id="3b6d2-410">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="3b6d2-411">**レベル**: コンピューター レベル *(既定)*</span><span class="sxs-lookup"><span data-stu-id="3b6d2-411">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="3b6d2-412">タブ **コンテンツ フィルター**:</span><span class="sxs-lookup"><span data-stu-id="3b6d2-412">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="3b6d2-413">**フィルター名**: Microsoft Defender ATP コンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="3b6d2-413">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="3b6d2-414">**識別子**: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-414">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="3b6d2-415">サービス **アドレス 、\*\*\*\*組織、\*\*\*\*ユーザー名、** パスワード、**証明書** を空白のままにする **(Include** *は* 選択されません) </span><span class="sxs-lookup"><span data-stu-id="3b6d2-415">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="3b6d2-416">**フィルターの順序**: Inspector</span><span class="sxs-lookup"><span data-stu-id="3b6d2-416">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="3b6d2-417">**ソケット フィルター**: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-417">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="3b6d2-418">**ソケット フィルターの指定要件**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3b6d2-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="3b6d2-419">[ **ネットワーク フィルター] フィールド** を空白のままにします **([含** める *] は* 選択されません)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-419">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="3b6d2-420">識別子、 **ソケット フィルター** **、ソケット フィルター** の指定 **された** 要件の正確な値は、上記で指定したとおりです。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-420">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![構成設定 mdatpmdav のイメージ](images/netext-create-profile.png)

3. <span data-ttu-id="3b6d2-422">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-422">Select the **Scope** tab.</span></span>

   ![[構成設定] [sco] タブのイメージ](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="3b6d2-424">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-424">Select **+ Add**.</span></span>

5. <span data-ttu-id="3b6d2-425">[ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-425">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="3b6d2-426">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-426">Select **+ Add**.</span></span>

    ![構成設定 adim のイメージ](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="3b6d2-428">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-428">Select **Save**.</span></span>

    ![構成設定のイメージ savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="3b6d2-430">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-430">Select **Done**.</span></span>

    ![構成設定 netextfinal のイメージ](images/netext-final.png)

<span data-ttu-id="3b6d2-432">または、「Jamf Pro を使用したカスタム構成プロファイルの展開」の説明に従って [、netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) をダウンロードして JAMF 構成プロファイル [にアップロードできます|方法 2: Jamf Pro に構成プロファイルをアップロードします](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-432">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3b6d2-433">手順 10: macOS で Microsoft Defender for Endpoint でスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="3b6d2-433">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="3b6d2-434">macOS の Microsoft Defender for Endpoint でスキャンをスケジュール [するの手順に従います](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-434">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3b6d2-435">手順 11: macOS に Microsoft Defender for Endpoint を展開する</span><span class="sxs-lookup"><span data-stu-id="3b6d2-435">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="3b6d2-436">保存した場所に移動します `wdav.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-436">Navigate to where you saved `wdav.pkg`.</span></span>

    ![エクスプローラー wdav pkg のイメージ](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="3b6d2-438">に名前を変更します `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-438">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![エクスプローラー 1 wdavmdmpkg のイメージ](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="3b6d2-440">Jamf Pro ダッシュボードを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-440">Open the Jamf Pro dashboard.</span></span>

    ![構成設定 jamfpro のイメージ](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="3b6d2-442">コンピューターを選択し、上部の歯車アイコンをクリックし、[コンピューターの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-442">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![構成設定 compmgmt のイメージ](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="3b6d2-444">[パッケージ **] で**、[+ **新規] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-444">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="3b6d2-445">![Bird Description が自動的に生成されたパッケージ new を含む図](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-445">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="3b6d2-446">[ **新しいパッケージ]** で、次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-446">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="3b6d2-447">**[全般] タブ**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-447">**General tab**</span></span>
    - <span data-ttu-id="3b6d2-448">表示名: 空白のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-448">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="3b6d2-449">pkg を選択するとリセットされます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-449">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="3b6d2-450">カテゴリ: なし (既定)</span><span class="sxs-lookup"><span data-stu-id="3b6d2-450">Category: None (default)</span></span>
    - <span data-ttu-id="3b6d2-451">ファイル名: [ファイル] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-451">Filename: Choose File</span></span>

    ![[構成設定のイメージ] [全般] タブ](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="3b6d2-453">ファイルを開き、またはをポイント `wdav.pkg` します `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-453">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![コンピューター画面のスクリーンショット 説明が自動的に生成される](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="3b6d2-455">[**開く**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-455">Select **Open**.</span></span> <span data-ttu-id="3b6d2-456">[表示名 **] を** **[Microsoft Defender Advanced Threat Protection] および [Microsoft Defender ウイルス対策] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-456">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="3b6d2-457">**マニフェスト ファイル** は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-457">**Manifest File** is not required.</span></span> <span data-ttu-id="3b6d2-458">Microsoft Defender Advanced Threat Protection はマニフェスト ファイルなしで動作します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-458">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="3b6d2-459">**オプション タブ**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-459">**Options tab**</span></span><br> <span data-ttu-id="3b6d2-460">既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-460">Keep default values.</span></span>

    <span data-ttu-id="3b6d2-461">**[制限] タブ**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-461">**Limitations tab**</span></span><br> <span data-ttu-id="3b6d2-462">既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-462">Keep default values.</span></span>
    
     ![[構成設定の制限] タブのイメージ](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="3b6d2-464">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-464">Select **Save**.</span></span> <span data-ttu-id="3b6d2-465">パッケージは Jamf Pro にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-465">The package is uploaded to Jamf Pro.</span></span> 

   ![構成設定パック upl jamf pro のイメージ](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="3b6d2-467">パッケージを展開に使用するには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-467">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![構成設定パック upl のイメージ](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="3b6d2-469">[ポリシー] **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-469">Navigate to the **Policies** page.</span></span>

    ![構成設定のポロのイメージ](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="3b6d2-471">[+ **新規] を** 選択して新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-471">Select **+ New** to create a new policy.</span></span>

    ![構成設定の新しいポリシーのイメージ](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="3b6d2-473">[ **全般]** 次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-473">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="3b6d2-474">表示名: MDATP Onboarding Contoso 200329 v100.86.92 以降</span><span class="sxs-lookup"><span data-stu-id="3b6d2-474">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="3b6d2-475">構成設定のイメージmdatponboard</span><span class="sxs-lookup"><span data-stu-id="3b6d2-475">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="3b6d2-476">[ **定期的なチェックイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-476">Select **Recurring Check-in**.</span></span> 
    
    ![構成設定の再チェック インのイメージ](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="3b6d2-478">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-478">Select **Save**.</span></span> 
 
14. <span data-ttu-id="3b6d2-479">[パッケージ **] を選択>構成します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-479">Select **Packages > Configure**.</span></span>
 
    ![構成設定パック構成のイメージ](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="3b6d2-481">[Microsoft **Defender Advanced Threat** Protection] と [Microsoft Defender ウイルス対策] の横にある **[追加] ボタンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-481">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![構成設定 MDATP と MDA の追加のイメージ](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="3b6d2-483">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-483">Select **Save**.</span></span>

    ![構成設定のイメージsavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="3b6d2-485">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-485">Select the **Scope** tab.</span></span>  

    ![構成設定 scptab のイメージ](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="3b6d2-487">ターゲット コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-487">Select the target computers.</span></span>

    ![構成設定 tgtcomp のイメージ](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="3b6d2-489">**Scope**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-489">**Scope**</span></span>
    
    <span data-ttu-id="3b6d2-490">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-490">Select **Add**.</span></span>
    
    ![構成設定 ad1img のイメージ](images/1c08d097829863778d562c10c5f92b67.png)

    ![構成設定 ad2img のイメージ](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="3b6d2-493">**セルフサービス**</span><span class="sxs-lookup"><span data-stu-id="3b6d2-493">**Self-Service**</span></span>
    
    ![構成設定セルフサービスのイメージ](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="3b6d2-495">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b6d2-495">Select **Done**.</span></span> 

    ![構成設定 do1img のイメージ](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![構成設定 do2img のイメージ](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




