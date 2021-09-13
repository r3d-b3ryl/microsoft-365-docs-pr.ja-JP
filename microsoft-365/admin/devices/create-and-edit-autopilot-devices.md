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
description: AutoPilot を使用してデバイスをアップロードする方法については、Microsoft 365 Business Premium。 プロファイルは、デバイスまたはデバイスのグループに割り当てできます。
ms.openlocfilehash: 37617a37f7ea07c46aca19bc75046ebccb0bb4a9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176696"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot デバイスを作成し編集する

## <a name="upload-a-list-of-devices"></a>デバイスの一覧をアップロードする

デバイスをアップロード [するには、ステップ バイ](add-autopilot-devices-and-profile.md) ステップ ガイドを使用できますが、[デバイス] タブでデバイスを **アップロード** することもできます。 
  
デバイスは、次の要件を満たす必要があります。
  
- Windows 10バージョン 1703 以降
    
- 最新のエクスペリエンスをWindowsした新しいデバイス

1. [デバイス] Microsoft 365 管理センター[**デバイス** \> **の自動パイロット] を選択します**。
  
2. [自動 **パイロット] ページで** 、[デバイス] **タブ** [デバイスの追加] \> **を選択します**。
    
    ![In the Devices tab, choose Add devices.](../../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. [デバイスの **追加] パネル** で、Save Close を準備した [デバイス](../misc/device-list.md) リスト CSV ファイル \> **を参照** \> **します**。
    
    この情報は、ハードウェア ベンダーから取得するか [、Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>プロファイルをデバイスまたはデバイスのグループに割り当てる

1. [デバイス **の準備Windows]** ページで、[デバイス] タブを選択し、1 つ以上のデバイスの横にあるチェック ボックスをオンにします。 
    
2. [ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。 
    
    まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。 
