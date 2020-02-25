---
title: Office 365 用 eNomCentral で DNS レコードを作成する
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Office 365 の eNomCentral で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: c4cd12667ebf945aa2f354ccfa0bad1688dc9863
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241122"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a>Office 365 用 eNomCentral で DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが eNomCentral の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
eNomCentral でこれらのレコードを追加すると、ドメインは Office 365 サービスと連携するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認用に TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
次の手順を実行するか、[ビデオ (46 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-検証-1-1](../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Choose the **Record Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Host Name** <br/> |**Record Type** <br/> |**Address** <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-検証-1-2](../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. [**保存**] を選択します。
    
    ![eNom-BP-検証-1-3](../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
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

次の手順を実行するか、[ビデオ (3 分 40 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Email Settings**] を選びます。
    
    ![eNom-BP-1-3](../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. [ **Service Selection**] ボックスで、[ **User (MX)**] を選びます。
    
    ![eNom-BP-1-4](../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |**Host Name**|**Address**|**Pref**|
    |:-----|:-----|:-----|
    |@  <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **注:** Office 365 アカウントから* \<ドメイン\>キー*を取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |
       
   ![eNom-BP-2-1](../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. [**保存**] を選択します。
    
    ![eNom-BP-2-2](../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. 他の既存の MX レコードがある場合は、そのレコードのチェック ボックスをオンにして選びます。
    
    ![eNom-BP-2-3](../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. [**削除] チェック**ボックスをオンにします。
    
    ![eNom-BP-2-4](../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

次の手順を実行するか、[ビデオ (4 分 24 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. [**新しい行**] を選択します。
    
    ![eNom-BP-3-1](../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. 6 つの新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |**Host Name**|**Record Type**|**アドレス**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME (Alias)  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME (Alias)  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME (Alias)  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME (Alias)  <br/> |enterpriseregistration.windows.net。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseenrollment  <br/> |CNAME (Alias)  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![eNom-BP-3-2](../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. [**保存**] を選択します。
    
    ![eNom-BP-3-3](../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。
  
次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    (Choose the **Record Type** value from the drop-down list.) 
    
    |**Host Name**|**Record Type**|**Address**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
   ![eNom-BP-4-1](../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. [**保存**] を選択します。
    
    ![eNom-BP-4-2](../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 個の SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

次の手順を実行するか、[ビデオ (5 分 50 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. **新しい行**の右側で、[ **SRV レコードまたは SPF レコードの追加**] を選択します。
    
    ![eNom-BP-5-1](../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. 2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |**Service**|**Protocol**|**Priority**|**Weight**|**Port**|**Target          (Hostname)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![eNom-BP-5-2](../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. [**保存**] を選択します。
    
    ![eNom-BP-5-3](../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  

