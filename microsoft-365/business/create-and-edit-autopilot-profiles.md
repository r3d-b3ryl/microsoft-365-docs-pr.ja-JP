---
title: AutoPilot プロファイルの作成と編集
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 自動操縦プロファイルを作成してデバイスに適用するだけでなく、プロファイルを編集または削除したり、デバイスからプロファイルを削除したりする方法について説明します。
ms.openlocfilehash: 58c16b68c66dce7541a02ecd0d2466babe8cc338
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560722"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="5d206-103">AutoPilot プロファイルを作成し編集する</span><span class="sxs-lookup"><span data-stu-id="5d206-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="5d206-104">プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5d206-104">Create a profile</span></span>

<span data-ttu-id="5d206-105">プロファイルがデバイスまたはデバイスのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5d206-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="5d206-106">Microsoft 365 Business 管理センターで、[**デバイス** \> **自動操縦**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d206-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="5d206-107">[**自動操縦**] ページで、 **[プロファイル] タブ** \>を選択してプロファイルを**作成**します。</span><span class="sxs-lookup"><span data-stu-id="5d206-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="5d206-108">[**プロファイルの作成**] ページで、「Marketing」などの特定に役立つプロファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d206-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="5d206-109">目的の設定を有効にして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d206-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="5d206-110">自動操縦プロファイル設定の詳細については、「[自動操縦プロファイル設定につい](autopilot-profile-settings.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d206-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="5d206-112">プロファイルをデバイスに適用する</span><span class="sxs-lookup"><span data-stu-id="5d206-112">Apply profile to a device</span></span>

<span data-ttu-id="5d206-113">プロファイルを作成したら、それをデバイスまたはデバイスのグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5d206-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="5d206-114">[ステップバイステップガイド](add-autopilot-devices-and-profile.md)で既存のプロファイルを選択して新しいデバイスに適用したり、デバイスまたはデバイスのグループの既存のプロファイルを置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d206-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="5d206-115">[ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="5d206-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="5d206-116">デバイス名の横にあるチェックボックスをオンにし、[**デバイス**] パネルで、[**割り当てられたプロファイル**] ドロップ\> **ダウンリストから**プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5d206-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="5d206-118">プロファイルの編集または削除</span><span class="sxs-lookup"><span data-stu-id="5d206-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="5d206-p103">デバイスにプロファイルを割り当てると、そのデバイスを既にユーザーに渡していても、そのプロファイルを更新できます。デバイスをインターネットに接続すると、セットアップ プロセス中に最新バージョンのプロファイルをダウンロードします。ユーザーがデバイスを出荷時の既定の設定にリセットする場合は、デバイスはもう一度プロファイルに最新の更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5d206-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="5d206-122">プロファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="5d206-122">Edit a profile</span></span>

1. <span data-ttu-id="5d206-123">[ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="5d206-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="5d206-124">デバイス名の横にあるチェックボックスをオンにし、[**プロファイル**] パネルで、利用可能な\>設定の**保存**を更新します。</span><span class="sxs-lookup"><span data-stu-id="5d206-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="5d206-125">ユーザーがデバイスをインターネットに接続する前にこの操作を行った場合、プロファイルはセットアップ プロセスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d206-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="5d206-126">プロファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="5d206-126">Delete a profile</span></span>

1. <span data-ttu-id="5d206-127">[ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="5d206-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="5d206-128">デバイス名の横にあるチェックボックスをオンにし、[**プロファイル**] パネルで [**プロファイル** \>の**保存**の削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d206-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="5d206-129">プロファイルを削除すると、プロファイルが割り当てられていたデバイスまたはデバイスのグループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="5d206-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="5d206-130">プロフィールを削除する</span><span class="sxs-lookup"><span data-stu-id="5d206-130">Remove a profile</span></span>

1. <span data-ttu-id="5d206-131">[ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="5d206-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="5d206-132">デバイス名の横にあるチェックボックスをオンにし、 **[デバイス**] パネルで、[**割り当てられたプロファイル**] \>ドロップダウン**リストから [** **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d206-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
