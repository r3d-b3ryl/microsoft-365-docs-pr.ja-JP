---
title: Connectに GoDaddy で DNS レコードをMicrosoft 365
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: ドメインを確認し、GoDaddy for Microsoft で電子メール、Skype for Business、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 0db80de3ca34f34eaaaa8952f2b49c2c8da62046
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556903"
---
# <a name="connect-your-dns-records-at-godaddy-to-microsoft-365"></a>Connectに GoDaddy で DNS レコードをMicrosoft 365

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。

使用している DNS ホスティング プロバイダーが GoDaddy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。

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

GoDaddy でこれらのレコードを追加すると、ドメインはユーザーと一緒に動作Microsoft サービス。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。 ログインを求めるメッセージが表示される場合があります。

1. [ **ドメイン] で**、確認するドメインの横にある 3 つのドットを選択し、[DNS の管理] **を選択します**。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [レコード **] で**、[追加] を **選択します**。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. Choose **TXT (Text)** from the drop-down list. 

1. 新しいレコードのボックスに、テーブルの値を入力またはコピーして貼り付けます。

    |**Record type** |**Host**|**TXT Value**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (テキスト)|@|MS=ms *XXXXXXXX*<br>**注**: これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 hour  <br>(ドロップダウン リストから値を選択します)。|

1. **[保存]** を選択します。

1. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
レコードを確認するには、次Microsoft 365。
  
1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。
    
2. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。   
  
3. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。 ログインを求めるメッセージが表示される場合があります。

2. [ **ドメイン] で**、確認するドメインの横にある 3 つのドットを選択し、[DNS の管理] **を選択します**。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

3. [レコード **] で**、[追加] を **選択します**。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

4. ドロップダウン リストから [ **MX (Mail Exchanger)**] を選びます。

5. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

    (ドロップダウン リスト **から TTL** 値を選択します)。

    |**Record type**|**Host**|**Points to**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。 <br/> |1 hour  <br/> |

6. **[保存]** を選択します。

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。

2. [ **ドメイン] で**、確認するドメインの横にある 3 つのドットを選択し、[DNS の管理] **を選択します**。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

3. [レコード **] で**、[追加] を **選択します**。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

4. ドロップダウン リストから [ **CNAME (Alias)**] を選びます。

5. 1 番目の CNAME レコードを作成します。

    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

    (ドロップダウン リスト **から TTL** 値を選択します)。

    |**Record type**|**Host**|**Points to**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |

6. **[保存]** を選択します。

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。 ログインを求めるメッセージが表示される場合があります。

2. [ **ドメイン] で**、確認するドメインの横にある 3 つのドットを選択し、[DNS の管理] **を選択します**。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

3. [レコード **] で**、[追加] を **選択します**。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

4. Choose **TXT (Text)** from the drop-down list.

5. In the boxes for the new record, type or copy and paste the following values.

    (ドロップダウン リスト **から TTL** 値を選択します)。

    |**Record type**|**Host**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (テキスト)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |1 時間  <br/> |

6. **[保存]** を選択します。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスにネットワーク を使用している場合にのみ、このオプションをMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信用の SRV レコードが 2 件、ユーザーをサービスにサインインして接続するための CNAME レコードが 2 件必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。 ログインを求めるメッセージが表示される場合があります。

1. [ **ドメイン] で**、確認するドメインの横にある 3 つのドットを選択し、[DNS の管理] **を選択します**。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [レコード **] で**、[追加] を **選択します**。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. ドロップダウン リストから [ **SRV (Service)**] を選びます。

1. 1 番目の SRV レコードを作成します。

    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

    (ドロップダウン リスト **から [レコードの** 種類] と **[TTL** 値] を選択します)。

    |**Record type**|**Name**|**Target**|**Protocol**|**Service**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 Hour  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 Hour  <br/> |

1. **[保存]** を選択します。

1. テーブルの 2 行目から値を選択して、他の SRV レコードを追加します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する
  
1. [ **追加] を選択します**。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. ドロップダウン **リストから [CNAME]** を選択します。

1. 新規レコードの空のボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |**Type**|**Host**|**Value**|**TTL**|
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

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。 ログインを求めるメッセージが表示される場合があります。

1. [ **ドメイン] で**、確認するドメインの横にある 3 つのドットを選択し、[DNS の管理] **を選択します**。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [レコード **] で**、[追加] を **選択します**。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="[追加] を選択します。":::

1. ドロップダウン リストから [ **CNAME (Alias)**] を選びます。
  
1. 新規レコードの空のボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。
    
    |**Type**|**Host**|**Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1 Hour  <br/> |
  
1. **[保存]** を選択します。 
  
1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
