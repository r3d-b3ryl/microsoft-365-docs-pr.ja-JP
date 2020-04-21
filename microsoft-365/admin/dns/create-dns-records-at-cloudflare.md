---
title: Cloudflare で Microsoft 用の DNS レコードを作成する
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、電子メール、Skype for Business Online、および Cloudflare for Microsoft の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: f04e4b4a29085a3ddd9b388c7178c1cd638445ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629709"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>Cloudflare で Microsoft 用の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
  
Cloudflare でこれらのレコードを追加すると、使用しているドメインが、Microsoft 365 サービスで機能するように設定されます。
  
Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。 
  
Cloudflare にサインアップしたときに、Cloudflare の [ **Setup**] プロセスを使用してドメインを追加しました。 
  
追加したドメインは、別のドメインレジストラーから購入されました。Cloudflare では、ドメイン登録サービスは提供されていません。 Microsoft 365 でドメインの DNS レコードを確認および作成するには、まず、Cloudflare のネームサーバーを使用するようにドメインレジストラーでネームサーバーを変更する必要があります。
  
ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。
    
    |||
    |:-----|:-----|
    |1 番目のネーム サーバー  <br/> |Cloudflare によって提供されるネーム サーバーの値を使用します。  <br/> |
    |2 番目のネーム サーバー  <br/> |Cloudflare によって提供されるネーム サーバーの値を使用します。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 他のネームサーバーが表示されている場合は、それらを削除する必要があります。 
  
3. 変更内容を保存します。
    
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。 ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。 最初にログインするように求められます。
  
2. [**ホーム**] ページで、更新するドメインを選択します。 
  
3. ドメインの [**概要**] ページで、[ **DNS**] を選択します。

  
4. [ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。 
    
    |**Type**|**Name**|**Automatic TTL**|**Content**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 分  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. **[保存]** を選択します。
  
  
9. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを検索します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
  
2. [**ホーム**] ページで、更新するドメインを選択します。 
  
3. ドメインの [**概要**] ページで、[ **DNS**] を選択します。

  
4. [ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。 
    
    |**Type**|**名前**|**メール サーバー**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<ドメインキー\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft 365 アカウントから* \<ドメイン\>キー*を取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md) |1-d  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/>|30 分  <br/> |
   

  
5. **[保存]** を選択します。
  
9. [ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、[ **Delete (X)**] アイコンを選択してそれらを削除します。 
  
10. 確認ダイアログボックスで、[**削除**] を選択して変更を確認します。 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な6つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
    
  
2. [**ホーム**] ページで、更新するドメインを選択します。 
  
3. ドメインの [**概要**] ページで、[ **DNS**] を選択します。

  
4. 5つの CNAME レコードの最初のレコードを追加します。
    
    [ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。
    
    
    |**Type**|**Name**|**Target**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutes  <br/> |
    
  
5. [ **DNS トラフィック**] アイコン (オレンジのクラウド) を選択して、cloudflare サーバーをバイパスします。
  
6. **[保存]** を選択します。
  
7. 他の 5 つの CNAME レコードをそれぞれ追加します。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインに対して既に SPF レコードがある場合は、Microsoft 365 用に新しいを作成しないでください。 代わりに、必要な Microsoft 365 値を現在のレコードに追加して、両方の値が含まれる*1 つ*の SPF レコードを作成できるようにします。 
  
1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。 最初にログインするように求められます。
    
  
2. [**ホーム**] ページで、更新するドメインを選択します。 
  
3. ドメインの [**概要**] ページで、[ **DNS**] を選択します。

  
4. [ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。  
    
    |**Type**|**名前**|**TTL**|**Content**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 分  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。   |

 
5. **[保存]** を選択します。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft に必要な2つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Cloudflare は、この機能を使用できるようにする必要があることに留意してください。 次の手順と現在の Cloudflare GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Cloudflare コミュニティ](https://community.cloudflare.com/)を活用してください。 

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。 最初にログインするように求められます。
      
2. [**ホーム**] ページで、更新するドメインを選択します。 
  
3. ドメインの [**概要**] ページで、[ **DNS**] を選択します。
  
4. 2 つの SRV レコードの最初のレコードを追加します。

    [ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の1行目の値を選択します。
        
    |**Type**|**Service**|**Protocol**|**Name**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |*Domain_name*を使用します。たとえば、contoso.com  |30 分 | 100|1-d |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|*Domain_name*を使用します。たとえば、contoso.com   |30 分 |100 |1-d |5061 | sipfed.online.lync.com |

  
5. **[保存]** を選択します。

  
6. 表の2行目の値を選択して、他の SRV レコードを追加します。 

    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
