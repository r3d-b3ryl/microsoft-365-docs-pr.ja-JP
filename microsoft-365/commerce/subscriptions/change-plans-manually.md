---
title: ビジネス プランの Microsoft 365 を手動で変更する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: nalinkla, jmueller
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
search.appverid: MET150
description: サブスクリプションを手動で変更するには、新しいサブスクリプションを購入し、両方のサブスクリプションが一覧表示され、アクティブであることを確認します。
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: f9e1a6eed45da6a125917a3ba6b181537248c9c6
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67322939"
---
# <a name="manually-change-microsoft-plans"></a>Microsoft プランを手動で変更する

## <a name="step-1-decide-how-to-change-plans"></a>手順 1: プランを変更する方法を決定する

すべてのユーザーを 1 つのプランから別のプランに変更する最善の方法は [、[アップグレード] タブを使用することです](upgrade-to-different-plan.md)。これは不可能な場合があります。 代わりに手動でプランを変更します。

- [ **アップグレード** ] タブに現在のプランをアップグレードできないことが示されている場合。

- [ **アップグレード** ] タブを選択した場合、目的のプランが一覧表示されません。

- すべてのユーザーを同じ方法でアップグレードしたくない場合。 一部の企業では、さまざまなユーザーを異なるプランに加入させる必要があります。 このために手動の変更を使用します。

手動による変更を続行するには、このトピックの [「手順 2: 新しいサブスクリプションを購入する](#step-2-buy-a-new-subscription) 」を参照してください。

> [!IMPORTANT]
> 現在のプランよりもデータ関連サービスが少ないプランに変更する (ダウングレード) 場合は、保持するデータを手動でバックアップする必要があります。 詳細については、「 [プランを変更する前にデータをバックアップする](move-users-different-subscription.md)」を参照してください。

## <a name="step-2-buy-a-new-subscription"></a>手順 2: 新しいサブスクリプションを購入する

**既に購入済みですか?** ユーザーを移動するサブスクリプションが既にある場合は、この手順をスキップし、 [手順 3: このトピックの新しいサブスクリプションとライセンスを確認してください](#step-3-check-your-new-subscription-and-licenses) 。

または

**新しいサブスクリプションとライセンスを購入します。** 「 [別の Microsoft 365 for Business サブスクリプションを購入](../try-or-buy-microsoft-365.md) する」の手順に従って、新しいサブスクリプションを購入します。

必ずユーザーが現在所属している組織と同じ組織のサブスクリプションを購入してください。 たとえば、移動するユーザーのメール アドレスを確認します。 電子メール アドレスに contoso.com が含まれている \@場合は、contoso.com の新しいサブスクリプションを購入する必要があります。
移動する各ユーザーのライセンスを含めます。

## <a name="step-3-check-your-new-subscription-and-licenses"></a>手順 3: 新しいサブスクリプションとライセンスを確認する

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

2. **両方のサブスクリプションが一覧表示され、アクティブであることを確認** するユーザーの移動元のサブスクリプションと、ユーザーを移動するサブスクリプションを一緒に表示する必要があります。 最初に確認したときに新しいサブスクリプションが表示されない場合は、後でもう一度確認してみてください。 両方のサブスクリプションがアクティブであることを確認します。 新しいサブスクリプションが一覧に表示されない、またはアクティブではない場合は[新しいサブスクリプションが一覧に表示されない、またはアクティブではない](#the-new-subscription-isnt-listed-or-isnt-active)を参照してください。

3. **各ユーザーに十分なライセンスがあることを確認** する各ユーザーには、サブスクリプションに一致するライセンスが必要です。 そのため、10 人のユーザーをMicrosoft 365 Business Premiumに移動する場合は、10 個のライセンスが使用可能であることを確認する必要があります。

4. **新しいサブスクリプションに対してさらにライセンスが必要ですか?**
   **[製品**] ページに移動し、[さらにライセンスを購入します](../licenses/buy-licenses.md)。

> [古いライセンスの処理](#what-about-the-old-licenses)」を参照してください。

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>新しいサブスクリプションが一覧に表示されない、またはアクティブではない

- **2 つのサブスクリプションを購入し、両方とも一覧に表示されない場合** 、異なる組織 (異なるドメイン) 用に購入した可能性があります。 サブスクリプションは組織の境界を超えることはできません。

- **追加のサブスクリプションがあり**、ここに記載されていない、またはアクティブでないことがわかっている場合は、 [Microsoft サポートにお問い合わせください](../../admin/get-help-support.md)。

### <a name="what-about-the-old-licenses"></a>古いライセンスの処理

現在のサブスクリプションのライセンスは後で削除されるので、それ以降は新しいユーザー ライセンスの料金のみを支払うことになります。

## <a name="step-4-reassign-licenses"></a>手順 4: ライセンスを再割り当てする

Office 365 プランから Microsoft 365 プランにアップグレードする場合は、すべてのユーザーのライセンス割り当てを変更する必要があります。 手動でプランを変更しても、ライセンスは自動的に割り当てられません。

### <a name="reassign-a-license-for-one-user"></a>1 人のユーザーのライセンスを再割り当てする

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. [ **アクティブなユーザー** ] ページで、ライセンスを割り当てるユーザーを選択します。

3. [ **ライセンスとアプリ** ] タブで、[ **ライセンス**] を展開し、割り当てるライセンスのボックスを選択し、[ **変更の保存**] を選択します。

### <a name="reassign-licenses-for-multiple-users-at-once"></a>複数のユーザーのライセンスを一度に再割り当てする

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. 既存のライセンスを置き換えるユーザーの名前の横にある円を選択します。

3. 上部にある 3 つのドット (その他のアクション) を選択し、[ **製品ライセンスの管理**] を選択します。

4. Select **Replace existing product license assignments** \> **Next**.

5. これらのユーザーに割り当てる製品を [ **オン**] の位置に切り替えます。

    > [!TIP]
    > - ユーザーが使用できるサービスを制限するには、そのユーザーで削除するサービスを [ **オフ**] の位置に切り替えます。 たとえば、Skype for Business Online 以外のすべてのサービスにユーザーがアクセスできるようにするには、Skype for Business Online サービスを [ **オフ**] の位置に切り替えます。
    > - 選択したユーザーで以前に割り当てられたライセンスは削除されます。

6. [**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] の順に選択します。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>手順 5: サブスクリプションを取り消すか、不要になったライセンスを削除する (省略可能)

1 つのサブスクリプションから別のサブスクリプションにすべてのユーザーを移動し、元のサブスクリプションが不要になった場合、[サブスクリプションをキャンセルする](cancel-your-subscription.md)ことができます。

一部のユーザーのみを別のサブスクリプションに移動した場合は、不要になった[ライセンスを削除](../licenses/buy-licenses.md)します。

## <a name="call-support-to-help-you-change-plans"></a>プランの変更に役立つサポートを呼び出す

[Microsoft サポートに電話でお問い合わせください](../../admin/get-help-support.md)。
