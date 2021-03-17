---
title: Microsoft Compliance Extension (プレビュー) を開始する
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
ms.openlocfilehash: d71c04433ec369856a510e9fb6382709ecb092f9
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826262"
---
# <a name="get-started-with-microsoft-compliance-extension-preview"></a><span data-ttu-id="1a7be-103">Microsoft Compliance Extension (プレビュー) を開始する</span><span class="sxs-lookup"><span data-stu-id="1a7be-103">Get started with Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="1a7be-104">以下の手順を使用して、Microsoft Compliance Extension をロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="1a7be-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1a7be-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="1a7be-105">Before you begin</span></span>

<span data-ttu-id="1a7be-106">Microsoft Compliance Extension を使用するには、デバイスがエンドポイント DLP に搭載されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="1a7be-107">DLP やエンドポイント DLP に慣れていない場合は、これらの記事をレビューします</span><span class="sxs-lookup"><span data-stu-id="1a7be-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="1a7be-108">Microsoft Compliance Extension の詳細</span><span class="sxs-lookup"><span data-stu-id="1a7be-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="1a7be-109">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="1a7be-109">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="1a7be-110">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="1a7be-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1a7be-111">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="1a7be-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="1a7be-112">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="1a7be-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="1a7be-113">エンドポイント データ損失防止の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="1a7be-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="1a7be-114">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="1a7be-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="1a7be-115">エンドポイント DLP のデバイス プロキシとインターネット接続の構成</span><span class="sxs-lookup"><span data-stu-id="1a7be-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="1a7be-116">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="1a7be-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="1a7be-117">SKU /サブスクリプション ライセンス</span><span class="sxs-lookup"><span data-stu-id="1a7be-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="1a7be-118">開始する前に、「[Microsoft 365サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」とアドオンを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1a7be-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="1a7be-119">Endpoint DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a7be-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="1a7be-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1a7be-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="1a7be-121">Microsoft 365 A5 (EDU) </span><span class="sxs-lookup"><span data-stu-id="1a7be-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="1a7be-122">Microsoft 365 E5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1a7be-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="1a7be-123">Microsoft 365 A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1a7be-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="1a7be-124">Microsoft 365 E5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="1a7be-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="1a7be-125">Microsoft 365 A5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="1a7be-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="1a7be-126">ライセンスのガイダンスに関する詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a7be-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="1a7be-127">ご所属の組織で エンドポイント DLP のライセンスを取得している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="1a7be-128">デバイスで Windows 10 x64 ビルド 1809 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="1a7be-129">デバイスで Antimalware Client バージョン 4.18.2101.9 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="1a7be-130">**Windows セキュリティ** アプリを開いて現在のバージョンを確認し、**[設定]** アイコンを選択して、**[バージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="1a7be-131">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1a7be-131">Permissions</span></span>

