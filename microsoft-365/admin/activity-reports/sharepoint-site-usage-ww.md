---
title: 管理センターでの Microsoft 365 レポート - SharePoint サイトの使用状況
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
description: SharePoint サイト利用状況レポートを取得して、ユーザーが SharePoint サイトに保存するファイルの数、アクティブに使用されているファイルの数、消費された記憶域の合計を確認します。
ms.openlocfilehash: 403ebfd75fca5ba5777832140155bb09734db3c7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233510"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>管理センターでの Microsoft 365 レポート - SharePoint サイトの使用状況

Microsoft 365 管理者の **レポート** ダッシュボードには、組織内のさまざまな製品のアクティビティの概要が表示されます。 これにより、各製品に固有のアクティビティについてより詳しく知ることができます。 たとえば、ユーザーが SharePoint サイトに保存するファイルの合計数、アクティブに使用されているファイルの数、およびこれらすべてのサイトにわたって使用される記憶域の観点から、SharePoint から得られる価値の概要をとらえることができます。 その後、[SharePoint サイトの利用状況] レポートを詳細に確認して、すべてのサイトの傾向およびサイトごとのレベル詳細を把握できます。 
  
> [!NOTE]
> レポートを表示するには、グローバル管理者、Microsoft 365 のグローバル閲覧者またはレポート閲覧者、または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者である必要があります。
管理センターの Microsoft 365 レポートは、GCC High テナントと DoD テナントではサポートされていません。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>[SharePoint サイトの利用状況] レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボード ホームページで、SharePoint **カードの** [その他の表示] ボタンをクリックします。
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>SharePoint サイトの利用状況レポートを解釈する

[サイトの利用状況] タブを選択すると、SharePoint レポートでサイトの **利用状況を表示** できます。<br/>![Microsoft 365 レポート - Microsoft SharePoint サイト利用状況レポート。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

[列 **の選択] を** 選択して、レポートに列を追加または削除します。  <br/> ![SharePoint サイト利用状況レポート - 列の選択](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|サイトの URL  <br/> |サイトの完全な URL。 <br/> |
|Deleted  <br/> |サイトの削除状態。 サイトを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> |
|サイト所有者  <br/> |サイトのプライマリ所有者のユーザー名。   <br/> |
|サイト所有者のプリンシパル名  <br/> |サイトの所有者の電子メール アドレス。 <br/> |
|最後のアクティビティの日付 (UTC)  <br/> | ファイル アクティビティが最後に検出された日付、またはサイトでページが表示された日付。  <br/> |
|サイトの感度ラベル ID  <br/> | サイトの感度ラベル。  <br/> |
|外部共有  <br/> | サイト上の外部のファイルの移動可能な設定。  <br/> |
|非管理対象デバイス ポリシー  <br/> | 非管理対象デバイスのサイト アクセス ポリシー。  <br/> |
|地域の場所  <br/> | サイトの地理的位置。  <br/> |
|ファイル  <br/> |サイト上のファイルの数。 <br/>|
|アクティブなファイル  <br/> | サイト上のアクティブなファイルの数。<br/> 注: レポートの指定した期間中にファイルが削除された場合、レポートに表示されるアクティブなファイルの数は、サイト上の現在のファイル数よりも多い場合があります。  <br/> |
|使用ストレージ (MB)  <br/> |サイトで現在使用されている記憶域の容量。  <br/>|
|割り当てられた記憶域 (MB)  <br/> |サイトに割り当てられる記憶域の最大容量。  <br/>|
|ページ ビュー  <br/> |サイトでページが表示された回数。  <br/>|
|アクセスされたページ  <br/> |サイトでアクセスされた一意のページの数。  <br/>|
|匿名リンク数  <br/> |サイトで [リンクを持つすべてのユーザー] を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|会社のリンク数  <br/> |サイトで "リンクを含む組織のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|ゲスト数のセキュリティで保護されたリンク  <br/> |サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|メンバー数のセキュリティで保護されたリンク  <br/> |サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|ルート Web テンプレート  <br/> |サイトの作成に使用するテンプレート。  <br/> 注: 異なるサイトの種類でデータをフィルター処理する場合は、データをエクスポートし、[ルート Web テンプレート] 列を使用します。 |
|||