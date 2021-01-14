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
ms.openlocfilehash: 5a5c8e77679b55f20269b135da52bc0498fd7c11
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840926"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="dd2c1-103">エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="dd2c1-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="dd2c1-104">Microsoft Endpoint Data Loss Prevention (Endpoint DLP) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="dd2c1-105">Microsoft のすべての DLP製品 の詳細については、 「[データ損失防止の概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="dd2c1-106">エンドポイント DLP の詳細については、「[エンドポイント データ損失防止の説明](endpoint-dlp-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="dd2c1-107">Microsoft Endpoint DLP は、Windows 10 デバイスを監視し、機密性の高いアイテムが使用および共有されていることを検出します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="dd2c1-108">これにより、適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dd2c1-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="dd2c1-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="dd2c1-110">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="dd2c1-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="dd2c1-111">Endpoint DLP を開始する前に、「[Microsoft 365サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」とアドオンを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="dd2c1-112">Endpoint DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="dd2c1-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dd2c1-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="dd2c1-114">Microsoft 365 A5 (EDU) </span><span class="sxs-lookup"><span data-stu-id="dd2c1-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="dd2c1-115">Microsoft 365 E5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="dd2c1-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="dd2c1-116">Microsoft 365 A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="dd2c1-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="dd2c1-117">Microsoft 365 E5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="dd2c1-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="dd2c1-118">Microsoft 365 A5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="dd2c1-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="dd2c1-119">許可</span><span class="sxs-lookup"><span data-stu-id="dd2c1-119">Permissions</span></span>

<span data-ttu-id="dd2c1-120">デバイス管理を有効にするには、使用するアカウントが次のいずれかの役割のメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="dd2c1-121">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-121">Global admin</span></span>
- <span data-ttu-id="dd2c1-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-122">Security admin</span></span>
- <span data-ttu-id="dd2c1-123">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-123">Compliance admin</span></span>

<span data-ttu-id="dd2c1-124">カスタムアカウントを使用してデバイス管理設定を表示する場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="dd2c1-125">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-125">Global admin</span></span>
- <span data-ttu-id="dd2c1-126">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-126">Compliance admin</span></span>
- <span data-ttu-id="dd2c1-127">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-127">Compliance data admin</span></span>
- <span data-ttu-id="dd2c1-128">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="dd2c1-128">Global reader</span></span>

<span data-ttu-id="dd2c1-129">カスタムアカウントを使用してオンボーディング/オフボーディングページにアクセスする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="dd2c1-130">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-130">Global admin</span></span>
- <span data-ttu-id="dd2c1-131">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-131">Compliance admin</span></span>

<span data-ttu-id="dd2c1-132">カスタムアカウントを使用してデバイスの監視をオン/オフにする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="dd2c1-133">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-133">Global admin</span></span>
- <span data-ttu-id="dd2c1-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-134">Compliance admin</span></span>

<span data-ttu-id="dd2c1-135">Endpoint DLP からのデータは、[Activity エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="dd2c1-136">Activity エクスプローラーに権限を付与する役割は4つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="dd2c1-137">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-137">Global admin</span></span>
- <span data-ttu-id="dd2c1-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-138">Compliance admin</span></span>
- <span data-ttu-id="dd2c1-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-139">Security admin</span></span>
- <span data-ttu-id="dd2c1-140">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="dd2c1-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="dd2c1-141">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="dd2c1-141">Prepare your endpoints</span></span>

<span data-ttu-id="dd2c1-142">これらの要件を満たすために、Endpoint DLP の導入を計画している Windows 10 デバイスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="dd2c1-143">Windows 10 x64 ビルド 1809 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="dd2c1-144">マルウェア対策クライアントのバージョンは 4.18.2009.7 以降です。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-144">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="dd2c1-145">Windows セキュリティ アプリを開いて現在のバージョンを確認し、[設定] アイコンを選択して、[バージョン情報] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-145">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="dd2c1-146">バージョン番号は、マルウェア対策クライアントのバージョンの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-146">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="dd2c1-147">Windows Update KB4052623 をインストールして、最新のマルウェア対策クライアントのバージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-147">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> <span data-ttu-id="dd2c1-148">注: Windows セキュリティ コンポーネントはいずれもアクティブである必要はありません。Windows セキュリティの状態に関係なくエンドポイント DLP を実行できます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-148">Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="dd2c1-149">次の Windows Update がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-149">The following Windows Updates are installed.</span></span> <span data-ttu-id="dd2c1-150">注: これらの更新プログラムは、デバイスをエンドポイント DLP にオンボードするための前提条件ではありませんが、重要な問題の修正が含まれているため、製品を使用する前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-150">Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="dd2c1-151">Windows 10 1809 の場合 - KB4559003、KB4577069、KB4580390</span><span class="sxs-lookup"><span data-stu-id="dd2c1-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="dd2c1-152">Windows 10 1903 または 1909 の場合 - KB4559004、KB4577062、KB4580386</span><span class="sxs-lookup"><span data-stu-id="dd2c1-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="dd2c1-153">Windows 10 2004 の場合 - KB4568831、KB4577063</span><span class="sxs-lookup"><span data-stu-id="dd2c1-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="dd2c1-154">Office 2016 を実行しているデバイスの場合 (他の Office バージョンではない) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="dd2c1-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="dd2c1-155">すべてのデバイスは[Azure Active Directory (Azure AD) に参加する ](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)か、Hybrid Azure AD に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="dd2c1-156">エンドポイント デバイスに Microsoft Chromium Edge ブラウザーをインストールして、クラウドへのアップロード アクティビティのポリシー アクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-156">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="dd2c1-157">「[Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-157">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="dd2c1-158">Microsoft 365 アプリ バージョン 2004 - 2008 の月次エンタープライズ チャネルを使用している場合、Office コンテンツを分類する Endpoint DLP に既知の問題があり、バージョン 2009 以降に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-158">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="dd2c1-159">現在のバージョンについては「[Microsoft 365 アプリの更新履歴 (日付別の一覧)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-159">See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="dd2c1-160">この問題の詳細については、[2020 年の最新のチャネル リリースのリリース ノート](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27)の「Office スイート」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-160">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="dd2c1-161">デバイス プロキシを使用してインターネットに接続するエンドポイントがある場合は、「[エンドポイント DLP のデバイス プロキシとインターネット接続設定の構成](endpoint-dlp-configure-proxy.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-161">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="dd2c1-162">デバイス管理へのデバイスのオンボーディング</span><span class="sxs-lookup"><span data-stu-id="dd2c1-162">Onboarding devices into device management</span></span>

<span data-ttu-id="dd2c1-163">デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-163">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="dd2c1-164">これらのアクションはどちらも Microsoft 365 コンプライアンスポータルで行われます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-164">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="dd2c1-165">まだオンボーディングされていないデバイスをオンボーディングする場合は、適切なスクリプトをダウンロードして、それらのデバイスに導入します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-165">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="dd2c1-166">[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-166">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="dd2c1-167">既に [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) にオンボーディングされているデバイスがある場合、それらは管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-167">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="dd2c1-168">[「Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用」の手順](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-168">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="dd2c1-169">オンボーディングデバイス</span><span class="sxs-lookup"><span data-stu-id="dd2c1-169">Onboarding devices</span></span>

<span data-ttu-id="dd2c1-170">この導入シナリオでは、まだオンボーディングされていないデバイスをオンボードし、Windows 10 デバイスで意図しない共有から機密アイテムを監視および保護します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-170">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="dd2c1-171">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-171">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="dd2c1-172">コンプライアンスセンターの設定ページを開き、[**オンボードデバイス**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-172">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd2c1-173">![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="dd2c1-173">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="dd2c1-174">通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-174">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="dd2c1-175">[**デバイス管理**]を選択して、[**デバイス**]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-175">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="dd2c1-176">デバイスをオンボードするまで、リストは空になります。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-176">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="dd2c1-177">オンボーディングプロセスを開始するには、[**オンボーディング**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-177">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="dd2c1-178">これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、**パッケージをダウンロード** します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-178">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd2c1-179">![導入方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="dd2c1-179">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="dd2c1-180">「[Windows 10 マシンのオンボーディングツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-180">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="dd2c1-181">このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-181">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="dd2c1-182">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-182">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="dd2c1-183">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-183">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="dd2c1-184">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-184">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="dd2c1-185">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-185">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="dd2c1-186">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-186">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="dd2c1-187">完了後、エンドポイントがオンボードされ、デバイスリストに表示され、監査アクティビティログのActivity エクスプローラーへの報告も開始されます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-187">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="dd2c1-188">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-188">This experience is under license enforcement.</span></span> <span data-ttu-id="dd2c1-189">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-189">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="dd2c1-190">Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用</span><span class="sxs-lookup"><span data-stu-id="dd2c1-190">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="dd2c1-191">このシナリオでは、Microsoft Defender for Endpoint は既に導入されており、レポートするエンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-191">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="dd2c1-192">これらすべてのエンドポイントが管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-192">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="dd2c1-193">新しいデバイスを引き続き Endpoint DLP にオンボーディングして、[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)を使用してカバレッジを拡大します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-193">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="dd2c1-194">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-194">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="dd2c1-195">コンプライアンスセンターの設定ページを開き、[**デバイスの監視を有効にする**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-195">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="dd2c1-196">[**デバイス管理**]を選択して、[**デバイス**]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-196">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="dd2c1-197">既に Microsoft Defender for Endpoint にレポートしているデバイスのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-197">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd2c1-198">![デバイス管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="dd2c1-198">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="dd2c1-199">追加のデバイスをオンボードする必要がある場合は、[**オンボーディング**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-199">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="dd2c1-200">これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、[**パッケージをダウンロード**]します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-200">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="dd2c1-201">「[Windows 10 マシンのオンボーディングツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-201">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="dd2c1-202">このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-202">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="dd2c1-203">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-203">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="dd2c1-204">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-204">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="dd2c1-205">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-205">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="dd2c1-206">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="dd2c1-206">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="dd2c1-207">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-207">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="dd2c1-208">完了後、エンドポイントがオンボードされ、[**デバイス**]テーブルの下に表示され、**Activity エクスプローラー** に監査ログのレポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-208">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="dd2c1-209">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-209">This experience is under license enforcement.</span></span> <span data-ttu-id="dd2c1-210">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-210">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="dd2c1-211">DLP 警告管理ダッシュボードでのエンドポイント DLP 警告の表示</span><span class="sxs-lookup"><span data-stu-id="dd2c1-211">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="dd2c1-212">Microsoft 365 コンプライアンス センターの [データ損失防止] ページを開き、[アラート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-212">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="dd2c1-213">エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-213">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="dd2c1-214">Activity エクスプローラーでのEndpoint DLPデータの表示</span><span class="sxs-lookup"><span data-stu-id="dd2c1-214">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="dd2c1-215">Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-215">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="dd2c1-216">エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-216">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dd2c1-217">![エンドポイント デバイスのアクティビティ エクスプローラー フィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="dd2c1-217">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd2c1-218">次の手順</span><span class="sxs-lookup"><span data-stu-id="dd2c1-218">Next steps</span></span>
<span data-ttu-id="dd2c1-219">デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd2c1-219">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="dd2c1-220">エンドポイントのデータ損失防止の使用 (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="dd2c1-220">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="dd2c1-221">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="dd2c1-221">See also</span></span>

- [<span data-ttu-id="dd2c1-222">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="dd2c1-222">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="dd2c1-223">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="dd2c1-223">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="dd2c1-224">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="dd2c1-224">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="dd2c1-225">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="dd2c1-225">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="dd2c1-226">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="dd2c1-226">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dd2c1-227">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dd2c1-227">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="dd2c1-228">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="dd2c1-228">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="dd2c1-229">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="dd2c1-229">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="dd2c1-230">Azure AD に参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="dd2c1-230">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="dd2c1-231">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="dd2c1-231">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
