---
title: Microsoft 365 OneDrive for Businessアクティビティ レポート
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 組織のOneDriveレポートを取得し、すべてのユーザーのOneDrive、共有されているファイルの数、および記憶域の使用率を知っています。
ms.openlocfilehash: 52e925774ba2315f582f1b5ba50a4a75fe221c10
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400797"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365管理センターの [レポート] - OneDrive for Businessアクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、OneDrive でのファイルの操作を調べることで、OneDrive を使用するライセンスを持つすべてのユーザーのアクティビティを把握できます。また、共有されているファイルの数を調べると、行われているコラボレーションのレベルを把握できます。

## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>OneDrive アクティビティ レポートの作成方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、カードの [その他の表示] OneDriveクリックします。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>OneDrive for Business アクティビティ レポートの解釈

[アクティビティ] タブを選択すると、OneDriveレポートでアクティビティ **を表示** できます。<br/>![Microsoft 365レポート - Microsoft OneDriveアクティビティ レポート。](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![OneDriveアクティビティ レポート - 列を選択します。](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。

**OneDrive for Business アクティビティ** レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|内容|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザー アカウントの所有者のユーザー OneDriveします。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |選択した日付範囲のユーザー アカウントでOneDriveアクティビティが実行された最新の日付。 . 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。  <br/> |
|表示または編集されたファイル  <br/> |ユーザーがアップロード、ダウンロード、変更、または表示したファイルの数。   <br/> |
|同期されたファイル  <br/> |ユーザーのローカル デバイスからユーザー アカウントに同期されたファイルOneDriveします。 <br/> |
|内部で共有されるファイル  <br/> | 組織内のユーザー、またはグループ内のユーザーと共有されているファイルの数 (外部ユーザーを含む場合があります)。  <br/> |
|外部で共有されるファイル  <br/> |組織外のユーザーと共有されているファイルの数。 <br/>|
|削除済み  <br/> | これは、ユーザーのライセンスが削除されたかどうかを示します。  <br/> 注: 削除されたユーザーのアクティビティは、選択した期間中にライセンスを取得された場合でも、レポートに表示されます。 [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。  <br/> |
|削除日  <br/> |ユーザーのライセンスが削除された日付。 <br/>|
|割り当てられた製品  <br/> |ユーザー Microsoft 365ライセンスされている製品の一覧です。|
|||