---
title: モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード
description: モバイル デバイス管理ツールを使用してデバイスに構成パッケージを展開し、デバイスがサービスにオンボードされます。
keywords: mdm を使用したオンボード デバイス、デバイス管理、オンボード Microsoft Defender for Endpoint デバイス、mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f0a0a35d41d56abfcc7975c9e79ff7d537b72f40
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338579"
---
# <a name="onboard-the-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="72a1d-104">モバイル デバイス管理Windows 10使用してデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="72a1d-104">Onboard the Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72a1d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="72a1d-105">**Applies to:**</span></span>
- [<span data-ttu-id="72a1d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72a1d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="72a1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72a1d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="72a1d-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="72a1d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="72a1d-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="72a1d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="72a1d-110">モバイル デバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="72a1d-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="72a1d-111">Defender for Endpoint は、デバイスを管理OMA-URIsポリシーを作成するためのユーザー情報を提供することで、MDM をサポートします。</span><span class="sxs-lookup"><span data-stu-id="72a1d-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="72a1d-112">Defender for Endpoint CSP の使用の詳細については [、「WindowsAdvancedThreatProtection CSP」](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) および [「WindowsAdvancedThreatProtection DDF ファイル」を参照してください](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="72a1d-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="72a1d-113">開始する前に</span><span class="sxs-lookup"><span data-stu-id="72a1d-113">Before you begin</span></span>
<span data-ttu-id="72a1d-114">デバイスを使用している場合Microsoft Intune MDM が登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="72a1d-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="72a1d-115">それ以外の場合、設定は正常に適用されません。</span><span class="sxs-lookup"><span data-stu-id="72a1d-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="72a1d-116">MDM を有効にする方法の詳細については、「デバイスMicrosoft Intune [(Microsoft Intune) 」を参照してください](/mem/intune/enrollment/device-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="72a1d-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="72a1d-117">デバイスを使用したオンボード Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="72a1d-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="72a1d-118">[![アプリケーションを使用した Defender for Endpoint へのオンボード デバイスを示す PDF のMicrosoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="72a1d-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="72a1d-119">[[](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)エンドポイント用 Defender [Visio展開](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)] のさまざまなパスを確認するには、PDF またはドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72a1d-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="72a1d-120">Intune の指示に [従います](/intune/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="72a1d-120">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="72a1d-121">Defender for Endpoint CSP の使用の詳細については [、「WindowsAdvancedThreatProtection CSP」](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) および [「WindowsAdvancedThreatProtection DDF ファイル」を参照してください](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="72a1d-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="72a1d-122">オンボード **デバイスの正常性状態ポリシーでは** 、読み取り専用プロパティが使用され、修復できません。</span><span class="sxs-lookup"><span data-stu-id="72a1d-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="72a1d-123">診断データレポートの頻度の構成は、バージョン 1703 の Windows 10デバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="72a1d-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="72a1d-124">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="72a1d-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="72a1d-125">詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="72a1d-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="72a1d-126">[MICROSOFT](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) Defender for Endpoint[の展開](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)Visioパスを確認するには、PDF またはドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72a1d-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="72a1d-127">モバイル デバイス管理ツールを使用したオフボードデバイスと監視デバイス</span><span class="sxs-lookup"><span data-stu-id="72a1d-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="72a1d-128">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="72a1d-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="72a1d-129">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="72a1d-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="72a1d-130">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="72a1d-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="72a1d-131">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="72a1d-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="72a1d-132">ポータルからオフボード パッケージ[Microsoft 365 Defenderします](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="72a1d-132">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

   1. <span data-ttu-id="72a1d-133">ナビゲーション ウィンドウで、[エンドポイント **デバイス** 設定  >  **オフ**  >  **ボード]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72a1d-133">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Offboarding**.</span></span>

   1. <span data-ttu-id="72a1d-134">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="72a1d-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="72a1d-135">[展開 **方法] フィールドで**、[**モバイル デバイスの管理/ 管理] を選択Microsoft Intune。**</span><span class="sxs-lookup"><span data-stu-id="72a1d-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="72a1d-136">[ **パッケージのダウンロード]** をクリックし、ファイルを.zipします。</span><span class="sxs-lookup"><span data-stu-id="72a1d-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="72a1d-137">パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="72a1d-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="72a1d-138">*"-MM-DD.offboarding WindowsDefenderATP_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="72a1d-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="72a1d-139">次のサポートMicrosoft Intune OMA-URI 設定を展開するには、次のカスタム構成ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="72a1d-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="72a1d-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="72a1d-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="72a1d-141">日付の種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="72a1d-141">Date type: String</span></span><br/>
      <span data-ttu-id="72a1d-142">値: [ファイルのコンテンツから値をコピーして貼りWindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding ファイル]</span><span class="sxs-lookup"><span data-stu-id="72a1d-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="72a1d-143">ポリシー設定の詳細については、「Microsoft Intuneのポリシー設定[Windows 10」を参照Microsoft Intune。](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="72a1d-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="72a1d-144">オフ **ボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。</span><span class="sxs-lookup"><span data-stu-id="72a1d-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72a1d-145">Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="72a1d-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="72a1d-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="72a1d-146">Related topics</span></span>
- [<span data-ttu-id="72a1d-147">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="72a1d-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="72a1d-148">デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="72a1d-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="72a1d-149">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="72a1d-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="72a1d-150">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="72a1d-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="72a1d-151">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="72a1d-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="72a1d-152">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="72a1d-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
