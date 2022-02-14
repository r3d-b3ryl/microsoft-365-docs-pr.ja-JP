---
title: 使用状況レポートのMicrosoft 365ユーザー
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
description: 使用状況分析、アクティビティ レポート、導入Microsoft 365のアクティブ ユーザーについて学習します。
ms.openlocfilehash: 748bd08e08cc5e8243c3733c4b3f8448e15ab050
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806098"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>使用状況レポートのMicrosoft 365ユーザー

## <a name="active-user-in-usage-reports"></a>利用状況レポートのアクティブ ユーザー

管理センターのMicrosoft 365分析Microsoft 365アクティビティ レポートのアクティブ [](usage-analytics.md) なユーザーは、次のように定義されます[](../activity-reports/activity-reports.md)。 
  
|**製品**|**アクティブ ユーザーの定義**|**注**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |次のアクションを実行したユーザー: [読み取りとしてマークする]、メッセージを送信する、予定を作成する、会議出席依頼を送信する、(仮として) 承諾する、または会議出席依頼を辞退する、会議をキャンセルする。  <br/> |予定表の情報は表示されません。これは今後の更新プログラムで追加される予定です。  <br/> |
|SharePoint Online  <br/> |作成、変更、表示、削除、内部または外部との共有、サイトのクライアントとの同期、サイトのページの閲覧により、ファイルを操作したあらゆるユーザー。  <br/> |Microsoft 365 Usage Analytics テンプレート アプリの SharePoint Online のアクティブなユーザー 指標は、SharePoint チーム サイトまたはグループ サイトに対してファイルアクティビティを行ったユーザーのみを反映します。 テンプレート アプリが更新され、管理センターの利用状況レポートと同じ定義に同期されます。  <br/> |
|OneDrive for Business  <br/> |作成、変更、表示、削除、内部または外部との共有、クライアントとの同期により、ファイルを操作したあらゆるユーザー。  <br/> ||
|Yammer  <br/> |Yammer でメッセージを読んだり、投稿したり、「いいね」を付けたりしたあらゆるユーザー。  <br/> ||
|Skype for Business  <br/> |ピアツーピアのセッション (インスタント メッセージ、通話、テレビ電話、アプリケーション共有、ファイル転送など) に参加した、あるいは会議を手配したか、会議に参加したあらゆるユーザー。  <br/> ||
|Office  <br/> |少なくとも 1 つのデバイスで、Microsoft 365 Pro Plus、Visio Pro、Project Proサブスクリプションをアクティブ化したユーザー。  <br/> ||
|Microsoft 365 グループ  <br/> |(メッセージがグループに送信されている場合) メールボックスを操作するあらゆるグループ メンバー。  <br/> |この定義は、グループ サイト ファイルアクティビティとグループ アクティビティ (Yammer サイトでのファイル アクティビティと、グループに関連付けられた Yammer グループに投稿されたメッセージ) で拡張されます。このデータは現在、利用状況分析テンプレート アプリMicrosoft 365使用できません  <br/> |
|Microsoft Teams  <br/> |チャット メッセージ、プライベート チャット メッセージ、通話、会議、その他のアクティビティに参加したユーザー。 その他のアクティビティは、メッセージ、アプリ、ファイルの作業、検索、チームとチャネルの後処理、および好意など、ユーザーによる他のチーム アクティビティの数として定義されます。これらに限定されません。  <br/> ||
   
## <a name="adoption-metrics"></a>導入指標

[Microsoft 365分析には](usage-analytics.md)、アクティブ ユーザーに関連する導入指標が多く含まれているので、時間の過ぎた製品の採用を示します。 これらの指標は、選択した月、年、および製品に対して有効であり、次のように定義されます。 
  
|**測定基準**|**説明**|
|:-----|:-----|
|EnabledUsers  <br/> |その月に製品を使用できるユーザーの数。  <br/> |
|ActiveUsers  <br/> |月にアクティブなユーザーの数。  <br/> |
|MoMReturningUsers  <br/> |前の月にもアクティブだった月にアクティブなユーザーの数。  <br/> |
|FirstTimeUsers  <br/> |以前にサービスを使用したことがない月にアクティブなユーザーの数。  <br/> |
|CumulativeActiveUsers  <br/> |月にアクティブなユーザーの数と前の月の数。  <br/> |
|ActiveUsers(%)  <br/> |ユーザーの割合は、その月に有効になっているユーザーの数と比較して、その月にアクティブな最も近い 10 分の 1 に四捨五入されます。  <br/> |
|MoMReturningUsers(%)  <br/> |ユーザーの割合 (最も近い 10 分の 1 に四捨五入) は、前の月にもアクティブであった月にアクティブで、アクティブなユーザーの数と比較します。  <br/> |
   
MoMReturningUsers、FirstTimeUsers&amp;、CumulativeActiveUsers は、2018 年 1 月 1 日からリセットされ、Microsoft Teams。
  
