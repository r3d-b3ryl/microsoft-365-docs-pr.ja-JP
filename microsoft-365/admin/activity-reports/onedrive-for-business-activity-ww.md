---
title: Microsoft 365 OneDrive for Business アクティビティ レポート
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
description: 組織の OneDrive 使用状況レポートを取得し、すべての OneDrive ユーザーのアクティビティ、共有されたファイルの数、ストレージ使用率を確認します。
ms.openlocfilehash: 02290333af41ee5e5773c0979fef1c282f2e0e21
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662635"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>管理センターの Microsoft 365 レポート - OneDrive for Business アクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、OneDrive でのファイルの操作を調べることで、OneDrive を使用するライセンスを持つすべてのユーザーのアクティビティを把握できます。また、共有されているファイルの数を調べると、行われているコラボレーションのレベルを把握できます。

## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>OneDrive アクティビティ レポートの作成方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、OneDrive カードの [ **その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>OneDrive for Business アクティビティ レポートの解釈

[アクティビティ] タブを選択すると、OneDrive レポートで **アクティビティ** を表示できます。<br/>![Microsoft 365 レポート - Microsoft OneDrive アクティビティ レポート。](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![OneDrive アクティビティ レポート - 列を選択します。](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 

**OneDrive for Business アクティビティ** レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |OneDrive アカウントの所有者のユーザー名。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |選択した日付範囲の OneDrive アカウントで、最新の日のファイル アクティビティが発生しました。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。  <br/> |
|表示または編集されたファイル  <br/> |ユーザーがアップロード、ダウンロード、変更、または表示したファイルの数。   <br/> |
|同期されたファイル  <br/> |ユーザーのローカル デバイスから OneDrive アカウントに同期されたファイルの数。 <br/> |
|内部で共有されるファイル  <br/> | 組織内のユーザー、またはグループ内のユーザーと共有されているファイルの数 (外部ユーザーを含む場合があります)。  <br/> |
|外部で共有されるファイル  <br/> |組織外のユーザーと共有されているファイルの数。 <br/>|
|Deleted  <br/> | これは、ユーザーのライセンスが削除されたことを示します。  <br/> 注: 削除されたユーザーのアクティビティは、選択した期間中にライセンスが付与されている限り、レポートに引き続き表示されます。 [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。  <br/> |
|削除された日付  <br/> |ユーザーのライセンスが削除された日付。 <br/>|
|割り当てられた製品  <br/> |ユーザーにライセンスが付与されている Microsoft 365 製品。|
|||