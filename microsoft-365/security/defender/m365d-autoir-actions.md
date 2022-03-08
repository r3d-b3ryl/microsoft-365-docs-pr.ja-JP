---
title: アクション センターでのアクションの表示と管理
description: アクション センターを使用して修復アクションを表示および管理する
keywords: アクション、センター、autoair、自動、調査、応答、修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 775781a5df9149ae99f1a051303f5d55c23f1bab
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323235"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>アクション センターでのアクションの表示と管理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

特定の修復アクションMicrosoft 365 Defender脅威保護機能が提供されます。 次に、いくつかの例を示します:

- [自動調査によって、](m365d-autoir.md) 修復アクションが自動的に実行される、または承認を待つ可能性があります。
- ウイルス対策、マルウェア対策、その他の脅威保護機能により、ファイル、URL、プロセスのブロック、検疫への成果物の送信など、修復アクションが発生する可能性があります。
- セキュリティ運用チームは、高度な狩猟中やアラートや[](advanced-hunting-overview.md)インシデントの調査中など、手動で修復[アクションを](investigate-alerts.md)[実行できます](investigate-incidents.md)。

> [!NOTE]
> 修復アクションを承認または拒否するには、[適切なアクセス許可](m365d-action-center.md#required-permissions-for-action-center-tasks)が必要です。 詳細については、「前提条件」を [参照してください](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。

## <a name="review-pending-actions-in-the-action-center"></a>アクション センターで保留中のアクションを確認する

自動調査を続行し適時完了できるよう、保留中のアクションはできるだけ早く承認 (または拒否) することが重要です。 

1. [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderに移動し</a>、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. アクション センターの [保留中] タブ **で** 、リスト内のアイテムを選択します。 そのフライアウト ウィンドウが開きます。 次に例を示します。

   :::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="アクションを承認または拒否する例。" lightbox="../../media/air-actioncenter-itemselected.png":::

4. フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査ページを開く]** を選択して、調査の詳細を表示します。
   - [承認 **] を** 選択して保留中のアクションを開始します。
   - 保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。
   - [Go **hunt] を** 選択して高度な [ハンティングに入る](advanced-hunting-overview.md)。 

## <a name="undo-completed-actions"></a>完了した操作を元に戻す

デバイスまたはファイルが脅威ではないと判断した場合は、これらのアクションが自動的または手動で実行されたかどうかに関わり、実行された修復アクションを元に戻すことができます。 [アクション センター] の [履歴] **タブ** で、次の操作を元に戻すことができます。  

| アクション ソース | サポートされているアクション |
|:---|:---|
| - 自動調査 <br/>- Microsoft Defender ウイルス対策 <br/>- 手動応答アクション | - デバイスの分離 <br/>- コードの実行を制限する <br/>- ファイルを検疫する <br/>- レジストリ キーを削除する <br/>- サービスを停止する <br/>- ドライバーを無効にする <br/>- スケジュールされたタスクを削除する |

### <a name="undo-one-remediation-action"></a>1 つの修復アクションを元に戻す

1. アクション センター () に移動し[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)、サインインします。

2. [履歴 **] タブ** で、元に戻す操作を選択します。

3. 画面の右側のウィンドウで、[元に戻す] を **選択します**。

### <a name="undo-multiple-remediation-actions"></a>複数の修復アクションを元に戻す

1. [アクション センター] に移動し、https://security.microsoft.com/action-center) サインインします。

2. [履歴 **] タブ** で、元に戻す操作を選択します。 同じアクションの種類を持つアイテムを選択してください。 フライアウト ウィンドウが開きます。

3. フライアウト ウィンドウで、[元に戻す] を **選択します**。

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>複数のデバイス間で検疫からファイルを削除するには 

1. アクション センター () に移動し[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)、サインインします。

2. [履歴 **] タブ** で、検疫ファイルのアクションの **種類を持つファイルを** 選択します。

3. 画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を選択 **します**。

## <a name="next-steps"></a>次の手順

- [自動調査の詳細と結果を表示する](m365d-autoir-results.md)
- [誤検知または誤検知に対処する](m365d-autoir-report-false-positives-negatives.md)
