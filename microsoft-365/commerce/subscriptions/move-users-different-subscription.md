---
title: ユーザーを別のサブスクリプションに移動する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
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
- manage_licenses
search.appverid: MET150
description: サブスクリプション間でユーザーを移動する方法について説明します。
ms.date: 05/12/2022
ms.openlocfilehash: c3450cecf4219f825740d5777cebeb05782b3dc4
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67322631"
---
# <a name="move-users-to-a-different-subscription"></a>ユーザーを別のサブスクリプションに移動する

複数の製品を持ち、1 つの製品のライセンスを持つユーザーを別の製品に移行する場合は、既存のライセンスを別の製品に置き換えることができます。

## <a name="before-you-begin"></a>はじめに

ライセンスを割り当てるには、グローバル管理者、ライセンス管理者、またはユーザー管理者である必要があります。詳細については「[Microsoft 365 の管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="move-users-to-a-different-subscription"></a>ユーザーを別のサブスクリプションに移動する

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

2. 既存のライセンスを置き換えるユーザーの名前の横にあるチェック ボックスをオンにします。

3. 上部にある [**製品ライセンスの管理**] を選択します。

4. [ **製品ライセンスの管理** ] ウィンドウで、[ **置換**  ] を選択し、ユーザーに割り当てるライセンスを選択します。

5. 下部にある [変更\>を **閉じて****保存]** を選択します。

## <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Microsoft 365 for Business プランを切り替える前にデータをバックアップする

ユーザーがデータ関連サービスが少ない別のサブスクリプションに切り替えられる場合、またはユーザーが組織を離れる場合は、新しいサブスクリプションに切り替える前に、Microsoft 365 に保存されているデータのコピーをダウンロードできます。

同じまたは複数のサービスを持つサブスクリプションにユーザーを移動する場合は、ユーザー データをバックアップする必要はありません。
  
### <a name="save-a-copy-of-outlook-information"></a>Outlook 情報のコピーを保存する

ユーザーが Outlook を使用している場合は、プランを切り替える前 [に、メール、連絡先、予定表を Outlook .pst ファイルにエクスポートまたはバックアップ](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) できます。
  
新しいプランへの切り替えが完了したら、ユーザーは [Outlook .pst ファイルから電子メール、連絡先、予定表をインポート](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)できます。
  
### <a name="save-files-stored-in-onedrive-for-business"></a>OneDrive for Businessに格納されているファイルを保存する

別のサブスクリプションに切り替える前に、ユーザーは [OneDrive または SharePoint から](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) 別の場所 (コンピューターのハード ドライブ上のフォルダーや組織のネットワーク上のファイル共有など) にファイルとフォルダーをダウンロードできます。
  
### <a name="save-yammer-information"></a>Yammer 情報を保存する

管理者はすべてのメッセージ、ノート、ファイル、トピック、ユーザー、グループを .zip ファイルにエクスポートできます。 詳細については、「 [Yammer Enterprise からデータをエクスポートする](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)」を参照してください。 開発者は [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) を使用してこれを行うこともできます。
  
### <a name="how-to-save-sharepoint-information"></a>SharePoint 情報を保存する方法

ユーザーが SharePoint Online を持つサブスクリプションからそれを持たないサブスクリプションに切り替えた場合、 **SharePoint** タイルは Microsoft 365 メニューに表示されなくなります。
  
ただし、新しいサブスクリプションが切り替え元のサブスクリプションと同じ組織内にある限り、ユーザーは引き続き SharePoint チーム サイトにアクセスできます。 チーム サイトへの直接 URL を使って、ノートブック、ドキュメント、タスク、予定表の表示や更新ができます。
  
> [!TIP]
> ユーザーはサブスクリプションが切り替わる前にチーム サイトにアクセスして、ブラウザーで URL をお気に入りまたはブックマークに保存しておくことをお勧めします。
  
チーム サイトの URL は、既定では以下の形式です。
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

組織の URL はここで  _\<orgDomain\>_ 指定します。
  
たとえば、組織のドメインが contoso.onmicrosoft.com の場合、チーム サイトへの直接 URL は `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` のようになります。
  
ユーザーは SharePoint チーム サイトからローカル コンピューターまたは別の場所に、いつでも SharePoint Online ドキュメントをダウンロードすることもできます。

## <a name="next-steps"></a>次の手順

[未使用のライセンスを他のユーザーに再割り当て](../../managed-desktop/get-started/assign-licenses.md)しない場合は、[サブスクリプションからライセンスを削除](../../commerce/licenses/buy-licenses.md)して、必要以上のライセンスを支払わないようにすることを検討してください。

## <a name="related-content"></a>関連コンテンツ

[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md) (記事)\
[サブスクリプションからライセンスを削除する](../licenses/buy-licenses.md) (記事)\
[手動でプランを変更する](change-plans-manually.md) (記事)\
[Microsoft 365 for Business のサブスクリプションとライセンスについて (](../licenses/subscriptions-and-licenses.md) 記事)\
[別の Microsoft 365 for Business サブスクリプションを購入する](../try-or-buy-microsoft-365.md) (記事)
