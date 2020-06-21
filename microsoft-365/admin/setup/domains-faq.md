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
description: ドメインの詳細については、よく寄せられる質問の回答を参照してください。
ms.openlocfilehash: a52513130f9bbbf7c4cd25d4c4827e833700d992
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739154"
---
# <a name="domains-faq"></a>ドメイン FAQ

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

この記事では、Office 365 のドメインに関してよく寄せられる質問にお答えします。

質問の回答が見つからない場合は、コメントを残してお知らせください。ご質問を FAQ の一覧に追加します。
    
## <a name="what-is-mx-priority"></a>MX 優先度とは何ですか?

メールは最も小さい優先順位番号 (最高の優先順位) でメール交換サーバーに配信されるので、メールのルーティングに使用する MX レコードは、最も小さい優先順位番号 (通常は 0 または *高い*  優先順位) が指定されている必要があります。 
  
- MX レコードを作成するときには、ほとんどの DNS ホスティング プロバイダーで、優先度順位を設定する必要があります。
    
- ボックスのラベルは [ *優先度*  ] の場合もあれば、[  *優先順位*  ] の場合もあります。 
    
- 数値を要求される場合もあれば、[ *低*  ]、[  *中*  ]、または [  *高*  ] を選択するように要求される場合もあります。 
    
- MX レコードが 1 つだけの場合は、任意の値を優先順位に指定できます。
    
- 複数の MX レコードがある場合は、メールのルーティングの MX レコードがドメインを所有していることを検証するために使用されるレコードより高い優先度になっていることを確認します。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>SPF レコードはどうやって検証できますか?

**SPF の TXT レコードを 1 つだけ** 持っているか作成していることが重要です。 既に SPF レコードがある場合は、新規に作成せずに、新しい Office 365 の値を追加します。 Microsoft メールの SPF レコードを追加または更新した後、次のいずれかのツールを使用して構文が正しいことを確認してください。 
  
