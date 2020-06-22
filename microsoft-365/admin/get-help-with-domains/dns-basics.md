---
title: DNS の基本
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: ドメイン管理に役立つドメインとそれに関連する DNS レコードについて説明します。
ms.openlocfilehash: 3a3a03c408d480b5d4678fde25c8830e063b1310
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780183"
---
# <a name="dns-basics"></a>DNS の基本

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
::: moniker range="o365-worldwide"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains in Office 365.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。 ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。 DNS とドメイン レジストラーの基本を理解することで、管理者は 21Vianet によって運営される Office 365 のドメインを管理できます。
  
::: moniker-end

## <a name="what-are-domain-names"></a>ドメイン名とは

Domain names are used in URLs and email addresses, and they have different levels. For example, mail.contoso.com is a domain name with the following three levels:
  
- **.com** はトップレベル ドメインです 
    
- **contoso** は第 2 レベル ドメインです 
    
- **mail** は第 3 レベル ドメインです 
    
Why use a third-level domain? You might want to have different domain names for marketing or a blog. For example, blog.contoso.com. You typically add a second-level domain, like contoso.com, to use with Office 365 but you can also use third-level domains if you like.
  
それぞれのドメインの機能の詳細については、[Office 365 サービスの各種ドメインの説明](https://go.microsoft.com/fwlink/?LinkId=402693)を参照してください。
  
## <a name="understand-dns-record-types"></a>DNS レコードの種類について

DNS records stored at a DNS host for your domain are used to direct traffic for your domain. The following table describes frequently used DNS records and how they're used with Office 365.
  
|**NS (ネームサーバー) レコード**|**ドメインの正式なネーム サーバーを識別します。 これらのネームサーバーを変更すると、DNS レコードが管理される場所および DNS システムがメール サーバーなどについての情報を探す場所が変わります。 Office 365 は独自のネームサーバーを持ちます。あるいは、自身のドメインと共に設定しているネームサーバーを使用することもできます。**|
|:-----|:-----|
|A レコード (アドレス レコード)  <br/> |ドメイン名を IP アドレスに関連付けます。  <br/> |
|CNAME (別名または正規名) レコード  <br/> |Redirects one domain to another in the DNS system. When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.  <br/> |
|MX (メール エクスチェンジャー) レコード  <br/> |Points to where your email should be sent. It also has a priority field so that you can send mail to different servers in a priority order.  <br/> |
|SPF (Sender Policy Framework) レコード  <br/> |TXT レコードで、メールのスプーフィングやフィッシングを防ぐために役立ちます。  <br/> |
|SRV (サービス) レコード  <br/> |Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Office 365 services. For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.  <br/> |
|TTL (time-to-live)  <br/> |ネーム サーバーは、この時間の分だけ DNS レコードを保持した後、更新バージョンを探します。  <br/> |
   
## <a name="how-does-dns-work"></a>DNS のしくみ

Part of setting up your domain with a cloud service like Office 365 includes changing or adding [DNS records](dns-basics.md) for the domain. These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites. 
  
The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses. IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.
  
So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name. When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Office 365 instead of somewhere else.
  
A domain's DNS records can be helpful in other ways, too. For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS レコードによってインターネットが正しい宛先にメールを届けるしくみ

As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses. One DNS record, called the MX record, is specifically for sending email to the right host.
  
DNS records are like a database of information about your domain. The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is. Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file. And that's where you update the MX record for your domain, to send email messages to Office 365.
  
 *When you change your email to Office 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Office 365.*  If other people use your domain for email, you must set up Office 365 mailboxes for each of those people. 
  
Sound complicated? Well, it can be, but we walk you through each step in the Office 365 domain setup.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS によって Web サイトを探す場所がわかる

When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com. The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain. There are lots of DNS servers, all connected to each other. The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.
  
::: moniker range="o365-worldwide"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Office 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-germany"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Office 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-21vianet"

contoso.com の NS レコードに「hichina.com」と記載するとします。 これで、インターネットは、hichina.com が contoso.com の他のすべての DNS レコードを一覧表示したゾーン ファイルを探す場所であることを認識できます。 それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。 たとえば、MX レコードに "メールを Office 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが Office 365 に送信されます。 そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。

::: moniker-end

The actual values that you must enter for all of this to work with Office 365 are listed for you when you're setting up your domain, in the domain setup steps. If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.
  
::: moniker range="o365-worldwide"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-germany"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-21vianet"

ドメインのゾーン ファイルがドメイン レジストラー以外の場所にあるのはなぜですか? HiChina のようなドメイン レジストラーでドメイン名を登録することもできますが、DNS レコードは別の DNS ホスティング会社や Web ホスティング会社で管理されているかもしれません。 ドメインの NS レコードには、その情報が格納されます。これにより、すべての DNS サーバーが検索対象を把握できます。

::: moniker-end

> [!NOTE]
> Office 365 でドメインをセットアップし、[Microsoft が DNS レコードをセットアップして管理する](../setup/domains-faq.md#how-does-office-365-manage-my-dns-records)ようにして、セットアップの一環として、[DNS 管理を Office 365 に変更](../setup/domains-faq.md#change-dns-management-to-office-365)します。 
 

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-office-365"></a>Office 365 でドメインを追加するのはなぜですか?


Adding a custom domain, like fourthcoffee.com, to Office 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Office 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Office 365 for email. 
  
> [!NOTE]
> Outlook や Word などの Microsoft アプリをダウンロードして使うだけであれば、ドメインを追加する必要はありません。その場合は、[PC または Mac に Office をインストールしてください](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。 
  
Office 365 では、ドメイン名をメール、一般向け Web サイト、インスタント メッセージング アドレスに使うことができます。
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Office 365) could be joe@contoso.com. 
    
- **Web サイト:** Microsoft 365 サブスクリプションに SharePoint Online Public Web サイト (現在では非売品) が含まれる場合は、一般向け Web サイトには contoso-public.sharepoint.com のような初期アドレスが割り当てられます。 会社の Web サイトを設定する場合は、 カスタム ドメイン名を使用して Web サイトのアドレスを変更して、www.contoso.com などにできます。 
    
- **インスタント メッセージング**: Skype for Business Online アドレスもドメイン名を使うようにカスタマイズできるため、組織内のユーザーは、短くて覚えやすいアドレス (joe@contoso.com など) を使って Skype for Business Online で相互接続できるようになります。 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-office-365"></a>Office 365 でドメインを追加するのはなぜですか?


Adding a custom domain, like fourthcoffee.com, to Office 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Office 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Office 365 for email. 
  
> [!NOTE]
> Outlook や Word などの Office 365 アプリをダウンロードして使うだけであれば、ドメインを追加する必要はありません。その場合は、[PC または Mac に Office をインストールしてください](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。 
  
Office 365 では、ドメイン名をメール、一般向け Web サイト、インスタント メッセージング アドレスに使うことができます。
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Office 365) could be joe@contoso.com. 
    
- **Web サイト:** サブスクリプションに SharePoint Online Public Web サイト (現在では非売品) が含まれる場合は、一般向け Web サイトには contoso-public.sharepoint.com のような初期アドレスが割り当てられます。 会社の Web サイトを設定する場合は、 カスタム ドメイン名を使用して Web サイトのアドレスを変更して、www.contoso.com などにできます。 
    
- **インスタント メッセージング**: Skype for Business Online アドレスもドメイン名を使うようにカスタマイズできるため、組織内のユーザーは、短くて覚えやすいアドレス (joe@contoso.com など) を使って Skype for Business Online で相互接続できるようになります。 
    
::: moniker-end

## <a name="the-dns-records-required-for-office-365"></a>Office 365 に必要な DNS レコード

There are a number of DNS records required for Office 365 to work with your domain. In addition to setting up your domain's MX record so email will be sent to Office 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.
  
You can [find a list of values](information-for-dns-records.md) to set up your domain. They're included right in the Microsoft 365 admin center. 
  
また、展開を予定している場合は、Office 365 に必要なすべての DNS レコードの一覧、それぞれのレコードの機能、値の例も確認してください。 「[Office 365 の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)」を確認してください。
  
## <a name="how-can-i-learn-more"></a>さらに詳しく知るには

次のいずれかを確認してください。 
  
- ドメインが登録されている場所がわからない場合 [ドメイン レジストラーの検索に関するヘルプをご覧ください。](find-your-domain-registrar.md)
    
- Office 365 でドメインを使う前に、[ウィザードのステップの完了が必要な理由](../setup/add-domain.md)を確認してください。 
    

