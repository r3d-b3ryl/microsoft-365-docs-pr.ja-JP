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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 Business の自動操縦を使用してデバイスをアップロードする方法について説明します。 プロファイルは、デバイスまたはデバイスのグループに割り当てることができます。
ms.openlocfilehash: 640e4af7cccde83c87d90a875c1d44dead7255ca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065986"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot デバイスの作成と編集

## <a name="upload-a-list-of-devices"></a>デバイスの一覧をアップロードする

[ステップバイステップガイド](add-autopilot-devices-and-profile.md)を使用してデバイスをアップロードできますが、[**デバイス**] タブでデバイスをアップロードすることもできます。 
  
デバイスは次の要件を満たす必要があります。
  
- Windows 10、バージョン1703以降
    
- Windows の標準外の機能を使用していない新しいデバイス

1. Microsoft 365 Business 管理センターで、[**デバイス** \> **自動操縦**] を選択します。
  
2. [**自動操縦**] ページで、[**デバイス**] タブの [ \> **デバイスの追加**] を選択します。
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. [**デバイスの追加**] パネルで、準備\>した[デバイスリストの CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照して、 **Close**を**保存** \>します。
    
    この情報は、ハードウェアベンダーから入手することも、 [G-et-windowsautopilotinfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使用して CSV ファイルを生成することもできます。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>プロファイルをデバイスまたはデバイスのグループに割り当てる

1. [ **Windows の準備**] ページで、[**デバイス**] タブを選択し、1つ以上のデバイスの横にあるチェックボックスをオンにします。 
    
2. [ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。 
    
    まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。 
    
