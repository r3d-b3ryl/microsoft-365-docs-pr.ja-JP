---
title: SharePoint アクティビティ レポートのMicrosoft 365 管理センター
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
description: SharePoint のライセンスを持つユーザー ファイルの操作、共有されたファイルの数、およびストレージ使用率について説明する SharePoint アクティビティ使用状況レポートを取得します。
ms.openlocfilehash: 4c330c45d3d6a0c906c3ad7e1b4d2391e3be4697
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662626"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>管理センターの Microsoft 365 レポート - SharePoint アクティビティ

Microsoft 365 管理者のレポート ダッシュボードには、組織内のさまざまな製品にわたるアクティビティの概要が表示されます。 これにより、各製品に固有のアクティビティについてより詳しく知ることができます。 [Microsoft 365 管理センターのアクティビティ レポートを](activity-reports.md)確認してください。
  
たとえば、ファイルの操作を調べることで、SharePoint を使用するライセンスを持つすべてのユーザーのアクティビティを把握できます。また、共有されているファイルの数を調べると、行われているコラボレーションのレベルを把握できます。
  
## <a name="how-do-i-get-to-the-sharepoint-activity-report"></a>SharePoint アクティビティ レポートにアクセス操作方法?

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、SharePoint カードの **[その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-sharepoint-activity-report"></a>SharePoint アクティビティ レポートを解釈する

[アクティビティ] タブを選択すると、SharePoint レポートで **アクティビティ** を表示できます。<br/>![Microsoft 365 レポート - Microsoft SharePoint アクティビティ レポート。](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。 

![SharePoint アクティビティ レポート - 列を選択します。](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。  

**SharePoint アクティビティ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を表示できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |SharePoint サイトでアクティビティを実行したユーザーの電子メール アドレス。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |ファイル アクティビティが実行された最新の日付、または選択した日付範囲のページがアクセスされました。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。  <br/> |
|表示または編集されたファイル  <br/> |ユーザーがアップロード、ダウンロード、変更、または表示したファイルの数。   <br/> |
|同期されたファイル  <br/> |ユーザーのローカル デバイスから SharePoint サイトに同期されたファイルの数。 <br/> |
|内部で共有されるファイル  <br/> | 組織内のユーザー、またはグループ内のユーザーと共有されたファイルの数 (外部ユーザーを含む場合があります)。  <br/> |
|外部で共有されるファイル  <br/> |組織外のユーザーと共有されているファイルの数。 <br/>|
|アクセスしたページ  <br/> |ユーザーによる一意のページへのアクセス。 <br/>|
|Deleted  <br/> | これは、ユーザーのライセンスが削除されたことを示します。  <br/>  **メモ：** 削除されたユーザーのアクティビティは、選択した期間中にライセンスが付与されている限り、レポートに表示されます。 [削除済みの列] は、アクティブではないユーザーに気づく際に役立ちますが、レポート内のデータには反映されます。  <br/> |
|削除された日付  <br/> |ユーザーのライセンスが削除された日付。 <br/>|
|割り当てられた製品  <br/> |ユーザーにライセンスが付与されている Microsoft 365 製品。|
|||