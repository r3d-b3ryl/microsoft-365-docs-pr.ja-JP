---
title: Microsoft 365管理センターのレポート - Dynamics 365 Customer Voice アクティビティ
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Microsoft Dynamics 365 Customer Voice アクティビティ レポートを取得する方法については、Microsoft 365 の [レポート] ダッシュボードを使用Microsoft 365 管理センター。
ms.openlocfilehash: 6c66b4fcee0d2f04e3178ede8360b87ad1abe597
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59177272"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365管理センターのレポート - Dynamics 365 Customer Voice アクティビティ

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、Dynamics 365 Customer Voice との対話を見て、Microsoft Dynamics 365 Customer Voice を使用するライセンスを持つすべてのユーザーのアクティビティを理解できます。 また、作成された Pro サーベイの数と、ユーザーが回答した Pro アンケートの数を確認することで、共同作業のレベルを理解するのにも役立ちます。 
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Dynamics  365 Customer Voice カードの [その他の表示] ボタンをクリックします。
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice アクティビティ レポートの解釈

[アクティビティ] タブを選択すると、Dynamics 365 Customer Voice レポートでアクティビティを **表示** できます。<br/>![Microsoft 365レポート - Microsoft Dynamics 365 Customer Voice アクティビティ レポート。](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![Dynamics 365 Customer Voice アクティビティ レポート - 列を選択します。](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |Microsoft Forms でアクティビティを実行したユーザーの電子メール アドレス。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |選択した日付範囲に対してユーザーがフォーム アクティビティを実行した最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/>これにより、テーブルをフィルター処理して、その特定の日にアクティビティを実行したユーザーのファイル アクティビティ データのみを表示します。  <br/> |
|作成されたアンケートの数  <br/> |ユーザーが作成したアンケートの数。   <br/> |
|アンケート回答数  <br/> |アンケートの配布先である応答者からの回答の数。|
|||