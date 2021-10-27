---
title: Connect 1 ~ 1 で IONOS で DNS レコード&をMicrosoft 365
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを 1&1 IONOS for Microsoft で設定する方法について説明します。
ms.openlocfilehash: d7bda20734851ece8e699bc19459f1eb6ece8f03
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586591"
---
# <a name="connect-your-dns-records-at-ionos-by-11-to-microsoft-365"></a>Connect 1 ~ 1 で IONOS で DNS レコード&をMicrosoft 365

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 

1&1 の IONOS が DNS ホスティング プロバイダーの場合は、この記事の手順に従ってドメインを確認し、電子メール、Skype for Business Online などについて DNS レコードを設定します。

## <a name="before-you-begin"></a>はじめに

ドメインの DNS レコードを設定するには、次の 2 つのオプションがあります。

- [**ドメイン の使用Connect**](#use-domain-connect-to-verify-and-set-up-your-domain)別のメール サービス プロバイダーを使用してドメインを設定していない場合は、ドメイン Connect の手順を使用して、新しいドメインを自動的に確認し、Microsoft 365 で使用する設定を行います。 

    または

- [**手動の手順を使用する**](#create-dns-records-with-manual-setup) 以下の手動手順を使用してドメインを確認し、ドメイン レジストラーに追加するレコードを選択します。 これにより、便利な場合など、新しい MX (メール) レコードを設定できます。 

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>ドメインを確認Connect設定するには、ドメイン サーバーを使用します。

次の手順に従って、IONOS を 1 つのドメインで自動的に確認&セットアップMicrosoft 365。

1. [ドメインMicrosoft 365 管理センター] を **設定**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**し**</a>、セットアップするドメインを選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-1.png" alt-text="[ドメイン] でドメインをMicrosoft 365。":::

1. 3 つのドット (その他のアクション) を選択し、[セットアップ>を **選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. [ドメインの接続方法]ページで、[続行] **を選択します**。   

1. [DNS レコードの追加] ページで、[DNS レコードの **追加] を選択します**。

1. [IONOS by 1&1 ログイン] ページで、アカウントにサインインし、[アカウント] **Connectを選択** し、[許可] を **選択します**。
 
    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-3.png" alt-text="[Connect] を選択し、[許可] を選択します。":::
   
    これで、ドメインのセットアップが完了Microsoft 365。 

## <a name="create-dns-records-with-manual-setup"></a>手動セットアップで DNS レコードを作成する

IONOS でこれらのレコードを 1&1 で追加すると、ドメインはユーザーと一緒に動作Microsoft サービス。
  
> [!CAUTION]
> 1~ 1&の IONOS では、ドメインに MX レコードとトップ レベルの自動検出 CNAME レコードの両方を設定できない点に注意してください。 このため、Exchange Online for Microsoft を構成する方法が制限されます。 回避策がありますが、1 から 1で IONOS でサブドメインを作成した経験がある場合にのみ、この方法を&勧めします。 このサービスの[](../setup/domains-faq.yml)制限にもかかわらず、1&1 で IONOS で独自の Microsoft DNS レコードを管理する場合は、この記事の手順に従ってドメインを確認し、電子メール、Skype for Business Online などのための DNS レコードを設定します。 
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
### <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. 開始するには、このリンクを使用して、IONOS の [ドメイン] ページに 1&1 で [移動します](https://my.1and1.com/)。 You'll be prompted to log in.

1. [ **メニュー] を** 選択し、[ドメインと **SSL] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::
  
1. [ **更新する** ドメインのアクション] で、ギア コントロールを選択し **、[DNS] を選択します**。
 
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから [DNS] を選択します。":::
    
1. [レコード **の追加] を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **[TXT] セクションを選択** します。
    
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-4.png" alt-text="[TXT] セクションを選択します。":::

1. [DNS レコードの追加] ページで、新しいレコードのボックスに、次の表の値を入力またはコピーして貼り付けます。 
    
    |**ホスト名** <br/> |**Value** <br/> | **TTL**
    |:-----|:-----|:-----|
    |(このフィールドは空白のままにする)  <br/> |MS=ms *XXXXXXXX*  <br/> 注: これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          | 1 hour |
    
1. **[保存]** を選択します。
  
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-5.png" alt-text="[保存] を選択します。":::
  
    数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

レコードを確認するには、次Microsoft 365。
  
1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。
    
1. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。
  
1. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
  
### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
  
> [!NOTE]
> アカウントに登録している場合は、1und1.de [サインインします](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 開始するには、このリンクを使用して、IONOS の [ドメイン] ページに 1&1 で [移動します](https://my.1and1.com/)。 You'll be prompted to log in.
    
1. [ **メニュー] を** 選択し、[ドメインと **SSL] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::
  
1. [ **更新する** ドメインのアクション] で、ギア コントロールを選択し **、[DNS] を選択します**。
 
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから [DNS] を選択します。":::
    
1. [レコード **の追加] を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **[MX] セクションを選択** します。
    
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX.png" alt-text="[MX] セクションを選択します。":::
  
1. [DNS レコードの追加] ページで、新しいレコードのボックスに、次の表の値を入力またはコピーして貼り付けます。 
    
    | **ホスト名**| **ポイント先** |**Priority**| **TTL** |
    |:-----|:-----|:-----| :-----|
    |  @  | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  注: Microsoft アカウント \<domain-key\> から取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。 | 1 hour |
  
1. **[保存]** を選択します。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX-Save.png" alt-text="[保存] を選択します。":::

1. MX レコードが既にリストされている場合は、[レコードの追加] ページで[レコードのごみ箱の削除] を選択して、各レコードを **削除** します。
 
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Delete.png" alt-text="[レコードの削除] を選択します。":::
 
### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

> [!NOTE]
> アカウントに登録している場合は、1und1.de [サインインします](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 開始するには、このリンクを使用して、IONOS の [ドメイン] ページに 1&1 で [移動します](https://my.1and1.com/)。 You'll be prompted to log in.
    
1. [ **メニュー] を** 選択し、[ドメインと **SSL] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::
  
1. [ **更新する** ドメインのアクション] で、ギア コントロールを選択し **、[DNS] を選択します**。
 
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから [DNS] を選択します。":::
    
    次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します<br/>(これは、1 つの IONOS&1 つのトップ レベル CNAME レコードのみをサポートしていますが、Microsoft では複数の CNAME レコードが必要なので、これが必要です。<br/>最初に、Autodiscover サブドメインを作成します。

1. [ **サブドメイン] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="[サブドメイン] を選択します。":::
  
1. [サブ **ドメインの追加] を選択します**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="[サブドメインの追加] を選択します。":::
  
1. 新しい **サブドメインの [サブドメインの** 追加] ボックスに、次の表の[サブドメインの追加] 値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します。

    |**サブドメインの追加**| **Alias** |
    |:-----|:-----|
    |autodiscover  <br/> | autodiscover.outlook.com |

1. [**作成した****自動検出** サブドメインのアクション] で、ギア コントロールを選択し、ドロップダウン リストから **[DNS]** を選択します。 <br/>
    
1. [レコード **の追加]** を選択し **、[CNAME] セクションを選択** します。

1. [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。 <br/>
    
    |**サブドメインの追加**| **Alias** |
    |:-----|:-----|
    |autodiscover  <br/> | autodiscover.outlook.com |
  
1. **[保存]** を選択します。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)を参照してください。 SPF レコードを検証するには、次のいずれかの[SPF 検証ツールを使用できます](../setup/domains-faq.yml)。 
  
> [!NOTE]
> アカウントに登録している場合は、1und1.de [サインインします](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 開始するには、このリンクを使用して、IONOS の [ドメイン] ページに 1&1 で [移動します](https://my.1and1.com/)。 You'll be prompted to log in.
    
1. [ **メニュー] を** 選択し、[ドメインと **SSL] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::
  
1. [ **更新する** ドメインのアクション] で、ギア コントロールを選択し **、[DNS] を選択します**。
 
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから [DNS] を選択します。":::
   
1. [レコード **の追加] を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **[SPF (TXT)] セクションを選択** します。
   
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT.png" alt-text="[SPF (TXT)] セクションを選択します。":::
 
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 <br/>
    
    |**型**|**ホスト名**|**Value**| **TTL** |
    |:-----|:-----|:-----|:-----|
    |SPF (TXT)  <br/> |(このフィールドは空のままにします。)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。 | 1 時間 |
  
1. **[保存]** を選択します。
 
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT-Save.png" alt-text="[保存] を選択します。":::
 
## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスにネットワーク を使用している場合にのみ、このオプションをMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信用の SRV レコードが 2 件、ユーザーをサービスにサインインして接続するための CNAME レコードが 2 件必要です。

### <a name="add-two-additional-cname-records"></a>2 つの追加の CNAME レコードを追加する
  
1. 開始するには、このリンクを使用して、IONOS の [ドメイン] ページに 1&1 で [移動します](https://my.1and1.com/)。 You'll be prompted to log in.
    
1. [ **メニュー] を** 選択し、[ドメインと **SSL] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::
  
1. [ **更新する** ドメインのアクション] で、ギア コントロールを選択し **、[DNS] を選択します**。
 
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから [DNS] を選択します。":::
    
    次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します<br/>(これは、1 つの IONOS&1 つのトップ レベル CNAME レコードのみをサポートしていますが、Microsoft では複数の CNAME レコードが必要なので、これが必要です。<br/>最初に、lyncdiscover サブドメインを作成します。

1. [ **サブドメイン] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="[サブドメイン] を選択します。":::
  
1. [サブ **ドメインの追加] を選択します**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="[サブドメインの追加] を選択します。":::
    
1. 新しい **サブドメインの [サブドメインの** 追加] ボックスに、次の表の[サブドメインの追加] 値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します。<br/> 
    
    |**サブドメインの追加**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
1. [ **作成** した **lyncdiscover** サブドメインのアクション] で、ギア コントロールを選択し、ドロップダウン リストから **[DNS]** を選択します。 <br/>
    
1. [レコード **の追加]** を選択し **、[CNAME] セクションを選択** します。

1. [ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。 <br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    
1. 別のサブドメイン (SIP) を作成します。 <br/>[サブ **ドメインの追加] を選択します**。
    
1. 新しい **サブドメインの [サブドメインの** 追加] ボックスに、次の表の[サブドメインの追加] 値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します。 <br/>
    
    |**サブドメインの追加**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |

1. [ **作成** したサブドメインのアクション] で、ギア コントロールを選択し、ドロップダウン リストから **[DNS]** を選択します。 <br/>
    
1. [レコード **の追加] を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **[CNAME] セクションを** 選択します。

1. [エイリアス **:] ボックス** に、次の表の **Alias** 値のみを入力またはコピーして貼り付けます。 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
1. 免責事項の [ **I am aware**] チェック ボックスをオンにして、[ **Save**] を選択します。

## <a name="add-the-two-srv-records-required-for-microsoft"></a>Microsoft に必要な 2 つの SRV レコードを追加する
  
> [!NOTE]
> アカウントに登録している場合は、1und1.de [サインインします](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 開始するには、このリンクを使用して、IONOS の [ドメイン] ページに 1&1 で [移動します](https://my.1and1.com/)。 You'll be prompted to log in.
    
1. [ **メニュー] を** 選択し、[ドメインと **SSL] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::
  
1. [ **更新する** ドメインのアクション] で、ギア コントロールを選択し **、[DNS] を選択します**。
 
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから [DNS] を選択します。":::
    
1. [レコード **の追加] を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **[SRV] セクションを** 選択します。
 
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV.png" alt-text="[SRV] セクションを選択します。":::
   
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 <br/>
    
    |**Type**|**Service**|**Protocol**|**ホスト名**|**ポイント先**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |_sip  <br/> |tls  <br/> |(このフィールドは空のままにします。)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
    |SRV  <br/> |_sipfederationtls  <br/> |tcp  <br/> |(このフィールドは空のままにします。)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 時間 <br/> |  
  
1. **[保存]** を選択します。
 
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV-Save.png" alt-text="[保存] を選択します。":::
 
1. 残りの SRV レコードを追加します。 
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
    
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高度なオプション: Intune とモバイル デバイスの管理 (Microsoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理では、ユーザーがサービスにデバイスを登録できるよう、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

> [!IMPORTANT]
> 他の CNAME レコードに使用したサブドメイン プロシージャに従い、次の表の値を指定します。 
  
1. 開始するには、このリンクを使用して、IONOS の [ドメイン] ページに 1&1 で [移動します](https://my.1and1.com/)。 You'll be prompted to log in.
    
1. [ **メニュー] を** 選択し、[ドメインと **SSL] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="[ドメインと SSL] を選択します。":::
  
1. [ **更新する** ドメインのアクション] で、ギア コントロールを選択し **、[DNS] を選択します**。
 
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="ドロップダウン リストから [DNS] を選択します。":::
    
    次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します<br/>(これは、1 つの IONOS&1 つのトップ レベル CNAME レコードのみをサポートしていますが、Microsoft では複数の CNAME レコードが必要なので、これが必要です。<br/>最初に、lyncdiscover サブドメインを作成します。

1. [ **サブドメイン] を選択します**。
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="[サブドメイン] を選択します。":::
  
1. [サブ **ドメインの追加] を選択します**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="[サブドメインの追加] を選択します。":::
    
1. 新しい **サブドメインの [サブドメインの** 追加] ボックスに、次の表の[サブドメインの追加] 値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します。<br/> 
    
    |**サブドメインの追加**|**Alias**|
    |:-----|:-----|
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
   
1. [ **作成** した **エンタープライズ登録サブ** ドメインのアクション] で、ギア コントロールを選択し、ドロップダウン リストから **[DNS]** を選択します。 <br/>
    
1. [レコード **の追加]** を選択し **、[CNAME] セクションを選択** します。

1. [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。 <br/>
    
    |**サブドメインの追加**|**Alias**|
    |:-----|:-----|
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    
1. 別のサブドメインを作成します。 <br/>[サブ **ドメインの追加] を選択します**。
    
1. 新しい **サブドメインの [サブドメインの** 追加] ボックスに、次の表の[サブドメインの追加] 値のみを入力またはコピーして貼り付けます。 (後の手順で **Alias** 値を追加します。 <br/>
    
    |**サブドメインの追加**|**Alias**|
    |:-----|:-----|
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

1. [ **作成** した **enterpriseenrollment** サブドメインのアクション] で、ギア コントロールを選択し、ドロップダウン リストから **[DNS]** を選択します。 <br/>
    
1. [レコード **の追加] を選択します**。

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="[レコードの追加] を選択します。":::

1. **[CNAME] セクションを** 選択します。

1. [エイリアス **:] ボックス** に、次の表の **Alias** 値のみを入力またはコピーして貼り付けます。 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
1. 免責事項の [ **I am aware**] チェック ボックスをオンにして、[ **Save**] を選択します。

  
