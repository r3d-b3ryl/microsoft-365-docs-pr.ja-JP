---
title: 管理センターでの Microsoft 365 レポート - Microsoft Teams デバイスの使用状況
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Microsoft 365 レポートから Microsoft Teams アプリの使用状況レポートを取得して、組織で使用されている Microsoft Teams アプリに関する洞察を得る。
ms.openlocfilehash: 54219b060767193e711c839d25780dd3b4a618bf
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233436"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>管理センターでの Microsoft 365 レポート - Microsoft Teams デバイスの使用状況

Microsoft 365 **レポート** ダッシュボードには、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams アプリの使用状況レポートでは、組織で使用されている Microsoft Teams アプリに関する分析情報を取得できます。
  
> [!NOTE]
> レポートを表示するには、グローバル管理者、Microsoft 365 のグローバル閲覧者またはレポート閲覧者、または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者である必要があります。  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを取得する手順

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボード ホームページで、Microsoft Teams アクティビティ **カードの** [その他の表示] ボタンをクリックします。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを解釈する

Teams レポートでデバイスの使用状況を表示するには、[デバイスの使用状況] **タブを選択** します。<br/>![Microsoft 365 レポート - Microsoft Teams デバイスの使用状況。](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

[列 **の選択] を** 選択して、レポートに列を追加または削除します。  <br/> ![Teams ユーザー デバイス レポート - 列の選択](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

[ **Microsoft Teams デバイスの使用状況**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、表 (7) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの表示名。  <br/> |
|Windows  <br/> |ユーザーが Windows ベースのコンピューター上の Teams デスクトップ クライアントでアクティブだった場合に選択されます。  <br/> |
|Mac  <br/> |ユーザーが macOS コンピューター上の Teams デスクトップ クライアントでアクティブだった場合に選択します。  <br/> |
|iOS  <br/> |ユーザーが iOS 用 Teams モバイル クライアントでアクティブだった場合に選択します。  <br/> |
|Android スマートフォン  <br/> | ユーザーが Android 用の Teams モバイル クライアントでアクティブだった場合に選択します。  <br/> |
|Chrome OS  <br/> |ユーザーが ChromeOS コンピューター上の Teams デスクトップ クライアントでアクティブだった場合に選択されます。|
|Linux  <br/> | ユーザーが Linux コンピューター上の Teams デスクトップ クライアントでアクティブだった場合に選択します。  <br/> |
|Web  <br/> |ユーザーがデバイス上の Teams Web クライアントでアクティブだった場合に選択されます。|
|最後のアクティビティの日付 (UTC)  <br/> |ユーザーが Teams アクティビティに参加した最後の日付 (UTC)。  <br/> |
|ライセンスされている|ユーザーに Teams を使用するライセンスが割り当てらた場合に選択します。|
|||