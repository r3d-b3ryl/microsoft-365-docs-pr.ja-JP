---
title: Microsoft 365 OneDrive for Business使用状況レポート
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: '組織全体OneDrive for Business使用するファイルとストレージの総数を確認するには、[使用状況レポート] の情報を取得します。 '
ms.openlocfilehash: d3b884f374cf3dde572bd67ad905fc308a1701d1
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400783"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365管理センターの [レポート] - OneDrive for Business使用状況

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
たとえば、ダッシュボードの OneDrive カードには、組織内で使用されているファイルの総数とストレージについて OneDrive for Business から得た値の概要が表示されます。これを詳細に調べて、アクティブな OneDrive アカウントの傾向や、ユーザーが操作しているファイル数と使用しているストレージの傾向を把握できます。このレポートには、各ユーザーの OneDrive ごとの詳細も表示されます。

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>使用状況レポートにアクセスOneDrive方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、カードの [その他の表示] OneDriveクリックします。
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive の利用状況レポートの解釈

[使用状況] タブを選択すると、OneDriveレポートで使用状況を **表示** できます。<br/>![Microsoft 365レポート - Microsoft OneDrive使用状況レポート。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![OneDriveレポート - 列を選択します。](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

過去 **7 OneDrive for Business**、30 日、90 日、または 180 日間の傾向について、使用状況レポートを表示できます。 ただし、レポートで特定の日を選択すると、現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|内容|
|:-----|:-----|
|**測定基準**|**定義**|
|URL  <br/> |ユーザーのアカウントの web OneDrive。 <br/> |
|削除済み  <br/> |ユーザーの削除状態OneDrive。 アカウントを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> |
|所有者  <br/> |管理者のプライマリ管理者のOneDrive。   <br/> |
|所有者プリンシパル名  <br/> |ユーザーの所有者の電子メール OneDrive。 <br/> |
|最終アクティビティ日 (UTC)  <br/> | ファイル アクティビティがレポート で実行された最新のOneDrive。 OneDrive にファイル アクティビティがなかった場合、値は空白になります。  <br/> |
|ファイル  <br/> |フォルダー内のファイルOneDrive。 <br/>|
|アクティブ ファイル  <br/> | 期間内のアクティブ ファイルの数。<br/> 注: レポートの指定した期間中にファイルが削除された場合、レポートに表示されるアクティブ なファイルの数は、OneDrive の現在のファイル数よりも多い場合があります。 >  削除されたユーザーはレポートに 180 日間表示され続けます。  <br/> |
|Storage使用 (MB)  <br/> |ユーザーが使用するストレージOneDrive MB 単位で指定します。 |
|||
   
> [!NOTE]
> このレポートには、有効なライセンスを持つユーザー OneDrive for Business含まれます。
