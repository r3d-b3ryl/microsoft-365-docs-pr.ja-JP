---
title: 管理センターの Microsoft 365 レポート-SharePoint サイトの使用状況
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
description: Sharepoint サイトの利用状況レポートを取得して、ユーザーが SharePoint サイトに格納しているファイルの数、アクティブに使用されている数、および使用されている記憶域の合計量を把握します。
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649828"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>管理センターの Microsoft 365 レポート-SharePoint サイトの使用状況

Microsoft 365 admin としての **レポート** ダッシュボードには、組織内のさまざまな製品におけるアクティビティの概要が表示されます。 これにより、各製品に固有のアクティビティについてより詳しく知ることができます。 たとえば、ユーザーが SharePoint サイトに保存するファイルの合計数、アクティブに使用されているファイルの数、およびこれらすべてのサイトにわたって使用される記憶域の観点から、SharePoint から得られる価値の概要をとらえることができます。 その後、[SharePoint サイトの利用状況] レポートを詳細に確認して、すべてのサイトの傾向およびサイトごとのレベル詳細を把握できます。 
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。
管理センターの Microsoft 365 レポートは、GCC High および DoD テナントではサポートされていません。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>[SharePoint サイトの利用状況] レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、SharePoint カードの [ **詳細を表示** ] ボタンをクリックします。
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>SharePoint サイトの利用状況レポートを解釈する

SharePoint レポートでサイトの利用状況を表示するには、[ **サイトの利用状況** ] タブを選択します。<br/>![Microsoft 365 レポート-Microsoft SharePoint サイトの利用状況レポート。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![SharePoint サイトの利用状況レポート-列の選択](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|サイトの URL  <br/> |サイトの完全な URL。 <br/> |
|Deleted  <br/> |サイトの削除状態。 サイトを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> |
|サイト所有者  <br/> |サイトのプライマリ所有者のユーザー名。   <br/> |
|サイト所有者のプリンシパル名  <br/> |サイトの所有者の電子メールアドレス。 <br/> |
|最後のアクティビティの日付 (UTC)  <br/> | ファイルアクティビティが最後に検出された日付、またはサイトでページが表示された日付。  <br/> |
|ファイル  <br/> |サイト上のファイルの数。 <br/>|
|作業中のファイル  <br/> | サイト上のアクティブなファイルの数。<br/> 注: レポートに指定された期間中にファイルが削除された場合、レポートに表示されるアクティブなファイルの数が、サイト上の現在のファイル数を超えることがあります。  <br/> |
|使用済み記憶域 (MB)  <br/> |サイトで現在使用されている記憶域の容量。  <br/>|
|割り当て済み記憶域 (MB)  <br/> |サイトに割り当てられている記憶域の最大容量。  <br/>|
|ページビュー  <br/> |サイトでページが表示された回数。  <br/>|
|アクセスしたページ  <br/> |サイト上でアクセスされた一意のページの数。  <br/>|
|ルート Web テンプレート  <br/> |サイトの作成に使用するテンプレート。  <br/> 注: 異なるサイトの種類でデータをフィルター処理する場合は、データをエクスポートし、[ルート Web テンプレート] 列を使用します。 |
|||