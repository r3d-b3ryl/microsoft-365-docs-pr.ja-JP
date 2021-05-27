---
title: Microsoft Defender for Endpoint on Mac の Intune ベースの展開
description: Mac に Microsoft Defender for Endpoint をインストールします。Microsoft Intune。
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
ms.openlocfilehash: 5aeffdaff39c2f10dfa5164764bff38e99c00010
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684221"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="af0b9-104">MacOS での Microsoft Defender for Endpoint の Intune ベースの展開</span><span class="sxs-lookup"><span data-stu-id="af0b9-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af0b9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="af0b9-105">**Applies to:**</span></span>

- [<span data-ttu-id="af0b9-106">macOS 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af0b9-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="af0b9-107">このトピックでは、Intune を介して macOS に Microsoft Defender for Endpoint を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-107">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="af0b9-108">展開が成功するには、次のすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0b9-108">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="af0b9-109">オンボーディング パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="af0b9-109">Download the onboarding package</span></span>](#download-the-onboarding-package)
1. [<span data-ttu-id="af0b9-110">クライアント デバイスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="af0b9-110">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="af0b9-111">システム拡張機能の承認</span><span class="sxs-lookup"><span data-stu-id="af0b9-111">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="af0b9-112">システム構成プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="af0b9-112">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="af0b9-113">アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="af0b9-113">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="af0b9-114">前提条件とシステム要件</span><span class="sxs-lookup"><span data-stu-id="af0b9-114">Prerequisites and system requirements</span></span>

<span data-ttu-id="af0b9-115">開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、メインの [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0b9-115">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="af0b9-116">概要</span><span class="sxs-lookup"><span data-stu-id="af0b9-116">Overview</span></span>

<span data-ttu-id="af0b9-117">次の表は、Intune 経由で Microsoft Defender for Endpoint on Mac を展開および管理するために必要な手順の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="af0b9-117">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="af0b9-118">詳細な手順については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af0b9-118">More detailed steps are available below.</span></span>

| <span data-ttu-id="af0b9-119">手順</span><span class="sxs-lookup"><span data-stu-id="af0b9-119">Step</span></span> | <span data-ttu-id="af0b9-120">サンプル ファイル名</span><span class="sxs-lookup"><span data-stu-id="af0b9-120">Sample file names</span></span> | <span data-ttu-id="af0b9-121">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="af0b9-121">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="af0b9-122">オンボーディング パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="af0b9-122">Download the onboarding package</span></span>](#download-the-onboarding-package) | <span data-ttu-id="af0b9-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="af0b9-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="af0b9-124">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="af0b9-124">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="af0b9-125">エンドポイント用 Microsoft Defender のシステム拡張機能を承認する</span><span class="sxs-lookup"><span data-stu-id="af0b9-125">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="af0b9-126">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="af0b9-126">MDATP_SysExt.xml</span></span> | <span data-ttu-id="af0b9-127">N/A</span><span class="sxs-lookup"><span data-stu-id="af0b9-127">N/A</span></span> |
| [<span data-ttu-id="af0b9-128">Microsoft Defender for Endpoint のカーネル拡張機能の承認</span><span class="sxs-lookup"><span data-stu-id="af0b9-128">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-the-onboarding-package) | <span data-ttu-id="af0b9-129">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="af0b9-129">MDATP_KExt.xml</span></span> | <span data-ttu-id="af0b9-130">N/A</span><span class="sxs-lookup"><span data-stu-id="af0b9-130">N/A</span></span> |
| [<span data-ttu-id="af0b9-131">Microsoft Defender for Endpoint へのフル ディスク アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="af0b9-131">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#full-disk-access) | <span data-ttu-id="af0b9-132">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="af0b9-132">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="af0b9-133">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="af0b9-133">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="af0b9-134">ネットワーク拡張ポリシー</span><span class="sxs-lookup"><span data-stu-id="af0b9-134">Network Extension policy</span></span>](#network-filter) | <span data-ttu-id="af0b9-135">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="af0b9-135">MDATP_NetExt.xml</span></span> | <span data-ttu-id="af0b9-136">N/A</span><span class="sxs-lookup"><span data-stu-id="af0b9-136">N/A</span></span> |
| [<span data-ttu-id="af0b9-137">Microsoft AutoUpdate (MAU) の構成</span><span class="sxs-lookup"><span data-stu-id="af0b9-137">Configure Microsoft AutoUpdate (MAU)</span></span>](mac-updates.md#intune) | <span data-ttu-id="af0b9-138">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="af0b9-138">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="af0b9-139">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="af0b9-139">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="af0b9-140">Microsoft Defender for Endpoint 構成設定</span><span class="sxs-lookup"><span data-stu-id="af0b9-140">Microsoft Defender for Endpoint configuration settings</span></span>](mac-preferences.md#intune-profile-1)<br/><br/> <span data-ttu-id="af0b9-141">**注:** macOS 用のサード パーティ製 AV の実行を計画している場合は、 に設定 `passiveMode` します `true` 。</span><span class="sxs-lookup"><span data-stu-id="af0b9-141">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="af0b9-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="af0b9-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="af0b9-143">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="af0b9-143">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="af0b9-144">エンドポイントおよび MS AutoUpdate (MAU) 通知の Microsoft Defender の構成</span><span class="sxs-lookup"><span data-stu-id="af0b9-144">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](mac-updates.md) | <span data-ttu-id="af0b9-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="af0b9-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="af0b9-146">com.microsoft.autoupdate2 または com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="af0b9-146">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |


## <a name="download-the-onboarding-package"></a><span data-ttu-id="af0b9-147">オンボーディング パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="af0b9-147">Download the onboarding package</span></span>

<span data-ttu-id="af0b9-148">次の方法でオンボーディング パッケージをMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="af0b9-148">Download the onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="af0b9-149">[Microsoft Defender セキュリティ センター] で、[デバイス設定  >  **オンボーディング]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-149">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="af0b9-150">オペレーティング システムを **macOS** に設定し、展開方法を [Mobile Device Management / Microsoft Intune]**に設定します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-150">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![オンボーディング設定のスクリーンショット](images/atp-mac-install.png)

3. <span data-ttu-id="af0b9-152">[オンボード **パッケージのダウンロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-152">Select **Download onboarding package**.</span></span> <span data-ttu-id="af0b9-153">同 _じディレクトリWindowsDefenderATPOnboardingPackage.zip_ として保存します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-153">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

4. <span data-ttu-id="af0b9-154">ファイルの内容を.zipします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-154">Extract the contents of the .zip file:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="af0b9-155">システム構成プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="af0b9-155">Create System Configuration profiles</span></span>

<span data-ttu-id="af0b9-156">次の手順では、Microsoft Defender for Endpoint が必要とするシステム構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-156">The next step is to create system configuration profiles that Microsoft Defender for Endpoint needs.</span></span>
<span data-ttu-id="af0b9-157">管理センター [でMicrosoft エンドポイント マネージャーデバイス](https://endpoint.microsoft.com/)構成 **プロファイル**  >  **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-157">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Devices** > **Configuration profiles**.</span></span>

### <a name="onboarding-blob"></a><span data-ttu-id="af0b9-158">BLOB のオンボーディング</span><span class="sxs-lookup"><span data-stu-id="af0b9-158">Onboarding blob</span></span>

<span data-ttu-id="af0b9-159">このプロファイルには、Microsoft Defender for Endpoint のライセンス情報が含まれているので、ライセンスされていないと報告されます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-159">This profile contains a license information for Microsoft Defender for Endpoint, without it it will report that it is not licensed.</span></span>

1. <span data-ttu-id="af0b9-160">[構成 **プロファイル] で [\*\*\*\*プロファイルの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-160">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="af0b9-161">[**プラットフォーム** = **macOS]**[**プロファイルの種類** = **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-161">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="af0b9-162">**テンプレート名** =**カスタム**.</span><span class="sxs-lookup"><span data-stu-id="af0b9-162">**Template name**=**Custom**.</span></span> <span data-ttu-id="af0b9-163">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-163">Click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-164">![カスタム構成プロファイルの作成](images/mdatp-6-systemconfigurationprofiles-1.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-164">![Custom Configuration Profile creation](images/mdatp-6-systemconfigurationprofiles-1.png)</span></span>

1. <span data-ttu-id="af0b9-165">プロファイルの名前を選択します。たとえば、「macOS のオンボーディングMDATPを選択します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-165">Choose a name for the profile, e.g., "MDATP onboarding for macOS".</span></span> <span data-ttu-id="af0b9-166">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-166">Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-167">![カスタム構成プロファイル - 名前](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-167">![Custom Configuration Profile - name](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="af0b9-168">構成プロファイル名の名前を選択します。たとえば、「macOS のオンボーディングMDATPを選択します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-168">Choose a name for the configuration profile name, e.g., "MDATP onboarding for macOS".</span></span>
1. <span data-ttu-id="af0b9-169">構成プロファイル ファイルとしてWindowsDefenderATPOnboarding.xmlオンボーディング パッケージから抽出した intune/WindowsDefenderATPOnboarding.xmlを選択します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-169">Select intune/WindowsDefenderATPOnboarding.xml that you extracted from the onboarding package above as configuration profile file.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-170">![カスタム構成プロファイルのファイルから構成をインポートする](images/mdatp-6-systemconfigurationprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-170">![Import a configuration from a file for Custom Configuration Profile](images/mdatp-6-systemconfigurationprofiles.png)</span></span>

1. <span data-ttu-id="af0b9-171">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-171">Click **Next**.</span></span>
1. <span data-ttu-id="af0b9-172">[割り当て] タブでデバイス **を割り当** てる。[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-172">Assign devices on the **Assignment** tab. Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-173">![カスタム構成プロファイル - 割り当て](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-173">![Custom Configuration Profile - assignment](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="af0b9-174">レビューと **作成**.</span><span class="sxs-lookup"><span data-stu-id="af0b9-174">Review and **Create**.</span></span>
1. <span data-ttu-id="af0b9-175">[**デバイス**  >  **構成プロファイル] を開** きます。作成したプロファイルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-175">Open **Devices** > **Configuration profiles**, you can see your created profile there.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-176">![カスタム構成プロファイル - 完了](images/mdatp-6-systemconfigurationprofiles-3.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-176">![Custom Configuration Profile - done](images/mdatp-6-systemconfigurationprofiles-3.png)</span></span>

### <a name="approve-system-extensions"></a><span data-ttu-id="af0b9-177">システム拡張機能の承認</span><span class="sxs-lookup"><span data-stu-id="af0b9-177">Approve System Extensions</span></span>

<span data-ttu-id="af0b9-178">このプロファイルは、macOS 10.15 (Catalina) 以降に必要です。</span><span class="sxs-lookup"><span data-stu-id="af0b9-178">This profile is needed for macOS 10.15 (Catalina) or newer.</span></span> <span data-ttu-id="af0b9-179">古い macOS では無視されます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-179">It will be ignored on older macOS.</span></span>

1. <span data-ttu-id="af0b9-180">[構成 **プロファイル] で [\*\*\*\*プロファイルの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-180">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="af0b9-181">[**プラットフォーム** = **macOS]**[**プロファイルの種類** = **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-181">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="af0b9-182">**テンプレート名** =**拡張機能**.</span><span class="sxs-lookup"><span data-stu-id="af0b9-182">**Template name**=**Extensions**.</span></span> <span data-ttu-id="af0b9-183">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-183">Click **Create**.</span></span>
1. <span data-ttu-id="af0b9-184">[基本 **] タブ** で、この新しいプロファイルに名前を付きます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-184">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="af0b9-185">[構成 **設定] タブで** 、[システム拡張機能] **を展開し、[** 許可されたシステム拡張機能] セクションに次 **のエントリを追加** します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-185">In the **Configuration settings** tab, expand **System Extensions** add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="af0b9-186">バンドル識別子</span><span class="sxs-lookup"><span data-stu-id="af0b9-186">Bundle identifier</span></span>         | <span data-ttu-id="af0b9-187">チーム識別子</span><span class="sxs-lookup"><span data-stu-id="af0b9-187">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="af0b9-188">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="af0b9-188">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="af0b9-189">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="af0b9-189">UBF8T346G9</span></span>
    <span data-ttu-id="af0b9-190">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="af0b9-190">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="af0b9-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="af0b9-191">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-192">![システム拡張機能の設定](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-192">![System extension settings](images/mac-system-extension-intune2.png)</span></span>

1. <span data-ttu-id="af0b9-193">[割り **当て] タブ** で、このプロファイルを [すべてのユーザー] または **[すべての&に割り当てる] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-193">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="af0b9-194">この構成プロファイルを確認して作成します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-194">Review and create this configuration profile.</span></span>

### <a name="kernel-extensions"></a><span data-ttu-id="af0b9-195">カーネル拡張機能</span><span class="sxs-lookup"><span data-stu-id="af0b9-195">Kernel Extensions</span></span>

<span data-ttu-id="af0b9-196">このプロファイルは、macOS 10.15 (Catalina) 以上で必要です。</span><span class="sxs-lookup"><span data-stu-id="af0b9-196">This profile is needed for macOS 10.15 (Catalina) or older.</span></span> <span data-ttu-id="af0b9-197">新しい macOS では無視されます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-197">It will be ignored on newer macOS.</span></span>

> [!CAUTION]
> <span data-ttu-id="af0b9-198">Apple Silicon (M1) デバイスは KEXT をサポートしていない。</span><span class="sxs-lookup"><span data-stu-id="af0b9-198">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="af0b9-199">KEXT ポリシーからなる構成プロファイルのインストールは、これらのデバイスで失敗します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-199">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="af0b9-200">[構成 **プロファイル] で [\*\*\*\*プロファイルの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-200">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="af0b9-201">[**プラットフォーム** = **macOS]**[**プロファイルの種類** = **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-201">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="af0b9-202">**テンプレート名** =**拡張機能**.</span><span class="sxs-lookup"><span data-stu-id="af0b9-202">**Template name**=**Extensions**.</span></span> <span data-ttu-id="af0b9-203">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-203">Click **Create**.</span></span>
1. <span data-ttu-id="af0b9-204">[基本 **] タブ** で、この新しいプロファイルに名前を付きます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-204">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="af0b9-205">[構成設定 **] タブで** 、[カーネル拡張機能 **] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-205">In the **Configuration settings** tab, expand **Kernel Extensions**.</span></span>
1. <span data-ttu-id="af0b9-206">チーム **識別子を** **UBF8T346G9** に設定し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-206">Set **Team identifier** to **UBF8T346G9** and click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-207">![カーネル拡張機能の設定](images/mac-kernel-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-207">![Kernel extension settings](images/mac-kernel-extension-intune2.png)</span></span>

1. <span data-ttu-id="af0b9-208">[割り **当て] タブ** で、このプロファイルを [すべてのユーザー] または **[すべての&に割り当てる] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-208">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="af0b9-209">この構成プロファイルを確認して作成します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-209">Review and create this configuration profile.</span></span>

### <a name="full-disk-access"></a><span data-ttu-id="af0b9-210">フル ディスク アクセス</span><span class="sxs-lookup"><span data-stu-id="af0b9-210">Full Disk Access</span></span>

   > [!CAUTION]
   > <span data-ttu-id="af0b9-211">macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれている。</span><span class="sxs-lookup"><span data-stu-id="af0b9-211">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="af0b9-212">このバージョンでは、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="af0b9-212">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="af0b9-213">この同意がない場合、Microsoft Defender for Endpoint はデバイスを完全に保護できません。</span><span class="sxs-lookup"><span data-stu-id="af0b9-213">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="af0b9-214">この構成プロファイルは、エンドポイント用 Microsoft Defender へのフル ディスク アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-214">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="af0b9-215">以前に Intune を使用して Microsoft Defender for Endpoint を構成した場合は、この構成プロファイルを使用して展開を更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-215">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

<span data-ttu-id="af0b9-216">[**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)を [、GitHubリポジトリからダウンロードします](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)。</span><span class="sxs-lookup"><span data-stu-id="af0b9-216">Download [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="af0b9-217">プロファイル名として "MDATP フル ディスク アクセス" を使用し、fulldisk.mobileconfig を構成プロファイル名としてダウンロードして、上記の 「オンボード BLOB」の手順に従います。 [](#onboarding-blob)</span><span class="sxs-lookup"><span data-stu-id="af0b9-217">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Full Disk Access" as profile name, and downloaded **fulldisk.mobileconfig** as Configuration profile name.</span></span>

### <a name="network-filter"></a><span data-ttu-id="af0b9-218">ネットワーク フィルター</span><span class="sxs-lookup"><span data-stu-id="af0b9-218">Network Filter</span></span>

<span data-ttu-id="af0b9-219">エンドポイント検出および応答機能の一環として、macOS 上の Microsoft Defender for Endpoint はソケット トラフィックを検査し、この情報をポータルMicrosoft Defender セキュリティ センターします。</span><span class="sxs-lookup"><span data-stu-id="af0b9-219">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="af0b9-220">次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-220">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="af0b9-221">[**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)を [、GitHubリポジトリからダウンロードします](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)。</span><span class="sxs-lookup"><span data-stu-id="af0b9-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="af0b9-222">プロファイル名として "MDATP ネットワーク フィルター" を使用し、構成プロファイル名としてダウンロードした **netfilter.mobileconfig** を使用して、上記の 「オンボード BLOB」の手順に従います。 [](#onboarding-blob)</span><span class="sxs-lookup"><span data-stu-id="af0b9-222">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **netfilter.mobileconfig** as Configuration profile name.</span></span>

### <a name="notifications"></a><span data-ttu-id="af0b9-223">通知</span><span class="sxs-lookup"><span data-stu-id="af0b9-223">Notifications</span></span>

<span data-ttu-id="af0b9-224">このプロファイルは、macOS 上の Microsoft Defender for Endpoint と Microsoft Auto Update が macOS 10.15 (Catalina) 以降の UI で通知を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-224">This profile is used to allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina) or newer.</span></span>

<span data-ttu-id="af0b9-225">ダウンロード [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) from [our GitHub リポジトリ](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="af0b9-225">Download [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="af0b9-226">プロファイル名として "MDATP ネットワーク フィルター" を使用し、構成プロファイル名として **notif.mobileconfig** をダウンロードして、上記の 「オンボード BLOB」の手順に従います。 [](#onboarding-blob)</span><span class="sxs-lookup"><span data-stu-id="af0b9-226">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **notif.mobileconfig** as Configuration profile name.</span></span>

### <a name="view-status"></a><span data-ttu-id="af0b9-227">状態の表示</span><span class="sxs-lookup"><span data-stu-id="af0b9-227">View Status</span></span>

<span data-ttu-id="af0b9-228">Intune の変更が登録済みデバイスに反映された後は、[デバイスの状態の監視]の下に表示  >  **されます**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-228">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="af0b9-229">![モニターでのデバイスの状態の表示](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-229">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="af0b9-230">アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="af0b9-230">Publish application</span></span>

<span data-ttu-id="af0b9-231">この手順では、登録済みコンピューターに Microsoft Defender for Endpoint を展開できます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-231">This step enables deploying Microsoft Defender for Endpoint to enrolled machines.</span></span>

1. <span data-ttu-id="af0b9-232">管理センター [でMicrosoft エンドポイント マネージャーを](https://endpoint.microsoft.com/)開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-232">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Apps**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-233">![アプリケーションを作成する準備ができました](images/mdatp-8-app-before.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-233">![Ready to create application](images/mdatp-8-app-before.png)</span></span>

1. <span data-ttu-id="af0b9-234">[プラットフォーム別] を> macOS >追加します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-234">Select By platform > macOS > Add.</span></span>
1. <span data-ttu-id="af0b9-235">[アプリ **の種類** = **] macOS を選択し、[** 選択]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-235">Choose **App type**=**macOS**, click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-236">![アプリケーションの種類を指定する](images/mdatp-9-app-type.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-236">![Specify application type](images/mdatp-9-app-type.png)</span></span>

1. <span data-ttu-id="af0b9-237">既定値を保持し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-237">Keep default values, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-238">![アプリケーションのプロパティ](images/mdatp-10-properties.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-238">![Application properties](images/mdatp-10-properties.png)</span></span>

1. <span data-ttu-id="af0b9-239">割り当てを追加し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-239">Add assignments, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-240">![Intune の割り当て情報のスクリーンショット](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

1. <span data-ttu-id="af0b9-241">レビューと **作成**.</span><span class="sxs-lookup"><span data-stu-id="af0b9-241">Review and **Create**.</span></span>
1. <span data-ttu-id="af0b9-242">App By   >  platform macOS **に**  >  **アクセスして**、すべてのアプリケーションの一覧に表示できます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-242">You can visit **Apps** > **By platform** > **macOS** to see it on the list of all applications.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-243">![アプリケーションの一覧](images/mdatp-12-applications.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-243">![Applications list](images/mdatp-12-applications.png)</span></span>

<span data-ttu-id="af0b9-244">(詳細については、Intune の Defender 展開用ページ [をご覧ください](/mem/intune/apps/apps-advanced-threat-protection-macos)。)</span><span class="sxs-lookup"><span data-stu-id="af0b9-244">(You can find detailed information on the [Intune's page for Defender deployment](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span></span>

   > [!CAUTION]
   > <span data-ttu-id="af0b9-245">上記で説明したように、必要なすべての構成プロファイルを作成し、すべてのコンピューターにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0b9-245">You have to create all required configuration profiles and push them to all machines, as explained above.</span></span>

## <a name="client-device-setup"></a><span data-ttu-id="af0b9-246">クライアント デバイスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="af0b9-246">Client device setup</span></span>

<span data-ttu-id="af0b9-247">標準インストール以外の Mac デバイスに対する特別なプロビジョニング[はポータル サイト必要ない](/intune-user-help/enroll-your-device-in-intune-macos-cp)。</span><span class="sxs-lookup"><span data-stu-id="af0b9-247">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="af0b9-248">デバイスの管理を確認します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-248">Confirm device management.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-249">![デバイス管理のスクリーンショットを確認する](images/mdatp-3-confirmdevicemgmt.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-249">![Confirm device management screenshot](images/mdatp-3-confirmdevicemgmt.png)</span></span>

    <span data-ttu-id="af0b9-250">[ **システム環境設定を開く]** を選択し、一 **覧で [管理プロファイル** ] を探し、[ **承認...] を選択します**。管理プロファイルが [確認済み] **と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-250">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![管理プロファイルのスクリーンショット](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="af0b9-252">[続行 **] を** 選択し、登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-252">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="af0b9-253">これで、より多くのデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-253">You may now enroll more devices.</span></span> <span data-ttu-id="af0b9-254">システム構成とアプリケーション パッケージのプロビジョニングが完了したら、後で登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-254">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="af0b9-255">Intune で、[デバイスの管理 **] [**  >  **すべての**  >  **デバイス] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="af0b9-255">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="af0b9-256">ここにリストされているデバイスの中からデバイスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-256">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="af0b9-257">![デバイスの追加スクリーンショット](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-257">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="af0b9-258">クライアント デバイスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="af0b9-258">Verify client device state</span></span>

1. <span data-ttu-id="af0b9-259">構成プロファイルをデバイスに展開した後、Mac デバイス **で [System Preferences**  >  **Profiles]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-260">![System Preferences のスクリーンショット](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span>

    ![System Preferences Profiles スクリーンショット](images/mdatp-14-systempreferencesprofiles.png)

2. <span data-ttu-id="af0b9-262">次の構成プロファイルが存在し、インストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="af0b9-263">管理 **プロファイルは** Intune システム プロファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0b9-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="af0b9-264">_Wdav-config_ と _wdav-kext_ は、Intune で追加されたシステム構成プロファイルです。</span><span class="sxs-lookup"><span data-stu-id="af0b9-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune:</span></span>

    ![プロファイルのスクリーンショット](images/mdatp-15-managementprofileconfig.png)

3. <span data-ttu-id="af0b9-266">右上隅には、Microsoft Defender for Endpoint アイコンも表示されます。</span><span class="sxs-lookup"><span data-stu-id="af0b9-266">You should also see the Microsoft Defender for Endpoint icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0b9-267">![ステータス バーのスクリーンショットの Microsoft Defender for Endpoint アイコン](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="af0b9-267">![Microsoft Defender for Endpoint icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="af0b9-268">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="af0b9-268">Troubleshooting</span></span>

<span data-ttu-id="af0b9-269">問題: ライセンスが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="af0b9-269">Issue: No license found.</span></span>

<span data-ttu-id="af0b9-270">解決策: 上記の手順に従って、デバイス プロファイルを作成するには、WindowsDefenderATPOnboarding.xml。</span><span class="sxs-lookup"><span data-stu-id="af0b9-270">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="af0b9-271">インストールの問題をログに記録する</span><span class="sxs-lookup"><span data-stu-id="af0b9-271">Logging installation issues</span></span>

<span data-ttu-id="af0b9-272">エラーが発生した場合にインストーラーによって作成される自動的に生成されたログを検索する方法の詳細については、「Logging [installation issues」を参照してください](mac-resources.md#logging-installation-issues)。</span><span class="sxs-lookup"><span data-stu-id="af0b9-272">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="af0b9-273">アンインストール</span><span class="sxs-lookup"><span data-stu-id="af0b9-273">Uninstallation</span></span>

<span data-ttu-id="af0b9-274">クライアント デバイス [から](mac-resources.md#uninstalling) macOS 上の Microsoft Defender for Endpoint を削除する方法の詳細については、「アンインストール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0b9-274">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
