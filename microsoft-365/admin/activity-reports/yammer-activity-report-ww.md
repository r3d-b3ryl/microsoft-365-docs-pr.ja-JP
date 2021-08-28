---
title: Microsoft 365管理センターのレポート - Yammerレポート
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
description: '[アクティビティ] Yammerレポートを取得し、メッセージの投稿、Yammer読み取りを行うユーザー数の詳細を知ります。'
ms.openlocfilehash: d938052da82c1f1a0c038813dd7a0d02bbb510e4
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58564782"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Microsoft 365管理センターのレポート - Yammerレポート

管理者Microsoft 365レポート **ダッシュボードには**、組織内の製品の使用状況に関するデータが表示されます。 管理センター [でアクティビティ レポートを確認します](activity-reports.md)。 **Yammer アクティビティ レポート** では、Yammer を使用してメッセージの投稿、「いいね!」の評価、または閲覧を行った一意のユーザー数や、組織全体で生成されたアクティビティの量を確認することで、Yammer に対する組織の関与レベルを把握することができます。 
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>アクティビティ レポートにアクセスYammer方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、カードの **[その他** の表示] Yammerクリックします。

  
## <a name="interpret-the-yammer-activity-report"></a>Yammer のアクティビティ レポートの内容を理解する

[アクティビティ] タブを選択すると、Yammerレポートでアクティビティ **を表示** できます。<br/>![Microsoft 365レポート - Microsoft Yammerアクティビティ レポート。](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![Yammerアクティビティ レポート - 列を選択します。](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。 このグリッドには、YammerアカウントMicrosoft 365シングル サインオンを使用してネットワークにログインしたユーザーが表示されます。 <br/> |
|表示名  <br/> |ユーザーの完全な名前。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> |
|ユーザーの状態  <br/> |アクティブ化、削除、または中断の 3 つの値のいずれかを指定します。 これらのレポートには、アクティブ、中断、削除されたユーザーのデータが表示されます。 保留中のユーザーはメッセージを投稿、読み取り、または同様に行えないので、保留中のユーザーは反映されません。  <br/> |
|状態の変更日 (UTC)  <br/> |ユーザーの状態が変更された日付は、Yammer。  <br/> |
|最終アクティビティ日 (UTC)  <br/> | ユーザーがメッセージを投稿、読み取り、または気に入った最後の日付。  <br/> |
|投稿  <br/> |指定した期間中にユーザーが投稿したメッセージの数。 <br/>|
|読み取り  <br/> |指定した期間中にユーザーが読み取った会話の数。  <br/> |
|いいね!  <br/> |指定した期間中にユーザーが気に入ったメッセージの数。  <br/>|
|割り当てられた製品  <br/> |このユーザーに割り当てられている製品。|
|||