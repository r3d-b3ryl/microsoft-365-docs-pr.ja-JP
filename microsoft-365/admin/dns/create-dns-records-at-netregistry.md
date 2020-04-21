---
title: Microsoft の Netregistry で DNS レコードを作成する
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の Netregistry にあるその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 6aed84a4eaf95674358aa54986cfbb76edec2ef3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629313"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a>Microsoft の Netregistry で DNS レコードを作成する

探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)してください。 
  
使用している DNS ホスティング プロバイダーが Netregistry の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
  
追加する主なレコードは次のとおりです。
  
- [確認のための TXT レコードを追加する](#add-a-txt-record-for-verification)
    
- [MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [Microsoft に必要な CNAME レコードを追加する](#add-the-cname-records-that-are-required-for-microsoft)
    
- [迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Microsoft に必要な2つの SRV レコードを追加する](#add-the-two-srv-records-that-are-required-for-microsoft)
    
これらのレコードを Netregistry で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。
  
Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="bkmk_txt"> </a>

ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。 ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. 管理するドメインの横にある、[ **Manage** ] を選択します。
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. [ **Zone Manager** ] を選択します。
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. [ **Add a zone record**] の一覧から [ **TXT record** ] を選択し、[**新しいレコードの作成**] を選択します。
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > TXT ボックスでは、エントリの前後に引用符を使用する必要があります。 
  
    [ **New TXT Record** ] フォームに、次の表の値を入力するか、コピーして貼り付けます。 
    
    |**名前**|**TTL (秒)**|**TXT (ポイント先のアドレスまたは値)**|
    |:-----|:-----|:-----|
    |(空白のまま)  <br/> |3600 (秒)  <br/> |"MS = msXXXXXXXX"  <br/> **注:** これは例です。 この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. [ **Add record**] を選択します。
    
これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="bkmk_mx"> </a>

1. まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. 管理するドメインの横にある、[ **Manage** ] を選択します。
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. [ **Zone Manager** ] を選択します。
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. [**現在のゾーンレコード**] で、リスト内の各 mx レコードの横にある [**削除**] を選択して、既定の mx レコードを削除します。 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. [ **Add a zone record**] の一覧から [ **MX record** ] を選択し、[**新しいレコードの作成**] を選択します。
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. [**新しい MX レコード**] フォームで、次の表の値を入力するか、コピーして貼り付けます。 
    
    |**名前**|**TTL (秒)**|**Exchange (ポイント先アドレスまたは値)**|**ホストは完全に修飾されていますか?**|**優先順位 (優先度)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |3600 (秒)  <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft アカウントから* \<ドメインキー\> *を取得します。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)      |(チェックボックスをオンにします)  <br/> |10   <br/> For more information about priority, see What is MX priority?  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. [ **Add Record** ] を選択します。
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する
<a name="bkmk_cname"> </a>

1. まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. 管理するドメインの横にある、[ **Manage** ] を選択します。
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. [ **Zone Manager** ] を選択します。
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. [ **Add a zone record**] の一覧から [ **CNAME record** ] を選択し、[**新しいレコードの作成**] を選択します。
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |**名前**|**Type**|**TTL**|**ホスト (ポイントまたはアドレスの値)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (秒)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (秒)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (秒)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (秒)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (秒)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. [ **Add record**] を選択します。
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. 前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。
    
    レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。
  
1. まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. 管理するドメインの横にある、[ **Manage** ] を選択します。
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. [ **Zone Manager** ] を選択します。
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. [ **Add a zone record**] の一覧から [ **TXT record** ] を選択し、[**新しいレコードの作成**] を選択します。
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    > [!NOTE]
    > TXT ボックスでは、エントリの前後に引用符を使用する必要があります。 
  
    |**名前**|**Type**|**TTL**|**TXT データ (ターゲット)**|
    |:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |TXT  <br/> |3600 (秒)  <br/> |"v = spf1 には、以下のようにします。  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. [ **Add Record** ] を選択します。
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft に必要な2つの SRV レコードを追加する
<a name="bkmk_srv"> </a>

1. まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. 管理するドメインの横にある [ **manage**] を選択します。
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. [ **Zone Manager** ] を選択します。
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. [ **Add a zone record**] の一覧から [ **SRV record** ] を選択し、[**新しいレコードの作成**] を選択します。
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    > [!NOTE]
    > [名前] フィールドは、サービス (たとえば、_sip) とプロトコル (たとえば、_tls) の組み合わせです。 
  
    |**Type**|**名前**|**TTL (秒)**|**Priority**|**Weight**|**Port**|**対象**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (サービス)  <br/> |_sip _tls  <br/> |3600 (秒)  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV (サービス)  <br/> |_sipfederationtls _tcp  <br/> |3600 (秒)  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. [ **Add Record** ] を選択します。
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. 上記の手順を繰り返し、他の SRV レコードを作成します。
    
    2 番目のレコードのボックスに、上の表の 2 行目の値を入力するかコピーして貼り付けます。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  

