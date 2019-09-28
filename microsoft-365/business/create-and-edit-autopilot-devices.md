---
title: AutoPilot デバイスの作成と編集
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 Business の自動操縦を使用してデバイスをアップロードする方法について説明します。 プロファイルは、デバイスまたはデバイスのグループに割り当てることができます。
ms.openlocfilehash: 9ae94266f5a41d8d115fc92f0f080a6fdbdc9f15
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288017"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot デバイスの作成と編集

## <a name="upload-a-list-of-devices"></a>デバイスの一覧をアップロードする

[[ステップ バイ ステップ ガイド](add-autopilot-devices-and-profile.md)] を使ってデバイスをアップロードできますが、[ **デバイス**] タブでアップロードすることもできます。 
  
デバイスは次の要件を満たしている必要があります。
  
- Windows 10 バージョン 1703 以降。
    
- Windows out-of-box experience を行っていない新しいデバイス。

1. Microsoft 365 Business 管理センターで、[**デバイス** \> **自動操縦**] を選択します。
  
2. [**自動操縦**] ページで、[**デバイス**] タブの [ \> **デバイスの追加**] を選択します。
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. [**デバイスの追加**] パネルで **、準備が** \>整っ\>た[デバイスリストの CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照**します。**
    
    この情報は、ハードウェアの製造元から、または csv ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>プロファイルをデバイスまたはデバイスのグループに割り当てる

1. [ **Windows の準備**] ページで [ **デバイス**] タブを選択し、1 つまたは複数のデバイスの横にあるチェック ボックスをオンにします。 
    
2. [ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。 
    
    まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。 
    
