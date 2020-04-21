---
title: Microsoft の Names.co.uk で DNS レコードを作成する
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: ドメインを確認し、電子メール、Skype for Business Online、および Names.co.uk のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 2552017e06001c0b28605558b823fdb4c670ef8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629325"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a>Microsoft の Names.co.uk で DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Names.co.uk の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
    
これらのレコードを Names.co.uk で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。
  
Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。 ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。
    
    (You may have to scroll down.)
        
    |**ホスト名**|**種類**|**結果**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-検証-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. **[保存]** を選択します。
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-検証-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. [ **Add/Modify DNS Zone**] ページの [ **Mail exchange records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (You may have to scroll down.)
    
    |**ホスト名**|**Priority**|**結果**|
    |:-----|:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |1-d  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/> > [!NOTE]>、Microsoft アカウントから* \<ドメイン\>キー*を取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. **[保存]** を選択します。
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. 他の MX レコードがリストにある場合は、[ **Mail exchange records**] セクションで各レコードを選び、キーボードの **Delete** キーを押して、レコードを削除します。 
    
    ![NamesUK-BP-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. **[保存]** を選択します。
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な6つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。
    
    (下へスクロールしなければならないことがあります)。
    
    |**Host Name**|**Type**|**Result**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![NamesUK-BP-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. **[保存]** を選択します。
    
    ![NamesUK-BP-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。
  
1. まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. [**アカウントの DNS ゾーン**] ページの [**ドメイン名**] 列で、更新するドメインの名前を選択します。 
    
    ![NamesUK-BP-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。
    
    (You may have to scroll down.)
    
    |**ホスト名**|**種類**|**結果**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
       
    ![NamesUK-BP-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. **[保存]** を選択します。
    
    (下へスクロールしなければならないことがあります。)
    
    ![NamesUK-BP-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft に必要な2つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. [ **Add/Modify DNS Zone**] ページの [ **Service records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    |**Name**|**Priority**|**Weight**|**Port**|**結果**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![NamesUK-BP-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. **[保存]** を選択します。
    
    (下へスクロールしなければならないことがあります。)
    
    ![NamesUK-BP-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
