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
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: '共有メールボックスからライセンスを削除して、別のユーザーに割り当てるか、ライセンスを返して支払いを行わない。 '
ms.date: 05/11/2021
ms.openlocfilehash: 89e5e3023121bb4633d7c8c1e2f92fbecc5f3e18
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370562"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>共有メールボックスからライセンスを削除する

共有メールボックスには通常、ライセンスは必要とされません。 共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーに割り当てるか、不要なライセンスの支払いを行わない方法でライセンスを返します。

> [!NOTE]
>
> 次Exchange Onlineシナリオでは、プラン 2 のライセンスが必要です。
>
> - 共有メールボックスには、50 GB を超えるストレージが使用されます。
> - 共有メールボックスは、インプレイス アーカイブを使用します。
> - 共有メールボックスは訴訟ホールドに配置されます。
> - 共有メールボックスには、割り当Microsoft 365 Defenderライセンスがあります。
> 
> ライセンスを割り当てる方法の手順については、「ユーザーにライセンスを割り当てる [」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。 


## <a name="remove-the-license"></a>ライセンスを削除する

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

   > [!NOTE]
   > [アクティブ ユーザー] ページからライセンスを削除する必要があります。 ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。
  
2. 共有メールボックスを選択します。

3. [ライセンス **とアプリ] タブの 1** つで、[ライセンス] **を展開** し、削除するライセンスのボックスをオフにします。

4. **[変更の保存]** を選択します。

5. [アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。

6. ライセンスの支払いは引き続き行います。 支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)\
[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)\
[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)\
[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)
