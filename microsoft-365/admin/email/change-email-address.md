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
description: '最初のメール アドレスを、メール アドレスのような使い方の良いメール アドレスにtom@fourthcoffee.com。 これを行うには、ドメイン名を購入し、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: d23c612eecae0a0b58d844fbbe25392ffa682fde
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656833"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
::: moniker range="o365-worldwide"

Microsoft 365 の最初のメール アドレスには、次のような .onmicrosoft.com が含tom@fourthcoffee.onmicrosoft.com。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-germany"

Office 365 Germany の最初のメール アドレスには、次のような .onmicrosoft.de が含tom@fourthcoffee.onmicrosoft.de。 このアドレスは、次のような分tom@fourthcoffee.de。 最初に作成したドメイン名など、独自のfourthcoffee.deがあります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet が運用している Office 365 の初期メール アドレスには、次のようなpartner.onmschina.cnが含tom@fourthcoffee.partner.onmschina.cn。 このアドレスは、次のような分tom@fourthcoffee.cn。 最初に作成したドメイン名など、独自のドメインfourthcoffee.cnがあります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

セットアップ中にドメインの MX レコードを更新して、ドメインの電子メールを Microsoft 365 に届く設定に変更すると、そのドメインに送信されたメールはすべて Microsoft 365 に届く開始されます。 MX レコードを変更する前に、ドメインにメールを持つすべてのユーザーのユーザーが追加され、Microsoft 365 にメールボックスが作成されている必要があります。 ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくない場合 You can take steps to [pilot Microsoft 365 with just a few email addresses instead.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してカスタム ドメインを使用するメール アドレスを変更する

これらの手順を実行するには、グローバル管理者アカウントが必要です。 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターに移動します<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。 

::: moniker-end 

2. [セットアップ ドメイン **]**  >  **ページに移動** します。 

3. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。
    
4. 自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。
    
Microsoft 365 でドメインに合った設定を正しく行うガイドが表示されます。

> [!NOTE]
> Exchange ライセンスを使用していない場合は、ドメインを使用して Microsoft 365 テナントからメールを送受信することはできません。
  
## <a name="related-articles"></a>関連記事

[Microsoft 365 を使用してカスタム ドメインを購入する](../get-help-with-domains/buy-a-domain-name.md)
 
