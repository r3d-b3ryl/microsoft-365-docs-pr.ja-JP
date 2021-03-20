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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 Business Premium で AutoPilot を使用してデバイスをアップロードする方法について説明します。 プロファイルは、デバイスまたはデバイスのグループに割り当てできます。
ms.openlocfilehash: 910abb98b94b749177b04cd12c766f82d348e379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913400"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot デバイスを作成し編集する

## <a name="upload-a-list-of-devices"></a>デバイスの一覧をアップロードする

デバイスをアップロード [するには、ステップ バイ](add-autopilot-devices-and-profile.md) ステップ ガイドを使用できますが、[デバイス] タブでデバイスを **アップロード** することもできます。 
  
デバイスは、次の要件を満たす必要があります。
  
- Windows 10 バージョン 1703 以降
    
- Windows のアウトオブボックス エクスペリエンスを使用していない新しいデバイス

1. Microsoft 365 管理センターで、[デバイスの **自動パイロット]** \> **を選択します**。
  
2. [自動 **パイロット] ページで** 、[デバイス] **タブ** [デバイスの追加] \> **を選択します**。
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. [デバイスの **追加] パネル** で、Save Close を準備した [デバイス](../admin/misc/device-list.md) リスト CSV ファイル \> **を参照** \> **します**。
    
    この情報は、ハードウェア ベンダーから取得するか [、Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>プロファイルをデバイスまたはデバイスのグループに割り当てる

1. [Windows の **準備] ページ** で、[デバイス] タブ **を** 選択し、1 つ以上のデバイスの横にあるチェック ボックスをオンにします。 
    
2. [ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。 
    
    まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。 
