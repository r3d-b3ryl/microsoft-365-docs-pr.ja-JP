---
title: Microsoft の Dyn.com で DNS レコードを作成する
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: ドメインを確認し、電子メール、Skype for Business Online、および Dyn.com のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: f9b705f94f05799b0aa97539e372c3efcfe2e4c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629589"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a>Microsoft の Dyn.com で DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Dyn.com の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
 
Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。 
    
3. ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。
    
4. [**エキスパートインターフェイスを有効にする**] を選択します。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-検証-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. [ **Create Record**] を選びます。
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。 
    
3. ドメインの [DNS] ページで、[**プレファレンス**] を選択します。
    
4. [**エキスパートインターフェイスを有効にする**] を選択します。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |MX  <br/> |10  *\<ドメインキー\>*  .mail.protection.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **10** は MX 優先度の値です。 MX 値の先頭に追加して、スペースで値の残りの部分から区切ってください。  <br/> **注:** Microsoft アカウントから* \<ドメインキー\> *を取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)      <br>    優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |
   
    ![Dyn-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. [ **Create Record**] を選びます。
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. 他の MX レコードがある場合は、[ **DELETE**] 列で各レコードのチェック ボックスをオンにして削除します。 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. [**変更の適用**] を選択します。
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な6つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。 
    
3. ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。
    
4. [**エキスパートインターフェイスを有効にする**] を選択します。
    
5. 6 つの CNAME レコードの最初のレコードを追加します。
    
    [ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リストから [ **Type**] の値を選びます。) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Dyn-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. [ **Create Record**] を選びます。
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. 残りの 5 つの CNAME レコードを追加します。
    
    [ **ADD DNS record** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **create record** ] を選択してそのレコードを完成させます。 
    
    6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。
  
1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。 
    
3. ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。
    
4. [**エキスパートインターフェイスを有効にする**] を選択します。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![Dyn-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. [ **Create Record**] を選びます。
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft に必要な2つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。 最初にログインするように求められます。 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。 
    
3. ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。
    
4. [**エキスパートインターフェイスを有効にする**] を選択します。
    
5. 2 つの SRV レコードの最初のレコードを追加します。
    
    [ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リストから [ **Type**] の値を選びます。) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip _tls|600|SRV|100 1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
    |_sipfederationtls _tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**<br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![Dyn-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. [ **Create Record**] を選びます。
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. 残りの SRV レコードを追加します。
    
    [ **ADD DNS record** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **create record** ] を選択してそのレコードを完成させます。 
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
