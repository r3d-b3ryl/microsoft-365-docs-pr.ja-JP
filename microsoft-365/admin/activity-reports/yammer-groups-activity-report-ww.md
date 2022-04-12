---
title: Microsoft 365 管理センター Yammer グループ アクティビティ レポート
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
description: 組織で作成および使用されているYammer グループの数とそのアクティビティについて知るために、Yammer グループ アクティビティ レポートを取得します。
ms.openlocfilehash: 443129beaf39a2e46bd5fbcb18bdb9cd9b4770c3
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781259"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>管理センターでレポートをMicrosoft 365する - Yammer グループ アクティビティ レポート

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Yammer グループ アクティビティ レポートでは、組織内の Yammer グループのアクティビティに関する詳細を取得し、作成されて使われている Yammer グループの数を確認できます。
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>Yammer グループ アクティビティ レポートにアクセス操作方法?

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Yammer カードの **[その他の表示**] ボタンをクリックします。
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer のグループ アクティビティ レポートの内容を理解する

グループ アクティビティ タブを選択すると、Yammer レポートで **グループ アクティビティ** を表示できます。<br/>![Microsoft 365 レポート - Microsoft Yammer グループ アクティビティ レポート。](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![Yammer グループ アクティビティ レポート - 列を選択します。](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

[ **Yammer グループ アクティビティ** ] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  <br/> |グループの名前を指定します。 <br/> |
|グループ管理者  <br/> |グループ管理者または所有者の名前。  <br/> |
|Deleted  <br/> |削除されたYammer グループの数。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  <br/> |
|型  <br/> |グループ、パブリック、プライベートの種類。 <br/> |
|Office 365に接続されている  <br/> |Yammer グループもMicrosoft 365 グループであるかどうかを示します。 <br/> |
|最終アクティビティ日 (UTC)  <br/> | メッセージがグループによって読み取られた、投稿された、または気に入った最新の日付。  <br/> |
|メンバー  <br/> | グループ内のメンバーの数。  <br/> |
|投稿  <br/> |レポート期間にYammer グループに投稿されたメッセージの数。 <br/>|
|読み取り  <br/> |レポート期間中にYammer グループで読み取られた会話の数。  <br/> |
|いいね!  <br/> |レポート期間中にYammer グループで気に入ったメッセージの数。 <br/>|
|ネットワーク名  <br/> |グループが属するネットワークの完全な名前。 |
|||