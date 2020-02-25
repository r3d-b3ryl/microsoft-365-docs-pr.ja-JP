---
title: Dreamhost で Office 365 用の DNS レコードを作成する
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: ドメインを確認し、電子メール、Skype for Business Online、および Dreamhost for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: f3f52e97fefece72dd96d9370e75e24fc4cebedf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248883"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a>Dreamhost で Office 365 用の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
使用している DNS ホスティング プロバイダーが DreamHost の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Lync などの DNS レコードを設定します。
 
これらのレコードを DreamHost で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認用に TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. [**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. [ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名前**|**Type**|**値**|**コメント**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)          |(このフィールドは省略可能です。)  <br/> |
   
   ![Dreamhost-検証-1-1](../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. [**今すぐレコードを追加**] を選択します。
    
    ![Dreamhost-BP-Verify-1-2](../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
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

以下の手順に従います。
  
1. まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. [**ダッシュボード**] ページで、[**メール**] を選択してから、[**カスタム MX**] を選択します。
    
    ![Dreamhost-BP-Configure-2-1](../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. [**メール配信の管理**] セクションの [**操作**] 列で、編集するドメインの [**編集**] を選択します。 
    
    ![Dreamhost-BP-Configure-2-2](../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. [ **Custom MX Record**] セクションにある新規レコードのボックスに、次の表から次の値を入力するかコピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    (MX レコードが他にもある場合は、それらのレコードが削除されるようにマーク付けします。)
    
    |**MX レコード (必須)**|
    |:-----|
    |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> 0 は、MX 優先度の値です。 この値を MX 値の先頭に追加して、スペースで他の値から分離します。  <br/> **注:** Office 365 アカウントから* \<ドメイン\>キー*を取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-2-3](../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. [**今すぐカスタム MX レコードを使用するように、このドメインを変更する**] を選択します。
    
    ![Dreamhost-BP-Configure-2-4](../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. 他の MX レコードが既にある場合は、エントリを選択し、キーボードの **Delete** キーを押して、各レコードを削除します。 
    
    ![Dreamhost-BP-Configure-2-5](../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. レコードを削除した場合は、[**今すぐカスタム MX レコードを更新**する] を選択します。
    
    ![Dreamhost-BP-Configure-2-6](../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

以下の手順に従います。
  
1. まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. [**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. [ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. [ **Add a custom DNS record**] セクションにある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名前**|**Type**|**値**|**コメント**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |(このフィールドは省略可能です。)  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |(このフィールドは省略可能です。)  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |(このフィールドは省略可能です。)  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |(このフィールドは省略可能です。)  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |(このフィールドは省略可能です。)  <br/> |
   
    ![Dreamhost-3-1](../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. [**今すぐレコードを追加**] を選択します。
    
    ![Dreamhost-BP-Configure-3-2](../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. 上記の2つの手順と、表の他の5つの行の値を使用して、残りの5つの CNAME レコードをそれぞれ追加します。

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。
  
以下の手順に従います。
  
1. まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. [**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. [ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. [ **Add a custom DNS record**] セクションにある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名前**|**Type**|**値**|**コメント**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |(このフィールドは省略可能です。)  <br/> |
   
   ![Dreamhost-4-1](../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. [**今すぐレコードを追加**] を選択します。
    
    ![Dreamhost-BP-Configure-4-2](../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. 上の 2 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 個の SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

以下の手順に従います。
  
1. まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. [**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. [ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. [ **Add a custom DNS record**] セクションにある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名前**|**Type**|**値**|**コメント**|
    |:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |(このフィールドは省略可能です。)  <br/> |
    |_sipfederationtls _tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |(このフィールドは省略可能です。)  <br/> |
   
    ![Dreamhost-5-1](../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. [ **Add Record Now!**] を選択します。
    
    ![Dreamhost-BP-Configure-5-2](../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. 上の 2 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

  
