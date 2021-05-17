---
title: AutoPilot デバイスの作成と編集
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: AutoPilot を使用してデバイスをアップロードする方法については、Microsoft 365 Business Premium。 プロファイルは、デバイスまたはデバイスのグループに割り当てできます。
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578489"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="4fcd0-104">AutoPilot デバイスを作成し編集する</span><span class="sxs-lookup"><span data-stu-id="4fcd0-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="4fcd0-105">デバイスの一覧をアップロードする</span><span class="sxs-lookup"><span data-stu-id="4fcd0-105">Upload a list of devices</span></span>

<span data-ttu-id="4fcd0-106">デバイスをアップロード [するには、ステップ バイ](add-autopilot-devices-and-profile.md) ステップ ガイドを使用できますが、[デバイス] タブでデバイスを **アップロード** することもできます。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="4fcd0-107">デバイスは、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="4fcd0-108">Windows 10バージョン 1703 以降</span><span class="sxs-lookup"><span data-stu-id="4fcd0-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="4fcd0-109">最新のエクスペリエンスをWindowsした新しいデバイス</span><span class="sxs-lookup"><span data-stu-id="4fcd0-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="4fcd0-110">[管理センター Microsoft 365で、[**デバイスの** \> **自動パイロット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="4fcd0-111">[自動 **パイロット] ページで** 、[デバイス] **タブ** [デバイスの追加] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="4fcd0-113">[デバイスの **追加] パネル** で、Save Close を準備した [デバイス](../admin/misc/device-list.md) リスト CSV ファイル \> **を参照** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="4fcd0-114">この情報は、ハードウェア ベンダーから取得するか [、Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="4fcd0-115">プロファイルをデバイスまたはデバイスのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4fcd0-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="4fcd0-116">[デバイス **の準備Windows]** ページで、[デバイス] タブを選択し、1 つ以上のデバイスの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="4fcd0-117">[ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="4fcd0-118">まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4fcd0-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
