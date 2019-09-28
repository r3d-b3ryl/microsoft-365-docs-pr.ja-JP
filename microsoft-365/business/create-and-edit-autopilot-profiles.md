---
title: AutoPilot プロファイルの作成と編集
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '自動操縦プロファイルを作成、編集、削除、または削除する方法について説明します。 '
ms.openlocfilehash: 8fae8af5e7aa7b866745d0b34a4fe11862de6e9d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287777"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="b41bb-103">AutoPilot プロファイルの作成と編集</span><span class="sxs-lookup"><span data-stu-id="b41bb-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="b41bb-104">プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b41bb-104">Create a profile</span></span>

<span data-ttu-id="b41bb-105">プロファイルがデバイスまたはデバイスのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="b41bb-106">Microsoft 365 Business 管理センターで、[**デバイス** \> **自動操縦**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b41bb-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="b41bb-107">[**自動操縦**] ページで、 **[プロファイル] タブ** \>を選択してプロファイルを**作成**します。</span><span class="sxs-lookup"><span data-stu-id="b41bb-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="b41bb-108">[ **プロファイルの作成**] ページで、識別に役立つプロファイルの名前を入力します。たとえば、マーケティングでは、必要な設定をオンにして (詳細については、「[AutoPilot プロファイルの設定について](autopilot-profile-settings.md)」を参照)、[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="b41bb-110">プロファイルをデバイスに適用する</span><span class="sxs-lookup"><span data-stu-id="b41bb-110">Apply profile to a device</span></span>

<span data-ttu-id="b41bb-p101">プロファイルを作成した後、デバイスまたはデバイスのグループに適用することができます。[ステップ バイ ステップ ガイド](add-autopilot-devices-and-profile.md)で既存のプロファイルを選んだり、プロファイルを新しいデバイスに適用したり、デバイスまたはデバイスのグループの既存のプロファイルを置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="b41bb-113">[ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="b41bb-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="b41bb-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="b41bb-116">プロファイルの編集または削除</span><span class="sxs-lookup"><span data-stu-id="b41bb-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="b41bb-p102">デバイスにプロファイルを割り当てると、そのデバイスを既にユーザーに渡していても、そのプロファイルを更新できます。デバイスをインターネットに接続すると、セットアップ プロセス中に最新バージョンのプロファイルをダウンロードします。ユーザーがデバイスを出荷時の既定の設定にリセットする場合は、デバイスはもう一度プロファイルに最新の更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b41bb-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="b41bb-120">プロファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="b41bb-120">Edit a profile</span></span>

1. <span data-ttu-id="b41bb-121">[ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="b41bb-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="b41bb-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="b41bb-123">ユーザーがデバイスをインターネットに接続する前にこの操作を行った場合、プロファイルはセットアップ プロセスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="b41bb-124">プロファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="b41bb-124">Delete a profile</span></span>

1. <span data-ttu-id="b41bb-125">[ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="b41bb-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="b41bb-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="b41bb-127">プロファイルを削除すると、プロファイルが割り当てられていたデバイスまたはデバイスのグループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="b41bb-128">プロフィールを削除する</span><span class="sxs-lookup"><span data-stu-id="b41bb-128">Remove a profile</span></span>

1. <span data-ttu-id="b41bb-129">[ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="b41bb-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="b41bb-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="b41bb-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
