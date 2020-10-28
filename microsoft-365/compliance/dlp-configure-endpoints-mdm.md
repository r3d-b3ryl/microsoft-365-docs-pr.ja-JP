---
title: モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード
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
description: モバイルデバイス管理ツールを使用して、サービスに利用されるように構成パッケージをデバイスに展開します。
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769482"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="a0cb4-103">モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a0cb4-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="a0cb4-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a0cb4-104">**Applies to:**</span></span>

- [<span data-ttu-id="a0cb4-105">Microsoft 365 エンドポイントのデータ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a0cb4-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="a0cb4-106">モバイルデバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="a0cb4-107">Microsoft 365 エンドポイントのデータ損失防止は、デバイスを管理するためのポリシーを作成するための OMA-URIs を提供することにより、MDMs をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="a0cb4-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="a0cb4-108">Before you begin</span></span>
<span data-ttu-id="a0cb4-109">Microsoft Intune を使用している場合は、デバイス MDM が登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="a0cb4-110">それ以外の場合、設定は正常に適用されません。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="a0cb4-111">Microsoft Intune で MDM を有効にする方法の詳細については、「 [Device enrollment (Microsoft intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="a0cb4-112">Microsoft Intune を使用しているオンボードデバイス</span><span class="sxs-lookup"><span data-stu-id="a0cb4-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="a0cb4-113">[Intune](https://docs.microsoft.com/intune/advanced-threat-protection)からの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="a0cb4-114">**利用 devices policy の** 状態は読み取り専用プロパティを使用しており、修復することはできません。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="a0cb4-115">モバイルデバイス管理ツールを使用した offboard およびモニターデバイス</span><span class="sxs-lookup"><span data-stu-id="a0cb4-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="a0cb4-116">セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="a0cb4-117">有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="a0cb4-118">オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="a0cb4-119">オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="a0cb4-120">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)からオフボードパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a0cb4-121">ナビゲーションウィンドウで、[ **設定** ] [デバイスのオンボードオフボード] を選択し  >  **Device onboarding**  >  **Offboarding** ます。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="a0cb4-122">[ **展開方法** ] フィールドで、[ **モバイルデバイス管理]/[Microsoft Intune** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune** .</span></span>
    
4. <span data-ttu-id="a0cb4-123">[ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-123">Click **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="a0cb4-124">.Zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="a0cb4-125">*DeviceCompliance_valid_until_YYYY-MM-DD* という名前のファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding* .</span></span>

6. <span data-ttu-id="a0cb4-126">Microsoft Intune カスタム構成ポリシーを使用して、次のサポートされている OMA URI 設定を展開します。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="a0cb4-127">OMA URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="a0cb4-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="a0cb4-128">日付型: String</span><span class="sxs-lookup"><span data-stu-id="a0cb4-128">Date type: String</span></span>      
      <span data-ttu-id="a0cb4-129">値: [次の値をコピーして貼り付け DeviceCompliance_valid_until_YYYY-MM-DD ファイルの内容をコピーして貼り付ける]</span><span class="sxs-lookup"><span data-stu-id="a0cb4-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="a0cb4-130">Microsoft Intune ポリシー設定の詳細については、「 [Microsoft intune の Windows 10 ポリシー設定](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="a0cb4-131">**Offboarded devices policy の** 状態は読み取り専用プロパティを使用しており、修復することはできません。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0cb4-132">オフボードを使用すると、デバイスはポータルへのセンサーデータの送信を停止しますが、デバイスからのデータは、必要なアラートへの参照も含めて最大6か月保持されます。</span><span class="sxs-lookup"><span data-stu-id="a0cb4-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0cb4-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0cb4-133">Related topics</span></span>
- [<span data-ttu-id="a0cb4-134">グループポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a0cb4-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="a0cb4-135">Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a0cb4-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="a0cb4-136">ローカルスクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a0cb4-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="a0cb4-137">オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="a0cb4-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="a0cb4-138">Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a0cb4-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
