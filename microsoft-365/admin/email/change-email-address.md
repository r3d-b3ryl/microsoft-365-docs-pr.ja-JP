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
description: ドメイン名を購入してMicrosoft 365に追加することで、メール アドレスを tom@fourthcoffee.com などのわかりやすいメール アドレスに変更します。
ms.openlocfilehash: 4630b3df4719611440e92801235fde20d7bd95f4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316423"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
::: moniker range="o365-worldwide"

Microsoft 365の最初のメール アドレスには、tom@fourthcoffee.onmicrosoft.com などの .onmicrosoft.com が含まれます。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet によって運用されているOffice 365の最初のメール アドレスには、tom@fourthcoffee.partner.onmschina.cn などの partner.onmschina.cn が含まれます。 tom@fourthcoffee.cn のようなフレンドリアドレスに変更できます。 最初に fourthcoffee.cn のように、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

ドメインのメールをMicrosoft 365に変更すると、セットアップ中にドメインの MX レコードを更新すると、そのドメインに送信されたすべての電子メールがMicrosoft 365に送信されます。 MX レコードを変更する前に、ドメインに電子メールを持っているすべてのユーザーに対して、Microsoft 365にユーザーを追加し、メールボックスを作成したことを確認します。 ドメイン内のすべてのユーザーのメールをMicrosoft 365に移動したくない場合 [代わりに、少数の電子メール アドレスでMicrosoft 365をパイロット](../misc/pilot-microsoft-365-from-my-custom-domain.md)する手順を実行できます。
  
## <a name="set-up-business-email-with-a-new-domain"></a>新しいドメインを使用してビジネス メールを設定する

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

5. **UsersActive** >  ユーザーに移動 **します**。

6. ユーザー名を編集するユーザーを選択し、追加したドメインに変更します。

> [!NOTE]
> Exchange ライセンスを使用していない場合は、ドメインを使用して、Microsoft 365 テナントから電子メールを送受信することはできません。
  
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365を使用してカスタム ドメインを購入する](../get-help-with-domains/buy-a-domain-name.md) (記事)\
[ドメインの管理](/admin) (リンク ページ)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)