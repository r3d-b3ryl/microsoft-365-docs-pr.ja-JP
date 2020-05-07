---
title: カスタム ドメインを使うように電子メール アドレスを変更する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '最初の電子メールアドレスを、tom@fourthcoffee.com のようなわかりやすい電子メールアドレスに変更します。 これを行うには、ドメイン名を購入して、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: baa2e49d98ed1d7b3de9af78b84403d028b4c91d
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053826"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
::: moniker range="o365-worldwide"

Microsoft 365 の最初の電子メールアドレス onmicrosoft.com は、tom@fourthcoffee.onmicrosoft.com のようになります。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-germany"

Office 365 ドイツの最初の電子メールアドレスには、tom@fourthcoffee.onmicrosoft.de などの onmicrosoft.de が含まれています。 Tom@fourthcoffee.de のようなわかりやすいアドレスに変更することができます。 Fourthcoffee.de など、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet が運用している Office 365 の最初の電子メールアドレスには、tom@fourthcoffee.partner.onmschina.cn などの partner.onmschina.cn が含まれています。 Tom@fourthcoffee.cn のようなわかりやすいアドレスに変更することができます。 Fourthcoffee.cn など、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

セットアップ時にドメインの MX レコードを更新することによって、ドメインの電子メールを Microsoft 365 にするように変更すると、そのドメインに送信されるすべての電子メールが Microsoft 365 に送られ始めます。 MX レコードを変更する前に、自分のドメインに電子メールを持っているすべてのユーザーに対して、Microsoft 365 でユーザーを追加し、メールボックスを作成していることを確認してください。 ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくありませんか。 [代わりに、少数のメールアドレスを使用して Microsoft 365 をパイロット](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)処理する手順を実行することができます。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してカスタムドメインを使用するように電子メールアドレスを変更する

これらの手順を実行するには、グローバル管理者アカウントが必要です。 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. の管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>に移動します。 

::: moniker-end 

2. [**セットアップ** > **ドメイン**] ページに移動します。 

3. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。
    
4. 自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。
    
Microsoft 365 のドメインですべての設定を適切に設定するようにガイドされます。

> [!NOTE]
> Exchange ライセンスを使用していない場合、ドメインを使用して Microsoft 365 テナントからメールを送受信することはできません。
  
## <a name="related-articles"></a>関連記事

[Microsoft 365 を使用してカスタムドメインを購入する](../get-help-with-domains/buy-a-domain-name.md)
 
