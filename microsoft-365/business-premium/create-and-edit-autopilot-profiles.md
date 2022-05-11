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
description: AutoPilot プロファイルを作成してデバイスに適用する方法と、プロファイルを編集または削除したり、デバイスからプロファイルを削除したりする方法について説明します。
ms.openlocfilehash: 231f3f762e1266b5529f36e792d1b4e4a5f11f03
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65320624"
---
# <a name="create-and-edit-autopilot-profiles"></a>AutoPilot プロファイルを作成し編集する

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

## <a name="create-a-profile"></a>プロファイルの作成

プロファイルがデバイスまたはデバイスのグループに割り当てられます。
  
1. Microsoft 365 管理センターで **[デバイス]** \> **[AutoPilot]** を選択します。
  
2. **[AutoPilot]** ページで、**[プロフィール]** タブ\> **[プロフィールの作成]** を選択します。

3. **[プロファイルの作成]** ページで、識別に役立つプロファイルの名前を入力します。たとえば、マーケティングでは、必要な設定をオンにして **[保存]** を選びます。詳細については、「[AutoPilot プロファイルの設定について](m365bp-autopilot-profile-settings.md)」を参照してください。

    ![Enter name and turn on settings in the Create profile panel.](./../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>プロファイルをデバイスに適用する

プロファイルを作成した後、デバイスまたはデバイスのグループに適用することができます。[ステップ バイ ステップ ガイド](m365bp-add-autopilot-devices-and-profile.md)で既存のプロファイルを選んだり、プロファイルを新しいデバイスに適用したり、デバイスまたはデバイスのグループの既存のプロファイルを置き換えたりします。
  
1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[デバイス]** パネルで、**[割り当てられたプロファイル]** のドロップダウンからプロファイルを選び、\> **[保存]** を選択します。

    ![In the Device panel, select an Assigned profile to apply it.](./../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>プロファイルの編集または削除

デバイスにプロファイルを割り当てると、そのデバイスを既にユーザーに渡していても、そのプロファイルを更新できます。デバイスをインターネットに接続すると、セットアップ プロセス中に最新バージョンのプロファイルをダウンロードします。ユーザーがデバイスを出荷時の既定の設定にリセットする場合は、デバイスはもう一度プロファイルに最新の更新プログラムをダウンロードします。
  
### <a name="edit-a-profile"></a>プロファイルを編集する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[プロファイル]** パネルで使用可能な設定を更新して、\> **[保存]** を選択します。

    ユーザーがデバイスをインターネットに接続する前にこの操作を行った場合、プロファイルはセットアップ プロセスに適用されます。

### <a name="delete-a-profile"></a>プロファイルを削除する

1. [ **Windows の準備**] ページで、[ **プロファイル**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[プロファイル]** パネルで **[プロファイルの削除]** \> **[保存]** の順に選択します。

    プロファイルを削除すると、プロファイルが割り当てられていたデバイスまたはデバイスのグループから削除されます。

### <a name="remove-a-profile"></a>プロフィールを削除する

1. [ **Windows の準備**] ページで、[ **デバイス**] タブを選びます。

2. デバイス名の横にあるチェック ボックスをオンにして、**[デバイス]** パネルで、**[割り当てられたプロファイル]** ドロップダウンから **[なし]** を選び、\> **[保存]** を選択します。

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)
