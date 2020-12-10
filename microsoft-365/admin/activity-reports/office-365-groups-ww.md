---
title: 管理センターの microsoft 365 レポート-Microsoft 365 グループ
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: グループとそのアクティビティについて知るために、Microsoft 365 groups レポートを取得します。
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611947"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>管理センターの microsoft 365 レポート-Microsoft 365 グループ

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft 365 groups レポートでは、組織内のグループのアクティビティについての洞察を得て、作成され、使用されているグループの数を確認できます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
  
## <a name="how-to-get-to-the-groups-report"></a>グループ レポートを作成する方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、[アクティブなユーザー-Microsoft 365 アプリ] または [アクティブなユーザー-Microsoft 365 Services カード] の [ **表示** ] ボタンをクリックして、Office 365 レポートページにアクセスします。
  
## <a name="interpret-the-groups-report"></a>グループ レポートを解釈する

Office 365 レポートで [ **グループアクティビティ** ] タブを選択すると、ライセンス認証を表示できます。<br/>![Microsoft 365 レポート-Microsoft Office 365 groups アクティビティ。](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Office 365 グループアクティビティレポート-列の選択](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|グループ名  <br/> |グループの名前を指定します。  <br/> |
|Deleted  <br/> |削除されたグループの数。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。  <br/> |
|グループの所有者  <br/> |グループの所有者の名前。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |グループによってメッセージが受信された最新の日付。 これはメールの会話、Yammer またはサイトでアクティビティが発生した最後の日付です。  <br/> |
|型  <br/> |グループの種類。 これにはプライベート グループとパブリック グループがあります。  <br/> |
|Exchange で受信した電子メール  <br/> |グループによって受信されたメッセージの数。|
|Exchange でのメール (合計)  <br/> |グループのメールボックス内のアイテムの合計数。  <br/> |
|Exchange で使用されるメールボックスの記憶域 (MB)  <br/> |グループのメールボックスによって使用される記憶域。 <br/>|
|SharePoint ファイル (合計)  <br/> |SharePoint グループサイトに格納されているファイルの数。  <br/> |
|SharePoint ファイル (アクティブ)  <br/> |レポート期間中に処理 (内部または外部共有) された SharePoint グループサイト内のファイルの数です。  <br/> |
|SharePoint で使用されているサイト記憶域の合計 (MB)  <br/> |レポート期間中に使用された記憶域の量 (MB 単位)。  <br/> |
|Yammer のメッセージ (投稿済み)  <br/> |レポート期間中に Yammer グループに投稿されたメッセージの数。  <br/> |
|Yammer のメッセージ (読み取り)  <br/> |レポート期間中に Yammer グループで読み取られた会話の数です。  <br/> |
|Yammer のメッセージ (好評)  <br/> |Yammer グループでレポート期間中に賛同されたメッセージの数。  <br/> |
|Members  <br/> |グループ内のメンバーの数。  <br/> |
|外部メンバー |グループ内の外部ユーザーの数。|
|||