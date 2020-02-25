---
title: 123-reg.co.uk で Office 365 用の DNS レコードを作成する
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: ドメインを確認し、電子メール、Skype for Business Online、および 123-reg.co.uk for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: acbc0f1c8a7eb7dcbe5f274d0f2c8b2c403e7de0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243026"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a>123-reg.co.uk で Office 365 用の DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが 123-reg.co.uk の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
これらのレコードを 123-reg.co.uk で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. [ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Hostname** <br/> |**Type** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
6. [**追加**] を選択します。
    
7. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

    
2. [**ドメイン**] ページで、確認するドメインを選択します。 
    
3. [**セットアップ**] ページで、[**セットアップの開始**] を選択します。
    
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. [ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Priority**|**Destination MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1-d  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **注:** Office 365 \<アカウントからドメイン\>キーを取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![テーブルの値をコピーして貼り付ける](../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. [**追加**] を選択します。
    
    ![[追加] を選択します。](../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. その他の MX レコードがある場合は、そのレコードの **削除 (ごみ箱)** アイコンを選んでそれぞれ削除します。 
    
    ![[削除] (ごみ箱アイコン) を選択します。](../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. [ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。 
    
5. 6 つの CNAME レコードの最初のレコードを追加します。
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Destination CNAME**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![テーブルから値をコピーして貼り付けます。](../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. [**追加**] を選択します。
    
    ![[追加] を選択します。](../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. 他の 5 つの CNAME レコードを追加します。
    
    [ **ADVANCED DNS** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。 
    
    6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 次に例を示します。 参考にしてください。 SPF レコードを確認するには、[SPF の検証ツール](../setup/domains-faq.md)を使うことができます。 
  
1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. [ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![123Reg-BP-4-1](../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. [**追加**] を選択します。
    
    ![[追加] を選択します。](../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 個の SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. [ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。 
    
5. 2 つの SRV レコードの最初のレコードを追加します。
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Hostname|Type|Priority|TTL|Destination SRV|
    |_sip _tls|SRV|100|3600|1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
    |_sipfederationtls _tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)** <br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![テーブルから値をコピーして貼り付けます。](../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. [**追加**] を選択します。
    
    ![[追加] を選択します。](../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. 他の SRV レコードを追加します。
    
    [ **ADVANCED DNS** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。 
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
