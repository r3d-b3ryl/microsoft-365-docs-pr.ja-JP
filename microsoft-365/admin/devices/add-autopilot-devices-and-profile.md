---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: AutoPilot をWindowsして、従業員が使用できる状態Windows 10新しいデバイスをセットアップする方法について学習します。
ms.openlocfilehash: 1a2350e836a84870a9eb304196d6c72831f52d60
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176720"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する

AutoPilot Windowsを使用して、ビジネス用の新しい Windows 10 デバイスをセットアップして、従業員に提供するときに使用できる状態にできます。
  
## <a name="device-requirements"></a>デバイスの要件

デバイスは、次の要件を満たす必要があります。
  
- Windows 10バージョン 1703 以降
    
- 最新のエクスペリエンスをWindowsした新しいデバイス
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>セットアップ ガイドを使用して、デバイスとプロファイルを作成する

デバイス グループまたはプロファイルをまだ作成していない場合は、ステップ バイ ステップ ガイドを使用して開始してください。 ガイドを使用[せずに、デバイス](create-and-edit-autopilot-devices.md)[を追加](create-and-edit-autopilot-profiles.md)してプロファイルを割り当てすることもできます。 
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

2. 左側のナビゲーション ウィンドウで、[デバイスの **自動パイロット]** \> **を選択します**。

    ![管理センターで、[デバイス] を選択し、[自動パイロット] を選択します。](../../media/AutoPilot.png)
  
2. [自動 **パイロット] ページで** 、[スタート ガイド] をクリックまたは **タップします**。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. [デバイスの **アップロード .csv付** きファイル] ページで、準備されたファイルがある場所を.CSVし、[次へ] を **開** \> **きます**。 ファイルには 3 つのヘッダーが必要です。
    
    - 列 A:デバイスのシリアル番号
    
    - 列 B:Windows 製品 ID
    
    - 列 C:ハードウェア ハッシュ
    
    この情報は、ハードウェア ベンダーから取得するか [、Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。 
    
    詳細については、[デバイスの一覧の CSV ファイル](../misc/device-list.md)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。 
    
> [!NOTE]
> このスクリプトでは、WMI を使用して、ユーザーがデバイスを自動パイロットに登録するために必要Windowsします。 結果の CSV ファイルが Windows 製品 ID (PKID) の値を収集しないのは正常です。これはデバイスを登録する必要はありません。出力 CSV に PKID が NULL である場合は、完全に問題ありません。 シリアル番号とハードウェア ハッシュだけが設定されます。
    
4. [プロファイルの **割り当て** ] ページで、既存のプロファイルを選択するか、新しいプロファイルを作成できます。 まだ作成していない場合は、作成を求めるメッセージが表示されます。 
    
    プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。
    
    既定の機能は必須であり、自動的に設定されます。 既定の機能は次のとおりです。
    
    - [Cortana、OneDrive OEM 登録をスキップします。
    
    - 会社のブランドを含む、サインイン エクスペリエンスを作成します。
    
    - ConnectアカウントにデバイスをAzure Active Directoryし、デバイスによって管理されるアカウントを自動的に登録Microsoft 365 Business Premium。
    
    詳細については、「概要 [- AutoPilot プロファイルの設定」を参照してください](autopilot-profile-settings.md)。 
    
5. 他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。 
    
    [ **次へ**] を選びます。
    
6. **完了すると、** 作成した (または選択した) プロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されます。 設定は、デバイス ユーザーが次にサインインするときに有効になります。 **[閉じる]** を選択します。

## <a name="related-content"></a>関連コンテンツ

[概要 - AutoPilot プロファイルの設定](autopilot-profile-settings.md) (記事)\
[デバイスとアプリ データを保護するためのオプション](../devices/choose-device-security.md) (記事)
