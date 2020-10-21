---
title: Microsoft 365 for business プランを手動で変更する
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: 新しいサブスクリプションを購入し、サブスクリプションとアクティブの両方が表示されていることを確認して、手動でサブスクリプションを変更します。
ms.openlocfilehash: 09557b3556db1e6f17d7a4cd54a88ba34d0f0bd7
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647821"
---
# <a name="change-plans-manually"></a>プランを手動で変更する

## <a name="step-1-decide-how-to-change-plans"></a>手順 1: プランの変更方法を決定する

すべてのユーザーを1つのプランから別のプランに変更するには [、[アップグレード] タブを使用](upgrade-to-different-plan.md)するのが最善の方法です。この方法は使用できない場合があります。 代わりに、プランを手動で変更します。

- [ **アップグレード** ] タブが表示されている場合は、現在のプランをアップグレードできません。

- [ **アップグレード** ] タブを選択すると、必要なプランが一覧に表示されません。

- すべてのユーザーを同じ方法でアップグレードしない場合。 一部の企業では、さまざまなユーザーを異なるプランに加入させる必要があります。 これには手動による変更を使用してください。

手動による変更を続行するには、このトピックの「 [手順 2: 新しいサブスクリプションを購入](#step-2-buy-a-new-subscription) する」を参照してください。

> [!IMPORTANT]
> 現在のプラン (ダウングレード) よりもデータ関連サービス数が少ないプランに変更する場合は、保持するデータを手動でバックアップする必要があります。 詳細については、「 [プランを変更する前にデータをバックアップする](back-up-data-before-switching-plans.md)」を参照してください。

## <a name="step-2-buy-a-new-subscription"></a>手順 2: 新しいサブスクリプションを購入する

**購入済みですか?** ユーザーを移動するサブスクリプションが既にある場合は、この手順を省略して、このトピックの「 [新しいサブスクリプションとライセンスを確認](#step-3-check-your-new-subscription-and-licenses) する」に進みます。

または

**新しいサブスクリプションとライセンスを購入します。** 「 [別の Microsoft 365 for business サブスクリプションを購入](../buy-another-subscription.md) する」の手順に従って、新しいサブスクリプションを購入します。

必ずユーザーが現在所属している組織と同じ組織のサブスクリプションを購入してください。 たとえば、移動するユーザーの電子メールアドレスを確認します。 メールアドレスに contoso.com が含まれている場合は \@ 、contoso.com の新しいサブスクリプションを購入する必要があります。
移動する各ユーザーのライセンスを含めます。

## <a name="step-3-check-your-new-subscription-and-licenses"></a>手順 3: 新しいサブスクリプションとライセンスを確認する

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。

2. **両方のサブスクリプションが一覧表示され、アクティブであることを確認する** ユーザーを移行するサブスクリプションと、ユーザーを移動するサブスクリプションが一緒に表示されている必要があります。 最初に確認したときに新しいサブスクリプションが表示されない場合は、後でもう一度確認してみてください。 両方のサブスクリプションがアクティブであることを確認してください。 新しいサブスクリプションが一覧に表示されない、またはアクティブではない場合は[新しいサブスクリプションが一覧に表示されない、またはアクティブではない](#the-new-subscription-isnt-listed-or-isnt-active)を参照してください。

3. **ユーザーごとに十分な数のライセンスがあることを確認する** 各ユーザーには、サブスクリプションに一致するライセンスが必要です。 そのため、10人のユーザーを Microsoft 365 Business Premium に移行する場合は、10個のライセンスが利用可能であることを確認する必要があります。

4. **新しいサブスクリプションのライセンスがさらに必要ですか?**
   [ **製品** ] ページに移動し、 [ライセンスを購入](../licenses/buy-licenses.md)します。

> [古いライセンスの処理](#what-about-the-old-licenses)」を参照してください。

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>新しいサブスクリプションが一覧に表示されない、またはアクティブではない

- **2 つのサブスクリプションを購入し、両方とも一覧に表示されない場合** 、異なる組織 (異なるドメイン) 用に購入した可能性があります。 サブスクリプションは組織の境界を超えることはできません。

- **追加のサブスクリプションがあることがわかっ**ており、ここにリストされていない場合、またはアクティブでない場合は、 [Microsoft サポートにお問い合わせ](../../admin/contact-support-for-business-products.md)ください。

### <a name="what-about-the-old-licenses"></a>古いライセンスの処理

現在のサブスクリプションのライセンスは後で削除されるので、それ以降は新しいユーザー ライセンスの料金のみを支払うことになります。

## <a name="step-4-reassign-licenses"></a>手順 4: ライセンスを再割り当てする

### <a name="reassign-a-license-for-one-user"></a>1 人のユーザーのライセンスを再割り当てする

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. [ **アクティブなユーザー** ] ページで、ライセンスを割り当てるユーザーを選択します。

3. [ **ライセンスとアプリ** ] タブで、[ **ライセンス**] を展開し、割り当てるライセンスのボックスを選択して、[ **変更の保存**] を選択します。

### <a name="reassign-licenses-for-multiple-users-at-once"></a>複数のユーザーのライセンスを一度に再割り当てする

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 既存のライセンスを置換するユーザーの名前の横にある円を選択します。

3. 上部で、[ **その他のオプション** (**...**)] を選択し、[ **製品ライセンスの管理**] を選択します。

4. Select **Replace existing product license assignments** \> **Next**.

5. これらのユーザーに割り当てる製品を [ **オン**] の位置に切り替えます。

    > [!TIP]
    > - ユーザーが使用できるサービスを制限するには、そのユーザーで削除するサービスを [ **オフ**] の位置に切り替えます。 たとえば、Skype for Business Online 以外のすべてのサービスにユーザーがアクセスできるようにするには、Skype for Business Online サービスを [ **オフ**] の位置に切り替えます。
    > - 選択したユーザーで以前に割り当てられたライセンスは削除されます。

6. [**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] の順に選択します。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>手順 5: サブスクリプションをキャンセルするか、不要になったライセンスを削除する (オプション)

1 つのサブスクリプションから別のサブスクリプションにすべてのユーザーを移動し、元のサブスクリプションが不要になった場合、[サブスクリプションをキャンセルする](cancel-your-subscription.md)ことができます。

一部のユーザーのみを別のサブスクリプションに移動した場合は、不要になった[ライセンスを削除](../licenses/remove-licenses-from-subscription.md)します。

## <a name="call-support-to-help-you-change-plans"></a>プランを変更するためのサポートへのお問い合わせ
[Microsoft サポートに連絡する](../../admin/contact-support-for-business-products.md)