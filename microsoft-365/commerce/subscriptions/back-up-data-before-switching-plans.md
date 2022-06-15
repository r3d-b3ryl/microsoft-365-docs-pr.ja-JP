---
title: プランを変更する前にデータをバックアップする
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, jmueller
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
description: Microsoft 365プランを変更する前に、コンテンツをBackup Outlook、OneDrive、Yammer、SharePointします。
ms.date: 03/17/2021
ms.openlocfilehash: fd5239deb88fbf9b87df7e62d85a3d2cc18e1df7
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102506"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>ビジネス プランのMicrosoft 365を切り替える前にデータをバックアップする

ユーザーがデータ関連サービスが少ない別のサブスクリプションに切り替えられる場合、またはユーザーが組織を離れる場合は、新しいサブスクリプションに切り替える前に、Microsoft 365に保存されているデータのコピーをダウンロードできます。

同じまたは複数のサービスを持つサブスクリプションにユーザーを移動する場合は、ユーザー データをバックアップする必要はありません。 [「ユーザーを別のサブスクリプションに移動する」を参照してください](./move-users-different-subscription.md)。
  
## <a name="save-a-copy-of-outlook-information"></a>Outlook情報のコピーを保存する

ユーザーにOutlookがある場合は、プランを切り替える前[に、メール、連絡先、予定表をOutlook .pst ファイルにエクスポートまたはバックアップ](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)できます。
  
新しいプランへの切り替えが完了したら、ユーザーはOutlook [.pst ファイルから電子メール、連絡先、予定表をインポート](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)できます。
  
## <a name="save-files-stored-in-onedrive-for-business"></a>OneDrive for Businessに格納されているファイルを保存する

ユーザーは、別のサブスクリプションに切り替える前に、コンピューターのハード ドライブ上のフォルダーや組織のネットワーク上のファイル共有など、OneDrive[またはSharePointから](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05)別の場所にファイルやフォルダーをダウンロードできます。
  
## <a name="save-yammer-information"></a>Yammer情報を保存する

管理者はすべてのメッセージ、ノート、ファイル、トピック、ユーザー、グループを .zip ファイルにエクスポートできます。 詳細については、「[Yammer Enterpriseからデータをエクスポートする](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)」を参照してください。 開発者は[、Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) を使用してこれを行うこともできます。
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint 情報を保存する方法

ユーザーが、SharePoint Online を持つサブスクリプションからそれを持たないサブスクリプションに切り替えた場合、**SharePoint** タイルはMicrosoft 365 メニューに表示されなくなります。
  
ただし、切り替える前と同じ組織で新しいサブスクリプションを使う場合、ユーザーは SharePoint チーム サイトに引き続きアクセスできます。チーム サイトへの直接 URL を使って、ノートブック、ドキュメント、タスク、予定表の表示や更新ができます。
  
> [!TIP]
> ユーザーはサブスクリプションが切り替わる前にチーム サイトにアクセスして、ブラウザーで URL をお気に入りまたはブックマークに保存しておくことをお勧めします。
  
チーム サイトの URL は、既定では以下の形式です。
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

組織の URL はここで  _\<orgDomain\>_ 指定します。
  
たとえば、組織のドメインが contoso.onmicrosoft.com の場合、チーム サイトへの直接 URL は `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` のようになります。
  
ユーザーは SharePoint チーム サイトからローカル コンピューターまたは別の場所に、いつでも SharePoint Online ドキュメントをダウンロードすることもできます。
