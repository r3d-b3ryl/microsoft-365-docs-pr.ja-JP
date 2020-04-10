---
title: Bluehost で Office 365 用の DNS レコードを作成する
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: ドメインを確認し、電子メール、Skype for Business Online、および Bluehost for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 8d8217aa3b87e103f37063248899467d79b6cf18
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211837"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a>Bluehost で Office 365 用の DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Bluehost の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
これらのレコードを Bluehost で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。 
    
    (下へスクロールしなければならないことがあります。)
    
3. [ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。
    
4. [* * DNS ゾーンエディター * *] ページの [ **Dns レコードの追加**] 領域で、新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
5. [ **Add record**] を選択します。
    
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
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

1. まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。 
    
    (下へスクロールしなければならないことがあります。)
    
3. [ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/>**注:** Office 365 アカウントから自分の\<*ドメイン キー*\>を取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |.0  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |
   
   ![ドロップダウンリストから [種類] を選択する](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. [ **Add record**] を選択します。
    
    ![[Add Record] を選択します。](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. その他の MX レコードが [ **MX (Mail Exchanger)** ] セクションにある場合は、それぞれのレコードを削除します。 
    
    その他の MX レコードのいずれかで、[削除] を選択し**ます。**
    
    ![追加の MX レコードごとに [削除] を選択します。](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. 確認ダイアログボックスで、[ **OK]** を選択します。
    
    ![[OK] を選択します。](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. 同じ手順に従って、一覧に表示されているその他の MX レコードをすべて削除します。
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。 
    
    (下へスクロールしなければならないことがあります。)
    
3. [ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。
    
4. [ **A (ホスト)** レコード] セクションで、**自動検出**レコードの行を見つけて、その行に対して [**削除**] を選択します。 
    
    > [!IMPORTANT]
    > You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously. 
  
    ![[削除] を選択します。](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. **[OK]** を選択します。
    
    ![[OK] を選択します。](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. 6 つの CNAME レコードの最初のレコードを作成します。
    
    [ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![最初の CNAME レコードを作成する](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. [ **Add record**] を選択します。
    
    ![[Add Record] を選択します。](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. 他の 5 つの CNAME レコードをそれぞれ追加します。
    
    引き続き [ **DNS レコードの追加**] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。 
    
    6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 次に例を示します。 参考にしてください。 SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。 
  
1. まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。 
    
    (下へスクロールしなければならないことがあります。)
    
3. [ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
        
    |**Host Record**|**TTL**|**Type**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![TXT 値をコピーする](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. [ **Add record**] を選択します。
    
    ![[Add Record] を選択します。](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。 
    
    (下へスクロールしなければならないことがあります。)
    
3. [ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。
    
4. 2 つの SRV レコードの最初のレコードを作成します。
    
    [ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Service**|**Protocol**|**Host**|**TTL**|**Type**|**Priority**|**Weight**|**Port**|**Points To**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![新しいレコードの値をコピーする](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. [ **Add record**] を選択します。
    
    ![[Add Record] を選択します。](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. 残りの SRV レコードを追加します。
    
    引き続き [ **DNS レコードの追加**] セクションで、表の他の行の値を使用してレコードを作成し、[ **Add record** ] をもう一度選択してそのレコードを完成させます。 
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  

