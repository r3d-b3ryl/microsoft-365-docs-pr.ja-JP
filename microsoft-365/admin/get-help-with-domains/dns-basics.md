---
title: DNS の基本
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: ドメイン ネーム システムは、コンピューターのホスト名を IP アドレスにマップします。DNS とドメイン レジストラーの基礎を理解することはドメインを管理するうえで役立ちます。
ms.openlocfilehash: 68b9b82d52e9bb2c4105237f0a29e8137623138e
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393909"
---
# <a name="dns-basics"></a><span data-ttu-id="28ed9-103">DNS の基本</span><span class="sxs-lookup"><span data-stu-id="28ed9-103">DNS basics</span></span>

 <span data-ttu-id="28ed9-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28ed9-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="28ed9-p101">contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。DNS とドメイン レジストラーの基礎を理解することは、管理者がドメインを管理するうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p101">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.</span></span>

## <a name="watch-domains--dns-an-overview"></a><span data-ttu-id="28ed9-108">視聴する: ドメインと DNS の概要</span><span class="sxs-lookup"><span data-stu-id="28ed9-108">Watch: Domains & DNS: An overview</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="28ed9-p102">contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。DNS とドメイン レジストラーの基礎を理解することは、管理者がドメインを管理するうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p102">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.</span></span>

## <a name="watch-domains--dns-an-overview"></a><span data-ttu-id="28ed9-112">視聴する: ドメインと DNS の概要</span><span class="sxs-lookup"><span data-stu-id="28ed9-112">Watch: Domains & DNS: An overview</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="28ed9-p103">contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。DNS とドメイン レジストラーの基礎を理解することは、管理者がドメインを管理するうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p103">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics will help admins manage domains.</span></span>
  
::: moniker-end

## <a name="what-are-domain-names"></a><span data-ttu-id="28ed9-116">ドメイン名とは</span><span class="sxs-lookup"><span data-stu-id="28ed9-116">What are domain names?</span></span>

<span data-ttu-id="28ed9-p104">ドメイン名は URL とメール アドレスで使用されます。また、さまざまなレベルがあります。 たとえば、mail.contoso.com は次の 3 つのレベルを持つドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p104">Domain names are used in URLs and email addresses, and they have different levels. For example, mail.contoso.com is a domain name with the following three levels:</span></span>
  
- <span data-ttu-id="28ed9-119">**.com** はトップレベル ドメインです</span><span class="sxs-lookup"><span data-stu-id="28ed9-119">**.com** is the top-level domain</span></span> 
    
- <span data-ttu-id="28ed9-120">**contoso** は第 2 レベル ドメインです</span><span class="sxs-lookup"><span data-stu-id="28ed9-120">**contoso** is the second-level domain</span></span> 
    
- <span data-ttu-id="28ed9-121">**mail** は第 3 レベル ドメインです</span><span class="sxs-lookup"><span data-stu-id="28ed9-121">**mail** is the third-level domain</span></span> 
    
<span data-ttu-id="28ed9-p105">第 3 レベル ドメインはなぜ必要なのでしょうか。 それは、マーケティングやブログで異なるドメイン名、 たとえば blog.contoso.com などを使いたい場合があるからです。 Microsoft で利用できるように contoso.com のような第 2 レベル ドメインを追加することは一般的ですが、第 3 レベル ドメインを利用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p105">Why use a third-level domain? You might want to have different domain names for marketing or a blog. For example, blog.contoso.com. You typically add a second-level domain, like contoso.com, to use with Microsoft but you can also use third-level domains if you like.</span></span>
  
<span data-ttu-id="28ed9-126">それぞれのドメインの機能の詳細については、[Microsoft 365 および Office 365 プラットフォーム サービスの説明](/office365/servicedescriptions/office-365-platform-service-description/domains)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28ed9-126">Learn more about what you can do with domains for each type of offering in the [Microsoft 365 and Office 365 platform service description](/office365/servicedescriptions/office-365-platform-service-description/domains).</span></span>
  
