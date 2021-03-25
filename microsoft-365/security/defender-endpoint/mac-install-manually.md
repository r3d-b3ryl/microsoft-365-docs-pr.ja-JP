---
title: macOS 用 Microsoft Defender ATP の手動展開
description: コマンド ラインから手動で macOS 用 Microsoft Defender ATP をインストールします。
keywords: microsoft、 defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b2629eb3d13e6eb908644dfcade46a7ac2768637
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187447"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="ec82a-104">microsoft Defender for Endpoint for macOS の手動展開</span><span class="sxs-lookup"><span data-stu-id="ec82a-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec82a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ec82a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec82a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ec82a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ec82a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec82a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ec82a-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ec82a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ec82a-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ec82a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="ec82a-110">このトピックでは、Microsoft Defender for Endpoint for macOS を手動で展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="ec82a-111">展開が成功するには、次のすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec82a-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="ec82a-112">インストール パッケージとオンボーディング パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="ec82a-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="ec82a-113">アプリケーションのインストール (macOS 10.15 以前のバージョン)</span><span class="sxs-lookup"><span data-stu-id="ec82a-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="ec82a-114">アプリケーションのインストール (macOS 11 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="ec82a-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="ec82a-115">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="ec82a-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="ec82a-116">前提条件とシステム要件</span><span class="sxs-lookup"><span data-stu-id="ec82a-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="ec82a-117">開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、 [メインの Microsoft Defender for Endpoint for macOS](microsoft-defender-endpoint-mac.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec82a-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="ec82a-118">インストール パッケージとオンボーディング パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="ec82a-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="ec82a-119">Microsoft Defender セキュリティ センターからインストールパッケージとオンボーディング パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ec82a-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="ec82a-120">Microsoft Defender セキュリティ センターで、[デバイス管理とオンボード **>設定>移動します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="ec82a-121">ページのセクション 1 で、オペレーティング システムを **macOS** に設定し、Deployment メソッドをローカル スクリプト **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="ec82a-122">ページのセクション 2 で、[インストール パッケージのダウンロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="ec82a-123">wdav.pkg としてローカル ディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="ec82a-124">ページのセクション 2 で、[オンボーディング パッケージの **ダウンロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="ec82a-125">同じディレクトリWindowsDefenderATPOnboardingPackage.zipとして保存します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Microsoft Defender セキュリティ センターのスクリーンショット](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="ec82a-127">コマンド プロンプトから、2 つのファイルが存在するように確認します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="ec82a-128">アプリケーションのインストール (macOS 10.15 以前のバージョン)</span><span class="sxs-lookup"><span data-stu-id="ec82a-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="ec82a-129">このプロセスを完了するには、デバイスに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec82a-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="ec82a-130">Finder でダウンロードした wdav.pkg に移動し、開きます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![アプリのインストールのスクリーンショット1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. <span data-ttu-id="ec82a-132">[ **続行] を** 選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![アプリのインストールのスクリーンショット2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > <span data-ttu-id="ec82a-134">Microsoft のドライバーのインストールを許可するように求めるメッセージが表示されます ("System Extension Blocked" または "Installation is on hold" のいずれかまたは両方)。</span><span class="sxs-lookup"><span data-stu-id="ec82a-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="ec82a-135">ドライバーのインストールを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec82a-135">The driver must be allowed to be installed.</span></span>

   ![アプリのインストールのスクリーンショット3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. <span data-ttu-id="ec82a-137">[ **セキュリティの基本設定を開く]** または [システム環境設定を開く **] >[セキュリティ] &選択します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="ec82a-138">[許可 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-138">Select **Allow**:</span></span>

    ![セキュリティとプライバシー ウィンドウのスクリーンショット](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   <span data-ttu-id="ec82a-140">インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="ec82a-141">[許可] を選択しない **場合**、インストールは 5 分後に続行されます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="ec82a-142">Microsoft Defender for Endpoint が読み込まれますが、リアルタイム保護などの一部の機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="ec82a-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="ec82a-143">これを解決 [する方法については、「カーネル拡張機能の問題](mac-support-kext.md) のトラブルシューティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec82a-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="ec82a-144">macOS は、Microsoft Defender for Endpoint の最初のインストール時にデバイスの再起動を要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec82a-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ec82a-145">デバイスが再起動されるまで、リアルタイム保護は利用できません。</span><span class="sxs-lookup"><span data-stu-id="ec82a-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="ec82a-146">アプリケーションのインストール (macOS 11 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="ec82a-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="ec82a-147">このプロセスを完了するには、デバイスに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec82a-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="ec82a-148">Finder でダウンロードした wdav.pkg に移動し、開きます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![アプリのインストールのスクリーンショット4](images/big-sur-install-1.png)

2. <span data-ttu-id="ec82a-150">[ **続行] を** 選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="ec82a-151">インストール プロセスの最後に、製品で使用されるシステム拡張機能を承認するように昇格されます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-151">At the end of the installation process, you will be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="ec82a-152">[Open **Security Preferences] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-152">Select **Open Security Preferences**.</span></span>

    ![システム拡張機能の承認](images/big-sur-install-2.png)

4. <span data-ttu-id="ec82a-154">[セキュリティ] **ウィンドウの [&] ウィンドウで** 、[許可] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![システム拡張機能のセキュリティの基本設定1](images/big-sur-install-3.png)

5. <span data-ttu-id="ec82a-156">Microsoft Defender for Endpoint for Mac で配布&すべてのシステム拡張機能について、手順 3 から 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="ec82a-157">エンドポイント検出と応答機能の一環として、Microsoft Defender for Endpoint for Mac はソケット トラフィックを検査し、この情報を Microsoft Defender セキュリティ センター ポータルに報告します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="ec82a-158">ネットワーク トラフィックをフィルター処理するための Microsoft Defender for Endpoint アクセス許可の付与を求めるメッセージが表示されたら、[許可] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ec82a-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![システム拡張機能のセキュリティの基本設定2](images/big-sur-install-4.png)

7. <span data-ttu-id="ec82a-160">[System **Preferences** Security & プライバシー] を開き、[プライバシー] タブに移動します。Microsoft Defender ATP および Microsoft Defender ATP Endpoint Security Extension にフル ディスク アクセスのアクセス許可を  >  **付与します**。   </span><span class="sxs-lookup"><span data-stu-id="ec82a-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![ディスクへのフル アクセス](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="ec82a-162">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="ec82a-162">Client configuration</span></span>

1. <span data-ttu-id="ec82a-163">wdav.pkg と MicrosoftDefenderATPOnboardingMacOs.py microsoft Defender for Endpoint for macOS を展開するデバイスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ec82a-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="ec82a-164">クライアント デバイスは orgId に関連付けではありません。</span><span class="sxs-lookup"><span data-stu-id="ec82a-164">The client device is not associated with orgId.</span></span> <span data-ttu-id="ec82a-165">*orgId 属性は* 空白です。</span><span class="sxs-lookup"><span data-stu-id="ec82a-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="ec82a-166">Python スクリプトを実行して構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ec82a-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="ec82a-167">デバイスが組織に関連付けられると、有効な *orgId* が報告されます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="ec82a-168">インストール後、右上隅の macOS ステータス バーに Microsoft Defender アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![ステータス バーのスクリーンショットの Microsoft Defender アイコン](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="ec82a-170">フル ディスク アクセスを許可する方法</span><span class="sxs-lookup"><span data-stu-id="ec82a-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="ec82a-171">macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれている。</span><span class="sxs-lookup"><span data-stu-id="ec82a-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="ec82a-172">このバージョンでは、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ec82a-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="ec82a-173">この同意がない場合、Microsoft Defender for Endpoint はデバイスを完全に保護できません。</span><span class="sxs-lookup"><span data-stu-id="ec82a-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="ec82a-174">同意を許可するには、System Preferences -> セキュリティ & プライバシー -> プライバシー -> フル ディスク アクセスを開きます。</span><span class="sxs-lookup"><span data-stu-id="ec82a-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="ec82a-175">ロック アイコンをクリックして変更します (ダイアログ ボックスの下部)。</span><span class="sxs-lookup"><span data-stu-id="ec82a-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="ec82a-176">[エンドポイント用 Microsoft Defender] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec82a-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="ec82a-177">インストールの問題をログに記録する</span><span class="sxs-lookup"><span data-stu-id="ec82a-177">Logging installation issues</span></span>

<span data-ttu-id="ec82a-178">エラー [が発生した場合に](mac-resources.md#logging-installation-issues) インストーラーによって作成される自動的に生成されたログを検索する方法の詳細については、「インストールの問題のログ記録」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec82a-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="ec82a-179">アンインストール</span><span class="sxs-lookup"><span data-stu-id="ec82a-179">Uninstallation</span></span>

<span data-ttu-id="ec82a-180">クライアント デバイス [から](mac-resources.md#uninstalling) macOS 用 Microsoft Defender for Endpoint を削除する方法の詳細については、「アンインストール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec82a-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
