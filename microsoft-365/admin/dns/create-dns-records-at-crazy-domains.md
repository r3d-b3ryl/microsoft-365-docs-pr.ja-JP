---
title: Microsoft 用の変わったドメインで DNS レコードを作成する
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の他のドメインにある他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: cf65173873affdc66e4e6d03764a3d6c842b7642
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646225"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a>Microsoft 用の変わったドメインで DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Crazy Domains の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
これらのレコードを、変わったドメインで追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。
  

  
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. **[マイアカウント**] セクションで、[ **Domains**] を選択します。
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. [ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. [ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. [ **Add Record** ] を選択します。
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. [ **Add Record**] ボックスの一覧から [ **TXT Record**] を選びます。 
    
    ![CrazyDomains-検証-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. **[追加]** を選択します。
    
    ![CrazyDomains-検証-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |**サブドメイン**|**テキスト レコード**|
    |:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-検証-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. **[更新]** を選択します。
    
    ![CrazyDomains-検証-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. **[マイアカウント**] セクションで、[ **Domains**] を選択します。
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. [ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. [ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. [ **Add Record** ] を選択します。
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. [ **Add Record:**] ボックスの一覧から [ **MX Record**] を選びます。 
    
    ![CrazyDomains-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. **[追加]** を選択します。
    
    ![CrazyDomains-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    (ドロップダウンリストから **優先度** の値を選択します。) 
    
    |**メール送信先ゾーン**|**優先度**|**割り当て先サーバー**|
    |:-----|:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |1-d  <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:***\<domain-key\>* Microsoft アカウントからを取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. **[更新]** を選択します。
    
    ![CrazyDomains-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. その他の MX レコードが [ **Mx Record** ] セクションに表示されている場合は、いずれかのレコードに対して [ **変更** ] を選択します。 
    
    ![CrazyDomains-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. **[削除]** を選択します。
    
    ![CrazyDomains-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. [ **更新** ] を選択して、削除を確認します。 
    
    ![CrazyDomains-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. この手順の前半で追加した MX レコードだけを残し、同じ手順で、一覧に表示されているその他の MX レコードをすべて削除します。
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な6つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. **[マイアカウント**] セクションで、[ **Domains**] を選択します。
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. [ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. [ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. [ **Add Record** ] を選択します。
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Choose **CNAME Record** from the **Add Record:** drop-down list. 
    
    ![CrazyDomains-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. **[追加]** を選択します。
    
    ![CrazyDomains-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. 6 つの CNAME レコードの最初のレコードを追加します。
    
    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |**サブドメイン**|**エイリアス**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![CrazyDomains-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. [ **ADD CNAME Record**] を選びます。
    
    ![CrazyDomains-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. 2 番目の CNAME レコードを追加します。
    
    新規レコードのボックスに、表の次の行の値を使用し、[ **ADD CNAME record**] をもう一度選択します。
    
    6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
11. [ **更新** ] を選択して変更を保存します。 
    
    ![CrazyDomains-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。 
  
1. まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. **[マイアカウント**] セクションで、[ **Domains**] を選択します。
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. [ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. [ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. [ **Add Record** ] を選択します。
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. [ **Add Record:**] ボックスの一覧から [ **TXT Record**] を選びます。 
    
    ![CrazyDomains-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. **[追加]** を選択します。
    
    ![CrazyDomains-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. 新規レコードのボックスに、次の表の値を入力するか貼り付けます。
    
    |**サブドメイン**|**テキスト レコード**|
    |:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![CrazyDomains-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. **[更新]** を選択します。
    
    ![CrazyDomains-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. **[マイアカウント**] セクションで、[ **Domains**] を選択します。
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. [ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. [ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. [ **Add Record** ] を選択します。
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. [ **Add Record:**] ボックスの一覧から [ **SRV Record**] を選びます。 
    
    ![CrazyDomains-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. **[追加]** を選択します。
    
    ![CrazyDomains-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. 2 つの SRV レコードの最初のレコードを追加します。
    
    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |**レコードの種類**|**サブドメイン**|**Priority**|**Weight**|**Port**|**対象**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV レコード  <br/> |_sip._tls  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV レコード  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![CrazyDomains-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. [ **ADD SRV Record**] を選びます。
    
    ![CrazyDomains-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. 残りの SRV レコードを追加します。
    
    新規レコードのボックスで、次の表の 2 行目の値を使用します。
    
11. [ **更新** ] を選択して変更を保存します。 
    
    ![CrazyDomains-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
