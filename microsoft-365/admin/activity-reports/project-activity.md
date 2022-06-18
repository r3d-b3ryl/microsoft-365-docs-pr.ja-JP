---
title: 'Microsoft 365 管理センター Project アクティビティ '
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
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
description: Project アクティビティ レポートを取得し、組織内のProjectアクティビティに関する分析情報を取得する方法について説明します。
ms.openlocfilehash: 704372359df2f460e9a87d6325d8ec4b116d3c60
ms.sourcegitcommit: f302de988d98628922eea1f509a3f639634ddc64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2022
ms.locfileid: "66151234"
---
# <a name="microsoft-365-reports-in-the-admin-center---project-activity"></a>管理センターでレポートをMicrosoft 365する - Project アクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 

**Project アクティビティ レポート** では、Projectとの対話を見て、Microsoft Projectを使用するライセンスを持つすべてのユーザーのアクティビティを理解できます。 また、アクセスしたプロジェクトの数と作成または編集されたタスクを調べて、コラボレーションのレベルを把握するのにも役立ちます。 
 
## <a name="how-to-get-to-the-project-activity-report"></a>Project アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。
2. ダッシュボードのホームページで、Project カードの **[その他の表示**] ボタンをクリックします。

## <a name="interpret-the-project-activity-report"></a>Project アクティビティ レポートを解釈する

このレポートを使用して、環境内のProjectのアクティビティと使用状況を確認できます。 このレポートには、次の 4 つの概要グラフが表示されます。  <br/>![Microsoft 365 レポート - Project アクティビティ。](../../media/project-activity.png)

- **アクティブなユーザー** - 毎日のアクティブなユーザーを時間の経過と共に表示します。 現時点では、これには、Web クライアントとProject Online デスクトップ クライアントのProjectのみが含まれています。
- **アクティブ ユーザー (クライアント別)** - クライアント (Web とデスクトップ クライアントのProject) によって分割された、毎日のアクティブなユーザーを毎日表示します Project Online。
- **Project アクティビティ** - 時間の経過に伴うProjectの 1 日のセッション数を各クライアント (Web およびProject Online デスクトップ クライアントのProject) ごとに表示します。
- **タスク アクティビティ** - Web のProjectで時間の経過と共に作成または編集されたタスクの 1 日の数を表示します 

また、このレポートには、環境内の各プロジェクト ユーザーのアクティビティを示すテーブルもあります。


テーブルに列を追加または削除する列の **選択を選択** します。  <br/> ![アクティビティ レポートProject - 列を選択します。](../../media/project-activity-columns.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 

**Projectアクティビティ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 レポートで特定の日を選択すると、その日のユーザーの使用状況が表示されるように、ユーザーごとのデータ テーブルが更新されます。 ただし、この機能は最新の 28 日間のみ機能します。

### <a name="privacy-settings-impact-on-the-dashboard"></a>プライバシー設定がダッシュボードに与える影響

ユーザーまたは管理者のプライバシー設定が **どちらも** 設定されていない場合、Project Online デスクトップ クライアントの **Projectアクティビティ** チャートの正確なメトリックはありません。 表示される数値は過不足になります。 プライバシー設定の詳細については、「[ポリシー設定を使用して、Microsoft 365 Apps for enterpriseのプライバシー制御を管理する」を](/deployoffice/privacy/manage-privacy-controls.md)参照してください。



## <a name="user-activity-table"></a>ユーザー アクティビティ テーブル
ユーザー アクティビティ テーブルの各メトリックの定義を次に示します。 

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーのプリンシパル名。   <br/> |
|表示名   <br/> |ユーザーの完全な名前。  <br/> |
|最終アクティビティの日付   <br/> |その行のユーザーがProjectでアクティビティを行った最新の日付 (概要レポートのアクティビティを含む)。   <br/> |
|アクセスしたプロジェクト (デスクトップ)   <br/> |ページの右上で選択された時間範囲の間に、Project Online デスクトップ クライアントでユーザーが開いたプロジェクトの数。    <br/> |
|アクセスしたプロジェクト (Web)   <br/> | ページの右上で選択された時間範囲の間に、Web のProjectのユーザーによって作成されたタスクの数。   <br/> |
|作成されたタスク (Web)   <br/> |ページの右上で選択された時間範囲の間に、Web のProjectのユーザーによって作成されたタスクの数。 <br/> |
|編集されたタスク (Web)    <br/> |ページの右上で選択された時間範囲の間に、Web のProjectでユーザーが編集したタスクの数。  <br/> |
|その他 <br/> |この値は、ユーザーがProject Onlineデスクトップ クライアントで、またはページの右上で選択された時間範囲の Web のProject (他の列でカバーされていない) でアクティビティを実行した場合に当てはまります。 ユーザーが持っていない場合、この値は false です。 <br/>|
|||

