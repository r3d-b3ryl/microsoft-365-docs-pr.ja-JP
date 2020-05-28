---
title: Microsoft 用の「Excel で DNS レコードを作成する」
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他の Microsoft 用のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: b462979a3ab1bcf769c78d15d9fd3ad03f307ef0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400342"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a>Microsoft 用の「Excel で DNS レコードを作成する」

探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)してください。 
  
使用している DNS ホスティング プロバイダーが OVH の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
  
追加する主なレコードは次のとおりです。 
  
- [Microsoft 用の「Excel で DNS レコードを作成する」](#create-dns-records-at-ovh-for-microsoft)
    
- [MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Microsoft に必要な CNAME レコードを追加する](#add-the-cname-records-that-are-required-for-microsoft)
    
- [迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Microsoft で必要な 2 つの SRV レコードを追加する](#add-the-two-srv-records-that-are-required-for-microsoft)
    
これらのレコードを "準備中" で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。

  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="bkmk_txt"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. [ **Domains**] の下で、編集するドメインの名前を選択します。
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. [ **DNS zone**] を選択します。
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. [**エントリを追加する**] を選択します。
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. **TXT**の選択
    
    ![[すべて選択] TXT エントリ](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。 
    
    |**Record type**|**サブドメイン**|**TTL**|**値**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(空白のまま)  <br/> |3600 (秒)  <br/> |MS=msxxxxxxxx  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
7. [**確認**] を選択します。 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="bkmk_mx"> </a>

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. [ **Domains**] の下で、編集するドメインの名前を選択します。
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. [ **DNS zone**] を選択します。
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. [**エントリを追加する**] を選択します。
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. [ **MX**] を選択します。
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。 
    
    > [!NOTE]
    > 既定では、移動先の相対表記を使用します。これにより、ターゲットレコードの末尾にドメイン名が追加されます。 絶対表記を代わりに使用するには、次の表に示すように、ターゲット レコードにドットを追加します。 
  
    |**Record type**|**サブドメイン**|**TTL**|**優先度**|**ターゲット**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(空白のまま)  <br/> |3600 (秒)  <br/> |10    <br/> 優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> |\<domain-key\>. mail.protection.outlook.com。  <br/> **注:***\<domain-key\>* Microsoft アカウントからを取得します。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![メールの "差し込み" MX レコード](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. [**次へ**] を選択します。
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. [**確認**] を選択します。
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. MX レコードが他にもある場合は、[ **DNS zone** ] ページですべて削除します。 各レコードを選択し、[**アクション**] 列で [ごみ箱-**削除**可能] アイコンを選択します。 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. [**確認**] を選択します。
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する
<a name="bkmk_cname"> </a>

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. [ **Domains**] の下で、編集するドメインの名前を選択します。
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. [ **DNS zone**] を選択します。
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. [**エントリを追加する**] を選択します。
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. [ **CNAME**] を選択します。
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. 1 番目の CNAME レコードを作成します。
    
    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。 
    
    |**Record type**|**サブドメイン**|**ターゲット**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com。  <br/> |3,600 秒  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com。  <br/> |3,600 秒  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> |3,600 秒  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> |3,600 秒  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> |3,600 秒  <br/> |
   
    !["はい" CNAME レコード](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. [**次へ**] を選択します。
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. [**確認**] を選択します。
    
9. 前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。
    
    レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。 
  
1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. [ **Domains**] の下で、編集するドメインの名前を選択します。
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. [ **DNS zone**] を選択します。
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. [**エントリを追加する**] を選択します。
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. [ **TXT**] を選択します。
    
6. 新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。
    
    |**レコードの種類**|**サブドメイン**|**TTL**|**TXT 値**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(空白のまま)  <br/> |3600 (秒)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![[詳細] SPF の TXT レコードを追加する](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. [**次へ**] を選択します。
    
    ![[追加] SPF の TXT レコードを追加し、[次へ] を選択します。](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. [**確認**] を選択します。
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="bkmk_srv"> </a>

1. まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. [ **Domains**] の下で、編集するドメインの名前を選択します。
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. [ **DNS zone**] を選択します。
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. [**エントリを追加する**] を選択します。
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. [ **SRV**] を選択します。
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. 1 番目の SRV レコードを作成します。
    
    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。 
    
    |**Record type**|**サブドメイン**|**Priority**|**Weight**|**Port**|**TTL**|**ターゲット**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |_sip _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |3600 (秒)  <br/> |sipdir.online.lync.com。  <br/> |
    |SRV (Service)  <br/> |_sipfederationtls _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |3600 (秒)  <br/> |sipfed.online.lync.com。  <br/> |
       
    !["はい" SRV レコード](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. [**次へ**] を選択します。
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. [**確認**] を選択します。
    
9. 上記の手順を繰り返し、他の SRV レコードを作成します。2 番目のレコードのボックスに、上の表の 2 行目の値を入力するかコピーして貼り付けます。
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
