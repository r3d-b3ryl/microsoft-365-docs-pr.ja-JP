---
title: Azure DNS ゾーンの DNS レコードを作成する
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: ドメインを確認し、Microsoft の Azure DNS ゾーンでメール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: c276570ec1d5ff079348bd8202ea597ef61e88f6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656869"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>Azure DNS ゾーンの DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
使用している DNS ホスティング プロバイダーが Azure の場合は、この記事の手順に従ってドメインを確認し、メールや Skype for Business Online などのために DNS レコードを設定します。
  
追加する主なレコードは次のとおりです。 
  
- [ドメインのネーム サーバー (NS) レコードを変更する](#change-your-domains-nameserver-ns-records)
    
- [確認用に TXT レコードを追加する](#add-a-txt-record-for-verification)

- [MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Microsoft に必要な 4 つの CNAME レコードを追加する](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Microsoft で必要な 2 つの SRV レコードを追加する](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Azure でこれらのレコードを追加すると、ドメインは Microsoft サービスで動作するように設定されます。
  
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。 
  
Azure にサインアップすると、DNS ゾーン内にリソース グループが作成され、そのリソース グループにドメイン名が割り当てられます。 そのドメイン名は、外部ドメイン レジストラーに登録されます。Azure はドメイン登録サービスを提供していない。
  
Microsoft でドメインの DNS レコードを確認して作成するには、まず、リソース グループに割り当てられている Azure ネームサーバーを使用するように、ドメイン レジストラーのネームサーバーを変更する必要があります。
  
ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。 Azure に割り当てられたネームサーバーの例を以下に示します。
    


**最初のネームサーバー:** Azure によって割り当てられたネーム サーバー値を使用します。  
**2 番目のネームサーバー:** Azure によって割り当てられたネーム サーバー値を使用します。  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> You should use at least two name server records. ドメイン レジストラーの Web サイトに他のネーム サーバーが一覧表示されている場合は、それらを削除する必要があります。 
  
3. 変更内容を保存します。
    
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ). 最初にログインするように求められます。
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. [ダッシュボード **] ページの** 検索バー **を使用** して **、DNS** ゾーンを入力します。 結果表示で、[サービス] 部分の **下の DNS** ゾーン **を選択** します。 リダイレクトが完了したら、更新するドメインを選択します。
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. On the **Settings** page for your domain, in the **DNS zone** area, select + **Record set**.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. [レコード **セットの** 追加] 領域の新規レコード セットのボックスで、次の表の値を選択します。 
    
    (Choose the **Type** and **TTL unit values** from the drop-down lists.) 
    
    |**名前**|**Type**|**TTL**|**TTL ユニット**|**値**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1   <br/> |時間  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. **[OK]** をクリックします。
  
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
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ). 最初にログインするように求められます。
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. [ダッシュボード **] ページ** の [ **すべてのリソース]** 領域で、更新するドメインを選択します。 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. On the **Settings** page for your domain, in the **DNS zone** area, select + **Record set**.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. [レコード **セットの** 追加] 領域の新規レコード セットのボックスで、次の表の値を選択します。 
    
    (Choose the **Type** and **TTL unit values** from the drop-down lists.) 
    
    |**名前**|**Type**|**TTL**|**TTL ユニット**|**Preference**|**Mail Exchange**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1   <br/> |時間  <br/> |10   <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. **[OK]** をクリックします。
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. [MX Records] セクションに他の **MX** レコードが表示されている場合は、それらを削除する必要があります。 
    
    まず **、DNS ゾーン領域で、MX** レコード セット **を選択します**。
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    次に、削除する MX レコードを選択します。
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. コンテキスト メニュー **(...)** を選択し、[削除] を **選択します**。
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. **[保存]** を選択します。
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な 4 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ). 最初にログインするように求められます。
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. [ダッシュボード **] ページ** の [ **すべてのリソース]** 領域で、更新するドメインを選択します。 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. On the **Settings** page for your domain, in the **DNS zone** area, select + **Record set**.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 4 つのレコードの最初の CNAME レコードを追加します。
    
    [レコード **セットの** 追加] 領域の新規レコード セットのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。 
    
    (Choose the **Type** and **TTL unit values** from the drop-down lists.) 
    
    |**名前**|**Type**|**TTL**|**TTL ユニット**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1   <br/> |時間  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1   <br/> |時間  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1   <br/> |時間  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. **[OK]** をクリックします。
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. 他の 3 つの CNAME レコードをそれぞれ追加します。
    
    DNS ゾーン領域 **で、[+** レコード セット] **を選択します**。 次に、空のレコード セットで、テーブルの次の行の値を使用してレコードを作成し **、[OK]** を再度選択してレコードを完成します。 
    
    4 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
7.  (省略可能)MDM 用に 2 つの CNAME レコードを追加します。

> [!IMPORTANT]
> Microsoft のモバイル デバイス管理 (MDM) を使用している場合は、2 つの追加の CNAME レコードを作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (MDM を使用していない場合は、この手順を省略できます)。 
  
|**名前**|**Type**|**TTL**|**TTL ユニット**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1   <br/> |時間  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1   <br/> |時間  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。 
  
1. To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ). 最初にログインするように求められます。
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. [ダッシュボード **] ページ** の [ **すべてのリソース]** 領域で、更新するドメインを選択します。 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. DNS ゾーン **領域で** 、TXT レコード セット **を選択します**。
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. [レコード **セットのプロパティ** ] 領域の新規レコード セットのボックスで、次の表の値を選択します。 
    
    (Choose the **Type** and **TTL unit values** from the drop-down lists.) 
    
    |**名前**|**Type**|**TTL**|**TTL ユニット**|**値**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1   <br/> |時間  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. **[保存]** を選択します。
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ). 最初にログインするように求められます。
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. [ダッシュボード **] ページ** の [ **すべてのリソース]** 領域で、更新するドメインを選択します。 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. On the **Settings** page for your domain, in the **DNS zone** area, select + **Record set**.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 2 つの SRV レコードの最初のレコードを追加します。
    
    [レコード **セットの** 追加] 領域の新規レコード セットのボックスで、次の表の最初の行の値を選択します。 
    
    (Choose the **Type** and **TTL unit values** from the drop-down lists.) 
    
    |**名前**|**Type**|**TTL**|**TTL ユニット**|**Priority**|**Weight**|**Port**|**対象**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |1   <br/> |時間  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |1   <br/> |時間  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. **[OK]** をクリックします。
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. 残りの SRV レコードを追加します。
    
    新規レコードのボックスに、表の 2 行目の値を入力するか、コピーして貼り付けます。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
