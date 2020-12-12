---
title: Microsoft 1 および 1&で DNS レコードを作成する
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを 1&1 の間で MICROSOFT 用にセットアップする方法について説明します。
ms.openlocfilehash: 8e2deab05b5ef8d8f22993d2bfdd032999ed9c39
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657998"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Microsoft 1&1 で DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
> [!CAUTION]
> 1&1 の場合、ドメインは MX レコードとトップ レベルの自動検出 CNAME レコードの両方を使用できない点に注意してください。 これにより、Microsoft 向け Exchange Online を構成する方法が制限されます。 回避策は存在しますが、1 ~  1 の間に 1 つの BUTOS で既にサブドメインを作成した経験がある場合にのみ、この方法を&することをお勧めします。 > このサービスの制限[](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)にもかかわらず、1&1 の間に独自の Microsoft DNS レコードを管理する場合は、この記事の手順に従ってドメインを確認し、メールや Skype for Business Online などのために DNS レコードを設定します。 
  
これらのレコードを 1&1 の間に追加すると、ドメインは Microsoft サービスで動作する設定に設定されます。
  
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。
  
1. To get started, go to your domains page at 1&1 BY USING [THIS link](https://my.1and1.com/). You'll be prompted to log in.
    
2. [ドメイン **の管理] を選択します**。
    
3. [ **ドメイン センター] ページ** で、更新するドメインを見つけ、そのドメインの **Panel** ( **v**) コントロールを選択します。
    
4. [ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。
    
5. [TXT レコード **と SRV レコード] セクションで** 、[Add Record ] (レコードの追加) **を選択します**。
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    ||||
    |:-----|:-----|:-----|
    |**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
    |TXT  <br/> |(このフィールドは空白のままにします)  <br/> |MS=ms *XXXXXXXX*  <br/> 注: これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
7. **[保存]** を選択します。
    
8. [保存 **] を再び** 選択します。 
    
9. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。
    
10. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

次の手順を実行するか、[ビデオ (3 分 22 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。
  
> [!NOTE]
> If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. To get started, go to your domains page at 1&1 BY USING [THIS link](https://my.1and1.com/). You'll be prompted to log in.
    
2. [ドメイン **の管理] を選択します**。
    
3. [ **ドメイン センター] ページ** で、更新するドメインを見つけ、そのドメインの **Panel** ( **v**) コントロールを選択します。
    
4. [ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。
    
5. [MX **レコード] セクション** の [メール エクスチェンジャー **(MX レコード)** ] 領域で、[その他のメール サーバー] **を選択します**。<br/>(下へスクロールしなければならないことがあります。)<br/>![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. 既に他の MX レコードがある場合は、それぞれのレコードを選び、キーボードの **Delete** キーを押して、レコードを削除します<br/>(登録されている MX レコードがない場合は、次の手順に進みます)。<br/>![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. [ **MX 1**] レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    |**MX 1**|**Priority**|
    |:-----|:-----|
    | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  注: Microsoft アカウント \<domain-key\> から取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> | 
    
    ![1 と 1 - 2 と 3 を構成する](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. **[保存]** を選択します。<br/>(下へスクロールしなければならないことがあります。)<br/>![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。<br/>![[DNS 設定の編集] ダイアログ ボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1&1 の場合、MX レコードを Microsoft の電子メール サービスに必要な CNAME レコードと共に使用できるよう、WORKAROUND が必要です。 この回避策では、一連のサブドメインを 1&1 の間で作成し、CNAME レコードに割り当てる必要があります。
  
> [!IMPORTANT]
> この手順を開始する前に、利用可能なサブドメインが 2 つ以上あることを確認してください。 このソリューションをお勧めできるのは、1 台または 1 人ののユーザーの間で既にサブドメインを作成した経験&場合のみです。 
  
### <a name="basic-cname-records"></a>基本的な CNAME レコード

次の手順を実行するか、[ビデオ (3 分 57 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。
  
> [!NOTE]
> If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. To get started, go to your domains page at 1&1 BY USING [THIS link](https://my.1and1.com/). You'll be prompted to log in.
    
2. [ドメイン **の管理] を選択します**。
    
3. [ドメイン **センター] ページ** で、更新するドメインを見つけ、[サブドメインの管理 **] を選択します**。<br/>![1 &amp; 1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します<br/>(1&1 の場合、1 つの&では 1 つのトップ レベル CNAME レコードしかサポートされますが、Microsoft は複数の CNAME レコードを必要とします。<br/>最初に、Autodiscover サブドメインを作成します。
    
4. [ **サブドメインの概要] セクションで** 、[サブドメインの **作成] を選択します**。
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. 新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。

    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   | 

    ![1 &amp; 1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. [サブ **ドメインの作成] を選択します**。<br/>![1 &amp; 1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. [ **サブドメインの** 概要] セクションで、作成した **自動** 検出サブドメインを探し、そのサブドメインの **Panel (v)** コントロールを選択します。 <br/>![1 &amp; 1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. [サブドメイン **の設定] 領域で、[DNS** 設定の編集 **] を選択します**。 <br/>![1 &amp; 1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. **[A/AAAA レコード (IP アドレス)** ] セクションの [IP アドレス **] (A レコード)** 領域で **、[CNAME] を選択します**。<br/>![1 &amp; 1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. [ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   |

    ![1 &amp; 1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. 免責事項の [ **I am aware**] チェック ボックスをオンにします。<br/>![1 &amp; 1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. **[保存]** を選択します。<br/>![1 &amp; 1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>追加の CNAME レコード

以降の手順に従って追加の CNAME レコードを作成すると、Skype for Business Online サービスが有効になります。 手順は、前に 2 つの CNAME レコードを作成したときの手順と同じです。
  
1. 3 つ目のサブドメイン (Lyncdiscover) を作成します。<br/>[ **サブドメインの概要] セクションで** 、[サブドメインの **作成] を選択します**。
    
2. 新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. [サブ **ドメインの作成] を選択します**。
    
4. [ドメイン センター **] ページで** 、[サブドメインの **管理] を選択します**。
    
5. [ **サブドメイン** の概要] セクションで、作成した **lyncdiscover** サブドメインを見つけ、そのサブドメインの **Panel (v)** コントロールを選択します。 <br/>[サブドメイン **の設定] 領域で、[DNS** 設定の編集 **] を選択します**。
    
6. **[A/AAAA レコード (IP アドレス)** ] セクションの [IP アドレス **] (A レコード)** 領域で **、[CNAME] を選択します**。
    
7. [ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。 <br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. I am aware disclaimer のチェック ボックスを **オンにし** 、[保存] を選択 **します**。
    
9. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。
    
10. 4 つ目のサブドメイン (SIP) を作成します。 <br/>[ **サブドメインの概要] セクションで** 、[サブドメインの **作成] を選択します**。
    
11. 新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。<br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. [サブ **ドメインの作成] を選択します**。
    
13. [ドメイン センター **] ページで** 、[サブドメインの **管理] を選択します**。
    
14. [ **サブドメインの** 概要] セクションで、作成した **sip** サブドメインを見つけ、そのサブドメインの **Panel (v)** コントロールを選択します。 <br/>[サブドメイン **の設定] 領域で、[DNS** 設定の編集 **] を選択します**。
    
15. **[A/AAAA レコード (IP アドレス)** ] セクションの [IP アドレス **] (A レコード)** 領域で **、[CNAME] を選択します**。
    
16. [ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. I am aware disclaimer のチェック ボックスを **オンにし** 、[保存] を選択 **します**。
    
18. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。
    
### <a name="cname-records-needed-for-mdm"></a>MDM に必要な CNAME レコード

> [!IMPORTANT]
> 手順は、他の 4 個の CNAME レコードの場合と同じですが、次の表の値を入力します。 
  
|**Create Subdomain**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)を参照してください。 SPF レコードを検証するには、次の[SPF 検証ツールのいずれかを使用できます](../setup/domains-faq.yml)。 
  
次の手順を実行するか、[ビデオ (5 分 9 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。
  
> [!NOTE]
> If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. To get started, go to your domains page at 1&1 BY USING [THIS link](https://my.1and1.com/). You'll be prompted to log in.
    
2. [ドメイン **の管理] を選択します**。
    
3. [ **ドメイン センター] ページ** で、更新するドメインを見つけ、そのドメインの **Panel** (**v**) コントロールを選択します。
    
4. [ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。
    
5. [TXT レコード **と SRV レコード] セクションで** 、[Add Record ] (レコードの追加) **を選択します**。 <br/>(下へスクロールしなければならないことがあります。)
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>(ドロップダウン リストから [**Type**] の値を選びます。) <br/>
    
    |**Type**|**Prefix**|**Name Value**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           | 
    
    ![TXT レコード](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. **[保存]** を選択します。<br/>![レコードを追加する](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. **[保存]** を選択します。<br/>![レコードを保存する](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。<br/>![[DNS 設定の編集] ダイアログ ボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する

次の手順を実行するか、[ビデオ (5 分 51 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。
  
> [!NOTE]
> If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. To get started, go to your domains page at 1&1 BY USING [THIS link](https://my.1and1.com/). You'll be prompted to log in.
    
2. [ドメイン **の管理] を選択します**。
    
3. [ **ドメイン センター] ページ** で、更新するドメインを見つけ、そのドメインの **Panel** ( **v**) コントロールを選択します。
    
4. [ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。
    
5. [TXT レコード **と SRV レコード] セクションで** 、[Add Record ] (レコードの追加) **を選択します**。
    
6. 2 つの SRV レコードの最初のレコードを追加します。<br/>[ **Add Record**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます <br/>(ドロップダウン リスト **から [Type]** と **[TTL]** の値を選択します)。 
    
    |**Type**|**Service**|**Protocol**|**Name**|**Host**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(このフィールドは空のままにします。)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1   <br/> |443  <br/> |3600 (1 h)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(このフィールドは空のままにします。)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1   <br/> |5061  <br/> |3600 (1 h)  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. **[保存]** を選択します。 <br/>![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. **[保存]** を選択します。 <br/>![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。 <br/>![[DNS 設定の編集] ダイアログ ボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. 残りの SRV レコードを追加します。 <br/>[TXT レコード **と SRV レコード] セクションで** 、[Add Record ] (レコードの追加) **を選択します**。 <br/>[Add **Record]** 領域で、テーブルの他の行の値を使用してレコードを作成し、もう一度 [追加]、[保存]、および [はい] を選択してレコードを完成します。  
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
