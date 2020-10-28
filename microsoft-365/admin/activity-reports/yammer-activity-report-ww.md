---
title: 管理センターでの Microsoft 365 レポート-Yammer アクティビティレポート
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
description: Yammer アクティビティレポートを取得して、Yammer を使用してメッセージを投稿したり、メッセージを読んだりするユーザーの数について理解します。
ms.openlocfilehash: fc6bf252892cc9b3f30cdcf464cd44cfc83c4f75
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779377"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>管理センターでの Microsoft 365 レポート-Yammer アクティビティレポート

Microsoft 365 admin として、 **レポート** ダッシュボードには、組織内の製品の使用状況に関するデータが表示されます。 [管理センターのアクティビティレポートを](activity-reports.md)チェックアウトします。 **Yammer アクティビティ レポート** では、Yammer を使用してメッセージの投稿、「いいね!」の評価、または閲覧を行った一意のユーザー数や、組織全体で生成されたアクティビティの量を確認することで、Yammer に対する組織の関与レベルを把握することができます。 
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Yammer アクティビティレポートを取得するにはどうすればよいですか?

1. 管理センターで、[ **レポート** ] \> [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、Yammer カードの [ **詳細表示** ] ボタンをクリックします。

  
## <a name="interpret-the-yammer-activity-report"></a>Yammer のアクティビティ レポートの内容を理解する

[ **アクティビティ** ] タブを選択すると、Yammer レポートでアクティビティを表示できます。<br/>![Microsoft 365 レポート-Microsoft Yammer アクティビティレポート。](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Yammer アクティビティレポート-列の選択](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

また、[ **エクスポート** ] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。 このグリッドには、Microsoft 365 アカウントを使用して Yammer にログインしたユーザー、またはシングルサインオンを使用してネットワークにログインしたユーザーが表示されます。 <br/> |
|表示名  <br/> |ユーザーの完全な名前。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> |
|ユーザーの状態  <br/> |アクティブ、削除済み、または中断の3つの値のいずれか。 これらのレポートには、アクティブ、中断、および削除されたユーザーのデータが表示されます。 保留中のユーザーは、メッセージの投稿、開封、またはそのような操作ができないため、保留中のユーザーは反映されません。  <br/> |
|状態変更日付 (UTC)  <br/> |Yammer でユーザーの都道府県が変更された日付。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> | ユーザーがメッセージを投稿、閲覧、または好評とした最後の日付。  <br/> |
|投稿  <br/> |指定した期間中にユーザーが投稿したメッセージの数。 <br/>|
|読み取り  <br/> |指定した期間中にユーザーが読んだ会話の数。  <br/> |
|いいね!  <br/> |指定した期間中にユーザーが賛同したメッセージの数。  <br/>|
|割り当てられた製品  <br/> |このユーザーに割り当てられている製品。|
|||