## <a name="understand-dns-record-types"></a><span data-ttu-id="28ed9-127">DNS レコードの種類について</span><span class="sxs-lookup"><span data-stu-id="28ed9-127">Understand DNS record types</span></span>

<span data-ttu-id="28ed9-p106">自分のドメインの DNS ホストに保存される DNS レコードを使用して、トラフィックをそのドメインへと導くことができます。 次の表では、よく使われる DNS レコードとその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p106">DNS records stored at a DNS host for your domain are used to direct traffic for your domain. The following table describes frequently used DNS records and how they're used.</span></span>
  
|<span data-ttu-id="28ed9-130">**NS (ネームサーバー) レコード**</span><span class="sxs-lookup"><span data-stu-id="28ed9-130">**NS (nameserver) record**</span></span>|<span data-ttu-id="28ed9-131">**ドメインの正式なネーム サーバーを識別します。 これらのネームサーバーを変更すると、DNS レコードが管理される場所および DNS システムがメール サーバーなどについての情報を探す場所が変わります。Microsoft は独自のネームサーバーを持ちます。あるいは、自身のドメインと共に設定しているネームサーバーを使用することもできます。**</span><span class="sxs-lookup"><span data-stu-id="28ed9-131">**Identifies the name servers that are the "authoritative nameservers" for a domain. When you change the nameservers for your domain, you change where your DNS records are managed and where the DNS system looks for information about mail servers and so on. Microsoft has its own nameservers, or you may decide to keep using the nameservers that are already set up with your domain.**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28ed9-132">A レコード (アドレス レコード)</span><span class="sxs-lookup"><span data-stu-id="28ed9-132">A record (address record)</span></span>  <br/> |<span data-ttu-id="28ed9-133">ドメイン名を IP アドレスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-133">Associates a domain name with an IP address.</span></span>  <br/> |
|<span data-ttu-id="28ed9-134">CNAME (別名または正規名) レコード</span><span class="sxs-lookup"><span data-stu-id="28ed9-134">CNAME (alias or canonical) record</span></span>  <br/> |<span data-ttu-id="28ed9-p107">あるドメインを DNS システム内の別のドメインにリダイレクトします。ネーム サーバーがドメインを検索し、CNAME レコードを見つけると、先頭のドメイン名を CNAME で置換し、新しい名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p107">Redirects one domain to another in the DNS system. When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.</span></span>  <br/> |
|<span data-ttu-id="28ed9-137">MX (メール エクスチェンジャー) レコード</span><span class="sxs-lookup"><span data-stu-id="28ed9-137">MX (mail exchanger) record</span></span>  <br/> |<span data-ttu-id="28ed9-p108">電子メールの送り先を示します。また、このレコードには、メールを優先度の順序で異なるサーバーに送ることができるように、優先度フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p108">Points to where your email should be sent. It also has a priority field so that you can send mail to different servers in a priority order.</span></span>  <br/> |
|<span data-ttu-id="28ed9-140">SPF (Sender Policy Framework) レコード</span><span class="sxs-lookup"><span data-stu-id="28ed9-140">SPF (sender policy framework) record</span></span>  <br/> |<span data-ttu-id="28ed9-141">TXT レコードで、メールのスプーフィングやフィッシングを防ぐために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-141">A TXT record that helps prevent email spoofing and phishing.</span></span>  <br/> |
|<span data-ttu-id="28ed9-142">SRV (サービス) レコード</span><span class="sxs-lookup"><span data-stu-id="28ed9-142">SRV (service) record</span></span>  <br/> |<span data-ttu-id="28ed9-p109">Skype for Business Online や Exchange Online で、Microsoft サービス間の情報フローを調整するために使われます。たとえば、SRV レコードは、Outlook Web App でプレゼンスを表示するため、また他の会社のユーザーと Skype for Business Online、Skype、またはその他のインスタント メッセージング ツールを使うために必要です。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p109">Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Microsoft services. For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.</span></span>  <br/> |
|<span data-ttu-id="28ed9-145">TTL (time-to-live)</span><span class="sxs-lookup"><span data-stu-id="28ed9-145">TTL (time-to-live)</span></span>  <br/> |<span data-ttu-id="28ed9-146">ネーム サーバーは、この時間の分だけ DNS レコードを保持した後、更新バージョンを探します。</span><span class="sxs-lookup"><span data-stu-id="28ed9-146">The amount of time that a nameserver keeps a DNS record before the server looks for an updated version.</span></span>  <br/> |
   
