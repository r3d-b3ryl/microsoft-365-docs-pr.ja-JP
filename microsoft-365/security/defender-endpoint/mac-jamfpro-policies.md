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
ms.openlocfilehash: 1559d8dca6b6909f22473c5a8f4d25d4bac501d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062252"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a><span data-ttu-id="25294-104">Jamf Pro で macOS 用 Microsoft Defender for Endpoint ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="25294-104">Set up the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25294-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="25294-105">**Applies to:**</span></span>

- [<span data-ttu-id="25294-106">Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="25294-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="25294-107">このページでは、Jamf Pro で macOS ポリシーを設定するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="25294-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="25294-108">次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25294-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="25294-109">Microsoft Defender for Endpoint オンボーディング パッケージの取得</span><span class="sxs-lookup"><span data-stu-id="25294-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="25294-110">オンボーディング パッケージを使用して Jamf Pro で構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="25294-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="25294-111">エンドポイントの Microsoft Defender の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="25294-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="25294-112">Microsoft Defender for Endpoint 通知の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="25294-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="25294-113">Microsoft AutoUpdate (MAU) の構成</span><span class="sxs-lookup"><span data-stu-id="25294-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="25294-114">Microsoft Defender for Endpoint へのフル ディスク アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="25294-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="25294-115">Microsoft Defender for Endpoint のカーネル拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="25294-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="25294-116">エンドポイント用 Microsoft Defender のシステム拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="25294-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="25294-117">ネットワーク拡張機能の構成</span><span class="sxs-lookup"><span data-stu-id="25294-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="25294-118">Microsoft Defender for Endpoint for Mac でのスキャンのスケジュール設定</span><span class="sxs-lookup"><span data-stu-id="25294-118">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="25294-119">Microsoft Defender for Endpoint for macOS の展開</span><span class="sxs-lookup"><span data-stu-id="25294-119">Deploy Microsoft Defender for Endpoint for macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="25294-120">手順 1: Microsoft Defender for Endpoint オンボーディング パッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="25294-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="25294-121">[Microsoft Defender セキュリティ センターで、[](https://securitycenter.microsoft.com )オンボーディングの **設定] >移動します**。</span><span class="sxs-lookup"><span data-stu-id="25294-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="25294-122">展開方法として、オペレーティング システムとして macOS、モバイル デバイス管理 / Microsoft Intune を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Microsoft Defender セキュリティ センターのイメージ](images/onboarding-macos.png)

3. <span data-ttu-id="25294-124">[ **オンボード パッケージのダウンロード] (WindowsDefenderATPOnboardingPackage.zip)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="25294-125">抽出 `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="25294-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="25294-126">ファイルを好みの場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="25294-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="25294-127">例: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。</span><span class="sxs-lookup"><span data-stu-id="25294-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="25294-128">手順 2: オンボード パッケージを使用して Jamf Pro で構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="25294-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="25294-129">前のセクション `WindowsDefenderATPOnboarding.plist` からファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="25294-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![WindowsDefenderATPOnboarding ファイルのイメージ](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="25294-131">Jamf Pro ダッシュボードで、[新規] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![新しい Jamf Pro ダッシュボードの作成イメージ](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="25294-133">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-133">Enter the following details:</span></span>

   <span data-ttu-id="25294-134">**全般**</span><span class="sxs-lookup"><span data-stu-id="25294-134">**General**</span></span>
   - <span data-ttu-id="25294-135">名前: macOS の MDATP オンボーディング</span><span class="sxs-lookup"><span data-stu-id="25294-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="25294-136">説明: mDATP EDR オンボーディング for macOS</span><span class="sxs-lookup"><span data-stu-id="25294-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="25294-137">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="25294-137">Category: None</span></span>
   - <span data-ttu-id="25294-138">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="25294-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="25294-139">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="25294-139">Level: Computer Level</span></span>

4. <span data-ttu-id="25294-140">[**アプリケーションの設定] &[構成] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![アプリの構成とカスタム設定のイメージ](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="25294-142">[ファイル **のアップロード (PLIST ファイル) を選択し、[基本設定ドメイン]** **に次を** 入力します `com.microsoft.wdav.atp` 。</span><span class="sxs-lookup"><span data-stu-id="25294-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![jamfpro plist アップロード ファイルのイメージ](images/jamfpro-plist-upload.png)

    ![アップロード ファイル プロパティリスト ファイルのイメージ](images/jamfpro-plist-file.png)

7. <span data-ttu-id="25294-145">[開 **く] を** 選択し、オンボーディング ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-145">Select **Open** and select the onboarding file.</span></span>

    ![オンボード ファイルのイメージ](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="25294-147">[アップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-147">Select **Upload**.</span></span> 

    ![plist ファイルのアップロードのイメージ](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="25294-149">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-149">Select the **Scope** tab.</span></span>

    ![[スコープのイメージ] タブ](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="25294-151">ターゲット コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-151">Select the target computers.</span></span>

    ![ターゲット コンピューターのイメージ](images/jamfpro-target-computer.png)

    ![ターゲットのイメージ](images/jamfpro-targets.png) 

11. <span data-ttu-id="25294-154">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-154">Select **Save**.</span></span>

    ![展開ターゲット コンピューターのイメージ](images/jamfpro-deployment-target.png)

    ![選択したターゲット コンピューターのイメージ](images/jamfpro-target-selected.png)

12. <span data-ttu-id="25294-157">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-157">Select **Done**.</span></span>

    ![ターゲット グループ コンピューターのイメージ](images/jamfpro-target-group.png)

    ![構成プロファイルの一覧](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="25294-160">手順 3: エンドポイントの Microsoft Defender の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="25294-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="25294-161">次の Microsoft Defender for Endpoint 構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="25294-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="25294-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="25294-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="25294-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="25294-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="25294-164">既定ではオンにされません。macOS 用にサードパーティの AV を実行する予定の場合は、 に設定します `true` 。</span><span class="sxs-lookup"><span data-stu-id="25294-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="25294-165">除外</span><span class="sxs-lookup"><span data-stu-id="25294-165">exclusions</span></span>
    - <span data-ttu-id="25294-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="25294-166">excludedPath</span></span>
    - <span data-ttu-id="25294-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="25294-167">excludedFileExtension</span></span>
    - <span data-ttu-id="25294-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="25294-168">excludedFileName</span></span>
    - <span data-ttu-id="25294-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="25294-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="25294-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="25294-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="25294-171">EICAR はサンプルに含め、概念実証を行う場合は、EICAR をテストする場合は特に削除してください。</span><span class="sxs-lookup"><span data-stu-id="25294-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="25294-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="25294-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="25294-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="25294-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="25294-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="25294-174">archive_bomb</span></span>
    - <span data-ttu-id="25294-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="25294-175">cloudService</span></span>
    - <span data-ttu-id="25294-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="25294-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="25294-177">tags</span><span class="sxs-lookup"><span data-stu-id="25294-177">tags</span></span>
    - <span data-ttu-id="25294-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="25294-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="25294-179">詳細については [、「Jamf 構成プロファイルのプロパティ 一覧」を参照してください](mac-preferences.md#property-list-for-jamf-configuration-profile)。</span><span class="sxs-lookup"><span data-stu-id="25294-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="25294-180">ファイルをとして保存します `MDATP_MDAV_configuration_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="25294-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="25294-181">Jamf Pro ダッシュボードで、[全般] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![新しい Jamf Pro ダッシュボードのイメージ](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="25294-183">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-183">Enter the following details:</span></span>

    <span data-ttu-id="25294-184">**全般**</span><span class="sxs-lookup"><span data-stu-id="25294-184">**General**</span></span>
    
    - <span data-ttu-id="25294-185">名前: MDATP MDAV 構成設定</span><span class="sxs-lookup"><span data-stu-id="25294-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="25294-186">説明:\<blank\></span><span class="sxs-lookup"><span data-stu-id="25294-186">Description:\<blank\></span></span>
    - <span data-ttu-id="25294-187">カテゴリ: なし (既定)</span><span class="sxs-lookup"><span data-stu-id="25294-187">Category: None (default)</span></span>
    - <span data-ttu-id="25294-188">配布方法: 自動インストール(既定)</span><span class="sxs-lookup"><span data-stu-id="25294-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="25294-189">Level: Computer Level(default)</span><span class="sxs-lookup"><span data-stu-id="25294-189">Level: Computer Level(default)</span></span>

    ![MDATP MDAV 構成設定のイメージ](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="25294-191">[**アプリケーションの設定] &[構成] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![アプリとカスタム設定のイメージ](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="25294-193">[ファイル **のアップロード] (PLIST ファイル) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-193">Select **Upload File (PLIST file)**.</span></span>

    ![構成設定 plist ファイルのイメージ](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="25294-195">[ **基本設定ドメイン] で、「PLIST** `com.microsoft.wdav` ファイルのアップロード  **」と入力し、[アップロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![構成設定の基本設定ドメインのイメージ](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="25294-197">[ファイル **の選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-197">Select **Choose File**.</span></span>

    ![構成設定のイメージファイルを選択する](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="25294-199">**[MDATP_MDAV_configuration_settings.plist] を選択し、[** 開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![mdatpmdav 構成設定のイメージ](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="25294-201">[アップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-201">Select **Upload**.</span></span>

    ![構成設定のアップロードのイメージ](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![構成設定のアップロード イメージのイメージ](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="25294-204">Intune ファイルをアップロードすると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="25294-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="25294-205">![構成設定 intune ファイルのアップロードのイメージ](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="25294-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="25294-206">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-206">Select **Save**.</span></span> 

    ![構成設定のイメージ 画像を保存する](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="25294-208">ファイルがアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="25294-208">The file is uploaded.</span></span>

    ![構成設定ファイルアップロード画像の画像](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![アップロードされた構成設定ファイルのイメージ](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="25294-211">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-211">Select the **Scope** tab.</span></span>

    ![構成設定スコープのイメージ](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="25294-213">**[Contoso's Machine Group] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="25294-214">[追加 **] を** 選択し、[保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-214">Select **Add**, then select **Save**.</span></span>

    ![構成設定のイメージを追加する](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![構成設定の保存のイメージの追加](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="25294-217">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-217">Select **Done**.</span></span> <span data-ttu-id="25294-218">新しい構成プロファイルが **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="25294-218">You'll see the new **Configuration profile**.</span></span>

    ![構成設定の構成プロファイル イメージのイメージ](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="25294-220">手順 4: 通知の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="25294-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="25294-221">これらの手順は、macOS 10.15 (Catalina) 以降に適用できます。</span><span class="sxs-lookup"><span data-stu-id="25294-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="25294-222">`notif.mobileconfig` [GitHub リポジトリからダウンロードする](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span><span class="sxs-lookup"><span data-stu-id="25294-222">Download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span></span>

2. <span data-ttu-id="25294-223">として保存します `MDATP_MDAV_notification_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="25294-223">Save it as `MDATP_MDAV_notification_settings.plist`.</span></span>

3. <span data-ttu-id="25294-224">Jamf Pro ダッシュボードで、[全般] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-224">In the Jamf Pro dashboard, select **General**.</span></span> 
       
4. <span data-ttu-id="25294-225">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-225">Enter the following details:</span></span>

    <span data-ttu-id="25294-226">**全般**</span><span class="sxs-lookup"><span data-stu-id="25294-226">**General**</span></span> 
    
    - <span data-ttu-id="25294-227">名前: MDATP MDAV 通知の設定</span><span class="sxs-lookup"><span data-stu-id="25294-227">Name: MDATP MDAV Notification settings</span></span>
    - <span data-ttu-id="25294-228">説明: macOS 10.15 (Catalina) 以降</span><span class="sxs-lookup"><span data-stu-id="25294-228">Description: macOS 10.15 (Catalina) or newer</span></span>
    - <span data-ttu-id="25294-229">カテゴリ: なし (既定)</span><span class="sxs-lookup"><span data-stu-id="25294-229">Category: None (default)</span></span>
    - <span data-ttu-id="25294-230">配布方法: 自動インストール(既定)</span><span class="sxs-lookup"><span data-stu-id="25294-230">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="25294-231">Level: Computer Level(default)</span><span class="sxs-lookup"><span data-stu-id="25294-231">Level: Computer Level(default)</span></span>

    ![構成設定 mdatpmdav のイメージ](images/c9820a5ff84aaf21635c04a23a97ca93.png)


5. <span data-ttu-id="25294-233">[ファイル **のアップロード] (PLIST ファイル) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-233">Select **Upload File (PLIST file)**.</span></span>

    ![構成設定アップロード plistfile のイメージ](images/7f9138053dbcbf928e5182ee7b295ebe.png)
 

6. <span data-ttu-id="25294-235">[**ファイルの選択]**  >  **MDATP_MDAV_Notification_Settings.plist を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-235">Select **Choose File** > **MDATP_MDAV_Notification_Settings.plist**.</span></span>


    ![構成設定 mdatpmdav notsettings のイメージ](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)


    ![構成設定 mdatpmdav notifsettings のイメージ](images/20e33b98eb54447881dc6c89e58b890f.png)

7. <span data-ttu-id="25294-238">[アップロード **を開く]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-238">Select **Open** > **Upload**.</span></span>

    ![構成設定 upl img のイメージ](images/7697c33b9fd376ae5a8023d01f9d3857.png)


    ![構成設定 upl イメージのイメージ](images/2bda9244ec25d1526811da4ea91b1c86.png)

8. <span data-ttu-id="25294-241">[スコープ] **タブを選択** し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-241">Select the **Scope** tab, then select **Add**.</span></span>

    ![構成設定スコープの追加のイメージ](images/441aa2ecd36abadcdd8aed03556080b5.png)


9. <span data-ttu-id="25294-243">**[Contoso's Machine Group] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-243">Select **Contoso's Machine Group**.</span></span> 

10. <span data-ttu-id="25294-244">[追加 **] を** 選択し、[保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-244">Select **Add**, then select **Save**.</span></span>
    
    ![構成設定 contoso machine grp save のイメージ](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    
    ![構成設定のイメージの保存の追加](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

11. <span data-ttu-id="25294-247">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-247">Select **Done**.</span></span> <span data-ttu-id="25294-248">新しい構成プロファイルが **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="25294-248">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="25294-249">![構成設定完了 img のイメージ](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="25294-249">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="25294-250">手順 5: Microsoft AutoUpdate (MAU) を構成する</span><span class="sxs-lookup"><span data-stu-id="25294-250">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="25294-251">次の Microsoft Defender for Endpoint 構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="25294-251">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="25294-252">として保存します `MDATP_MDAV_MAU_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="25294-252">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="25294-253">Jamf Pro ダッシュボードで、[全般] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-253">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![構成設定の一般的なイメージのイメージ](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="25294-255">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-255">Enter the following details:</span></span>

    <span data-ttu-id="25294-256">**全般**</span><span class="sxs-lookup"><span data-stu-id="25294-256">**General**</span></span> 
    
    - <span data-ttu-id="25294-257">名前: MDATP MDAV MAU の設定</span><span class="sxs-lookup"><span data-stu-id="25294-257">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="25294-258">説明: MacOS 用 MDATP の Microsoft AutoUpdate 設定</span><span class="sxs-lookup"><span data-stu-id="25294-258">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="25294-259">カテゴリ: なし (既定)</span><span class="sxs-lookup"><span data-stu-id="25294-259">Category: None (default)</span></span>
    - <span data-ttu-id="25294-260">配布方法: 自動インストール(既定)</span><span class="sxs-lookup"><span data-stu-id="25294-260">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="25294-261">Level: Computer Level(default)</span><span class="sxs-lookup"><span data-stu-id="25294-261">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="25294-262">[**アプリケーションの設定] &[構成] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-262">In **Application & Custom Settings** select **Configure**.</span></span>

    ![構成設定アプリとカスタム設定のイメージ](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="25294-264">[ファイル **のアップロード] (PLIST ファイル) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-264">Select **Upload File (PLIST file)**.</span></span>

    ![構成設定 plist のイメージ](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="25294-266">[基本 **設定ドメイン]** に「:」 `com.microsoft.autoupdate2` と入力し **、[PLIST ファイルのアップロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-266">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![構成設定のプリフェッチ ドメインのイメージ](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="25294-268">[ファイル **の選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-268">Select **Choose File**.</span></span>

    ![構成設定の選択ファイルのイメージ](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="25294-270">**[MDATP_MDAV_MAU_settings.plist] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-270">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![構成設定 mdatpmdavmau 設定のイメージ](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="25294-272">[アップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-272">Select **Upload**.</span></span>
    <span data-ttu-id="25294-273">![構成設定 uplimage のイメージ](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="25294-273">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![構成設定 uplimg のイメージ](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="25294-275">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-275">Select **Save**.</span></span>

    ![構成設定 saveimg のイメージ](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="25294-277">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-277">Select the **Scope** tab.</span></span>
   
     ![構成設定 scopetab のイメージ](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="25294-279">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-279">Select **Add**.</span></span>
    
    ![構成設定 addimg1 のイメージ](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![構成設定 addimg2 のイメージ](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![構成設定 addimg3 のイメージ](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="25294-283">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-283">Select **Done**.</span></span>
    
    ![構成設定 doneimage のイメージ](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="25294-285">手順 6: エンドポイント用 Microsoft Defender へのフル ディスク アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="25294-285">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="25294-286">Jamf Pro ダッシュボードで、[構成プロファイル **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-286">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![構成設定構成プロファイルのイメージ](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="25294-288">[+ **新規] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-288">Select **+ New**.</span></span> 

3. <span data-ttu-id="25294-289">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-289">Enter the following details:</span></span>

    <span data-ttu-id="25294-290">**全般**</span><span class="sxs-lookup"><span data-stu-id="25294-290">**General**</span></span> 
    - <span data-ttu-id="25294-291">名前: MDATP MDAV - EDR および AV へのフル ディスク アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="25294-291">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="25294-292">説明: macOS Catalina 以降では、新しいプライバシー設定ポリシーコントロール</span><span class="sxs-lookup"><span data-stu-id="25294-292">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="25294-293">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="25294-293">Category: None</span></span>
    - <span data-ttu-id="25294-294">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="25294-294">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="25294-295">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="25294-295">Level: Computer level</span></span>


    ![構成設定全般のイメージ](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="25294-297">[ **プライバシー設定の構成] ポリシーコントロールで、[構成** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-297">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![構成のプライバシー ポリシー制御のイメージ](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="25294-299">[ **プライバシー設定ポリシー制御] で、** 次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-299">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="25294-300">識別子: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="25294-300">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="25294-301">識別子の種類: バンドル ID</span><span class="sxs-lookup"><span data-stu-id="25294-301">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="25294-302">コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="25294-302">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![構成設定のプライバシー設定ポリシー制御の詳細のイメージ](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="25294-304">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-304">Select **+ Add**.</span></span>

    ![構成設定のイメージ システム ポリシーのすべてのファイルを追加する](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="25294-306">[アプリまたはサービス] で **、SystemPolicyAllFiles に設定する**</span><span class="sxs-lookup"><span data-stu-id="25294-306">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="25294-307">[アクセス] の下: [許可] に **設定します。**</span><span class="sxs-lookup"><span data-stu-id="25294-307">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="25294-308">[ **保存]** を選択します (右下の保存は選択しない)。</span><span class="sxs-lookup"><span data-stu-id="25294-308">Select **Save** (not the one at the bottom right).</span></span>

    ![構成設定の保存イメージのイメージ](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="25294-310">[アプリ アクセス `+` ] の横にある **記号をクリックして** 、新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="25294-310">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![構成設定アプリアクセスのイメージ](images/tcc-add-entry.png)

9. <span data-ttu-id="25294-312">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-312">Enter the following details:</span></span>

    - <span data-ttu-id="25294-313">識別子: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="25294-313">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="25294-314">識別子の種類: バンドル ID</span><span class="sxs-lookup"><span data-stu-id="25294-314">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="25294-315">コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="25294-315">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="25294-316">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-316">Select **+ Add**.</span></span>

    ![構成設定 tcc epsext エントリのイメージ](images/tcc-epsext-entry.png)

    - <span data-ttu-id="25294-318">[アプリまたはサービス] で **、SystemPolicyAllFiles に設定する**</span><span class="sxs-lookup"><span data-stu-id="25294-318">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="25294-319">[アクセス] の下: [許可] に **設定します。**</span><span class="sxs-lookup"><span data-stu-id="25294-319">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="25294-320">[ **保存]** を選択します (右下の保存は選択しない)。</span><span class="sxs-lookup"><span data-stu-id="25294-320">Select **Save** (not the one at the bottom right).</span></span>

    ![構成設定 tcc epsext image2 のイメージ](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="25294-322">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-322">Select the **Scope** tab.</span></span>

    ![構成設定スコープのイメージ](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="25294-324">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-324">Select **+ Add**.</span></span>

    ![構成設定のイメージ addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="25294-326">[ **グループ名]** > [コンピューター グループ] **を** 選択> **Contoso の MachineGroup を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-326">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![構成設定 contoso machinegrp のイメージ](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="25294-328">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-328">Select **Add**.</span></span> 

16. <span data-ttu-id="25294-329">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-329">Select **Save**.</span></span> 
    
17. <span data-ttu-id="25294-330">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-330">Select **Done**.</span></span>
    
    ![構成設定 donimg のイメージ](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![構成設定 donimg2 のイメージ](images/6c8b406ee224335a8c65d06953dc756e.png)


## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="25294-333">手順 7: Microsoft Defender for Endpoint のカーネル拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="25294-333">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="25294-334">[構成プロファイル **] で、[+** 新規 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-334">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自動的に生成されたソーシャル メディア投稿の説明のスクリーンショット](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="25294-336">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-336">Enter the following details:</span></span>

    <span data-ttu-id="25294-337">**全般**</span><span class="sxs-lookup"><span data-stu-id="25294-337">**General**</span></span> 
    
    - <span data-ttu-id="25294-338">名前: MDATP MDAV カーネル拡張機能</span><span class="sxs-lookup"><span data-stu-id="25294-338">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="25294-339">説明: MDATP カーネル拡張機能 (kext)</span><span class="sxs-lookup"><span data-stu-id="25294-339">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="25294-340">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="25294-340">Category: None</span></span>
    - <span data-ttu-id="25294-341">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="25294-341">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="25294-342">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="25294-342">Level: Computer Level</span></span>

    ![構成設定 mdatpmdav カーネルのイメージ](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="25294-344">[承認済 **みカーネル拡張機能の構成] で、[構成** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-344">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![構成設定承認済みカーネル ext のイメージ](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="25294-346">[ **承認済みカーネル拡張機能]** で、次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-346">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="25294-347">表示名: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="25294-347">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="25294-348">チーム ID: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="25294-348">Team ID: UBF8T346G9</span></span>

    ![構成設定 appr カーネル拡張機能のイメージ](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="25294-350">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-350">Select the **Scope** tab.</span></span>

    ![構成設定スコープ タブ img のイメージ](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="25294-352">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-352">Select **+ Add**.</span></span>

7. <span data-ttu-id="25294-353">[ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-353">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="25294-354">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-354">Select **+ Add**.</span></span>

    ![構成設定のイメージにイメージを追加する](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="25294-356">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-356">Select **Save**.</span></span>

    ![構成設定の saveimag のイメージ](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="25294-358">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-358">Select **Done**.</span></span>

    ![doneimag の構成設定のイメージ](images/1c9bd3f68db20b80193dac18f33c22d0.png)


## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="25294-360">手順 8: エンドポイント用 Microsoft Defender のシステム拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="25294-360">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="25294-361">[構成プロファイル **] で、[+** 新規 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-361">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自動的に生成されたソーシャル メディア投稿の説明のスクリーンショット](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="25294-363">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-363">Enter the following details:</span></span>

    <span data-ttu-id="25294-364">**全般**</span><span class="sxs-lookup"><span data-stu-id="25294-364">**General**</span></span>
    
    - <span data-ttu-id="25294-365">名前: MDATP MDAV システム拡張機能</span><span class="sxs-lookup"><span data-stu-id="25294-365">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="25294-366">説明: MDATP システム拡張機能</span><span class="sxs-lookup"><span data-stu-id="25294-366">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="25294-367">カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="25294-367">Category: None</span></span>
    - <span data-ttu-id="25294-368">配布方法: 自動的にインストールする</span><span class="sxs-lookup"><span data-stu-id="25294-368">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="25294-369">レベル: コンピューター レベル</span><span class="sxs-lookup"><span data-stu-id="25294-369">Level: Computer Level</span></span>

    ![構成設定 sysext new prof のイメージ](images/sysext-new-profile.png)

3. <span data-ttu-id="25294-371">[ **システム拡張機能] で、[構成** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-371">In **System Extensions** select **Configure**.</span></span>

   ![構成設定 sysext config のイメージ](images/sysext-configure.png)

4. <span data-ttu-id="25294-373">[System **Extensions] に次** の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-373">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="25294-374">表示名: Microsoft Corp. System Extensions</span><span class="sxs-lookup"><span data-stu-id="25294-374">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="25294-375">システム拡張の種類: 許可されているシステム拡張機能</span><span class="sxs-lookup"><span data-stu-id="25294-375">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="25294-376">チーム識別子: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="25294-376">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="25294-377">許可されるシステム拡張機能:</span><span class="sxs-lookup"><span data-stu-id="25294-377">Allowed System Extensions:</span></span>
     - <span data-ttu-id="25294-378">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="25294-378">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="25294-379">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="25294-379">**com.microsoft.wdav.netext**</span></span>

    ![構成設定 sysextconfig2 のイメージ](images/sysext-configure2.png)

5. <span data-ttu-id="25294-381">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-381">Select the **Scope** tab.</span></span>

    ![構成設定 scopeimage のイメージ](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="25294-383">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-383">Select **+ Add**.</span></span>

7. <span data-ttu-id="25294-384">[ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-384">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="25294-385">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-385">Select **+ Add**.</span></span>

   ![構成設定 addima のイメージ](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="25294-387">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-387">Select **Save**.</span></span>

   ![構成設定 sysext スコープのイメージ](images/sysext-scope.png)

10. <span data-ttu-id="25294-389">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-389">Select **Done**.</span></span>

    ![構成設定 sysext-final のイメージ](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="25294-391">手順 9: ネットワーク拡張機能を構成する</span><span class="sxs-lookup"><span data-stu-id="25294-391">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="25294-392">エンドポイント検出と応答機能の一環として、Microsoft Defender for Endpoint for Mac はソケット トラフィックを検査し、この情報を Microsoft Defender セキュリティ センター ポータルに報告します。</span><span class="sxs-lookup"><span data-stu-id="25294-392">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="25294-393">次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="25294-393">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="25294-394">JAMF にはコンテンツ フィルター ポリシーの組み込みのサポートが用意されていません。これは、Microsoft Defender for Endpoint for Mac がデバイスにインストールするネットワーク拡張機能を有効にするための前提条件です。</span><span class="sxs-lookup"><span data-stu-id="25294-394">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint for Mac installs on the device.</span></span> <span data-ttu-id="25294-395">さらに、JAMF は展開するポリシーの内容を変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="25294-395">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="25294-396">そのため、次の手順では、構成プロファイルに署名する回避策を提供します。</span><span class="sxs-lookup"><span data-stu-id="25294-396">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="25294-397">`netfilter.mobileconfig` [GitHub リポジトリからデバイスにダウンロード](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)し、次のように保存します。`com.microsoft.network-extension.mobileconfig`</span><span class="sxs-lookup"><span data-stu-id="25294-397">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) to your device and save it as `com.microsoft.network-extension.mobileconfig`</span></span>

2. <span data-ttu-id="25294-398">JAMF の組 [み込](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) みの証明機関を使用して署名証明書を作成するには、このページの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="25294-398">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority</span></span>

3. <span data-ttu-id="25294-399">証明書を作成してデバイスにインストールしたら、macOS デバイスからターミナルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25294-399">After the certificate is created and installed to your device, run the following command from the Terminal from a macOS device:</span></span>

   ```bash
   $ security cms -S -N "<certificate name>" -i com.microsoft.network-extension.mobileconfig -o com.microsoft.network-extension.signed.mobileconfig
   ```

   ![署名済み構成を作成するコマンドを含むターミナル ウィンドウ](images/netext-create-profile.png)

4. <span data-ttu-id="25294-401">JAMF ポータルから [構成プロファイル] に移動 **し、[** アップロード] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="25294-401">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> 

   ![アップロード ウィンドウのイメージ](images/netext-upload-file.png)

5. <span data-ttu-id="25294-403">[ファイル **の選択] を選択** し、 を選択します `microsoft.network-extension.signed.mobileconfig` 。</span><span class="sxs-lookup"><span data-stu-id="25294-403">Select **Choose File** and select `microsoft.network-extension.signed.mobileconfig`.</span></span>

   ![アップロード ウィンドウのイメージ netext choose file](images/netext-choose-file.png)

6. <span data-ttu-id="25294-405">[アップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-405">Select **Upload**.</span></span>

   ![アップロード ウィンドウ netext アップロード ファイル 2 の画像](images/netext-upload-file2.png)

7. <span data-ttu-id="25294-407">ファイルをアップロードすると、新しいページにリダイレクトされ、このプロファイルの作成が完了します。</span><span class="sxs-lookup"><span data-stu-id="25294-407">After uploading the file, you are redirected to a new page to finalize the creation of this profile.</span></span>

   ![新しい構成プロファイル netext プロファイル ページのイメージ](images/netext-profile-page.png)

8. <span data-ttu-id="25294-409">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-409">Select the **Scope** tab.</span></span>

   ![[構成設定] [sco] タブのイメージ](images/0df36fc308ba569db204ee32db3fb40a.png)

9. <span data-ttu-id="25294-411">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-411">Select **+ Add**.</span></span>

10. <span data-ttu-id="25294-412">[ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-412">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

11. <span data-ttu-id="25294-413">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-413">Select **+ Add**.</span></span>

    ![構成設定 adim のイメージ](images/0dde8a4c41110dbc398c485433a81359.png)

12. <span data-ttu-id="25294-415">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-415">Select **Save**.</span></span>

    ![構成設定のイメージ savimg netextscop](images/netext-scope.png)

13. <span data-ttu-id="25294-417">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-417">Select **Done**.</span></span>

    ![構成設定 netextfinal のイメージ](images/netext-final.png)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="25294-419">手順 10: Microsoft Defender for Endpoint for Mac でスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="25294-419">Step 10: Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>
<span data-ttu-id="25294-420">「Microsoft Defender [for Endpoint for Mac でスキャンをスケジュールする」の手順に従います](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。</span><span class="sxs-lookup"><span data-stu-id="25294-420">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="25294-421">手順 11: Microsoft Defender for Endpoint for macOS を展開する</span><span class="sxs-lookup"><span data-stu-id="25294-421">Step 11: Deploy Microsoft Defender for Endpoint for macOS</span></span>

1. <span data-ttu-id="25294-422">保存した場所に移動します `wdav.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="25294-422">Navigate to where you saved `wdav.pkg`.</span></span>

    ![エクスプローラー wdav pkg のイメージ](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="25294-424">に名前を変更します `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="25294-424">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![エクスプローラー 1 wdavmdmpkg のイメージ](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="25294-426">Jamf Pro ダッシュボードを開きます。</span><span class="sxs-lookup"><span data-stu-id="25294-426">Open the Jamf Pro dashboard.</span></span>

    ![構成設定 jamfpro のイメージ](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="25294-428">コンピューターを選択し、上部の歯車アイコンをクリックし、[コンピューターの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-428">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![構成設定 compmgmt のイメージ](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="25294-430">[パッケージ **] で**、[+ **新規] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-430">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="25294-431">![Bird Description が自動的に生成されたパッケージ new を含む図](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="25294-431">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="25294-432">[ **新しいパッケージ]** で、次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-432">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="25294-433">**[全般] タブ**</span><span class="sxs-lookup"><span data-stu-id="25294-433">**General tab**</span></span>
    - <span data-ttu-id="25294-434">表示名: 空白のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="25294-434">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="25294-435">pkg を選択するとリセットされます。</span><span class="sxs-lookup"><span data-stu-id="25294-435">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="25294-436">カテゴリ: なし (既定)</span><span class="sxs-lookup"><span data-stu-id="25294-436">Category: None (default)</span></span>
    - <span data-ttu-id="25294-437">ファイル名: [ファイル] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-437">Filename: Choose File</span></span>

    ![[構成設定のイメージ] [全般] タブ](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="25294-439">ファイルを開き、またはをポイント `wdav.pkg` します `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="25294-439">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![コンピューター画面のスクリーンショット 説明が自動的に生成される](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="25294-441">[**開く**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-441">Select **Open**.</span></span> <span data-ttu-id="25294-442">[表示名 **] を** **[Microsoft Defender Advanced Threat Protection] および [Microsoft Defender ウイルス対策] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="25294-442">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="25294-443">**マニフェスト ファイル** は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="25294-443">**Manifest File** is not required.</span></span> <span data-ttu-id="25294-444">Microsoft Defender Advanced Threat Protection はマニフェスト ファイルなしで動作します。</span><span class="sxs-lookup"><span data-stu-id="25294-444">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="25294-445">**オプション タブ**</span><span class="sxs-lookup"><span data-stu-id="25294-445">**Options tab**</span></span><br> <span data-ttu-id="25294-446">既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="25294-446">Keep default values.</span></span>

    <span data-ttu-id="25294-447">**[制限] タブ**</span><span class="sxs-lookup"><span data-stu-id="25294-447">**Limitations tab**</span></span><br> <span data-ttu-id="25294-448">既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="25294-448">Keep default values.</span></span>
    
     ![[構成設定の制限] タブのイメージ](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="25294-450">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-450">Select **Save**.</span></span> <span data-ttu-id="25294-451">パッケージは Jamf Pro にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="25294-451">The package is uploaded to Jamf Pro.</span></span> 

   ![構成設定パック upl jamf pro のイメージ](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="25294-453">パッケージを展開に使用するには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="25294-453">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![構成設定パック upl のイメージ](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="25294-455">[ポリシー] **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="25294-455">Navigate to the **Policies** page.</span></span>

    ![構成設定のポロのイメージ](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="25294-457">[+ **新規] を** 選択して新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="25294-457">Select **+ New** to create a new policy.</span></span>

    ![構成設定の新しいポリシーのイメージ](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="25294-459">[ **全般]** 次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="25294-459">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="25294-460">表示名: MDATP Onboarding Contoso 200329 v100.86.92 以降</span><span class="sxs-lookup"><span data-stu-id="25294-460">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="25294-461">構成設定のイメージmdatponboard</span><span class="sxs-lookup"><span data-stu-id="25294-461">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="25294-462">[ **定期的なチェックイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-462">Select **Recurring Check-in**.</span></span> 
    
    ![構成設定の再チェック インのイメージ](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="25294-464">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-464">Select **Save**.</span></span> 
 
14. <span data-ttu-id="25294-465">[パッケージ **] を選択>構成します**。</span><span class="sxs-lookup"><span data-stu-id="25294-465">Select **Packages > Configure**.</span></span>
 
    ![構成設定パック構成のイメージ](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="25294-467">[Microsoft **Defender Advanced Threat** Protection] と [Microsoft Defender ウイルス対策] の横にある **[追加] ボタンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="25294-467">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![構成設定 MDATP と MDA の追加のイメージ](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="25294-469">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-469">Select **Save**.</span></span>

    ![構成設定のイメージsavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="25294-471">[スコープ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="25294-471">Select the **Scope** tab.</span></span>  

    ![構成設定 scptab のイメージ](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="25294-473">ターゲット コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-473">Select the target computers.</span></span>

    ![構成設定 tgtcomp のイメージ](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="25294-475">**Scope**</span><span class="sxs-lookup"><span data-stu-id="25294-475">**Scope**</span></span>
    
    <span data-ttu-id="25294-476">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-476">Select **Add**.</span></span>
    
    ![構成設定 ad1img のイメージ](images/1c08d097829863778d562c10c5f92b67.png)

    ![構成設定 ad2img のイメージ](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="25294-479">**セルフサービス**</span><span class="sxs-lookup"><span data-stu-id="25294-479">**Self-Service**</span></span>
    
    ![構成設定セルフサービスのイメージ](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="25294-481">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="25294-481">Select **Done**.</span></span> 

    ![構成設定 do1img のイメージ](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![構成設定 do2img のイメージ](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




