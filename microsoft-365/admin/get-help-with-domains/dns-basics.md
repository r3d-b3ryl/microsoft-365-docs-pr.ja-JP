---
title: DNS の基本
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: ドメイン ネーム システムは、コンピューターのホスト名を IP アドレスにマップします。DNS とドメイン レジストラーの基礎を理解することはドメインを管理するうえで役立ちます。
ms.openlocfilehash: 308f41c6b1c899ae731d1dcf3e7fc02e5a3cb5ed
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085929"
---
# <a name="dns-basics"></a>DNS の基本

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
::: moniker range="o365-worldwide"

contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。DNS とドメイン レジストラーの基礎を理解することは、管理者がドメインを管理するうえで役立ちます。

## <a name="watch-domains--dns-an-overview"></a>視聴する: ドメインと DNS の概要
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。DNS とドメイン レジストラーの基礎を理解することは、管理者がドメインを管理するうえで役立ちます。
  
::: moniker-end

## <a name="what-are-domain-names"></a>ドメイン名とは

ドメイン名は URL とメール アドレスで使用されます。また、さまざまなレベルがあります。 たとえば、mail.contoso.com は次の 3 つのレベルを持つドメイン名です。
  
- **.com** はトップレベル ドメインです 
    
- **contoso** は第 2 レベル ドメインです 
    
- **mail** は第 3 レベル ドメインです 
    
第 3 レベル ドメインはなぜ必要なのでしょうか。 それは、マーケティングやブログで異なるドメイン名、 たとえば blog.contoso.com などを使いたい場合があるからです。 Microsoft で利用できるように contoso.com のような第 2 レベル ドメインを追加することは一般的ですが、第 3 レベル ドメインを利用することも可能です。
  
それぞれのドメインの機能の詳細については、[Microsoft 365 および Office 365 プラットフォーム サービスの説明](/office365/servicedescriptions/office-365-platform-service-description/domains)を参照してください。
  
## <a name="understand-dns-record-types"></a>DNS レコードの種類について

自分のドメインの DNS ホストに保存される DNS レコードを使用して、トラフィックをそのドメインへと導くことができます。 次の表では、よく使われる DNS レコードとその使用方法について説明します。
  
|**NS (ネームサーバー) レコード**|**ドメインの正式なネーム サーバーを識別します。 これらのネームサーバーを変更すると、DNS レコードが管理される場所および DNS システムがメール サーバーなどについての情報を探す場所が変わります。Microsoft は独自のネームサーバーを持ちます。あるいは、自身のドメインと共に設定しているネームサーバーを使用することもできます。**|
|:-----|:-----|
|A レコード (アドレス レコード)  <br/> |ドメイン名を IP アドレスに関連付けます。  <br/> |
|CNAME (別名または正規名) レコード  <br/> |あるドメインを DNS システム内の別のドメインにリダイレクトします。ネーム サーバーがドメインを検索し、CNAME レコードを見つけると、先頭のドメイン名を CNAME で置換し、新しい名前を検索します。  <br/> |
|MX (メール エクスチェンジャー) レコード  <br/> |電子メールの送り先を示します。また、このレコードには、メールを優先度の順序で異なるサーバーに送ることができるように、優先度フィールドも含まれます。  <br/> |
|SPF (Sender Policy Framework) レコード  <br/> |TXT レコードで、メールのスプーフィングやフィッシングを防ぐために役立ちます。  <br/> |
|SRV (サービス) レコード  <br/> |Skype for Business Online や Exchange Online で、Microsoft サービス間の情報フローを調整するために使われます。たとえば、SRV レコードは、Outlook Web App でプレゼンスを表示するため、また他の会社のユーザーと Skype for Business Online、Skype、またはその他のインスタント メッセージング ツールを使うために必要です。  <br/> |
|TTL (time-to-live)  <br/> |ネーム サーバーは、この時間の分だけ DNS レコードを保持した後、更新バージョンを探します。  <br/> |
   
## <a name="how-does-dns-work"></a>DNS のしくみ

Microsoft 365 などのクラウド サービスでドメインをセットアップするときには、そのドメインの [DNS レコード](dns-basics.md)の変更や追加が必要になります。そのような変更が必要になる理由は、メールの送り先や Web サイトの場所を探すために、インターネットが DNS (ドメイン ネーム システム) とドメイン名を使用しているためです。 
  
