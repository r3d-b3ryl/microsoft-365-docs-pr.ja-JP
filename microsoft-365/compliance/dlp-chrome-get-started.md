---
title: Microsoft Compliance Extension を開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft Compliance Extension の準備と導入。
ms.openlocfilehash: a76a4b1ab5b92a1e237663f65002b99d792b13bb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288373"
---
# <a name="get-started-with-microsoft-compliance-extension"></a><span data-ttu-id="1773e-103">Microsoft Compliance Extension を開始する</span><span class="sxs-lookup"><span data-stu-id="1773e-103">Get started with Microsoft Compliance Extension</span></span>

<span data-ttu-id="1773e-104">以下の手順を使用して、Microsoft Compliance Extension をロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="1773e-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1773e-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="1773e-105">Before you begin</span></span>

<span data-ttu-id="1773e-106">Microsoft Compliance Extension を使用するには、デバイスがエンドポイント DLP に搭載されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="1773e-107">DLP やエンドポイント DLP に慣れていない場合は、これらの記事をレビューします</span><span class="sxs-lookup"><span data-stu-id="1773e-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="1773e-108">Microsoft Compliance Extension の詳細</span><span class="sxs-lookup"><span data-stu-id="1773e-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="1773e-109">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="1773e-109">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="1773e-110">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="1773e-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1773e-111">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="1773e-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="1773e-112">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="1773e-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="1773e-113">エンドポイント データ損失防止の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="1773e-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="1773e-114">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="1773e-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="1773e-115">エンドポイント DLP のデバイス プロキシとインターネット接続の構成</span><span class="sxs-lookup"><span data-stu-id="1773e-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="1773e-116">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="1773e-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="1773e-117">SKU /サブスクリプション ライセンス</span><span class="sxs-lookup"><span data-stu-id="1773e-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="1773e-118">開始する前に、「[Microsoft 365サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」とアドオンを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1773e-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="1773e-119">Endpoint DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="1773e-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="1773e-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1773e-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="1773e-121">Microsoft 365 A5 (EDU) </span><span class="sxs-lookup"><span data-stu-id="1773e-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="1773e-122">Microsoft 365 E5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1773e-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="1773e-123">Microsoft 365 A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1773e-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="1773e-124">Microsoft 365 E5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="1773e-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="1773e-125">Microsoft 365 A5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="1773e-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="1773e-126">ライセンスのガイダンスに関する詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1773e-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="1773e-127">ご所属の組織で エンドポイント DLP のライセンスを取得している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="1773e-128">デバイスで Windows 10 x64 ビルド 1809 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="1773e-129">デバイスで Antimalware Client バージョン 4.18.2101.9 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="1773e-130">**Windows セキュリティ** アプリを開いて現在のバージョンを確認し、**[設定]** アイコンを選択して、**[バージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="1773e-131">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1773e-131">Permissions</span></span>

<span data-ttu-id="1773e-132">Endpoint DLP からのデータは、[Activity エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="1773e-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="1773e-133">Activity エクスプローラーに権限を付与する役割は 7 つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1773e-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="1773e-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="1773e-134">Global admin</span></span>
- <span data-ttu-id="1773e-135">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="1773e-135">Compliance admin</span></span>
- <span data-ttu-id="1773e-136">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="1773e-136">Security admin</span></span>
- <span data-ttu-id="1773e-137">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="1773e-137">Compliance data admin</span></span>
- <span data-ttu-id="1773e-138">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="1773e-138">Global reader</span></span>
- <span data-ttu-id="1773e-139">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="1773e-139">Security reader</span></span>
- <span data-ttu-id="1773e-140">レポート閲覧者</span><span class="sxs-lookup"><span data-stu-id="1773e-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="1773e-141">インストールの全体的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="1773e-141">Overall installation workflow</span></span>

<span data-ttu-id="1773e-p105">Microsoft Compliance Extension の展開は、多段階のプロセスです。一度に 1 台のマシンにインストールするか、Microsoft エンドポイント マネージャーやグループ ポリシーを使用して組織全体に展開するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1773e-p105">Deploying Microsoft Compliance Extension is a multi-phase process. You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="1773e-144">[デバイスを準備します](#prepare-your-devices)。</span><span class="sxs-lookup"><span data-stu-id="1773e-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="1773e-145">基本的なセットアップ シングル マシンのセルフホスト</span><span class="sxs-lookup"><span data-stu-id="1773e-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="1773e-146">Microsoft エンドポイント マネージャーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1773e-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="1773e-147">グループ ポリシーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1773e-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="1773e-148">拡張機能をテストする</span><span class="sxs-lookup"><span data-stu-id="1773e-148">Test the Extension</span></span>](#test-the-extension)
6. <span data-ttu-id="1773e-149">[アラート管理ダッシュボードを使用して、Chrome DLP アラートを表示する](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)。</span><span class="sxs-lookup"><span data-stu-id="1773e-149">[Use the Alerts Management Dashboard to viewing Chrome DLP alerts](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)</span></span>
7. [<span data-ttu-id="1773e-150">Activity エクスプローラーでの Chrome DLPデータの表示</span><span class="sxs-lookup"><span data-stu-id="1773e-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer)

### <a name="prepare-infrastructure"></a><span data-ttu-id="1773e-151">インフラストラクチャの準備</span><span class="sxs-lookup"><span data-stu-id="1773e-151">Prepare infrastructure</span></span>

<span data-ttu-id="1773e-152">監視しているすべての Windows 10 デバイスに Microsoft Compliance Extension をロールアウトしている場合は、許可されていないアプリのリストおよび許可されていないブラウザーのリストから Google Chrome を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="1773e-153">詳細については、「[許可されていないブラウザー](endpoint-dlp-using.md#unallowed-browsers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1773e-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="1773e-154">少数のデバイスにしかロールアウトしない場合は、Chrome を許可されていないブラウザーまたは許可されていないアプリのリストに残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="1773e-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="1773e-155">Microsoft Compliance Extension がインストールされているコンピューターでは、両方のリストの表示制限が回避されます。</span><span class="sxs-lookup"><span data-stu-id="1773e-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>

### <a name="prepare-your-devices"></a><span data-ttu-id="1773e-156">デバイスを準備する</span><span class="sxs-lookup"><span data-stu-id="1773e-156">Prepare your devices</span></span>

1. <span data-ttu-id="1773e-157">これらのトピックの手順を使用して、デバイスをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="1773e-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="1773e-158">エンドポイント データ損失防止の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="1773e-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="1773e-159">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="1773e-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="1773e-160">エンドポイント DLP のデバイス プロキシとインターネット接続の構成</span><span class="sxs-lookup"><span data-stu-id="1773e-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="1773e-161">基本的なセットアップ シングル マシンのセルフホスト</span><span class="sxs-lookup"><span data-stu-id="1773e-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="1773e-162">これは推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="1773e-162">This is the recommended method.</span></span>

1. <span data-ttu-id="1773e-163">Microsoft Compliance Extension をインストールする Windows 10 コンピューターにサインインし、管理者としてこの PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1773e-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span>

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ```

2. <span data-ttu-id="1773e-164">[Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco) に移動します。</span><span class="sxs-lookup"><span data-stu-id="1773e-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3. <span data-ttu-id="1773e-165">Chrome Web ストアのページに記載されている手順で、拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1773e-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="1773e-166">Microsoft エンドポイント マネージャーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1773e-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="1773e-167">この設定方法は、組織全体の展開に使用します。</span><span class="sxs-lookup"><span data-stu-id="1773e-167">Use this setup method for organization-wide deployments.</span></span>

##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="1773e-168">Microsoft エンドポイント マネージャーで必要なレジストリ キーを有効にする</span><span class="sxs-lookup"><span data-stu-id="1773e-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="1773e-169">次のコンテンツを使用して PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1773e-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. <span data-ttu-id="1773e-170">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1773e-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3. <span data-ttu-id="1773e-171">**[デバイス]** > >  **[スクリプト]** の順に移動し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4. <span data-ttu-id="1773e-172">プロンプトが表示されたら、作成したスクリプトの場所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1773e-172">Browse to the location of the script created when prompted.</span></span>

5. <span data-ttu-id="1773e-173">次の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-173">Select the following settings:</span></span>
    1. <span data-ttu-id="1773e-174">ログオンした資格情報を使用して、このスクリプトを実行する: はい</span><span class="sxs-lookup"><span data-stu-id="1773e-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="1773e-175">スクリプトの署名チェックを強制する: いいえ</span><span class="sxs-lookup"><span data-stu-id="1773e-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="1773e-176">64 ビットの PowerShell ホストでスクリプトを実行する: はい</span><span class="sxs-lookup"><span data-stu-id="1773e-176">Run script in 64-bit PowerShell Host: YES</span></span>

6. <span data-ttu-id="1773e-177">適切なデバイス グループを選択し、ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1773e-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="1773e-178">Microsoft エンドポイント マネージャーの強制インストール手順</span><span class="sxs-lookup"><span data-stu-id="1773e-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="1773e-179">Microsoft Compliance Extension を強制インストールされた拡張機能のリストに追加する前に、Chrome ADMX を取り込むことが重要です。</span><span class="sxs-lookup"><span data-stu-id="1773e-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="1773e-180">Microsoft エンドポイント マネージャーでのこの手順は、Google で以下のとおり文書化されています。[Microsoft Intune を使用して Chrome ブラウザーを管理する - Google Chrome Enterprise ヘルプ](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)</span><span class="sxs-lookup"><span data-stu-id="1773e-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="1773e-181">ADMX を取り込んだ後、以下の手順でこの拡張機能の構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1773e-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1. <span data-ttu-id="1773e-182">Microsoft エンドポイント マネージャー管理センター (https://endpoint.microsoft.com)) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1773e-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2. <span data-ttu-id="1773e-183">構成プロファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="1773e-183">Navigate to Configuration Profiles.</span></span>

3. <span data-ttu-id="1773e-184">**[プロファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-184">Select **Create Profile**.</span></span>

4. <span data-ttu-id="1773e-185">**Windows 10** をプラットフォームとして選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-185">Select **Windows 10** as the platform.</span></span>

5. <span data-ttu-id="1773e-186">プロファイルの種類として **[カスタム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-186">Select **Custom** as profile type.</span></span>

6. <span data-ttu-id="1773e-187">**[設定]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-187">Select the **Settings** tab.</span></span>

7. <span data-ttu-id="1773e-188">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-188">Select **Add**.</span></span>

8. <span data-ttu-id="1773e-189">次のポリシー情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1773e-189">Enter the following policy information.</span></span>

    <span data-ttu-id="1773e-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="1773e-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="1773e-191">データ型: `String`</span><span class="sxs-lookup"><span data-stu-id="1773e-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="1773e-192">値: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="1773e-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9. <span data-ttu-id="1773e-193">[作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1773e-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="1773e-194">グループ ポリシーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1773e-194">Deploy using Group Policy</span></span>

<span data-ttu-id="1773e-195">Microsoft エンドポイント マネージャーを使用しない場合は、グループ ポリシーを使用して Microsoft Compliance Extension を組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="1773e-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="1773e-196">デバイスはグループ ポリシーで管理できる必要があり、すべての Chrome ADMX をグループ ポリシー セントラル ストアにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="1773e-197">詳細については、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1773e-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2. <span data-ttu-id="1773e-198">以下の PowerShell コマンドを使用して、PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1773e-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3. <span data-ttu-id="1773e-199">**グループ ポリシー管理コンソール** を開き、自分の組織単位 (OU) に移動します。</span><span class="sxs-lookup"><span data-stu-id="1773e-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4. <span data-ttu-id="1773e-200">右クリックして、**[このドメインに GPO を作成し、このコンテナーにリンクする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="1773e-201">プロンプトが表示されたら、このグループ ポリシー オブジェクト (GPO) にわかりやすい名前を割り当て、作成を終了します。</span><span class="sxs-lookup"><span data-stu-id="1773e-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5. <span data-ttu-id="1773e-202">GPO を右クリックし、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-202">Right-click the GPO and select **Edit**.</span></span>

6. <span data-ttu-id="1773e-203">**[コンピュータの構成]** > >  **[環境設定]** > >  **[コントロールパネルの設定]** > >  **[スケジュールされたタスク]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1773e-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7. <span data-ttu-id="1773e-204">右クリックして **[新規作成]** > >  **[即時タスク (Windows 7 以降)** を選択して新しい即時タスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="1773e-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8. <span data-ttu-id="1773e-205">タスクに名前と説明をつけます。</span><span class="sxs-lookup"><span data-stu-id="1773e-205">Give the task a name & description.</span></span>

9. <span data-ttu-id="1773e-206">即時タスクを実行するための対応するアカウントを選択します (NT Authority など)。</span><span class="sxs-lookup"><span data-stu-id="1773e-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="1773e-207">**[最上位の特権で実行する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="1773e-208">Windows 10 用のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1773e-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="1773e-209">**[アクション]** タブで、アクション **[プログラムの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="1773e-210">手順 1 で作成した Program/Script のパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1773e-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="1773e-211">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="1773e-212">Chrome 拡張機能を ForceInstall リストに追加する</span><span class="sxs-lookup"><span data-stu-id="1773e-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1. <span data-ttu-id="1773e-213">グループ ポリシー管理エディターで、OU に移動します。</span><span class="sxs-lookup"><span data-stu-id="1773e-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2. <span data-ttu-id="1773e-214">以下のパスを展開します。**[コンピューター/ユーザーの構成]** > >  **[ポリシー]** > >  **[管理用テンプレート]** > >  **[クラシック管理用テンプレート]** > >  **[Google]** > >  **[Google Chrome]** > >  **[拡張機能]**</span><span class="sxs-lookup"><span data-stu-id="1773e-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="1773e-215">このパスは、お使いの構成によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-215">This path may vary depending on your configuration.</span></span>

3. <span data-ttu-id="1773e-216">**[強制インストールした拡張機能リストの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-216">Select **Configure the list of force-installed extensions**.</span></span>

4. <span data-ttu-id="1773e-217">右クリックして、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-217">Right click and select **Edit**.</span></span>

5. <span data-ttu-id="1773e-218">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-218">Select **Enabled**.</span></span>

6. <span data-ttu-id="1773e-219">**[表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-219">Select **Show**.</span></span>

7. <span data-ttu-id="1773e-220">**[値]** の下で、以下のエントリを追加します。`echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="1773e-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8. <span data-ttu-id="1773e-221">**[OK]**、**[適用]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="1773e-222">拡張機能をテストする</span><span class="sxs-lookup"><span data-stu-id="1773e-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="1773e-223">クラウド サービスへのアップロード、または許可されていないブラウザー クラウド エグレスによるアクセス</span><span class="sxs-lookup"><span data-stu-id="1773e-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>

1. <span data-ttu-id="1773e-224">機密性の高いアイテムを作成または取得し、組織の制限されたサービス ドメインの 1 つへのファイルのアップロードを試します。</span><span class="sxs-lookup"><span data-stu-id="1773e-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="1773e-225">機密データは、組み込みの [[機密情報の種類]](sensitive-information-type-entity-definitions.md) のいずれか、またはご所属の組織の機密情報の種類のいずれかに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="1773e-226">テストを行っているデバイスでは、ファイルを開いた場合にこのアクションが許可されていないことを示す DLP トースト通知が表示されることが必要です。</span><span class="sxs-lookup"><span data-stu-id="1773e-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="1773e-227">Chrome での他の DLP シナリオのテスト</span><span class="sxs-lookup"><span data-stu-id="1773e-227">Testing other DLP scenarios in Chrome</span></span>

<span data-ttu-id="1773e-228">許可されていないブラウザー/アプリのリストから Chrome を削除した後、以下のシナリオをテストして、挙動が組織の要件を満たしていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1773e-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="1773e-229">クリップボードを使用して、機密アイテムのデータを他のドキュメントにコピーする</span><span class="sxs-lookup"><span data-stu-id="1773e-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
  - <span data-ttu-id="1773e-230">テストするには、クリップボードへのコピー操作に対して保護されているファイルを Chrome ブラウザーで開き、ファイルからデータのコピーを試します。</span><span class="sxs-lookup"><span data-stu-id="1773e-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
  - <span data-ttu-id="1773e-231">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1773e-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="1773e-232">文書を印刷する</span><span class="sxs-lookup"><span data-stu-id="1773e-232">Print a document</span></span>
  - <span data-ttu-id="1773e-233">テストするには、クリップボードへの印刷操作に対して保護されているファイルを Chrome ブラウザーで開き、ファイルの印刷を試します。</span><span class="sxs-lookup"><span data-stu-id="1773e-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
  - <span data-ttu-id="1773e-234">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1773e-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="1773e-235">USB リムーバブル メディアへのコピー</span><span class="sxs-lookup"><span data-stu-id="1773e-235">Copy to USB Removeable Media</span></span>
  - <span data-ttu-id="1773e-236">テストするには、リムーバブル メディア ストレージへのファイルの保存を試します。</span><span class="sxs-lookup"><span data-stu-id="1773e-236">To test, try to save the file to a removeable media storage.</span></span>
  - <span data-ttu-id="1773e-237">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1773e-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="1773e-238">ネットワーク共有へのコピー</span><span class="sxs-lookup"><span data-stu-id="1773e-238">Copy to Network Share</span></span>
  - <span data-ttu-id="1773e-239">テストするには、ネットワーク共有へのファイルの保存を試します。</span><span class="sxs-lookup"><span data-stu-id="1773e-239">To test, try to save the file to a network share.</span></span>
  - <span data-ttu-id="1773e-240">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1773e-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>

### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="1773e-241">アラート管理ダッシュボードを使用して、Chrome DLP アラートを表示する</span><span class="sxs-lookup"><span data-stu-id="1773e-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="1773e-242">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)の **[データ損失防止]** ページを開き、**[アラート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="1773e-243">エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1773e-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="1773e-244">Activity エクスプローラーでのエンドポイント DLP データの表示</span><span class="sxs-lookup"><span data-stu-id="1773e-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="1773e-245">Microsoft 365 コンプライアンスセンターでドメインの [データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、**Activity エクスプローラー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1773e-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="1773e-246">エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="1773e-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1773e-247">![エンドポイント デバイスのアクティビティ エクスプローラー フィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="1773e-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="1773e-248">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="1773e-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="1773e-249">クラウド エグレスに対する上書きのブロックの適用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1773e-249">Block Override enforcement for cloud egress is not supported.</span></span>
2. <span data-ttu-id="1773e-250">シークレット モードはサポートされていないため、無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1773e-250">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1773e-251">次の手順</span><span class="sxs-lookup"><span data-stu-id="1773e-251">Next steps</span></span>

<span data-ttu-id="1773e-252">デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1773e-252">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="1773e-253">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="1773e-253">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="1773e-254">関連項目</span><span class="sxs-lookup"><span data-stu-id="1773e-254">See also</span></span>

- [<span data-ttu-id="1773e-255">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="1773e-255">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="1773e-256">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="1773e-256">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="1773e-257">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="1773e-257">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="1773e-258">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="1773e-258">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1773e-259">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="1773e-259">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="1773e-260">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1773e-260">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="1773e-261">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="1773e-261">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="1773e-262">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="1773e-262">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="1773e-263">Azure AD に参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="1773e-263">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="1773e-264">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="1773e-264">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
