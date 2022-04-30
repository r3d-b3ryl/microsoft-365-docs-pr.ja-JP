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
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: Microsoft 365 Business Premium で AutoPilot を使用してデバイスをアップロードする方法について説明します。 プロファイルをデバイスまたはデバイスのグループに割り当てる
ms.openlocfilehash: 2ae149744198803e7cd5441421b93147c965f256
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095230"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot デバイスを作成し編集する

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

## <a name="upload-a-list-of-devices"></a>デバイスの一覧をアップロードする

[[ステップ バイ ステップ ガイド]](m365bp-add-autopilot-devices-and-profile.md) を使ってデバイスをアップロードできますが、**[デバイス]** タブでアップロードすることもできます。 
  
デバイスは次の要件を満たしている必要があります。
  
- Windows 10 バージョン 1703 以降
    
- Windows out-of-box experience を行っていない新しいデバイス。

1. Microsoft 365 管理センター で、**[デバイス]** \> **[AutoPilot]** の順に選択します。
  
2. **[AutoPilot]** ページで、**[デバイス]** タブ\> **[デバイスの追加]** の順に選びます。
    
    ![In the Devices tab, choose Add devices.](./../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. **[デバイスの追加]** パネルで準備した [[デバイス リスト CSV ファイル]](../admin/misc/device-list.md) を参照し、\> **[保存]** \> **[閉じる]** の順に選択します。
    
    この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [Get-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) を使って、入手できます。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>プロファイルをデバイスまたはデバイスのグループに割り当てる

1. **[Windows の準備]** ページで **[デバイス]** タブを選択し、1 つまたは複数のデバイスの横にあるチェック ボックスをオンにします。 
    
2. [ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。 
    
    まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](../admin/devices/create-and-edit-autopilot-profiles.md)」の手順をご覧ください。 

## <a name="see-also"></a>関連項目

[ビジネス プラン用に Microsoft 365 をセキュリティで保護する上位 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)
