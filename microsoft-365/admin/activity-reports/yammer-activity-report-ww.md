---
title: Microsoft 365 管理センター Yammer アクティビティ レポート
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
description: Yammer アクティビティ レポートを取得し、Yammerを使用してメッセージの投稿や読み取りを行うユーザーの数の詳細を確認します。
ms.openlocfilehash: 3ab1f13ec9b7b86bb1a7d858b849f22e687ae8aa
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781295"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>管理センターでレポートをMicrosoft 365する - Yammer アクティビティ レポート

管理者Microsoft 365、レポート ダッシュボードには、組織内の製品の使用状況に関するデータが表示されます。 [管理センターでアクティビティ レポートを確認します](activity-reports.md)。 **Yammer アクティビティ レポート** では、Yammer を使用してメッセージの投稿、「いいね!」の評価、または閲覧を行った一意のユーザー数や、組織全体で生成されたアクティビティの量を確認することで、Yammer に対する組織の関与レベルを把握することができます。 
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Yammer アクティビティ レポートにアクセス操作方法?

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Yammer カードの **[その他の表示**] ボタンをクリックします。

  
## <a name="interpret-the-yammer-activity-report"></a>Yammer のアクティビティ レポートの内容を理解する

[アクティビティ] タブを選択すると、Yammer レポートで **アクティビティ** を表示できます。<br/>![Microsoft 365 レポート - Microsoft Yammer アクティビティ レポート。](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![アクティビティ レポートYammer - 列を選択します。](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

**Yammerアクティビティ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。 このグリッドには、Microsoft 365 アカウントを使用してYammerにログインしたユーザー、またはシングル サインオンを使用してネットワークにログインしたユーザーが表示されます。 <br/> |
|表示名  <br/> |ユーザーの完全な名前。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> |
|ユーザーの状態  <br/> |アクティブ化、削除、または中断の 3 つの値のいずれか。 これらのレポートには、アクティブ、中断、および削除されたユーザーのデータが表示されます。 保留中のユーザーはメッセージを投稿、読み取り、または好きにできないため、保留中のユーザーは反映されません。  <br/> |
|状態変更日 (UTC)  <br/> |Yammerでユーザーの状態が変更された日付。  <br/> |
|最終アクティビティ日 (UTC)  <br/> | ユーザーがメッセージを投稿、読み取り、または気に入った最後の日付。  <br/> |
|投稿  <br/> |指定した期間中にユーザーが投稿したメッセージの数。 <br/>|
|読み取り  <br/> |指定した期間中にユーザーが読み取った会話の数。  <br/> |
|いいね!  <br/> |指定した期間中にユーザーが気に入ったメッセージの数。  <br/>|
|割り当てられた製品  <br/> |このユーザーに割り当てられている製品。|
|||