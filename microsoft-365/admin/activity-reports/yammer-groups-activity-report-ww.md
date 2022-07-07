---
title: Yammer グループのアクティビティ レポートをMicrosoft 365 管理センターする
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
description: Yammer グループアクティビティ レポートを入手して、組織内で作成および使用されている Yammer グループの数とそのアクティビティの詳細を確認します。
ms.openlocfilehash: c4a967a10763d702cdd798059783f15ec6482927
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662572"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>管理センターの Microsoft 365 レポート - Yammer グループ アクティビティ レポート

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Yammer グループ アクティビティ レポートでは、組織内の Yammer グループのアクティビティに関する詳細を取得し、作成されて使われている Yammer グループの数を確認できます。
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>Yammer グループ アクティビティ レポートにアクセス操作方法?

1. 管理センターで、 **レポート** に移動し、[ **使用状況**] を選択します。 
2. ダッシュボードのホームページで、Yammer カードの **[その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer のグループ アクティビティ レポートの内容を理解する

Yammer レポートでグループ アクティビティを表示するには、[ **グループ アクティビティ** ] タブを選択します。

![Microsoft 365 レポート - Microsoft Yammer グループアクティビティ レポート。](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  

![Yammer グループ アクティビティ レポート - 列を選択します。](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 

[ **Yammer グループ アクティビティ** ] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  |グループの名前を指定します。 |
|グループ管理者  |グループ管理者または所有者の名前。  |
|Deleted  |削除された Yammer グループの数。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  |
|型 |グループ、パブリック、プライベートの種類。 |
|Office 365に接続されている  |Yammer グループも Microsoft 365 グループであるかどうかを示します。 |
|最終アクティビティ日 (UTC)  | メッセージがグループによって読み取られた、投稿された、または気に入った最新の日付。  |
|メンバー  | グループ内のメンバーの数。  |
|投稿 |レポート期間に Yammer グループに投稿されたメッセージの数。 |
|読み取り   |レポート期間中に Yammer グループで読み取られた会話の数。   |
|いいね!  |レポート期間中に Yammer グループで気に入ったメッセージの数。 |
|ネットワーク名   |グループが属するネットワークの完全な名前。 |
