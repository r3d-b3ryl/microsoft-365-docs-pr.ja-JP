---
title: カスタム ドメインを使うように電子メール アドレスを変更する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: ドメイン名を購入して Microsoft 365 に追加することで、メール アドレスを tom@fourthcoffee.com のようなわかりやすいメール アドレスに変更します。
ms.openlocfilehash: 2c6085ee9c951b9afb3d44460bfd613b63375986
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66602428"
---
# <a name="change-your-microsoft-365-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使用するように Microsoft 365 のメール アドレスを変更する

YouTube の [Microsoft 365 小規模ビジネス ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
::: moniker range="o365-worldwide"

Microsoft 365 の最初のメール アドレスには、tom@fourthcoffee.onmicrosoft.com などの .onmicrosoft.com が含まれています。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet によって運用されているOffice 365の最初のメール アドレスには、tom@fourthcoffee.partner.onmschina.cn などの partner.onmschina.cn が含まれます。 tom@fourthcoffee.cn のようなフレンドリアドレスに変更できます。 最初に fourthcoffee.cn のように、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

ドメインのメールを Microsoft 365 に送信するように変更すると、セットアップ中にドメインの MX レコードを更新すると、そのドメインに送信されたすべてのメールが Microsoft 365 に送信されます。 MX レコードを変更する前に、ドメインにメールを持っているすべてのユーザーに対して、Microsoft 365 でユーザーを追加し、メールボックスを作成したことを確認します。 ドメイン内のすべてのユーザーのメールを Microsoft 365 に移動したくない場合 [代わりに、少数の電子メール アドレスを使用して Microsoft 365 をパイロット](../misc/pilot-microsoft-365-from-my-custom-domain.md)する手順を実行できます。
  
## <a name="set-up-business-email-with-a-new-domain"></a>新しいドメインを使用してビジネス メールを設定する

[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2198215)で、このビデオや他の動画を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA?autoplay=false]

メールアドレス用に新しいドメイン名を購入し、Microsoft 365 でメールアドレスを設定します。

1. 新しいドメイン名の連絡先情報を入力してメールアドレス用の新しいドメイン名を購入し、支払方法を選択してから注文します。
1. アドレスの最初の部分 (＠マークの前) を変更するか、そのままにします。 
1. Microsoft 365 からサインアウトして、新しいメールアドレスでもう一度サインインします。 従業員のメールアドレスが新しいドメインで更新されます。 

## <a name="set-up-business-email-with-an-existing-domain"></a>既存のドメインを使用してビジネス メールを設定する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxApu?autoplay=false]

既に所有しているドメイン名を、Web サイト アドレスや他のプロバイダーのメール アドレスに使用します。

1. ドメインをホストしている Web サイトにサインインします。 ボタンをクリックして自動的に確認するか、手動でドメインを更新することができます。 
1. メールアドレスをカスタマイズするか、そのままにします。
1. Microsoft 365 からサインアウトして、新しいメールアドレスでもう一度サインインします。 従業員のメールアドレスが新しいドメインで更新されます。

## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してカスタム ドメインを使用するようにメール アドレスを変更する

これらの手順を実行するには、グローバル管理者である必要があります。

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターに移動します<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>。

::: moniker-end

2. **[セットアップ]** > **[ドメイン]** ページの順に移動します。

3. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。

4. 手順に従って、ドメインを所有していることを確認します。 Microsoft 365 でドメインを正しくセットアップするすべての手順が表示されます。

5. **[ユーザー****のアクティブユーザー]** >  に移動します。

6. ユーザー名を編集するユーザーを選択し、追加したドメインに変更します。

> [!NOTE]
> Exchange ライセンスを使用していない場合、ドメインを使用して Microsoft 365 テナントから電子メールを送受信することはできません。
  
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 を使用してカスタム ドメインを購入](../get-help-with-domains/buy-a-domain-name.md) する (記事)\
[ドメインの管理](/admin) (リンク ページ)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)