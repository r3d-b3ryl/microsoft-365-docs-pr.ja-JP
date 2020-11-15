---
title: Microsoft 365 エンドポイント データ損失防止を開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
description: Microsoft 365 エンドポイントのデータ損失防止を設定して、ファイルアクティビティを監視し、それらのファイルの保護アクションをエンドポイントに実装します。
ms.openlocfilehash: 6ba3b83d634f946f818890a732a83166f346162d
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073096"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="6c79d-103">エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="6c79d-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="6c79d-p101">Microsoft エンドポイント データ損失防止 (エンドポイント DLP) は、Microsoft 365 サービス全体の機密アイテムを検出して保護するために使用できる Microsoft 365 データ損失防止 (DLP) スイート機能の一部です。Microsoft のあらゆる DLP サービスの詳細については、「[データ損失防止の概要](data-loss-prevention-policies.md)」を参照してください。エンドポイント DLP の詳細については、「[エンドポイントのデータ損失防止について](endpoint-dlp-learn-about.md)」を参照してください。 </span><span class="sxs-lookup"><span data-stu-id="6c79d-p101">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services. For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md). To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="6c79d-p102">Microsoft エンドポイント DLP を使用すると、Windows 10 デバイスを監視し、機密アイテムが使用され、共有されていることを検出できます。これにより、それらが適切に使用され、保護されていることを確認し、それらを危険にさらす可能性のある危険な動作を防ぐために必要な可視性と制御が得られます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p102">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared. This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6c79d-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="6c79d-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="6c79d-110">SKU /サブスクリプション ライセンス</span><span class="sxs-lookup"><span data-stu-id="6c79d-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="6c79d-p103">エンドポイント DLP の使用を開始する前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)とアドオンを確認する必要があります。エンドポイント DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p103">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons. To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="6c79d-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6c79d-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="6c79d-114">Microsoft 365 A5 (EDU) </span><span class="sxs-lookup"><span data-stu-id="6c79d-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="6c79d-115">Microsoft 365 E5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="6c79d-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="6c79d-116">Microsoft 365 A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="6c79d-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="6c79d-117">Microsoft 365 E5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="6c79d-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="6c79d-118">Microsoft 365 A5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="6c79d-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="6c79d-119">許可</span><span class="sxs-lookup"><span data-stu-id="6c79d-119">Permissions</span></span>

<span data-ttu-id="6c79d-120">デバイス管理を有効にするには、使用するアカウントが次のいずれかの役割のメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6c79d-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="6c79d-121">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-121">Global admin</span></span>
- <span data-ttu-id="6c79d-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-122">Security admin</span></span>
- <span data-ttu-id="6c79d-123">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-123">Compliance admin</span></span>

<span data-ttu-id="6c79d-124">カスタムアカウントを使用してデバイス管理設定を表示する場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6c79d-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="6c79d-125">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-125">Global admin</span></span>
- <span data-ttu-id="6c79d-126">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-126">Compliance admin</span></span>
- <span data-ttu-id="6c79d-127">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-127">Compliance data admin</span></span>
- <span data-ttu-id="6c79d-128">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="6c79d-128">Global reader</span></span>

<span data-ttu-id="6c79d-129">カスタムアカウントを使用してオンボーディング/オフボーディングページにアクセスする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6c79d-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="6c79d-130">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-130">Global admin</span></span>
- <span data-ttu-id="6c79d-131">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-131">Compliance admin</span></span>

<span data-ttu-id="6c79d-132">カスタムアカウントを使用してデバイスの監視をオン/オフにする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6c79d-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="6c79d-133">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-133">Global admin</span></span>
- <span data-ttu-id="6c79d-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-134">Compliance admin</span></span>

<span data-ttu-id="6c79d-p104">エンドポイント DLP からのデータは、[アクティビティ エクスプローラー](data-classification-activity-explorer.md)で表示できます。アクティビティ エクスプローラーへのアクセス許可を付与する役割は 4 つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p104">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="6c79d-137">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-137">Global admin</span></span>
- <span data-ttu-id="6c79d-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-138">Compliance admin</span></span>
- <span data-ttu-id="6c79d-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-139">Security admin</span></span>
- <span data-ttu-id="6c79d-140">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="6c79d-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="6c79d-141">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="6c79d-141">Prepare your endpoints</span></span>

