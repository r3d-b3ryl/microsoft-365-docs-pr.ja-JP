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
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Office 365 ドメイン管理に役立つドメインとそれに関連する DNS レコードについて説明します。
ms.openlocfilehash: 4fd41102193a9e630ed04a9d1fb2e196dc94486b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210470"
---
# <a name="dns-basics"></a>DNS の基本

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
::: moniker range="o365-worldwide"

contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。DNS とドメイン レジストラーの基礎を理解することは、管理者が Office 365 でドメインを管理するうえで役立ちます。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。DNS とドメイン レジストラーの基礎を理解することは、管理者が Office 365 でドメインを管理するうえで役立ちます。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

contoso.com のようなドメイン名は、ドメイン レジストラーの世界中のシステムとデータベースを使って管理されています。 ドメイン ネーム システム (DNS) は、人間が判読できるコンピューター ホスト名とネットワーク機器によって使用される IP アドレス間のマッピングを提供します。 DNS とドメイン レジストラーの基本を理解することで、管理者は 21Vianet によって運営される Office 365 のドメインを管理できます。
  
::: moniker-end

## <a name="what-are-domain-names"></a>ドメイン名とは

ドメイン名は URL とメール アドレスで使用されます。また、さまざまなレベルがあります。 たとえば、mail.contoso.com は次の 3 つのレベルを持つドメイン名です。
  
- **.com** はトップレベル ドメインです 
    
- **contoso** は第 2 レベル ドメインです 
    
- **mail** は第 3 レベル ドメインです 
    
第 3 レベル ドメインはなぜ必要なのでしょうか。 それは、マーケティングやブログで異なるドメイン名、 たとえば blog.contoso.com などを使いたい場合があるからです。 Office 365 で利用できるように contoso.com のような第 2 レベル ドメインを追加することは一般的ですが、第 3 レベル ドメインを利用することも可能です。
  
