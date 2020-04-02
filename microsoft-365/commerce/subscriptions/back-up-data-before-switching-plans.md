---
title: ビジネスプラン用に Office 365 を切り替える前にデータをバックアップする
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Office 365 のサブスクリプションを切り替える前、またはユーザーが組織を離れた場合は、Outlook、OneDrive、Yammer、および SharePoint コンテンツをバックアップします。
ms.openlocfilehash: 3d8196bcbd0296e1b6e681b1077d165e168d2f2f
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105749"
---
# <a name="back-up-data-before-switching-office-365-for-business-plans"></a>ビジネスプラン用に Office 365 を切り替える前にデータをバックアップする

データ関連のサービスの数が少ない別のサブスクリプションにユーザーを切り替える場合や、ユーザーが組織を離れる場合、新しいサブスクリプションに切り替える前に、Office 365 に保存してあるデータのコピーをダウンロードできます。
  
## <a name="save-a-copy-of-outlook-information"></a>Outlook 情報のコピーを保存する

ユーザーが Outlook を使用している場合は、プランを切り替える前に、[電子メール、連絡先、予定表を outlook の .pst ファイルにエクスポートまたはバックアップ](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)することができます。
  
新しいプランへの切り替えが完了すると、ユーザーは[Outlook .pst ファイルからメール、連絡先、予定表をインポート](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)できます。
  
## <a name="save-files-stored-in-onedrive-for-business"></a>OneDrive for business に保存されているファイルを保存する

別のサブスクリプションに切り替える前に、ユーザーは[OneDrive または SharePoint からファイルやフォルダー](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)を別の場所 (コンピューターのハードドライブ上のフォルダー、または組織のネットワーク上のファイル共有) にダウンロードできます。
  
## <a name="save-yammer-information"></a>Yammer 情報の保存

管理者はすべてのメッセージ、ノート、ファイル、トピック、ユーザー、グループを .zip ファイルにエクスポートできます。 詳細については、「 [Yammer Enterprise からデータをエクスポート](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)する」を参照してください。 開発者は[YAMMER API](https://go.microsoft.com/fwlink/p/?linkid=842495)を使用してこれを行うこともできます。
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint 情報を保存する方法

ユーザーが SharePoint Online を持つサブスクリプションから、それを持たないサブスクリプションに切り替えられた場合、 **sharepoint**タイルは Office 365 メニューに表示されなくなります。
  
ただし、切り替える前と同じ組織で新しいサブスクリプションを使う場合、ユーザーは SharePoint チーム サイトに引き続きアクセスできます。チーム サイトへの直接 URL を使って、ノートブック、ドキュメント、タスク、予定表の表示や更新ができます。
  
> [!TIP]
> ユーザーはサブスクリプションが切り替わる前にチーム サイトにアクセスして、ブラウザーで URL をお気に入りまたはブックマークに保存しておくことをお勧めします。
  
チーム サイトの URL は、既定では以下の形式です。
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

ここで、 _ \<orgdomain\> _は組織の URL です。
  
たとえば、組織のドメインが contoso.onmicrosoft.com の場合、チーム サイトへの直接 URL は https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx のようになります。
  
ユーザーは SharePoint チーム サイトからローカル コンピューターまたは別の場所に、いつでも SharePoint Online ドキュメントをダウンロードすることもできます。