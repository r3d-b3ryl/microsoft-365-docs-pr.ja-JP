---
title: アクション センターでアクションを表示および管理する
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
ms.openlocfilehash: 43c48081a86e33cd918bc4de8f01859bc1107583
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666836"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>アクション センターでアクションを表示および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defenderの脅威保護機能により、特定の修復アクションが発生する可能性があります。 次に、いくつかの例を示します:

- [自動調査を](m365d-autoir.md) 行うと、自動的に実行されるか、承認を待つ修復アクションが発生する可能性があります。
- ウイルス対策、マルウェア対策、その他の脅威保護機能により、ファイル、URL、またはプロセスをブロックしたり、アーティファクトを検疫に送信したりするなどの修復アクションが発生する可能性があります。
- セキュリティ運用チームは、 [高度な捜索](advanced-hunting-overview.md) 中や [アラート](investigate-alerts.md) や [インシデント](investigate-incidents.md)の調査中など、修復アクションを手動で実行できます。

> [!NOTE]
> 修復アクションを承認または拒否するには、[適切なアクセス許可](m365d-action-center.md#required-permissions-for-action-center-tasks)が必要です。 詳細については、前提条件を参照 [してください](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。

## <a name="review-pending-actions-in-the-action-center"></a>アクション センターで保留中のアクションを確認する

自動調査を続行し適時完了できるよう、保留中のアクションはできるだけ早く承認 (または拒否) することが重要です。 

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. アクション センターの [ **保留中]** タブで、リスト内の項目を選択します。 ポップアップ ウィンドウが開きます。 次に例を示します。

   :::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="アクションを承認または拒否するオプション" lightbox="../../media/air-actioncenter-itemselected.png":::

4. ポップアップ ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査を開く] ページ** を選択して、調査の詳細を表示します。
   - [ **承認] を** 選択して保留中のアクションを開始します。
   - 保留中のアクションが実行されないようにするには、[ **拒否] を** 選択します。
   - [ **Go hunt** ] を選択して [高度なハンティング](advanced-hunting-overview.md)に移動します。 

## <a name="undo-completed-actions"></a>完了したアクションを元に戻す

デバイスまたはファイルが脅威でないと判断した場合は、それらのアクションが自動的に実行されたか手動で実行されたかに関係なく、実行された修復アクションを元に戻すことができます。 アクション センターの [ **履歴** ] タブでは、次のいずれかの操作を元に戻すことができます。  

| アクション ソース | サポートされているアクション |
|:---|:---|
| - 自動調査 <br/>- Microsoft Defender ウイルス対策 <br/>- 手動応答アクション | - デバイスの分離 <br/>- コードの実行を制限する <br/>- ファイルの検疫 <br/>- レジストリ キーの削除 <br/>- サービスの停止 <br/>- ドライバーの無効化 <br/>- スケジュールされたタスクの実行 |

### <a name="undo-one-remediation-action"></a>1 つの修復アクションを元に戻す

1. アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) に移動し、サインインします。

2. **[履歴]** タブで、元に戻す処理を選択します。

3. 画面の右側のウィンドウで、**[元に戻す]** を選択します。

### <a name="undo-multiple-remediation-actions"></a>複数の修復アクションを元に戻す

1. アクション センターに移動し、https://security.microsoft.com/action-center) サインインします。

2. **[履歴]** タブで、元に戻す処理を選択します。 必ず、同じアクションの種類を持つ項目を選択してください。 ポップアップ ウィンドウが開きます。

3. ポップアップ ウィンドウで **[元に戻す]** を選択します。

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>複数のデバイス間で検疫からファイルを削除するには 

1. アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) に移動し、サインインします。

2. [ **履歴** ] タブで、検疫ファイルアクションの種類を持つ **ファイルを** 選択します。

3. 画面の右側のウィンドウで、**[このファイルのその他 X 個のインスタンスに適用する]** を選択し、**[元に戻す]** を選択します。

## <a name="next-steps"></a>次の手順

- [自動調査の詳細と結果を表示する](m365d-autoir-results.md)
- [false positives または false negatives に対処する](m365d-autoir-report-false-positives-negatives.md)
