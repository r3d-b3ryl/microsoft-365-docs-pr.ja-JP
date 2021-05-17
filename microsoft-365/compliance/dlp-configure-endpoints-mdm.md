---
title: モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: モバイル デバイス管理ツールを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917993"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="402e3-103">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="402e3-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="402e3-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="402e3-104">**Applies to:**</span></span>

- [<span data-ttu-id="402e3-105">Microsoft 365エンドポイント データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="402e3-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="402e3-106">モバイル デバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="402e3-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="402e3-107">Microsoft 365エンドポイント のデータ損失防止は、デバイスを管理するためのOMA-URIsを作成する機能を提供することで、MDM をサポートします。</span><span class="sxs-lookup"><span data-stu-id="402e3-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="402e3-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="402e3-108">Before you begin</span></span>
<span data-ttu-id="402e3-109">デバイスを使用している場合Microsoft Intune MDM が登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="402e3-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="402e3-110">それ以外の場合、設定は正常に適用されません。</span><span class="sxs-lookup"><span data-stu-id="402e3-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="402e3-111">MDM を有効にする方法の詳細については、「デバイスMicrosoft Intune [(Microsoft Intune) 」を参照してください](/mem/intune/enrollment/device-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="402e3-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="402e3-112">デバイスを使用したオンボード Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="402e3-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="402e3-113">Intune の指示に [従います](/intune/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="402e3-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="402e3-114">オンボード **デバイスの正常性状態ポリシーでは** 、読み取り専用プロパティが使用され、修復できません。</span><span class="sxs-lookup"><span data-stu-id="402e3-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="402e3-115">モバイル デバイス管理ツールを使用したオフボードデバイスと監視デバイス</span><span class="sxs-lookup"><span data-stu-id="402e3-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="402e3-116">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="402e3-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="402e3-117">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="402e3-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="402e3-118">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="402e3-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="402e3-119">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="402e3-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="402e3-120">Microsoft コンプライアンス センターからオフボード パッケージ [を取得します](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="402e3-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="402e3-121">ナビゲーション ウィンドウで、[デバイスオンボーディング **設定**  >  **オフボード]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="402e3-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="402e3-122">[展開 **方法] フィールドで**、[**モバイル デバイスの管理/ 管理] を選択Microsoft Intune。**</span><span class="sxs-lookup"><span data-stu-id="402e3-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="402e3-123">[ **パッケージのダウンロード]** をクリックし、ファイルを.zipします。</span><span class="sxs-lookup"><span data-stu-id="402e3-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="402e3-124">パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="402e3-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="402e3-125">*"-MM-DD.offboarding DeviceCompliance_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="402e3-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="402e3-126">次のサポートMicrosoft Intune OMA-URI 設定を展開するには、次のカスタム構成ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="402e3-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="402e3-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="402e3-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="402e3-128">日付の種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="402e3-128">Date type: String</span></span>      
      <span data-ttu-id="402e3-129">値: [ファイルのコンテンツから値をコピーして貼り付DeviceCompliance_valid_until_YYYY-MM-DD.offboarding ファイル]</span><span class="sxs-lookup"><span data-stu-id="402e3-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="402e3-130">ポリシー設定の詳細については、「Microsoft Intuneのポリシー設定[Windows 10」を参照Microsoft Intune。](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="402e3-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="402e3-131">オフ **ボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。</span><span class="sxs-lookup"><span data-stu-id="402e3-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402e3-132">Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="402e3-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="402e3-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="402e3-133">Related topics</span></span>
- [<span data-ttu-id="402e3-134">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="402e3-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="402e3-135">デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="402e3-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="402e3-136">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="402e3-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="402e3-137">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="402e3-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="402e3-138">オンボーディングMicrosoft Defender Advanced Threat Protectionのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="402e3-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)