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
description: ドメイン名を購入してMicrosoft 365に追加して、メールアドレスを tom@fourthcoffee.com などのわかりやすいメールアドレスに変更します。
ms.openlocfilehash: d5e70856c9200cd7e5df0eded25b6ff460e5d1fe
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572095"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
::: moniker range="o365-worldwide"

Microsoft 365の最初のメールアドレスには、tom@fourthcoffee.onmicrosoft.com などの .onmicrosoft.com が含まれています。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-germany"

ドイツでの最初のメールアドレス Office 365には、tom@fourthcoffee.onmicrosoft.de など、.onmicrosoft.de が含まれています。 tom@fourthcoffee.de のような親しみやすいアドレスに変更できます。 最初に fourthcoffee.de のように、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet が運営するOffice 365の最初のメールアドレスには、tom@fourthcoffee.partner.onmschina.cn などの partner.onmschina.cn が含まれています。 tom@fourthcoffee.cn のような親しみやすいアドレスに変更できます。 最初に fourthcoffee.cn のように、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

ドメインのメールを変更してMicrosoft 365に入ると、セットアップ中にドメインの MX レコードを更新すると、そのドメインに送信されるすべてのメールがMicrosoft 365に送信されます。 MX レコードを変更する前に、ドメインに電子メールを持っているすべてのユーザーに対して、ユーザーを追加し、メールボックスを作成Microsoft 365確認してください。 ドメインの全員のメールをMicrosoft 365に移動したくないですか? [代わりに、少数の電子メール アドレスでMicrosoft 365をパイロット](../misc/pilot-microsoft-365-from-my-custom-domain.md)する手順を実行できます。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365管理センターを使用してカスタム ドメインを使用するようにメール アドレスを変更する

これらの手順を実行するには、グローバル管理者アカウントが必要です。 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. の管理センターに<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>移動します。 

::: moniker-end 

2. **[セットアップ**  >  **ドメイン]** ページに移動します。 

3. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。
    
4. 自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。
    
Microsoft 365でドメインで正しく設定する方法を案内します。

> [!NOTE]
> Exchangeライセンスを使用していない場合、ドメインを使用してMicrosoft 365テナントからメールを送受信することはできません。
  
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365を使用してカスタム ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)する (記事)
