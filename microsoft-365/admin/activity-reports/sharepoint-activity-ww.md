---
title: 管理センターの Microsoft 365 レポート-SharePoint アクティビティ
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Sharepoint アクティビティの使用状況レポートを取得して、すべての SharePoint ユーザー、共有ファイル数、ストレージ使用率のアクティビティについて把握します。
ms.openlocfilehash: 1d4b288fed9e15139c92bc7e43795393d03ba2fb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649831"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>管理センターの Microsoft 365 レポート-SharePoint アクティビティ

Microsoft 365 管理者としての **レポート** ダッシュボードには、組織内のさまざまな製品におけるアクティビティの概要が表示されます。 これにより、各製品に固有のアクティビティについてより詳しく知ることができます。 [Microsoft 365 管理センターのアクティビティレポート](activity-reports.md)を確認してください。
  
たとえば、ファイルの操作を調べることで、SharePoint を使用するライセンスを持つすべてのユーザーのアクティビティを把握できます。また、共有されているファイルの数を調べると、行われているコラボレーションのレベルを把握できます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>SharePoint アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、SharePoint カードの [ **詳細を表示** ] ボタンをクリックします。
  
## <a name="interpret-the-sharepoint-activity-report"></a>SharePoint アクティビティレポートを解釈する

[ **アクティビティ** ] タブを選択すると、SharePoint レポートでアクティビティを表示できます。<br/>![Microsoft 365 レポート-Microsoft SharePoint アクティビティレポート。](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![SharePoint アクティビティレポート-列の選択](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |SharePoint サイトでアクティビティを実行したユーザーの電子メールアドレス。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |ファイルアクティビティが最後に実行された日付、または選択した日付範囲のページがアクセスされた日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。  <br/> |
|表示または編集されたファイル  <br/> |ユーザーがアップロード、ダウンロード、変更、または表示したファイルの数。   <br/> |
|同期されたファイル  <br/> |ユーザーのローカルデバイスから SharePoint サイトに同期されたファイルの数。 <br/> |
|内部共有ファイル  <br/> | 組織内のユーザーが共有しているファイルの数、またはグループ内のユーザー (外部ユーザーが含まれる可能性があります)。  <br/> |
|外部共有ファイル  <br/> |組織外のユーザーと共有されているファイルの数。 <br/>|
|アクセスしたページ  <br/> |ユーザーが一意のページにアクセスする。 <br/>|
|Deleted  <br/> | これは、ユーザーのライセンスが削除されたことを示します。  <br/>  **注:** 削除されたユーザーのアクティビティは、選択した期間中にライセンスされていた場合に限りレポートに表示されます。 [削除済みの列] は、アクティブではないユーザーに気づく際に役立ちますが、レポート内のデータには反映されます。  <br/> |
|削除された日付  <br/> |ユーザーのライセンスが削除された日付。 <br/>|
|割り当てられた製品  <br/> |ユーザーにライセンスされている Microsoft 365 製品。|
|||