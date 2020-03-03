---
title: 一般法人向け Office 365 プランを手動で切り替える
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
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: eb0d0680-5677-41a0-8c46-4b9d47f1c209
ROBOTS: NOINDEX
description: 新しいサブスクリプションを購入し、両方のサブスクリプションが一覧表示され、アクティブであることを確認して、Office 365 for business サブスクリプションを手動で切り替えます。
ms.openlocfilehash: 19efd94f320fcf5dc54f44b70b436f713a663a40
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354710"
---
# <a name="switch-office-365-for-business-plans-manually"></a>一般法人向け Office 365 プランを手動で切り替える

::: moniker range="o365-worldwide"
> [!NOTE]
> この記事は、古い管理センターに適用されます。 新しい管理センターに関する記事を表示するには、「[プランを手動で変更](change-plans-manually.md)する」を参照してください。 新しい管理センターは、Microsoft 365 のすべての管理者が利用でき、ホームページの上部にある [**新しい管理センター**の切り替え] を選択して選択することができます。 詳細については、「[新しい Microsoft 365 管理センターについて](../../admin/microsoft-365-admin-center-preview.md)」を参照してください。
::: moniker-end

## <a name="step-1-decide-how-to-switch-plans"></a>手順 1: プランを切り替える方法を決定する

