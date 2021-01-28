---
title: ビジネス向け Microsoft 365 プランを手動で変更する
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
description: 新しいサブスクリプションを購入し、両方のサブスクリプションが一覧に表示され、アクティブな状態にすることで、サブスクリプションを手動で変更します。
ms.openlocfilehash: 1127a48ff23c528e3218bae4ccfd063df5e3c26d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029388"
---
# <a name="change-plans-manually"></a>手動でプランを変更する

## <a name="step-1-decide-how-to-change-plans"></a>手順 1: プランを変更する方法を決定する

すべてのユーザーを別のプランに変更する最善の方法は、[アップグレード] [タブを使用する方法です](upgrade-to-different-plan.md)。これができない場合があります。 代わりに、手動でプランを変更します。

- [アップグレード **]** タブに現在のプランをアップグレードできない場合。

- [アップグレード] タブを **選択すると** 、目的のプランが一覧に表示されません。

- すべてのユーザーを同じ方法でアップグレードしない場合。 一部の企業では、さまざまなユーザーを異なるプランに加入させる必要があります。 このために手動で変更を行います。

手動による変更を続行するには、「手順 2: このトピックの [新しいサブスクリプション](#step-2-buy-a-new-subscription) を購入する」を参照してください。

> [!IMPORTANT]
> データ関連サービスが現在のプラン (ダウングレード) よりも少ないプランに変更する場合は、保持するデータを手動でバックアップする必要があります。 詳細については、「プランを変更 [する前にデータをバックアップする」を参照してください](back-up-data-before-switching-plans.md)。

## <a name="step-2-buy-a-new-subscription"></a>手順 2: 新しいサブスクリプションを購入する

**既に購入済みですか?** ユーザーを移動するサブスクリプションが既にある場合は、この手順を省略して、「手順 [3:](#step-3-check-your-new-subscription-and-licenses) このトピックで新しいサブスクリプションとライセンスを確認する」に進みます。

OR

**新しいサブスクリプションとライセンスを購入します。** 「別の [Microsoft 365 for Business サブスクリプションを](../buy-another-subscription.md) 購入する」の手順に従って、新しいサブスクリプションを購入します。

必ずユーザーが現在所属している組織と同じ組織のサブスクリプションを購入してください。 たとえば、移動するユーザーのメール アドレスを確認します。 メール アドレスにメール アドレスが含contoso.com、新しいサブスクリプションを購入する必要 \@ contoso.com。
移動する各ユーザーのライセンスを含めます。

## <a name="step-3-check-your-new-subscription-and-licenses"></a>手順 3: 新しいサブスクリプションとライセンスを確認する

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。

2. **両方のサブスクリプションが一覧表示され、アクティブな状態を確認する** ユーザーを移動するサブスクリプションと、ユーザーを移動するサブスクリプションを一緒に一覧表示する必要があります。 最初に確認したときに新しいサブスクリプションが表示されない場合は、後でもう一度確認してみてください。 両方のサブスクリプションがアクティブな状態を確認します。 新しいサブスクリプションが一覧に表示されない、またはアクティブではない場合は[新しいサブスクリプションが一覧に表示されない、またはアクティブではない](#the-new-subscription-isnt-listed-or-isnt-active)を参照してください。

3. **ユーザーごとに十分なライセンスを持っている** 各ユーザーには、サブスクリプションと一致するライセンスが必要です。 そのため、10 人のユーザーを Microsoft 365 Business Premium に移行する場合は、10 個のライセンスが利用可能な必要があります。

4. **新しいサブスクリプションのライセンスが必要な場合**
   [製品] ページ **に移動し** 、ライセンス [を追加購入します](../licenses/buy-licenses.md)。

> [古いライセンスの処理](#what-about-the-old-licenses)」を参照してください。

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>新しいサブスクリプションが一覧に表示されない、またはアクティブではない

- **2 つのサブスクリプションを購入し、両方とも一覧に表示されない場合** 、異なる組織 (異なるドメイン) 用に購入した可能性があります。 サブスクリプションは組織の境界を超えることはできません。

- **If you know you have an additional subscription,** and it's not listed here, or is not active, [call Microsoft support](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>古いライセンスの処理

現在のサブスクリプションのライセンスは後で削除されるので、それ以降は新しいユーザー ライセンスの料金のみを支払うことになります。

## <a name="step-4-reassign-licenses"></a>手順 4: ライセンスを再割り当てする

### <a name="reassign-a-license-for-one-user"></a>1 人のユーザーのライセンスを再割り当てする

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. [アクティブ **なユーザー]** ページで、ライセンスを割り当てるユーザーを選択します。

3. [ライセンス **とアプリ** ] タブで、[ **ライセンス**] を展開し、割り当てるライセンスのボックスを選択して、[変更の保存] **を選択します**。

### <a name="reassign-licenses-for-multiple-users-at-once"></a>複数のユーザーのライセンスを一度に再割り当てする

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. 既存のライセンスを置き換えるユーザーの名前の横にある円を選択します。

3. 上部にある [その他のオプション **(** **...]**) を選択し、[製品ライセンスの管理] **を選択します**。

4. Select **Replace existing product license assignments** \> **Next**.

5. これらのユーザーに割り当てる製品を [ **オン**] の位置に切り替えます。

    > [!TIP]
    > - ユーザーが使用できるサービスを制限するには、そのユーザーで削除するサービスを [ **オフ**] の位置に切り替えます。 たとえば、Skype for Business Online 以外のすべてのサービスにユーザーがアクセスできるようにするには、Skype for Business Online サービスを [ **オフ**] の位置に切り替えます。
    > - 選択したユーザーで以前に割り当てられたライセンスは削除されます。

6. [**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] の順に選択します。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>手順 5: サブスクリプションをキャンセルするか、不要になったライセンスを削除する (オプション)

1 つのサブスクリプションから別のサブスクリプションにすべてのユーザーを移動し、元のサブスクリプションが不要になった場合、[サブスクリプションをキャンセルする](cancel-your-subscription.md)ことができます。

一部のユーザーのみを別のサブスクリプションに移動した場合は、不要になった[ライセンスを削除](../licenses/remove-licenses-from-subscription.md)します。

## <a name="call-support-to-help-you-change-plans"></a>プランの変更に役立つサポートへのお電話
[Microsoft サポートに問い合わせください](../../admin/contact-support-for-business-products.md)
