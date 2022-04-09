---
title: アプリ使用状況レポートをMicrosoft 365 管理センター Teamsする
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Microsoft 365 レポートからMicrosoft Teamsアプリの使用状況レポートを取得することで、組織で使用されているMicrosoft Teams アプリに関する分析情報を取得します。
ms.openlocfilehash: 158c96772a79d6fb3a4b37f9593087661ea88070
ms.sourcegitcommit: 46e796c6b76a01516c48977335bbf5076ca74a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "64738337"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>管理センターでレポートをMicrosoft 365する - デバイスの使用状況をMicrosoft Teamsする

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams アプリの使用状況レポートでは、組織内で使用されているMicrosoft Teams アプリに関する分析情報を取得できます。
  
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを取得する手順

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Microsoft Teamsアクティビティ カードの **[その他の表示**] ボタンをクリックします。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを解釈する

[デバイスの使用状況] タブを選択すると、Teams レポートで **デバイスの使用状況** を確認できます。<br/>![Microsoft 365 レポート - デバイスの使用状況をMicrosoft Teamsします。](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![ユーザー デバイス レポートTeams - 列を選択します。](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

[ **Microsoft Teams デバイスの使用状況**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの表示名。  <br/> |
|Windows  <br/> |Windows ベースのコンピューター上のTeams デスクトップ クライアントでユーザーがアクティブな場合に選択されます。  <br/> |
|Mac  <br/> |macOS コンピューター上のTeams デスクトップ クライアントでユーザーがアクティブであった場合に選択されます。  <br/> |
|iOS  <br/> |ユーザーが iOS 用Teamsモバイル クライアントでアクティブであった場合に選択されます。  <br/> |
|Android スマートフォン  <br/> | Android 用のモバイル クライアントTeamsユーザーがアクティブな場合に選択されます。  <br/> |
|Chrome OS  <br/> |ユーザーが ChromeOS コンピューター上のTeams デスクトップ クライアントでアクティブであった場合に選択されます。|
|Linux  <br/> | Linux コンピューター上のTeams デスクトップ クライアントでユーザーがアクティブであった場合に選択されます。  <br/> |
|Web  <br/> |ユーザーがデバイス上のTeams Web クライアントでアクティブであった場合に選択されます。|
|最終アクティビティ日 (UTC)  <br/> |ユーザーがTeams アクティビティに参加した最後の日付 (UTC)。  <br/> |
|ライセンスが付与されている|ユーザーがTeamsを使用するライセンスを持つ場合に選択します。|

## <a name="see-also"></a>関連項目
[Microsoft Teams ユーザー アクティビティ レポート](../activity-reports/microsoft-teams-user-activity-preview.md) 

[Microsoft Teams利用状況レポート](../activity-reports/microsoft-teams-usage-activity.md) 
