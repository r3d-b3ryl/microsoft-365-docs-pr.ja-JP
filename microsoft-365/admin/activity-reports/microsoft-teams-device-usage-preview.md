---
title: Microsoft 365 管理センター Teams アプリの使用状況レポート
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
description: Microsoft 365 レポートから Microsoft Teams アプリの使用状況レポートを取得して、組織で使用されている Microsoft Teams アプリに関する分析情報を取得します。
ms.openlocfilehash: 22e176235a455b288e078cfd5cd135beff5d668d
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66663000"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>管理センターの Microsoft 365 レポート - Microsoft Teams デバイスの使用状況

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams アプリの使用状況レポートでは、組織内で使用されている Microsoft Teams アプリに関する分析情報を取得できます。
  
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを取得する手順

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Microsoft Teams アクティビティ カードの **[その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを解釈する

[デバイスの使用状況] タブを選択すると、Teams レポートで **デバイスの使用状況** を確認できます。<br/>![Microsoft 365 レポート - Microsoft Teams デバイスの使用状況。](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  

![Teams ユーザー デバイス レポート - 列を選択します。](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 

[ **Microsoft Teams デバイスの使用状況**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの表示名。  <br/> |
|Windows  <br/> |ユーザーが Windows ベースのコンピューター上の Teams デスクトップ クライアントでアクティブであった場合に選択されます。  <br/> |
|Mac  <br/> |ユーザーが macOS コンピューター上の Teams デスクトップ クライアントでアクティブであった場合に選択されます。  <br/> |
|iOS  <br/> |ユーザーが iOS 用 Teams モバイル クライアントでアクティブであった場合に選択されます。  <br/> |
|Android スマートフォン  <br/> | ユーザーが Android 用 Teams モバイル クライアントでアクティブであった場合に選択されます。  <br/> |
|Chrome OS  <br/> |ユーザーが ChromeOS コンピューター上の Teams デスクトップ クライアントでアクティブであった場合に選択されます。|
|Linux  <br/> | ユーザーが Linux コンピューター上の Teams デスクトップ クライアントでアクティブであった場合に選択されます。  <br/> |
|Web  <br/> |ユーザーがデバイス上の Teams Web クライアントでアクティブであった場合に選択されます。|
|最終アクティビティ日 (UTC)  <br/> |ユーザーが Teams アクティビティに参加した最後の日付 (UTC)。  <br/> |
|ライセンスが付与されている|ユーザーが Teams を使用するライセンスを持つ場合に選択されます。|

## <a name="see-also"></a>関連項目
[Microsoft Teams ユーザー アクティビティ レポート](../activity-reports/microsoft-teams-user-activity-preview.md) 

[Microsoft Teams の使用状況アクティビティ レポート](../activity-reports/microsoft-teams-usage-activity.md) 
