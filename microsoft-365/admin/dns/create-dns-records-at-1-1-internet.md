---
title: Office 365 用の 1&1 IONOS で DNS レコードを作成する
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを 1&1 IONOS for Office 365 で設定する方法について説明します。
ms.openlocfilehash: e31c9d9d08e29156ff6197c030de6b0f4169b5f4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211873"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a>Office 365 用の 1&1 IONOS で DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
> [!CAUTION]
> 1&1 IONOS では、ドメインは MX レコードとトップレベル自動検出 CNAME レコードの両方を持つことはできないことに注意してください。 これにより、Office 365 用に Exchange Online を構成する方法が制限されます。 回避策がありますが、1&1 IONOS でサブドメインを作成した経験がある場合に**のみ**、この方法を使用することをお勧めします。 > このサービスの[制限](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)にかかわらず、1&1 IONOS で独自の OFFICE 365 DNS レコードを管理することを選択する場合は、この記事の手順に従って、ドメインを確認し、電子メール、Skype For business Online などの dns レコードを設定します。 
  
これらのレコードを 1&1 IONOS に追加すると、使用しているドメインが、Office 365 サービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。 You'll be prompted to log in.
    
2. [ **Manage domains**] を選びます。
    
3. [**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。
    
4. [**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
5. [ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
    |TXT  <br/> |(このフィールドは空白のままにしておきます)  <br/> |MS=ms *XXXXXXXX*  <br/> 注: これは例です。 Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
7. [**保存**] を選択します。
    
8. [**保存**] をもう一度選択します。 
    
9. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
10. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。
  
Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする
<a name="BKMK_add_MX"> </a>

次の手順を実行するか、[ビデオ (3 分 22 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
> [!NOTE]
> 1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。 
  
1. まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。 You'll be prompted to log in.
    
2. [ **Manage domains**] を選びます。
    
3. [**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。
    
4. [**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
5. In the **MX Records** section, in the ** Mail Exchanger (MX Record) ** area, select **Other mail server**.<br/>(下へスクロールしなければならないことがあります。)<br/>![1&amp;1-BP-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. 既に他の MX レコードがある場合は、それぞれのレコードを選び、キーボードの **Delete** キーを押して、レコードを削除します<br/>(登録されている MX レコードがない場合は、次の手順に進みます)。<br/>![1&amp;1-BP-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. [ **MX 1**] レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    |**MX 1**|**Priority**|
    |:-----|:-----|
    | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/>  注: Office 365 \<アカウントからドメイン\>キーを取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> | 
    
    ![1および 1-構成2および3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. [**保存**] を選択します。<br/>(You may have to scroll down.)<br/>![1&amp;1-BP-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。<br/>![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1&1 IONOS には、Office 365 電子メールサービスに必要な CNAME レコードと共に MX レコードを使用できるようにするための回避策が必要です。 この回避策では、1&1 IONOS にサブドメインのセットを作成し、それらを CNAME レコードに割り当てる必要があります。
  
> [!IMPORTANT]
> この手順を開始する前に、利用可能なサブドメインが 2 つ以上あることを確認してください。 この解決策は、サブドメインの作成に IONOS 1&1 で既に経験している場合にのみお勧めします。 
  
### <a name="basic-cname-records"></a>基本的な CNAME レコード

次の手順を実行するか、[ビデオ (3 分 57 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
> [!NOTE]
> 1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。 
  
1. まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。 You'll be prompted to log in.
    
2. [ **Manage domains**] を選びます。
    
3. [**ドメインセンター** ] ページで、更新するドメインを見つけ、[サブドメインの**管理**] を選択します。<br/>![1&amp;1-BP-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します<br/>(1&1 IONOS でサポートされる最上位の CNAME レコードは1つだけなので、このようにする必要がありますが、Office 365 にはいくつかの CNAME レコードが必要です。)<br/>最初に、Autodiscover サブドメインを作成します。
    
4. [**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. 新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。

    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   | 

    ![1&amp;1-BP-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. [**サブドメインの作成**] を選択します。<br/>![1&amp;1-BP-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. [**サブドメインの概要**] セクションで、作成したばかりの**自動検出**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。 <br/>![1&amp;1-BP-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. [**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。 <br/>![1&amp;1-BP-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. [ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。<br/>![1&amp;1-BP-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. [ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   |

    ![1&amp;1-BP-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. 免責事項の [ **I am aware**] チェック ボックスをオンにします。<br/>![1&amp;1-BP-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. [**保存**] を選択します。<br/>![1&amp;1-BP-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>追加の CNAME レコード

以降の手順に従って追加の CNAME レコードを作成すると、Skype for Business Online サービスが有効になります。 手順は、前に 2 つの CNAME レコードを作成したときの手順と同じです。
  
1. 3 つ目のサブドメイン (Lyncdiscover) を作成します。<br/>[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。
    
2. 新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. [**サブドメインの作成**] を選択します。
    
4. [**ドメインセンター** ] ページで、[サブドメインの**管理**] を選択します。
    
5. [**サブドメインの概要**] セクションで、作成したばかりの**lyncdiscover**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。 <br/>[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
6. In the **A/AAAA Records (IP Addresses)** section, in the ** IP address (A Record) ** area, select **CNAME**.
    
7. [ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。 <br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. [ **I am aware** ] 免責事項のチェックボックスをオンにして、[**保存**] を選択します。
    
9. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
10. 4 つ目のサブドメイン (SIP) を作成します。 <br/>[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。
    
11. 新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。<br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. [**サブドメインの作成**] を選択します。
    
13. [**ドメインセンター** ] ページで、[サブドメインの**管理**] を選択します。
    
14. [**サブドメインの概要**] セクションで、作成したばかりの**sip**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。 <br/>[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
15. In the **A/AAAA Records (IP Addresses)** section, in the ** IP address (A Record) ** area, select **CNAME**.
    
16. [ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. [ **I am aware** ] 免責事項のチェックボックスをオンにして、[**保存**] を選択します。
    
18. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
### <a name="cname-records-needed-for-mdm"></a>MDM に必要な CNAME レコード

> [!IMPORTANT]
> 手順は、他の 4 個の CNAME レコードの場合と同じですが、次の表の値を入力します。 
  
|**Create Subdomain**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 次に例を示します。 参考にしてください。 SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。 
  
次の手順を実行するか、[ビデオ (5 分 9 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
> [!NOTE]
> 1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。 
  
1. まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。 You'll be prompted to log in.
    
2. [ **Manage domains**] を選びます。
    
3. [**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** (**v**)] コントロールを選択します。
    
4. [**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
5. [ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。 <br/>(You may have to scroll down.)
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>(Choose the **Type** value from the drop-down list.) <br/>
    
    |**種類**|**Prefix**|**Name Value**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           | 
    
    ![TXT レコード](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. [**保存**] を選択します。<br/>![レコードを追加する](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. [**保存**] を選択します。<br/>![レコードを保存する](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。<br/>![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 つの SRV レコードを追加する

次の手順を実行するか、[ビデオ (5 分 51 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
> [!NOTE]
> 1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。 
  
1. まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。 You'll be prompted to log in.
    
2. [ **Manage domains**] を選びます。
    
3. [**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。
    
4. [**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
5. [ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。
    
6. 2 つの SRV レコードの最初のレコードを追加します。<br/>[ **Add Record**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます <br/>(ドロップダウンリストから [ **Type** ] と [ **TTL** ] の値を選びます。) 
    
    |**Type**|**Service**|**Protocol**|**Name**|**Host**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(Leave this field empty.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1-d  <br/> |443  <br/> |3600 (1 h)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(このフィールドは空のままにします。)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |3600 (1 h)  <br/> |  
    
    ![1&amp;1-BP-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. [**保存**] を選択します。 <br/>![1&amp;1-BP-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. [**保存**] を選択します。 <br/>![1&amp;1-BP-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。 <br/>![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. 残りの SRV レコードを追加します。 <br/>[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。 <br/>[ **Add Record** ] 領域で、表の他の行の値を使用してレコードを作成し、[**追加**]、[**保存**]、および **[はい]** を再度選択してレコードを完成させます。 
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
