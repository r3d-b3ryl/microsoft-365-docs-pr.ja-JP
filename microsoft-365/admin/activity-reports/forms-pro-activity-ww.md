---
title: 管理センターの Microsoft 365 レポート-Dynamics 365 お客様の音声アクティビティ
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
description: Microsoft 365 管理センターの Microsoft 365 レポートダッシュボードを使用して、Microsoft Dynamics 365 カスタマー音声アクティビティレポートを取得する方法について説明します。
ms.openlocfilehash: 0a854c7a89977a96e11d8ec28fd7789e8418c1cf
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988956"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>管理センターの Microsoft 365 レポート-Dynamics 365 お客様の音声アクティビティ

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、Microsoft Dynamics 365 お客様の音声を使用するためにライセンスを付与されたすべてのユーザーのアクティビティを、Dynamics 365 Customer Voice との相互作用に基づいて理解することができます。 また、ユーザーが応答した Pro の調査の数と、ユーザーが応答した pro アンケートの数を確認することによって、コラボレーションのレベルを理解することもできます。 
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 お客様の音声アクティビティレポートを取得する方法

1. 管理センターで、[ **レポート** ] \> [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、Dynamics 365 のお客様の音声カードの [ **詳細表示** ] ボタンをクリックします。
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 お客様の音声アクティビティレポートを解釈する

[ **アクティビティ** ] タブを選択すると、Dynamics 365 の顧客の音声レポートでアクティビティを表示できます。<br/>![Microsoft 365 レポート-Microsoft Dynamics 365 お客様の音声アクティビティレポート。](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Dynamics 365 お客様の音声アクティビティレポート-列の選択](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

また、[ **エクスポート** ] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |Microsoft Forms でアクティビティを実行したユーザーの電子メールアドレス。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |ユーザーが選択した日付範囲に対してフォームの動作が実行された最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/>これにより、特定の日にアクティビティを実行したユーザーのファイルアクティビティデータのみを表示するようにテーブルがフィルター処理されます。  <br/> |
|作成されたアンケートの数  <br/> |ユーザーが作成したアンケートの数。   <br/> |
|アンケートの回答数  <br/> |アンケートが配信されたレスポンダーからの応答の数。|
|||