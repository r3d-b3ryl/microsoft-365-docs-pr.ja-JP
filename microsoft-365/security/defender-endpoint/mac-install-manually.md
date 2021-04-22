---
title: macOS での Microsoft Defender for Endpoint の手動展開
description: コマンド ラインから手動で macOS に Microsoft Defender for Endpoint をインストールします。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d8458f1bacc6577d83878a94c24e649371d90038
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935331"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="4cd72-104">macOS での Microsoft Defender for Endpoint の手動展開</span><span class="sxs-lookup"><span data-stu-id="4cd72-104">Manual deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4cd72-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4cd72-105">**Applies to:**</span></span>
- [<span data-ttu-id="4cd72-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4cd72-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4cd72-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cd72-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4cd72-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4cd72-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4cd72-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4cd72-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4cd72-110">このトピックでは、Microsoft Defender for Endpoint を macOS に手動で展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-110">This topic describes how to deploy Microsoft Defender for Endpoint on macOS manually.</span></span> <span data-ttu-id="4cd72-111">展開が成功するには、次のすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="4cd72-112">インストール パッケージとオンボーディング パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="4cd72-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="4cd72-113">アプリケーションのインストール (macOS 10.15 以前のバージョン)</span><span class="sxs-lookup"><span data-stu-id="4cd72-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="4cd72-114">アプリケーションのインストール (macOS 11 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="4cd72-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="4cd72-115">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="4cd72-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="4cd72-116">前提条件とシステム要件</span><span class="sxs-lookup"><span data-stu-id="4cd72-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="4cd72-117">開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、メインの [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd72-117">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="4cd72-118">インストール パッケージとオンボーディング パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="4cd72-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="4cd72-119">Microsoft Defender セキュリティ センターからインストールパッケージとオンボーディング パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="4cd72-120">Microsoft Defender セキュリティ センターで、[デバイス管理とオンボード **>設定>移動します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="4cd72-121">ページのセクション 1 で、オペレーティング システムを **macOS** に設定し、Deployment メソッドをローカル スクリプト **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="4cd72-122">ページのセクション 2 で、[インストール パッケージのダウンロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="4cd72-123">wdav.pkg としてローカル ディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="4cd72-124">ページのセクション 2 で、[オンボーディング パッケージの **ダウンロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="4cd72-125">同じディレクトリWindowsDefenderATPOnboardingPackage.zipとして保存します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Microsoft Defender セキュリティ センターのスクリーンショット](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="4cd72-127">コマンド プロンプトから、2 つのファイルが存在するように確認します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="4cd72-128">アプリケーションのインストール (macOS 10.15 以前のバージョン)</span><span class="sxs-lookup"><span data-stu-id="4cd72-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="4cd72-129">このプロセスを完了するには、デバイスに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="4cd72-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="4cd72-130">Finder でダウンロードした wdav.pkg に移動し、開きます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![アプリのインストールのスクリーンショット1](images/mdatp-28-appinstall.png)

2. <span data-ttu-id="4cd72-132">[ **続行] を** 選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![アプリのインストールのスクリーンショット2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > <span data-ttu-id="4cd72-134">Microsoft のドライバーのインストールを許可するように求めるメッセージが表示されます ("System Extension Blocked" または "Installation is on hold" のいずれかまたは両方)。</span><span class="sxs-lookup"><span data-stu-id="4cd72-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="4cd72-135">ドライバーのインストールを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-135">The driver must be allowed to be installed.</span></span>

   ![アプリのインストールのスクリーンショット3](images/mdatp-30-systemextension.png)

3. <span data-ttu-id="4cd72-137">[ **セキュリティの基本設定を開く]** または [システム環境設定を開く **] >[セキュリティ] &選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="4cd72-138">[許可 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-138">Select **Allow**:</span></span>

    ![セキュリティとプライバシー ウィンドウのスクリーンショット](images/mdatp-31-securityprivacysettings.png)

   <span data-ttu-id="4cd72-140">インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="4cd72-141">[許可] を選択しない **場合**、インストールは 5 分後に続行されます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="4cd72-142">Microsoft Defender for Endpoint が読み込まれますが、リアルタイム保護などの一部の機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="4cd72-143">これを解決 [する方法については、「カーネル拡張機能の問題](mac-support-kext.md) のトラブルシューティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd72-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="4cd72-144">macOS は、Microsoft Defender for Endpoint の最初のインストール時にデバイスの再起動を要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4cd72-145">デバイスが再起動されるまで、リアルタイム保護は利用できません。</span><span class="sxs-lookup"><span data-stu-id="4cd72-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="4cd72-146">アプリケーションのインストール (macOS 11 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="4cd72-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="4cd72-147">このプロセスを完了するには、デバイスに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="4cd72-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="4cd72-148">Finder でダウンロードした wdav.pkg に移動し、開きます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![アプリのインストールのスクリーンショット4](images/big-sur-install-1.png)

2. <span data-ttu-id="4cd72-150">[ **続行] を** 選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="4cd72-151">インストール プロセスの最後に、製品で使用されるシステム拡張機能を承認するように昇格されます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-151">At the end of the installation process, you'll be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="4cd72-152">[Open **Security Preferences] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-152">Select **Open Security Preferences**.</span></span>

    ![システム拡張機能の承認](images/big-sur-install-2.png)

4. <span data-ttu-id="4cd72-154">[セキュリティ] **ウィンドウの [&] ウィンドウで** 、[許可] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![システム拡張機能のセキュリティの基本設定1](images/big-sur-install-3.png)

5. <span data-ttu-id="4cd72-156">Microsoft Defender for Endpoint on Mac で配布&すべてのシステム拡張機能について、手順 3 から 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint on Mac.</span></span>

6. <span data-ttu-id="4cd72-157">エンドポイント検出と応答機能の一環として、Microsoft Defender for Endpoint on Mac はソケット トラフィックを検査し、この情報を Microsoft Defender セキュリティ センター ポータルに報告します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="4cd72-158">ネットワーク トラフィックをフィルター処理するための Microsoft Defender for Endpoint アクセス許可の付与を求めるメッセージが表示されたら、[許可] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![システム拡張機能のセキュリティの基本設定2](images/big-sur-install-4.png)

7. <span data-ttu-id="4cd72-160">[System **Preferences** Security & プライバシー] を開き、[プライバシー] タブに移動します。Microsoft Defender ATP および Microsoft Defender ATP Endpoint Security Extension にフル ディスク アクセスのアクセス許可を  >  **付与します**。   </span><span class="sxs-lookup"><span data-stu-id="4cd72-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![ディスクへのフル アクセス](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="4cd72-162">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="4cd72-162">Client configuration</span></span>

1. <span data-ttu-id="4cd72-163">wdav.pkg と MicrosoftDefenderATPOnboardingMacOs.py を macOS に Microsoft Defender for Endpoint を展開するデバイスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint on macOS.</span></span>

    <span data-ttu-id="4cd72-164">クライアント デバイスがクライアント デバイスに関連付org_id。</span><span class="sxs-lookup"><span data-stu-id="4cd72-164">The client device isn't associated with org_id.</span></span> <span data-ttu-id="4cd72-165">org_id *属性は* 空白です。</span><span class="sxs-lookup"><span data-stu-id="4cd72-165">Note that the *org_id* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="4cd72-166">Python スクリプトを実行して構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="4cd72-167">デバイスが組織に関連付けられたので、有効な組織 ID を報告します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-167">Verify that the device is now associated with your organization and reports a valid org ID:</span></span>

    ```bash
    mdatp health --field org_id
    ```

    <span data-ttu-id="4cd72-168">インストール後、右上隅の macOS ステータス バーに Microsoft Defender アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4cd72-169">![ステータス バーのスクリーンショットの Microsoft Defender アイコン](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="4cd72-169">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>


## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="4cd72-170">フル ディスク アクセスを許可する方法</span><span class="sxs-lookup"><span data-stu-id="4cd72-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="4cd72-171">macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれている。</span><span class="sxs-lookup"><span data-stu-id="4cd72-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="4cd72-172">このバージョンでは、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="4cd72-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="4cd72-173">この同意がない場合、Microsoft Defender for Endpoint はデバイスを完全に保護できません。</span><span class="sxs-lookup"><span data-stu-id="4cd72-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

1. <span data-ttu-id="4cd72-174">同意を許可するには **、[System Preferences**  >  **Security &プライバシー**  >  **のフル** ディスク アクセス  >  **] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-174">To grant consent, open **System Preferences** > **Security & Privacy** > **Privacy** > **Full Disk Access**.</span></span> <span data-ttu-id="4cd72-175">ロック アイコンをクリックして変更します (ダイアログ ボックスの下部)。</span><span class="sxs-lookup"><span data-stu-id="4cd72-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="4cd72-176">[エンドポイント用 Microsoft Defender] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-176">Select Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="4cd72-177">AV 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-177">Run an AV detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="4cd72-178">新しくオンボードされたデバイスで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-178">Perform the following steps on the newly onboarded device:</span></span>

    1. <span data-ttu-id="4cd72-179">リアルタイム保護が有効であることを確認します (次のコマンドを実行した結果 1 で示されます)。</span><span class="sxs-lookup"><span data-stu-id="4cd72-179">Ensure that real-time protection is enabled (denoted by a result of 1 from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. <span data-ttu-id="4cd72-180">ターミナル ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-180">Open a Terminal window.</span></span> <span data-ttu-id="4cd72-181">次のコマンドをコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-181">Copy and execute the following command:</span></span>

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. <span data-ttu-id="4cd72-182">このファイルは、Defender for Endpoint on Mac で検疫されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-182">The file should have been quarantined by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="4cd72-183">次のコマンドを使用して、検出された脅威の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-183">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

3. <span data-ttu-id="4cd72-184">EDR 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-184">Run an EDR detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="4cd72-185">新しくオンボードされたデバイスで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-185">Perform the following steps on the newly onboarded device:</span></span>

   1. <span data-ttu-id="4cd72-186">Microsoft Edge for Mac や Safari などのブラウザーで。</span><span class="sxs-lookup"><span data-stu-id="4cd72-186">In your browser such as Microsoft Edge for Mac or Safari.</span></span>

   1. <span data-ttu-id="4cd72-187">MDATP MacOS ファイルをダウンロードDIY.zip抽出 https://aka.ms/mdatpmacosdiy します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-187">Download MDATP MacOS DIY.zip from https://aka.ms/mdatpmacosdiy and extract.</span></span>

      <span data-ttu-id="4cd72-188">次のメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-188">You may be prompted:</span></span>

      > <span data-ttu-id="4cd72-189">"mdatpclientanalyzer.blob.core.windows.net" でダウンロードを許可しますか?</span><span class="sxs-lookup"><span data-stu-id="4cd72-189">Do you want to allow downloads on "mdatpclientanalyzer.blob.core.windows.net"?</span></span><br/>
      > <span data-ttu-id="4cd72-190">[Web サイトの基本設定] でファイルをダウンロードできる Web サイトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-190">You can change which websites can download files in Websites Preferences.</span></span>

4. <span data-ttu-id="4cd72-191">**[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-191">Click **Allow**.</span></span>

5. <span data-ttu-id="4cd72-192">[ **ダウンロード] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-192">Open **Downloads**.</span></span>

6. <span data-ttu-id="4cd72-193">**MDATP MacOS DIY が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-193">You should see **MDATP MacOS DIY**.</span></span>

   > [!TIP]
   > <span data-ttu-id="4cd72-194">ダブルクリックすると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-194">If you double-click, you will get the following message:</span></span>
   > 
   > > <span data-ttu-id="4cd72-195">**開発者が検証者になれませんので、"MDATP MacOS DIY" を開くことができません。**</span><span class="sxs-lookup"><span data-stu-id="4cd72-195">**"MDATP MacOS DIY" cannot be opened because the developer cannot be verifier.**</span></span><br/>
   > > <span data-ttu-id="4cd72-196">macOS は、このアプリがマルウェアから解放されているのを確認できません。</span><span class="sxs-lookup"><span data-stu-id="4cd72-196">macOS cannot verify that this app is free from malware.</span></span><br/>
   > > <span data-ttu-id="4cd72-197">**\[ ごみ箱の \] 取り消しに\*\*\*\*\[ 移動する \]**</span><span class="sxs-lookup"><span data-stu-id="4cd72-197">**\[Move to Trash\]** **\[Cancel\]**</span></span> 
  
7. <span data-ttu-id="4cd72-198">[ **キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-198">Click **Cancel**.</span></span>

8. <span data-ttu-id="4cd72-199">**MDATP MacOS DIY を右クリックし**、[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4cd72-199">Right-click **MDATP MacOS DIY**, and then click **Open**.</span></span> 

    <span data-ttu-id="4cd72-200">システムは、次のメッセージを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-200">The system should display the following message:</span></span>

    > <span data-ttu-id="4cd72-201">**macOS は **MDATP MacOS DIY の開発者を確認できません**。本当に開く必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="4cd72-201">**macOS cannot verify the developer of **MDATP MacOS DIY**. Are you sure you want to open it?**</span></span><br/>
    > <span data-ttu-id="4cd72-202">このアプリを開いて、コンピューターと個人情報を Mac に害を与えるマルウェアやプライバシーを侵害する可能性のあるシステム セキュリティを上書きします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-202">By opening this app, you will be overriding system security which can expose your computer and personal information to malware that may harm your Mac or compromise your privacy.</span></span>

10. <span data-ttu-id="4cd72-203">[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-203">Click **Open**.</span></span>

    <span data-ttu-id="4cd72-204">システムは、次のメッセージを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-204">The system should display the following message:</span></span>

    > <span data-ttu-id="4cd72-205">エンドポイント用 Microsoft Defender - macOS EDR DIY テスト ファイル</span><span class="sxs-lookup"><span data-stu-id="4cd72-205">Microsoft Defender for Endpoint - macOS EDR DIY test file</span></span><br/>
    > <span data-ttu-id="4cd72-206">対応するアラートは、MDATP ポータルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cd72-206">Corresponding alert will be available in the MDATP portal.</span></span>

11. <span data-ttu-id="4cd72-207">[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cd72-207">Click **Open**.</span></span>

    <span data-ttu-id="4cd72-208">数分で"macOS EDR テスト アラート" という名前のアラートが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd72-208">In a few minutes an alert named "macOS EDR Test Alert" should be raised.</span></span>

12. <span data-ttu-id="4cd72-209">[Microsoft Defender セキュリティ センター] ( に移動します https://SecurityCenter.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="4cd72-209">Go to Microsoft Defender Security Center (https://SecurityCenter.microsoft.com).</span></span>

13. <span data-ttu-id="4cd72-210">[アラート キュー] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-210">Go to the Alert Queue.</span></span>

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="重大度、カテゴリ、検出元、およびアクションの折りたたみメニューを示す macOS EDR テストアラートの例。":::
    
    <span data-ttu-id="4cd72-212">アラートの詳細とデバイスのタイムラインを確認し、通常の調査手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4cd72-212">Look at the alert details and the device timeline, and perform the regular investigation steps.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="4cd72-213">インストールの問題をログに記録する</span><span class="sxs-lookup"><span data-stu-id="4cd72-213">Logging installation issues</span></span>

<span data-ttu-id="4cd72-214">エラー [が発生した場合に](mac-resources.md#logging-installation-issues) インストーラーによって作成される自動的に生成されたログを検索する方法の詳細については、「インストールの問題のログ記録」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd72-214">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="4cd72-215">アンインストール</span><span class="sxs-lookup"><span data-stu-id="4cd72-215">Uninstallation</span></span>

<span data-ttu-id="4cd72-216">クライアント デバイス [から](mac-resources.md#uninstalling) macOS 上の Microsoft Defender for Endpoint を削除する方法の詳細については、「アンインストール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd72-216">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
