---
title: Microsoft 365 管理センターのアクティビティ レポート
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
description: Microsoft Forms アクティビティ レポートを取得する方法については、Microsoft 365の [レポート] ダッシュボードを使用Microsoft 365 管理センター。
ms.openlocfilehash: 7b44dfe9fe8582a9efa7d768e9136b77f5d4219b
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400916"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365管理センターの [レポート] - フォーム アクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、フォームとのやり取りを見て、Microsoft フォームを使用するライセンスを持つすべてのユーザーのアクティビティを理解できます。 また、ユーザーが回答したフォームとフォームの数を確認することで、共同作業のレベルを理解するのにも役立ちます。
  
## <a name="how-to-get-to-the-forms-activity-report"></a>フォーム アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、[フォーム] カードの **[その他の** 表示] ボタンをクリックします。
  
## <a name="interpret-the-forms-activity-report"></a>フォーム アクティビティ レポートの解釈

[アクティビティ] タブを選択すると、フォーム レポートでアクティビティ **を表示** できます。<br/>![Microsoft 365レポート - Microsoft Forms アクティビティ レポート。](../../media/275fb0a1-b9d9-4233-8aaf-e7df73cc705f.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![フォーム アクティビティ レポート - 列を選択します。](../../media/0c9b0b69-5dc7-43ea-8e2c-54407b6ce2ab.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

フォーム **アクティビティ レポート** は、過去 7 日間、30 日間、90 日、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|内容|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |Microsoft Forms でアクティビティを実行したユーザーの電子メール アドレス。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |選択した日付範囲に対してユーザーがフォーム アクティビティを実行した最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/><br/>これにより、テーブルをフィルター処理して、その特定の日にアクティビティを実行したユーザーのファイル アクティビティ データのみを表示します。  <br/> |
|作成されたフォームの数  <br/> |ユーザーが作成したフォームの数。   <br/> |
|応答されたフォームの数  <br/> |ユーザーが応答を送信したフォームの数。|
|||
