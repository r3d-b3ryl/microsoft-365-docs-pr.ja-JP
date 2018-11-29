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
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot デバイスの作成と編集

## <a name="upload-a-list-of-devices"></a>デバイスの一覧をアップロードする

[[ステップ バイ ステップ ガイド](add-autopilot-devices-and-profile.md)] を使ってデバイスをアップロードできますが、[ **デバイス**] タブでアップロードすることもできます。 
  
デバイスは次の要件を満たしている必要があります。
  
- Windows 10 バージョン 1703 以降。
    
- Windows out-of-box experience を行っていない新しいデバイス。
    
1. Microsoft 365 Business 管理センターの [ **デバイス アクション**] カードで、[ **AutoPilot で Windows を展開する**] を選びます。 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. **Windows の準備**] ページで、[**デバイス**] タブを選択します\>**デバイスを追加**します。
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 準備した[CSV ファイルのデバイス ・ リスト](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)に参照を [スタート] パネルの [**デバイスの追加** \> **保存** \> **閉じる**。
    
    この情報は、ハードウェアの製造元から、または csv ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>プロファイルをデバイスまたはデバイスのグループに割り当てる

1. [ **Windows の準備**] ページで [ **デバイス**] タブを選択し、1 つまたは複数のデバイスの横にあるチェック ボックスをオンにします。 
    
2. [ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。 
    
    まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。 
    
