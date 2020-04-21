---
title: Microsoft のホバー時に DNS レコードを作成する
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: ドメインを確認し、メール、Skype for Business Online、および Microsoft のホバー時に他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 328020dffe5d6549f7a0418a01d99b18ef9c5035
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629517"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a>Microsoft のホバー時に DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Hover の場合は、この記事に示す手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードの設定を行います。
     
これらのレコードを Hover で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。
  
Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。 ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. [**ドメインの管理**] で、編集するドメインの名前を選択します。
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. [ **DNS** ] タブを選択します。 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. [ **Add New**] を選択します。
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    ||||
    |:-----|:-----|:-----|
    |ホスト名  <br/> |レコードの種類  <br/> |値  <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. **[保存]** を選択します。
    
    ![[保存] を選択します。](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft 365 に戻り、Microsoft 365 にレコードを検索するよう要求します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. [**ドメインの管理**] で、編集するドメインの名前を選択します。
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. [ **DNS** ] タブを選択します。 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. [ **Add New**] を選択します。
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 新しいレコードのボックスで、[ **Record Type**] に [ **MX**] を選び、次の表の値を入力するか、コピーして貼り付けます。
    
    |**Hostname**|**レコードの種類**|**優先度**|**ホスト名**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |.0  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft アカウントから* \<ドメインキー\> *を取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. **[保存]** を選択します。
    
    ![[保存] を選択します。](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. これ以外の MX レコードがある場合は、次の 2 段階のプロセスに従って、それぞれのレコードを削除します。
    
    最初に、削除するレコードにマウスポインターて、[**削除**] を選択します。
    
    ![マウスをポイントし、[削除] を選択します。](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    次に、[**はい]** を選択して各削除を確認します。 
    
    ![[はい] を選択して削除を確認する](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    この手順の最初に追加した MX レコード以外の MX レコードをすべて削除するまで、このプロセスを繰り返します。
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. [**ドメインの管理**] で、編集するドメインの名前を選択します。
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. [ **DNS** ] タブを選択します。 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 6 つの CNAME レコードの最初のレコードを追加します。
    
    [ **Add New**] を選択します。
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 新しいレコードの空のボックスで、[ **Record Type**] に [ **CNAME**] を選び、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |**Hostname**|**レコードの種類**|**ターゲット ホスト**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. **[保存]** を選択します。
    
    ![[保存] を選択します。](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. 上の 3 つの手順に従って、表の残りの 5 行の値を使って、残りの 5 つの CNAME レコードをそれぞれ追加します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。 
  
次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. [**ドメインの管理**] で、編集するドメインの名前を選択します。
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. [ **DNS** ] タブを選択します。 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. [ **Add New**] を選択します。
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    |**ホスト名**|**レコードの種類**|**値**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. **[保存]** を選択します。
    
    ![[保存] を選択します。](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft に必要な2つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. [**ドメインの管理**] で、編集するドメインの名前を選択します。
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. [ **DNS** ] タブを選択します。 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 2 つの SRV レコードの最初のレコードを追加します。
    
    [ **Add New**] を選択します。
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 新しいレコードの空のボックスで、[ **Record Type**] に [ **SRV**] を選び、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |**ホスト名**|**レコードの種類**|**Priority**|**Weight**|**Port**|**対象**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |SRV  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp  <br/> |SRV  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. **[保存]** を選択します。
    
    ![[保存] を選択します。](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. 上の 3 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
