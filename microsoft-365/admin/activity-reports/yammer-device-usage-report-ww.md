---
title: デバイス使用状況レポートのMicrosoft 365 管理センター Yammer
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
description: Yammerデバイス使用状況レポートを入手して、ユーザーがYammerを使用しているデバイス、デバイスの種類別の毎日のユーザー数、ユーザーごとの詳細について詳しく説明します。
ms.openlocfilehash: faf5b364090fe4ed88e0a6dd977238e65f3e6c68
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65467188"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>管理センターでレポートをMicrosoft 365する - デバイス使用状況レポートYammer

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
Yammer デバイスの使用状況レポートでは、ユーザーが Yammer を使用しているデバイスについての情報を示します。デバイスの種類別に毎日使用するユーザー数を表示したり、デバイスの種類別にユーザー数を表示したりします。どちらも選択した期間で表示できます。また、ユーザーごとの詳細を表示することもできます。
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Yammer デバイスの使用状況レポートの作成方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Yammer カードの **[その他の表示**] ボタンをクリックします。
  
## <a name="interpret-the-yammer-device-usage-report"></a>Yammerデバイス使用状況レポートを解釈する

[デバイスの使用状況] タブを選択すると、OneDrive レポートで **使用状況** を表示できます。<br/>![Microsoft 365 レポート - Microsoft Yammer デバイス使用状況レポート。](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![デバイス使用状況レポートYammer - 列を選択します。](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

**Yammerデバイス使用状況** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。
  
|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザーの電子メール アドレス。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。 このグリッドには、Microsoft 365 アカウントを使用してYammerにログインしたユーザー、またはシングル サインオンを使用してネットワークにログインしたユーザーが表示されます。 <br/> |
|表示名  <br/> |ユーザーの完全な名前。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> |
|ユーザーの状態  <br/> |アクティブ、削除、または中断の 3 つの値のいずれか。 これらのレポートには、アクティブ、中断、および削除されたユーザーのデータが表示されます。 保留中のユーザーはメッセージを投稿、読み取り、または好きにできないため、保留中のユーザーは反映されません。   <br/> |
|状態変更日 (UTC)  <br/> |Yammerでユーザーの状態が変更された日付。  <br/> |
|最終アクティビティ日 (UTC)  <br/> |ユーザーがYammer アクティビティに参加した最後の日付 (UTC)。  <br/> |
|Web  <br/> |ユーザーが Web でYammerを使用したかどうかを示します。  <br/> |
|Windows電話  <br/> | ユーザーがWindows電話でYammerを使用したかどうかを示します。  <br/> |
|Android スマートフォン  <br/> |ユーザーがAndroid電話でYammerを使用したかどうかを示します。 <br/>|
|Iphone <br/> | ユーザーがiPhoneでYammerを使用したかどうかを示します。  <br/> |
|Ipad  <br/> |ユーザーがiPadでYammerを使用したかどうかを示します。 <br/>|
|他  <br/> |ユーザーが別のデバイスでYammerを使用したかどうかを示します。前に示されていません。 <br/>|
|||