インターネットは DNS (ドメイン ネーム システム) を使うように設定され、それによってユーザーはわかりやすい名前 (contoso.com など) を使ってインターネット上の特定の場所を見つけることができますが、実際には覚えにくい IP (インターネット プロトコル) アドレスと呼ばれる数字が割り当てられています。IP アドレスは 70.42.241.42 のように表示されるため、ドメイン名を使うほうがメール ホストや Web サイトなどの場所を簡単に特定できます。
  
つまり、インターネットでは、DNS レコードによって、ドメイン名を使ったメールの送り先 (joe@contoso.com など) や Web サイトの場所 (www.contoso.com など) がわかるということです。DNS レコードにドメインの情報が正確に設定されていれば、DNS システムによって適切にルーティングされるため、メールは Microsoft 365 だけに届きます。
  
ドメインの DNS レコードは、他のことでも役に立ちます。 たとえば、Exchange は DNS レコードをチェックして、Outlook が正しい Exchange サーバーとの接続を自動的にセットアップすることを確認します。
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS レコードによってインターネットが正しい宛先にメールを届けるしくみ

上で説明したとおり、DNS はわかりやすいドメイン名を覚えにくい IP アドレスにマッピングして、トラフィックをインターネット上で転送しています。 DNS レコードの 1 つである MX レコードは、正しいホストにメールを送るためのものです。
  
DNS レコードは、ドメイン情報のデータベースのようなものです。レコードとレコード値は、各ドメインに対するレコードとレコード値のリストが含まれたゾーン ファイルと呼ばれる場所に保持されます。ドメイン レジストラーや DNS をホストする会社は、ユーザーにドメインのゾーン ファイルのレコードを編集するための UI を Web サイトで提供します。ユーザーは、その UI を使って、ドメインに対する MX レコードを更新し、メール メッセージを Microsoft 365 に送信できるようになります。
  
 *次の手順で、ドメインの MX レコードを更新することでメールを Microsoft 365 に変更すると、そのドメインに送信されたすべてのメールが Microsoft 365 に届くようになります。*  他のユーザーがメール用にそのドメインを使用する場合は、それらのユーザーごとに Microsoft 365 メールボックスをセットアップする必要があります。 
  
Microsoft ドメインのセットアップは複雑そうに思うかもしれませんが、手順については、詳しく説明します。
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS によって Web サイトを探す場所がわかる

Web サイトのアドレス (例: www.contoso.com) を入力すると、DNS サーバーの 1 つ (ここでは contoso.com) で、ネーム サーバー (NS) レコードと呼ばれるものが、最初にインターネット上で検索されます。インターネットでは、NS レコードによって、ドメインに対する他のすべての DNS レコード値を持つゾーン ファイルの場所が認識されます。DNS サーバーの数は多く、すべてが互いに接続されています。すべてのサーバーでは、登録されているすべての一意のドメイン名とドメインのゾーン ファイルの場所を互いに認識しています。
  
::: moniker range="o365-worldwide"

たとえば、contoso.com に対する NS レコードに "godaddy.com" という値があるとします。それにより、インターネット上で、contoso.com に対する他のすべての DNS レコードのリストを含むゾーン ファイルが GoDaddy.com にあることがわかります。それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。たとえば、MX レコードに "メールを Microsoft 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが Office 365 に送信されます。そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。

::: moniker-end

::: moniker range="o365-21vianet"

たとえば、contoso.com に対する NS レコードに "hichina.com" という値があるとします。それにより、インターネット上で、contoso.com に対する他のすべての DNS レコードのリストを含むゾーン ファイルが hichina.com にあることがわかります。それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。たとえば、MX レコードに "メールを Microsoft 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが送信されます。そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。

::: moniker-end

ドメインのセットアップ時に、Microsoft 365 を操作するために入力が必要な実際の値は、ドメインのセットアップ手順に記載されています。手動でセットアップを実行する場合は、それらの値をコピーして、自分の DNS ホスト (ドメイン レジストラーなど) で正しい DNS レコード (MX レコード、CNAME レコードなど) に貼り付けます。
  
::: moniker range="o365-worldwide"

