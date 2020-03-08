---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Windows 自動操縦を使用して、従業員が使用できるように、自社の新しい Windows 10 デバイスをセットアップする方法について説明します。
ms.openlocfilehash: 3b1cf297914862aaa74fdf9a8bb7290d00f73b1d
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561582"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="4651e-103">ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="4651e-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="4651e-104">Windows 自動操縦を使用して、自分の組織のために**新しい**windows 10 デバイスをセットアップし、従業員に提供するときに使用できる状態にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4651e-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="4651e-105">デバイスの要件</span><span class="sxs-lookup"><span data-stu-id="4651e-105">Device requirements</span></span>

<span data-ttu-id="4651e-106">デバイスは次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4651e-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="4651e-107">Windows 10、バージョン1703以降</span><span class="sxs-lookup"><span data-stu-id="4651e-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="4651e-108">Windows の標準外の機能を使用していない新しいデバイス</span><span class="sxs-lookup"><span data-stu-id="4651e-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="4651e-109">セットアップ ガイドを使用して、デバイスとプロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4651e-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="4651e-110">[![管理センターについて知らせるラベルが変更されていますので、詳細については、aka.ms/aboutM365preview を参照してください。](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="4651e-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="4651e-111">デバイスグループまたはプロファイルをまだ作成していない場合は、まず、ステップバイステップガイドを使用して開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4651e-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="4651e-112">ガイドを使用せずに、[デバイスを追加](create-and-edit-autopilot-devices.md)したり、[プロファイルを割り当て](create-and-edit-autopilot-profiles.md)たりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4651e-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="4651e-113"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4651e-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4651e-114">左側のナビゲーションウィンドウで、[**デバイス** \> **自動操縦**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4651e-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![管理センターで、[デバイス] を選択し、[自動操縦] を選択します。](../media/AutoPilot.png)
  
2. <span data-ttu-id="4651e-116">[**自動操縦**] ページで、[**スタートガイド**] をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="4651e-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="4651e-118">[**デバイスの一覧を含む .csv ファイルのアップロード**] ページで、準備した場所を参照します。CSV ファイルを開き、[**次へ**] を**開き** \>ます。</span><span class="sxs-lookup"><span data-stu-id="4651e-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="4651e-119">ファイルには3つのヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="4651e-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="4651e-120">列 A:デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="4651e-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="4651e-121">列 B:Windows 製品 ID</span><span class="sxs-lookup"><span data-stu-id="4651e-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="4651e-122">列 C:ハードウェア ハッシュ</span><span class="sxs-lookup"><span data-stu-id="4651e-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="4651e-123">この情報は、ハードウェアベンダーから入手することも、 [G-et-windowsautopilotinfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使用して CSV ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4651e-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="4651e-p103">詳細については、[デバイスの一覧の CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4651e-p103">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="4651e-126">[**プロファイルの割り当て**] ページで、既存のプロファイルを選択するか、または新しいプロファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4651e-126">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="4651e-127">まだ持っていない場合は、作成するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4651e-127">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="4651e-128">プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="4651e-128">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="4651e-129">既定の機能は必須であり、自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4651e-129">The default features are required and are set automatically.</span></span> <span data-ttu-id="4651e-130">既定の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4651e-130">The default features are:</span></span>
    
    - <span data-ttu-id="4651e-131">Cortana、OneDrive、OEM 登録をスキップします。</span><span class="sxs-lookup"><span data-stu-id="4651e-131">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="4651e-132">会社のブランドを含む、サインイン エクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4651e-132">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="4651e-133">デバイスを Azure Active Directory アカウントに接続し、Microsoft 365 Business によって管理されるように自動的に登録します。</span><span class="sxs-lookup"><span data-stu-id="4651e-133">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="4651e-134">詳細については、「[自動操縦プロファイルの設定につい](autopilot-profile-settings.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4651e-134">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="4651e-135">他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4651e-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="4651e-136">[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4651e-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="4651e-137">**完了し**たら、作成した (または選択した) プロファイルが、デバイスの一覧をアップロードして作成したデバイスグループに適用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="4651e-137">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="4651e-138">この設定は、デバイスユーザーが次にサインインしたときに有効になります。</span><span class="sxs-lookup"><span data-stu-id="4651e-138">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="4651e-139">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4651e-139">Choose **Close**.</span></span>
    
