---
title: 管理センターの Microsoft 365 レポート-OneDrive for Business の使用状況
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
description: 'OneDrive for Business の使用状況レポートを取得して、組織全体で使用されているファイルと記憶域の合計数を確認します。 '
ms.openlocfilehash: 3855c7d06d202ee4d0590fcf5b8ca758d8120133
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649808"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>管理センターの Microsoft 365 レポート-OneDrive for Business の使用状況

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
たとえば、ダッシュボードの OneDrive カードには、組織内で使用されているファイルの総数とストレージについて OneDrive for Business から得た値の概要が表示されます。これを詳細に調べて、アクティブな OneDrive アカウントの傾向や、ユーザーが操作しているファイル数と使用しているストレージの傾向を把握できます。このレポートには、各ユーザーの OneDrive ごとの詳細も表示されます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>OneDrive アクティビティ レポートの作成方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、OneDrive カードの [ **詳細表示** ] ボタンをクリックします。
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive の利用状況レポートの解釈

[ **使用状況** ] タブを選択すると、OneDrive レポートでの使用状況を確認できます。<br/>![Microsoft 365 レポート-Microsoft OneDrive 使用状況レポート。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![OneDrive 使用状況レポート-列の選択](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|URL  <br/> |ユーザーの OneDrive の web アドレス。 <br/> |
|Deleted  <br/> |OneDrive の削除の状態。 アカウントを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> |
|Owner  <br/> |OneDrive のプライマリ管理者のユーザー名。   <br/> |
|所有者のプリンシパル名  <br/> |OneDrive の所有者の電子メールアドレス。 <br/> |
|最後のアクティビティの日付 (UTC)  <br/> | OneDrive でファイルアクティビティが最後に実行された日付。 OneDrive にファイル アクティビティがなかった場合、値は空白になります。  <br/> |
|ファイル  <br/> |OneDrive 内のファイルの数。 <br/>|
|作業中のファイル  <br/> | 期間内のアクティブなファイルの数。<br/> 注: レポートに指定された期間中にファイルが削除された場合、レポートに表示されるアクティブなファイルの数が、OneDrive 内の現在のファイル数を超えることがあります。 >  削除されたユーザーはレポートに 180 日間表示され続けます。  <br/> |
|使用済み記憶域 (MB)  <br/> |OneDrive で使用される記憶域の量 (MB 単位)。 |
|||