---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: お客様のビジネスの新しい Windows 10 デバイスを設定するのには Windows の自動操縦装置を使用する方法について説明します。
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868997"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する

従業員にデバイスを渡すとすぐに生産的に使用できるように、Windows AutoPilot を使ってビジネス用に新しい Windows 10 デバイスを設定することができます。
  
## <a name="device-requirements"></a>デバイスの要件

デバイスは次の要件を満たしている必要があります。
  
- Windows 10 バージョン 1703 以降。
    
- Windows out-of-box experience を行っていない新しいデバイス。
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>セットアップ ガイドを使用して、デバイスとプロファイルを作成する

まだ作成したデバイス グループまたはプロファイルがない場合は、ステップ バイ ステップ ガイドを使用して開始するのが最適な方法ですが、ガイドを使用せずに、[デバイスを追加](create-and-edit-autopilot-devices.md)して[プロファイルを割り当てる](create-and-edit-autopilot-profiles.md)こともできます。 
  
1. Microsoft 365 Business 管理センターで [ **デバイス アクション**] カードを見つけて、[ **AutoPilot で Windows を展開する**] を選びます。
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. [ **Windows の準備**] ページで、[ **スタート ガイド**] をクリックまたはタップします。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. **デバイスのリストを使用して .csv ファイルのアップロード**] ページで、ある、準備の場所を参照します。CSV ファイルを**開いている** \> **次**です。3 つのヘッダーがあります。
    
  - 列 A:デバイスのシリアル番号
    
  - 列 B:Windows 製品 ID
    
  - 列 C:ハードウェア ハッシュ
    
    この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。 
    
    詳細については、[デバイスの一覧の CSV ファイル](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。 
    
4. [ **プロファイルの割り当て**] ページで、既存のプロファイルを選択するか、新しいプロファイルを作成します。まだプロファイルがない場合は、新しく作成するように求めるメッセージが表示されます。 
    
    プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。
    
    既定の機能は必須であり、自動的に設定されます。既定の機能は次のとおりです。
    
  - Cortana、OneDrive、および OEM の登録はスキップされます。
    
  - 会社のブランドを含む、サインイン エクスペリエンスを作成します。
    
  - 使用しているデバイスは、Azure Active Directory アカウントに接続され、Microsoft 365 Business で管理されるように自動的に登録されます。
    
    詳しくは、
    
    「[AutoPilot プロファイルの設定について](autopilot-profile-settings.md)」をご覧ください。 
    
5. 他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。 
    
    [ **次へ**] を選びます。
    
6. [ **完了しました**] ページでは、作成 (または選択) したプロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されることを示しています。デバイスのユーザーが次にサインインすると、これらの設定が有効になります。[ **閉じる**] を選びます。
    