<span data-ttu-id="1a7be-132">Endpoint DLP からのデータは、[Activity エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="1a7be-133">Activity エクスプローラーに権限を付与する役割は 7 つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1a7be-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="1a7be-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="1a7be-134">Global admin</span></span>
- <span data-ttu-id="1a7be-135">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="1a7be-135">Compliance admin</span></span>
- <span data-ttu-id="1a7be-136">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="1a7be-136">Security admin</span></span>
- <span data-ttu-id="1a7be-137">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="1a7be-137">Compliance data admin</span></span>
- <span data-ttu-id="1a7be-138">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="1a7be-138">Global reader</span></span>
- <span data-ttu-id="1a7be-139">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="1a7be-139">Security reader</span></span>
- <span data-ttu-id="1a7be-140">レポート閲覧者</span><span class="sxs-lookup"><span data-stu-id="1a7be-140">Reports reader</span></span>

### <a name="chrome-dependency"></a><span data-ttu-id="1a7be-141">Chrome の依存関係</span><span class="sxs-lookup"><span data-stu-id="1a7be-141">Chrome dependency</span></span>

<span data-ttu-id="1a7be-142">Microsoft Compliance Extension は、現在の Chrome のバージョンと過去 3 つのバージョンに対応しています。</span><span class="sxs-lookup"><span data-stu-id="1a7be-142">The Microsoft Compliance Extension is supported for the current version of Chrome and the past three versions.</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="1a7be-143">インストールの全体的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="1a7be-143">Overall installation workflow</span></span>

<span data-ttu-id="1a7be-144">Microsoft Compliance Extension の導入は、複数の手順を踏まえて行われます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-144">Deploying Microsoft Compliance Extension is a multi-phase process.</span></span> <span data-ttu-id="1a7be-145">一度に 1 台のマシンにインストールするか、Microsoft エンドポイント マネージャーやグループ ポリシーを使用して組織全体に展開するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-145">You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="1a7be-146">[デバイスを準備します](#prepare-your-devices)。</span><span class="sxs-lookup"><span data-stu-id="1a7be-146">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="1a7be-147">基本的なセットアップ シングル マシンのセルフホスト</span><span class="sxs-lookup"><span data-stu-id="1a7be-147">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="1a7be-148">Microsoft エンドポイント マネージャーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1a7be-148">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="1a7be-149">グループ ポリシーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1a7be-149">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="1a7be-150">拡張機能をテストする</span><span class="sxs-lookup"><span data-stu-id="1a7be-150">Test the Extension</span></span>](#test-the-extension)
6. <span data-ttu-id="1a7be-151">[アラート管理ダッシュボードを使用して、Chrome DLP アラートを表示する](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)。</span><span class="sxs-lookup"><span data-stu-id="1a7be-151">[Use the Alerts Management Dashboard to viewing Chrome DLP alerts](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)</span></span>
7. [<span data-ttu-id="1a7be-152">Activity エクスプローラーでの Chrome DLPデータの表示</span><span class="sxs-lookup"><span data-stu-id="1a7be-152">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a><span data-ttu-id="1a7be-153">インフラストラクチャの準備</span><span class="sxs-lookup"><span data-stu-id="1a7be-153">Prepare infrastructure</span></span>

<span data-ttu-id="1a7be-154">監視しているすべての Windows 10 デバイスに Microsoft Compliance Extension を展開している場合は、許可されていないアプリのリストから Google Chrome を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-154">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed apps list.</span></span> <span data-ttu-id="1a7be-155">詳細については、「[許可されていないブラウザー](endpoint-dlp-using.md#unallowed-browsers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a7be-155">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="1a7be-156">少数のデバイスにしか展開しない場合は、Chrome を許可しないブラウザーのリストに残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-156">If you are only rolling it out to a few devices you can leave Chrome on the unallowed browser list.</span></span> <span data-ttu-id="1a7be-157">Microsoft Compliance Extension がインストールされているコンピューターでは、許可されていないアプリの表示制限が回避されます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-157">The Microsoft Compliance Extension will bypass the restrictions of the unallowed apps list for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="1a7be-158">デバイスを準備する</span><span class="sxs-lookup"><span data-stu-id="1a7be-158">Prepare your devices</span></span>

1. <span data-ttu-id="1a7be-159">これらのトピックの手順を使用して、デバイスをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="1a7be-159">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="1a7be-160">エンドポイント データ損失防止の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="1a7be-160">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="1a7be-161">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="1a7be-161">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="1a7be-162">エンドポイント DLP のデバイス プロキシとインターネット接続の構成</span><span class="sxs-lookup"><span data-stu-id="1a7be-162">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="1a7be-163">基本的なセットアップ シングル マシンのセルフホスト</span><span class="sxs-lookup"><span data-stu-id="1a7be-163">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="1a7be-164">これは推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="1a7be-164">This is the recommended method.</span></span> 

1. <span data-ttu-id="1a7be-165">Microsoft Compliance Extension をインストールする Windows 10 コンピューターにサインオンし、管理者としてこの PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-165">Sign on to the Windows 10 computer that you want to install the Microsoft Compliance Extension on and run the this PowerShell script as an administrator.</span></span> 

```powershell
Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
``` 

2.  <span data-ttu-id="1a7be-166">[Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco) に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-166">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>
3.  <span data-ttu-id="1a7be-167">Chrome Web ストアのページに記載されている手順で、拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a7be-167">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="1a7be-168">Microsoft エンドポイント マネージャーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1a7be-168">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="1a7be-169">この設定方法は、組織全体の展開に使用します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-169">Use this setup method for organization Wide deployments</span></span> 

##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="1a7be-170">Microsoft エンドポイント マネージャーで必要なレジストリ キーを有効にする</span><span class="sxs-lookup"><span data-stu-id="1a7be-170">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="1a7be-171">次のコンテンツを使用して PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-171">Create a PowerShell script with the following contents:</span></span>
```powershell
Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```
2.  <span data-ttu-id="1a7be-172">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1a7be-172">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>
3.  <span data-ttu-id="1a7be-173">**[デバイス]** > >  **[スクリプト]** の順に移動し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-173">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>
4.  <span data-ttu-id="1a7be-174">プロンプトが表示されたら、作成したスクリプトの場所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a7be-174">Browse to the location of the script created when prompted.</span></span>
5.  <span data-ttu-id="1a7be-175">次の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-175">Select the following settings:</span></span>
    1. <span data-ttu-id="1a7be-176">ログオンした資格情報を使用して、このスクリプトを実行する: はい</span><span class="sxs-lookup"><span data-stu-id="1a7be-176">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="1a7be-177">スクリプトの署名チェックを強制する: いいえ</span><span class="sxs-lookup"><span data-stu-id="1a7be-177">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="1a7be-178">64 ビットの PowerShell ホストでスクリプトを実行する: はい</span><span class="sxs-lookup"><span data-stu-id="1a7be-178">Run script in 64-bit PowerShell Host: YES</span></span>
6.  <span data-ttu-id="1a7be-179">適切なデバイス グループを選択し、ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-179">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="1a7be-180">Microsoft エンドポイント マネージャーの強制インストール手順</span><span class="sxs-lookup"><span data-stu-id="1a7be-180">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="1a7be-181">Microsoft Compliance Extension を強制インストールされた拡張機能のリストに追加する前に、Chrome ADMX を取り込むことが重要です。</span><span class="sxs-lookup"><span data-stu-id="1a7be-181">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="1a7be-182">Microsoft エンドポイント マネージャーでのこの手順は、Google で以下のとおり文書化されています。[Microsoft Intune を使用して Chrome ブラウザーを管理する - Google Chrome Enterprise ヘルプ](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)</span><span class="sxs-lookup"><span data-stu-id="1a7be-182">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="1a7be-183">ADMX を取り込んだ後、以下の手順でこの拡張機能の構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-183">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="1a7be-184">Microsoft エンドポイント マネージャー管理センター (https://endpoint.microsoft.com)) にサインインします</span><span class="sxs-lookup"><span data-stu-id="1a7be-184">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com)</span></span>
2.  <span data-ttu-id="1a7be-185">構成プロファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-185">Navigate to Configuration Profiles.</span></span>
3.  <span data-ttu-id="1a7be-186">**[プロファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-186">Select **Create Profile**.</span></span>
4.  <span data-ttu-id="1a7be-187">**Windows 10** をプラットフォームとして選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-187">Select **Windows 10** as the platform.</span></span>
5.  <span data-ttu-id="1a7be-188">プロファイルの種類として **[カスタム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-188">Select **Custom** as profile type.</span></span>
6.  <span data-ttu-id="1a7be-189">**[設定]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-189">Select the **Settings** tab.</span></span>
7.  <span data-ttu-id="1a7be-190">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-190">Select **Add**.</span></span>
8.  <span data-ttu-id="1a7be-191">次のポリシー情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-191">Enter the following policy information.</span></span>
<span data-ttu-id="1a7be-192">OMA-URI: ./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist Data type: String Value: <enabled/><data id=”ExtensionInstallForcelistDesc” value=”1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/></span><span class="sxs-lookup"><span data-stu-id="1a7be-192">OMA-URI: ./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist Data type: String Value: <enabled/><data id=”ExtensionInstallForcelistDesc” value=”1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/></span></span>

9.  <span data-ttu-id="1a7be-193">[作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7be-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="1a7be-194">グループ ポリシーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="1a7be-194">Deploy using Group Policy</span></span>

<span data-ttu-id="1a7be-195">Microsoft エンドポイント マネージャーを使用しない場合は、グループ ポリシーを使用して Microsoft Compliance Extension を組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="1a7be-196">デバイスはグループ ポリシーで管理できる必要があり、すべての Chrome ADMX をグループ ポリシー セントラル ストアにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="1a7be-197">詳細については、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a7be-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>
2.  <span data-ttu-id="1a7be-198">以下を使用して、PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-198">Create a PowerShell script using this:</span></span>

```powershell
et-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

3.  <span data-ttu-id="1a7be-199">**グループ ポリシー管理コンソール** を開き、自分の組織単位 (OU) に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>
4.  <span data-ttu-id="1a7be-200">右クリックして、**[このドメインに GPO を作成し、このコンテナーにリンクする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="1a7be-201">プロンプトが表示されたら、このグループ ポリシー オブジェクト (GPO) にわかりやすい名前を割り当て、作成を終了します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>
5.  <span data-ttu-id="1a7be-202">GPO を右クリックし、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-202">Right-click the GPO and select **Edit**.</span></span>
6.  <span data-ttu-id="1a7be-203">**[コンピュータの構成]** > >  **[環境設定]** > >  **[コントロールパネルの設定]** > >  **[スケジュールされたタスク]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>
7.  <span data-ttu-id="1a7be-204">右クリックして **[新規作成]** > >  **[即時タスク (Windows 7 以降)** を選択して新しい即時タスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>
8.  <span data-ttu-id="1a7be-205">タスクに名前と説明をつけます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-205">Give the task a name & description.</span></span>
9.  <span data-ttu-id="1a7be-206">即時タスクを実行するための対応するアカウントを選択します (NT Authority など)。</span><span class="sxs-lookup"><span data-stu-id="1a7be-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>
10. <span data-ttu-id="1a7be-207">**[最上位の特権で実行する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-207">Select **Run with highest privileges**.</span></span>
11. <span data-ttu-id="1a7be-208">Windows 10 用のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-208">Configure the policy for Windows 10.</span></span>
12. <span data-ttu-id="1a7be-209">**[アクション]** タブで、アクション **[プログラムの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-209">In the **Actions** tab, select the action **Start a program**.</span></span>
13. <span data-ttu-id="1a7be-210">手順 1 で作成した Program/Script のパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-210">Enter the path to the Program/Script created in Step 1.</span></span>
14. <span data-ttu-id="1a7be-211">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="1a7be-212">Chrome 拡張機能を ForceInstall リストに追加する</span><span class="sxs-lookup"><span data-stu-id="1a7be-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="1a7be-213">グループ ポリシー管理エディターで、OU に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-213">In the Group Policy Management Editor, navigate to your OU.</span></span>
2.  <span data-ttu-id="1a7be-214">以下のパスを展開します。**[コンピューター/ユーザーの構成]** > >  **[ポリシー]** > >  **[管理用テンプレート]** > >  **[クラシック管理用テンプレート]** > >  **[Google]** > >  **[Google Chrome]** > >  **[拡張機能]**</span><span class="sxs-lookup"><span data-stu-id="1a7be-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="1a7be-215">このパスは、お使いの構成によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-215">This path may vary depending on your configuration.</span></span>
3.  <span data-ttu-id="1a7be-216">**[強制インストールした拡張機能リストの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-216">Select **Configure the list of force-installed extensions**.</span></span>
4.  <span data-ttu-id="1a7be-217">右クリックして、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-217">Right click and select **Edit**.</span></span>
5.  <span data-ttu-id="1a7be-218">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-218">Select **Enabled**.</span></span>
6.  <span data-ttu-id="1a7be-219">**[表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-219">Select **Show**.</span></span>
7.  <span data-ttu-id="1a7be-220">**[値]** の下で、以下のエントリを追加します。`echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="1a7be-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>
8.  <span data-ttu-id="1a7be-221">**[OK]**、**[適用]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="1a7be-222">拡張機能をテストする</span><span class="sxs-lookup"><span data-stu-id="1a7be-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="1a7be-223">クラウド サービスへのアップロード、または許可されていないブラウザー クラウド エグレスによるアクセス</span><span class="sxs-lookup"><span data-stu-id="1a7be-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="1a7be-224">機密性の高いアイテムを作成または取得し、組織の制限されたサービス ドメインの 1 つへのファイルのアップロードを試します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="1a7be-225">機密データは、組み込みの [[機密情報の種類]](sensitive-information-type-entity-definitions.md) のいずれか、またはご所属の組織の機密情報の種類のいずれかに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7be-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="1a7be-226">テストを行っているデバイスでは、ファイルを開いた場合にこのアクションが許可されていないことを示す DLP トースト通知が表示されることが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a7be-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="1a7be-227">Chrome での他の DLP シナリオのテスト</span><span class="sxs-lookup"><span data-stu-id="1a7be-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="1a7be-228">許可されていないブラウザー/アプリのリストから Chrome を削除した後、以下のシナリオをテストして、挙動が組織の要件を満たしていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="1a7be-229">クリップボードを使用して、機密アイテムのデータを他のドキュメントにコピーする</span><span class="sxs-lookup"><span data-stu-id="1a7be-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="1a7be-230">テストするには、クリップボードへのコピー操作に対して保護されているファイルを Chrome ブラウザーで開き、ファイルからデータのコピーを試します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="1a7be-231">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="1a7be-232">文書を印刷する</span><span class="sxs-lookup"><span data-stu-id="1a7be-232">Print a document</span></span>
    - <span data-ttu-id="1a7be-233">テストするには、クリップボードへの印刷操作に対して保護されているファイルを Chrome ブラウザーで開き、ファイルの印刷を試します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="1a7be-234">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="1a7be-235">USB リムーバブル メディアへのコピー</span><span class="sxs-lookup"><span data-stu-id="1a7be-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="1a7be-236">テストするには、リムーバブル メディア ストレージへのファイルの保存を試します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="1a7be-237">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="1a7be-238">ネットワーク共有へのコピー</span><span class="sxs-lookup"><span data-stu-id="1a7be-238">Copy to Network Share</span></span>
    - <span data-ttu-id="1a7be-239">テストするには、ネットワーク共有へのファイルの保存を試します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="1a7be-240">予想される結果ファイルを開いた場合に、この操作が許可されていないことを示す DLP トースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a7be-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="1a7be-241">アラート管理ダッシュボードを使用して、Chrome DLP アラートを表示する</span><span class="sxs-lookup"><span data-stu-id="1a7be-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="1a7be-242">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)の **[データ損失防止]** ページを開き、**[アラート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="1a7be-243">エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a7be-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="1a7be-244">Activity エクスプローラーでのエンドポイント DLP データの表示</span><span class="sxs-lookup"><span data-stu-id="1a7be-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="1a7be-245">Microsoft 365 コンプライアンスセンターでドメインの [データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、**Activity エクスプローラー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="1a7be-246">エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="1a7be-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1a7be-247">![エンドポイント デバイスのアクティビティ エクスプローラー フィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="1a7be-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="1a7be-248">次の手順</span><span class="sxs-lookup"><span data-stu-id="1a7be-248">Next steps</span></span>
<span data-ttu-id="1a7be-249">デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a7be-249">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="1a7be-250">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="1a7be-250">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="1a7be-251">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="1a7be-251">See also</span></span>

- [<span data-ttu-id="1a7be-252">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="1a7be-252">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="1a7be-253">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="1a7be-253">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="1a7be-254">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="1a7be-254">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="1a7be-255">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="1a7be-255">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1a7be-256">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="1a7be-256">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="1a7be-257">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a7be-257">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="1a7be-258">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="1a7be-258">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="1a7be-259">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="1a7be-259">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="1a7be-260">Azure AD に参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="1a7be-260">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="1a7be-261">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="1a7be-261">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
