---
title: カスタム ドメインを使うように電子メール アドレスを変更する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: '最初の電子メール アドレスを 、ユーザー設定のような使い tom@fourthcoffee.com。 これを行うには、ドメイン名を購入し、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: c7ded3712fa0f8894ae0b8b9d864a1a5a58e4558
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470991"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
::: moniker range="o365-worldwide"

Microsoft 365 の最初の電子メール アドレスには、次のような .onmicrosoft.com が含 tom@fourthcoffee.onmicrosoft.com。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-germany"

365 ドイツ 365 Officeの最初の電子メール アドレスには、次のような .onmicrosoft.de が tom@fourthcoffee.onmicrosoft.de。 このアドレスは、他のユーザーと同じフレンドリアドレス tom@fourthcoffee.de。 最初に使用するドメイン名など、独自の fourthcoffee.de があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet がOffice 365 の初期メール アドレスには、partner.onmschina.cn のような tom@fourthcoffee.partner.onmschina.cn。 このアドレスは、他のユーザーと同じフレンドリなアドレス tom@fourthcoffee.cn。 最初に使用するドメイン名など、独自の fourthcoffee.cn があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

ドメインのメールを Microsoft 365 に変更すると、セットアップ中にドメインの MX レコードを更新すると、そのドメインに送信されるメールはすべて Microsoft 365 に送信されます。 MX レコードを変更する前に、ドメインにメールを送信しているすべてのユーザーにユーザーを追加し、Microsoft 365 でメールボックスを作成してください。 ドメインのすべてのユーザーのメールを Microsoft 365 に移動したくない場合 代わりに、少数の電子メール アドレスで [Microsoft 365 をパイロットするための手順を実行できます](../misc/pilot-microsoft-365-from-my-custom-domain.md?view=o365-worldwide)。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してカスタム ドメインを使用するメール アドレスを変更する

これらの手順を実行するには、グローバル管理者アカウントが必要です。 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. で管理センターに移動します<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。 

::: moniker-end 

2. [セットアップ ドメイン **]**  >  **ページに移動** します。 

3. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。
    
4. 自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。
    
Microsoft 365 のドメインですべてが正しく設定されるようにガイドされます。

> [!NOTE]
> Exchange ライセンスを使用していない場合は、ドメインを使用して Microsoft 365 テナントからの電子メールの送受信を行う必要があります。
  
## <a name="related-articles"></a>関連記事

[Microsoft 365 を使用してカスタム ドメインを購入する](../get-help-with-domains/buy-a-domain-name.md)