それぞれのドメインの機能の詳細については、[Office 365 サービスの各種ドメインの説明](https://go.microsoft.com/fwlink/?LinkId=402693)を参照してください。
  
## <a name="understand-dns-record-types"></a>DNS レコードの種類について

自分のドメインの DNS ホストに保存される DNS レコードを使用して、トラフィックをそのドメインへと導くことができます。 次の表では、よく使われる DNS レコードと、Office 365 での使われ方について説明します。
  
|**NS (ネームサーバー) レコード**|**ドメインの正式なネーム サーバーを識別します。 これらのネームサーバーを変更すると、DNS レコードが管理される場所および DNS システムがメール サーバーなどについての情報を探す場所が変わります。 Office 365 は独自のネームサーバーを持ちます。あるいは、自身のドメインと共に設定しているネームサーバーを使用することもできます。**|
|:-----|:-----|
|A レコード (アドレス レコード)  <br/> |ドメイン名を IP アドレスに関連付けます。  <br/> |
|CNAME (別名または正規名) レコード  <br/> |あるドメインを DNS システム内の別のドメインにリダイレクトします。ネーム サーバーがドメインを検索し、CNAME レコードを見つけると、先頭のドメイン名を CNAME で置換し、新しい名前を検索します。  <br/> |
|MX (メール エクスチェンジャー) レコード  <br/> |電子メールの送り先を示します。また、このレコードには、メールを優先度の順序で異なるサーバーに送ることができるように、優先度フィールドも含まれます。  <br/> |
|SPF (Sender Policy Framework) レコード  <br/> |TXT レコードで、メールのスプーフィングやフィッシングを防ぐために役立ちます。  <br/> |
|SRV (サービス) レコード  <br/> |Skype for Business Online や Exchange Online で、Office 365 サービス間の情報フローを調整するために使われます。たとえば、SRV レコードは、Outlook Web App でプレゼンスを表示するため、また他の会社のユーザーと Skype for Business Online、Skype、またはその他のインスタント メッセージング ツールを使うために必要です。  <br/> |
|TTL (time-to-live)  <br/> |ネーム サーバーは、この時間の分だけ DNS レコードを保持した後、更新バージョンを探します。  <br/> |
   
## <a name="how-does-dns-work"></a>DNS のしくみ

Office 365 などのクラウド サービスでドメインをセットアップするときには、そのドメインの [DNS レコード](dns-basics.md)の変更や追加が必要になります。そのような変更が必要になる理由は、メールの送り先や Web サイトの場所を探すために、インターネットが DNS (ドメイン ネーム システム) とドメイン名を使用しているためです。 
  
インターネットは DNS (ドメイン ネーム システム) を使うように設定され、それによってユーザーはわかりやすい名前 (contoso.com など) を使ってインターネット上の特定の場所を見つけることができますが、実際には覚えにくい IP (インターネット プロトコル) アドレスと呼ばれる数字が割り当てられています。IP アドレスは 70.42.241.42 のように表示されるため、ドメイン名を使うほうがメール ホストや Web サイトなどの場所を簡単に特定できます。
  
つまり、インターネットでは、DNS レコードによって、ドメイン名を使ったメールの送り先 (joe@contoso.com など) や Web サイトの場所 (www.contoso.com など) がわかるということです。DNS レコードにドメインの情報が正確に設定されていれば、DNS システムによって適切にルーティングされるため、メールは Office 365 だけに届きます。
  
ドメインの DNS レコードは、他のことでも役に立ちます。 たとえば、Exchange は DNS レコードをチェックして、Outlook が正しい Exchange サーバーとの接続を自動的にセットアップすることを確認します。
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS レコードによってインターネットが正しい宛先にメールを届けるしくみ

上で説明したとおり、DNS はわかりやすいドメイン名を覚えにくい IP アドレスにマッピングして、トラフィックをインターネット上で転送しています。 DNS レコードの 1 つである MX レコードは、正しいホストにメールを送るためのものです。
  
DNS レコードは、ドメイン情報のデータベースのようなものです。レコードとレコード値は、各ドメインに対するレコードとレコード値のリストが含まれたゾーン ファイルと呼ばれる場所に保持されます。ドメイン レジストラーや DNS をホストする会社は、ユーザーにドメインのゾーン ファイルのレコードを編集するための UI を Web サイトで提供します。ユーザーは、その UI を使って、ドメインに対する MX レコードを更新し、メール メッセージを Office 365 に送信できるようになります。
  
 *次の手順で、ドメインの MX レコードを更新することでメールを Office 365 に変更すると、そのドメインに送信されたすべてのメールが Office 365 に届くようになります。*  他のユーザーがメール用にそのドメインを使用する場合は、それらのユーザーごとに Office 365 メールボックスをセットアップする必要があります。 
  
Office 365 ドメインのセットアップは複雑そうに思うかもしれませんが、手順については、詳しく説明します。
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS によって Web サイトを探す場所がわかる

Web サイトのアドレス (例: www.contoso.com) を入力すると、DNS サーバーの 1 つ (ここでは contoso.com) で、ネーム サーバー (NS) レコードと呼ばれるものが、最初にインターネット上で検索されます。インターネットでは、NS レコードによって、ドメインに対する他のすべての DNS レコード値を持つゾーン ファイルの場所が認識されます。DNS サーバーの数は多く、すべてが互いに接続されています。すべてのサーバーでは、登録されているすべての一意のドメイン名とドメインのゾーン ファイルの場所を互いに認識しています。
  
::: moniker range="o365-worldwide"

たとえば、contoso.com に対する NS レコードに "godaddy.com" という値があるとします。それにより、インターネット上で、contoso.com に対する他のすべての DNS レコードのリストを含むゾーン ファイルが GoDaddy.com にあることがわかります。それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。たとえば、MX レコードに "メールを Office 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが Office 365 に送信されます。そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。

::: moniker-end

::: moniker range="o365-germany"

たとえば、contoso.com に対する NS レコードに "godaddy.com" という値があるとします。それにより、インターネット上で、contoso.com に対する他のすべての DNS レコードのリストを含むゾーン ファイルが GoDaddy.com にあることがわかります。それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。たとえば、MX レコードに "メールを Office 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが Office 365 に送信されます。そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。

::: moniker-end

::: moniker range="o365-21vianet"

contoso.com の NS レコードに「hichina.com」と記載するとします。 これで、インターネットは、hichina.com が contoso.com の他のすべての DNS レコードを一覧表示したゾーン ファイルを探す場所であることを認識できます。 それらの DNS レコードには、contoso.com 宛てのメールの送信先を指定する MX レコードと他のレコードが含まれます。 たとえば、MX レコードに "メールを Office 365 に送信する" という意味の値が含まれている場合は、contoso.com のメール アドレス (joe@contoso.com など) に送信されるすべてのメール メッセージが Office 365 に送信されます。 そして、その場所に "joe" というメールボックスがある場合は、メールが配信されます。

::: moniker-end

ドメインのセットアップ時に、Office 365 を操作するために入力が必要な実際の値は、ドメインのセットアップ手順に記載されています。手動でセットアップを実行する場合は、それらの値をコピーして、自分の DNS ホスト (ドメイン レジストラーなど) で正しい DNS レコード (MX レコード、CNAME レコードなど) に貼り付けます。
  
::: moniker range="o365-worldwide"

自分のドメイン レジストラー以外の場所に自分のドメインのゾーン ファイルがある理由はなんでしょうか。 ドメイン名を GoDaddy のようなドメイン レジストラーに登録しても、自分の DNS レコードは別の場所 (別の DNS をホストする会社や Web をホストする会社) で管理できます。 ドメインに対する NS レコードにはその情報が格納されているため、どこを探すべきかすべての DNS サーバーにわかるのです。

::: moniker-end

::: moniker range="o365-germany"

自分のドメイン レジストラー以外の場所に自分のドメインのゾーン ファイルがある理由はなんでしょうか。 ドメイン名を GoDaddy のようなドメイン レジストラーに登録しても、自分の DNS レコードは別の場所 (別の DNS をホストする会社や Web をホストする会社) で管理できます。 ドメインに対する NS レコードにはその情報が格納されているため、どこを探すべきかすべての DNS サーバーにわかるのです。

::: moniker-end

::: moniker range="o365-21vianet"

ドメインのゾーン ファイルがドメイン レジストラー以外の場所にあるのはなぜですか? HiChina のようなドメイン レジストラーでドメイン名を登録することもできますが、DNS レコードは別の DNS ホスティング会社や Web ホスティング会社で管理されているかもしれません。 ドメインの NS レコードには、その情報が格納されます。これにより、すべての DNS サーバーが検索対象を把握できます。

::: moniker-end

> [!NOTE]
> Office 365 でドメインをセットアップし、[Office 365 が DNS レコードをセットアップして管理する](../setup/domains-faq.md#how-does-office-365-manage-my-dns-records)ようにして、セットアップの一環として、 [DNS 管理を Office 365 に変更](../setup/domains-faq.md#change-dns-management-to-office-365)します。 
 

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-office-365"></a>Office 365 でドメインを追加するのはなぜですか?


Office 365 に fourthcoffee.com などのカスタム ドメインを追加すると、短くて親しみやすいメール アドレスやユーザー ID をサービスで使えるようになります。 Office 365 アカウントにサインアップすると、[使用するドメインが割り当てられます](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx)が、ドメイン名には "onmicrosoft.com" が含まれています。ユーザーの多くは、Office 365 のメールを使う予定がある場合、組織やビジネスのドメインを追加することを選びます。 
  
> [!NOTE]
> Outlook や Word などの Office 365 アプリをダウンロードして使うだけであれば、ドメインを追加する必要はありません。その場合は、[PC または Mac に Office をインストールしてください](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)。 
  
Office 365 では、ドメイン名をメール、一般向け Web サイト、インスタント メッセージング アドレスに使うことができます。
  
- **メール:** 自分のドメイン名を使ってメールをカスタマイズできるため、アカウントに割り当てられた [初期設定の onmicrosoft.com メール アドレス](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx)よりも短くて覚えやすいアドレスを使うことができます。したがって、(Office 365 にサインインするための 職場のアカウント でもある) メール アドレスを、joe@contoso.onmicrosoft.com から、たとえば joe@contoso.com に変更できます。 
    
- **Web サイト:** Office 365 サブスクリプションに SharePoint Online Public Web サイト (現在では非売品) が含まれる場合は、一般向け Web サイトには contoso-public.sharepoint.com のような初期アドレスが割り当てられます。 会社の Web サイトを設定する場合は、 カスタム ドメイン名を使用して Web サイトのアドレスを変更して、www.contoso.com などにできます。 
    
- **インスタント メッセージング**: Skype for Business Online アドレスもドメイン名を使うようにカスタマイズできるため、組織内のユーザーは、短くて覚えやすいアドレス (joe@contoso.com など) を使って Skype for Business Online で相互接続できるようになります。 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-office-365"></a>Office 365 でドメインを追加するのはなぜですか?


Office 365 に fourthcoffee.com などのカスタム ドメインを追加すると、短くて親しみやすいメール アドレスやユーザー ID をサービスで使えるようになります。 Office 365 アカウントにサインアップすると、[使用するドメインが割り当てられます](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx)が、ドメイン名には "onmicrosoft.com" が含まれています。ユーザーの多くは、Office 365 のメールを使う予定がある場合、組織やビジネスのドメインを追加することを選びます。 
  
> [!NOTE]
> Outlook や Word などの Office 365 アプリをダウンロードして使うだけであれば、ドメインを追加する必要はありません。その場合は、[PC または Mac に Office をインストールしてください](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)。 
  
Office 365 では、ドメイン名をメール、一般向け Web サイト、インスタント メッセージング アドレスに使うことができます。
  
- **メール:** 自分のドメイン名を使ってメールをカスタマイズできるため、アカウントに割り当てられた [初期設定の onmicrosoft.com メール アドレス](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx)よりも短くて覚えやすいアドレスを使うことができます。したがって、(Office 365 にサインインするための 職場のアカウント でもある) メール アドレスを、joe@contoso.onmicrosoft.com から、たとえば joe@contoso.com に変更できます。 
    
- **Web サイト:** Office 365 サブスクリプションに SharePoint Online Public Web サイト (現在では非売品) が含まれる場合は、一般向け Web サイトには contoso-public.sharepoint.com のような初期アドレスが割り当てられます。 会社の Web サイトを設定する場合は、 カスタム ドメイン名を使用して Web サイトのアドレスを変更して、www.contoso.com などにできます。 
    
- **インスタント メッセージング**: Skype for Business Online アドレスもドメイン名を使うようにカスタマイズできるため、組織内のユーザーは、短くて覚えやすいアドレス (joe@contoso.com など) を使って Skype for Business Online で相互接続できるようになります。 
    
::: moniker-end

## <a name="the-dns-records-required-for-office-365"></a>Office 365 に必要な DNS レコード

ドメインで Office 365 を使用するには、いくつかの DNS レコードが必要です。メールを Office 365 に送信するためのドメインの MX レコードのセットアップのほか、Outlook と正しい Exchange サーバーとの自動接続の確認、インスタント メッセージングのセットアップ、迷惑メールからの保護などの作業に役立つレコードもあります。
  
ドメインをセットアップするには、Office 365 ポータルの[値の一覧を参照](information-for-dns-records.md)してください。 
  
また、展開を予定している場合は、Office 365 に必要なすべての DNS レコードの一覧、それぞれのレコードの機能、値の例も確認してください。 「[Office 365 の外部ドメイン ネーム システムのレコード](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)」を確認してください。
  
## <a name="how-can-i-learn-more"></a>さらに詳しく知るには

次のいずれかを確認してください。 
  
- ドメインが登録されている場所がわからない場合 [ドメイン レジストラーの検索に関するヘルプをご覧ください。](find-your-domain-registrar.md)
    
- Office 365 でドメインを使う前に、[ウィザードのステップの完了が必要な理由](../setup/add-domain.md)を確認してください。 
    

