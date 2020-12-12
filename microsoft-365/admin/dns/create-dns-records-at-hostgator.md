---
title: Hostgator で Microsoft 用の DNS レコードを作成する
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: ドメインを確認し、メール、Skype for Business Online、および Hostgator for Microsoft のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 3fe13df9b7e41d88c9bf06149eb894a028c4e350
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658089"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Hostgator で Microsoft 用の DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。 
  
使用している DNS ホスティング プロバイダーが Hostgator の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
> [!IMPORTANT]
> この記事の他の手順を使用して[](#point-your-domain-to-your-hosting-account)DNS レコードを追加する前に、最初の手順を実行する必要があります。 

Hostgator でこれらすべての変更を行った後、ドメインは Microsoft サービスで動作するために設定されます。
  

  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="point-your-domain-to-your-hosting-account"></a>ドメインがホスティング アカウントを指すようにする
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> この手順どおりに行ってから、この記事のその他の手順どおりに行う必要があります。 
  
この手順に従って、ドメインとホスティング アカウントを関連付けます。
  
1. まず、[このリンク](https://portal.hostgator.com/)を使って Hostgator でドメイン管理ページにアクセスします。 ログインするように求められます。
    
2. 左側 **の [ドメイン** ] を選択します。
  
3. [ドメイン **の管理] ページ** で、更新するドメインを選択します。 
  
4. 左側のポップアップ メニューで、[ネーム サーバー] を **選択します**。
  
5. ドメインの **[ネーム サーバー** ] ページの[ホスティング アカウントを自動的にポイントする] ドロップダウン リストで、ドメインに関連付けられているホスティング アカウントを選択します。 
  
6. [Save **Name Servers] (ネーム サーバーの保存) を選択します**。
    
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。 
  
Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. 開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. cPanel アドレスは次のように表示されます https://YourSiteAddress:secure-port-number 。 Hostgator から受け取ったサインアップ メールにはそのアドレスが指定され、cPanel リンクはホスティング ページでも **利用** できます)。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md). 
  
2. [コントロール **パネル] ページの** [ドメイン] 領域 **で** 、[Advanced **Zone Editor] を選択します**。
    
3. [Advanced **Zone Editor]** ページの [Add **a Record]** 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**名前** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
    |Use  *your* domain_name . (for example, fourthcoffee.com.)  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
4. [ **Add Record** ] を選択します。
    
5. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
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

> [!IMPORTANT]
> この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。 
  
1. 開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. cPanel アドレスは次のように表示されます https://YourSiteAddress:secure-port-number 。 Hostgator から受け取ったサインアップ メールにはそのアドレスが指定され、cPanel リンクはホスティング ページでも **利用** できます)。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md). 
  
2. [コントロール **パネル] ページの** [電子メール] 領域 **で** 、[MX エントリ] **を選択します**。
    
 
3. [ **Email Routing**] 領域で、[ **Remote Mail Exchanger**] を選びます。

4. [**変更**] を選択します。
  
5. [新 **しいレコードの** 追加] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    |**Priority**|**Destination**|
    |:-----|:-----|
    |0  <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注: Microsoft アカウントから** 取得\< *domain-key*  \> します。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
  
6. [新しい **レコードの追加] を選択します**。
   
 
7. その他の MX レコードが [ **MX Records**] セクションにある場合は、それぞれのレコードを削除します。 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。 
  
1. 開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. cPanel アドレスは次のように表示されます https://YourSiteAddress:secure-port-number 。 Hostgator から受け取ったサインアップ メールにはそのアドレスが指定され、cPanel リンクはホスティング ページでも **利用** できます)。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md). 
  
2. [コントロール **パネル] ページの** [ドメイン] 領域 **で** 、[Advanced **Zone Editor] を選択します**。
    
3. 6 つの CNAME レコードの最初のレコードを追加します。
    
    [Advanced **Zone Editor]** ページの [Add **a Record]** 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |**名前**|**TTL**|**Type**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*。 (例: autodiscover.fourthcoffee.com。)  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*。 (たとえば、sip.fourthcoffee.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*。 (たとえば、lyncdiscover.fourthcoffee.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*。 (例: enterpriseregistration.fourthcoffee.com。)  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*。 (例: enterpriseregistration.fourthcoffee.com。)  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. [ **Add Record** ] を選択します。

5. 他の 5 つの CNAME レコードをそれぞれ追加します。
    
    [Add **a Record]** セクションで、テーブルの次の行の値を使用してレコードを作成し、[Add **Record]** を再度選択してレコードを完成します。 
    
    6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords)を参照してください。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
> [!IMPORTANT]
> この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。 
  
1. 開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. cPanel アドレスは次のように表示されます https://YourSiteAddress:secure-port-number 。 Hostgator から受け取ったサインアップ メールにはそのアドレスが指定され、cPanel リンクはホスティング ページでも **利用** できます)。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md). 
  
2. [コントロール **パネル] ページの** [ドメイン] 領域 **で** 、[Advanced **Zone Editor] を選択します**。
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |**名前**|**TTL**|**Type**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |Use  *your* domain_name . (for example, fourthcoffee.com.)  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
  
4. [ **Add Record** ] を選択します。
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。 
  
1. 開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. cPanel アドレスは次のように表示されます https://YourSiteAddress:secure-port-number 。 Hostgator から受け取ったサインアップ メールにはそのアドレスが指定され、cPanel リンクはホスティング ページでも **利用** できます)。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md). 
  
2. [コントロール **パネル] ページの** [ドメイン] 領域 **で** 、[Advanced **Zone Editor] を選択します**。

    
3. 2 つの SRV レコードの最初のレコードを追加します。
    
    [ **Advanced DNS Zone Editor**] ページの [ **Add a Record**] 領域で、新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
    |**名前**|**TTL**|**Type**|**Priority**|**Weight**|**Port**|**対象**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls。 *domain_name*。 (例: _sip._tls.fourthcoffee.com)。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp. *domain_name*。 (例: _sipfederationtls._tcp.fourthcoffee.com)。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. [ **Add Record** ] を選択します。

  
5. 残りの SRV レコードを追加します。
    
    [Add **a Record]** セクションで、テーブルの次の行の値を使用してレコードを作成し、[Add **Record]** を再度選択してレコードを完成します。 
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
