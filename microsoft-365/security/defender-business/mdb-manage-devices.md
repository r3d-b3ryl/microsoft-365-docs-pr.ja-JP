---
title: Microsoft Defender for Businessでデバイスを管理する
description: Defender for Business でデバイスを追加、削除、管理する方法、中小企業向けのエンドポイント保護について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: b904f6a6f42b2b218099c46dbf67dc9e1b086bf6
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320484"
---
# <a name="manage-devices-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでデバイスを管理する

Defender for Business では、次のようにデバイスを管理できます。

- [オンボードされたデバイスの一覧を表示](#view-the-list-of-onboarded-devices) して、リスク レベル、露出レベル、正常性状態を確認する
- 脅威の検出[があるデバイスに対してアクションを実行](#take-action-on-a-device-that-has-threat-detections)する
- [Defender for Business にデバイスをオンボードする](#onboard-a-device)  
- [Defender for Business からデバイスをオフボードにする](#offboard-a-device)


## <a name="view-the-list-of-onboarded-devices"></a>オンボードされたデバイスの一覧を表示する

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="デバイス インベントリのスクリーンショット":::

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[ **デバイス インベントリ**] を選択します。

3. デバイスを選択してポップアップ パネルを開き、その状態の詳細を確認してアクションを実行できます。 

   デバイスがまだ一覧にない場合は、 [デバイスを Defender for Business にオンボードする](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>脅威の検出があるデバイスに対してアクションを実行する

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="選択したデバイスのスクリーンショット(詳細とアクションが使用可能)":::

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[デバイス インベントリ]** を選択します。 

2. デバイスを選択してポップアップ パネルを開き、表示される情報を確認します。

3. 省略記号 (**...**) を選択して、アクション メニューを開きます。 

4. 「**ウイルス対策スキャンを実行する**」や「**自動調査を開始する**」などのアクションを選択します。 

## <a name="onboard-a-device"></a>デバイスをオンボードする

[「Defender for Business にデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。

## <a name="offboard-a-device"></a>デバイスのオフボード

[デバイスのオフボードを参照してください](mdb-offboard-devices.md)。

## <a name="next-steps"></a>次の手順

- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)
- [デバイス グループを作成または編集する](mdb-create-edit-device-groups.md)