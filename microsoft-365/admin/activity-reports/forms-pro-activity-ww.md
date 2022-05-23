---
title: Microsoft Dynamics 365 のお客様の音声アクティビティ レポート
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: レポート ダッシュボードを使用して Microsoft Dynamics 365 Customer Voice アクティビティ レポートを取得する方法と、ライセンスを持つユーザーの共同作業方法を確認する方法について説明します。
ms.openlocfilehash: 8f936f2b3232d8086928751c9846a8d762ff8219
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65636572"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>管理センターでレポートをMicrosoft 365する - Dynamics 365 Customer Voice アクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、Microsoft Dynamics 365 Customer Voice を使用するライセンスを持つすべてのユーザーのアクティビティを理解するには、Dynamics 365 Customer Voice との対話を確認します。 また、作成されたProアンケートの数と、ユーザーが回答したアンケートのProを調べて、共同作業のレベルを把握するのにも役立ちます。 
  
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Dynamics 365 Customer Voice カードの [ **その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice アクティビティ レポートを解釈する

[アクティビティ] タブを選択すると、Dynamics 365 Customer Voice レポートで **アクティビティ** を表示できます。<br/>![Microsoft 365 レポート - Microsoft Dynamics 365 Customer Voice アクティビティ レポート。](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![Dynamics 365 Customer Voice アクティビティ レポート - 列を選択します。](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 2,000 人を超えるユーザーがいる場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

**Dynamics 365 Customer Voice アクティビティ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |Microsoft Formsでアクティビティを実行したユーザーの電子メール アドレス。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |選択した日付範囲に対してユーザーがフォーム アクティビティを実行した最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/>これによりテーブルがフィルター処理され、特定の日にアクティビティを実行したユーザーに対してのみファイル アクティビティ データが表示されます。  <br/> |
|作成されたアンケートの数  <br/> |ユーザーが作成したアンケートの数。   <br/> |
|アンケート回答の数  <br/> |アンケートが配布されたレスポンダーからの回答の数。|
|||