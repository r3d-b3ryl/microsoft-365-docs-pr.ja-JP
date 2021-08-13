---
title: ビジネス プランMicrosoft 365手動で変更する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: サブスクリプションを手動で変更するには、新しいサブスクリプションを購入し、両方のサブスクリプションがリストされアクティブに設定されます。
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: d8a084111ce2e0869332cdfa7fe438c314295d7a9044a0c715d065ff8c49544d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53802588"
---
# <a name="change-plans-manually"></a>手動でプランを変更する

## <a name="step-1-decide-how-to-change-plans"></a>手順 1: プランを変更する方法を決定する

すべてのユーザーをあるプランから別のプランに変更する最善の方法は、[ [アップグレード] タブを使用する方法です](upgrade-to-different-plan.md)。場合によっては、これは使用できない場合があります。 代わりに手動でプランを変更します。

- [アップグレード **] タブ** に現在のプランをアップグレードできないと示されている場合。

- [アップグレード] タブを **選択** すると、必要なプランが一覧に表示されません。

- すべてのユーザーを同じ方法でアップグレードしない場合。 一部の企業では、さまざまなユーザーを異なるプランに加入させる必要があります。 これには手動で変更を使用します。

手動で変更を続行するには、このトピックの [「手順 2: 新](#step-2-buy-a-new-subscription) しいサブスクリプションを購入する」を参照してください。

> [!IMPORTANT]
> データ関連サービスが現在のプラン (ダウングレード) よりも少ないプランに変更する場合は、保持するデータを手動でバックアップする必要があります。 詳細については、「計画を変更 [する前にデータをバックアップする」を参照してください](back-up-data-before-switching-plans.md)。

## <a name="step-2-buy-a-new-subscription"></a>手順 2: 新しいサブスクリプションを購入する

**既に購入済みですか?** ユーザーを移動するサブスクリプションが既にある場合は、この手順をスキップして、「手順 [3:](#step-3-check-your-new-subscription-and-licenses) このトピックの新しいサブスクリプションとライセンスを確認する」に進みます。

または

**新しいサブスクリプションとライセンスを購入します。**「ビジネス サブスクリプション用に別 [のMicrosoft 365を購入する」の](../try-or-buy-microsoft-365.md)手順に従って、新しいサブスクリプションを購入します。

必ずユーザーが現在所属している組織と同じ組織のサブスクリプションを購入してください。 たとえば、移動するユーザーのメール アドレスを確認します。 電子メール アドレスにメール アドレスが contoso.com 場合は、新しいサブスクリプションを購入する \@ 必要 contoso.com。
移動する各ユーザーのライセンスを含めます。

## <a name="step-3-check-your-new-subscription-and-licenses"></a>手順 3: 新しいサブスクリプションとライセンスを確認する

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。

2. **両方のサブスクリプションが一覧表示され、アクティブな状態を確認する** ユーザーを移動するサブスクリプションと、ユーザーを移動するサブスクリプションを一緒に一覧表示する必要があります。 最初に確認したときに新しいサブスクリプションが表示されない場合は、後でもう一度確認してみてください。 両方のサブスクリプションがアクティブな状態を確認します。 新しいサブスクリプションが一覧に表示されない、またはアクティブではない場合は[新しいサブスクリプションが一覧に表示されない、またはアクティブではない](#the-new-subscription-isnt-listed-or-isnt-active)を参照してください。

3. **ユーザーごとに十分なライセンスを持っているか確認する** 各ユーザーには、サブスクリプションに一致するライセンスが必要です。 したがって、10 人のユーザーを 10 人のユーザーに移動Microsoft 365 Business Premium、10 個のライセンスが使用可能なライセンスを使用できる必要があります。

4. **新しいサブスクリプションのライセンスが必要な場合**
   [製品] ページ **に移動し** 、その他 [のライセンスを購入します](../licenses/buy-licenses.md)。

> [古いライセンスの処理](#what-about-the-old-licenses)」を参照してください。

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>新しいサブスクリプションが一覧に表示されない、またはアクティブではない

- **2 つのサブスクリプションを購入し、両方とも一覧に表示されない場合** 、異なる組織 (異なるドメイン) 用に購入した可能性があります。 サブスクリプションは組織の境界を超えることはできません。

- **サブスクリプションが追加で、** ここに記載されていない場合、またはアクティブではない場合は [、Microsoft サポートにお問い合わせください](../../business-video/get-help-support.md)。

### <a name="what-about-the-old-licenses"></a>古いライセンスの処理

現在のサブスクリプションのライセンスは後で削除されるので、それ以降は新しいユーザー ライセンスの料金のみを支払うことになります。

## <a name="step-4-reassign-licenses"></a>手順 4: ライセンスの再割り当て

新しいプランからOffice 365プランMicrosoft 365、すべてのユーザーのライセンス割り当てを変更する必要があります。 手動でプランを変更した場合、ライセンスは自動的に割り当てされません。

### <a name="reassign-a-license-for-one-user"></a>1 人のユーザーのライセンスを再割り当てする

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. [アクティブ **ユーザー] ページ** で、ライセンスを割り当てるユーザーを選択します。

3. [ライセンス **とアプリ] タブ** で、[ **ライセンス**] を展開し、割り当てるライセンスのボックスを選択し、[変更の保存] **を選択します**。

### <a name="reassign-licenses-for-multiple-users-at-once"></a>複数のユーザーのライセンスを一度に再割り当てする

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. 既存のライセンスを置き換えるユーザーの名前の横にある円を選択します。

3. 上部で 3 つのドット (その他のアクション) を選択し、[製品ライセンスの管理 **] を選択します**。

4. Select **Replace existing product license assignments** \> **Next**.

5. これらのユーザーに割り当てる製品を [ **オン**] の位置に切り替えます。

    > [!TIP]
    > - ユーザーが使用できるサービスを制限するには、そのユーザーで削除するサービスを [ **オフ**] の位置に切り替えます。 たとえば、Skype for Business Online 以外のすべてのサービスにユーザーがアクセスできるようにするには、Skype for Business Online サービスを [ **オフ**] の位置に切り替えます。
    > - 選択したユーザーで以前に割り当てられたライセンスは削除されます。

6. [**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] の順に選択します。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>手順 5: サブスクリプションをキャンセルするか、不要になったライセンスを削除する (オプション)

1 つのサブスクリプションから別のサブスクリプションにすべてのユーザーを移動し、元のサブスクリプションが不要になった場合、[サブスクリプションをキャンセルする](cancel-your-subscription.md)ことができます。

一部のユーザーのみを別のサブスクリプションに移動した場合は、不要になった[ライセンスを削除](../licenses/buy-licenses.md)します。

## <a name="call-support-to-help-you-change-plans"></a>プランの変更に役立つサポートを呼び出す
[Microsoft サポートへのお問い合わせください](../../business-video/get-help-support.md)
