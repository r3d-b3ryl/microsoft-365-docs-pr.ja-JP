---
title: Microsoft の eNomCentral で DNS レコードを作成する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の eNomCentral のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780399"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>Microsoft の eNomCentral で DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが eNomCentral の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
これらのレコードを eNomCentral で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。

  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
次の手順を実行するか、[ビデオ (46 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-検証-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    ドロップダウンリストから [ **Record Type** ] の値を選択します。
    
    ||||
    |:-----|:-----|:-----|
    |**Host Name** <br/> |**Record Type** <br/> |**Address** <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-検証-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. [**保存**] を選択します。
    
    ![eNom-BP-検証-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

次の手順を実行するか、[ビデオ (3 分 40 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Email Settings**] を選びます。
    
    ![eNom-BP-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. [ **Service Selection**] ボックスで、[ **User (MX)**] を選びます。
    
    ![eNom-BP-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |**Host Name**|**Address**|**Pref**|
    |:-----|:-----|:-----|
    |@  <br/> | *\<domain-key\>*. mail.protection.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> **注:***\<domain-key\>* Microsoft アカウントからを取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> 優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> |
       
   ![eNom-BP-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. [**保存**] を選択します。
    
    ![eNom-BP-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. 他の既存の MX レコードがある場合は、そのレコードのチェック ボックスをオンにして選びます。
    
    ![eNom-BP-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. [**削除] チェック**ボックスをオンにします。
    
    ![eNom-BP-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する 
<a name="BKMK_add_CNAME"> </a>

次の手順を実行するか、[ビデオ (4 分 24 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. [**新しい行**] を選択します。
    
    ![eNom-BP-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. 6 つの新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。
    
ドロップダウンリストから [ **Record Type** ] の値を選択します。
        
    |**Host Name**|**Record Type**|**アドレス**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME (Alias)  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME (Alias)  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME (Alias)  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME (Alias)  <br/> |enterpriseregistration.windows.net。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseenrollment  <br/> |CNAME (Alias)  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. [**保存**] を選択します。
    
    ![eNom-BP-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。
  
次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
ドロップダウンリストから [ **Record Type** ] の値を選択します。
    
    |**Host Name**|**Record Type**|**Address**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
   ![eNom-BP-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. [**保存**] を選択します。
    
    ![eNom-BP-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

次の手順を実行するか、[ビデオ (5 分 50 秒から開始) を参照](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)してください。
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. [ **My domains**] の下で、編集するドメインの名前を選択します。
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. [ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. **新しい行**の右側で、[ **SRV レコードまたは SPF レコードの追加**] を選択します。
    
    ![eNom-BP-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. 2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |**Service**|**Protocol**|**Priority**|**Weight**|**Port**|**Target          (Hostname)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![eNom-BP-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. [**保存**] を選択します。
    
    ![eNom-BP-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

