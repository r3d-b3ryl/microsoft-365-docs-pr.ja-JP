---
title: Microsoft 365 管理センター フォーム アクティビティ レポート
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
description: Microsoft 365 レポート ダッシュボードを使用してMicrosoft Formsアクティビティ レポートを取得する方法と、ライセンスを持つユーザーがフォームと対話する方法を確認する方法について説明します。
ms.openlocfilehash: 106baca93a3cd7078c97d3ca3f5430efc540d4af
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662132"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>管理センターの Microsoft 365 レポート - フォーム アクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、フォームとの対話を見て、Microsoft Formsを使用するライセンスを持つすべてのユーザーのアクティビティを理解できます。 また、作成されたフォームとユーザーが応答したフォームの数を調べて、コラボレーションのレベルを理解するのにも役立ちます。
  
## <a name="how-to-get-to-the-forms-activity-report"></a>フォーム アクティビティ レポートにアクセスする方法

1. 管理センターで、 **レポート** に移動し、[ **使用状況**] を選択します。 
2. ダッシュボードのホームページで、フォーム カードの **[その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-forms-activity-report"></a>フォーム アクティビティ レポートを解釈する

[アクティビティ] タブを選択すると、フォーム レポートで **アクティビティ** を表示できます。

![Microsoft 365 レポート - アクティビティ レポートMicrosoft Forms。](../../media/275fb0a1-b9d9-4233-8aaf-e7df73cc705f.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。 

![フォーム アクティビティ レポート - 列を選択します。](../../media/0c9b0b69-5dc7-43ea-8e2c-54407b6ce2ab.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 

**フォーム アクティビティ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を表示できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|測定基準|定義|
|Username   |Microsoft Formsでアクティビティを実行したユーザーの電子メール アドレス。   |
|最終アクティビティ日 (UTC)   |選択した日付範囲に対してユーザーがフォーム アクティビティを実行した最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/><br/>これによりテーブルがフィルター処理され、特定の日にアクティビティを実行したユーザーに対してのみファイル アクティビティ データが表示されます。   |
|作成されたフォームの数   |ユーザーが作成したフォームの数。    |
|応答されたフォームの数  |ユーザーが返信を送信したフォームの数。|

