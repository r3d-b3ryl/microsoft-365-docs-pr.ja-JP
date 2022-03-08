---
title: プランを変更する前にデータをバックアップする
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: プランOutlook変更するOneDrive、Yammer、SharePointコンテンツのバックアップMicrosoft 365します。
ms.date: 03/17/2021
ms.openlocfilehash: 57f897b353cfe61d5c9cae56c1d367d5e57a29ca
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317935"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>ビジネス プランのデータを切り替える前Microsoft 365バックアップする

データ関連サービスが少ない別のサブスクリプションに切り替わる場合、またはユーザーが組織を離れる場合は、Microsoft 365 に保存されているデータのコピーを新しいサブスクリプションに切り替える前にダウンロードできます。

同じサービスまたは複数のサービスを持つサブスクリプションにユーザーを移動する場合は、ユーザー データをバックアップする必要があります。 「ユーザー [を別のサブスクリプションに移動する」を参照してください](./move-users-different-subscription.md)。
  
## <a name="save-a-copy-of-outlook-information"></a>情報のコピーをOutlookする

ユーザーがOutlook場合は、計画が切り替わる前に、メール、連絡先、予定表を Outlook [.pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) ファイルにエクスポートまたはバックアップできます。
  
新しいプランへの切り替えが完了すると、ユーザーはメール、連絡先、予定表を別の [.pst ファイルOutlookインポートできます](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。
  
## <a name="save-files-stored-in-onedrive-for-business"></a>ファイルに保存されたファイルをOneDrive for Business

別のサブスクリプションに切り替える前に、[OneDrive または SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) から別の場所 (コンピューターのハード ドライブ上のフォルダー、組織のネットワーク上のファイル共有など) にファイルとフォルダーをダウンロードできます。
  
## <a name="save-yammer-information"></a>情報Yammer保存

管理者はすべてのメッセージ、ノート、ファイル、トピック、ユーザー、グループを .zip ファイルにエクスポートできます。 詳細については、「データをエクスポート[する」を参照Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)。 開発者は、YAMMER [API を使用](https://go.microsoft.com/fwlink/p/?linkid=842495)してこれを実行することもできます。
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint 情報を保存する方法

ユーザーが SharePoint Online を持つサブスクリプションからそれを持つサブスクリプションに切り替えた場合、SharePoint タイルは [Microsoft 365]  メニューに表示されなくなりました。
  
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
