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
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: e08c53dd949858a1fcc9af9c8553c5d0eed07cef
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65173087"
---
# <a name="manage-devices-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでデバイスを管理する

Microsoft Defender for Businessでは、次のようにデバイスを管理できます。

- [オンボードされたデバイスの一覧を表示](#view-the-list-of-onboarded-devices) して、リスク レベル、露出レベル、正常性状態を確認する
- 脅威の検出[があるデバイスに対してアクションを実行](#take-action-on-a-device-that-has-threat-detections)する
- [Defender for Business にデバイスをオンボードする](#onboard-a-device)  
- [Defender for Business からデバイスをオフボードにする](#offboard-a-device)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="view-the-list-of-onboarded-devices"></a>オンボードされたデバイスの一覧を表示する

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="デバイス インベントリのスクリーンショット":::

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[ **デバイス インベントリ**] を選択します。

3. デバイスを選択してポップアップ パネルを開き、その状態の詳細を確認してアクションを実行できます。 

   デバイスがまだ一覧にない場合は、[デバイスをMicrosoft Defender for Businessにオンボードする](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>脅威の検出があるデバイスに対してアクションを実行する

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="選択したデバイスのスクリーンショット(詳細とアクションが使用可能)":::

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、[**デバイス インベントリ**] を選択します。 

2. デバイスを選択してポップアップ パネルを開き、表示される情報を確認します。

3. 省略記号 (**...**) を選択して、アクション メニューを開きます。 

4. **ウイルス対策スキャンの実行** や **自動調査の開始** などのアクションを選択します。 

## <a name="onboard-a-device"></a>デバイスをオンボードする

[「Microsoft Defender for Businessにデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。

## <a name="offboard-a-device"></a>デバイスのオフボード

[デバイスのオフボードを参照してください](mdb-offboard-devices.md)。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)
- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)
- [デバイス グループを作成または編集する](mdb-create-edit-device-groups.md)