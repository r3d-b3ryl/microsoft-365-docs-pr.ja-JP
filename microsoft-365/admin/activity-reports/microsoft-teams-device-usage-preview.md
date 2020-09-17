---
title: Microsoft Teams デバイスの使用状況
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
description: Microsoft 365 レポートから Microsoft Teams アプリの使用状況レポートを取得することによって、組織で使用される Microsoft Teams アプリの洞察を得ることができます。
ms.openlocfilehash: 98b8d6241b94445c9cb47d2c464d47c5609efdfe
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949080"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>管理センターの microsoft 365 レポート-Microsoft Teams デバイスの使用状況

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams アプリの使用状況レポートでは、組織で使用されている Microsoft Teams アプリについての洞察を得ることができます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを取得する手順

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、Microsoft Teams のアクティビティカードの [ **詳細表示** ] ボタンをクリックします。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを解釈する

[デバイスの使用 **状況** ] タブを選択すると、Teams レポートで使用するデバイスを表示できます。<br/>![Microsoft 365 レポート-Microsoft Teams デバイスの使用状況。](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Teams ユーザーデバイスレポート-列の選択](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの表示名。 [表示名] をクリックすると、Microsoft Teams 管理センターのユーザーの設定ページに移動できます。  <br/> |
|Windows  <br/> |ユーザーが Windows ベースのコンピューター上の Teams デスクトップクライアントでアクティブだった場合に選択されます。  <br/> |
|Mac  <br/> |ユーザーが macOS コンピューターの Teams デスクトップクライアントでアクティブだった場合に選択されます。  <br/> |
|iOS  <br/> |ユーザーが iOS 用の Teams モバイルクライアント上でアクティブだった場合に選択されます。  <br/> |
|Android スマートフォン  <br/> | ユーザーが Android 用の Teams モバイルクライアント上でアクティブだった場合に選択されます。  <br/> |
|Chrome OS  <br/> |ユーザーが ChromeOS コンピューター上の Teams デスクトップクライアントでアクティブだった場合に選択されます。|
|Linux  <br/> | ユーザーが Linux コンピューター上の Teams デスクトップクライアントでアクティブだった場合に選択されます。  <br/> |
|Web  <br/> |ユーザーがデバイス上の Teams web クライアントでアクティブだった場合に選択されます。|
|最後のアクティビティの日付 (UTC)  <br/> |ユーザーが Teams アクティビティに参加した最後の日付 (UTC)。  <br/> |
|ライセンスされている|ユーザーが Teams を使用するライセンスを持っている場合に選択されます。|
|||