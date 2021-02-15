---
title: 管理センターでの Microsoft 365 レポート - Microsoft Teams ユーザー アクティビティ
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
description: Microsoft Teams ユーザー アクティビティ レポートを取得し、組織内の Teams アクティビティに関する洞察を得る方法について説明します。
ms.openlocfilehash: e8e4ab6fd78fb290243d8fdc780b5a7a14ca2ee0
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233412"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>管理センターでの Microsoft 365 レポート - Microsoft Teams ユーザー アクティビティ

Microsoft 365 **レポート** ダッシュボードには、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams のユーザー アクティビティ レポートでは、組織内の Microsoft Teams アクティビティに関する分析情報を取得できます。
  
> [!NOTE]
> レポートを表示するには、グローバル管理者、Microsoft 365 のグローバル閲覧者またはレポート閲覧者、または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者である必要があります。  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Microsoft Teams ユーザー アクティビティ レポートを取得する手順

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。
2. ダッシュボード ホームページで、Microsoft Teams アクティビティ **カードの** [その他の表示] ボタンをクリックします。

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft Teams ユーザー アクティビティ レポートを解釈する

Teams レポートでユーザー アクティビティを表示するには、[ユーザー アクティビティ] タブ **を選択** します。 <br/>![Microsoft 365 レポート - Microsoft Teams ユーザー アクティビティ。](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

[列 **の選択] を** 選択して、レポートに列を追加または削除します。  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 オーディオ時間、ビデオ時間 **、画面共有** 時間のエクスポート形式は、ISO8601 継続時間形式に従います。 

[ **Microsoft Teams ユーザー アクティビティ**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、表 (7) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。

データの品質を確保するために、過去 3 日間の毎日のデータ検証チェックを実行し、検出されたギャップを埋めます。 プロセス中に履歴データに違いがある場合があります。

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。   <br/> |
|チャネル メッセージ   <br/> |指定した期間中にユーザーがチーム チャットに投稿した一意のメッセージの数。  <br/> |
|チャット メッセージ   <br/> |指定した期間中にユーザーがプライベート チャットに投稿した一意のメッセージの数。  <br/> |
|会議の総数   <br/> |指定した期間中にユーザーが参加したオンライン会議の数。  <br/> |
|1 対 1 通話   <br/> | 指定された期間中にユーザーが参加した 1 対 1 の通話の数。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |ユーザーが Microsoft Teams アクティビティに参加した最後の日付。<br/> |
|会議に参加した adhoc   <br/> | 指定した期間中にユーザーが参加した予定表でスケジュールされていない会議の数。  <br/> |
|会議開催の adhoc <br/> |指定した期間中にユーザーが開催した予定表でスケジュールされていない会議の数。 <br/>|
|スケジュールされた会議  <br/> |指定した期間中にユーザーが開催したスケジュールされた会議の数。  <br/> |
|ライセンスされている |ユーザーに Teams を使用するライセンスが割り当てらた場合に選択します。|
|その他のアクティビティ|ユーザーはアクティブですが、レポートで提供される公開されているアクションの種類 (チャネル メッセージとチャット メッセージの送信または返信、1 対 1 の通話と会議への参加のスケジュールまたは参加) 以外のアクティビティを実行しています。 アクションの例としては、ユーザーが Teams の状態や Teams のステータス メッセージを変更したり、チャネル メッセージの投稿を開いたが返信しない場合があります。 |
|||