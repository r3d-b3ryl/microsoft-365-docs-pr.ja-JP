---
title: Yammer デバイス使用状況レポートのMicrosoft 365 管理センター
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Yammer デバイスの使用状況レポートを入手して、ユーザーが Yammer を使用しているデバイスの詳細、デバイスの種類別の毎日のユーザー数、ユーザーごとの詳細を確認します。
ms.openlocfilehash: e2ca63fb67b08c96a6b4c5528092b14f55739540
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66663066"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>管理センターの Microsoft 365 レポート - Yammer デバイス使用状況レポート

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
Yammer デバイスの使用状況レポートでは、ユーザーが Yammer を使用しているデバイスについての情報を示します。デバイスの種類別に毎日使用するユーザー数を表示したり、デバイスの種類別にユーザー数を表示したりします。どちらも選択した期間で表示できます。また、ユーザーごとの詳細を表示することもできます。
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Yammer デバイスの使用状況レポートの作成方法

1. 管理センターで、 **レポート** に移動し、[ **使用状況**] を選択します。 
2. ダッシュボードのホームページで、Yammer カードの **[その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-yammer-device-usage-report"></a>Yammer デバイス使用状況レポートを解釈する

[デバイスの使用状況] タブを選択すると、OneDrive レポートで **使用状況** を表示できます。

![Microsoft 365 レポート - Microsoft Yammer デバイス使用状況レポート。](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  

![Yammer デバイス使用状況レポート - 列を選択します。](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 

**Yammer デバイス使用状況** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。 このグリッドには、Microsoft 365 アカウントを使用して Yammer にログインしたユーザー、またはシングル サインオンを使用してネットワークにログインしたユーザーが表示されます。 <br/> |
|表示名  <br/> |ユーザーの完全な名前。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> |
|ユーザーの状態  <br/> |アクティブ、削除、または中断の 3 つの値のいずれか。 これらのレポートには、アクティブ、中断、および削除されたユーザーのデータが表示されます。 保留中のユーザーはメッセージを投稿、読み取り、または好きにできないため、保留中のユーザーは反映されません。   <br/> |
|状態変更日 (UTC)  <br/> |Yammer でユーザーの状態が変更された日付。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |ユーザーが Yammer アクティビティに参加した最後の日付 (UTC)。  <br/> |
|Web  <br/> |ユーザーが Web で Yammer を使用したかどうかを示します。  <br/> |
|Windows Phone  <br/> | ユーザーが Windows Phone で Yammer を使用したかどうかを示します。  <br/> |
|Android スマートフォン  <br/> |ユーザーが Android スマートフォンで Yammer を使用したかどうかを示します。 <br/>|
|Iphone <br/> | ユーザーが iPhone で Yammer を使用したかどうかを示します。  <br/> |
|Ipad  <br/> |ユーザーが iPad で Yammer を使用したかどうかを示します。 <br/>|
|他  <br/> |ユーザーが以前に一覧表示されていない別のデバイスで Yammer を使用したかどうかを示します。 <br/>|
|||