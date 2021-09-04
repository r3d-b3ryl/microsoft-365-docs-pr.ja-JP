---
title: Microsoft 365管理センターのレポート - Microsoft ブラウザーの使用状況
ms.author: waxiaoyu
author: sarahwxy
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '[レポート] ダッシュボードの [レポート] ダッシュボードを使用して Microsoft Microsoft 365利用状況レポートを取得するMicrosoft 365 管理センター。'
ms.openlocfilehash: 0e2d3b2ecc0ad196a64f15966fe034edb2601555
ms.sourcegitcommit: 59bda7cfd92ef1b0e97858da51a776ec668bcfe0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2021
ms.locfileid: "58884208"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>Microsoft 365管理センターのレポート - Microsoft ブラウザーの使用状況

[Microsoft 365 **レポート]** ダッシュボードには、組織内の製品全体のアクティビティの概要が表示されます。 これにより、個々の製品レベルレポートを掘り下して、各製品内のアクティビティに関するより詳細な分析情報を提供できます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft ブラウザーの使用状況レポートでは、ユーザーの使用状況、Internet Explorer、Microsoft Edge 従来版に関するMicrosoft Edgeできます。 利用状況レポートは、Microsoft Microsoft 365を使用してアクセスされるオンライン サービスに基づいて行います。

> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、または Skype for Business 管理者のグローバル管理者、グローバル リーダー、またはレポート リーダーである必要があります。

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>Microsoft ブラウザー使用状況レポートにアクセスする方法

1. 管理センターで、[レポートの使用状況] **ページ** \> <b><a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">に移動</a></b> します。

2. ダッシュボードのホームページで、Microsoft ブラウザー **の使用状況** カードの [その他の表示] ボタンをクリックします。

## <a name="how-to-notify-users-to-upgrade-their-browser"></a>ブラウザーのアップグレードをユーザーに通知する方法

:::image type="content" alt-text="Microsoft ブラウザー使用状況レポートのアクション フロー。" source="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png" lightbox="../../media/1ef4eb08-18b8-4dda-aa15-1aad013ecd70.png":::

グローバル管理者は、エッジ レガシ (サポートされていない) および Internet Explorer で Microsoft 365 サービスを使用しているユーザーにメッセージを送信することをオプトインできます (すぐにサポートされません)。 この対象となるメッセージは、これらのブラウザーのサポートがすぐに送信され、Microsoft Edge に関する情報とブラウザーを切り替える簡単な手順を含むサポート記事へのリンクがユーザーに通知されます。 

この機能は、レポート ページで確認できます。 メッセージが作成されると、ユーザーは 2021 年 8 月 17 日まで指定された頻度で通知を受け取ります。 この機能をいつでもオフにし、ユーザーへの通知の送信を停止できます。 通知の送信を再度開始するには、機能をオンに戻します。

## <a name="interpret-the-microsoft-browser-usage-report"></a>Microsoft ブラウザー使用状況レポートの解釈

:::image type="content" alt-text="Microsoft ブラウザー使用状況レポート。" source="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png" lightbox="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png":::

|アイテム|説明|
|:-----|:-----|
|1. |**Microsoft ブラウザー使用状況レポート** は、過去 7 日間、30 日間、90 日、または 180 日間の傾向を確認できます。 |
|2. |各レポートのデータは、通常、過去 7 日間までカバーされます。 |
|3。 |[**日次アクティブ ユーザー** ] グラフには、Microsoft Edge サービスへのアクセスにMicrosoft Edge 従来版、Internet Explorerの日次ユーザー数Microsoft 365表示されます。 |
|4. |[**アクティブ ユーザー]** グラフには、選択した期間に Microsoft Edge、Microsoft Edge 従来版、Internet Explorer を使用して Microsoft 365 サービスにアクセスするユーザーの総数が表示されます。 |
|5. |テーブルには、ユーザー レベルでのデータの内訳が表示されます。テーブルの列は追加または削除できます。  <br/><br/>**ユーザー** 名は、Microsoft ブラウザーを使用してサービスにMicrosoft 365ユーザーの電子メール アドレスです。<br><br/>**ユーザー Microsoft Edge** サービスへの接続に使用した場合、Microsoft EdgeマークがMicrosoft 365されます。<br/><br/>**ユーザー Microsoft Edge 従来版** サービスへの接続に使用した場合に、Microsoft Edge 従来版マークがMicrosoft 365されます。<br/><br/>**ユーザー Internet Explorer** サービスへの接続に使用した場合、Internet ExplorerがMicrosoft 365されます。 |
|6. |[列の **選択] アイコン** を選択して、レポートの列を追加または削除します。|
|7. |また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、簡単な集計、並べ替え、およびフィルター処理を実行して、さらに分析できます。 ユーザー数が 100 人未満の場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行えます。 ユーザーが 100 人を超える場合は、フィルター処理と並べ替えを行う場合は、データをエクスポートする必要があります。|
