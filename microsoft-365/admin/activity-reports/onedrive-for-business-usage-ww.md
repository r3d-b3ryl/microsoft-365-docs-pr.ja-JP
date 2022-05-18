---
title: 使用状況レポートをMicrosoft 365 OneDrive for Businessする
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
description: OneDrive for Business使用状況レポートを入手して、組織全体で使用されるファイルとストレージの合計数の詳細を確認します。
ms.openlocfilehash: d195a521fba9dc82867821e27414d125dca09c61
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65467276"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>管理センターでレポートをMicrosoft 365する - 使用状況OneDrive for Business

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
たとえば、ダッシュボードの OneDrive カードには、組織内で使用されているファイルの総数とストレージについて OneDrive for Business から得た値の概要が表示されます。これを詳細に調べて、アクティブな OneDrive アカウントの傾向や、ユーザーが操作しているファイル数と使用しているストレージの傾向を把握できます。このレポートには、各ユーザーの OneDrive ごとの詳細も表示されます。

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>OneDrive使用状況レポートにアクセス操作方法。

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、OneDrive カードの **[その他の表示**] ボタンをクリックします。
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive の利用状況レポートの解釈

[使用状況] タブを選択すると、OneDrive レポートで **使用状況** を表示できます。<br/>![Microsoft 365 レポート - 使用状況レポートMicrosoft OneDrive。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![使用状況レポートOneDrive - 列を選択します。](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

**OneDrive for Business使用状況** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|URL  <br/> |ユーザーのOneDriveの Web アドレス。 <br/> |
|Deleted  <br/> |OneDriveの削除状態。 アカウントを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> |
|Owner  <br/> |OneDriveのプライマリ管理者のユーザー名。   <br/> |
|所有者プリンシパル名  <br/> |OneDriveの所有者の電子メール アドレス。 <br/> |
|最終アクティビティ日 (UTC)  <br/> | OneDriveでファイル アクティビティが実行された最新の日付。 OneDrive にファイル アクティビティがなかった場合、値は空白になります。  <br/> |
|Files  <br/> |OneDrive内のファイルの数。 <br/>|
|アクティブなファイル  <br/> | 期間内のアクティブなファイルの数。<br/> 注: レポートの指定された期間中にファイルが削除された場合、レポートに表示されるアクティブ なファイルの数が、OneDriveの現在のファイル数よりも大きくなる可能性があります。 >  削除されたユーザーはレポートに 180 日間表示され続けます。  <br/> |
|Storage使用 (MB)  <br/> |OneDriveが使用するストレージの量 (MB 単位)。 |
|||
   
> [!NOTE]
> レポートには、有効なOneDrive for Business ライセンスを持つユーザーのみが含まれます。
