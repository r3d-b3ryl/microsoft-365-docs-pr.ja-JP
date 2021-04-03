---
title: 管理センターの Microsoft 365 レポート - SharePoint アクティビティ
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: SharePoint アクティビティ使用状況レポートを取得して、すべての SharePoint ユーザーのアクティビティ、共有されているファイルの数、およびストレージ使用率について知る。
ms.openlocfilehash: 71cea1e4b5875c0c00dd6dc6cb564e01b84cfb77
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579520"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>管理センターの Microsoft 365 レポート - SharePoint アクティビティ

Microsoft 365 管理者として、[レポート] ダッシュボードには、組織内のさまざまな製品のアクティビティの概要が表示されます。 これにより、各製品に固有のアクティビティについてより詳しく知ることができます。 [Microsoft 365 管理センターのアクティビティ レポートを確認してください](activity-reports.md)。
  
たとえば、ファイルの操作を調べることで、SharePoint を使用するライセンスを持つすべてのユーザーのアクティビティを把握できます。また、共有されているファイルの数を調べると、行われているコラボレーションのレベルを把握できます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>SharePoint アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、SharePoint カードの **[その他の** 表示] ボタンをクリックします。
  
## <a name="interpret-the-sharepoint-activity-report"></a>SharePoint アクティビティ レポートの解釈

[アクティビティ] タブを選択すると、SharePoint レポートでアクティビティ **を表示** できます。<br/>![Microsoft 365 レポート - Microsoft SharePoint アクティビティ レポート。](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![SharePoint アクティビティ レポート - 列の選択](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |SharePoint サイトでアクティビティを実行したユーザーの電子メール アドレス。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |ファイル アクティビティが実行された最新の日付、または選択した日付範囲のページが表示された日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。  <br/> |
|表示または編集されたファイル  <br/> |ユーザーがアップロード、ダウンロード、変更、または表示したファイルの数。   <br/> |
|同期されたファイル  <br/> |ユーザーのローカル デバイスから SharePoint サイトに同期されたファイルの数。 <br/> |
|内部で共有されるファイル  <br/> | 組織内のユーザー、またはグループ内のユーザーと共有されたファイルの数 (外部ユーザーを含む場合があります)。  <br/> |
|外部で共有されるファイル  <br/> |組織外のユーザーと共有されているファイルの数。 <br/>|
|アクセスしたページ  <br/> |ユーザーによる一意のページへのアクセス。 <br/>|
|Deleted  <br/> | これは、ユーザーのライセンスが削除されたかどうかを示します。  <br/>  **注:** 削除されたユーザーのアクティビティは、選択した期間中にライセンスを取得した場合でも、レポートに表示されます。 [削除済みの列] は、アクティブではないユーザーに気づく際に役立ちますが、レポート内のデータには反映されます。  <br/> |
|削除日  <br/> |ユーザーのライセンスが削除された日付。 <br/>|
|割り当てられた製品  <br/> |ユーザーにライセンスされている Microsoft 365 製品。|
|||