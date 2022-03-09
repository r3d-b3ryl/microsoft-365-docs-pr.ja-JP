---
title: Microsoft 365 管理センター Yammerアクティビティ レポートをグループ分けする
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
description: 組織でYammer使用されているグループの数と、そのアクティビティについてYammerグループアクティビティ レポートを取得します。
ms.openlocfilehash: bfc6756b6db65a846a767f50f20f9011abf01ef8
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400411"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Microsoft 365管理センターの [レポート] - [グループYammerアクティビティ レポート]

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Yammer グループ アクティビティ レポートでは、組織内の Yammer グループのアクティビティに関する詳細を取得し、作成されて使われている Yammer グループの数を確認できます。
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>グループアクティビティ レポートにアクセスYammer方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、カードの **[その他** の表示] Yammerクリックします。
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer のグループ アクティビティ レポートの内容を理解する

[グループ アクティビティ] タブを選択すると、Yammerレポートでグループ アクティビティ **を表示** できます。<br/>![Microsoft 365レポート - Microsoft Yammerグループ アクティビティ レポート。](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![Yammerグループアクティビティ レポート - 列を選択します。](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

[ **Yammer グループ アクティビティ** ] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|内容|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  <br/> |グループの名前を指定します。 <br/> |
|グループ管理者  <br/> |グループ管理者または所有者の名前。  <br/> |
|削除済み  <br/> |削除されたグループYammerします。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  <br/> |
|型  <br/> |パブリックまたはプライベートのグループの種類。 <br/> |
|ネットワークに接続Office 365  <br/> |ユーザー グループがYammerグループであるかどうかをMicrosoft 365します。 <br/> |
|最終アクティビティ日 (UTC)  <br/> | メッセージがグループによって読み取り、投稿、または気に入った最新の日付。  <br/> |
|メンバー  <br/> | グループ内のメンバーの数。  <br/> |
|投稿  <br/> |レポート期間中にグループにYammerメッセージの数。 <br/>|
|読み取り  <br/> |レポート期間中にグループで読み取Yammer会話の数。  <br/> |
|いいね!  <br/> |レポート期間のグループで気に入Yammerメッセージの数。 <br/>|
|ネットワーク名  <br/> |グループが属するネットワークの完全な名前。 |
|||