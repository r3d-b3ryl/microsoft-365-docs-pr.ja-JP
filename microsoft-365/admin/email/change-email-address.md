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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '最初のメール アドレスを設定したメール アドレスのわかりやすいメール アドレス (たとえばtom@fourthcoffee.com。 これを行うには、ドメイン名を購入して、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: dc6d418961fe29a363aa6a787d8c0bb2d11d7e97
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814482"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
::: moniker range="o365-worldwide"

Microsoft 365 の初期メール アドレスには、.onmicrosoft.com、たとえばクライアントtom@fourthcoffee.onmicrosoft.com。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-germany"

Office 365 Germany の最初のメール アドレスには、.onmicrosoft.de など .onmicrosoft.de が含tom@fourthcoffee.onmicrosoft.de。 このアドレスを、使用するドメインシリアのアドレスtom@fourthcoffee.de。 最初のドメイン名など、独自のドメインfourthcoffee.deがあります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

Office 365 が運用している Office 365 の最初の電子メール アドレスには、次のようなpartner.onmschina.cnが含tom@fourthcoffee.partner.onmschina.cn。 このパラメーターは、メッセージを作成したいなどのわかりやすいアドレスtom@fourthcoffee.cn。 最初に、自分のドメイン名 (たとえば、最初fourthcoffee.cn必要です。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

セットアップ中にドメインの MX レコードを更新して、ドメインのメールを Microsoft 365 に移行すると、そのドメインに送信されたすべてのメールが Microsoft 365 に送信されるされるはずです。 MX レコードを変更する前に、ドメインにメールを持つすべてのユーザーについて、Microsoft 365 にユーザーを追加してメールボックスを作成したことを確認してください。 ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくない場合 代わりに、少数のメール [アドレスで Microsoft 365 をパイロット運用する手順を実行できます](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用して、カスタム ドメインを使うメール アドレスを変更する

これらの手順を実行するには、全体管理者アカウントが必要です。 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>admin center at. 

::: moniker-end 

2. [セットアップ ドメイン]**ページ**  >  **に移動**します。 

3. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。
    
4. 自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。
    
すべてのドメインを Microsoft 365 で正しくセットアップするガイドが表示されます。

> [!NOTE]
> Exchange ライセンスを使用していない場合は、そのドメインを使用して Microsoft 365 テナントの電子メールを送受信することはできません。
  
## <a name="related-articles"></a>関連記事

[Microsoft 365 を使用したカスタム ドメインの購入](../get-help-with-domains/buy-a-domain-name.md)
 
