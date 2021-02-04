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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Windows AutoPilot を使用して、従業員が使用する準備が整ったビジネス向け新しい Windows 10 デバイスをセットアップする方法について学習します。
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099752"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する

Windows AutoPilot を使用して、ビジネス向 **け新しい** Windows 10 デバイスをセットアップし、従業員に提供するときに使用する準備が整います。
  
## <a name="device-requirements"></a>デバイスの要件

デバイスは、次の要件を満たす必要があります。
  
- Windows 10 バージョン 1703 以降
    
- Windows の Out-Of-Box Experience を使用していない新しいデバイス
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>セットアップ ガイドを使用して、デバイスとプロファイルを作成する

[![管理センターについて知らせるラベルが変更されていますので、詳細については、aka.ms/aboutM365preview を参照してください。](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

デバイス グループまたはプロファイルをまだ作成していない場合は、ステップ バイ ステップ ガイドを使用して開始する最適な方法です。 また、ガイド[を使用せずにデバイス](create-and-edit-autopilot-devices.md)[を追加](create-and-edit-autopilot-profiles.md)し、プロファイルを割り当てすることもできます。 
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。

2. 左側のナビゲーション ウィンドウで **、[Devices** \> **AutoPilot] を選択します**。

    ![管理センターで、デバイスを選択してから AutoPilot を選択します。](../media/AutoPilot.png)
  
2. **[AutoPilot] ページで**、[スタート ガイド] をクリック **またはタップします**。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. [デバイスの **一覧を含む .csv** ファイルのアップロード] ページで、準備した場所を参照します。CSV ファイルを開き、[ **次へ] を** \> **開きます**。 ファイルには 3 つのヘッダーが必要です。
    
    - 列 A:デバイスのシリアル番号
    
    - 列 B:Windows 製品 ID
    
    - 列 C:ハードウェア ハッシュ
    
    この情報は、ハードウェア ベンダーから取得するか [、Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。 
    
    詳細については、[デバイスの一覧の CSV ファイル](https://docs.microsoft.com/microsoft-365/admin/misc/device-list)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。 
    
> [!NOTE]
> このスクリプトは WMI を使用して、ユーザーが Windows Autopilot にデバイスを登録するために必要なプロパティを取得します。 出力 CSV にデバイスを登録する必要はありません。出力 CSV で PKID が NULL の場合は問題ありません。結果の CSV ファイルで Windows 製品 ID (PKID) の値を収集しないのは通常です。 シリアル番号とハードウェア ハッシュだけが設定されます。
    
4. [プロファイル **の割り当て** ] ページでは、既存のプロファイルを選択するか、新しいプロファイルを作成できます。 まだ作成していない場合は、作成するように求めるメッセージが表示されます。 
    
    プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。
    
    既定の機能は必須であり、自動的に設定されます。 既定の機能は次のとおりです。
    
    - Cortana、OneDrive、OEM 登録をスキップします。
    
    - 会社のブランドを含む、サインイン エクスペリエンスを作成します。
    
    - デバイスを Azure Active Directory アカウントに接続し、Microsoft 365 Business Premium によって管理されるデバイスを自動的に登録します。
    
    詳細については [、「AutoPilot プロファイルの設定について」を参照してください](autopilot-profile-settings.md)。 
    
5. 他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。 
    
    [ **次へ**] を選びます。
    
6. **完了すると、** 作成 (または選択) したプロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されます。 設定は、デバイス ユーザーが次にサインインするときに有効になります。 **[閉じる]** を選択します。
    
