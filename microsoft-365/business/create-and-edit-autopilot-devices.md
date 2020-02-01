---
title: AutoPilot デバイスの作成と編集
f1.keywords:
- NOCSH
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 Business の自動操縦を使用してデバイスをアップロードする方法について説明します。 プロファイルは、デバイスまたはデバイスのグループに割り当てることができます。
ms.openlocfilehash: 5a99f691b0325f511f34e3a6c3a20f08ee8d909f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594013"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="11bba-104">AutoPilot デバイスの作成と編集</span><span class="sxs-lookup"><span data-stu-id="11bba-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="11bba-105">デバイスの一覧をアップロードする</span><span class="sxs-lookup"><span data-stu-id="11bba-105">Upload a list of devices</span></span>

<span data-ttu-id="11bba-106">[ステップバイステップガイド](add-autopilot-devices-and-profile.md)を使用してデバイスをアップロードできますが、[**デバイス**] タブでデバイスをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="11bba-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="11bba-107">デバイスは次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bba-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="11bba-108">Windows 10、バージョン1703以降</span><span class="sxs-lookup"><span data-stu-id="11bba-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="11bba-109">Windows の標準外の機能を使用していない新しいデバイス</span><span class="sxs-lookup"><span data-stu-id="11bba-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="11bba-110">Microsoft 365 Business 管理センターで、[**デバイス** \> **自動操縦**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bba-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="11bba-111">[**自動操縦**] ページで、[**デバイス**] タブの [ \> **デバイスの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bba-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="11bba-113">[**デバイスの追加**] パネルで、準備\>した[デバイスリストの CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照して、 **Close**を**保存** \>します。</span><span class="sxs-lookup"><span data-stu-id="11bba-113">On the **Add devices** panel, browse to a [Device list CSV file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="11bba-114">この情報は、ハードウェアベンダーから入手することも、 [G-et-windowsautopilotinfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使用して CSV ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="11bba-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="11bba-115">プロファイルをデバイスまたはデバイスのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="11bba-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="11bba-116">[ **Windows の準備**] ページで、[**デバイス**] タブを選択し、1つ以上のデバイスの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="11bba-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="11bba-117">[ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="11bba-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="11bba-118">まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11bba-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
