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
ms.localizationpriority: medium
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
description: AutoPilot を使用してデバイスをアップロードする方法については、Microsoft 365 Business Premium。 プロファイルは、デバイスまたはデバイスのグループに割り当てできます。
ms.openlocfilehash: 784db256bb5dae16739722566b6f7a9c8511a678
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313889"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot デバイスを作成し編集する

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../../security/defender-business/mdb-overview.md)。

## <a name="upload-a-list-of-devices"></a>デバイスの一覧をアップロードする

デバイスをアップロード [するには、ステップ バイ](add-autopilot-devices-and-profile.md) ステップ ガイドを使用できますが、[デバイス] タブでデバイスを **アップロード** することもできます。 
  
デバイスは、次の要件を満たす必要があります。
  
- Windows 10バージョン 1703 以降
    
- 最新のエクスペリエンスをWindowsした新しいデバイス

1. [デバイス] Microsoft 365 管理センター[**デバイスの自動** パイロット] \> **を選択します**。
  
2. [自動 **パイロット] ページで、[** デバイス] タブ [デバイス **の** 追加 **] を**\>選択します。
    
    ![In the Devices tab, choose Add devices.](../../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. [デバイスの **追加] パネル** で、[閉じる保存] を準備した [デバイス リスト CSV](../misc/device-list.md) ファイル\>**を参照** \> **します**。
    
    この情報は、ハードウェア ベンダーから取得するか、 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>プロファイルをデバイスまたはデバイスのグループに割り当てる

1. [デバイス **の準備Windows**] ページで、[デバイス]  タブを選択し、1 つ以上のデバイスの横にあるチェック ボックスをオンにします。 
    
2. [ **デバイス**] パネルで、[ **割り当てられたプロファイル**] ドロップダウンからプロファイルを選択します。 
    
    まだプロファイルがない場合は、「[AutoPilot プロファイルの作成と編集](create-and-edit-autopilot-profiles.md)」の手順をご覧ください。 

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../security-and-compliance/secure-your-business-data.md)