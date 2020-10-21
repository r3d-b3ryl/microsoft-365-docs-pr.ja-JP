---
title: Microsoft の GoDaddy で DNS レコードを作成する
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: ドメインを確認し、電子メール、Skype for Business Online、および GoDaddy のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 995e579e21a185084d9ee64a7ee462930d845844
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646129"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a>Microsoft の GoDaddy で DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。

使用している DNS ホスティング プロバイダーが GoDaddy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。

これらのレコードを GoDaddy で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。

> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。

以下の手順に従います。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. [ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **[追加]** を選択します。

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. ドロップダウン リストから [ **TXT (Text)**] を選びます。 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

    |**Record type** |**Host**|**TXT Value**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (テキスト)|@|MS=ms *XXXXXXXX*<br>**注**: これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)|1 hour  <br>(ドロップダウンリストから値を選択します。)|

      ![GoDaddy-検証-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. **[保存]** を選択します。

6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。

Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。



4. **[ドメインの確認]** ページで、**[確認]** を選択します。



> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="BKMK_add_MX"> </a>

以下の手順に従います。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. [ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **[追加]** を選択します。

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. ドロップダウン リストから [ **MX (Mail Exchanger)**] を選びます。

    ![GoDaddy-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。

    (ドロップダウンリストから [ **TTL** ] の値を選びます。)

    |**Record type**|**Host**|**Points to**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:***\<domain-key\>* Microsoft アカウントからを取得します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> 優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> |1 hour  <br/> |

6. **[保存]** を選択します。

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

以下の手順に従います。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. [ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **[追加]** を選択します。

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. ドロップダウン リストから [ **CNAME (Alias)**] を選びます。

    ![GoDaddy-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. 1 番目の CNAME レコードを作成します。

    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

    (ドロップダウンリストから [ **TTL** ] の値を選びます。)

    |**Record type**|**Host**|**Points to**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 時間  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 時間  <br/> |



6. これらの手順を繰り返して、すべての CNAME レコードを作成するまで、次の CNAME レコードを追加します。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。

以下の手順に従います。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. [ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **[追加]** を選択します。

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. ドロップダウン リストから [ **TXT (Text)**] を選びます。

    ![GoDaddy-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. 新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。

    (ドロップダウンリストから [ **TTL** ] の値を選びます。)

    |**Record type**|**Host**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (テキスト)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |1 時間  <br/> |

    ![GoDaddy-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. **[保存]** を選択します。


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

以下の手順に従います。

1. まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. [ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **[追加]** を選択します。

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. ドロップダウン リストから [ **SRV (Service)**] を選びます。

    ![GoDaddy-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. 1 番目の SRV レコードを作成します。

    新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。

    (ドロップダウンリストから [ **Record type** ] と [ **TTL** ] の値を選びます。)

    |**Record type**|**Name**|**Target**|**Protocol**|**Service**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1-d  <br/> |443  <br/> |1 hour  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |1 時間  <br/> |

    ![GoDaddy-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. **手順 5**を繰り返して、他の SRV レコードを作成します。

7. **[保存]** を選択します。

> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
