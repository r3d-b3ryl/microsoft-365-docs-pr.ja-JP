---
title: Microsoft 365管理センターのレポート - SharePoint使用状況
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: ユーザーが SharePoint SharePoint サイトに保存するファイルの数、アクティブに使用されるファイルの数、および使用されたストレージの合計を確認するには、SharePoint サイト使用状況レポートを取得します。
ms.openlocfilehash: d2c549dbb5ab456dddedf0422cd8aebafab1987d
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393333"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365管理センターのレポート - SharePoint使用状況

管理者としてMicrosoft 365レポート **ダッシュボードには**、組織内のさまざまな製品のアクティビティの概要が表示されます。 これにより、各製品に固有のアクティビティについてより詳しく知ることができます。 たとえば、ユーザーが SharePoint サイトに保存するファイルの合計数、アクティブに使用されているファイルの数、およびこれらすべてのサイトにわたって使用される記憶域の観点から、SharePoint から得られる価値の概要をとらえることができます。 その後、[SharePoint サイトの利用状況] レポートを詳細に確認して、すべてのサイトの傾向およびサイトごとのレベル詳細を把握できます。 
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。
Microsoft 365管理センターのレポートは、High テナントと DoD テナントGCCサポートされていません。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>[SharePoint サイトの利用状況] レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、カードの [その **他の表示**] SharePointクリックします。
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>サイト利用状況SharePointレポートを解釈する

[サイトの使用状況] タブを選択すると、SharePointレポートでサイトの使用状況 **を表示** できます。<br/>![Microsoft 365レポート - Microsoft SharePoint利用状況レポート。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![SharePoint利用状況レポート - 列を選択する](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|項目|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|サイトの URL  <br/> |サイトの完全な URL。 <br/> |
|Deleted  <br/> |サイトの削除状態。 サイトを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> |
|サイト所有者  <br/> |サイトのプライマリ所有者のユーザー名。   <br/> |
|サイト所有者プリンシパル名  <br/> |サイトの所有者の電子メール アドレス。 <br/> |
|最終アクティビティ日 (UTC)  <br/> | ファイルアクティビティが最後に検出された日付、またはサイトでページが表示された日付。  <br/> |
|サイトの感度ラベル ID  <br/> | サイトの感度ラベル。  <br/> |
|外部共有  <br/> | サイトの外部のsharable設定。  <br/> |
|管理されていないデバイス ポリシー  <br/> | 管理されていないデバイスのサイト アクセス ポリシー。  <br/> |
|地域の場所  <br/> | サイトの地理的な場所。  <br/> |
|ファイル  <br/> |サイト上のファイルの数。 <br/>|
|アクティブ ファイル  <br/> | サイト上のアクティブ なファイルの数。<br/> 注: レポートの指定された期間中にファイルが削除された場合、レポートに表示されるアクティブ なファイルの数は、サイト上の現在のファイル数よりも多い場合があります。  <br/> |
|Storage使用 (MB)  <br/> |サイトで現在使用されている記憶域の量。  <br/>|
|Storage済み (MB)  <br/> |サイトに割り当てられた記憶域の最大量。  <br/>|
|ページ ビュー  <br/> |サイトでページが表示された回数。  <br/>|
|アクセスしたページ  <br/> |サイトにアクセスした一意のページの数。  <br/>|
|匿名リンク数  <br/> |サイト上の [リンクを持つすべてのユーザー] を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|会社のリンク数  <br/> |サイト上の "リンクを持つ組織のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|ゲスト数のセキュリティで保護されたリンク  <br/> |サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|メンバー数のセキュリティで保護されたリンク  <br/> |サイト上の "特定のユーザー" を使用してドキュメントまたはフォルダーを共有する回数。  <br/>|
|ルート Web テンプレート  <br/> |サイトの作成に使用するテンプレート。  <br/> 注: 異なるサイトの種類でデータをフィルター処理する場合は、データをエクスポートし、[ルート Web テンプレート] 列を使用します。 |
|||