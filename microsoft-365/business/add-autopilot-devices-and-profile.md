---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Windows 自動操縦を使用して、ビジネス用に新しい Windows 10 デバイスをセットアップする方法について説明します。
ms.openlocfilehash: d028ea3e902965d55c445dc3b3a02aa315201b25
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574790"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="ba1eb-103">ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="ba1eb-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="ba1eb-104">Windows 自動操縦を使用して、従業員に提供されるとすぐに生産性を高めることができるように、自社の**新しい**windows 10 デバイスをセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="ba1eb-105">デバイスの要件</span><span class="sxs-lookup"><span data-stu-id="ba1eb-105">Device requirements</span></span>

<span data-ttu-id="ba1eb-106">デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="ba1eb-107">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="ba1eb-108">Windows out-of-box experience を行っていない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="ba1eb-109">セットアップ ガイドを使用して、デバイスとプロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="ba1eb-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="ba1eb-110">[![[ラベル] 管理センターが変更されたことを知らせるために、aka.ms/aboutM365preview で詳細を確認できます。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="ba1eb-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="ba1eb-111">まだ作成したデバイス グループまたはプロファイルがない場合は、ステップ バイ ステップ ガイドを使用して開始するのが最適な方法ですが、ガイドを使用せずに、[デバイスを追加](create-and-edit-autopilot-devices.md)して[プロファイルを割り当てる](create-and-edit-autopilot-profiles.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="ba1eb-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ba1eb-113">左側のナビゲーションで、[**デバイス** \>の**自動操縦**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![管理センターで、[デバイス] を選択し、[自動操縦] をクリックします。](media/AutoPilot.png)
  
2. <span data-ttu-id="ba1eb-115">[**自動操縦**] ページで、[**スタートガイド**] をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="ba1eb-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span><span class="sxs-lookup"><span data-stu-id="ba1eb-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="ba1eb-119">列 A:デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="ba1eb-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="ba1eb-120">列 B:Windows 製品 ID</span><span class="sxs-lookup"><span data-stu-id="ba1eb-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="ba1eb-121">列 C:ハードウェア ハッシュ</span><span class="sxs-lookup"><span data-stu-id="ba1eb-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="ba1eb-122">この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="ba1eb-p102">詳細については、[デバイスの一覧の CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="ba1eb-p103">[ **プロファイルの割り当て**] ページで、既存のプロファイルを選択するか、新しいプロファイルを作成します。まだプロファイルがない場合は、新しく作成するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="ba1eb-127">プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="ba1eb-p104">既定の機能は必須であり、自動的に設定されます。既定の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="ba1eb-130">Cortana、OneDrive、および OEM の登録はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="ba1eb-131">会社のブランドを含む、サインイン エクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="ba1eb-132">使用しているデバイスは、Azure Active Directory アカウントに接続され、Microsoft 365 Business で管理されるように自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="ba1eb-133">詳しくは、</span><span class="sxs-lookup"><span data-stu-id="ba1eb-133">For more information, see</span></span>
    
    <span data-ttu-id="ba1eb-134">「[AutoPilot プロファイルの設定について](autopilot-profile-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="ba1eb-135">他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="ba1eb-136">[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="ba1eb-p105">[ **完了しました**] ページでは、作成 (または選択) したプロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されることを示しています。デバイスのユーザーが次にサインインすると、これらの設定が有効になります。[ **閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ba1eb-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    