- [SPF レコード テスト ツール](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig Web インターフェイス](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Office 365 では DNS レコードはどのように管理されますか?

Office 365 での DNS 管理には 2 つのオプションがあります。
  
1. ネームサーバー (NS) レコードを変更すると、メール用の MX レコードを設定するのと同様に、Microsoft はすべてのサービス固有のレコードを処理できるようになります。 **(推奨)**
    
2. You add DNS records for email and other Office 365 services at your DNS host yourself. **(Experts only)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 で DNS レコードが作成され、ホストされます。 
**メリット** 
- Office 365 サービスの DNS レコードの入力ミスについて心配する必要がありません。  
- ドメインレジストラーと DNS ホストを自由に選べます。 
- ネーム サーバー レコードの変更を許可しているプロバイダーであれば、必要なレコード タイプの一部をサポートしていないプロバイダーであっても、問題なく機能します。   
- Office 365 が新しい DNS レコードを追加しても、ユーザーは更新を行う必要がありません。  

#### <a name="disadvantages"></a>デメリット 
- Office 365 の外部では、DNS レコードを変更してメールをホストすることができません。 
- 一般向け Web サイトのアドレス (例: www.fourthcoffee.com) としてドメインをすでに使用している場合、ユーザーを Office 365 からそのアドレスにリダイレクトする必要があります。 
- Setting up redirection requires a static IP address, which is not always easily available for public websites. - If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.  

 ### <a name="you-manage-the-dns-records-yourself"></a>DNS レコードを自分で管理する 
 #### <a name="advantages"></a>メリット
- Office 365 サービスの DNS レコードを自分で管理できます。   
- アドレスに自分のドメインが含まれる公開 Web サイト (www.fourthcoffee.com など) がある場合は、Office 365 でドメインをセットアップした後、ユーザーが引き続きその Web サイトを表示できるようにするために、リダイレクションの使用について考える必要はありません。    
- メールをオンプレミスの Exchange サーバーなどでホストすることができる柔軟性があります。  
 
#### <a name="disadvantages"></a>デメリット
Office 365 の DNS レコードを自分で設定する必要があります (GoDaddy ドメインを所有している場合を除く)。 
-  現在の DNS ホストが Microsoft 365 に必要なレコードの種類の一部をサポートしていない場合は、一部の機能を使用できないため、別の DNS ホストに切り替える必要がある場合があります。 
- Office 365 で DNS レコードの要件が変更されたり新しいサービスが追加されたりした場合、DNS ホストでの更新を自分で行う必要があります。 
   
## <a name="what-is-a-domain-name"></a>ドメイン名とは何ですか?


A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.* 
  
Office 365 で「**rob\@contoso.com**」のようなカスタム ドメインを使用すると、ブランドの信頼性や認知度を高めることができます。 
  
[Office 365 でドメインを購入して](../get-help-with-domains/buy-a-domain-name.md) 自動的に設定するか、ドメイン レジストラーで購入したり、入手済みのドメインを使用したりすることができます。
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>Microsoft から購入したドメインを別のプロバイダーに移行できますか。

はい。ただし Office 365 での購入後 60 日を経過するまでは、他のレジストラーに Office 365 ドメインを移行できません。

*Whois* クエリ上では Office 365 で購入したドメイン レジストラーが Wild West Domains LLC として表示されることにご注意ください。 ただし Office 365 で購入したドメインに関しては Office 365 にのみお問い合わせ可能です。
  
以下の手順に従って Office 365 からコードを取得し、その後別のドメイン レジストラーの Web サイトで、そのレジストラーへのドメイン名の移行を設定します。

::: moniker range="o365-worldwide"

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end
    
2. [**ドメイン**] ページで、別のドメイン レジストラーへ移行させる Office 365 ドメインを選択し、[**ドメインの移行**]  >  [**ドメインの移行の有効化**] の順に選択します。
       
4. 手順に従って、ドメインの移行を準備します。
    
5. コードを取得したら、ドメイン名の管理に使用するドメイン レジストラーの Web サイトに移動し、サイトの指示に従って、ドメインを移行します (方法についてはレジストラーのヘルプを参照)。
    
6. コードをもう一度表示する必要がある場合は、Office 365 の [**ドメイン設定**] ページで、[**ドメイン移行の認証コードの表示**] を選択します。
    
7. 移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。
    
8. 手順を完了するには、管理センターの [**ドメイン**] ページに戻り、[**ドメイン移行の完了**] を選択します。 

*注: Office 365 で購入したドメインは、ネーム サーバーの変更または Office 365 テナント間でのドメインの移行の対象外です。 これらのいずれかが必要な場合、ドメイン登録を別のレジストラーに移行する必要があります。*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Office 365 での DNS レコードの管理方法はどうやって変えるのですか?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>DNS の管理を Office 365 以外の DNS ホストで行うように変更する
   
1. 自分のドメインのドメイン レジストラーにサインインします。
    
2. Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host. (The DNS host is often the domain registrar.)
    
3. リンクにアクセスし、ドメインのセットアップ ウィザードに移動します。

::: moniker range="o365-worldwide"

4. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

4. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

4. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
5. [**ドメイン**] ページで、切り替えを行うドメインを選び、[**DNSの管理**] を選択します。
    
6. ドメインのセットアップ ウィザードの [**オンライン サービスの設定**] ページで、[**自分の DNS レコードを管理する**] を選択し、[**次へ**] を選択します。
    
7. [**DNS 設定の更新**] ページのウィザードが推奨する DNS レコードを自分のレジストラーの Web サイトに追加します。 
    
8. レコードを追加したら、Office 365 に戻って [**確認**] を選択します。
    

### <a name="change-dns-management-to-office-365"></a>DNS 管理を Office 365 に変更する

::: moniker range="o365-worldwide"

1. 管理センターで、[ドメインの**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> ] ページに移動します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
2. [**ドメイン**] ページで、切り替えを行うドメインを選び、[**DNS の管理**] を選択します。
    
3. ドメインのセットアップ ウィザードの [**オンライン サービスの設定**] ページで、[**自分用にオンライン サービスをセットアップします。(推奨)**] を選択し、[**次へ**] を選択します。
    
4. ドメインの確認をまだ行っていない場合は、手順に従って最初にそれを行います。
    
5. On the **Update DNS settings** page, we list the nameservers for Office 365. Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers. 
    
4. ネームサーバーを更新したら、**1 時間以上待ちます**。 その後、Office 365 のウィザードに戻り、[**確認**] を選択します。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>DNS プロバイダーで特定のレコードの種類がサポートされない場合はどうなりますか?

If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work. We recommend that you transfer your domain to a registrar that supports all required DNS records.
  
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
    
 **SRV レコードがサポートされない場合** 、次の Office 365 機能は使用できません。 
  
- Skype for Business Online IM およびプレゼンスの Outlook Web App との統合
    
- 他の組織の Skype for Business Online ユーザーとの外部通信 (フェデレーション)。
    
- 公衆インターネット接続 (PIC) (Skype for Business Online のユーザーが Microsoft アカウント (旧称: Windows Live ID) を使用してサインインする場合)。
    
 **複数の CNAME レコードがサポートされてない場合は、** 次の Skype for Business Online の機能の中から機能を選択する必要があります。 
  
- メール デスクトップ クライアントとモバイル クライアントでは、自動検出を使用して Exchange Online サービスが自動的に検出されるため、ユーザーはサーバー名を入力せずにサインインできます。
    
- Skype for Business Online デスクトップ クライアントでは、自動検出を使用して Skype for Business Online サービスが自動的に検出されるため、ユーザーはサーバー名を入力せずにサインインできます。
    
- Skype for Business Online モバイル クライアントでは、自動検出を使用して Skype for Business Online サービスが自動的に検出されるため、ユーザーはサーバー名を入力せずにサインインできます。

- Microsoft Teams は、オンプレミスまたはオンラインのいずれかの Skype for Business とフェデレーションを行います。 詳細については、「 [Microsoft Teams 用に組織のネットワークを準備](https://docs.microsoft.com/microsoftteams/prepare-network)する」を参照してください。
    
 **If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email. SPF records work by identifying the servers that are authorized to send email from your domain. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Office 365 の既定のドメインを設定または変更する方法

既定のドメインを選択するには、1 つ以上のカスタム ドメインが Office 365 に追加されている必要があります。

::: moniker range="o365-worldwide"

1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

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

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>Office 365 でカスタム サブドメインまたは複数のドメインを追加することはできますか?

::: moniker range="o365-worldwide"

Yes! To add subdomains, you must manage your own DNS settings at your registrar's website. If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.

::: moniker-end

::: moniker range="o365-germany"

Yes! To add subdomains, you must manage your own DNS settings at your registrar's website. If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.

::: moniker-end

::: moniker range="o365-21vianet"

Yes! To add subdomains, you must manage your own DNS settings at your registrar's website. If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.

::: moniker-end

通常、最大 900 のドメインを Office 365 サブスクリプションに追加できます。
  
例えば、contoso.com と contosomaketing.com の各ドメインを追加し、その後に www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com などのサブドメインを追加することができます。
  
サブドメインを追加すると、確認が行われる親ドメインでの確認に基づき、自動的に確認されます。
  
When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.  *When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> contoso.com ドメインを既に Office 365 テナントに追加している場合は、サブドメイン xyz.contoso.com を別の Office 365 テナントに追加することもできます。 サブドメインを追加すると、DNS ホスティング プロバイダーに TXT レコードを追加するように求められます。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>"onmicrosoft.com" ドメインがあるのはなぜですか?

Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service. The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*. 
  
 ***alan\@contoso.com* のように表示されるメール アドレスを希望する場合は、**[ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、または「[Office 365 にユーザーとドメインを追加する](add-domain.md)」の手順に従って操作します (既にドメインを所有している場合)。 
  
- **You can't rename the onmicrosoft domain after sign-up.** For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com. To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365. 
    
- **You can't rename your team site URL.** Your team site URL is based on your onmicrosoft.com domain name. Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site. 
    
- **You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain. 
    
You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>"onmicrosoft.de" ドメインがあるのはなぜですか?

Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service. The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*. 
  
 ***alan@contoso.de* のように表示されるメール アドレスを希望する場合は、**[ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、または「[Office 365 にユーザーとドメインを追加する](add-domain.md)」の手順に従って操作します (既にドメインを所有している場合)。 
  
- **You can't rename the onmicrosoft domain after sign-up.** For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de. To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365. 
    
- **You can't rename your team site URL.** Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site. 
    
- **You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain. 
    
You can keep using the initial onmicrosoft.de domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>非営利団体または教育機関のステータスを確認するにはどうすればよいですか?

1. [管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-home)で [**セットアップ**] を選択してウィザードを開始します。 (最初に Office 365 にサインインしてください。) 
    
2. 学校の管理者になるには、Office 365 で [**管理者になる**] オプションを選択します。 
    
3. You'll be prompted to add a TXT DNS record at the DNS host website for your domain. Why? Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.
    
4. レコードを追加したら Office 365 ポータルに戻り、レコードを追加したことを確認します。そうすると、Office 365 で確認が行われます。
    
Have a nonprofit and want to get Office 365? [Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service. 
  
学校の管理者になる方法の詳細については、 [こちらのヘルプ記事をご覧ください](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>カスタム ドメインの少数のメール アドレスだけを使用して Office 365 の試験運用をすることは可能ですか?

可能ですが、制約があります。
  
- 現在のメール プロバイダーで、メール転送のサービスが提供されている必要があります。
    
- You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you. To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.
    
- 一部の Office 365 の機能は利用できません。
- ユーザーは、もう 1 つのメール プロバイダーを利用するユーザーの空き時間情報を表示できません。
- 管理者は、1 か所からすべてのユーザーのアカウントを管理することはできません。
- ユーザーは Office 365 のスパム フィルターを利用できない可能性があります。

### <a name="how-to-set-up-an-office-365-pilot"></a>Office 365 パイロットをセットアップする方法
    
1. Microsoft 365 管理センターにサインインする
    
    1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
        
    2. [**設定**] \> [**ドメイン**] の順に移動します。   
    
2. 使用するドメインを所有していることを確認します。
    
    1. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。 
        
    2. パネルで、ドメインを入力し (この例の場合、cohowinery.com)、[**次へ**] を選択します。 
        
    3. [**ドメインの確認**] ページで手順に沿って操作します。 
        
    4. ドロップダウン リストから自分の DNS ホスティング プロバイダーを選択し、手順に沿って操作してこのドメインを所有していることを証明します。
        
    5. [**確認**] を選択します。 DNS の変更が有効になるまでの時間は、数分から 72 時間です。 
        
    6. 確認が成功すると、DNS レコードを変更するように求められます。
    
3. Exchange Online で、このドメインを共有ドメインとして設定します。
    
    1. **Exchange 管理センター** (EAC) に移動します。 
        
    2. [**メール フロー**] セクションで [**承認済みドメイン**] を選択します。 
        
    3. 変更するドメインをダブルクリックします。
        
    4. 開いたウィンドウで、[**内部の中継**] を選択します。 
        
    5. [**保存**] を選択します。 設定が有効になるまでに数分間かかる場合があります。 
    
4. オプションで、既存のメール サーバーのブロックを解除します。
    
    1. Office 365 は、Exchange Online Protection (EOP) を使用してスパム保護を行います。 EOP が現在のメールサーバーによって転送された大量のスパムを検出した場合は、それをブロックすることで、転送が動作しないようにすることができます。 他の電子メールプロバイダーが使用するスパム保護に自信がある場合は、そのサーバーを Office 365 の許可一覧に追加することができます。 ただし、これにより、元のサーバー経由で受信したすべてのスパムが Office 365 メールボックスに届くようにすることもできます。これにより、Office 365 がスパムを阻止しているかどうかを評価することはできません。
    
    2. Exchange 管理センター (EAC)に移動します。
        
    3. EAC で、[**保護**]、[**接続フィルター**] の順に選びます。 
        
    4. [**IP 許可一覧**] で **+** を選択し、現在のメール プロバイダーから入手できるメール サーバー IP アドレスを追加します。 
    
5. ユーザー アカウントを作成してプライマリ (Reply-To) アドレスを設定する
    
    1. Microsoft 365 管理センターに移動します。
        
    2. 左側のナビゲーション バーで、[**ユーザー**] \> [**アクティブなユーザー**] の順に選択します。 
        
    3. ユーザー アカウントを作成する。
        
    4. 各アカウントについて、**+ (新規)** を選択し、必要な情報を入力します。 
        
    5. ユーザーのメールを現在のものと同じにするには、[**ユーザー名**] フィールドの内容はユーザーの現在のメール アドレスと完全に一致する必要があります。 
        
    6. ユーザー名の横のドロップダウン リストからカスタム ドメイン名を選択します。
        
    7. [**作成**] \> [**閉じる**] の順に選択します。 
        
6. DNS ホスティング プロバイダーで DNS レコードを更新する
    
    1. Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). **Make the following exceptions:**
    
        1. 新しい MX レコードは作成せず、既存の MX レコードの変更も行いません。
            
        2. If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record. For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".
            
        3. If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com. This authorizes outgoing messages from both email systems.
            
7. 現在のプロバイダーでのメール転送を設定する
    
    1. 現在のメール プロバイダーで、onmicrosoft.com domain ドメインへの転送を管理するユーザーのメール アカウントで設定します。
        
    2. ユーザー A のメールボックスからの転送先は usera@yourcompany.onmicrosoft.com です。
        
    3. ユーザー B のメールボックスからの転送先は userb@yourcompany.onmicrosoft.com です。
        
    4. この手順が完了すると、次のことが可能になります。
        
    5. usera@yourcompany.onmicrosoft.com と userb@yourcompany.onmicrosoft.com へ送信されるすべてのメールは Office 365 で利用可能になります。
    
    6. 注:
        
        - 転送の設定の詳細は、現在のメール プロバイダーにお問い合わせください。
            
        - 現在のメール プロバイダーでメッセージのコピーを保持する必要はありません。
            
        - ほとんどのプロバイダーは、転送をするメールに Reply-to アドレスを残すため、返信メッセージは元の送信者に送信されます。
    
8. メール フローのテスト
    
    1. ユーザー A の資格情報を使用して Outlook Web App にサインインします。
        
    2. 次のタスクを実行します。
        
    3. ローカル Microsoft メールをテストします。 たとえば、ユーザー B に電子メールを送信します。この電子メールはすぐに配信されます。 このシナリオでは、Office 365 はメールボックスをローカルとして認識するため、メッセージは元のサーバー上のユーザー B のメールボックスにルーティングされません。
        
    4. Test email to someone who's on the other email system. For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.
        
    5. 外部アカウントから、または他の電子メールシステムの従業員の電子メールアカウントから、他のメールシステムで転送が正しく設定されていることを確認します。 たとえば、User C の元のサーバーアカウントまたは Hotmail アカウントから、ユーザー A に電子メールを送信して、そのメールがユーザー A の Office 365 メールボックスに届くことを確認します。
        
9. メールボックスのコンテンツの移動
    
    1. Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst). Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.
        
    2. When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center. To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.
    
