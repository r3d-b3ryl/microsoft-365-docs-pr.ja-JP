---
title: 一般法人向け Office 365 サブスクリプションからライセンスを削除する
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
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9c64d127-e2dd-4ecc-81f5-2f87e5a74803
description: ライセンスが既に他のユーザーに割り当てられている場合に、Office 365 for business サブスクリプションからライセンスを削除する方法について説明します。
ms.openlocfilehash: d1af1b5696d359daf6578e090180b79587952106
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242329"
---
# <a name="remove-licenses-from-your-office-365-for-business-subscription"></a>一般法人向け Office 365 サブスクリプションからライセンスを削除する

ユーザーに割り当てられているライセンスは、サブスクリプションから削除することはできません。 ユーザーに現在割り当てられているライセンスを削除する場合は、サブスクリプションからライセンスを削除する前に、[ユーザーから](../../admin/manage/remove-licenses-from-users.md)ライセンスを削除する必要があります。

::: moniker range="o365-worldwide"

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

## <a name="remove-licenses"></a>Remove licenses

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。

2. [ **Products & services** ] ページで、ライセンスを削除するサブスクリプションを見つけ、[**ライセンスの追加/削除**] を選択します。

    [[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)

3. [**ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[**変更の送信**] を選択します。 たとえば、110 個のライセンスがあり、そのうち 5 個を削除する場合は、105 と入力します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。

2. [**サブスクリプション**] ページで、ライセンスを削除するサブスクリプションを選択し、[ライセンスの**追加/削除**] を選択します。

    [[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)

3. [ **ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[ **送信**] を選択します。 たとえば、110 個のライセンスを持っていて、5 個のライセンスを削除する場合は、「105」と入力します。


::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。

2. [**サブスクリプション**] ページで、ライセンスを削除するサブスクリプションを選択し、[ライセンスの**追加/削除**] を選択します。

    [[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)

3. [ **ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[ **送信**] を選択します。 たとえば、110 個のライセンスを持っていて、5 個のライセンスを削除する場合は、「105」と入力します。

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>[ライセンスの追加/削除] のリンクが表示されない場合

このセクションでは、[ **ライセンスの追加/削除**] のリンクが表示されない場合の理由と対処方法について説明します。
  
### <a name="a-credit-check-is-pending"></a>与信審査が保留中

与信審査が保留中の場合、"与信審査待ち" のメッセージが表示され、その与信審査が完了するまで、ライセンスを削除できません。与信審査が保留中の場合は、与信審査が完了しているかどうかを後で確認してください。通常、与信審査が完了するまで 2 営業日かかります。
  
与信審査が完了したら、[ **ユーザー**] セクションに [ **ライセンスの追加/削除**] のリンクが表示されます。 その場合は、「 [Office 365 for business サブスクリプションからライセンスを削除](#remove-licenses-from-your-office-365-for-business-subscription)する」にアクセスしてください。
  
### <a name="you-activated-the-subscription-using-a-product-key"></a>プロダクト キーを使用してサブスクリプションをアクティベートした

サブスクリプションを購入し、25 桁のプロダクト キーでライセンス認証を行っていると、"プリペイド" と表示されます。サブスクリプションがプロダクト キーを使って前払いされている場合、既に支払いが済んでいるため、ライセンスを削除することができません。ただし、サブスクリプションを更新するときに、不要なライセンスを削除できます。
  
### <a name="you-bought-your-subscription-through-a-partner"></a>パートナーを通じてサブスクリプションを購入した

CSP またはパートナーを通じてサブスクリプションを購入した場合、ライセンスを削除することはできません。 CSP に問い合わせるか、ボリュームライセンスサービスセンター (VLSC) のリンクを使用してパートナーにお問い合わせください。
  
## <a name="what-you-need-to-know-about-removing-licenses-from-users-in-office-365-for-business"></a>一般法人向け Office 365 ユーザーからライセンスを削除することについて知っておくべきこと

- グローバル管理者かユーザー管理者である必要があります。詳細については、「[管理者の役割につい](../../admin/add-users/about-admin-roles.md)て」を参照してください。

- この手順は、既存のユーザー アカウントの 1 つにライセンスを追加するときに使用します。ユーザー アカウントを追加すると同時にライセンスを割り当てる方法については、[こちら](../../admin/add-users/add-users.md)を参照してください。

## <a name="articles-about-managing-licenses-for-your-subscription"></a>サブスクリプションのライセンス管理に関する記事

- [サブスクリプションとライセンスを理解する](subscriptions-and-licenses.md)

- [ユーザーからライセンスを削除する](../../admin/manage/remove-licenses-from-users.md)

- [ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)

- [サブスクリプションのライセンスを購入する](buy-licenses.md)

- [別のサブスクリプションを購入する](../buy-another-subscription.md)

- [アドオンを購入または編集する](../buy-or-edit-an-add-on.md)

- [Yammer ユーザーライセンスを管理する](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## <a name="related-links"></a>関連リンク

[サブスクリプションをキャンセルする](../subscriptions/cancel-your-subscription.md)
