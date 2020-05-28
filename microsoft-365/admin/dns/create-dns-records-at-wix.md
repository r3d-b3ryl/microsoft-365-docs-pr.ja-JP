---
title: Microsoft の Wix で DNS レコードを作成する
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の Wix でその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: b5fe216e65954bbcbdd9a1da223258a8362743ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400294"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Microsoft の Wix で DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
使用している DNS ホスティング プロバイダーが Wix の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。
  
追加する主なレコードは次のとおりです。 
  
- [確認用に TXT レコードを追加する](#add-a-txt-record-for-verification)
    
- [MX レコードを追加して、自分のドメインのメールが Microsoft に届くよう](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)にします。
    
- [Microsoft に必要な5つの CNAME レコードを追加](#add-the-five-cname-records-that-are-required-for-microsoft)します。
    
- [迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Microsoft に必要な2つの SRV レコードを追加](#add-the-two-srv-records-that-are-required-for-microsoft)します。
    
これらのレコードを Wix で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_txt"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. **[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。 
    
3. DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**TXT Value** <br/> |**TTL** <br/> |
|自動入力  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。 
    
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
  
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
   
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_mx"> </a>

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. **[マイドメイン**] ページの [**メールボックス**] 領域で、[ **MX レコードの構成**] リンクを選択します。 
    
3. [**自分のメールプロバイダー** ] ドロップダウンリストから [**その他**] を選択します。 
    
4. [ **+ 他の追加**] を選択します。
    
5. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
|**Host Name**|**ポイント先**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|
|自動入力 <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/> **注:***\<domain-key\>* Microsoft アカウントからを取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md) |.0  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 | 1 Hour|
   
6. その他の MX レコードが一覧表示されている場合は、それぞれのレコードを削除します。 
    
7. **[OK]** を選択します。
    
8. 確認ダイアログボックスで、[ **OK]** を選択します。
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な5つの CNAME レコードを追加する
<a name="BKMK_cname"> </a>

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。最初にログインするように求められます。
    
2. **[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。 
    
3. CNAME レコードの DNS エディターの**cname (エイリアス)** 行で、[ **+ 追加**] を選択します。 
    
4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
|**Host Name**|**Points to**|**TTL**|
|:-----|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 Hour <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。 
    
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。  
  
1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. **[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。 
    
3. DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。 
    
4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
|**Host Name**|**TXT Value**|**TTL**|
|:-----|:-----|:-----|
|[空白のままにする]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。<br/> |TXT  <br/> | 1 Hour |
   
5. DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。 
    
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_srv"> </a>

1. まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. **[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。 
    
3. DNS エディターの [ **SRV** ] 行で、[ **+ 他の追加**] を選択します。 
    
4. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
|**Service**|**Protocol**|**Name**|**Weight**|**Port**|**Target**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |自動入力 |1   |443   |sipdir.online.lync.com |100 |1 Hour |
|sipfed|tcp |自動入力|1  |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。 
    
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  

