---
title: Microsoft 365 エンドポイント データ損失防止を開始する
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
description: Microsoft 365 エンドポイントのデータ損失防止を設定して、ファイルアクティビティを監視し、それらのファイルの保護アクションをエンドポイントに実装します。
ms.openlocfilehash: 134c5426e428372670a50c76301a9e9e0c10b343
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061669"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="8db18-103">エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="8db18-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="8db18-104">Microsoft Endpoint Data Loss Prevention (Endpoint DLP) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="8db18-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="8db18-105">MicrosoftのすべてのDLP製品の詳細については、「[データ損失防止の概要](dlp-learn-about-dlp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db18-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="8db18-106">エンドポイント DLP の詳細については、「[エンドポイント データ損失防止の説明](endpoint-dlp-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db18-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="8db18-107">Microsoft Endpoint DLP は、Windows 10 デバイスを監視し、機密性の高いアイテムが使用および共有されていることを検出します。</span><span class="sxs-lookup"><span data-stu-id="8db18-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="8db18-108">これにより、適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="8db18-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8db18-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="8db18-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="8db18-110">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="8db18-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="8db18-111">Endpoint DLP を開始する前に、「[Microsoft 365サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」とアドオンを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8db18-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="8db18-112">Endpoint DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="8db18-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="8db18-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8db18-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="8db18-114">Microsoft 365 A5 (EDU) </span><span class="sxs-lookup"><span data-stu-id="8db18-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="8db18-115">Microsoft 365 E5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="8db18-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="8db18-116">Microsoft 365 A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="8db18-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="8db18-117">Microsoft 365 E5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="8db18-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="8db18-118">Microsoft 365 A5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="8db18-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="8db18-119">許可</span><span class="sxs-lookup"><span data-stu-id="8db18-119">Permissions</span></span>

<span data-ttu-id="8db18-120">デバイス管理を有効にするには、使用するアカウントが次のいずれかの役割のメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8db18-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="8db18-121">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-121">Global admin</span></span>
- <span data-ttu-id="8db18-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-122">Security admin</span></span>
- <span data-ttu-id="8db18-123">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-123">Compliance admin</span></span>

<span data-ttu-id="8db18-124">カスタムアカウントを使用してデバイス管理設定を表示する場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8db18-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="8db18-125">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-125">Global admin</span></span>
- <span data-ttu-id="8db18-126">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-126">Compliance admin</span></span>
- <span data-ttu-id="8db18-127">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-127">Compliance data admin</span></span>
- <span data-ttu-id="8db18-128">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="8db18-128">Global reader</span></span>

<span data-ttu-id="8db18-129">カスタムアカウントを使用してオンボーディング/オフボーディングページにアクセスする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8db18-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="8db18-130">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-130">Global admin</span></span>
- <span data-ttu-id="8db18-131">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-131">Compliance admin</span></span>

<span data-ttu-id="8db18-132">カスタムアカウントを使用してデバイスの監視をオン/オフにする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8db18-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="8db18-133">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-133">Global admin</span></span>
- <span data-ttu-id="8db18-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-134">Compliance admin</span></span>

