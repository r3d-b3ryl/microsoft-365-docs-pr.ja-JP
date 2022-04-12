---
title: ブラウザー使用状況レポートのMicrosoft 365 管理センター
ms.author: waxiaoyu
author: sarahwxy
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
- MET150
- MOE150
- GEA150
description: Microsoft 365 管理センターの [Microsoft 365 レポート] ダッシュボードを使用して Microsoft ブラウザー使用状況レポートを取得する方法について説明します。
ms.openlocfilehash: 29b4161b9bb6cbc509d6541e13fa9222628534b4
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782019"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>管理センターでレポートをMicrosoft 365する - Microsoft ブラウザーの使用状況

Microsoft 365 レポート ダッシュボードには、組織内の製品全体のアクティビティの概要が表示されます。 これにより、個々の製品レベルのレポートをドリルダウンして、各製品内のアクティビティに関するより詳細な分析情報を得ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft ブラウザーの使用状況レポートでは、Internet Explorer、Microsoft Edge 従来版、および新しいMicrosoft Edge使用状況に関する分析情報を取得できます。 使用状況レポートは、Microsoft ブラウザーを使用してアクセスされるMicrosoft 365 オンライン サービスに基づいています。

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>Microsoft ブラウザーの使用状況レポートにアクセスする方法

1. 管理センターで、[**レポート**\>の <b><a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a></b>] ページに移動します。

2. ダッシュボードのホームページで、Microsoft ブラウザーの使用状況カードの [ **その他の表示** ] ボタンをクリックします。

## <a name="how-to-notify-users-to-upgrade-their-browser"></a>ブラウザーをアップグレードするようにユーザーに通知する方法

:::image type="content" alt-text="Microsoft ブラウザー使用状況レポートアクション フロー。" source="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png" lightbox="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png":::

グローバル管理者は、Internet Explorer から Microsoft 365 サービスにアクセスしているユーザーにメッセージを送信することを選択できます (Internet Explorer デスクトップ アプリケーションは 2022 年 6 月 15 日に廃止されます)。 この対象となるメッセージは、これらのブラウザーのサポートが間もなく終了することをユーザーに通知し、Microsoft Edgeに関する情報とブラウザーを切り替えるために従う簡単な手順を含むサポート記事へのリンクをユーザーに通知します。 

この機能は、組織で Internet Explorer の使用状況がレポートに表示されている場合 (必要なグローバル管理者アクセス許可) がある場合は、Microsoft ブラウザー使用状況レポート ページで確認できます。 メッセージが作成されると、ユーザーは 2022 年 6 月 15 日まで指定された頻度で通知を受け取ります。 この機能はいつでもオンまたはオフにできます。

これは、現在、米国のグローバル管理者のみが利用でき、オンラインでユーザー通知Excel許可する、期限付きの機能です。

## <a name="interpret-the-microsoft-browser-usage-report"></a>Microsoft ブラウザー使用状況レポートを解釈する

:::image type="content" alt-text="Microsoft ブラウザーの使用状況レポート。" source="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png" lightbox="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png":::

|アイテム|説明|
|:-----|:-----|
|1. |**Microsoft ブラウザーの使用状況** レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 |
|2. |各レポートのデータは、通常、過去 7 日間まで対象となります。 |
|3。 |**[日次アクティブ ユーザー**] グラフには、Microsoft Edge、Microsoft Edge 従来版、Internet Explorer の 1 日のユーザー数が、Microsoft 365 サービスへのアクセスに使用された場合に表示されます。 |
|4. |**[アクティブ ユーザー]** グラフには、選択した期間に Microsoft 365 サービスにアクセスするために使用した場合に、Microsoft Edge、Microsoft Edge 従来版、Internet Explorer を使用しているユーザーの合計数が表示されます。 |
|5. |テーブルには、ユーザー レベルでのデータの内訳が表示されます。テーブルの列は追加または削除できます。  <br/><br/>**ユーザー名** は、Microsoft ブラウザーを使用してMicrosoft 365 サービスに接続したユーザーの電子メール アドレスです。<br><br/>**使用Microsoft Edge** は、ユーザーがMicrosoft 365 サービスへの接続にMicrosoft Edgeした場合に目盛りを表示します。<br/><br/>**使用Microsoft Edge 従来版** は、ユーザーがMicrosoft 365 サービスへの接続にMicrosoft Edge 従来版した場合に目盛りを表示します。<br/><br/>**ユーザーが Internet Explorer を** 使用してMicrosoft 365 サービスに接続した場合、使用された Internet Explorer には目盛りが表示されます。 |
|6. |[ **列の選択]** アイコンを選択して、レポートの列を追加または削除します。|
|7. |また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、簡単な集計、並べ替え、フィルター処理を実行して詳細な分析を行うことができます。 ユーザーが 100 人未満の場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 100 人を超えるユーザーがいる場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。|
