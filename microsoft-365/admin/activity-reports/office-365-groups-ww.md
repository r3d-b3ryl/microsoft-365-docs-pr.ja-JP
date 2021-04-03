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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Microsoft 365 のグループ レポートで、グループとそのアクティビティについて確認します。
ms.openlocfilehash: fd3aa664b5a40bb5fffe0ed23e07ba6f1a5907c2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579568"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>管理センターでの Microsoft 365 レポート - Microsoft 365 グループ

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft 365 グループレポートでは、組織内のグループのアクティビティに関する詳細を分析したり、作成中および使用中のグループの数を確認したりすることができます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。  
  
## <a name="how-to-get-to-the-groups-report"></a>グループ レポートを作成する方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、[アクティブ ユーザー  - Microsoft 365 Apps] または [アクティブ ユーザー - Microsoft 365 Services] カードの [その他の表示] ボタンをクリックして、[Office 365 レポート] ページに移動します。
  
## <a name="interpret-the-groups-report"></a>グループ レポートを解釈する

[グループ] アクティビティ タブを選択すると、Office 365 レポートでライセンス認証 **を表示** できます。<br/>![Microsoft 365 レポート - Microsoft Office 365 グループアクティビティを表示します。](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![Office 365 グループアクティビティ レポート - 列の選択](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  <br/> |グループの名前を指定します。  <br/> |
|Deleted  <br/> |削除されたグループの数。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  <br/> |
|グループ所有者  <br/> |グループ所有者の名前。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |グループがメッセージを受信した最新の日付。 これはメールの会話、Yammer またはサイトでアクティビティが発生した最後の日付です。  <br/> |
|型  <br/> |グループの種類。 これにはプライベート グループとパブリック グループがあります。  <br/> |
|Exchange で受信したメール  <br/> |グループによって受信されたメッセージの数。|
|Exchange のメール (合計)  <br/> |グループのメールボックス内のアイテムの総数。  <br/> |
|Exchange (MB) で使用されるメールボックス ストレージ  <br/> |グループのメールボックスで使用される記憶域。 <br/>|
|SharePoint ファイル (合計)  <br/> |SharePoint グループ サイトに格納されているファイルの数。  <br/> |
|SharePoint ファイル (アクティブ)  <br/> |レポート期間中に (表示または変更、同期、内部または外部共有) に作用した SharePoint グループ サイト内のファイルの数。  <br/> |
|SharePoint に使用されるサイト ストレージの合計 (MB)  <br/> |レポート期間中に使用される MB 単位の記憶域の量。  <br/> |
|[メッセージ] Yammer (投稿)  <br/> |レポート期間中にグループにYammerメッセージの数。  <br/> |
|[メッセージ] Yammer (読み取り)  <br/> |レポート期間中にグループで読み取Yammer会話の数。  <br/> |
|[メッセージ] Yammer (お気に入り)  <br/> |レポート期間中に、Yammerグループで気に入ったメッセージの数。  <br/> |
|メンバー  <br/> |グループ内のメンバーの数。  <br/> |
|外部メンバー |グループ内の外部ユーザーの数。|
|||