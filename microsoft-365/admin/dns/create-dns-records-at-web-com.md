---
title: Microsoft 向け web.com DNS レコードを作成する
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
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを microsoft web.comセットアップする方法について説明します。
ms.openlocfilehash: 943070f3790f532a0cc686270e0ecdea08f802fd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656893"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>Microsoft 向け web.com DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
使用web.com DNS ホスティング プロバイダーである場合は、この記事の手順に従って、ドメインを確認し、メールや Skype for Business Online などのために DNS レコードを設定します。
  
これらのレコードを web.comすると、ドメインは Microsoft サービスで動作する設定に設定されます。

  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。 
  
ユーザーアカウントにサインアップweb.comセットアップ プロセスを使用してドメインweb.com **追加** しました。 
  
Microsoft でドメインの DNS レコードを確認して作成するには、まず、web.com のネームサーバーを使用するために、ドメイン レジストラーでネームサーバーを変更する必要があります。
  
ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。
    
    |||
    |:-----|:-----|
    |1 番目のネーム サーバー  <br/> |指定されたネームサーバー値を使用web.com。  <br/> |
    |2 番目のネーム サーバー  <br/> |指定されたネームサーバー値を使用web.com。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 一覧に他のネーム サーバーがある場合は、それらを削除する必要があります。 
  
3. 変更内容を保存します。
    
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 最初にログインします。
  
2. [アカウント マネージャー **] ページで** 、[自分のドメイン名 **] を選択します**。 
  
3. Under **Manage *my domain***, select **Edit Advanced DNS Records**.

  
4. [Domain **Names] ページ** の **[Text (TXT Records)**] で **、[Edit TXT Records]** をクリックし、次の表から値を選択します。 
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. [続行] **を選択します**。
  
  
6. 数分待って新しい TXT レコードを確認し、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 最初にログインします。
  
2. [アカウント マネージャー **] ページで** 、[自分のドメイン名 **] を選択します**。 
  
3. Under **Manage *my domain***, select **Edit Advanced DNS Records**.

4. [**メール サーバー (MX レコード)] で****、[MX** レコードの編集] をクリックし、次の表の値を選択します。 
    
    |**Priority**|**TTL**|**メール サーバー**|
    |:-----|:-----|:-----|
    |1   <br/> 優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> |3600  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md) |
   

5. **[保存]** を選択します。
  
6. IF there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete,** and select **Save**. 
  
7. 確認画面で、[変更の保存] **を選択します**。 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な Six CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 最初にログインするように求められます。
     
2. [アカウント マネージャー **] ページで** 、[自分のドメイン名 **] を選択します**。 
  
3. Under **Manage *my domain***, select **Edit Advanced DNS Records**.

4. 6 つの CNAME レコードの最初のレコードを追加します。
    
    [ **ホスト エイリアス (CNAME レコード)**] で **、[CNAME** レコードの編集] をクリックし、次の表の値を選択します。
    
    
    |**Alias**|**TTL**|**Refers to Host Name**|**その他のホスト**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (なし)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (なし)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (なし)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (なし)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (なし)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (なし)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. [続行] **を選択します**。
  
6. 他の 5 つの CNAME レコードをそれぞれ追加します。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。 
  
1. To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 最初にログインします。
    
  
2. [アカウント マネージャー **] ページで** 、[自分のドメイン名 **] を選択します**。 
  
3. Under **Manage *my domain***, select **Edit Advanced DNS Records**.

  
4. [Domain **Names] ページ** の **[Text (TXT Records)**] で **、[Edit TXT Records]** をクリックし、次の表から値を選択します。   
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。   |

 
5. [続行] **を選択します**。

6. [**変更の保存**] を選択します。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> この機能を利用するにはweb.comが必要です。 以下の手順と現在のグラフィカル ユーザー インターフェイス (グラフィカル ユーザー インターフェイス) の間でweb.comが表示される場合は、このコミュニティ [web.comしてください](https://community.web.com.com/)。 

1. To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp). 最初にログインします。
      
2. [アカウント マネージャー **] ページで** 、[自分のドメイン名 **] を選択します**。 
  
3. Under **Manage *my domain***, select **Edit Advanced DNS Records**.
  
4. 2 つの SRV レコードの最初のレコードを追加します。

    [**サービス (SRV レコード) ] で****、[SRV レコード** の編集] をクリックし、次の表の値を選択します。 
        
    |**Service**|**Protocol**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1  |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1  |5061 | sipfed.online.lync.com |

  
5. テーブルの 2 行目の値を選択して、他の SRV レコードを追加します。 
  
6. [続行] **を選択します**。

7. [**変更の保存**] を選択します。

    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