## <a name="how-does-dns-work"></a><span data-ttu-id="28ed9-147">DNS のしくみ</span><span class="sxs-lookup"><span data-stu-id="28ed9-147">How does DNS work?</span></span>

<span data-ttu-id="28ed9-p110">Microsoft 365 などのクラウド サービスでドメインをセットアップするときには、そのドメインの [DNS レコード](dns-basics.md)の変更や追加が必要になります。そのような変更が必要になる理由は、メールの送り先や Web サイトの場所を探すために、インターネットが DNS (ドメイン ネーム システム) とドメイン名を使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p110">Part of setting up your domain with a cloud service like Microsoft 365 includes changing or adding [DNS records](dns-basics.md) for the domain. These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites.</span></span> 
  
<span data-ttu-id="28ed9-p111">インターネットは DNS (ドメイン ネーム システム) を使うように設定され、それによってユーザーはわかりやすい名前 (contoso.com など) を使ってインターネット上の特定の場所を見つけることができますが、実際には覚えにくい IP (インターネット プロトコル) アドレスと呼ばれる数字が割り当てられています。IP アドレスは 70.42.241.42 のように表示されるため、ドメイン名を使うほうがメール ホストや Web サイトなどの場所を簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p111">The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses. IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.</span></span>
  
<span data-ttu-id="28ed9-p112">つまり、インターネットでは、DNS レコードによって、ドメイン名を使ったメールの送り先 (joe@contoso.com など) や Web サイトの場所 (www.contoso.com など) がわかるということです。DNS レコードにドメインの情報が正確に設定されていれば、DNS システムによって適切にルーティングされるため、メールは Microsoft 365 だけに届きます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p112">So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name. When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Microsoft 365 instead of somewhere else.</span></span>
  
<span data-ttu-id="28ed9-p113">ドメインの DNS レコードは、他のことでも役に立ちます。 たとえば、Exchange は DNS レコードをチェックして、Outlook が正しい Exchange サーバーとの接続を自動的にセットアップすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p113">A domain's DNS records can be helpful in other ways, too. For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.</span></span>
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a><span data-ttu-id="28ed9-156">DNS レコードによってインターネットが正しい宛先にメールを届けるしくみ</span><span class="sxs-lookup"><span data-stu-id="28ed9-156">DNS records help the Internet send email to the right place</span></span>

<span data-ttu-id="28ed9-p114">上で説明したとおり、DNS はわかりやすいドメイン名を覚えにくい IP アドレスにマッピングして、トラフィックをインターネット上で転送しています。 DNS レコードの 1 つである MX レコードは、正しいホストにメールを送るためのものです。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p114">As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses. One DNS record, called the MX record, is specifically for sending email to the right host.</span></span>
  
<span data-ttu-id="28ed9-p115">DNS レコードは、ドメイン情報のデータベースのようなものです。レコードとレコード値は、各ドメインに対するレコードとレコード値のリストが含まれたゾーン ファイルと呼ばれる場所に保持されます。ドメイン レジストラーや DNS をホストする会社は、ユーザーにドメインのゾーン ファイルのレコードを編集するための UI を Web サイトで提供します。ユーザーは、その UI を使って、ドメインに対する MX レコードを更新し、メール メッセージを Microsoft 365 に送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p115">DNS records are like a database of information about your domain. The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is. Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file. And that's where you update the MX record for your domain, to send email messages to Microsoft 365.</span></span>
  
 <span data-ttu-id="28ed9-p116">*次の手順で、ドメインの MX レコードを更新することでメールを Microsoft 365 に変更すると、そのドメインに送信されたすべてのメールが Microsoft 365 に届くようになります。*  他のユーザーがメール用にそのドメインを使用する場合は、それらのユーザーごとに Microsoft 365 メールボックスをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p116">*When you change your email to Microsoft 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Microsoft 365.*  If other people use your domain for email, you must set up Microsoft 365 mailboxes for each of those people.</span></span> 
  
