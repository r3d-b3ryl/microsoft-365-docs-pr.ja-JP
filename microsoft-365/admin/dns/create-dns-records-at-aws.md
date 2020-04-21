---
title: Microsoft の Amazon Web サービス (AWS) で DNS レコードを作成する
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: ドメインを確認し、電子メール、Skype for Business Online、および Amazon Web Services (AWS) for Microsoft のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 086a5d7210d2c722aeda701dc62a699ca0eaec87
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629733"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>Microsoft の Amazon Web サービス (AWS) で DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
DNS ホスティングプロバイダーが AWS の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype Online for Business などの DNS レコードを設定します。
  
これらのレコードを AWS で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。
  
Microsfot を使用した web サイトのホストと DNS の詳細については、「 [Microsoft でパブリック web サイトを使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)する」を参照してください。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。 ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**リソース**] ページで、[ **Hosted Zones**] を選択します。
    
3. [* * Hosted Zones * *] ページの [ **Domain Name** ] 列で、編集するドメインの名前を選択します。 
    
4. [ **Create Record Set**] を選びます。
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**名前** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
    |(Leave this field empty.)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**注:** これは例です。 Microsoft 365 の表に記載されている、特定の**宛先またはポイントを**使用して、ここでのアドレスを指定します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |単純  <br/> |
   
6. **[作成]** を選択します。
    
7. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>MX レコードを追加して、自分のドメインのメールが Microsoft 365 に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**リソース**] ページで、[ **Hosted Zones**] を選択します。
    
3. [ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。 
    
4. [ **Create Record Set**] を選びます。
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**名前**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |MX - Mail Exchange  <br/> |No  <br/> |300  <br/> |0  *\<ドメイン キー\>*  .mail.protection.outlook.com.  <br/> 0 は、MX 優先度の値です。 この値を MX 値の先頭に追加して、スペースで他の値から分離します。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **注:**\<Microsoft 365 アカウントから*ドメインキー* \>を取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |単純  <br/> |
       
    ![AWS-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. **[作成]** を選択します。
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. 他の MX レコードがある場合は削除します。
    
    > [!IMPORTANT]
    > AWS は、複数のレコードが含まれる可能性のあるセットとして MX レコードを格納します。 [**レコードセットを削除**する] を選択し**ない**でください。これにより、追加した MX レコードを含むすべての MX レコードが削除されます。 代わりに、次の手順を使用してください。 
  
    最初に、MX レコードセットを選択します。
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    次に、[ **Edit Record Set**] 領域で、[ **Value**] ボックスのエントリを選んで、キーボードの **Delete** キーを押し、使われなくなった MX レコードをすべて削除します。 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. [ **Save Record Set**] を選択します。
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Microsoft 365 に必要な5つの CNAME レコードを追加します。
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**リソース**] ページで、[ **Hosted Zones**] を選択します。
    
3. [ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。 
    
4. [ **Create Record Set**] を選びます。
    
5. 1 番目の CNAME レコードを追加します。
    
    [ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。 
    
    [ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。 
    
    |**名前**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - 正規名  <br/> |No  <br/> |300  <br/> |autodiscover.outlook.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |Simple  <br/> |
    |sip  <br/> |CNAME - 正規名  <br/> |No  <br/> |300  <br/> |sipdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |Simple  <br/> |
    |lyncdiscover  <br/> |CNAME - 正規名  <br/> |No  <br/> |300  <br/> |webdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |Simple  <br/> |
    |enterpriseregistration  <br/> |CNAME - 正規名  <br/> |No  <br/> |300  <br/> |enterpriseregistration.windows.net。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |Simple  <br/> |
    |EnterpriseEnrollment  <br/> |CNAME - 正規名  <br/> |No  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |Simple  <br/> |
   
    ![AWS-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. **[作成]** を選択します。
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. 残りの 4 つの CNAME レコードを追加します。
    
    [ **Hosted Zones** ] ページで、[ **create record Set**] を選択し、表の次の行の値を使用してレコードを作成して、もう一度 [ **create** ] を選択してそのレコードを完成させます。 
    
    この手順を繰り返し、5つの CNAME レコードをすべて作成します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。 次に例を示します。 これらの[外部ドメインネームシステムレコードを Microsoft に対して](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)確認します。 SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。 
  
1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**リソース**] ページで、[ **Hosted Zones**] を選択します。
    
3. [ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。 
    
4. **TXT**レコードセットを選択します。 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. [ **レコード セットの編集**] 領域で、既存のレコード用の [ **Value:**] ボックス内にある現在のエントリの最後で、キーボードの Enter キーを押して新規の行を作成します。次に、その行 (既存の値の下) に、次のテーブルの値を入力、またはコピーして貼り付けます (表の下のイラストに例があります)。 
    
    |**Value:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> (画面の手順で必要になる引用符は自動的に補完されます。手動で入力する必要はありません。)  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![AWS-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. [ **Save Record Set**] を選択します。
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Microsoft 365 に必要な2つの SRV レコードを追加します。
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**リソース**] ページで、[ **Hosted Zones**] を選択します。
    
3. [ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。 
    
4. [ **Create Record Set**] を選びます。
    
5. 1 番目の SRV レコードを追加します。
    
    [ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。 
    
    [ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。 
    
    |**名前**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls|SRV - サービス ロケータ|No|300|100 1 443 sipdir.online.lync.com. **この値は、ピリオド (.) で終了する必要があります。**><br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |Simple|
    |_sipfederationtls _tcp|SRV - サービス ロケータ|No|300|100 1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**<br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |単純|
   
    ![AWS-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. **[作成]** を選択します。
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. 他の SRV レコードを追加します。
    
    [ **Hosted Zones** ] ページで、[ **create record Set**] を選択し、表の次の行の値を使用してレコードを作成して、もう一度 [ **create** ] を選択してそのレコードを完成させます。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。 
  
