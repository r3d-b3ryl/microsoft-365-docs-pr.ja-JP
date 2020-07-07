---
title: ドメインに関する FAQ
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: ドメインの詳細については、よく寄せられる質問への回答を検索してください。
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049738"
---
# <a name="domains-faq"></a>ドメイン FAQ

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

この記事では、Microsoft 365 のドメインに関してよく寄せられる質問に対する回答を示します。

質問の回答が見つからない場合は、コメントを残してお知らせください。ご質問を FAQ の一覧に追加します。

この記事の内容

[MX 優先度](#what-is-mx-priority) 
 とは[自分のドメインの SPF レコードを検証するにはどうすればよいですか?](#how-can-i-validate-spf-records-for-my-domain) 
[ドメイン名](#what-is-a-domain-name) 
 とは[DNS プロバイダーが特定のレコードの種類をサポートしていない場合はどうなりますか?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
[Microsoft 365 で既定のドメインを設定または変更するにはどうすればよいですか?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
[Microsoft 365 にカスタムサブドメインまたは複数のドメインを追加できますか。](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
["Onmicrosoft.com" ドメインがあるのはなぜですか?](#why-do-i-have-an-onmicrosoftcom-domain) 
["Onmicrosoft.de" ドメインがあるのはなぜですか?](#why-do-i-have-an-onmicrosoftde-domain) 
非[営利団体または教育機関の状態を確認するには](#how-do-i-verify-my-nonprofit-or-education-status)どうすればよいですか?
    
## <a name="what-is-mx-priority"></a>MX 優先度とは何ですか?

メールは最も小さい優先順位番号 (最高の優先順位) でメール交換サーバーに配信されるので、メールのルーティングに使用する MX レコードは、最も小さい優先順位番号 (通常は 0 または *高い*  優先順位) が指定されている必要があります。 
  
- MX レコードを作成するときには、ほとんどの DNS ホスティング プロバイダーで、優先度順位を設定する必要があります。
    
- ボックスのラベルは [ *優先度*  ] の場合もあれば、[  *優先順位*  ] の場合もあります。 
    
- 数値を要求される場合もあれば、[ *低*  ]、[  *中*  ]、または [  *高*  ] を選択するように要求される場合もあります。 
    
- MX レコードが 1 つだけの場合は、任意の値を優先順位に指定できます。
    
- 複数の MX レコードがある場合は、メールのルーティングの MX レコードがドメインを所有していることを検証するために使用されるレコードより高い優先度になっていることを確認します。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>SPF レコードはどうやって検証できますか?

**SPF の TXT レコードを1つだけ**持っているか作成しておくことが重要です。 既に SPF レコードがある場合は、新しい Microsoft 365 値を作成するのではなく、新しい Microsoft 値を追加する必要があります。 Microsoft メールの SPF レコードを追加または更新した後、次のいずれかのツールを使用して構文が正しいことを確認してください。 
  
- [SPF レコード テスト ツール](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig Web インターフェイス](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>ドメイン名とは何ですか?

A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.* 
  
Microsoft 365 で "**渡 \@ contoso.com**" のようなカスタムドメインを使用すると、ブランドの信頼性と認識を構築するのに役立ちます。 
  
[Microsoft 365 でドメインを購入し、自動的に設定](../get-help-with-domains/buy-a-domain-name.md)することも、ドメインレジストラーで購入したり、既に所有しているドメインを購入したりすることもできます。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>DNS プロバイダーで特定のレコードの種類がサポートされない場合はどうなりますか?

独自の DNS レコードを管理していて、DNS ホストが Microsoft 365 に必要なすべての DNS レコードをサポートしていない場合は、一部の Microsoft 365 機能が動作しません。 必要な DNS レコードをすべてサポートしているレジストラーにドメインを移行することをお勧めします。
  
すべての必須の DNS レコードをサポートするプロバイダー。
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Microsoft 365 で既定のドメインを設定または変更するにはどうすればよいですか?

既定のドメインを選択するには、少なくとも1つのカスタムドメインが Microsoft 365 に追加されている必要があります。

::: moniker range="o365-worldwide"

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
2. [**ドメイン**] ページで、新しいメール アドレスの既定として設定するドメインを選択します。 
    
3. [**既定に設定**] を選択します。
    
::: moniker range="o365-worldwide"

*.onmicrosoft.com* ドメインの最初の部分の名前を変更することはできません。 

::: moniker-end

::: moniker range="o365-germany"

*.onmicrosoft.de* ドメインの最初の部分の名前を変更することはできません。 

::: moniker-end

::: moniker range="o365-21vianet"

*.partner.onmschina.cn* ドメインの最初の部分の名前を変更することはできません。 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Microsoft 365 にカスタムサブドメインまたは複数のドメインを追加できますか。

::: moniker range="o365-worldwide"

はい。 サブドメインを追加するには、レジストラーの web サイトで独自の DNS 設定を管理する必要があります。 NS レコードでの DNS 設定の管理を行う場合や、Microsoft からドメインを購入した場合は、サブドメインを追加することはできません。

::: moniker-end

::: moniker range="o365-germany"

Yes! To add subdomains, you must manage your own DNS settings at your registrar's website. If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.

::: moniker-end

::: moniker range="o365-21vianet"

Yes! To add subdomains, you must manage your own DNS settings at your registrar's website. If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.

::: moniker-end

通常、Microsoft 365 サブスクリプションには最大900のドメインを追加できます。
  
例えば、contoso.com と contosomaketing.com の各ドメインを追加し、その後に www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com などのサブドメインを追加することができます。
  
サブドメインを追加すると、確認が行われる親ドメインでの確認に基づき、自動的に確認されます。
  
Microsoft 365 に複数のドメインを追加する場合は、追加した任意のドメインで任意のサービス (電子メールなど) をホストできます。  *電子メールを Microsoft 365 に変更すると、ドメインの MX レコードを更新すると、そのドメインに送信されるすべての電子メールが Microsoft 365 に送られ始めます。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Contoso.com ドメインを Microsoft 365 サブスクリプションに追加した場合は、他の Microsoft 365 組織にサブドメイン xyz.contoso.com を追加することもできます。 サブドメインを追加する際に、DNS ホスティングプロバイダーに TXT レコードを追加するように求めるメッセージが表示されます。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>"onmicrosoft.com" ドメインがあるのはなぜですか?

Microsoft 365 は、サービスにサインアップするときに、 *contoso.onmicrosoft.com*などのドメインを作成します。 サインアップ時に作成するユーザー ID には、 *alan@contoso.onmicrosoft.com*のようなドメインが含まれています。 
  
 ***Alan \@ contoso.com*のように電子メールを表示する場合**は[、ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、既に所有している場合は「[ユーザーとドメインを Microsoft 365 に追加](add-domain.md)する」の手順に従ってください。 
  
- **サインアップ後に onmicrosoft ドメインの名前は変更できません** 。 たとえば、選んだ初期ドメインが fourthcoffee.onmicrosoft.com の場合、fabrikam.onmicrosoft.com に変更することはできません。 別の onmicrosoft.com ドメインを使用するには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。 
    
- **You can't rename your team site URL.** Your team site URL is based on your onmicrosoft.com domain name. Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site. 
    
- **onmicrosoft ドメインは、削除できません。** Microsoft 365 は、サブスクリプションの背後で使用されているため、これを維持する必要があります。 カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。 
    
You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>"onmicrosoft.de" ドメインがあるのはなぜですか?

Microsoft 365 は、サービスにサインアップするときに、 *contoso.onmicrosoft.de*などのドメインを作成します。 サインアップ時に作成するユーザー ID には、 *alan@contoso.onmicrosoft.de*のようなドメインが含まれています。 
  
 ***Alan@contoso.de*のように電子メールを表示する場合**は[、ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、既に所有している場合は「[ユーザーとドメインを Microsoft 365 に追加](add-domain.md)する」の手順に従ってください。 
  
- **サインアップ後に onmicrosoft ドメインの名前は変更できません** 。 たとえば、選択した初期ドメインが fourthcoffee.onmicrosoft.de の場合、fabrikam.onmicrosoft.de に変更することはできません。 別の onmicrosoft.de ドメインを使用するには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。 
    
- **You can't rename your team site URL.** Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site. 
    
- **onmicrosoft ドメインは、削除できません。** Microsoft 365 は、サブスクリプションの背後で使用されているため、これを維持する必要があります。 カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。 
    
You can keep using the initial onmicrosoft.de domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>非営利団体または教育機関のステータスを確認するにはどうすればよいですか?

1. [管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-home)で [**セットアップ**] を選択してウィザードを開始します。 (必ず Microsoft 365 にサインインしてください)。 
    
2. 学校の管理者になるには、Microsoft 365 で [**管理者になる**] オプションを選択します。 
    
3. ドメインの DNS ホスト web サイトに TXT DNS レコードを追加するように求めるメッセージが表示されます。 それはなぜでしょうか。 DNS ホストでサインインし、ドメインのレコードを追加することにより、Microsoft 365 にドメイン名を所有していることを証明します。
    
4. レコードを追加した後、Microsoft 365 ポータルに戻り、追加されたことを確認して、Microsoft 365 で確認できるようにします。
    
非営利団体があり、Microsoft 365 を入手する必要がある場合 [組織に資格](https://www.microsoft.com/en-us/nonprofits/eligibility)があることを確認してから、サービスにサインアップしてください。 
  
学校の管理者になる方法の詳細については、 [こちらのヘルプ記事をご覧ください](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。