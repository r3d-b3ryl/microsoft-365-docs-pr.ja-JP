---
title: Microsoft の Google ドメインで DNS レコードを作成する
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: ドメインを確認して、Microsoft の Google ドメインで電子メール、Lync、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: baa406f61346dc052ab90a1b1c1271ab585d92c7
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939205"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Microsoft の Google ドメインで DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Google Domains の場合は、この記事に記載された手順に従い、ドメインの確認を行って、メールや Lync などの DNS レコードを設定します。
  
これらのレコードを Google ドメインで追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. DNS レコードの追加後にメールフローなどに問題が発生した場合は、「 [Microsoft でドメインまたは DNS レコードを追加した後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
1. [**サインイン**] を選択します。
    
2. ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。
    
2. [**マイドメイン**] ページで、Microsoft と共に使用するドメインを見つけて、その横にある [**管理**] リンクを選択します。 左側のナビゲーションで、[ **DNS**] を選択します。
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**名前** <br/> |**Type** <br/> |**TTL** <br/> |**Data** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
4. [**追加**] を選択します。
    
5. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
2. [**サインイン**] を選択します。
    
3. ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。
4. [ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。
    
    > [!IMPORTANT]
    > G Suite メール アカウントを持っている場合は、そのアカウントに関連付けられている MX レコードを最初に削除する必要があります。 G Suite MX レコードでは、Microsoft に必要な MX レコードを追加することはできません。 G Suite のレコードを削除しても、G Suite アカウントは削除されないことにご注意ください。 G Suite の MX レコードを削除するには、次の手順のようにします。 
  
5. [**統合レコード**] セクションの [ **G Suite** ] 領域で、[**削除**] を選択します。
    
    (You may have to scroll down.)
    
    ![[代理レコード] セクションで、[削除] を選択します。](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. **[削除]** を選択します。
    
    ![[削除] を選択します。](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名前**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **0** は MX 優先度の値です。 MX 値の先頭に追加して、値の残りの部分からスペースで区切ってください。  <br/> **注:** Microsoft アカウントから自分の\<*ドメイン キー*\>を取得します。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)          優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. **[追加]** を選択します。
    
    ![[追加] を選択します。](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. 他のカスタム MX レコードがある場合は、それを削除します。
    
1. MX レコードの行で [**編集**] を選択します。 
    
    ![MX レコード行の [編集] を選択します。](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. その他のカスタム MX レコードごとに、[**データ**] ボックスのエントリを選択し、キーボードの**delete**キーを押してそのレコードを削除します。 
    
    各 MX レコードの [ **Data**] エントリの削除が終わるまで、この操作を繰り返します。 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. その他の MX レコードのそれぞれの**データ**入力を削除したら、[**保存**] を選択して変更を保存します。 
    
    ![[保存] を選択します。](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な5つの CNAME レコードを追加する

1. 開始するには、[Google Domains]https://domains.google.com/registrar)ページにアクセスして、サインインします。
    
2. [ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。 
    
3. 1 番目の CNAME レコードを追加します。
    
    [ **Custom resource records**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名前**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. **[追加]** を選択します。
    
    ![[追加] を選択します。](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. 残りの 4 つの CNAME レコードを追加します。
    
    [ **Custom resource records** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。 
    
    必要な CNAME レコードをすべて作成するまで、このプロセスを繰り返します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)を参照してください。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
1. [**サインイン**] を選択します。
    
2. ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。
    
3. [ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。 
    
4. [ **Custom resource records** ] セクションの [TXT record] 行で、[ **Edit**] を選択します。 
    
    > [!IMPORTANT]
    > Google Domains では TXT レコードが 1 つのセットとして格納されており、このセットには複数のレコードを入れることができます。既に他の TXT レコードが 1 つ以上あるときは (たとえば、ドメインの検証に使用した TXT レコード)、新しい TXT レコードをそのレコード セットに追加する必要があります。追加の TXT レコードを別の行として入力しようとすると、「 **Duplicate record**」というエラー メッセージが返されます。 
  
    ![TXT レコード行の [編集] を選択します。](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. **(+)** コントロールを選択します。 
    
    ![プラスコントロールを選択する](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    (下へスクロールしなければならないことがあります。)
    
    |**Data**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           
   
   ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. [**保存**] を選択します。
    
    ![[保存] を選択します。](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
2. [**サインイン**] を選択します。
    
3. ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。
    
4. [ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。 
    
5. 1 番目の SRV レコードを追加します。
    
    In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**名前**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip _tls|SRV|1H|100 1 443 sipdir.online.lync.com. **この値は、ピリオド (.) で終了する必要があります。****注:** このエントリをコピーして貼り付けることをお勧めします。この場合、すべてのスペースが正しい状態に保たれます。           |
    |_sipfederationtls _tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**

    スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。       
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. **[追加]** を選択します。
    
    ![[追加] を選択します。](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. 残りの SRV レコードを追加します。
    
    [ **Custom resource records** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。 
    
    > [!NOTE]
    > 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
