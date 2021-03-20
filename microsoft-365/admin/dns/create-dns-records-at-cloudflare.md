---
title: Microsoft 用 Cloudflare で DNS レコードを作成する
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Cloudflare for Microsoft のドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910380"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>Microsoft 用 Cloudflare で DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
  
Cloudflare でこれらのレコードを追加すると、Microsoft 365 サービスで動作するドメインがセットアップされます。
  
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。 
  
Cloudflare にサインアップしたときに、Cloudflare の [ **Setup**] プロセスを使用してドメインを追加しました。 
  
追加したドメインは、Cloudflare または別のドメイン レジストラーから購入されました。 Microsoft 365 でドメインの DNS レコードを確認して作成するには、まず、Cloudflare のネームサーバーを使用するために、ドメイン レジストラーでネームサーバーを変更する必要があります。
  
ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。
    
    |||
    |:-----|:-----|
    |1 番目のネーム サーバー  <br/> |Cloudflare によって提供されるネーム サーバーの値を使用します。  <br/> |
    |2 番目のネーム サーバー  <br/> |Cloudflare によって提供されるネーム サーバーの値を使用します。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 他にネーム サーバーが一覧表示されている場合は、それらを削除する必要があります。 
  
3. 変更内容を保存します。
    
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft の電子メールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
  
2. [ホーム **] ページ** で、更新するドメインを選択します。 
  
3. ドメインの **[概要]** ページで **、[DNS] を選択します**。

  
4. **[DNS 管理] ページで**、[レコードの追加]**を** クリックし、次の表から値を選択します。 
    
    | 種類 | 氏名 | Automatic TTL | コンテンツ |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. **[保存]** を選択します。
  
  
9. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻ってレコードを検索します。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
  
2. [ホーム **] ページ** で、更新するドメインを選択します。 
  
3. ドメインの **[概要]** ページで **、[DNS] を選択します**。

  
4. **[DNS 管理] ページで**、[レコードの追加]**を** クリックし、次の表から値を選択します。 
    
    | 種類 | 氏名 | メール サーバー | Priority | TTL |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft  *\<domain-key\>*  365 アカウントから取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md) |1  <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。 <br/>|30 分  <br/> |
   

  
5. **[保存]** を選択します。
  
9. [ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、[ **Delete (X)**] アイコンを選択してそれらを削除します。 
  
10. 確認ダイアログ ボックスで、[削除] **を選択して** 変更を確認します。 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
    
  
2. [ホーム **] ページ** で、更新するドメインを選択します。 
  
3. ドメインの **[概要]** ページで **、[DNS] を選択します**。

  
4. 5 つの CNAME レコードの最初のレコードを追加します。
    
    **[DNS 管理] ページで**、[レコードの追加]**を** クリックし、次の表から値を選択します。
    
    
    | 種類 | 氏名 | Target | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutes  <br/> |
    
  
5. **[DNS トラフィック] アイコン**(オレンジ 色のクラウドを灰色に変更) を選択して、Cloudflare サーバーをバイパスします。
  
6. **[保存]** を選択します。
  
7. 他の 5 つの CNAME レコードをそれぞれ追加します。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが "*1 つ*" の SPF レコードに含まれるようにします。 
  
1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。 最初にログインするように求められます。
    
  
2. [ホーム **] ページ** で、更新するドメインを選択します。 
  
3. ドメインの **[概要]** ページで **、[DNS] を選択します**。

  
4. **[DNS 管理] ページで**、[レコードの追加]**を** クリックし、次の表から値を選択します。  
    
    | 種類 | 氏名 | TTL | コンテンツ |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。   |

 
5. **[保存]** を選択します。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> この機能を利用するには、Cloudflare が責任を負います。 以下の手順と現在の Cloudflare GUI (グラフィカル ユーザー インターフェイス) の間に不一致がある場合は [、Cloudflare コミュニティを活用してください](https://community.cloudflare.com/)。 

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。 最初にログインするように求められます。
      
2. [ホーム **] ページ** で、更新するドメインを選択します。 
  
3. ドメインの **[概要]** ページで **、[DNS] を選択します**。
  
4. 2 つの SRV レコードの最初のレコードを追加します。

    **[DNS 管理] ページで**、[レコードの追加]**を** クリックし、次の表の最初の行から値を選択します。
        
    | 種類 | サービス | プロトコル | 名前 | TTL | Priority | 太さ | ポート | Target |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |ユーザーのアカウント *をdomain_name。* たとえば、contoso.com  |30 分 | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|ユーザーのアカウント *をdomain_name。* たとえば、contoso.com   |30 分 |100 |1 |5061 | sipfed.online.lync.com |

  
5. **[保存]** を選択します。

  
6. テーブルの 2 行目から値を選択して、他の SRV レコードを追加します。 

    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
