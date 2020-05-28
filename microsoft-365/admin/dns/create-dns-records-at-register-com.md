---
title: Microsoft の Register.com で DNS レコードを作成する
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: ドメインを確認し、電子メール、Skype for Business Online、および Register.com のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 7b2353b4b6832c9316e302ace4db948e2550a28f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400330"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Microsoft の Register.com で DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Register.com の場合は、この記事に示す手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードの設定を行います。
  
追加する主なレコードは次のとおりです。 次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
- [Register.com で TXT レコードを追加して、ドメインを所有していることを確認する](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Microsoft に必要な CNAME レコードを追加する](#add-the-cname-records-that-are-required-for-microsoft)
    
- [迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Microsoft で必要な 2 つの SRV レコードを追加する](#add-the-two-srv-records-that-are-required-for-microsoft)
    
これらのレコードを Register.com で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。
  

  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Register.com で TXT レコードを追加して、ドメインを所有していることを確認する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
次の手順を実行するか、[ビデオ (44 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。
    
2. [ **ドメイン**] を選択します。
    
3. [**管理**] を選択します。
    
4. 変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。
    
5. [**高度な技術設定**] セクションまで下にスクロールしてから、[ **TXT レコードの編集 (SPF)**] を選択します。
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
7. [**続行**] を選択します。
    
8. 次のページで、[**続行**] をもう一度選択して、変更内容を確認します。 
    
9. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

次の手順を実行するか、[ビデオ (3 分 32 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。
    
2. [ **ドメイン**] を選択します。
    
3. [**管理**] を選択します。
    
4. 変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。
    
5. [**高度な技術設定**] セクションまでスクロールし、[**メールエクスチェンジャーレコードの編集**] を選択します。
    
    ![[メールエクスチェンジャーレコードの編集] を選択する](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    (ドロップダウンリストから**優先度**の値を選択します。) 
    
    |****Host Name****|****Priority****|****Mail Server****|
    |:-----|:-----|:-----|
    |@  <br/> |High  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/>  <br/>**注:**\<*domain-key*\>Microsoft アカウントからを取得します。 <br> [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. MX レコードが他にもリストされている場合は、レコードを 1 つずつ選択して削除します。
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. [**続行**] を選択します。
    
    ![[続行] を選択する](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. 次のページで [**続行**] を選択して、変更を確認して保存します。 
    
    ![[続行] を選択する](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

次の手順を実行するか、[ビデオ (4 分 23 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。
    
2. [ **ドメイン**] を選択します。
    
3. [**管理**] を選択します。
    
4. 変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。
    
5. [**高度な技術設定**] セクションまでスクロールし、[**ドメインエイリアスレコードの編集**] を選択します。
    
    ![[ドメインエイリアスレコードの編集] を選択する](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. [**追加するドメインエイリアス**] を選択します。
    
    ![[その他のドメインエイリアスの追加] を選択します。](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. 必要な CNAME レコードを追加します。
    
    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |****最初のフィールド (ラベルなし)****|****points to****|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![テーブルから DNS の値をコピーして貼り付けます。](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. 必要な CNAME レコードをすべて追加したら、[**続行**] を選択します。
    
    ![[続行] を選択する](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. 次のページで [**続行**] を選択して、変更を確認して保存します。 
    
    ![[続行] を選択する](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。  
  
次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。
    
2. [ **ドメイン**] を選択します。
    
3. [**管理**] を選択します。
    
4. 変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。
    
5. [**高度な技術設定**] セクションまでスクロールして、[ **TXT レコードの編集 (SPF)**] を選択します。
    
    ![[Edit TXT Records (SPF)] を選択します。](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    |****Host Name****|****TXT Record****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。  |
   
     ![テーブルから値をコピーして貼り付けます。](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. [**続行**] を選択します。
    
    ![[続行] を選択する](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. 次のページで [**続行**] を選択して、変更を確認して保存します。 
    
    ![[続行] を選択する](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

次の手順を実行するか、[ビデオ (5 分 55 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。
  
1. まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。
    
2. [ **ドメイン**] を選択します。
    
3. [**管理**] を選択します。
    
4. 変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。
    
5. [**高度な技術設定**] セクションまでスクロールして、[ **SRV レコードの編集**] を選択します。
    
    ![[SRV レコードの編集] を選択する](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. 2 つの SRV レコードの最初のレコードを追加します。
    
    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    (ドロップダウンリストから**優先度**の値を選択します。) 
    
    |****Service****|****Proto****|****Name****|****Priority****|****Weight****|****Port****|****Target****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |High  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |High  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. [ **Add MORE SRV records**] を選びます。
    
    ![[追加する SRV レコードの追加] を選択する](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. 2 番目の SRV レコードを追加します。
    
    上の表の 2 行目の値を 2 つ目のレコードのボックスに入力するか、コピーして貼り付けます。
    
9. 両方の SRV レコードを追加したら、[**続行**] を選択します。
    
    ![[続行] を選択する](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. 次のページで [**続行**] を選択して、変更を確認して保存します。 
    
    ![[続行] を選択する](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
