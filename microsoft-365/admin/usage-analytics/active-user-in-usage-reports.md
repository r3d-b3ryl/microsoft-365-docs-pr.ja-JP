---
title: Microsoft 365使用状況レポートのアクティブ ユーザー
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Microsoft 365利用状況分析、アクティビティ レポート、導入メトリックのアクティブ ユーザーについて説明します。
ms.openlocfilehash: 748bd08e08cc5e8243c3733c4b3f8448e15ab050
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806098"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Microsoft 365使用状況レポートのアクティブ ユーザー

## <a name="active-user-in-usage-reports"></a>利用状況レポートのアクティブ ユーザー

Microsoft 365[利用状況分析](usage-analytics.md)と[管理センターのアクティビティ レポート](../activity-reports/activity-reports.md)のMicrosoft 365製品のアクティブ ユーザーは、次のように定義されます。 
  
|**製品**|**アクティブ ユーザーの定義**|**注**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |次のいずれかの操作を実行したユーザー: 読み取りとしてマーク、メッセージの送信、予定の作成、会議出席依頼の送信、会議出席依頼の承諾 (仮)、会議出席依頼の拒否、会議の取り消し。  <br/> |予定表の情報は表示されません。これは今後の更新プログラムで追加される予定です。  <br/> |
|SharePoint Online  <br/> |作成、変更、表示、削除、内部または外部との共有、サイトのクライアントとの同期、サイトのページの閲覧により、ファイルを操作したあらゆるユーザー。  <br/> |Microsoft 365 Usage Analytics テンプレート アプリの SharePoint Online のアクティブなユーザー メトリックには、SharePoint チーム サイトまたはグループ サイトに対してファイル アクティビティを行ったユーザーのみが反映されます。 テンプレート アプリが更新され、管理センターの使用状況レポートと同じ定義に定義が同期されます。  <br/> |
|OneDrive for Business  <br/> |作成、変更、表示、削除、内部または外部との共有、クライアントとの同期により、ファイルを操作したあらゆるユーザー。  <br/> ||
|Yammer  <br/> |Yammer でメッセージを読んだり、投稿したり、「いいね」を付けたりしたあらゆるユーザー。  <br/> ||
|Skype for Business  <br/> |ピアツーピアのセッション (インスタント メッセージ、通話、テレビ電話、アプリケーション共有、ファイル転送など) に参加した、あるいは会議を手配したか、会議に参加したあらゆるユーザー。  <br/> ||
|Office  <br/> |Microsoft 365 Pro Plus、Visio Pro、またはProject Proサブスクリプションを少なくとも 1 つのデバイスでアクティブ化したユーザー。  <br/> ||
|Microsoft 365 グループ  <br/> |(メッセージがグループに送信されている場合) メールボックスを操作するあらゆるグループ メンバー。  <br/> |この定義は、グループ サイト のファイル アクティビティとYammer グループ アクティビティ (グループ サイトのファイル アクティビティと、グループに関連付けられているYammer グループに投稿されたメッセージ) によって強化されます。このデータは現在、Microsoft 365 Usage Analytics テンプレート アプリでは使用できません  <br/> |
|Microsoft Teams  <br/> |チャット メッセージ、プライベート チャット メッセージ、通話、会議、またはその他のアクティビティに参加したユーザー。 その他のアクティビティは、メッセージ、アプリの好み、ファイルの操作、検索、フォロー、チームとチャネルの優先など、ユーザーによって他のチーム アクティビティの数として定義されます。これらに限定されません。  <br/> ||
   
## <a name="adoption-metrics"></a>導入メトリック

[Microsoft 365使用状況分析](usage-analytics.md)には、アクティブ ユーザーに関連する導入メトリックが多く含まれていて、時間の経過と共に製品の導入が示されます。 これらのメトリックは、選択された月、年、および製品に対して有効であり、次のように定義されます。 
  
|**測定基準**|**説明**|
|:-----|:-----|
|EnabledUsers  <br/> |その月に製品を使用できるユーザーの数。  <br/> |
|ActiveUsers  <br/> |月にアクティブなユーザーの数。  <br/> |
|MoMReturningUsers  <br/> |前の月にもアクティブだった月にアクティブなユーザーの数。  <br/> |
|FirstTimeUsers  <br/> |前にサービスを使用したことがない月にアクティブなユーザーの数。  <br/> |
|CumulativeActiveUsers  <br/> |月にアクティブなユーザーの数と前の月の数。  <br/> |
|ActiveUsers(%)  <br/> |その月に有効になっているユーザーの数と比較して、アクティブなユーザーの割合は、最も近い 10 分の 10 に丸められます。  <br/> |
|MoMReturningUsers(%)  <br/> |アクティブなユーザーの数と比較して、前の月にもアクティブであった月にアクティブなユーザーの割合 (最も近い 10 分の 1 に丸められます)。  <br/> |
   
MoMReturningUsers、FirstTimeUsers、 &amp; CumulativeActiveUsers は、Microsoft Teamsを含めて 2018 年 1 月 1 日からリセットされました。
  
