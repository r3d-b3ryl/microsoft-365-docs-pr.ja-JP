---
title: Microsoft 365 Endpoint データ損失防止 (プレビュー) を開始する
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
ms.openlocfilehash: 82ba434d1874ce57abcf0bcc4b60858e0e2ccbf8
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779215"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="7285e-103">Endpoint Data Loss Prevention (プレビュー) を開始する</span><span class="sxs-lookup"><span data-stu-id="7285e-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="7285e-104">Microsoft Endpoint Data Loss Prevention (Endpoint DLP) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="7285e-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="7285e-105">Microsoft のすべての DLP製品 の詳細については、 「[データ損失防止の概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7285e-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="7285e-106">Endpoint DLP の詳細については、「[Endpoint のデータ損失防止について (プレビュー) ](endpoint-dlp-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7285e-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="7285e-107">Microsoft Endpoint DLP は、Windows 10 デバイスを監視し、機密性の高いアイテムが使用および共有されていることを検出します。</span><span class="sxs-lookup"><span data-stu-id="7285e-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="7285e-108">これにより、適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="7285e-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7285e-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="7285e-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="7285e-110">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="7285e-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="7285e-111">Endpoint DLP を開始する前に、「[Microsoft 365サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」とアドオンを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7285e-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="7285e-112">Endpoint DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="7285e-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="7285e-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7285e-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="7285e-114">Microsoft 365 A5 (EDU) </span><span class="sxs-lookup"><span data-stu-id="7285e-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="7285e-115">Microsoft 365 E5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7285e-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="7285e-116">Microsoft 365 A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7285e-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="7285e-117">Microsoft 365 E5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="7285e-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="7285e-118">Microsoft 365 A5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="7285e-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="7285e-119">許可</span><span class="sxs-lookup"><span data-stu-id="7285e-119">Permissions</span></span>

<span data-ttu-id="7285e-120">デバイス管理を有効にするには、使用するアカウントが次のいずれかの役割のメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7285e-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="7285e-121">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-121">Global admin</span></span>
- <span data-ttu-id="7285e-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-122">Security admin</span></span>
- <span data-ttu-id="7285e-123">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-123">Compliance admin</span></span>

<span data-ttu-id="7285e-124">カスタムアカウントを使用してデバイス管理設定を表示する場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7285e-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="7285e-125">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-125">Global admin</span></span>
- <span data-ttu-id="7285e-126">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-126">Compliance admin</span></span>
- <span data-ttu-id="7285e-127">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-127">Compliance data admin</span></span>
- <span data-ttu-id="7285e-128">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="7285e-128">Global reader</span></span>

<span data-ttu-id="7285e-129">カスタムアカウントを使用してオンボーディング/オフボーディングページにアクセスする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7285e-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="7285e-130">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-130">Global admin</span></span>
- <span data-ttu-id="7285e-131">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-131">Compliance admin</span></span>

<span data-ttu-id="7285e-132">カスタムアカウントを使用してデバイスの監視をオン/オフにする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7285e-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="7285e-133">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-133">Global admin</span></span>
- <span data-ttu-id="7285e-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-134">Compliance admin</span></span>

