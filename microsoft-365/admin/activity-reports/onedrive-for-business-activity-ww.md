---
title: 管理センターの Microsoft 365 レポート-OneDrive for Business アクティビティ
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
description: 組織の OneDrive 使用状況レポートを取得し、すべての OneDrive ユーザーのアクティビティ、共有ファイル数、および記憶域の使用率を把握します。
ms.openlocfilehash: e83ec835f0aa4a453f14a44d9582edcfd5aa6433
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649811"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>管理センターの Microsoft 365 レポート-OneDrive for Business アクティビティ

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要トピック](activity-reports.md)を参照してください。
  
たとえば、OneDrive でのファイルの操作を調べることで、OneDrive を使用するライセンスを持つすべてのユーザーのアクティビティを把握できます。また、共有されているファイルの数を調べると、行われているコラボレーションのレベルを把握できます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>OneDrive アクティビティ レポートの作成方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、OneDrive カードの [ **詳細表示** ] ボタンをクリックします。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>OneDrive for Business アクティビティ レポートの解釈

OneDrive レポートでアクティビティを表示するには、[ **アクティビティ** ] タブを選択します。<br/>![Microsoft 365 レポート-Microsoft OneDrive アクティビティレポート。](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![OneDrive アクティビティレポート-列の選択](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |OneDrive アカウントの所有者のユーザー名。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |選択した日付範囲の OneDrive アカウントでファイルアクティビティが実行された最新の日付。 . 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。  <br/> |
|表示または編集されたファイル  <br/> |ユーザーがアップロード、ダウンロード、変更、または表示したファイルの数。   <br/> |
|同期されたファイル  <br/> |ユーザーのローカルデバイスから OneDrive アカウントに同期されたファイルの数。 <br/> |
|内部共有ファイル  <br/> | 組織内のユーザー、またはグループ内のユーザー (外部ユーザーが含まれる可能性がある) を使用して共有されているファイルの数。  <br/> |
|外部共有ファイル  <br/> |組織外のユーザーと共有されているファイルの数。 <br/>|
|Deleted  <br/> | これは、ユーザーのライセンスが削除されたことを示します。  <br/> 注: 削除されたユーザーのアクティビティは、選択した期間中にライセンスされていた場合に限り、レポートに表示されたままになります。 [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。  <br/> |
|削除された日付  <br/> |ユーザーのライセンスが削除された日付。 <br/>|
|割り当てられた製品  <br/> |ユーザーにライセンスされている Microsoft 365 製品。|
|||