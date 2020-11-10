---
title: 管理センターフォームアクティビティの Microsoft 365 レポート
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
description: Microsoft 365 管理センターの Microsoft 365 レポートダッシュボードを使用して Microsoft Forms アクティビティレポートを取得する方法について説明します。
ms.openlocfilehash: 17d56e3974b877e15b81af5d4e195985c4985155
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988963"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>管理センターフォームアクティビティの Microsoft 365 レポート

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、フォームを使用して Microsoft Forms を使用するためにライセンスを供与されたすべてのユーザーのアクティビティを把握することができます。 また、作成されたフォームの数とユーザーが応答したフォームの数を確認することによって、コラボレーションのレベルを理解することもできます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-to-get-to-the-forms-activity-report"></a>フォームアクティビティレポートを取得する方法

1. 管理センターで、[ **レポート** ] \> [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、フォームカードの [ **詳細表示** ] ボタンをクリックします。
  
## <a name="interpret-the-forms-activity-report"></a>フォームアクティビティレポートを解釈する

[ **アクティビティ** ] タブを選択すると、フォームレポートでアクティビティを表示できます。<br/>![Microsoft 365 レポート-Microsoft Forms アクティビティレポート。](../../media/275fb0a1-b9d9-4233-8aaf-e7df73cc705f.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![フォームアクティビティレポート-列の選択](../../media/0c9b0b69-5dc7-43ea-8e2c-54407b6ce2ab.png)

また、[ **エクスポート** ] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |Microsoft Forms でアクティビティを実行したユーザーの電子メールアドレス。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |ユーザーが選択した日付範囲に対してフォームの動作が実行された最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/><br/>これにより、特定の日にアクティビティを実行したユーザーのファイルアクティビティデータのみを表示するようにテーブルがフィルター処理されます。  <br/> |
|作成されたフォームの数  <br/> |ユーザーが作成したフォームの数。   <br/> |
|応答したフォームの数  <br/> |ユーザーが返信を送信したフォームの数。|
|||