すべてのユーザーを1つのプランから別のプランに切り替えるには、[[プランの切り替え] ボタン](switch-to-a-different-plan.md#use-the-switch-plans-button)を使用するのが最善の方法です。 この方法は使用できない場合があります。 代わりに、手動で切り替えます。
  
- [ **プランの切り替え**] ボタンがない。

- [**プランの切り替え**] ボタンを選択すると、必要なプランが一覧に表示されません。

- すべてのユーザーを同じ方法で切り替えたくない場合。 一部の企業では、さまざまなユーザーを異なるプランに加入させる必要があります。 このためには、手動で切り替えます。

手動スイッチを続行するには、このトピックの「[手順 2: 新しいサブスクリプションを購入](#step-2-buy-a-new-subscription)する」を参照してください。
  
## <a name="step-2-buy-a-new-subscription"></a>手順 2: 新しいサブスクリプションを購入する

 **購入済みですか?** ユーザーを移動するサブスクリプションが既にある場合は、この手順を省略して、このトピックの「[新しいサブスクリプションとライセンスを確認](#step-3-check-your-new-subscription-and-licenses)する」に進みます。
  
- または
  
 **新しいサブスクリプションとライセンスを購入する:** 「 [別の一般法人向け Office 365 を購入する](../buy-another-subscription.md)」の手順に従って新しいサブスクリプションを購入します。
  
必ずユーザーが現在所属している組織と同じ組織のサブスクリプションを購入してください。 たとえば、移動するユーザーの電子メールアドレスを確認します。 そのメール アドレスに @contoso.com が含まれている場合、contoso.com の新しいサブスクリプションを購入する必要があります。 移動する各ユーザーのライセンスを含めます。
  
 **プランの選択についてサポートが必要な場合**は、「 [Office 365 for business 製品の比較](https://go.microsoft.com/fwlink/p/?linkid=842056)ページ」または「サポートへのお[問い合わせ](../../admin/contact-support-for-business-products.md)」を参照してください。
  
## <a name="step-3-check-your-new-subscription-and-licenses"></a>手順 3: 新しいサブスクリプションとライセンスを確認する

1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[サブスクリプション]</a> ページに移動します。

    Office 365 Germany を使用している場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[サブスクリプション]</a> ページに移動します。

    21Vianet が運営する Office 365 を使用している場合は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。

2. **両方のサブスクリプションが一覧表示され、アクティブであることを確認する**

    ユーザーの移動元のサブスクリプションと移動先のサブスクリプションが共に一覧表示されている必要があります。最初に確認したときに新しいサブスクリプションが表示されない場合は、後でもう一度確認してみてください。両方のサブスクリプションが [ **アクティブ**] に一覧表示されていることを確認します。新しいサブスクリプションが一覧に表示されない、またはアクティブではない場合は[新しいサブスクリプションが一覧に表示されない、またはアクティブではない](#the-new-subscription-isnt-listed-or-isnt-active)を参照してください。

   **新しい一般法人向け Office 365 サブスクリプションと使用可能なライセンス数**

    ![The subscription page showing the number of licenses for the new subscription.](../../media/65a73e96-7c95-4daa-b6ec-71a4bf74dda5.png)
  
3. **各ユーザーに割り当てる十分な数のライセンスがあることを確認する**

    各ユーザーには、サブスクリプションと一致するライセンスが必要です。このため、10 ユーザーを Office 365 Enterprise E5 に移動する場合は、10 個のライセンスが使用可能であることを確認する必要があります。この画像では、Office 365 Enterprise E5 用の 10 個のライセンスが購入されており、その 10 個すべてのライセンスが割り当て可能です。

4. **新しいサブスクリプションのライセンスがさらに必要ですか?** [**サブスクリプション**] ページに移動し、 [Office 365 for business サブスクリプションのライセンスを購入](../licenses/buy-licenses.md)します。
  
    [古いライセンスの処理](#what-about-the-old-licenses)」を参照してください。

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>新しいサブスクリプションが一覧に表示されない、またはアクティブではない

- **サブスクリプションを請求書で購入し** 、与信審査が必要な場合、サブスクリプションが使用可能になるまで最長 2 営業日かかる可能性があります。

- **2 つのサブスクリプションを購入し、両方とも一覧に表示されない場合** 、異なる組織 (異なるドメイン) 用に購入した可能性があります。サブスクリプションは組織の境界を超えることはできません。

- **追加のサブスクリプションがあることがわかっ**ており、ここにリストされていない場合、または [**アクティブ**] の下にリストされていない場合は、[サポート] を[呼び出し](../../admin/contact-support-for-business-products.md)ます。

### <a name="what-about-the-old-licenses"></a>古いライセンスの処理

現在のサブスクリプションのライセンスは後で削除されるので、それ以降は新しいユーザー ライセンスの料金のみを支払うことになります。
  
## <a name="step-4-reassign-licenses"></a>手順 4: ライセンスを再割り当てする

### <a name="reassign-a-license-for-one-user"></a>1 人のユーザーのライセンスを再割り当てする

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

    Office 365 Germany を使用している場合は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブ ユーザー</a>] ページに移動します。

    21Vianet が運営する Office 365 を使用している場合は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブ ユーザー</a>] ページに移動します。

2. [ **アクティブなユーザー**] ページで、ライセンスを割り当てるユーザーの名前の横にあるボックスをオンにします。

3. 右側の [**製品ライセンス**] 行で、[**編集**] を選択します。

4. [ **製品のライセンス**] ウィンドウで、このユーザーに割り当てるライセンスを [ **オン**] の位置に切り替えます。既定では、そのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。

    > [!TIP]
    > ユーザーが使用できるサービスを制限するには、そのユーザーで削除するサービスを [ **オフ**] の位置に切り替えます。たとえば、Skype for Business Online 以外のすべてのサービスにユーザーがアクセスできるようにするには、Skype for Business Online サービスを [ **オフ**] の位置に切り替えます。
  
    ![Setting license assignments for a user.](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
5. このユーザーが不要になったライセンスを**オフ**の位置に切り替えます。

6. [**製品ライセンス**] ウィンドウの下部で、 **[クローズクローズ** \>を**割り当てる** \> ] を選択**します。**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>複数のユーザーのライセンスを一度に再割り当てする

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a> ] ページに移動するか、[ \> **アクティブな**ユーザー]**を選択し**ます。

    Office 365 Germany を使用している場合は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブ ユーザー</a>] ページに移動します。

    21Vianet が運営する Office 365 を使用している場合は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブ ユーザー</a>] ページに移動します。

2. 既存のライセンスを置き換えるユーザー名の横のチェック ボックスをオンにします。

3. [ **一括処理**] ウィンドウで、[ **製品ライセンスの編集**] を選択します。

4. [ **製品の割り当て**] ウィンドウで、[ **既存の製品ライセンス割り当てを置き換える**] \> [ **次へ**] の順に選択します。

5. これらのユーザーに割り当てる製品を [ **オン**] の位置に切り替えます。

    > [!TIP]
    > - ユーザーが使用できるサービスを制限するには、そのユーザーで削除するサービスを [ **オフ**] の位置に切り替えます。 たとえば、Skype for Business Online 以外のすべてのサービスにユーザーがアクセスできるようにするには、Skype for Business Online サービスを [ **オフ**] の位置に切り替えます。
    > - 選択したユーザーで以前に割り当てられたライセンスは削除されます。
  
    ![Setting license assignments for a user.](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
6. [ **既存の製品を置き換える** ] ウィンドウの下部で、[ **置換**] \> [ **閉じる**] の順に選択します。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>手順 5: サブスクリプションをキャンセルするか、不要になったライセンスを削除する (オプション)

1 つのサブスクリプションから別のサブスクリプションにすべてのユーザーを移動し、元のサブスクリプションが不要になった場合、[サブスクリプションをキャンセルする](cancel-your-subscription.md)ことができます。
  
一部のユーザーのみを別のサブスクリプションに移動した場合は、不要になった[ライセンスを削除](../licenses/remove-licenses-from-subscription.md)します。
  
## <a name="call-support-to-help-you-switch-plans"></a>プランの切り替えを支援するサポートに問い合わせる

[電話でのお問い合わせ](../../admin/contact-support-for-business-products.md)