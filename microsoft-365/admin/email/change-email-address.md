---
title: カスタム ドメインを使うように電子メール アドレスを変更する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: '最初の電子メールアドレスを、tom@fourthcoffee.com のようなわかりやすい電子メールアドレスに変更します。 これを行うには、ドメイン名を購入して、Office 365 に追加する必要があります。 '
ms.openlocfilehash: 1c3c77f9626cdf292e0fb9400070cef3df05a9d6
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115978"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
::: moniker range="o365-worldwide"

Office 365 の最初のメール アドレスには tom@fourthcoffee.onmicrosoft.com のように .onmicrosoft.com が含まれます。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。既に持っている場合は、それをご利用いただけます。持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-germany"

Office 365 ドイツの最初の電子メールアドレスには、tom@fourthcoffee.onmicrosoft.de などの onmicrosoft.de が含まれています。 Tom@fourthcoffee.de のようなわかりやすいアドレスに変更することができます。 Fourthcoffee.de など、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet が運用している Office 365 の最初の電子メールアドレスには、tom@fourthcoffee.partner.onmschina.cn などの partner.onmschina.cn が含まれています。 Tom@fourthcoffee.cn のようなわかりやすいアドレスに変更することができます。 Fourthcoffee.cn など、独自のドメイン名が必要になります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

セットアップ中にドメインの MX レコードを更新することによって、ドメインのメールが Office 365 に届くように変更すると、そのドメインに送信されたすべてのメールが Office 365 に送信されるようなります。MX レコードを変更する前に、ドメインにメールを持つすべてのユーザーを Office 365 に追加し、メールボックスを作成したことを確認してください。ドメインのすべてのユーザーのメールを Office 365 に移動したくない場合は、[代わりに、少数のメール アドレスで Office 365 を試験運用する](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)手順を実行します。
  
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
    
Office 365 でドメインを正しくセットアップするすべての手順が表示されます。

> [!NOTE]
> Exchange ライセンスを使用していない場合は、ドメインを使用して Office 365 テナントからメールを送受信することはできません。
  
## <a name="related-articles"></a>関連記事

[Office 365 を使用したドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)
 