<span data-ttu-id="28ed9-p117">Microsoft ドメインのセットアップは複雑そうに思うかもしれませんが、手順については、詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p117">Sound complicated? Well, it can be, but we walk you through each step in the Microsoft domain setup.</span></span>
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a><span data-ttu-id="28ed9-167">DNS によって Web サイトを探す場所がわかる</span><span class="sxs-lookup"><span data-stu-id="28ed9-167">DNS tells the Internet where to look for websites too</span></span>

<span data-ttu-id="28ed9-p118">Web サイトのアドレス (例: www.contoso.com) を入力すると、DNS サーバーの 1 つ (ここでは contoso.com) で、ネーム サーバー (NS) レコードと呼ばれるものが、最初にインターネット上で検索されます。インターネットでは、NS レコードによって、ドメインに対する他のすべての DNS レコード値を持つゾーン ファイルの場所が認識されます。DNS サーバーの数は多く、すべてが互いに接続されています。すべてのサーバーでは、登録されているすべての一意のドメイン名とドメインのゾーン ファイルの場所を互いに認識しています。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p118">When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com. The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain. There are lots of DNS servers, all connected to each other. The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="28ed9-p119">たとえば、contoso.com に対する NS レコードに "godaddy.com" という値があるとします。それにより、インターネット上で、contoso.com に対する他のすべての DNS レコードのリストを含むゾーン ファイルが GoDaddy.com にあることがわかります。それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。たとえば、MX レコードに "メールを Microsoft 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが Office 365 に送信されます。そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p119">Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="28ed9-p120">たとえば、contoso.com に対する NS レコードに "godaddy.com" という値があるとします。それにより、インターネット上で、contoso.com に対する他のすべての DNS レコードのリストを含むゾーン ファイルが GoDaddy.com にあることがわかります。それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。たとえば、MX レコードに "メールを Microsoft 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが Office 365 に送信されます。そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p120">Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="28ed9-p121">たとえば、contoso.com に対する NS レコードに "hichina.com" という値があるとします。それにより、インターネット上で、contoso.com に対する他のすべての DNS レコードのリストを含むゾーン ファイルが hichina.com にあることがわかります。それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。たとえば、MX レコードに "メールを Microsoft 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが送信されます。そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p121">Let's say that the NS record for contoso.com says "hichina.com." Now the Internet knows that hichina.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

