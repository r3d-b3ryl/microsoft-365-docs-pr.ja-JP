---
title: Microsoft Defender for Business でデバイスを管理する (プレビュー)
description: Microsoft Defender for Business でデバイスを管理する方法 (プレビュー)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 5bb36ecb0ca2d382ce64a6746b1c6bfcfceff22b
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421140"
---
# <a name="manage-devices-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business でデバイスを管理する (プレビュー)

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

Microsoft Defender for Business (プレビュー) では、次のようにデバイスを管理できます。

- [オンボード デバイスのリストを表示](#view-the-list-of-onboarded-devices) して、リスク レベル、露出レベル、正常性状態を確認する
- [脅威の検出があるデバイス](#take-action-on-a-device-that-has-threat-detections) でアクションを実行する
- [デバイスを Defender for Business にオンボードする (プレビュー)](#onboard-a-device)  
- [Defender for Business からのデバイスのオフボード (プレビュー)](#offboard-a-device)

## <a name="view-the-list-of-onboarded-devices"></a>オンボード デバイスの一覧を表示する

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="デバイス インベントリのスクリーンショット":::

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション ウィンドウで、[デバイス インベントリ] **を選択します**。

3. デバイスを選択して、そのフライアウト パネルを開き、その状態の詳細とアクションを実行できます。 

   デバイスがまだリストされていない場合は、Microsoft Defender for Business にデバイス [をオンボードする (プレビュー)](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>脅威の検出があるデバイスでアクションを実行する

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="利用可能な詳細とアクションを含む選択したデバイスのスクリーンショット":::

1. [ポータル( [https://security.microsoft.com](https://security.microsoft.com) Microsoft 365 Defender] のナビゲーション ウィンドウで、[デバイス インベントリ]**を選択します**。 

2. デバイスを選択して、そのフライアウト パネルを開き、表示される情報を確認します。

3. 省略記号 (**...**) を選択して、[操作] メニューを開きます。 

4. [ウイルス対策スキャンの実行] や **[自動** 調査の開始] **などのアクションを選択します**。 

## <a name="onboard-a-device"></a>デバイスのオンボード

「 [オンボード デバイスから Microsoft Defender for Business (プレビュー)」を参照してください](mdb-onboard-devices.md)。

## <a name="offboard-a-device"></a>デバイスのオフボード

「 [デバイスのオフボード」を参照してください](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device)。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)

- [デバイス グループの作成または編集](mdb-create-edit-device-groups.md)
