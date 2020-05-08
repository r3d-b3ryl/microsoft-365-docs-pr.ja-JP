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
ms.openlocfilehash: de14012ebf9e7cdd22e41505f316ab665773c670
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165883"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する

Windows 自動操縦を使用して、自分の組織のために**新しい**windows 10 デバイスをセットアップし、従業員に提供するときに使用できる状態にすることができます。
  
## <a name="device-requirements"></a>デバイスの要件

デバイスは次の要件を満たす必要があります。
  
- Windows 10、バージョン1703以降
    
- Windows の標準外の機能を使用していない新しいデバイス
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>セットアップ ガイドを使用して、デバイスとプロファイルを作成する

[![管理センターについて知らせるラベルが変更されていますので、詳細については、aka.ms/aboutM365preview を参照してください。](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

デバイスグループまたはプロファイルをまだ作成していない場合は、まず、ステップバイステップガイドを使用して開始することをお勧めします。 ガイドを使用せずに、[デバイスを追加](create-and-edit-autopilot-devices.md)したり、[プロファイルを割り当て](create-and-edit-autopilot-profiles.md)たりすることもできます。 
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。

2. 左側のナビゲーションウィンドウで、[**デバイス** \> **自動操縦**] を選択します。

    ![管理センターで、[デバイス] を選択し、[自動操縦] を選択します。](../media/AutoPilot.png)
  
2. [**自動操縦**] ページで、[**スタートガイド**] をクリックまたはタップします。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. [**デバイスの一覧を含む .csv ファイルのアップロード**] ページで、準備した場所を参照します。CSV ファイルを開き、[**次へ**] を**開き** \>ます。 ファイルには3つのヘッダーが必要です。
    
    - 列 A:デバイスのシリアル番号
    
    - 列 B:Windows 製品 ID
    
    - 列 C:ハードウェア ハッシュ
    
    この情報は、ハードウェアベンダーから入手することも、 [G-et-windowsautopilotinfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使用して CSV ファイルを生成することもできます。 
    
    詳細については、[デバイスの一覧の CSV ファイル](https://docs.microsoft.com/microsoft-365/admin/misc/device-list)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。 
    
4. [**プロファイルの割り当て**] ページで、既存のプロファイルを選択するか、または新しいプロファイルを作成することができます。 まだ持っていない場合は、作成するように求められます。 
    
    プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。
    
    既定の機能は必須であり、自動的に設定されます。 既定の機能は次のとおりです。
    
    - Cortana、OneDrive、OEM 登録をスキップします。
    
    - 会社のブランドを含む、サインイン エクスペリエンスを作成します。
    
    - デバイスを Azure Active Directory アカウントに接続し、Microsoft 365 Business Premium によって管理されるように自動的に登録します。
    
    詳細については、「[自動操縦プロファイルの設定につい](autopilot-profile-settings.md)て」を参照してください。 
    
5. 他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。 
    
    [ **次へ**] を選びます。
    
6. **完了し**たら、作成した (または選択した) プロファイルが、デバイスの一覧をアップロードして作成したデバイスグループに適用されることを示します。 この設定は、デバイスユーザーが次にサインインしたときに有効になります。 **[閉じる]** を選択します。
    
