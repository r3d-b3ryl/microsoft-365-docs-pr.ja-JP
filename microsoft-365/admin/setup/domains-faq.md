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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: ドメインの詳細については、よく寄せられる質問の回答を参照してください。
ms.custom: okr_smb
ms.openlocfilehash: 0b9b79c3cab74f4f809f0bd96ed5a51c17282ccd
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048163"
---
# <a name="domains-faq"></a>ドメイン FAQ

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

**SPF の TXT レコードを1つだけ**持っているか作成しておくことが重要です。既に SPF レコードがある場合は、新しい Office 365 の値を新しく作成するのではなく、そのレコードに追加する必要があります。Microsoft メールの SPF レコードを追加または更新した後、次のいずれかのツールを使用して構文が正しいことを確認してください。 
  
- [SPF レコード テスト ツール](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig Web インターフェイス](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Office 365 では DNS レコードはどのように管理されますか?

Office 365 での DNS 管理には 2 つのオプションがあります。
  
1. ネームサーバー (NS) レコードを変更すると、メール用の MX レコードを設定するのと同様に、Microsoft はすべてのサービス固有のレコードを処理できるようになります。**(推奨)**
    
2. DNS ホストで、メールやその他の Office 365 サービスに DNS レコードを自分で追加します。** (上級ユーザーのみ)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 で DNS レコードが作成され、ホストされます。 
**メリット** 
- Office 365 サービスの DNS レコードの入力ミスについて心配する必要がありません。  
- ドメインレジストラーと DNS ホストを自由に選べます。 
- ネーム サーバー レコードの変更を許可しているプロバイダーであれば、必要なレコード タイプの一部をサポートしていないプロバイダーであっても、問題なく機能します。   
- Office 365 が新しい DNS レコードを追加しても、ユーザーは更新を行う必要がありません。  

#### <a name="disadvantages"></a>デメリット 
- Office 365 の外部では、DNS レコードを変更してメールをホストすることができません。 
- 一般向け Web サイトのアドレス (例: www.fourthcoffee.com) としてドメインをすでに使用している場合、ユーザーを Office 365 からそのアドレスにリダイレクトする必要があります。 
- リダイレクトを設定するには静的 IP アドレスが必要ですが、一般向け WEB サイトのために常時利用できるとは限りません。ドメインのネーム サーバーの変更が現在のドメイン レジストラーで許可されない場合、この　DNS 管理オプションを使用するには別のレジストラーに切り替える必要があります。  

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


ドメインとは、メール アドレスの **@** 記号の後や、Web アドレスの **www.** の後に表示される固有の名前です。通常は、  *yourbusiness.com*  や  *stateuniversity.edu*  のように、組織の名前と標準的なインターネット サフィックスの形式を取ります。 
  
Office 365 で「**rob\@contoso.com**」のようなカスタム ドメインを使用すると、ブランドの信頼性や認知度を高めることができます。 
  
[Office 365 でドメインを購入して](../get-help-with-domains/buy-a-domain-name.md) 自動的に設定するか、ドメイン レジストラーで購入したり、入手済みのドメインを使用したりすることができます。
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>Microsoft から購入したドメインを別のプロバイダーに移行できますか。

はい。ただし Office 365 での購入後 60 日を経過するまでは、他のレジストラーに Office 365 ドメインを移行できません。

*Whois* クエリ上では Office 365 で購入したドメイン レジストラーが Wild West Domains LLC として表示されることにご注意ください。 ただし Office 365 で購入したドメインに関しては Office 365 にのみお問い合わせ可能です。
  
以下の手順に従って Office 365 からコードを取得し、その後別のドメイン レジストラーの Web サイトで、そのレジストラーへのドメイン名の移行を設定します。

::: moniker range="o365-worldwide"

1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

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
    
2. レジストラーの Web サイトで、ネームサーバー レコードの更新を行うエリアを見つけ、ネームサーバーのポイント先をドメインの DNS ホストに更新します (DNS ホストがドメイン レジストラーであることもよくあります)。
    
3. リンクにアクセスし、ドメインのセットアップ ウィザードに移動します。

::: moniker range="o365-worldwide"

4. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

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

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。

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
    
5. [ **DNS 設定の更新** ] ページに Office 365 のネームサーバーが一覧表示されます。自分のドメインのドメイン レジストラーに移動して、ネームサーバーを Office 365 ネームサーバーに更新します。 
    
4. ネームサーバーを更新したら、**1 時間以上待ちます**。 その後、Office 365 のウィザードに戻り、[**確認**] を選択します。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>DNS プロバイダーで特定のレコードの種類がサポートされない場合はどうなりますか?

独自の DNS レコードを管理している場合、DNS ホストが Office 365 に必要な DNS レコードの一部しかサポートしていないと、Office 365 の一部の機能は動作しません。必要な DNS レコードをすべてサポートしているレジストラーにドメインを移行することをお勧めします。
  
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
    
 **SPF/TXT レコードがサポートされない場合** 、他のユーザーがドメインを使用して、スパムまたはその他の悪意のあるメールを送信できる可能性があります。SPF レコードは、ユーザーのドメインからメールを送信することを承認されているサーバーを識別することで動作します。 
  
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

はい。サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。NS レコードの DNS 設定の管理を Microsoft が行っている場合または Microsoft からドメインを購入した場合は、サブドメインを追加できません。

::: moniker-end

::: moniker range="o365-germany"

はい。サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。NS レコードの DNS 設定の管理を Microsoft が行っている場合または Microsoft からドメインを購入した場合は、サブドメインを追加できません。

::: moniker-end

::: moniker range="o365-21vianet"

はい。サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。NS レコードの DNS 設定の管理を 21Vianet が行っている場合は、サブドメインを追加できません。

::: moniker-end

通常、最大 900 のドメインを Office 365 サブスクリプションに追加できます。
  
例えば、contoso.com と contosomaketing.com の各ドメインを追加し、その後に www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com などのサブドメインを追加することができます。
  
サブドメインを追加すると、確認が行われる親ドメインでの確認に基づき、自動的に確認されます。
  
複数のドメインを Office 365 に追加すると、追加した任意のドメインで任意のサービス (メールなど) をホストできます。 *ドメインの MX レコードを更新することでメールを Office 365 に変更すると、そのドメインに送信されたすべてのメールが Office 365 に届くようになります。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> contoso.com ドメインを既に Office 365 テナントに追加している場合は、サブドメイン xyz.contoso.com を別の Office 365 テナントに追加することもできます。 サブドメインを追加すると、DNS ホスティング プロバイダーに TXT レコードを追加するように求められます。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>"onmicrosoft.com" ドメインがあるのはなぜですか?

サービスにサインアップすると、Office 365 では、*contoso.onmicrosoft.com* のようなドメインが作成されます。サインアップ時に作成するユーザー ID には、*alan@contoso.onmicrosoft.com* のようなドメインが含まれています。 
  
 ***alan\@contoso.com* のように表示されるメール アドレスを希望する場合は、**[ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、または「[Office 365 にユーザーとドメインを追加する](add-domain.md)」の手順に従って操作します (既にドメインを所有している場合)。 
  
- **サインアップ後に onmicrosoft ドメインの名前は変更できません** 。たとえば、選んだ初期ドメインが fourthcoffee.onmicrosoft.com の場合、fabrikam.onmicrosoft.com に変更することはできません。別の onmicrosoft.com ドメインを使うには、Office 365 で新しいサブスクリプションを開始する必要があります。 
    
- **チーム サイトの URL の名前を変更することはできません。** チーム サイトの URL は onmicrosoft.com ドメイン名に基づいています。SharePoint Online のアーキテクチャの動作方法のため、残念ながらチーム サイトの名前は変更できません。 
    
- **onmicrosoft ドメインは、削除できません。** Office 365 では、サブスクリプションの処理に初期ドメインが必要なため、保持しておく必要があります。カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。 
    
ドメインを追加した後でも、初期の onmicrosoft.com ドメインを使うことができます。初期ドメインは、メールやその他のサービスでも引き続き利用できます。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>"onmicrosoft.de" ドメインがあるのはなぜですか?

サービスにサインアップすると、Office 365 では、*contoso.onmicrosoft.de* のようなドメインが作成されます。サインアップ時に作成するユーザー ID には、 *alan@contoso.onmicrosoft.de* のようなドメインが含まれています。 
  
 ***alan@contoso.de* のように表示されるメール アドレスを希望する場合は、**[ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、または「[Office 365 にユーザーとドメインを追加する](add-domain.md)」の手順に従って操作します (既にドメインを所有している場合)。 
  
- **サインアップ後に onmicrosoft ドメインの名前は変更できません**。たとえば、選んだ初期ドメインが fourthcoffee.onmicrosoft.de の場合、fabrikam.onmicrosoft.de に変更することはできません。別の onmicrosoft.de ドメインを使うには、Office 365 で新しいサブスクリプションを開始する必要があります。 
    
- **チーム サイトの URL の名前を変更することはできません。** チーム サイトの URL は onmicrosoft.de ドメイン名に基づいています。SharePoint Online のアーキテクチャの動作方法のため、残念ながらチーム サイトの名前は変更できません。 
    
- **onmicrosoft ドメインは、削除できません。** Office 365 では、サブスクリプションの処理に初期ドメインが必要なため、保持しておく必要があります。カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。 
    
ドメインを追加した後でも、初期の onmicrosoft.de ドメインを使うことができます。初期ドメインは、メールやその他のサービスでも引き続き利用できます。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>非営利団体または教育機関のステータスを確認するにはどうすればよいですか?

1. [管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-home)で [**セットアップ**] を選択してウィザードを開始します。 (最初に Office 365 にサインインしてください。) 
    
2. 学校の管理者になるには、Office 365 で [**管理者になる**] オプションを選択します。 
    
3. TXT DNS レコードをドメインの DNS ホスト Web サイトで追加するようメッセージが表示されます。この理由は、DNS ホストへサインインしてドメイン用のレコードを追加することにより、ユーザーがドメイン名の所有者だということが Office 365 で証明されるからです。
    
4. レコードを追加したら Office 365 ポータルに戻り、レコードを追加したことを確認します。そうすると、Office 365 で確認が行われます。
    
非営利団体で Office 365 の購入を検討している場合。[お客様の組織に資格があることを確認してから、](https://www.microsoft.com/en-us/nonprofits/eligibility)サービスにサインアップしてください。 
  
学校の管理者になる方法の詳細については、 [こちらのヘルプ記事をご覧ください](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>カスタム ドメインの少数のメール アドレスだけを使用して Office 365 の試験運用をすることは可能ですか?

可能ですが、制約があります。
  
- 現在のメール プロバイダーで、メール転送のサービスが提供されている必要があります。
    
- Office 365 関連の DNS レコードの管理を Office 365 に任せるのではなく、DNS ホスティング プロバイダーで自分で行う必要があります。DNS レコードを自分で管理する場合は、「Office 365 にドメインを追加する」を参照して手順を確認してください。
    
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
    
    1. Office 365 は Exchange Online Protection (EOP) を使用してスパム対策を行っています。EOP は、ユーザーの現在のメール サーバーから大量のスパムが転送されていることを検出するとそれをブロックし、そのため転送が機能しなくなる場合があります。もう 1 つのメール プロバイダーのスパム対策を信用することができる場合、Office 365 でそのサーバーをホワイトリストすることができます。ただしこの場合、元のサーバーを通して送信されるスパムは Office 365 のメールボックスに到達し、Office 365 のスパム対策の効果を評価することはできなくなります。
    
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
    
    1. DNS ホスティング プロバイダーの Web サイトにサインインし、「[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成する](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」の手順に沿って操作します。**以下の例外を設定します。**
    
        1. 新しい MX レコードは作成せず、既存の MX レコードの変更も行いません。
            
        2. 以前のメール プロバイダー用の Sender Policy Framework (SPF) が既にある場合、Exchange Online 用に新しい SPF (TXT) レコードを作成する代わりに、現在の TXT レコードに "include:spf.protection.outlook.com" を追加します。例: "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all"。
            
        3. SPF レコードがまだない場合は、Office 365 が推奨するレコードに変更を加えて現在のメール プロバイダー用のドメインを含め、spf.protection.outlook.com も含めます。両方のメール システムからの送信メッセージが承認されます。
            
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
        
    3. ローカル Microsoft メールをテストします。たとえば、ユーザー B に電子メールを送信します。この電子メールはすぐに配信されます。このシナリオでは、Office 365 はメールボックスをローカルとして認識するため、メッセージは元のサーバー上のユーザー B のメールボックスにルーティングされません。
        
    4. もう 1 つのメール システム上のユーザーへのメール送信をテストします。例えば、ユーザー C にメールを送信します。このメールは、元のサーバーにあるユーザー C のメールボックスに送信されるはずです。
        
    5. 外部アカウントから、または他の電子メールシステムの従業員の電子メールアカウントから、他のメールシステムで転送が正しく設定されていることを確認します。たとえば、User C の元のサーバーアカウントまたは Hotmail アカウントから、ユーザー A に電子メールを送信して、そのメールがユーザー A の Office 365 メールボックスに届くことを確認します。
        
9. メールボックスのコンテンツの移動
    
    1. 移動するユーザーが 2 人しかいなく、ユーザー A とユーザー B は既に 2 人とも Outlook を使用しているため、新しい Outlook プロファイルで古い .PST ファイルを開き、Outlook アイテムのインポートに表示されるメッセージ、予定表アイテム、連絡先などを Outlook データ ファイル (.pst) からコピーしてメールを移動させられます。 Office 365 メールボックスの正しい場所に一旦配置されると、アイテムはすべてのデバイスからどこからでもアクセスすることができます。
        
    2. より多数のメールボックスが関与する場合、または従業員がまだ Outlook を使用していない場合、Exchange 管理センターで提供される移行ツールを使用できます。開始するには、Exchange 管理センターへ移動し、「電子メールを IMAP サーバーから Exchange Online メールボックスに移行する」の手順に従います。
    
