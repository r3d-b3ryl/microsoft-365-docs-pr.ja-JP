---
title: 共有メールボックスからライセンスを削除する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: '共有メールボックスからライセンスを削除して、別のユーザーに割り当てる。 '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698305"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>共有メールボックスからライセンスを削除する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

共有メールボックスは、通常、ライセンスを必要とします。 ユーザーにライセンスを割り当てるか、ライセンスを返して不要なライセンスの支払いを行わないでいく場合は、次の手順に従って共有メールボックスからライセンスを削除します。

> [!NOTE]
> 次のシナリオでは、ライセンスが必要です。
> 1. 共有メールボックスには 50 GB を超える記憶域が使用されます。
> 2. 共有メールボックスは、イン Place Archiving を使用します。
> 3. 共有メールボックスは訴訟ホールドの対象です。
> 4. 共有メールボックスには、Microsoft Defender ライセンスが割り当てされています。

  
## <a name="remove-the-license"></a>ライセンスを削除する

::: moniker range="o365-worldwide"

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

   > [!NOTE]
   > [アクティブなユーザー] ページからライセンスを削除する必要があります。 ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。 
  
2. 共有メールボックスを選択します。

3. [ライセンス **とアプリ] タブで** 、[ **ライセンス** ] を展開し、削除するライセンスのチェック ボックスをオフにします。

4. [**変更の保存**] を選択します。

5. When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.

6. ライセンスの支払いは引き続き行います。 支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/remove-licenses-from-subscription.md)。

::: moniker-end

::: moniker range="o365-germany"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

    > [!NOTE]
    > [アクティブなユーザー] ページからライセンスを削除する必要があります。 ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。

2. 共有メールボックスを選択し、[製品ライセンス] の横にある **[編集** ] **を選択します**。

3. [製品 **ライセンス] ページで**、削除するライセンスのトグルを [オフ] に設定します。

4. [**保存**] を選択します。

5. When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.

6. ライセンスの支払いは引き続き行います。 支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/remove-licenses-from-subscription.md)。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

    > [!NOTE]
    > [アクティブなユーザー] ページからライセンスを削除する必要があります。 ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。

2. 共有メールボックスを選択し、[製品ライセンス] の横にある **[編集** ] **を選択します**。

3. [製品 **ライセンス] ページで**、削除するライセンスのトグルを [オフ] に設定します。

4. [**保存**] を選択します。

5. When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.

6. ライセンスの支払いは引き続き行います。 支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/remove-licenses-from-subscription.md)。

::: moniker-end 

 

## <a name="related-articles"></a>関連記事

[共有メールボックスについて](about-shared-mailboxes.md)

[共有メールボックスを作成する](create-a-shared-mailbox.md)

[共有メールボックスを構成する](configure-a-shared-mailbox.md)

[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)

[共有メールボックスの問題を解決する](resolve-issues-with-shared-mailboxes.md)
