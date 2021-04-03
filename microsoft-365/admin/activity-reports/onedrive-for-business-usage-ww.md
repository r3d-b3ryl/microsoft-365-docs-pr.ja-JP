---
title: 管理センターの Microsoft 365 レポート - OneDrive for Business の使用状況
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 'OneDrive for Business Usage Report を取得して、組織全体で使用されるファイルとストレージの総数を確認します。 '
ms.openlocfilehash: 54a3b1e041ee6155b5ce89d6cd5bc73233d1f69b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579544"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>管理センターの Microsoft 365 レポート - OneDrive for Business の使用状況

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
たとえば、ダッシュボードの OneDrive カードには、組織内で使用されているファイルの総数とストレージについて OneDrive for Business から得た値の概要が表示されます。これを詳細に調べて、アクティブな OneDrive アカウントの傾向や、ユーザーが操作しているファイル数と使用しているストレージの傾向を把握できます。このレポートには、各ユーザーの OneDrive ごとの詳細も表示されます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>OneDrive アクティビティ レポートの作成方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、OneDrive カードの **[** その他の表示] ボタンをクリックします。
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive の利用状況レポートの解釈

OneDrive レポートで使用状況を表示するには、[使用状況] タブを **選択** します。<br/>![Microsoft 365 レポート - Microsoft OneDrive 使用状況レポート。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![OneDrive 使用状況レポート - 列の選択](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|URL  <br/> |ユーザーの OneDrive の Web アドレス。 <br/> |
|Deleted  <br/> |OneDrive の削除状態。 アカウントを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> |
|Owner  <br/> |OneDrive のプライマリ管理者のユーザー名。   <br/> |
|所有者プリンシパル名  <br/> |OneDrive の所有者の電子メール アドレス。 <br/> |
|最終アクティビティ日 (UTC)  <br/> | OneDrive でファイル アクティビティが実行された最新の日付。 OneDrive にファイル アクティビティがなかった場合、値は空白になります。  <br/> |
|ファイル  <br/> |OneDrive 内のファイルの数。 <br/>|
|アクティブ ファイル  <br/> | 期間内のアクティブ ファイルの数。<br/> 注: レポートの指定した期間中にファイルが削除された場合、レポートに表示されるアクティブ なファイルの数は、OneDrive の現在のファイル数よりも多い場合があります。 >  削除されたユーザーはレポートに 180 日間表示され続けます。  <br/> |
|使用される記憶域 (MB)  <br/> |OneDrive が MB で使用する記憶域の量。 |
|||