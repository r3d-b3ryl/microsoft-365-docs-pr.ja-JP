---
title: Autopilot プロファイルを作成し編集する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Autopilot プロファイルを作成してデバイスに適用し、プロファイルを編集または削除するか、デバイスからプロファイルを削除する方法について説明します。
ms.openlocfilehash: 6f019e494eb073f47921f4adef454c0e48541b49
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489698"
---
# <a name="create-and-edit-autopilot-profiles"></a>Autopilot プロファイルを作成し編集する

[Windows Autopilot 展開プロファイル](/mem/autopilot/profiles)は、[device グループ](m365bp-device-groups-mdb.md)にあるデバイスに適用できます。 展開プロファイルは、ユーザーが持つ Windows の展開と登録のエクスペリエンスを決定します。 

## <a name="create-a-profile"></a>プロファイルの作成

プロファイルがデバイスまたはデバイスのグループに割り当てられます。
  
1. Microsoft 365 管理センターで、[ **デバイス** \> **Autopilot** ]を選択します。
  
2. [ **Autopilot** ] ページで、[ **プロファイル** ] タブ \>[ **プロファイルの作成**] を選択します。

3. **プロファイルの作成** ページで、プロファイルを識別するのに役立つプロファイルの名前 (例えばマーケティングなど) を入力します。 目的の設定をオンにし、[**保存**] を選びます。 Autopilot プロファイル設定の詳細については、「 [Autopilot プロファイル設定について](m365bp-Autopilot-profile-settings.md)」を参照してください。

    ![Enter name and turn on settings in the Create profile panel.](./../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>プロファイルをデバイスに適用する

プロファイルを作成した後、デバイスまたはデバイスのグループに適用することができます。[ステップ バイ ステップ ガイド](m365bp-add-Autopilot-devices-and-profile.md)で既存のプロファイルを選んだり、プロファイルを新しいデバイスに適用したり、デバイスまたはデバイスのグループの既存のプロファイルを置き換えたりします。
  
1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[デバイス]** パネルで、**[割り当てられたプロファイル]** のドロップダウンからプロファイルを選び、\> **[保存]** を選択します。

    ![In the Device panel, select an Assigned profile to apply it.](./../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>プロファイルの編集または削除

デバイスにプロファイルを割り当てると、そのデバイスを既にユーザーに渡していても、そのプロファイルを更新できます。デバイスをインターネットに接続すると、セットアップ プロセス中に最新バージョンのプロファイルをダウンロードします。ユーザーがデバイスを出荷時の既定の設定にリセットする場合は、デバイスはもう一度プロファイルに最新の更新プログラムをダウンロードします。
  
### <a name="edit-a-profile"></a>プロファイルを編集する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[プロファイル]** パネルで使用可能な設定を更新して、\> **[保存]** を選択します。

    ユーザーがデバイスをインターネットに接続する前にこのタスクを実行すると、プロファイルがセットアップ プロセスに適用されます。

### <a name="delete-a-profile"></a>プロファイルを削除する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[プロファイル]** パネルで **[プロファイルの削除]** \> **[保存]** の順に選択します。

    プロファイルを削除すると、プロファイルが割り当てられていたデバイスまたはデバイスのグループから削除されます。

### <a name="remove-a-profile"></a>プロフィールを削除する

1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[デバイス]** パネルで、**[割り当てられたプロファイル]** ドロップダウンから **[なし]** を選び、\> **[保存]** を選択します。

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)
