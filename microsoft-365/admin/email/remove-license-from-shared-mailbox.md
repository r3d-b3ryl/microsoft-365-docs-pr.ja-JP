---
title: 共有メールボックスからライセンスを削除する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: sinakassaw, nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: '共有メールボックスからライセンスを削除して別のユーザーに割り当てるか、ライセンスを返して支払いを行わないようにします。 '
ms.date: 04/22/2022
ms.openlocfilehash: 5248c7fdb807a91ab2a9a7dfd44bdb375eb7d0f0
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65678922"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>共有メールボックスからライセンスを削除する

共有メールボックスには通常、ライセンスは必要ありません。 次の手順に従って、共有メールボックスからライセンスを削除し、ユーザーにライセンスを割り当てるか、必要のないライセンスの支払いを行わないようにライセンスを返すことができます。

> [!NOTE]
>
> 次のシナリオでは、Exchange Online プラン 2 ライセンスが必要です。
>
> - 共有メールボックスには、50 GB を超えるストレージが使用されています。
> - 共有メールボックスでは、インプレース アーカイブが使用されます。
> - 共有メールボックスは訴訟ホールドに置かれます。
> 
> ライセンスを割り当てる方法の詳細な手順については、「ユーザーに [ライセンスを割り当てる」を](/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。 


## <a name="remove-the-license"></a>ライセンスを削除する

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

   > [!NOTE]
   > [アクティブなユーザー] ページからライセンスを削除する必要があります。 ライセンスはユーザー設定であるため、[共有メールボックス] ページからライセンスを削除することはできません。
  
2. 共有メールボックスを選択します。

3. [ **ライセンスとアプリ** ] タブで [ **ライセンス** ] を展開し、削除するライセンスのチェック ボックスをオフにします。

4. **[変更の保存]** を選択します。

5. **[アクティブなユーザー**] ページに戻ると、共有メールボックスの状態は **ライセンスなし** になります。

6. ライセンスの支払いは引き続き行います。 支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックス GWT を作成する](create-a-shared-mailbox.md) (記事)\
[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)\
[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)\
[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)
