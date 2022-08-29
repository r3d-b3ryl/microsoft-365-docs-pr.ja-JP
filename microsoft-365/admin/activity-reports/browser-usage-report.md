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
description: Microsoft 365 管理センターの Microsoft 365 レポート ダッシュボードを使用して、Microsoft ブラウザーの使用状況レポートを取得する方法について説明します。
ms.openlocfilehash: 2444a93a1a68cd994da19325a8a00af868b6ba16
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67386519"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-browser-usage"></a>管理センターの Microsoft 365 レポート - Microsoft ブラウザーの使用状況

Microsoft 365 レポート ダッシュボードには、組織内の製品全体のアクティビティの概要が表示されます。 これにより、個々の製品レベルのレポートをドリルダウンして、各製品内のアクティビティに関するより詳細な分析情報を得ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 

Microsoft 365 管理 センターの **Microsoft ブラウザー使用状況レポート** では、ユーザーが Microsoft Edge 経由で Microsoft 365 オンライン サービスにアクセスするかどうかを確認できます。 このレポート分析情報は、組織を Microsoft Edge に移行するのに役立ちます。 使用状況レポートは、Microsoft 365 アカウントにサインインし、Microsoft Edge ブラウザーを使用して Microsoft 365 サービスにアクセスする組織内のユーザーの集計数に基づいています。

## <a name="how-to-get-to-the-microsoft-browser-usage-report"></a>Microsoft ブラウザーの使用状況レポートにアクセスする方法

1. 管理センターで、[**レポート**\>の <b><a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a></b>] ページに移動します。

2. ダッシュボードのホームページで、Microsoft ブラウザーの使用状況カードの [ **その他の表示** ] ボタンをクリックします。


## <a name="interpret-the-microsoft-browser-usage-report"></a>Microsoft ブラウザー使用状況レポートを解釈する

:::image type="content" alt-text="Microsoft ブラウザーの使用状況レポート。" source="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png" lightbox="../../media/95557c88-24ee-417d-a828-96ba00b17aaf.png":::

**Microsoft ブラウザーの使用状況** レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 

**[日次アクティブ ユーザー**] グラフには、Microsoft 365 サービスへのアクセスに使用した場合の Microsoft Edge の 1 日のユーザー数が表示されます。

**[アクティブ ユーザー]** グラフには、選択した期間に Microsoft Edge を使用している間に Microsoft 365 サービスにアクセスするユーザーの合計数が表示されます。

このレポートは、Microsoft 365 管理 センターの利用状況ダッシュボードのアクティビティ レポートへの既存のアクセス権を持つ IT 管理者に限定されたアクセス許可を持つ組織の内部です。

> [!NOTE]
> Microsoft ブラウザーの使用状況とユーザー レベルのレポートを集計できます。 ユーザー レベルの識別は [組織のポリシーに従って削除](activity-reports.md#show-user-details-in-the-reports) でき、 [ロール ベースのアクセス制御](../../admin/add-users/assign-admin-roles.md) を使用してレポート アクセスを調整できます。


|アイテム|説明|
|:-----|:-----|
|**Username** | Microsoft Edge を使用して Microsoft 365 サービスに接続したユーザーの電子メール アドレス。|
| **使用済み Microsoft Edge**| Microsoft 365 サービス ユーザーが Microsoft Edge に接続している場合は、目盛りを表示します。|

[ **列の選択]** アイコンを選択して、レポートの列を追加または削除します。

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、簡単な集計、並べ替え、フィルター処理を実行して詳細な分析を行うことができます。 
