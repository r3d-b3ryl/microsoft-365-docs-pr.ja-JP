---
title: 管理センターの Microsoft 365 レポート-Yammer groups アクティビティレポート
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
description: Yammer グループアクティビティレポートを取得して、組織で作成され、使用されている Yammer グループの数とそのアクティビティを把握します。
ms.openlocfilehash: db2136e049e448b1727dc4612256288da2c64402
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779342"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>管理センターの Microsoft 365 レポート-Yammer groups アクティビティレポート

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Yammer グループ アクティビティ レポートでは、組織内の Yammer グループのアクティビティに関する詳細を取得し、作成されて使われている Yammer グループの数を確認できます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>Yammer グループアクティビティレポートにアクセスするにはどうすればよいですか?

1. 管理センターで、[ **レポート** ] \> [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、Yammer カードの [ **詳細表示** ] ボタンをクリックします。

  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer のグループ アクティビティ レポートの内容を理解する

Yammer レポートでグループアクティビティを表示するには、[ **グループアクティビティ** ] タブを選択します。<br/>![Microsoft 365 レポート-Microsoft Yammer groups アクティビティレポート。](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Yammer グループアクティビティレポート-列の選択](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

また、[ **エクスポート** ] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  <br/> |グループの名前を指定します。 <br/> |
|グループ管理者  <br/> |グループ管理者または所有者の名前。  <br/> |
|Deleted  <br/> |削除された Yammer グループの数。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  <br/> |
|型  <br/> |グループの種類 (パブリックまたはプライベート)。 <br/> |
|Office 365 に接続されている  <br/> |Yammer グループが Microsoft 365 グループでもあるかどうかを示します。 <br/> |
|最後のアクティビティの日付 (UTC)  <br/> | グループによってメッセージが開封、投稿、または好評にされた最新の日付。  <br/> |
|メンバー  <br/> | グループ内のメンバーの数。  <br/> |
|投稿  <br/> |レポート期間中に Yammer グループに投稿されたメッセージの数。 <br/>|
|読み取り  <br/> |レポート期間中に Yammer グループで読み取られた会話の数です。  <br/> |
|いいね!  <br/> |Yammer グループでレポート期間中に賛同されたメッセージの数。 <br/>|
|ネットワーク名  <br/> |グループが属するネットワークの完全な名前。 |
|||