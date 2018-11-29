---
title: AutoPilot デバイスの作成と編集
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 365 ビジネスのマイクロソフトの自動操縦装置を使用してデバイスにアップロードする方法について説明します。プロファイルは、デバイスまたはデバイスのグループに割り当てることができます。
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869248"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="7726d-104">AutoPilot デバイスの作成と編集</span><span class="sxs-lookup"><span data-stu-id="7726d-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="7726d-105">デバイスの一覧をアップロードする</span><span class="sxs-lookup"><span data-stu-id="7726d-105">Upload a list of devices</span></span>

<span data-ttu-id="7726d-106">[[ステップ バイ ステップ ガイド](add-autopilot-devices-and-profile.md)] を使ってデバイスをアップロードできますが、[ **デバイス**] タブでアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7726d-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="7726d-107">デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7726d-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="7726d-108">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="7726d-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="7726d-109">Windows out-of-box experience を行っていない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="7726d-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="7726d-110">Microsoft 365 Business 管理センターの [ **デバイス アクション**] カードで、[ **AutoPilot で Windows を展開する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7726d-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="7726d-112">**Windows の準備**] ページで、[**デバイス**] タブを選択します\>**デバイスを追加**します。</span><span class="sxs-lookup"><span data-stu-id="7726d-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="7726d-114">準備した[CSV ファイルのデバイス ・ リスト](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)に参照を [スタート] パネルの [**デバイスの追加** \> **保存** \> **閉じる**。</span><span class="sxs-lookup"><span data-stu-id="7726d-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="7726d-115">この情報は、ハードウェアの製造元から、または csv ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。</span><span class="sxs-lookup"><span data-stu-id="7726d-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="7726d-116">プロファイルをデバイスまたはデバイスのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="7726d-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="7726d-117">[ **Windows の準備**] ページで [ **デバイス**] タブを選択し、1 つまたは複数のデバイスの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7726d-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="7726d-118">[ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7726d-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="7726d-119">まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7726d-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
