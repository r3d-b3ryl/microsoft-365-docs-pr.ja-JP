---
title: 管理センターの microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Microsoft Teams ユーザーアクティビティレポートを取得して、組織内の Teams アクティビティを把握する方法について説明します。
ms.openlocfilehash: b85f073a2916b646a5a03e62913de44b410ca058
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988472"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>管理センターの microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams ユーザーアクティビティレポートでは、組織内の Microsoft Teams アクティビティについての洞察を得ることができます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Microsoft Teams ユーザー アクティビティ レポートを取得する手順

1. 管理センターで、[ **レポート** ] \> [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。
2. ダッシュボードのホームページから、Microsoft Teams のアクティビティカードの [ **詳細表示** ] ボタンをクリックします。

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft Teams ユーザー アクティビティ レポートを解釈する

[ **ユーザーアクティビティ** ] タブを選択すると、Teams レポートでユーザーアクティビティを表示できます。 <br/>![Microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ。](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

また、[ **エクスポート** ] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 **音声時間** 、 **ビデオ時間** 、 **スクリーン共有時間** のエクスポート形式は、[形式の形式に従っています。

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。   <br/> |
|チャネルメッセージ   <br/> |指定された期間中にユーザーがチームチャットで投稿した一意のメッセージの数。  <br/> |
|チャットメッセージ   <br/> |指定された期間中にユーザーがプライベートチャットで投稿した一意のメッセージの数。  <br/> |
|会議の合計数   <br/> |指定された期間中にユーザーが参加したオンライン会議の数。  <br/> |
|1:1 通話   <br/> | 指定された期間中にユーザーが参加した1:1 通話の数。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |ユーザーが Microsoft Teams アクティビティに参加した最後の日付。<br/> |
|アドホックミーティング参加   <br/> | 指定された期間中にユーザーが参加した予定表でスケジュールされていない会議の数。  <br/> |
|開催された会議 (アドホック) <br/> |指定された期間中にユーザーが開催した予定表でスケジュールされていない会議の数。 <br/>|
|開催予定の会議  <br/> |指定された期間中にユーザーが開催した予約済みミーティングの数。  <br/> |
|ライセンスされている |ユーザーが Teams を使用するライセンスを持っている場合に選択されます。|
|その他のアクティビティ|ユーザーはアクティブですが、レポートで提供されている公開されたアクションの種類 (チャネルメッセージおよびチャットメッセージへの送信または返信、1:1 通話と会議の開催または参加) に対して、他のアクティビティを実行しています。 アクションの例としては、ユーザーが Teams の状態または Teams の状態メッセージを変更した場合や、チャネルメッセージの投稿を開いた場合に、返信を行わない場合があります。 |
|||