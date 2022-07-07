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
ms.openlocfilehash: d31b290e9409e7d0e9a49013e0397578b5829697
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66663022"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>管理センターの Microsoft 365 レポート - Dynamics 365 Customer Voice アクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、Microsoft Dynamics 365 Customer Voice を使用するライセンスを持つすべてのユーザーのアクティビティを理解するには、Dynamics 365 Customer Voice との対話を確認します。 また、ユーザーが回答した Pro Surveys と Pro Surveys の数を調べて、共同作業のレベルを理解するのにも役立ちます。 
  
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice アクティビティ レポートにアクセスする方法

1. 管理センターで、 **レポート** に移動し、[ **使用状況**] を選択します。 
2. ダッシュボードのホームページで、Dynamics 365 Customer Voice カードの [ **その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice アクティビティ レポートを解釈する

[アクティビティ] タブを選択すると、Dynamics 365 Customer Voice レポートで **アクティビティ** を表示できます。

![Microsoft 365 レポート - Microsoft Dynamics 365 Customer Voice アクティビティ レポート。](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![Dynamics 365 Customer Voice アクティビティ レポート - 列を選択します。](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。

**Dynamics 365 Customer Voice アクティビティ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|測定基準|定義|
|Username  |Microsoft Formsでアクティビティを実行したユーザーの電子メール アドレス。 |
|最終アクティビティ日 (UTC)  |選択した日付範囲に対してユーザーがフォーム アクティビティを実行した最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/>これによりテーブルがフィルター処理され、特定の日にアクティビティを実行したユーザーに対してのみファイル アクティビティ データが表示されます。  |
|作成されたアンケートの数  |ユーザーが作成したアンケートの数。   |
|アンケート回答の数  |アンケートが配布されたレスポンダーからの回答の数。|
