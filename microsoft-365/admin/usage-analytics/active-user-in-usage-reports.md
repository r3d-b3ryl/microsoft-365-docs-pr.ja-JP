---
title: Microsoft 365 の利用状況レポートのアクティブユーザー
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Microsoft 365 usage analytics、アクティビティレポート、導入指標のアクティブなユーザーについて説明します。
ms.openlocfilehash: b4834d96b2f762d77f0d27309cf8c71a782b0dcd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402884"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Microsoft 365 の利用状況レポートのアクティブユーザー

## <a name="active-user-in-usage-reports"></a>利用状況レポートのアクティブ ユーザー

Microsoft 365 products for [microsoft 365 usage analytics](usage-analytics.md)と[管理センターのアクティビティレポート](../activity-reports/activity-reports.md)のアクティブユーザーは、次のように定義されています。 
  
|**製品**|**アクティブ ユーザーの定義**|**注**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |電子メールを閲覧または送信したあらゆるユーザー。  <br/> |予定表の情報は表示されません。これは今後の更新プログラムで追加される予定です。  <br/> |
|SharePoint Online  <br/> |作成、変更、表示、削除、内部または外部との共有、サイトのクライアントとの同期、サイトのページの閲覧により、ファイルを操作したあらゆるユーザー。  <br/> |Microsoft 365 Usage Analytics テンプレートアプリの SharePoint Online のアクティブユーザー指標では、SharePoint チームサイトまたはグループサイトに対してファイルアクティビティを行ったユーザーのみが反映されます。 テンプレートアプリは、管理センターの利用状況レポートと同じように定義を同期するように更新されます。  <br/> |
|OneDrive for Business  <br/> |作成、変更、表示、削除、内部または外部との共有、クライアントとの同期により、ファイルを操作したあらゆるユーザー。  <br/> ||
|Yammer  <br/> |Yammer でメッセージを読んだり、投稿したり、「いいね」を付けたりしたあらゆるユーザー。  <br/> ||
|Skype for Business  <br/> |ピアツーピアのセッション (インスタント メッセージ、通話、テレビ電話、アプリケーション共有、ファイル転送など) に参加した、あるいは会議を手配したか、会議に参加したあらゆるユーザー。  <br/> ||
|Office  <br/> |少なくとも1つのデバイスで Microsoft 365 Pro Plus、Visio Pro、Project Pro のサブスクリプションをアクティブ化したユーザー。  <br/> ||
|Microsoft 365 グループ  <br/> |(メッセージがグループに送信されている場合) メールボックスを操作するあらゆるグループ メンバー。  <br/> |この定義は、グループサイトファイルアクティビティと Yammer グループアクティビティ (グループサイトのファイルアクティビティと、グループに関連付けられた Yammer グループに投稿されたメッセージ) によって強化されます。このデータは現在、Microsoft 365 Usage Analytics テンプレートアプリでは使用できません  <br/> |
|Microsoft Teams  <br/> |チャットメッセージ、プライベートチャットメッセージ、通話、会議、その他のアクティビティに参加したユーザー。 その他のアクティビティは、ユーザーによるその他のチームアクティビティの数として定義されます。これには、favoriting メッセージ、アプリ、ファイルの処理、検索、teams およびチャネルのフォロー、およびそれらの操作が含まれます。  <br/> ||
   
## <a name="adoption-metrics"></a>導入指標

[Microsoft 365 usage analytics](usage-analytics.md)には、時間の経過と共に製品の導入を示すためにアクティブなユーザーに関連する追加の導入指標が含まれています。 これらの指標は、選択された月、年、および製品に対して有効であり、次のように定義されます。 
  
|**測定基準**|**説明**|
|:-----|:-----|
|EnabledUsers  <br/> |その月に製品の使用が有効になっているユーザーの数。  <br/> |
|ActiveUsers  <br/> |その月にアクティブなユーザーの数。  <br/> |
|MoMReturningUsers  <br/> |前月にアクティブだった月のアクティブなユーザーの数。  <br/> |
|FirstTimeUsers  <br/> |以前にサービスを使用していなかった月にアクティブなユーザーの数。  <br/> |
|CumulativeActiveUsers  <br/> |前月にアクティブなユーザーの数と前月にあるユーザーの数。  <br/> |
|ActiveUsers (%)  <br/> |ユーザーの割合。月内に有効になっているユーザー数と比較して、1月のうちで最も近いものに切り上げられます。  <br/> |
|MoMReturningUsers (%)  <br/> |アクティブなユーザーの数と比較して、前の月にアクティブであった月のうち、最も近いユーザーの割合。  <br/> |
   
MoMReturningUsers、FirstTimeUsers、 &amp; CumulativeActiveUsers は、Microsoft Teams が含まれる2018年1月1日以降にリセットされました。
  
