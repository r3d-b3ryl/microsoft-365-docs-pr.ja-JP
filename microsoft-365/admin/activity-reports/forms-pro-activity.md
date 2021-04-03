---
title: 管理センターの Microsoft 365 レポート - Dynamics 365 Customer Voice アクティビティ
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
- MET150
- MOE150
- GEA150
description: Microsoft 365 管理センターの Microsoft 365 レポート ダッシュボードを使用して、Microsoft Dynamics 365 Customer Voice アクティビティ レポートを取得する方法について説明します。
ms.openlocfilehash: 26d376602caebcb5276b77a3d2c962a14e5fead5
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579652"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>管理センターの Microsoft 365 レポート - Dynamics 365 Customer Voice アクティビティ

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
たとえば、Dynamics 365 Customer Voice との対話を見て、Microsoft Dynamics 365 Customer Voice を使用するライセンスを持つすべてのユーザーのアクティビティを理解できます。 また、作成された Pro サーベイの数と、ユーザーが回答した Pro サーベイを確認することで、共同作業のレベルを理解するのにも役立ちます。 
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Forms Pro アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。

    
2. [レポート **の選択] ドロップダウンから****、[Dynamics 365 Customer Voice アクティビティ] を** \> **選択します**。

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 Customer Voice アクティビティ レポートの解釈

ユーザーの Dynamics 365 Customer Voice アクティビティのビューを取得するには、[アクティビティ] グラフと [ユーザー] グラフ **を****参照** します。 

![フォーム アクティビティ レポート](../../media/formsproactivity.png)

|アイテム|説明|
|:-----|:-----|
|1.  <br/> |**Dynamics 365 Customer Voice** アクティビティ レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、表 (7) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。   <br/> |
|2.  <br/> |各レポートのデータは、通常、過去 48 時間と同じ最新のデータです。  <br/> |
|3。  <br/> |[ **ユーザー]** ビューは、アクティブな Dynamics 365 Customer Voice ユーザーの数の傾向を理解するのに役立ちます。 ユーザーは、特定の期間に Pro Survey (作成、編集、表示など) のアクティビティを実行した場合、アクティブと見なされます。  <br/> |
|4.  <br/> |[ **アクティビティ]** ビューを使用すると、アクティブなユーザー数の傾向を把握できます。 アクティブなユーザーとは、特定の期間内にファイル アクティビティ (保存、同期、変更、共有) を実行したか、ページにアクセスしたユーザーです。<br/> 注: 1 つのアンケートでアクティビティが複数回発生する場合がありますが、アクティブなアンケートは 1 つのみカウントされます。 たとえば、Pro Survey を作成し、指定した期間に同じアンケートを複数回編集し続け、1 つのアンケートとしてカウントされます。 <br>|
|5.<br/>|[ユーザー **] グラフ** の Y 軸は、一意のユーザーの数です。 X 軸は、一意のユーザーがアクティブな日付です。 凡例は次のとおりです。<br/><br/>**デザイナーは** 、ユーザーが Dynamics 365 Customer Voice Survey を作成または編集したという意味です。<br><br>アクティビティ グラフ **の** Y 軸は、アンケートごとの Dynamics 365 Customer Voice 応答の数です。 X 軸は、アンケートまたは応答アクティビティが発生した日付です。 凡例は次のとおりです。<br/><br/>**作成されたアンケート** は、ユーザーが作成した一意の Dynamics 365 Customer Voice アンケートの数です。<br>**応答とは** 、アンケートを受け取ったユーザーが送信した匿名または匿名以外の回答の数です。 |
|6.<br/>|凡例の項目を選択して、グラフに表示する系列をフィルター処理できます。 たとえば、[ユーザー] グラフで、デザイナー、レスポンダー、または合計ユーザーを選択して、各ユーザーに関連する情報のみを表示します。 この選択を変更しても、下のグリッド テーブルの情報は変更されません。|
|7.<br/>|次の表に、ユーザー単位のアクティビティの内訳を示します。 凡例は次のとおりです。<br/><br/>**ユーザー** 名は、Microsoft フォームでアクティビティを実行したユーザーの電子メール アドレスです。<br/>**最後のアクティビティ日付 (UTC)** は、選択した日付範囲に対してユーザーがフォーム アクティビティを実行した最新の日付です。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/>これにより、テーブルをフィルター処理して、その特定の日にアクティビティを実行したユーザーのファイル アクティビティ データのみを表示します。<br/><br/>**作成されたアンケートの数** は、ユーザーが作成したアンケートの数です。<br/> **アンケート回答数は** 、アンケートの配布先である回答者からの回答数です。|
|8.<br/>|[列の **管理] アイコンを** 選択して、レポートの列を追加または削除します。|
|9.<br/>|また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、簡単な集計、並べ替え、フィルター処理を実行して、さらに分析できます。 ユーザー数が 100 人未満の場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行えます。 ユーザーが 100 人を超える場合は、フィルター処理と並べ替えを行う場合は、データをエクスポートする必要があります。|