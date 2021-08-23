---
title: AutoPilot プロファイルの作成と編集
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: AutoPilot プロファイルを作成してデバイスに適用する方法と、プロファイルを編集または削除する方法、またはデバイスからプロファイルを削除する方法について学習します。
ms.openlocfilehash: 4f54b4baac1cd9364d852116115f07fae021b823
ms.sourcegitcommit: 251551539b1532fdac7b7e3dd2733a75c62e8a54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58360622"
---
# <a name="create-and-edit-autopilot-profiles"></a>AutoPilot プロファイルを作成し編集する

## <a name="create-a-profile"></a>プロファイルの作成

プロファイルがデバイスまたはデバイスのグループに割り当てられます。
  
1. [デバイス] Microsoft 365 管理センター[**デバイス** \> **の自動パイロット] を選択します**。
  
2. **[AutoPilot] ページで**、[プロファイル] タブ **の [プロファイルの作成** \> **] を選択します**。
    
3. [プロファイル **の作成] ページ** で、プロファイルを識別するのに役立つプロファイルの名前 (マーケティングなど) を入力します。 必要な設定をオンにし、[保存] を **選択します**。 AutoPilot プロファイル設定の詳細については、「自動パイロット プロファイル設定について [」を参照してください](autopilot-profile-settings.md)。
    
    ![Enter name and turn on settings in the Create profile panel.](../../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>プロファイルをデバイスに適用する

プロファイルを作成した後、それをデバイスまたはデバイスのグループに適用できます。 ステップ バイ ステップ ガイドで既存[](add-autopilot-devices-and-profile.md)のプロファイルを選択し、それを新しいデバイスに適用するか、デバイスまたはデバイスのグループの既存のプロファイルを置き換えます。 
  
1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。 
    
2. デバイス名の横にあるチェック ボックスをオンにし、[デバイス] パネルで 、[割り当てられたプロファイル] ドロップダウン リストからプロファイルを選択 \> **します**。
    
    ![In the Device panel, select an Assigned profile to apply it.](../../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>プロファイルの編集または削除

デバイスにプロファイルを割り当てると、そのデバイスを既にユーザーに渡していても、そのプロファイルを更新できます。デバイスをインターネットに接続すると、セットアップ プロセス中に最新バージョンのプロファイルをダウンロードします。ユーザーがデバイスを出荷時の既定の設定にリセットする場合は、デバイスはもう一度プロファイルに最新の更新プログラムをダウンロードします。 
  
### <a name="edit-a-profile"></a>プロファイルを編集する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。 
    
2. デバイス名の横にあるチェック ボックスをオンにし、[プロファイル] パネルで、使用可能な設定の [保存] を更新 \> **します**。
    
    ユーザーがデバイスをインターネットに接続する前にこの操作を行った場合、プロファイルはセットアップ プロセスに適用されます。
    
### <a name="delete-a-profile"></a>プロファイルを削除する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。 
    
2. デバイス名の横にあるチェック ボックスをオンにし、[プロファイル] パネルで [プロファイルの保存を削除]**を** \> **選択します**。
    
    プロファイルを削除すると、プロファイルが割り当てられていたデバイスまたはデバイスのグループから削除されます。
    
### <a name="remove-a-profile"></a>プロフィールを削除する

1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。 
    
2. デバイス名の横にあるチェック ボックスをオンにし、[デバイス] パネルで、[割り当てられたプロファイル] ドロップダウン リストの [保存] から [**なし**] を選択 \> **します**。
    