<span data-ttu-id="6c79d-142">これらの要件を満たすために、Endpoint DLP の導入を計画している Windows 10 デバイスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="6c79d-143">Windows 10 x64 ビルド 1809 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c79d-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="6c79d-p105">マルウェア対策クライアントのバージョンは、4.18.2009.7 以降です。Windows セキュリティ アプリを開いて現在のバージョンを確認し、[設定] アイコンを選び、[バージョン情報] を選択します。バージョン番号はマルウェア対策クライアント バージョンの下に表示されます。Windows Update KB4052623 をインストールして、最新のマルウェア対策クライアント バージョンに更新します。注: Windows セキュリティ コンポーネントをアクティブにする必要はありません。エンドポイント DLP は、Windows セキュリティの状態に関係なく実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p105">Antimalware Client Version is 4.18.2009.7 or newer. Check your current version by opening Windows Security app, select the Settings icon, and then select About. The version number is listed under Antimalware Client Version. Update to the latest Antimalware Client Version by installing Windows Update KB4052623. Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="6c79d-p106">次の Windows Update がインストールされています。注: これらの更新プログラムは、デバイスをエンドポイント DLP にオンボードするための前提条件ではありませんが、重要な問題の修正が含まれているため、製品を使用する前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p106">The following Windows Updates are installed. Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="6c79d-151">Windows 10 1809 の場合 - KB4559003、KB4577069、KB4580390</span><span class="sxs-lookup"><span data-stu-id="6c79d-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="6c79d-152">Windows 10 1903 または 1909 の場合 - KB4559004、KB4577062、KB4580386</span><span class="sxs-lookup"><span data-stu-id="6c79d-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="6c79d-153">Windows 10 2004 の場合 - KB4568831、KB4577063</span><span class="sxs-lookup"><span data-stu-id="6c79d-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="6c79d-154">Office 2016 を実行しているデバイスの場合 (他の Office バージョンではない) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="6c79d-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="6c79d-155">すべてのデバイスは [Azure Active Directory (Azure AD) に参加する ](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)か、Hybrid Azure AD に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c79d-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="6c79d-p107">エンドポイント デバイスに Microsoft Chromium Edge ブラウザーをインストールして、クラウドへのアップロード アクティビティのポリシー アクションを適用します。詳しくは、「[Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p107">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity. See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="6c79d-p108">Microsoft 365 Apps バージョン 2004 - 2008 の月次エンタープライズ チャネルを使用している場合、Office コンテンツを分類するエンドポイント DLP に既知の問題があり、バージョン 2009 以降に更新する必要があります。現在のバージョンについては「[Microsoft 365 アプリの更新履歴 (日付別の一覧)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)」をご覧ください。この問題の詳細については、[2020 年の最新のチャネル リリースのリリース ノート](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27)の「Office スイート」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p108">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later. See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions. To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="6c79d-161">デバイス管理へのデバイスのオンボーディング</span><span class="sxs-lookup"><span data-stu-id="6c79d-161">Onboarding devices into device management</span></span>

<span data-ttu-id="6c79d-p109">デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードする必要があります。これらのアクションはどちらも Microsoft 365 コンプライアンス ポータルで行われます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p109">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device. Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="6c79d-p110">まだオンボードされていないデバイスをオンボードする場合は、適切なスクリプトをダウンロードして、それらのデバイスに展開します。「[デバイスのオンボーディング](endpoint-dlp-getting-started.md#onboarding-devices)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p110">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices. Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="6c79d-p111">既に [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) にオンボードされているデバイスがある場合、それらは管理対象デバイスのリストに表示されます。「[Microsoft Defender for Endpoint にオンボードされているデバイスを使用する](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p111">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list. Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="6c79d-168">デバイスのオンボーディング</span><span class="sxs-lookup"><span data-stu-id="6c79d-168">Onboarding devices</span></span>

<span data-ttu-id="6c79d-169">この導入シナリオでは、まだオンボーディングされていないデバイスをオンボードし、Windows 10 デバイスで意図しない共有から機密アイテムを監視および保護します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-169">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="6c79d-170">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-170">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="6c79d-171">コンプライアンスセンターの設定ページを開き、[ **オンボードデバイス** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-171">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c79d-172">![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="6c79d-172">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="6c79d-173">通常は、デバイスのオンボーディングが有効になるまでに約 60 秒かかりますが、Microsoft サポートを利用する前に最大 30 分お待ちください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-173">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="6c79d-p112">**[デバイス管理]** を選択して、 **[デバイス]** リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p112">Choose **Device management** to open the **Devices** list. The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="6c79d-176">オンボーディング プロセスを開始するには、 **[オンボーディング]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-176">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="6c79d-177">これらの追加デバイスに導入する方法を[ **導入方法** ]リストから選択し、 **パッケージをダウンロード** します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-177">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c79d-178">![展開方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="6c79d-178">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="6c79d-p113">「[Windows 10 マシンのオンボーディング ツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。このリンクをクリックすると、手順 5 で選択した展開パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p113">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="6c79d-181">グループポリシーを使用したWindows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-181">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="6c79d-182">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-182">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="6c79d-183">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-183">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="6c79d-184">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-184">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="6c79d-185">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="6c79d-185">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="6c79d-186">完了後、エンドポイントがオンボードされ、デバイス リストに表示されます。アクティビティ エクスプローラーへの監査アクティビティ ログのレポートも開始されます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-186">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="6c79d-p114">これは、ライセンス執行時でのエクスペリエンスです。 必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p114">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="6c79d-189">Microsoft Defender for Endpoint にオンボードされているデバイスを使用する</span><span class="sxs-lookup"><span data-stu-id="6c79d-189">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="6c79d-p115">このシナリオでは、既に Microsoft Defender for Endpoint が展開されていて、レポートしているエンドポイントがあります。これらのすべてのエンドポイントが管理対象デバイスのリストに表示されます。「[デバイスのオンボーディング](endpoint-dlp-getting-started.md#onboarding-devices)」の手順を使用して、引き続き新しいデバイスをエンドポイント DLP にオンボードしてカバレッジを拡大することができます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p115">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in. All these endpoints will appear in the managed devices list. You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="6c79d-193">[Microsoft コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-193">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="6c79d-194">コンプライアンス センターの設定ページを開き、 **[デバイスの監視を有効にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-194">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="6c79d-p116">**[デバイス管理]** を選択して、 **[デバイス]** リストを開きます。既に Microsoft Defender for Endpoint にレポートしているデバイスのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p116">Choose **Device management** to open the **Devices** list. You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c79d-197">![デバイス管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="6c79d-197">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="6c79d-198">追加のデバイスをオンボードする必要がある場合は、[ **オンボーディング** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-198">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="6c79d-199">これらの追加デバイスに展開する方法を **[展開方法]** リストから選択し、 **パッケージをダウンロード** します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-199">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="6c79d-p117">「[Windows 10 マシンのオンボーディング ツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。このリンクをクリックすると、手順 5 で選択した展開パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p117">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="6c79d-202">グループポリシーを使用したWindows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-202">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="6c79d-203">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-203">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="6c79d-204">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-204">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="6c79d-205">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="6c79d-205">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="6c79d-206">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="6c79d-206">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="6c79d-207">完了後、エンドポイントがオンボードされ、 **[デバイス]** テーブルに表示され、 **アクティビティ エクスプローラー** に監査ログのレポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-207">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="6c79d-p118">これは、ライセンス執行時でのエクスペリエンスです。 必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6c79d-p118">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="6c79d-210">DLP アラート管理ダッシュボードでのエンドポイント DLP アラートの表示</span><span class="sxs-lookup"><span data-stu-id="6c79d-210">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="6c79d-211">Microsoft 365 コンプライアンス センターの [データ損失防止] ページを開き、[アラート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-211">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="6c79d-212">エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-212">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="6c79d-213">アクティビティ エクスプローラーでのエンドポイント DLP データの表示</span><span class="sxs-lookup"><span data-stu-id="6c79d-213">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="6c79d-214">Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-214">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="6c79d-215">エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6c79d-215">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c79d-216">![エンドポイント デバイスのアクティビティ エクスプローラー フィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="6c79d-216">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c79d-217">次の手順</span><span class="sxs-lookup"><span data-stu-id="6c79d-217">Next steps</span></span>
<span data-ttu-id="6c79d-218">デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c79d-218">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="6c79d-219">エンドポイントのデータ損失防止の使用 (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="6c79d-219">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="6c79d-220">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="6c79d-220">See also</span></span>

- [<span data-ttu-id="6c79d-221">エンドポイントのデータ損失防止について学ぶ (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="6c79d-221">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="6c79d-222">エンドポイントのデータ損失防止の使用 (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="6c79d-222">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="6c79d-223">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="6c79d-223">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="6c79d-224">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="6c79d-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="6c79d-225">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="6c79d-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="6c79d-226">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c79d-226">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="6c79d-227">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="6c79d-227">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="6c79d-228">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="6c79d-228">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="6c79d-229">Azure AD に参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="6c79d-229">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="6c79d-230">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="6c79d-230">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
