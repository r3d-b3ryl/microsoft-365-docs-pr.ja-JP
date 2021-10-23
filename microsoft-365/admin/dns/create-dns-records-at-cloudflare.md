---
title: Connectに Cloudflare で DNS レコードをMicrosoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、Cloudflare for Microsoft で電子メール、Skype for Business、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 968979be1da5c54a109687df16cb706efb3bdea5
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556943"
---
# <a name="connect-your-dns-records-at-cloudflare-to-microsoft-365"></a>Connectに Cloudflare で DNS レコードをMicrosoft 365

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 

使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。

## <a name="before-you-begin"></a>はじめに

ドメインの DNS レコードを設定するには、次の 2 つのオプションがあります。

- [**ドメイン の使用Connect**](#use-domain-connect-to-verify-and-set-up-your-domain)別のメール サービス プロバイダーを使用してドメインを設定していない場合は、ドメイン Connect の手順を使用して、新しいドメインを自動的に確認し、Microsoft 365 で使用する設定を行います。 

または

- [**手動の手順を使用する**](#create-dns-records-with-manual-setup) 以下の手動手順を使用してドメインを確認し、ドメイン レジストラーに追加するレコードを選択します。 これにより、便利な場合など、新しい MX (メール) レコードを設定できます。 

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>ドメインを確認Connect設定するには、ドメイン サーバーを使用します。

次の手順に従って、Cloudflare ドメインを自動的に確認して設定Microsoft 365。

1. [ドメインMicrosoft 365 管理センター] を **設定**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**し**</a>、セットアップするドメインを選択します。

1. 3 つのドット (その他のアクション) を選択し、[セットアップ>を **選択します**。

1. [ドメインの接続方法]ページで、[続行] **を選択します**。   

1. [DNS レコードの追加] ページで、[DNS レコードの **追加] を選択します**。

1. Cloudflare ログイン ページで、アカウントにサインインし、[承認] を **選択します**。
    
    これで、ドメインのセットアップが完了Microsoft 365。 

## <a name="create-dns-records-with-manual-setup"></a>手動セットアップで DNS レコードを作成する

Cloudflare でこれらのレコードを追加すると、ドメインはユーザーサービスで動作Microsoft 365されます。

> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
### <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。 
  
Cloudflare にサインアップしたときに、Cloudflare の [ Setup] プロセスを使用してドメインを追加しました。 
  
追加したドメインは、Cloudflare または別のドメイン レジストラーから購入されました。 Microsoft 365 でドメインの DNS レコードを確認して作成するには、まず、Cloudflare ネーム サーバーを使用するために、ドメイン レジストラーでネーム サーバーを変更する必要があります。
  
ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。
    
    |||
    |:-----|:-----|
    |1 番目のネーム サーバー  <br/> |Cloudflare によって提供されるネーム サーバーの値を使用します。  <br/> |
    |2 番目のネーム サーバー  <br/> |Cloudflare によって提供されるネーム サーバーの値を使用します。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 他にネーム サーバーが一覧表示されている場合は、それらを削除する必要があります。 
  
3. 変更内容を保存します。
    
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft の電子メールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
### <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
  
1. [ホーム] ページで、更新するドメインを選択します。 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::
 
1. ドメインの [概要] ページで **、[DNS] を選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::
  
1. [DNS 管理] ページで **、[+レコードの** 追加] を選択し、テーブルの値を入力またはコピーして貼り付けます。 
    
    | **Type** | **Name** | **TTL** | **Content** |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)    |
    
1. **[保存]** を選択します。
  
1. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻ってレコードを検索します。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
レコードを確認するには、次Microsoft 365。
  
1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。
    
2. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。   
  
3. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
    
### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
  
2. [ホーム] ページで、更新するドメインを選択します。 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::
 
3. ドメインの [概要] ページで **、[DNS] を選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

4. [DNS 管理] ページで **、[+レコードの** 追加] を選択し、テーブルの値を入力またはコピーして貼り付けます。 
    
    | **Type** | **名前** | **メール サーバー** |  **TTL** | **Priority** |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:** 自分の *\<domain-key\>* アカウントからMicrosoft 365します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md) |30 分  <br/> | 1  <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。 <br/>|
   
5. **[保存]** を選択します。
  
6. [MX レコード] セクションに他の **MX** レコードが一覧表示されている場合は、[編集] を選択して削除し、[削除] を選択 **します**。 
  
7. 確認ダイアログ ボックスで、[削除] **を選択して** 変更を確認します。 

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
      
2. [ホーム] ページで、更新するドメインを選択します。 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::
 
3. ドメインの [概要] ページで **、[DNS] を選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

4. CNAME レコードを追加します。
    
    **[DNS 管理] ページで****、[+レコードの** 追加] を選択し、テーブルの値を入力またはコピーして貼り付けます。

    | 種類 | 氏名 | Target | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minutes  <br/> |> |
  
6. **[保存]** を選択します。
    
### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。 代わりに、現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが "*1 つ*" の SPF レコードに含まれるようにします。 
  
1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。  
  
2. [ホーム] ページで、更新するドメインを選択します。 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::
 
3. ドメインの [概要] ページで **、[DNS] を選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

4. [DNS 管理] ページで **、[+レコードの** 追加] を選択し、次の表から値を選択します。  
    
    | 種類 | 氏名 | TTL | コンテンツ |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。   |
 
5. **[保存]** を選択します。
  
## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスにネットワーク を使用している場合にのみ、このオプションをMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信用の SRV レコードが 2 件、ユーザーをサービスにサインインして接続するための CNAME レコードが 2 件必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

> [!IMPORTANT]
> Cloudflare は、この機能を利用できる状態にするための責任を負います。 以下の手順と現在の Cloudflare GUI (グラフィカル ユーザー インターフェイス) の間に不一致が発生した場合は[、Cloudflare](https://community.cloudflare.com/)インターフェイスをCommunity。 

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
      
2. [ホーム] ページで、更新するドメインを選択します。 

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::
  
3. ドメインの [概要] ページで **、[DNS] を選択します**。
  
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

4. 2 つの SRV レコードの最初のレコードを追加します。

    [DNS 管理] ページで **、[+レコード** の追加] を選択し、テーブルの最初の行から値を選択またはコピーして貼り付けます。
        
    | **Type** | **名前** | **Service** | **Protocol** |  **TTL** | **Priority** | **Weight** | **Port** | **Target** |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip | ユーザーのアカウント *をdomain_name。* たとえば、contoso.com  ||TLS |30 分 | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|ユーザーのアカウント *をdomain_name。* たとえば、contoso.com   |30 分 |100 |1 |5061 | sipfed.online.lync.com |
  
5. **[保存]** を選択します。

6. テーブルの 2 行目から値を選択して、他の SRV レコードを追加します。 
 
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する
  
1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
      
2. [ホーム] ページで、更新するドメインを選択します。 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::
 
3. ドメインの [概要] ページで **、[DNS] を選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

4. 1 番目の CNAME レコードを追加します。
    
    [DNS 管理] ページで **、[+レコード** の追加] を選択し、次の表の最初の行の値を入力またはコピーして貼り付けます。
    
    |**Type**|**Name**|**Target**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
  
1. [保存] を **選択します**。 
  
1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高度なオプション: Intune とモバイル デバイスの管理 (Microsoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理では、ユーザーがサービスにデバイスを登録できるよう、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。
      
2. [ホーム] ページで、更新するドメインを選択します。 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="更新するドメインを選択します。":::
 
3. ドメインの [概要] ページで **、[DNS] を選択します**。

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="[DNS] を選択します。":::

4. 1 番目の CNAME レコードを追加します。
    
    [DNS 管理] ページで **、[+レコード** の追加] を選択し、テーブルの最初の行から値を入力またはコピーして貼り付けます。
    
    |**Type**|**Name**|**Target**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
  
8. **[保存]** を選択します。 
  
9. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

  
