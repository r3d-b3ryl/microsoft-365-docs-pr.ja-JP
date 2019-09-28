---
title: AutoPilot デバイスの作成と編集
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 Business の自動操縦を使用してデバイスをアップロードする方法について説明します。 プロファイルは、デバイスまたはデバイスのグループに割り当てることができます。
ms.openlocfilehash: 9ae94266f5a41d8d115fc92f0f080a6fdbdc9f15
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288017"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="d1ff3-104">AutoPilot デバイスの作成と編集</span><span class="sxs-lookup"><span data-stu-id="d1ff3-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="d1ff3-105">デバイスの一覧をアップロードする</span><span class="sxs-lookup"><span data-stu-id="d1ff3-105">Upload a list of devices</span></span>

<span data-ttu-id="d1ff3-106">[[ステップ バイ ステップ ガイド](add-autopilot-devices-and-profile.md)] を使ってデバイスをアップロードできますが、[ **デバイス**] タブでアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="d1ff3-107">デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="d1ff3-108">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="d1ff3-109">Windows out-of-box experience を行っていない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="d1ff3-110">Microsoft 365 Business 管理センターで、[**デバイス** \> **自動操縦**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="d1ff3-111">[**自動操縦**] ページで、[**デバイス**] タブの [ \> **デバイスの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="d1ff3-113">[**デバイスの追加**] パネルで **、準備が** \>整っ\>た[デバイスリストの CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照**します。**</span><span class="sxs-lookup"><span data-stu-id="d1ff3-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="d1ff3-114">この情報は、ハードウェアの製造元から、または csv ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="d1ff3-115">プロファイルをデバイスまたはデバイスのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="d1ff3-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="d1ff3-116">[ **Windows の準備**] ページで [ **デバイス**] タブを選択し、1 つまたは複数のデバイスの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="d1ff3-117">[ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="d1ff3-118">まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1ff3-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
