---
title: AutoPilot プロファイルの作成と編集
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '作成、編集、削除、または自動操縦装置のプロファイルを削除するについて説明します。 '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869303"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="84b1e-103">AutoPilot プロファイルの作成と編集</span><span class="sxs-lookup"><span data-stu-id="84b1e-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="84b1e-104">プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="84b1e-104">Create a profile</span></span>

<span data-ttu-id="84b1e-105">プロファイルがデバイスまたはデバイスのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="84b1e-106">Microsoft 365 Business 管理センターの [ **デバイス アクション**] カードで、[ **AutoPilot で Windows を展開する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-106">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="84b1e-108">**Windows の準備**] ページで、[**プロファイル**] タブを選択します\>**プロファイルを作成**します。</span><span class="sxs-lookup"><span data-stu-id="84b1e-108">On the **Prepare Windows** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="84b1e-109">[ **プロファイルの作成**] ページで、識別に役立つプロファイルの名前を入力します。たとえば、マーケティングでは、必要な設定をオンにして (詳細については、「[AutoPilot プロファイルの設定について](autopilot-profile-settings.md)」を参照)、[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-109">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="84b1e-111">プロファイルをデバイスに適用する</span><span class="sxs-lookup"><span data-stu-id="84b1e-111">Apply profile to a device</span></span>

<span data-ttu-id="84b1e-p101">プロファイルを作成した後、デバイスまたはデバイスのグループに適用することができます。[ステップ バイ ステップ ガイド](add-autopilot-devices-and-profile.md)で既存のプロファイルを選んだり、プロファイルを新しいデバイスに適用したり、デバイスまたはデバイスのグループの既存のプロファイルを置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="84b1e-114">[ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-114">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="84b1e-115">**デバイス**パネルのデバイス名の横にあるチェック ・ ボックスをクリックし、**割り当てられたプロファイル**ドロップダウン リストからプロファイルを選択して\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="84b1e-115">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="84b1e-117">プロファイルの編集または削除</span><span class="sxs-lookup"><span data-stu-id="84b1e-117">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="84b1e-p102">デバイスにプロファイルを割り当てると、そのデバイスを既にユーザーに渡していても、そのプロファイルを更新できます。デバイスをインターネットに接続すると、セットアップ プロセス中に最新バージョンのプロファイルをダウンロードします。ユーザーがデバイスを出荷時の既定の設定にリセットする場合は、デバイスはもう一度プロファイルに最新の更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="84b1e-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="84b1e-121">プロファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="84b1e-121">Edit a profile</span></span>

1. <span data-ttu-id="84b1e-122">[ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-122">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="84b1e-123">デバイス名の横のチェック ボックスをクリックし、**プロファイル**にパネルを更新、使用可能な設定のいずれかの\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="84b1e-123">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="84b1e-124">ユーザーがデバイスをインターネットに接続する前にこの操作を行った場合、プロファイルはセットアップ プロセスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-124">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="84b1e-125">プロファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="84b1e-125">Delete a profile</span></span>

1. <span data-ttu-id="84b1e-126">[ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-126">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="84b1e-127">デバイス名の横のチェック ボックスをクリックし、[**プロファイル**] パネルで [**プロファイルの削除**] をクリックします\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="84b1e-127">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="84b1e-128">プロファイルを削除すると、プロファイルが割り当てられていたデバイスまたはデバイスのグループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-128">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="84b1e-129">プロフィールを削除する</span><span class="sxs-lookup"><span data-stu-id="84b1e-129">Remove a profile</span></span>

1. <span data-ttu-id="84b1e-130">[ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="84b1e-130">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="84b1e-131">**デバイス**パネルのデバイス名の横にあるチェック ・ ボックスをクリックし、**割り当てられたプロファイル**ドロップダウン リストから **[なし]** を選択して\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="84b1e-131">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
