---
title: Microsoft Defender for Business でデバイスを管理する
description: Microsoft Defender for Business でデバイスを管理する方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 33087884da4b3f6e011963535784b14f9c2e9175
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375523"
---
# <a name="manage-devices-in-microsoft-defender-for-business"></a>Microsoft Defender for Business でデバイスを管理する

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

Microsoft Defender for Business では、次のようにデバイスを管理できます。

- [オンボード デバイスのリストを表示](#view-the-list-of-onboarded-devices) して、リスク レベル、露出レベル、正常性状態を確認する
- [脅威の検出があるデバイス](#take-action-on-a-device-that-has-threat-detections) でアクションを実行する
- [デバイスを Defender for Business にオンボードする](#onboard-a-device)  
- [Defender for Business からデバイスをオフボードする](#offboard-a-device)

## <a name="view-the-list-of-onboarded-devices"></a>オンボード デバイスの一覧を表示する

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="デバイス インベントリのスクリーンショット":::

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション ウィンドウで、[デバイス インベントリ] **を選択します**。

3. デバイスを選択して、そのフライアウト パネルを開き、その状態の詳細とアクションを実行できます。 

   デバイスがまだリストされていない場合は [、Microsoft Defender for Business にデバイスをオンボードする](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>脅威の検出があるデバイスでアクションを実行する

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="利用可能な詳細とアクションを含む選択したデバイスのスクリーンショット":::

1. [ポータル( [https://security.microsoft.com](https://security.microsoft.com) Microsoft 365 Defender] のナビゲーション ウィンドウで、[デバイス インベントリ]**を選択します**。 

2. デバイスを選択して、そのフライアウト パネルを開き、表示される情報を確認します。

3. 省略記号 (**...**) を選択して、[操作] メニューを開きます。 

4. [ウイルス対策スキャンの実行] や **[自動** 調査の開始] **などのアクションを選択します**。 

## <a name="onboard-a-device"></a>デバイスのオンボード

「 [オンボード デバイスから Microsoft Defender for Business」を参照してください](mdb-onboard-devices.md)。

## <a name="offboard-a-device"></a>デバイスのオフボード

「 [デバイスのオフボード」を参照してください](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device)。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)

- [デバイス グループの作成または編集](mdb-create-edit-device-groups.md)
