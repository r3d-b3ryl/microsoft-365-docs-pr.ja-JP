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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: ドメイン名を購入し、ドメイン名に追加して、tom@fourthcoffee.com のような使いMicrosoft 365。
ms.openlocfilehash: a24a6b2f488f98d5a372be23ab3397d2854c56cb1b6ac75d9b229baf2365bc72
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53832759"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>カスタム ドメインを使うように電子メール アドレスを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
::: moniker range="o365-worldwide"

ユーザーの初期メール アドレスには、Microsoft 365のような .onmicrosoft.com が含 tom@fourthcoffee.onmicrosoft.com。 これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。 このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-germany"

ドイツの最初の電子メール Office 365には、次のような .onmicrosoft.de が含 tom@fourthcoffee.onmicrosoft.de。 このアドレスは、他のユーザーと同じフレンドリアドレス tom@fourthcoffee.de。 最初に使用するドメイン名など、独自の fourthcoffee.de があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet Office 365の初期メール アドレスには、partner.onmschina.cn のような tom@fourthcoffee.partner.onmschina.cn。 このアドレスは、他のユーザーと同じフレンドリなアドレス tom@fourthcoffee.cn。 最初に使用するドメイン名など、独自の fourthcoffee.cn があります。 既に持っている場合は、それをご利用いただけます。 持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。

::: moniker-end

ドメインのメールを Microsoft 365 に変更すると、セットアップ中にドメインの MX レコードを更新すると、そのドメインに送信されたメールはすべて Microsoft 365 に送信されます。 MX レコードを変更する前に、ドメインに電子メールを持Microsoft 365ユーザーと作成したメールボックスをユーザーに追加し、メールボックスを作成してください。 ドメイン上のすべてのユーザーのメールをメールに移動Microsoft 365? 代わりに、いくつかの電子メール[アドレスMicrosoft 365をパイロットする手順を実行できます](../misc/pilot-microsoft-365-from-my-custom-domain.md)。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>ユーザー設定を使用してカスタム ドメインを使用するメール アドレスを変更Microsoft 365 管理センター

これらの手順を実行するには、グローバル管理者である必要があります。

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. で管理センターに移動します<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。

::: moniker-end

2. [セットアップ ドメイン **]**  >  **ページに移動** します。

3. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。

4. 手順に従って、ドメインを所有している必要があります。 すべての設定がドメインに正しく設定されるようにガイドが表示Microsoft 365。

5. [ユーザー] **[アクティブ**  >  **なユーザー] に移動します**。

6. ユーザー名を編集するユーザーを選択し、追加したドメインに変更します。

> [!NOTE]
> ドメイン ライセンスを使用していないExchangeドメインを使用して、ドメインのテナントから電子メールを送受信Microsoft 365できません。
  
## <a name="related-content"></a>関連コンテンツ

[カスタム ドメインを購入するには、Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (記事)\
[ドメインの管理](../get-help-with-domains/index.yml) (リンク ページ)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)