自分のドメイン レジストラー以外の場所に自分のドメインのゾーン ファイルがある理由はなんでしょうか。 ドメイン名を GoDaddy のようなドメイン レジストラーに登録しても、自分の DNS レコードは別の場所 (別の DNS をホストする会社や Web をホストする会社) で管理できます。 ドメインに対する NS レコードにはその情報が格納されているため、どこを探すべきかすべての DNS サーバーにわかるのです。

::: moniker-end

::: moniker range="o365-21vianet"

自分のドメイン レジストラー以外の場所に自分のドメインのゾーン ファイルがある理由はなんでしょうか。 ドメイン名を HiChina のようなドメイン レジストラーに登録しても、自分の DNS レコードは別の場所 (別の DNS をホストする会社や Web をホストする会社) で管理できます。 ドメインに対する NS レコードにはその情報が格納されているため、どこを探すべきかすべての DNS サーバーにわかるのです。

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Microsoft 365 でドメインを追加するのはなぜですか?


Microsoft 365 に fourthcoffee.com などのカスタム ドメインを追加すると、短くて親しみやすいメール アドレスやユーザー ID をサービスで使えるようになります。 Microsoft 365 アカウントにサインアップすると、[使用するドメインが割り当てられます](../setup/domains-faq.yml)が、ドメイン名には "onmicrosoft.com" が含まれています。ユーザーの多くは、Microsoft 365 のメールを使う予定がある場合、組織やビジネスのドメインを追加することを選びます。 
  
> [!NOTE]
> Outlook や Word などの Microsoft アプリをダウンロードして使うだけであれば、ドメインを追加する必要はありません。その場合は、[PC または Mac に Office をインストールしてください](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。 
  
Microsoft 365 では、ドメイン名をメール、一般向け Web サイト、インスタント メッセージング アドレスに使うことができます。
  
- **メール:** 自分のドメイン名を使ってメールをカスタマイズできるため、アカウントに割り当てられた [初期設定の onmicrosoft.com メール アドレス](../setup/domains-faq.yml)よりも短くて覚えやすいアドレスを使うことができます。したがって、(Microsoft 365 にサインインするための 職場のアカウント でもある) メール アドレスを、joe@contoso.onmicrosoft.com から、たとえば joe@contoso.com に変更できます。 
    
- **Web サイト:** Microsoft 365 サブスクリプションに SharePoint Online Public Web サイト (現在では非売品) が含まれる場合は、一般向け Web サイトには contoso-public.sharepoint.com のような初期アドレスが割り当てられます。 会社の Web サイトを設定する場合は、 カスタム ドメイン名を使用して Web サイトのアドレスを変更して、www.contoso.com などにできます。 
    
- **インスタント メッセージング**: Skype for Business Online アドレスもドメイン名を使うようにカスタマイズできるため、組織内のユーザーは、短くて覚えやすいアドレス (joe@contoso.com など) を使って Skype for Business Online で相互接続できるようになります。 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Microsoft 365 に必要な DNS レコード

ドメインで Microsoft 365 を使用するには、いくつかの DNS レコードが必要です。メールを Microsoft 365 に送信するためのドメインの MX レコードのセットアップのほか、Outlook と正しい Exchange サーバーとの自動接続の確認、インスタント メッセージングのセットアップ、迷惑メールからの保護などの作業に役立つレコードもあります。
  
ドメインをセットアップするには、<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsoft 365 管理センター</a>の[値の一覧を参照](information-for-dns-records.md)してください。 
  
また、展開を予定している場合は、Microsoft 365 に必要なすべての外部ドメイン ネーム システムの レコードの一覧、それぞれのレコードの機能、値の例も確認してください。 「[Microsoft 365 の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)」を確認してください。
  
## <a name="next-steps"></a>次の手順

次のいずれかを確認してください。 
  
- ドメインが登録されている場所を確認するには、「[ドメイン レジストラーの検索方法](find-your-domain-registrar.md)」を参照してください。
- Microsoft 365 でドメインを使う前に、「[ウィザードの手順の完了が必要な理由](../setup/add-domain.md)」を確認してください。

## <a name="related-content"></a>関連コンテンツ

[ドメインの FAQ](../setup/domains-faq.yml) (記事)\
[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)\
[ドメインの管理](/admin) (リンク ページ)