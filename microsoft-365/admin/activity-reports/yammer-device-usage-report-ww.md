---
title: 管理センターの Microsoft 365 レポート-Yammer デバイスの使用状況レポート
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
description: Yammer デバイスの使用状況レポートを取得して、ユーザーが Yammer を使用しているデバイスについて把握します。
ms.openlocfilehash: fae76e9ef769248217140c059004efc7ad330928
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779387"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>管理センターの Microsoft 365 レポート-Yammer デバイスの使用状況レポート

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
Yammer デバイスの使用状況レポートでは、ユーザーが Yammer を使用しているデバイスについての情報を示します。デバイスの種類別に毎日使用するユーザー数を表示したり、デバイスの種類別にユーザー数を表示したりします。どちらも選択した期間で表示できます。また、ユーザーごとの詳細を表示することもできます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Yammer デバイスの使用状況レポートの作成方法

1. 管理センターで、[ **レポート** ] \> [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、Yammer カードの [ **詳細表示** ] ボタンをクリックします。
  
## <a name="interpret-the-yammer-device-usage-report"></a>Yammer デバイスの使用状況レポートを解釈する

OneDrive レポートでの使用状況を表示するには、[ **デバイスの使用状況** ] タブを選択します。<br/>![Microsoft 365 レポート-Microsoft Yammer デバイスの使用状況レポート。](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Yammer デバイスの使用状況レポート-列の選択](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

また、[ **エクスポート** ] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。 このグリッドには、Microsoft 365 アカウントを使用して Yammer にログインしたユーザー、またはシングルサインオンを使用してネットワークにログインしたユーザーが表示されます。 <br/> |
|表示名  <br/> |ユーザーの完全な名前。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> |
|ユーザーの状態  <br/> |アクティブ、削除済み、または中断の3つの値のいずれか。 これらのレポートには、アクティブ、中断、および削除されたユーザーのデータが表示されます。 保留中のユーザーは、メッセージの投稿、開封、またはそのような操作ができないため、保留中のユーザーは反映されません。   <br/> |
|状態変更日付 (UTC)  <br/> |Yammer でユーザーの都道府県が変更された日付。  <br/> |
|最後のアクティビティの日付 (UTC)  <br/> |ユーザーが Yammer アクティビティに参加した最後の日付 (UTC)。  <br/> |
|Web  <br/> |ユーザーが web 上で Yammer を使用したかどうかを示します。  <br/> |
|Windows phone  <br/> | ユーザーが Windows phone で Yammer を使用したかどうかを示します。  <br/> |
|Android スマートフォン  <br/> |ユーザーが Android 電話で Yammer を使用したかどうかを示します。 <br/>|
|iphone <br/> | ユーザーが iPhone で Yammer を使用したかどうかを示します。  <br/> |
|ipad  <br/> |ユーザーが iPad で Yammer を使用したかどうかを示します。 <br/>|
|も  <br/> |ユーザーが別のデバイスで Yammer を使用しているかどうかを示します (前述のリストには含まれていません)。 <br/>|
|||