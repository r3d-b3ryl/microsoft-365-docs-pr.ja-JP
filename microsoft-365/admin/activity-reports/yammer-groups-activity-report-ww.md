---
title: Microsoft 365管理センターのレポート - Yammerアクティビティ レポート
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 組織でYammer使用されているグループの数と、そのアクティビティYammerグループアクティビティ レポートを取得します。
ms.openlocfilehash: 18ed4519a0f7859d8084f2144a58f4a726db530a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59177176"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Microsoft 365管理センターのレポート - Yammerアクティビティ レポート

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Yammer グループ アクティビティ レポートでは、組織内の Yammer グループのアクティビティに関する詳細を取得し、作成されて使われている Yammer グループの数を確認できます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。  
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>グループアクティビティ レポートにアクセスYammer方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、カードの **[その他** の表示] Yammerクリックします。

  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer のグループ アクティビティ レポートの内容を理解する

[グループ アクティビティ] タブを選択すると、Yammerレポートでグループ アクティビティ **を表示** できます。<br/>![Microsoft 365レポート - Microsoft Yammerアクティビティ レポート。](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![Yammerアクティビティ レポート - 列を選択します。](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  <br/> |グループの名前を指定します。 <br/> |
|グループ管理者  <br/> |グループ管理者または所有者の名前。  <br/> |
|Deleted  <br/> |削除されたグループYammerします。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  <br/> |
|型  <br/> |パブリックまたはプライベートのグループの種類。 <br/> |
|ネットワークに接続Office 365  <br/> |ユーザー グループがYammerグループであるかどうかをMicrosoft 365します。 <br/> |
|最終アクティビティ日 (UTC)  <br/> | メッセージがグループによって読み取り、投稿、または気に入った最新の日付。  <br/> |
|メンバー  <br/> | グループ内のメンバーの数。  <br/> |
|投稿  <br/> |レポート期間中に、Yammerグループに投稿されたメッセージの数。 <br/>|
|読み取り  <br/> |レポート期間中にグループで読み取Yammer会話の数。  <br/> |
|いいね!  <br/> |レポート期間中に、Yammerグループで気に入ったメッセージの数。 <br/>|
|ネットワーク名  <br/> |グループが属するネットワークの完全な名前。 |
|||