---
title: Microsoft 365 管理センター グループ のレポート
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Microsoft 365 グループ レポートを取得して、組織内のグループのアクティビティに関する分析情報を取得し、作成および使用されているグループの数を確認します。
ms.openlocfilehash: dc3d05fdad68f18b24dae06021b0cb15306b4338
ms.sourcegitcommit: e6443eb3a4c826792806873428c0c17b59f4fde5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2022
ms.locfileid: "65889238"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>管理センターでの Microsoft 365 レポート - Microsoft 365 グループ

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft 365 グループレポートでは、組織内のグループのアクティビティに関する詳細を分析したり、作成中および使用中のグループの数を確認したりすることができます。
  
## <a name="how-to-get-to-the-groups-report"></a>グループ レポートを作成する方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。

2. ダッシュボードのホームページで、アクティブ ユーザーの [Microsoft 365 アプリ] または [アクティブ ユーザー- Microsoft 365 Services] カードの [ **その他の表示** ] ボタンをクリックして、Office 365 レポート ページにアクセスします。
  
## <a name="interpret-the-groups-report"></a>グループ レポートを解釈する

[ **グループ] アクティビティ** タブを選択すると、Office 365 レポートでライセンス認証を表示できます。

:::image type="content" alt-text="Microsoft 365 レポート - Microsoft Office 365 グループのアクティビティ。" source="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png" lightbox="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png":::

[ **列の選択] を選択** して、レポートに列を追加または削除します。

:::image type="content" alt-text="Office 365 グループ アクティビティ レポート - 列を選択します。" source="../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png":::

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 2,000 人を超えるユーザーがいる場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

**グループ** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を表示できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。

|測定基準|定義|
|:-----|:-----|
|グループ名 |グループの名前を指定します。 |
|Deleted |削除されたグループの数。 削除されたがレポート期間中にアクティビティがあるグループは、グリッドでこのフラグが true に設定されることで示されます。 |
|グループ所有者 |グループ所有者の名前。 |
|最終アクティビティ日 (UTC) |グループがメッセージを受信した最新の日付。 これはメールの会話、Yammer またはサイトでアクティビティが発生した最後の日付です。 |
|種類 |グループの種類。 これにはプライベート グループとパブリック グループがあります。 |
|Exchange で受信した電子メール |グループが受信したメッセージの数。|
|Exchange の電子メール (合計) |グループのメールボックス内のアイテムの合計数。 |
|Exchange に使用されるメールボックス ストレージ (MB) |グループのメールボックスで使用されるストレージ。 |
|SharePoint ファイル (合計) |SharePoint グループ サイトに格納されているファイルの数。 |
|SharePoint ファイル (アクティブ) |レポート期間中に (表示または変更、同期、内部または外部で共有された) SharePoint グループ サイト内のファイルの数。 |
|SharePoint に使用されるサイト ストレージの合計 (MB) |レポート期間中に使用されるストレージの量 (MB 単位)。 |
|Yammer のメッセージ (投稿済み) |レポート期間に Yammer グループに投稿されたメッセージの数。 |
|Yammer のメッセージ (読み取り) |レポート期間中に Yammer グループで読み取られた会話の数。 |
|Yammer のメッセージ (いいね) |レポート期間中に Yammer グループで気に入ったメッセージの数。 |
|メンバー |グループ内のメンバーの数。 |
|外部メンバー |グループ内の外部ユーザーの数。|
|開催された会議の合計数  |指定された期間中にユーザーが開催した 1 回限りのスケジュールされた会議と定期的な会議の合計。|
|チャネル メッセージ  |指定した期間中にユーザーがチーム チャットに投稿した一意のメッセージの数。 これには、元の投稿と返信が含まれます。 |


## <a name="related-content"></a>関連コンテンツ

[管理センターの Microsoft 365 レポート](activity-reports.md) (記事)\
[セキュリティ & コンプライアンス センターのスマート レポートと分析情報](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance) (記事)\
[管理センターの Microsoft 365 レポート - アクティブ ユーザー](../../admin/activity-reports/active-users-ww.md) (記事)

