---
title: 管理センターでの Microsoft 365 レポート - Microsoft 365 グループ
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Microsoft 365 のグループ レポートで、グループとそのアクティビティについて確認します。
ms.openlocfilehash: ed598633205aab83920abef79e766ef16e248f43
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394137"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>管理センターでの Microsoft 365 レポート - Microsoft 365 グループ

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft 365 グループレポートでは、組織内のグループのアクティビティに関する詳細を分析したり、作成中および使用中のグループの数を確認したりすることができます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。  
  
## <a name="how-to-get-to-the-groups-report"></a>グループ レポートを作成する方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、[アクティブ なユーザー] ( Microsoft 365 Apps または [アクティブ ユーザー - Microsoft 365 サービス] カードの [その他の表示] ボタンをクリックして、[Office 365 レポート] ページに移動します。
  
## <a name="interpret-the-groups-report"></a>グループ レポートを解釈する

[グループ] アクティビティ タブを選択すると、Office 365レポートでライセンス認証 **を表示** できます。<br/>![Microsoft 365レポート - Microsoft Office 365グループアクティビティ。](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![Office 365アクティビティ レポート - 列の選択](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

|項目|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  <br/> |グループの名前を指定します。  <br/> |
|Deleted  <br/> |削除されたグループの数。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  <br/> |
|グループ所有者  <br/> |グループ所有者の名前。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |グループがメッセージを受信した最新の日付。 これはメールの会話、Yammer またはサイトでアクティビティが発生した最後の日付です。  <br/> |
|型  <br/> |グループの種類。 これにはプライベート グループとパブリック グループがあります。  <br/> |
|受信したメールは、Exchange  <br/> |グループによって受信されたメッセージの数。|
|[メール] Exchange (合計)  <br/> |グループのメールボックス内のアイテムの総数。  <br/> |
|メールボックス ストレージは、Exchange (MB) に使用されます。  <br/> |グループのメールボックスで使用される記憶域。 <br/>|
|SharePointファイル (合計)  <br/> |グループ サイトに保存SharePoint数。  <br/> |
|SharePointファイル (アクティブ)  <br/> |レポート期間中に実行された SharePoint グループ サイト内のファイルの数 (表示または変更、同期、内部または外部共有)。  <br/> |
|ユーザーに使用されるサイト ストレージSharePoint (MB)  <br/> |レポート期間中に使用される MB 単位の記憶域の量。  <br/> |
|[メッセージ] Yammer (投稿)  <br/> |レポート期間中に、Yammerグループに投稿されたメッセージの数。  <br/> |
|[メッセージ] Yammer (読み取り)  <br/> |レポート期間中にグループで読み取Yammer会話の数。  <br/> |
|[メッセージ] Yammer (お気に入り)  <br/> |レポート期間中に、Yammerグループで気に入ったメッセージの数。  <br/> |
|メンバー  <br/> |グループ内のメンバーの数。  <br/> |
|外部メンバー |グループ内の外部ユーザーの数。|
|||

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365管理センターのレポート](activity-reports.md)(記事)\
[セキュリティ コンプライアンス センター&レポート](../../compliance/reports-in-security-and-compliance.md) (記事)\
[Microsoft 365管理センターの [レポート] - アクティブ ユーザー](../../admin/activity-reports/active-users-ww.md) (記事)

