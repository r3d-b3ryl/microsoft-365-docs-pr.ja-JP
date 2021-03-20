---
title: Microsoft の DNS レコード Dyn.com 作成する
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法については、Microsoft Dyn.com 説明します。
ms.openlocfilehash: 432dc630d49cc3494d17b3f007f813d66dc6b1c3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910332"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a>Microsoft の DNS レコード Dyn.com 作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。 
  
使用している DNS ホスティング プロバイダーが Dyn.com の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
 

  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。 
    
3. ドメインの **DNS ページ** で、[基本設定] **を選択します**。
    
4. [エキスパート **インターフェイスの有効化] を選択します**。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. [レコード **の作成] を選択します**。
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
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

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。 
    
3. ドメインの DNS ページで、[基本設定] **を選択します**。
    
4. [エキスパート **インターフェイスの有効化] を選択します**。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |MX  <br/> |10  *\<domain-key\>*  .mail.protection.outlook.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **10** は MX 優先度の値です。 MX 値の先頭に追加して、スペースで値の残りの部分から区切ってください。  <br/> **注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)      <br>    優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。 <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. [レコード **の作成] を選択します**。
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. 他の MX レコードがある場合は、[ **DELETE**] 列で各レコードのチェック ボックスをオンにして削除します。 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. **[Apply Changes]\(変更の適用\)** を選択します。
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。 
    
3. ドメインの **DNS ページ** で、[基本設定] **を選択します**。
    
4. [エキスパート **インターフェイスの有効化] を選択します**。
    
5. 6 つの CNAME レコードの最初のレコードを追加します。
    
    [ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リストから [ **Type**] の値を選びます。) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. [レコード **の作成] を選択します**。
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. 残りの 5 つの CNAME レコードを追加します。
    
    [DNS **レコードの追加**] セクションで、テーブルの次の行の値を使用してレコードを作成し、もう一度 [レコードの作成] を選択してそのレコードを完了します。 
    
    6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。
  
1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。 
    
3. ドメインの **DNS ページ** で、[基本設定] **を選択します**。
    
4. [エキスパート **インターフェイスの有効化] を選択します**。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. [レコード **の作成] を選択します**。
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。 最初にログインするように求めるメッセージが表示されます 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. [ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。 
    
3. ドメインの **DNS ページ** で、[基本設定] **を選択します**。
    
4. [エキスパート **インターフェイスの有効化] を選択します**。
    
5. 2 つの SRV レコードの最初のレコードを追加します。
    
    [ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リストから [ **Type**] の値を選びます。) 
    
    |**Host**|**TTL**|**Type**|**データ**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|600|SRV|100 1 443 sipdir.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**<br>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
    |_sipfederationtls._tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**<br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. [レコード **の作成] を選択します**。
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. 残りの SRV レコードを追加します。
    
    [DNS **レコードの追加**] セクションで、テーブルの 2 行目の値を使用してレコードを作成し、もう一度 [レコードの作成] を選択して、そのレコードを完了します。 
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
