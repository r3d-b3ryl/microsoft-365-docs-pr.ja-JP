---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: お客様のビジネスの新しい Windows 10 デバイスを設定するのには Windows の自動操縦装置を使用する方法について説明します。
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868997"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="fc7ce-103">ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="fc7ce-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="fc7ce-104">従業員にデバイスを渡すとすぐに生産的に使用できるように、Windows AutoPilot を使ってビジネス用に新しい Windows 10 デバイスを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="fc7ce-105">デバイスの要件</span><span class="sxs-lookup"><span data-stu-id="fc7ce-105">Device requirements</span></span>

<span data-ttu-id="fc7ce-106">デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="fc7ce-107">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="fc7ce-108">Windows out-of-box experience を行っていない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="fc7ce-109">セットアップ ガイドを使用して、デバイスとプロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fc7ce-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="fc7ce-110">まだ作成したデバイス グループまたはプロファイルがない場合は、ステップ バイ ステップ ガイドを使用して開始するのが最適な方法ですが、ガイドを使用せずに、[デバイスを追加](create-and-edit-autopilot-devices.md)して[プロファイルを割り当てる](create-and-edit-autopilot-profiles.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="fc7ce-111">Microsoft 365 Business 管理センターで [ **デバイス アクション**] カードを見つけて、[ **AutoPilot で Windows を展開する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="fc7ce-113">[ **Windows の準備**] ページで、[ **スタート ガイド**] をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="fc7ce-p101">**デバイスのリストを使用して .csv ファイルのアップロード**] ページで、ある、準備の場所を参照します。CSV ファイルを**開いている** \> **次**です。3 つのヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="fc7ce-117">列 A:デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="fc7ce-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="fc7ce-118">列 B:Windows 製品 ID</span><span class="sxs-lookup"><span data-stu-id="fc7ce-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="fc7ce-119">列 C:ハードウェア ハッシュ</span><span class="sxs-lookup"><span data-stu-id="fc7ce-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="fc7ce-120">この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="fc7ce-p102">詳細については、[デバイスの一覧の CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="fc7ce-p103">[ **プロファイルの割り当て**] ページで、既存のプロファイルを選択するか、新しいプロファイルを作成します。まだプロファイルがない場合は、新しく作成するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="fc7ce-125">プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="fc7ce-p104">既定の機能は必須であり、自動的に設定されます。既定の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="fc7ce-128">Cortana、OneDrive、および OEM の登録はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="fc7ce-129">会社のブランドを含む、サインイン エクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="fc7ce-130">使用しているデバイスは、Azure Active Directory アカウントに接続され、Microsoft 365 Business で管理されるように自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="fc7ce-131">詳しくは、</span><span class="sxs-lookup"><span data-stu-id="fc7ce-131">For more information, see</span></span>
    
    <span data-ttu-id="fc7ce-132">「[AutoPilot プロファイルの設定について](autopilot-profile-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="fc7ce-133">他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="fc7ce-134">[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="fc7ce-p105">[ **完了しました**] ページでは、作成 (または選択) したプロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されることを示しています。デバイスのユーザーが次にサインインすると、これらの設定が有効になります。[ **閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fc7ce-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    