<span data-ttu-id="7285e-135">Endpoint DLP からのデータは、[Activity エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="7285e-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="7285e-136">Activity エクスプローラーに権限を付与する役割は4つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7285e-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="7285e-137">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-137">Global admin</span></span>
- <span data-ttu-id="7285e-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-138">Compliance admin</span></span>
- <span data-ttu-id="7285e-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-139">Security admin</span></span>
- <span data-ttu-id="7285e-140">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="7285e-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="7285e-141">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="7285e-141">Prepare your endpoints</span></span>

<span data-ttu-id="7285e-142">これらの要件を満たすために、Endpoint DLP の導入を計画している Windows 10 デバイスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7285e-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="7285e-143">Windows 10 x64 ビルド 1809 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7285e-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="7285e-144">マルウェア対策クライアントのバージョンは 4.18.2009.7 以降です。</span><span class="sxs-lookup"><span data-stu-id="7285e-144">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="7285e-145">Windows セキュリティ アプリを開いて現在のバージョンを確認し、[設定] アイコンを選択して、[バージョン情報] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7285e-145">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="7285e-146">バージョン番号は、マルウェア対策クライアントのバージョンの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7285e-146">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="7285e-147">Windows Update KB4052623 をインストールして、最新のマルウェア対策クライアントのバージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="7285e-147">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> <span data-ttu-id="7285e-148">注: Windows セキュリティ コンポーネントはいずれもアクティブである必要はありません。Windows セキュリティの状態に関係なくエンドポイント DLP を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7285e-148">Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="7285e-149">次の Windows Update がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7285e-149">The following Windows Updates are installed.</span></span> <span data-ttu-id="7285e-150">注: これらの更新プログラムは、デバイスをエンドポイント DLP にオンボードするための前提条件ではありませんが、重要な問題の修正が含まれているため、製品を使用する前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7285e-150">Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="7285e-151">Windows 10 1809 の場合 - KB4559003、KB4577069、KB4580390</span><span class="sxs-lookup"><span data-stu-id="7285e-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="7285e-152">Windows 10 1903 または 1909 の場合 - KB4559004、KB4577062、KB4580386</span><span class="sxs-lookup"><span data-stu-id="7285e-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="7285e-153">Windows 10 2004 の場合 - KB4568831、KB4577063</span><span class="sxs-lookup"><span data-stu-id="7285e-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="7285e-154">Office 2016 を実行しているデバイスの場合 (他の Office バージョンではない) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="7285e-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="7285e-155">すべてのデバイスは[Azure Active Directory (Azure AD) に参加する ](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)か、Hybrid Azure AD に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7285e-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="7285e-156">エンドポイント デバイスに Microsoft Chromium Edge ブラウザーをインストールして、クラウドへのアップロード アクティビティのポリシー アクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="7285e-156">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="7285e-157">「[Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7285e-157">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="7285e-158">デバイス管理へのデバイスのオンボーディング</span><span class="sxs-lookup"><span data-stu-id="7285e-158">Onboarding devices into device management</span></span>

<span data-ttu-id="7285e-159">デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7285e-159">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="7285e-160">これらのアクションはどちらも Microsoft 365 コンプライアンスポータルで行われます。</span><span class="sxs-lookup"><span data-stu-id="7285e-160">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="7285e-161">まだオンボーディングされていないデバイスをオンボーディングする場合は、適切なスクリプトをダウンロードして、それらのデバイスに導入します。</span><span class="sxs-lookup"><span data-stu-id="7285e-161">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="7285e-162">[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7285e-162">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="7285e-163">既に [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) にオンボーディングされているデバイスがある場合、それらは管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7285e-163">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="7285e-164">[「Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用」の手順](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7285e-164">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="7285e-165">オンボーディングデバイス</span><span class="sxs-lookup"><span data-stu-id="7285e-165">Onboarding devices</span></span>

<span data-ttu-id="7285e-166">この導入シナリオでは、まだオンボーディングされていないデバイスをオンボードし、Windows 10 デバイスで意図しない共有から機密アイテムを監視および保護します。</span><span class="sxs-lookup"><span data-stu-id="7285e-166">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="7285e-167">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="7285e-167">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="7285e-168">コンプライアンスセンターの設定ページを開き、[ **オンボードデバイス** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="7285e-168">Open the Compliance Center settings page and choose **Onboard devices** .</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7285e-169">![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="7285e-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="7285e-170">通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="7285e-170">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="7285e-171">[ **デバイス管理** ]を選択して、[ **デバイス** ]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="7285e-171">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="7285e-172">デバイスをオンボードするまで、リストは空になります。</span><span class="sxs-lookup"><span data-stu-id="7285e-172">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="7285e-173">オンボーディングプロセスを開始するには、[ **オンボーディング** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="7285e-173">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="7285e-174">これらの追加デバイスに導入する方法を[ **導入方法** ]リストから選択し、 **パッケージをダウンロード** します。</span><span class="sxs-lookup"><span data-stu-id="7285e-174">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package** .</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7285e-175">![導入方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="7285e-175">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="7285e-176">「[Windows 10 マシンのオンボーディングツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7285e-176">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="7285e-177">このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7285e-177">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="7285e-178">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-178">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="7285e-179">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-179">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="7285e-180">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-180">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="7285e-181">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-181">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="7285e-182">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="7285e-182">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="7285e-183">完了後、エンドポイントがオンボードされ、デバイスリストに表示され、監査アクティビティログのActivity エクスプローラーへの報告も開始されます。</span><span class="sxs-lookup"><span data-stu-id="7285e-183">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="7285e-184">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="7285e-184">This experience is under license enforcement.</span></span> <span data-ttu-id="7285e-185">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="7285e-185">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="7285e-186">Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用</span><span class="sxs-lookup"><span data-stu-id="7285e-186">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7285e-187">このシナリオでは、Microsoft Defender for Endpoint は既に導入されており、レポートするエンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="7285e-187">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="7285e-188">これらすべてのエンドポイントが管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7285e-188">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="7285e-189">新しいデバイスを引き続き Endpoint DLP にオンボーディングして、[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)を使用してカバレッジを拡大します。</span><span class="sxs-lookup"><span data-stu-id="7285e-189">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="7285e-190">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="7285e-190">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="7285e-191">コンプライアンスセンターの設定ページを開き、[ **デバイスの監視を有効にする** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="7285e-191">Open the Compliance Center settings page and choose **Enable device monitoring** .</span></span>

3. <span data-ttu-id="7285e-192">[ **デバイス管理** ]を選択して、[ **デバイス** ]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="7285e-192">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="7285e-193">既に Microsoft Defender for Endpoint にレポートしているデバイスのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7285e-193">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7285e-194">![デバイス管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="7285e-194">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="7285e-195">追加のデバイスをオンボードする必要がある場合は、[ **オンボーディング** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="7285e-195">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="7285e-196">これらの追加デバイスに導入する方法を[ **導入方法** ]リストから選択し、[ **パッケージをダウンロード** ]します。</span><span class="sxs-lookup"><span data-stu-id="7285e-196">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package** .</span></span>

6. <span data-ttu-id="7285e-197">「[Windows 10 マシンのオンボーディングツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7285e-197">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="7285e-198">このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7285e-198">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="7285e-199">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-199">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="7285e-200">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-200">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="7285e-201">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-201">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="7285e-202">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="7285e-202">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="7285e-203">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="7285e-203">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="7285e-204">完了後、エンドポイントがオンボードされ、[ **デバイス** ]テーブルの下に表示され、 **Activity エクスプローラー** に監査ログのレポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="7285e-204">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer** .</span></span>

> [!NOTE]
><span data-ttu-id="7285e-205">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="7285e-205">This experience is under license enforcement.</span></span> <span data-ttu-id="7285e-206">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="7285e-206">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="7285e-207">Activity エクスプローラーでのEndpoint DLPデータの表示</span><span class="sxs-lookup"><span data-stu-id="7285e-207">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="7285e-208">Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7285e-208">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="7285e-209">エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7285e-209">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7285e-210">![エンドポイント デバイスのアクティビティ エクスプローラー フィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="7285e-210">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="7285e-211">次の手順</span><span class="sxs-lookup"><span data-stu-id="7285e-211">Next steps</span></span>
<span data-ttu-id="7285e-212">デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7285e-212">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="7285e-213">エンドポイントのデータ損失防止の使用 (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="7285e-213">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="7285e-214">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="7285e-214">See also</span></span>

- [<span data-ttu-id="7285e-215">エンドポイントのデータ損失防止について学ぶ (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="7285e-215">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="7285e-216">エンドポイントのデータ損失防止の使用 (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="7285e-216">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="7285e-217">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="7285e-217">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="7285e-218">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="7285e-218">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="7285e-219">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="7285e-219">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="7285e-220">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) </span><span class="sxs-lookup"><span data-stu-id="7285e-220">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="7285e-221">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="7285e-221">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="7285e-222">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="7285e-222">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="7285e-223">Azure AD に参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="7285e-223">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="7285e-224">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="7285e-224">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
