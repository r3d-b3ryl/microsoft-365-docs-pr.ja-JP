---
title: MyDomain で Office 365 用の DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: ドメインを確認し、メール、Skype for Business Online、その他のサービスに対する DNS レコードを Office 365 用の My Domain でセットアップする方法について説明します。
ms.openlocfilehash: 5a935ea456175f6d63926c9aa33280c4ec113abd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249371"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a>Office 365 用の MyDomain で DNS レコードを作成する


  
 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
> [!CAUTION]
> MyDomain の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Office 365 プランでも、MyDomain で DNS レコードを管理する場合は、[かなりのサービスの制限事項](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。 
  
サービスの制限事項があっても MyDomain で自分の Office 365 DNS レコードを管理する場合は、この記事に示す手順に従って、メールや Skype for Business Online などの DNS レコードを設定してください。
    
これらのレコードを MyDomain で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。
    
2. [**お気に入り**] セクションで、[**Domain Central**] を選択します。
    
3. [**ドメイン**] で、編集するドメインの名前を選択します。
    
4. [**概要**] 行で、[**DNS**] を選択します。
    
5. [**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。
    
6. [**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    ||
    |:-----|
    |**Content** <br/> |
    |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
7. [**追加**] を選択します。
    
8. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。
  
Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。
    
2. [**ドメイン**] ページで、確認するドメインを選択します。 
    
3. [**セットアップ**] ページで、[**セットアップの開始**] を選択します。
    
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**お気に入り**] セクションで、[**Domain Central**] を選択します。
    
3. [**ドメイン**] で、編集するドメインの名前を選択します。
    
4. [**概要**] 行で、[**DNS**] を選択します。
    
5. [**変更**] ドロップダウン リストから、[**MX レコード**] を選択します。
    
    ![MyDomain-BP-Configure-2-1](../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |**[優先度]**|**Host**|**Points To:**|
    |:-----|:-----|:-----|
    |0  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |@  <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/> **注:** Office 365 アカウントから自分の\<*ドメイン キー*\>を取得します。 > [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MyDomain-BP-Configure-2-2](../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. [**追加**] を選択します。
    
    ![MyDomain-BP-Configure-2-3](../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. MX レコードが他にもある場合は、各レコードの [**アクション**] 列にある [**削除**] を選択して削除します。 
    
    ![MyDomain-BP-Configure-2-4](../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. [**OK**] を選択します。
    
    ![MyDomain-BP-Configure-2-5](../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**お気に入り**] セクションで、[**Domain Central**] を選択します。
    
3. [**ドメイン**] で、編集するドメインの名前を選択します。
    
4. [**概要**] 行で、[**DNS**] を選択します。
    
5. [**変更**] ドロップダウン リストから、[**CNAME エイリアス**] を選択します。
    
    ![MyDomain-BP-Configure-3-1](../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. 1 番目の CNAME レコードを追加します。
    
    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |**Host**|**Points To:**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. [**追加**] を選択し、最初のレコードを追加します。 
    
    ![MyDomain-BP-Configure-3-3](../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. 2 番目の CNAME レコードを追加します。
    
    上の表の 2 行目の値を使用し、[**追加**] を選択して 2 番目のレコードを追加します。 
    
    同様に、表の 3 行目、4 行目、5 行目、6 行目の値を使用して、残りのレコードを追加します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードになるようにします。 次に例を示します。 参考にしてください。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**お気に入り**] セクションで、[**Domain Central**] を選択します。
    
3. [**ドメイン**] で、編集するドメインの名前を選択します。
    
4. [**概要**] 行で、[**DNS**] を選択します。
    
5. [**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。
    
    ![MyDomain-BP-Configure-4-1](../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. [**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |**Content**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![MyDomain-BP-Configure-4-2](../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. [**追加**] を選択します。
    
    ![MyDomain-BP-Configure-4-3](../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> MyDomain の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Office 365 プランでも、MyDomain で DNS レコードを管理する場合は、[かなりのサービスの制限事項](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。 
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
