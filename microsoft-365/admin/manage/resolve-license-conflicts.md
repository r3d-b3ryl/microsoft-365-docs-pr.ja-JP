---
title: ライセンスの競合を解決する
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Microsoft 365 for business サブスクリプションとのライセンスの競合を解決する方法について説明します。
ms.openlocfilehash: 284a6b169c02314dd2bbd0e13c10c081cb50f58d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114455"
---
# <a name="resolve-license-conflicts"></a>ライセンスの競合を解決する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

新しいユーザーを作成する前に、サブスクリプションに必要なライセンスを購入することをお勧めします。 ユーザー アカウントを作成したとき、新しい ユーザーにライセンスを割り当てることができます。 すべてのライセンスをユーザーに既に割り当てているが、一部のライセンスの期限が切れている場合、あるいは既にユーザーに割り当てられているライセンスを削除するとき、ライセンスの競合が発生します。 詳細については、「サブスクリプションからライセンス [を削除する」を参照してください](../../commerce/licenses/remove-licenses-from-subscription.md)。
  
## <a name="how-do-i-view-license-conflicts"></a>ライセンスの競合を確認する方法

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. 競合に **関する** 情報については、[状態] 列を確認します。 競合がある場合は、1 人または複数のユーザーに有効なライセンスが必要なという警告メッセージが表示されます。

    > [!NOTE]
    > 競合がない場合は [ **状態**] 列が表示されません。

## <a name="how-do-i-resolve-license-conflicts"></a>ライセンスの競合を解決する方法

ライセンスの競合を解決するには [、ライセンスを](../../commerce/licenses/buy-licenses.md) 追加購入するか、ライセンスが不要になったユーザーからライセンス [を削除します](remove-licenses-from-users.md)。 任意で、[ユーザー アカウントを削除してライセンスを解放する](../add-users/delete-a-user.md)こともできます。
  
## <a name="related-articles"></a>関連記事

[ユーザーにライセンスを割り当てる](assign-licenses-to-users.md)
  
[ユーザーからライセンスを削除する](remove-licenses-from-users.md)