<span data-ttu-id="28ed9-p122">ドメインのセットアップ時に、Microsoft 365 を操作するために入力が必要な実際の値は、ドメインのセットアップ手順に記載されています。手動でセットアップを実行する場合は、それらの値をコピーして、自分の DNS ホスト (ドメイン レジストラーなど) で正しい DNS レコード (MX レコード、CNAME レコードなど) に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p122">The actual values that you must enter for all of this to work with Microsoft 365 are listed for you when you're setting up your domain, in the domain setup steps. If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="28ed9-p123">自分のドメイン レジストラー以外の場所に自分のドメインのゾーン ファイルがある理由はなんでしょうか。 ドメイン名を GoDaddy のようなドメイン レジストラーに登録しても、自分の DNS レコードは別の場所 (別の DNS をホストする会社や Web をホストする会社) で管理できます。 ドメインに対する NS レコードにはその情報が格納されているため、どこを探すべきかすべての DNS サーバーにわかるのです。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p123">Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="28ed9-p124">自分のドメイン レジストラー以外の場所に自分のドメインのゾーン ファイルがある理由はなんでしょうか。 ドメイン名を GoDaddy のようなドメイン レジストラーに登録しても、自分の DNS レコードは別の場所 (別の DNS をホストする会社や Web をホストする会社) で管理できます。 ドメインに対する NS レコードにはその情報が格納されているため、どこを探すべきかすべての DNS サーバーにわかるのです。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p124">Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="28ed9-p125">自分のドメイン レジストラー以外の場所に自分のドメインのゾーン ファイルがある理由はなんでしょうか。 ドメイン名を HiChina のようなドメイン レジストラーに登録しても、自分の DNS レコードは別の場所 (別の DNS をホストする会社や Web をホストする会社) で管理できます。 ドメインに対する NS レコードにはその情報が格納されているため、どこを探すべきかすべての DNS サーバーにわかるのです。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p125">Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like HiChina, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="28ed9-198">Microsoft 365 でドメインを追加するのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="28ed9-198">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="28ed9-p126">Microsoft 365 に fourthcoffee.com などのカスタム ドメインを追加すると、短くて親しみやすいメール アドレスやユーザー ID をサービスで使えるようになります。 Microsoft 365 アカウントにサインアップすると、[使用するドメインが割り当てられます](../setup/domains-faq.yml)が、ドメイン名には "onmicrosoft.com" が含まれています。ユーザーの多くは、Microsoft 365 のメールを使う予定がある場合、組織やビジネスのドメインを追加することを選びます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p126">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](../setup/domains-faq.yml) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="28ed9-202">Outlook や Word などの Microsoft アプリをダウンロードして使うだけであれば、ドメインを追加する必要はありません。その場合は、[PC または Mac に Office をインストールしてください](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。</span><span class="sxs-lookup"><span data-stu-id="28ed9-202">If you just want to download and use Microsoft apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="28ed9-203">Microsoft 365 では、ドメイン名をメール、一般向け Web サイト、インスタント メッセージング アドレスに使うことができます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-203">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="28ed9-p127">**メール:** 自分のドメイン名を使ってメールをカスタマイズできるため、アカウントに割り当てられた [初期設定の onmicrosoft.com メール アドレス](../setup/domains-faq.yml)よりも短くて覚えやすいアドレスを使うことができます。したがって、(Microsoft 365 にサインインするための 職場のアカウント でもある) メール アドレスを、joe@contoso.onmicrosoft.com から、たとえば joe@contoso.com に変更できます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p127">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](../setup/domains-faq.yml) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="28ed9-206">**Web サイト:** Microsoft 365 サブスクリプションに SharePoint Online Public Web サイト (現在では非売品) が含まれる場合は、一般向け Web サイトには contoso-public.sharepoint.com のような初期アドレスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-206">**Website:** If you have an Microsoft 365 subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="28ed9-207">会社の Web サイトを設定する場合は、 カスタム ドメイン名を使用して Web サイトのアドレスを変更して、www.contoso.com などにできます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-207">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="28ed9-208">**インスタント メッセージング**: Skype for Business Online アドレスもドメイン名を使うようにカスタマイズできるため、組織内のユーザーは、短くて覚えやすいアドレス (joe@contoso.com など) を使って Skype for Business Online で相互接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="28ed9-208">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="28ed9-209">Microsoft 365 でドメインを追加するのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="28ed9-209">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="28ed9-p129">Microsoft 365 に fourthcoffee.com などのカスタム ドメインを追加すると、短くて親しみやすいメール アドレスやユーザー ID をサービスで使えるようになります。 Microsoft 365 アカウントにサインアップすると、[使用するドメインが割り当てられます](../setup/domains-faq.yml)が、ドメイン名には "onmicrosoft.com" が含まれています。ユーザーの多くは、Microsoft 365 のメールを使う予定がある場合、組織やビジネスのドメインを追加することを選びます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p129">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](../setup/domains-faq.yml) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="28ed9-213">Outlook や Word などの Microsoft 365 アプリをダウンロードして使うだけであれば、ドメインを追加する必要はありません。その場合は、[PC または Mac に Office をインストールしてください](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。</span><span class="sxs-lookup"><span data-stu-id="28ed9-213">If you just want to download and use Microsoft 365 apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="28ed9-214">Microsoft 365 では、ドメイン名をメール、一般向け Web サイト、インスタント メッセージング アドレスに使うことができます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-214">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="28ed9-p130">**メール:** 自分のドメイン名を使ってメールをカスタマイズできるため、アカウントに割り当てられた [初期設定の onmicrosoft.com メール アドレス](../setup/domains-faq.yml)よりも短くて覚えやすいアドレスを使うことができます。したがって、(Microsoft 365 にサインインするための 職場のアカウント でもある) メール アドレスを、joe@contoso.onmicrosoft.com から、たとえば joe@contoso.com に変更できます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p130">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](../setup/domains-faq.yml) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="28ed9-217">**Web サイト:** サブスクリプションに SharePoint Online Public Web サイト (現在では非売品) が含まれる場合は、一般向け Web サイトには contoso-public.sharepoint.com のような初期アドレスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-217">**Website:** If you have a subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="28ed9-218">会社の Web サイトを設定する場合は、 カスタム ドメイン名を使用して Web サイトのアドレスを変更して、www.contoso.com などにできます。</span><span class="sxs-lookup"><span data-stu-id="28ed9-218">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="28ed9-219">**インスタント メッセージング**: Skype for Business Online アドレスもドメイン名を使うようにカスタマイズできるため、組織内のユーザーは、短くて覚えやすいアドレス (joe@contoso.com など) を使って Skype for Business Online で相互接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="28ed9-219">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a><span data-ttu-id="28ed9-220">Microsoft 365 に必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="28ed9-220">The DNS records required for Microsoft 365</span></span>

