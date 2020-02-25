---
title: Web.com for Office 365 で DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: ドメインを確認し、電子メール、Skype for Business Online、および web.com for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249457"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a>Web.com for Office 365 で DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
DNS ホスティングプロバイダーが web.com の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。
  
これらのレコードを web.com で追加すると、使用しているドメインが、Office 365 サービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。 
  
Web.com にサインアップしたときに、web.com**セットアップ**プロセスを使用してドメインを追加しました。 
  
Office 365 でドメインの DNS レコードを確認および作成するには、最初にドメインレジストラーでネームサーバーを変更して、web .com のネームサーバーを使用する必要があります。
  
ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。
    
    |||
    |:-----|:-----|
    |1 番目のネーム サーバー  <br/> |Web.com によって提供される nameserver 値を使用します。  <br/> |
    |2 番目のネーム サーバー  <br/> |Web.com によって提供される nameserver 値を使用します。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 他のネームサーバーが表示されている場合は、それらを削除する必要があります。 
  
3. 変更内容を保存します。
    
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。 
  
## <a name="add-a-txt-record-for-verification"></a>確認用に TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。 最初にログインします。
  
2. [**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。 
  
3. [* * Manage * my domain * * *] で、[ **ADVANCED DNS レコードの編集**] を選択します。

  
4. [ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。 
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. [**続行**] を選択します。
  
  
6. 新しい TXT レコードが確認されるまで数分待ってから、作成したレコードがインターネットを介して更新できるようにします。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

    
2. [**ドメイン**] ページで、確認するドメインを選択します。 
    
    
  
3. [**セットアップ**] ページで、[**セットアップの開始**] を選択します。
    
    
  
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。 最初にログインします。
  
2. [**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。 
  
3. [* * Manage * my domain * * *] で、[ **ADVANCED DNS レコードの編集**] を選択します。

4. [**メールサーバー (Mx records)**] で、[ **Mx レコードの編集**] をクリックし、次の表の値を選択します。 
    
    |**優先度**|**TTL**|**メール サーバー**|
    |:-----|:-----|:-----|
    |1-d  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |3600  <br/> |*\<ドメインキー\>*  .mail.protection.outlook.com  <br/> **注:** Office 365 アカウントから* \<ドメイン\>キー*を取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md) |
   

5. [**保存**] を選択します。
  
6. その他の MX レコードが [ **Mx records** ] セクションに表示されている場合は、[**削除**] でそのレコードの横にあるチェックボックスをオンにして、[**保存**] を選択します。 
  
7. 確認画面で、[**変更の保存**] を選択します。 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な6つの CNAME レコードを追加します。
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。 You'll be prompted to log in first.
     
2. [**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。 
  
3. [* * Manage * my domain * * *] で、[ **ADVANCED DNS レコードの編集**] を選択します。

4. 6 つの CNAME レコードの最初のレコードを追加します。
    
    [ **Host alias (Cname records)**] で [ **Cname レコードの編集**] をクリックし、次の表の値を選択します。
    
    
    |**Alias**|**TTL**|**Refers to Host Name**|**その他のホスト**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (なし)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (なし)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (なし)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (なし)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (なし)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (なし)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. [**続行**] を選択します。
  
6. 他の 5 つの CNAME レコードをそれぞれ追加します。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 
  
1. まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。 最初にログインします。
    
  
2. [**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。 
  
3. [* * Manage * my domain * * *] で、[ **ADVANCED DNS レコードの編集**] を選択します。

  
4. [ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。   
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。   |

 
5. [**続行**] を選択します。

6. [**変更の保存**] を選択します。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 個の SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Web.com は、この機能を使用できるようにする責任があることに注意してください。 次の手順と現在の web.com GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Web.com コミュニティ](https://community.web.com.com/)を活用してください。 

1. まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。 最初にログインします。
      
2. [**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。 
  
3. [* * Manage * my domain * * *] で、[ **ADVANCED DNS レコードの編集**] を選択します。
  
4. 2 つの SRV レコードの最初のレコードを追加します。

    [**サービス (Srv レコード)**] で、[ **Srv レコードの編集**] をクリックし、次の表の値を選択します。 
        
    |**Service**|**Protocol**|**TTL**|**優先度**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1-d |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1-d |5061 | sipfed.online.lync.com |

  
5. 表の2行目の値を選択して、他の SRV レコードを追加します。 
  
6. [**続行**] を選択します。

7. [**変更の保存**] を選択します。

    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
