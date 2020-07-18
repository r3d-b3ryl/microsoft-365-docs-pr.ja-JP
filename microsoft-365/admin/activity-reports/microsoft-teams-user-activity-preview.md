---
title: 管理センターの microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ-プレビュー
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
ms.openlocfilehash: 734a4dfd62160c2f4d29b8faffb3268a1962fe4f
ms.sourcegitcommit: a50260b7c5be7374e8e2bea19cc08406ef51ac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "45167343"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity--preview"></a>管理センターの microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ-プレビュー

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams ユーザーアクティビティレポートでは、組織内の Microsoft Teams アクティビティについての洞察を得ることができます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-to-get-to-the-preview-microsoft-teams-user-activity-report"></a>Microsoft Teams のプレビューユーザーアクティビティレポートを取得する方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。
2. **[レポートの選択**] ドロップダウンから、[ **Microsoft Teams**] を選択します。
  
## <a name="interpret-the-preview-microsoft-teams-user-activity-report"></a>Microsoft Teams のプレビューのユーザーアクティビティレポートを解釈する

[**ユーザーアクティビティ**] タブを選択すると、[Teams のプレビュー] レポートでユーザーアクティビティを表示できます。
  
|||
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
|その他のアクティビティ|ユーザーはアクティブと見なされますが、チャットメッセージ、1:1 通話、チャネルメッセージ、会議の合計、および開催された会議に対して0の値があります。 例アクションとしては、microsoft teams クライアントがフォアグラウンドでアクティブになったとき、アクションが作成メッセージ領域で実行されたとき、microsoft teams クライアントでのトーストの表示、バナーが microsoft teams クライアントに表示されたなどがあります。 |
|||