---
title: AutoPilot プロファイルの作成と編集
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 自動操縦プロファイルを作成してデバイスに適用するだけでなく、プロファイルを編集または削除したり、デバイスからプロファイルを削除したりする方法について説明します。
ms.openlocfilehash: e58418813ed0b4d23a5fa7e1d23aae33d8850e7f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400976"
---
# <a name="create-and-edit-autopilot-profiles"></a>AutoPilot プロファイルを作成し編集する

## <a name="create-a-profile"></a>プロファイルの作成

プロファイルがデバイスまたはデバイスのグループに割り当てられます。
  
1. Microsoft 365 管理センターで、[**デバイス** \> **自動操縦**] を選択します。
  
2. [**自動操縦**] ページで、[**プロファイル] タブ**を選択してプロファイルを \> **作成**します。
    
3. [**プロファイルの作成**] ページで、「Marketing」などの特定に役立つプロファイルの名前を入力します。 目的の設定を有効にして、[**保存**] を選択します。 自動操縦プロファイル設定の詳細については、「[自動操縦プロファイル設定につい](autopilot-profile-settings.md)て」を参照してください。
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>プロファイルをデバイスに適用する

プロファイルを作成したら、それをデバイスまたはデバイスのグループに適用できます。 [ステップバイステップガイド](add-autopilot-devices-and-profile.md)で既存のプロファイルを選択して新しいデバイスに適用したり、デバイスまたはデバイスのグループの既存のプロファイルを置き換えたりすることができます。 
  
1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。 
    
2. デバイス名の横にあるチェックボックスをオンにし、[**デバイス**] パネルで、[**割り当てられたプロファイル**] ドロップダウンリストからプロファイルを選択し \> **Save**ます。
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>プロファイルの編集または削除

デバイスにプロファイルを割り当てると、そのデバイスを既にユーザーに渡していても、そのプロファイルを更新できます。デバイスをインターネットに接続すると、セットアップ プロセス中に最新バージョンのプロファイルをダウンロードします。ユーザーがデバイスを出荷時の既定の設定にリセットする場合は、デバイスはもう一度プロファイルに最新の更新プログラムをダウンロードします。 
  
### <a name="edit-a-profile"></a>プロファイルを編集する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。 
    
2. デバイス名の横にあるチェックボックスをオンにし、[**プロファイル**] パネルで、利用可能な設定の保存を更新し \> **Save**ます。
    
    ユーザーがデバイスをインターネットに接続する前にこの操作を行った場合、プロファイルはセットアップ プロセスに適用されます。
    
### <a name="delete-a-profile"></a>プロファイルを削除する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。 
    
2. デバイス名の横にあるチェックボックスをオンにし、[**プロファイル**] パネルで [**プロファイル**の保存の削除] を選択し \> **Save**ます。
    
    プロファイルを削除すると、プロファイルが割り当てられていたデバイスまたはデバイスのグループから削除されます。
    
### <a name="remove-a-profile"></a>プロフィールを削除する

1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。 
    
2. デバイス名の横にあるチェックボックスをオンにし、[**デバイス**] パネルで、[**割り当てられたプロファイル**] ドロップダウン**リストから [** 保存] を選択し \> **Save**ます。
    
