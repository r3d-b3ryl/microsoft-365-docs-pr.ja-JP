---
title: Google Domains で Microsoft 用の DNS レコードを作成する
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: ドメインを確認し、メール、Lync、その他のサービスに対する DNS レコードを Microsoft 用の Google ドメインでセットアップする方法について説明します。
ms.openlocfilehash: 9a1d0a8513f6071a3c9c686c10f6fd282f1a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910224"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Google Domains で Microsoft 用の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
使用している DNS ホスティング プロバイダーが Google Domains の場合は、この記事に記載された手順に従い、ドメインの確認を行って、メールや Lync などの DNS レコードを設定します。
  
これらのレコードを Google Domains で追加すると、使用しているドメインが、Microsoft のサービスで機能するように設定されます。
  

  
> [!NOTE]
> 通常は DNS の変更が反映されるまで約 15 分かかります。 ただし、インターネットの DNS システム全体を更新するための変更を行った場合、それ以上の時間がかかる場合もあります。 DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Microsoft でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
1. [**サインイン**] を選びます。
    
2. ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。
    
2. [**My Domains**] ページで、Microsoft で使用するドメインを見つけ、その横にある [**管理**] リンクを選択します。 左側のナビゲーションで、[**DNS**] を選択します。
    
3. [**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**名前** <br/> |**Type** <br/> |**TTL** <br/> |**データ** <br/> |
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
    
2. [**サインイン**] を選びます。
    
3. ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。
4. [**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。
    
    > [!IMPORTANT]
    > G Suite メール アカウントを持っている場合は、そのアカウントに関連付けられている MX レコードを最初に削除する必要があります。 G Suite の MX レコードがあると、Microsoft に必要な MX レコードなど、他の MX レコードを追加できません。 G Suite のレコードを削除しても、G Suite アカウントは削除されないことにご注意ください。 G Suite の MX レコードを削除するには、次の手順のようにします。 
  
5. 最初に、[**統合的な記録**] セクションの [**G Suite**] 領域で、[**削除**] を選択します。
    
    (下へスクロールすることが必要な場合があります)。
    
    ![[統合的な記録] セクションで [削除] をクリックする](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. **[削除]** を選択します。
    
    ![[削除] を選択する](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. [**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |**名前**|**Type**|**TTL**|**データ**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **0** は MX 優先度の値です。 MX 値の先頭に追加して、値の残りの部分からスペースで区切ってください。  <br/> **注: Microsoft アカウントから** 取得\<*domain-key*\> します。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)          優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。 <br/> |
   
    ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. **[追加]** を選択します。
    
    ![[追加] を選択する](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. 他のカスタム MX レコードがある場合は、それを削除します。
    
1. MX レコード行の **[編集]** を選択します。 
    
    ![MX レコード行の [編集] を選択します。](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. 他のカスタム MX レコードごとに、[**データ**] ボックスのエントリを選び、キーボードの **Delete** キーを押して、そのレコードを削除します。 
    
    各 MX レコードの [**Data**] エントリの削除が終わるまで、この操作を繰り返します。 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. 他の各 MX レコードの [**データ**] エントリを削除したら、[**保存**] を選択して変更を保存します。 
    
    ![[保存] を選択します。](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な 5 つの CNAME レコードを追加する

1. はじめに、[Google Domains ページ] (https://domains.google.com/registrar)) にアクセスしてサインインします。
    
2. [**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。 
    
3. 1 番目の CNAME レコードを追加します。
    
    [**Custom resource records**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (下へスクロールすることが必要な場合があります)。
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |**名前**|**Type**|**TTL**|**データ**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
    ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. **[追加]** を選択します。
    
    ![[追加] を選択する](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. 残りの 4 つの CNAME レコードを追加します。
    
    [**カスタム リソース レコード**] セクションで、表の次の行の値を使用してレコードを作成して、もう一度 [**追加**] を選んでレコードの作成を完了します。 
    
    必要な CNAME レコードをすべて作成するまで、このプロセスを繰り返します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords)を参照してください。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
1. [**サインイン**] を選びます。
    
2. ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。
    
3. [**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。 
    
4. [**カスタム リソース レコード**] セクションの TXT レコードの行の [**編集**] を選びます。 
    
    > [!IMPORTANT]
    > Google Domains では TXT レコードが 1 つのセットとして格納されており、このセットには複数のレコードを入れることができます。既に他の TXT レコードが 1 つ以上あるときは (たとえば、ドメインの検証に使用した TXT レコード)、新しい TXT レコードをそのレコード セットに追加する必要があります。追加の TXT レコードを別の行として入力しようとすると、「**Duplicate record**」というエラー メッセージが返されます。 
  
    ![TXT レコード行の [編集] を選択します。](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. [**+**] コントロールを選びます。 
    
    ![プラス コントロールを選択します。](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    (下へスクロールすることが必要な場合があります)。
    
    |**データ**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           
   
   ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. [**保存**] を選択します。
    
    ![[保存] を選択します。](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
2. [**サインイン**] を選びます。
    
3. ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。
    
4. [**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。 
    
5. 最初の SRV レコードを追加します。
    
    [**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |**名前**|**Type**|**TTL**|**データ**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H|100 1 443 sipdir.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません** **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
    |_sipfederationtls._tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**

    スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。       
   
    ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. **[追加]** を選択します。
    
    ![[追加] を選択する](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. 残りの SRV レコードを追加します。
    
    [**カスタムカスタム リソース レコード**] セクションで、表の 2 行目の値を使用してレコードを作成して、もう一度 [**追加**] を選んでレコードの作成を完了します。 
    
    > [!NOTE]
    > 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