<span data-ttu-id="28ed9-p132">ドメインで Microsoft 365 を使用するには、いくつかの DNS レコードが必要です。メールを Microsoft 365 に送信するためのドメインの MX レコードのセットアップのほか、Outlook と正しい Exchange サーバーとの自動接続の確認、インスタント メッセージングのセットアップ、迷惑メールからの保護などの作業に役立つレコードもあります。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p132">There are a number of DNS records required for Microsoft 365 to work with your domain. In addition to setting up your domain's MX record so email will be sent to Microsoft 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.</span></span>
  
<span data-ttu-id="28ed9-p133">ドメインをセットアップするには、Microsoft 365 管理センターの[値の一覧を参照](information-for-dns-records.md)してください。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p133">You can [find a list of values](information-for-dns-records.md) to set up your domain. They're included right in the Microsoft 365 admin center.</span></span> 
  
<span data-ttu-id="28ed9-p134">また、展開を予定している場合は、Microsoft 365 に必要なすべての外部ドメイン ネーム システムの レコードの一覧、それぞれのレコードの機能、値の例も確認してください。 「[Microsoft 365 の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p134">Or, if you're planning a deployment, you may want to review a list of all the DNS records required for Microsoft 365, what their function is, and example values. Check out [External Domain Name System records for Microsoft 365](../../enterprise/external-domain-name-system-records.md).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="28ed9-227">次の手順</span><span class="sxs-lookup"><span data-stu-id="28ed9-227">Next steps</span></span>

<span data-ttu-id="28ed9-228">次のいずれかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="28ed9-228">Check out one of the following:</span></span> 
  
- <span data-ttu-id="28ed9-p135">ドメインが登録されている場所を確認するには、「[ドメイン レジストラーの検索方法](find-your-domain-registrar.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28ed9-p135">Not sure where your domain is registered? [Get help finding your domain registrar.](find-your-domain-registrar.md)</span></span>
- <span data-ttu-id="28ed9-231">Microsoft 365 でドメインを使う前に、「[ウィザードの手順の完了が必要な理由](../setup/add-domain.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="28ed9-231">Find out [why you have to complete the wizard steps](../setup/add-domain.md) before you can use your domain with Microsoft 365.</span></span>

## <a name="related-content"></a><span data-ttu-id="28ed9-232">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="28ed9-232">Related content</span></span>

<span data-ttu-id="28ed9-233">[ドメインの FAQ](../setup/domains-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="28ed9-233">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="28ed9-234">[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="28ed9-234">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="28ed9-235">[ドメインの管理](index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="28ed9-235">[Manage domains](index.yml) (link page)</span></span>