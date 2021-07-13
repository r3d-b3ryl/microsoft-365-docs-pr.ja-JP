---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: AutoPilot をWindowsして、従業員が使用できる状態Windows 10新しいデバイスをセットアップする方法について学習します。
ms.openlocfilehash: f160ddcd1e41bd44c908ecc8bbd30a9819f76902
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393441"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="a779a-103">ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="a779a-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="a779a-104">AutoPilot Windowsを使用して、ビジネス用の新しい Windows 10 デバイスをセットアップして、従業員に提供するときに使用できる状態にできます。</span><span class="sxs-lookup"><span data-stu-id="a779a-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="a779a-105">デバイスの要件</span><span class="sxs-lookup"><span data-stu-id="a779a-105">Device requirements</span></span>

<span data-ttu-id="a779a-106">デバイスは、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="a779a-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="a779a-107">Windows 10バージョン 1703 以降</span><span class="sxs-lookup"><span data-stu-id="a779a-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="a779a-108">最新のエクスペリエンスをWindowsした新しいデバイス</span><span class="sxs-lookup"><span data-stu-id="a779a-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="a779a-109">セットアップ ガイドを使用して、デバイスとプロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="a779a-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="a779a-110">デバイス グループまたはプロファイルをまだ作成していない場合は、ステップ バイ ステップ ガイドを使用して開始してください。</span><span class="sxs-lookup"><span data-stu-id="a779a-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="a779a-111">ガイドを使用[せずに、デバイス](create-and-edit-autopilot-devices.md)[を追加](create-and-edit-autopilot-profiles.md)してプロファイルを割り当てすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a779a-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="a779a-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a779a-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a779a-113">左側のナビゲーション ウィンドウで、[デバイスの **自動パイロット]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a779a-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![管理センターで、[デバイス] を選択し、[自動パイロット] を選択します。](../media/AutoPilot.png)
  
2. <span data-ttu-id="a779a-115">[自動 **パイロット] ページで** 、[スタート ガイド] をクリックまたは **タップします**。</span><span class="sxs-lookup"><span data-stu-id="a779a-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="a779a-117">[デバイスの **アップロード .csv付** きファイル] ページで、準備されたファイルがある場所を.CSVし、[次へ] を **開** \> **きます**。</span><span class="sxs-lookup"><span data-stu-id="a779a-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="a779a-118">ファイルには 3 つのヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a779a-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="a779a-119">列 A:デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="a779a-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="a779a-120">列 B:Windows 製品 ID</span><span class="sxs-lookup"><span data-stu-id="a779a-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="a779a-121">列 C:ハードウェア ハッシュ</span><span class="sxs-lookup"><span data-stu-id="a779a-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="a779a-122">この情報は、ハードウェア ベンダーから取得するか [、Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="a779a-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="a779a-p103">詳細については、[デバイスの一覧の CSV ファイル](../admin/misc/device-list.md)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a779a-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a779a-125">このスクリプトでは、WMI を使用して、ユーザーがデバイスを自動パイロットに登録するために必要Windowsします。</span><span class="sxs-lookup"><span data-stu-id="a779a-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="a779a-126">結果の CSV ファイルが Windows 製品 ID (PKID) の値を収集しないのは正常です。これはデバイスを登録する必要はありません。出力 CSV に PKID が NULL である場合は、完全に問題ありません。</span><span class="sxs-lookup"><span data-stu-id="a779a-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="a779a-127">シリアル番号とハードウェア ハッシュだけが設定されます。</span><span class="sxs-lookup"><span data-stu-id="a779a-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="a779a-128">[プロファイルの **割り当て** ] ページで、既存のプロファイルを選択するか、新しいプロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a779a-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="a779a-129">まだ作成していない場合は、作成を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a779a-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="a779a-130">プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="a779a-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="a779a-131">既定の機能は必須であり、自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a779a-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="a779a-132">既定の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a779a-132">The default features are:</span></span>
    
    - <span data-ttu-id="a779a-133">[Cortana、OneDrive OEM 登録をスキップします。</span><span class="sxs-lookup"><span data-stu-id="a779a-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="a779a-134">会社のブランドを含む、サインイン エクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a779a-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="a779a-135">ConnectアカウントにデバイスをAzure Active Directoryし、デバイスによって管理されるアカウントを自動的に登録Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="a779a-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="a779a-136">詳細については、「概要 [- AutoPilot プロファイルの設定」を参照してください](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a779a-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="a779a-137">他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a779a-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="a779a-138">[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a779a-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="a779a-139">**完了すると、** 作成した (または選択した) プロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a779a-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="a779a-140">設定は、デバイス ユーザーが次にサインインするときに有効になります。</span><span class="sxs-lookup"><span data-stu-id="a779a-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="a779a-141">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a779a-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="a779a-142">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="a779a-142">Related content</span></span>

<span data-ttu-id="a779a-143">[概要 - AutoPilot プロファイルの設定](autopilot-profile-settings.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="a779a-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="a779a-144">[デバイスとアプリ データを保護するためのオプション](../admin/devices/choose-device-security.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="a779a-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
