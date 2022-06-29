---
title: 'Microsoft 365 管理センター プロジェクト アクティビティ '
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
description: Project アクティビティ レポートを取得し、組織内の Project アクティビティに関する分析情報を取得する方法について説明します。
ms.openlocfilehash: 202f9e0655f2d96e6897f2803a43264741343381
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66486238"
---
# <a name="microsoft-365-reports-in-the-admin-center---project-activity"></a>管理センターの Microsoft 365 レポート - プロジェクト アクティビティ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。

**Project アクティビティ レポートでは、Microsoft Project** を使用するライセンスを持つすべてのユーザーのアクティビティを理解するには、Project とのやり取りを確認します。 また、アクセスしたプロジェクトの数と作成または編集されたタスクを調べて、コラボレーションのレベルを把握するのにも役立ちます。

## <a name="how-to-get-to-the-project-activity-report"></a>Project アクティビティ レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。
2. ダッシュボードのホームページで、プロジェクト カードの **[その他の表示** ] ボタンをクリックします。

## <a name="interpret-the-project-activity-report"></a>Project アクティビティ レポートを解釈する

このレポートを使用すると、環境内の Project のアクティビティと使用状況を確認できます。 このレポートには、次の 4 つの概要グラフが表示されます。  <br/>![Microsoft 365 レポート - Project アクティビティ。](../../media/project-activity.png)

- **アクティブなユーザー** - 毎日のアクティブなユーザーを時間の経過と共に表示します。 現時点では、これには Project for the Web および Project Online デスクトップ クライアントのみが含まれます。
- **アクティブ ユーザー (クライアント別)** - クライアント (Project for the Web とデスクトップ クライアント) によって分割された、毎日のアクティブなユーザーを時間の経過と共に表示します Project Online。
- **Project アクティビティ** - 時間の経過に伴う Project の 1 日のセッション数をクライアント (Project for the Web および Project Online デスクトップ クライアント) ごとに表示します。
- **タスク アクティビティ** - Project for the Web で時間の経過と共に作成または編集されたタスクの 1 日の数を表示します。

また、このレポートには、環境内の各プロジェクト ユーザーのアクティビティを示すテーブルもあります。

テーブルに列を追加または削除する列の **選択を選択** します。

![プロジェクト アクティビティ レポート - 列を選択します。](../../media/project-activity-columns.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。

**Project アクティビティ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 レポートで特定の日を選択すると、その日のユーザーの使用状況が表示されるように、ユーザーごとのデータ テーブルが更新されます。 ただし、この機能は最新の 28 日間のみ機能します。

### <a name="privacy-settings-impact-on-the-dashboard"></a>プライバシー設定がダッシュボードに与える影響

ユーザーまたは管理者のプライバシー設定が **どちらも** 設定されていない場合、Project Online デスクトップ クライアントの **Project アクティビティ** チャートの正確なメトリックはありません。 表示される数値は過不足になります。 プライバシー設定の詳細については、「[ポリシー設定を使用して、Microsoft 365 Apps for enterpriseのプライバシー制御を管理する」を](/deployoffice/privacy/manage-privacy-controls.md)参照してください。

## <a name="user-activity-table"></a>ユーザー アクティビティ テーブル

ユーザー アクティビティ テーブルの各メトリックの定義を次に示します。

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名|ユーザーのプリンシパル名。|
|表示名|ユーザーの完全な名前。|
|最終アクティビティの日付|その行のユーザーが Project でアクティビティを行った最新の日付 。サマリー レポート内のアクティビティも含まれます。|
|アクセスしたプロジェクト (デスクトップ)|ページの右上で選択された時間範囲の間に、Project Online デスクトップ クライアントでユーザーが開いたプロジェクトの数。|
|アクセスしたプロジェクト (Web)| ページの右上で選択された時間範囲の間に、Project for the Web でユーザーが作成したタスクの数。|
|作成されたタスク (Web)|ページの右上で選択された時間範囲の間に、Project for the Web でユーザーが作成したタスクの数。|
|編集されたタスク (Web)|ページの右上で選択された時間範囲の間に、Project for the Web でユーザーが編集したタスクの数。|
|その他|この値は、ユーザーがProject Onlineデスクトップ クライアントまたは Project for the Web (他の列でカバーされていない) で、ページの右上で選択された時間範囲でアクティビティを実行した場合に当てはまります。 ユーザーが持っていない場合、この値は false です。|
