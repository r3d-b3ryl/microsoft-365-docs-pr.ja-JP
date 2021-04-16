---
title: プランを変更する前にデータをバックアップする
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Microsoft 365 プランを変更する前に、Outlook、OneDrive、Yammer SharePoint コンテンツをバックアップします。
ms.openlocfilehash: ecfd17d779cbb39ff786b192f72621bc94677776
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860525"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Microsoft 365 for business プランを切り替える前にデータをバックアップする

ユーザーがデータ関連サービスが少ない別のサブスクリプションに切り替わる場合、またはユーザーが組織を離れる場合は、Microsoft 365 に保存されているデータのコピーを新しいサブスクリプションに切り替える前にダウンロードできます。

同じサービスまたは複数のサービスを持つサブスクリプションにユーザーを移動する場合は、ユーザー データをバックアップする必要があります。 「ユーザー [を別のサブスクリプションに移動する」を参照してください](./move-users-different-subscription.md)。
  
## <a name="save-a-copy-of-outlook-information"></a>Outlook 情報のコピーを保存する

ユーザーが Outlook を使用している場合は、計画を切り替える前に、メール、連絡先、予定表を [Outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) ファイルにエクスポートまたはバックアップできます。
  
新しいプランへの切り替えが完了すると [、Outlook .pst](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)ファイルからメール、連絡先、予定表をインポートできます。
  
## <a name="save-files-stored-in-onedrive-for-business"></a>OneDrive for Business に保存されているファイルを保存する

別のサブスクリプションに切り替える前に、 [ユーザーは OneDrive](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) または SharePoint から別の場所 (コンピューターのハード ドライブ上のフォルダー、組織のネットワーク上のファイル共有など) にファイルとフォルダーをダウンロードできます。
  
## <a name="save-yammer-information"></a>情報Yammer保存

管理者はすべてのメッセージ、ノート、ファイル、トピック、ユーザー、グループを .zip ファイルにエクスポートできます。 詳細については、「エンタープライズからデータをエクスポート [する」をYammerしてください](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)。 開発者は、API Yammer [を使用](https://go.microsoft.com/fwlink/p/?linkid=842495) して、これを実行することもできます。
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint 情報を保存する方法

ユーザーが SharePoint Online を持つサブスクリプションから、そのサブスクリプションを持つサブスクリプションを持たなかったサブスクリプションに切り替えた場合 **、SharePoint** タイルは Microsoft 365 メニューに表示されなくなりました。
  
ただし、切り替える前と同じ組織で新しいサブスクリプションを使う場合、ユーザーは SharePoint チーム サイトに引き続きアクセスできます。チーム サイトへの直接 URL を使って、ノートブック、ドキュメント、タスク、予定表の表示や更新ができます。
  
> [!TIP]
> ユーザーはサブスクリプションが切り替わる前にチーム サイトにアクセスして、ブラウザーで URL をお気に入りまたはブックマークに保存しておくことをお勧めします。
  
チーム サイトの URL は、既定では以下の形式です。
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

組織  _\<orgDomain\>_ の URL はここで指定します。
  
たとえば、組織のドメインが contoso.onmicrosoft.com の場合、チーム サイトへの直接 URL は `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` のようになります。
  
ユーザーは SharePoint チーム サイトからローカル コンピューターまたは別の場所に、いつでも SharePoint Online ドキュメントをダウンロードすることもできます。