<span data-ttu-id="8db18-135">Endpoint DLP からのデータは、[Activity エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="8db18-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="8db18-136">Activity エクスプローラーに権限を付与する役割は4つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8db18-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="8db18-137">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-137">Global admin</span></span>
- <span data-ttu-id="8db18-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-138">Compliance admin</span></span>
- <span data-ttu-id="8db18-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-139">Security admin</span></span>
- <span data-ttu-id="8db18-140">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="8db18-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="8db18-141">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="8db18-141">Prepare your endpoints</span></span>

<span data-ttu-id="8db18-142">これらの要件を満たすために、Endpoint DLP の導入を計画している Windows 10 デバイスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8db18-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="8db18-143">Windows 10 x64 ビルド 1809 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db18-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="8db18-144">マルウェア対策クライアントのバージョンは 4.18.2009.7 以降です。</span><span class="sxs-lookup"><span data-stu-id="8db18-144">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="8db18-145">Windows セキュリティ アプリを開いて現在のバージョンを確認し、[設定] アイコンを選択して、[バージョン情報] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8db18-145">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="8db18-146">バージョン番号は、マルウェア対策クライアントのバージョンの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db18-146">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="8db18-147">Windows Update KB4052623 をインストールして、最新のマルウェア対策クライアントのバージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="8db18-147">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="8db18-148">注: Windows セキュリティ コンポーネントはいずれもアクティブである必要はなく、Windows セキュリティの状態に関係なくエンドポイント DLP を実行できますが、[リアルタイム保護と動作の監視](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db18-148">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="8db18-149">次の Windows Update がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="8db18-149">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="8db18-150">これらの更新プログラムは、デバイスをエンドポイント DLP にオンボードするための前提条件ではありませんが、重要な問題の修正が含まれているため、製品を使用する前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db18-150">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="8db18-151">Windows 10 1809 の場合 - KB4559003、KB4577069、KB4580390</span><span class="sxs-lookup"><span data-stu-id="8db18-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="8db18-152">Windows 10 1903 または 1909 の場合 - KB4559004、KB4577062、KB4580386</span><span class="sxs-lookup"><span data-stu-id="8db18-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="8db18-153">Windows 10 2004 の場合 - KB4568831、KB4577063</span><span class="sxs-lookup"><span data-stu-id="8db18-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="8db18-154">Office 2016 を実行しているデバイスの場合 (他の Office バージョンではない) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="8db18-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="8db18-155">すべてのデバイスは、次のいずれかを満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db18-155">All devices must be one of these:</span></span>
- [<span data-ttu-id="8db18-156">Azure Active Directory (Azure AD) への参加</span><span class="sxs-lookup"><span data-stu-id="8db18-156">Azure Active Directory (Azure AD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="8db18-157">Hybrid Azure AD への参加</span><span class="sxs-lookup"><span data-stu-id="8db18-157">Hybrid Azure AD joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
- [<span data-ttu-id="8db18-158">AAD の登録</span><span class="sxs-lookup"><span data-stu-id="8db18-158">AAD registered</span></span>](/azure/active-directory/user-help/user-help-register-device-on-network)

5. <span data-ttu-id="8db18-159">エンドポイント デバイスに Microsoft Chromium Edge ブラウザーをインストールして、クラウドへのアップロード アクティビティのポリシー アクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="8db18-159">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="8db18-160">「[Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db18-160">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="8db18-161">Microsoft 365 アプリ バージョン 2004 - 2008 の月次エンタープライズ チャネルを使用している場合、Office コンテンツを分類する Endpoint DLP に既知の問題があり、バージョン 2009 以降に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db18-161">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="8db18-162">現在のバージョンについては「[Microsoft 365 アプリの更新履歴 (日付別の一覧)](/officeupdates/update-history-microsoft365-apps-by-date)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8db18-162">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="8db18-163">この問題の詳細については、[2020 年の最新のチャネル リリースのリリース ノート](/officeupdates/current-channel#version-2010-october-27)の「Office スイート」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db18-163">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="8db18-164">デバイス プロキシを使用してインターネットに接続するエンドポイントがある場合は、「[エンドポイント DLP のデバイス プロキシとインターネット接続設定の構成](endpoint-dlp-configure-proxy.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8db18-164">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="8db18-165">デバイス管理へのデバイスのオンボーディング</span><span class="sxs-lookup"><span data-stu-id="8db18-165">Onboarding devices into device management</span></span>

<span data-ttu-id="8db18-166">デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8db18-166">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="8db18-167">これらのアクションはどちらも Microsoft 365 コンプライアンスポータルで行われます。</span><span class="sxs-lookup"><span data-stu-id="8db18-167">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="8db18-168">まだオンボーディングされていないデバイスをオンボーディングする場合は、適切なスクリプトをダウンロードして、それらのデバイスに導入します。</span><span class="sxs-lookup"><span data-stu-id="8db18-168">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="8db18-169">[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8db18-169">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="8db18-170">既に [Microsoft Defender for Endpoint](/windows/security/threat-protection/) にオンボーディングされているデバイスがある場合、それらは管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db18-170">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="8db18-171">[「Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用」の手順](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8db18-171">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="8db18-172">オンボーディングデバイス</span><span class="sxs-lookup"><span data-stu-id="8db18-172">Onboarding devices</span></span>

<span data-ttu-id="8db18-173">この導入シナリオでは、まだオンボーディングされていないデバイスをオンボードし、Windows 10 デバイスで意図しない共有から機密アイテムを監視および保護します。</span><span class="sxs-lookup"><span data-stu-id="8db18-173">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="8db18-174">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="8db18-174">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="8db18-175">コンプライアンスセンターの設定ページを開き、[**オンボードデバイス**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="8db18-175">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8db18-176">![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="8db18-176">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="8db18-177">通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="8db18-177">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="8db18-178">[**デバイス管理**]を選択して、[**デバイス**]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="8db18-178">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="8db18-179">デバイスをオンボードするまで、リストは空になります。</span><span class="sxs-lookup"><span data-stu-id="8db18-179">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="8db18-180">オンボーディングプロセスを開始するには、[**オンボーディング**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="8db18-180">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="8db18-181">これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、**パッケージをダウンロード** します。</span><span class="sxs-lookup"><span data-stu-id="8db18-181">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8db18-182">![導入方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="8db18-182">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="8db18-183">「[Windows 10 マシンのオンボーディングツールと方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8db18-183">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="8db18-184">このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db18-184">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="8db18-185">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-185">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="8db18-186">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-186">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="8db18-187">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-187">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="8db18-188">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-188">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="8db18-189">シングル セッション シナリオでの非永続的な仮想デスクトップ インフラストラクチャ (VDI) マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-189">Onboard non-persistent virtual desktop infrastructure (VDI) machines in single-session scenarios</span></span>

<span data-ttu-id="8db18-190">完了後、エンドポイントがオンボードされ、デバイスリストに表示され、監査アクティビティログのActivity エクスプローラーへの報告も開始されます。</span><span class="sxs-lookup"><span data-stu-id="8db18-190">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="8db18-191">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="8db18-191">This experience is under license enforcement.</span></span> <span data-ttu-id="8db18-192">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8db18-192">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="8db18-193">Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用</span><span class="sxs-lookup"><span data-stu-id="8db18-193">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8db18-194">このシナリオでは、Microsoft Defender for Endpoint は既に導入されており、レポートするエンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="8db18-194">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="8db18-195">これらすべてのエンドポイントが管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db18-195">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="8db18-196">新しいデバイスを引き続き Endpoint DLP にオンボーディングして、[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)を使用してカバレッジを拡大します。</span><span class="sxs-lookup"><span data-stu-id="8db18-196">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="8db18-197">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="8db18-197">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="8db18-198">コンプライアンスセンターの設定ページを開き、[**デバイスの監視を有効にする**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="8db18-198">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="8db18-199">[**デバイス管理**]を選択して、[**デバイス**]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="8db18-199">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="8db18-200">既に Microsoft Defender for Endpoint にレポートしているデバイスのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db18-200">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8db18-201">![デバイス管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="8db18-201">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="8db18-202">追加のデバイスをオンボードする必要がある場合は、[**オンボーディング**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="8db18-202">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="8db18-203">これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、[**パッケージをダウンロード**]します。</span><span class="sxs-lookup"><span data-stu-id="8db18-203">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="8db18-204">「[Windows 10 マシンのオンボーディングツールと方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8db18-204">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="8db18-205">このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db18-205">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="8db18-206">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-206">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="8db18-207">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-207">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="8db18-208">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-208">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="8db18-209">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="8db18-209">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="8db18-210">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="8db18-210">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="8db18-211">完了後、エンドポイントがオンボードされ、[**デバイス**]テーブルの下に表示され、**Activity エクスプローラー** に監査ログのレポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="8db18-211">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="8db18-212">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="8db18-212">This experience is under license enforcement.</span></span> <span data-ttu-id="8db18-213">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8db18-213">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="8db18-214">DLP 警告管理ダッシュボードでのエンドポイント DLP 警告の表示</span><span class="sxs-lookup"><span data-stu-id="8db18-214">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="8db18-215">Microsoft 365 コンプライアンス センターの [データ損失防止] ページを開き、[アラート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8db18-215">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="8db18-216">エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db18-216">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="8db18-217">Activity エクスプローラーでのEndpoint DLPデータの表示</span><span class="sxs-lookup"><span data-stu-id="8db18-217">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="8db18-218">Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8db18-218">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="8db18-219">エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8db18-219">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8db18-220">![エンドポイント デバイスのアクティビティ エクスプローラー フィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="8db18-220">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="8db18-221">次の手順</span><span class="sxs-lookup"><span data-stu-id="8db18-221">Next steps</span></span>
<span data-ttu-id="8db18-222">デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8db18-222">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="8db18-223">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="8db18-223">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="8db18-224">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="8db18-224">See also</span></span>

- [<span data-ttu-id="8db18-225">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="8db18-225">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="8db18-226">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="8db18-226">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="8db18-227">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="8db18-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="8db18-228">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="8db18-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="8db18-229">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="8db18-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="8db18-230">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8db18-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="8db18-231">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="8db18-231">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="8db18-232">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="8db18-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="8db18-233">Azure AD に参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="8db18-233">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="8db18-234">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="8db18-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
