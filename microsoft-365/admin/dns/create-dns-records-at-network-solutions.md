---
title: Connectソリューションで DNS レコードを作成して、Microsoft 365
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Microsoft のネットワーク ソリューションで、ドメインを確認し、電子メール、オンライン、Skype for Businessサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: f0599ef178e9a3dde097b94e7c3f980f59e88636
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586353"
---
# <a name="connect-your-dns-records-at-network-solutions-to-microsoft-365"></a>Connectソリューションで DNS レコードを作成して、Microsoft 365

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。 
  
使用している DNS ホスティング プロバイダーが Network Solutions の場合は、この記事に示す手順に従い、ドメインを確認して、メール、Skype for Business Online などの DNS レコードを設定します。
    
ネットワーク ソリューションでこれらのレコードを追加すると、ドメインはネットワーク ソリューションで動作Microsoft サービス。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。
  
1. ランディング ページで、[ドメイン名] **を選択します**。

1. 変更するドメインの横にあるチェック ボックスをオンにします。
  
1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストから [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::
  
1. 下にスクロールして [ **高度なツール]** を選択し、[高度な DNS レコード] の横にある [ **管理**] を **選択します**。

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。
  
1. [ **続行] を** 選択し、[高度な DNS レコードの管理] ページで **、[+ADD RECORD] を選択します**。

1. [ **種類]** で、ドロップダウン リストから **[TXT]** を選択します。
  
1. In the boxes for the new record, type or copy and paste the values in the following table.
    
    |**参照先**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。  [確認する方法](../get-help-with-domains/information-for-dns-records.md) |3600  <br/>    |
  
1. [ **追加] を選択します**。
  
    > [!NOTE]
    > 右上 **の [クラシック ビュー** ] を選択して、作成した TXT レコードを表示します。   
  
1. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

レコードを確認するには、次Microsoft 365。
  
1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。
    
1. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。
  
1. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
  
1. まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。
  
1. ランディング ページで、[ドメイン名] **を選択します**。

1. 変更するドメインの横にあるチェック ボックスをオンにします。
  
1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::
  
1. 下にスクロールして [ **高度なツール]** を選択し、[高度な DNS レコード] の横にある [ **管理**] を **選択します**。
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。
    
1. [高度な DNS レコードの管理] ページで **、[+ADD RECORD] を選択します**。

1. [ **種類]** で、ドロップダウン リストから **[MX]** を選択します。
  
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    **参照先** |**メール サーバー**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|
    | @ | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **この値は、ピリオド (.) で終わらせない場合があります。** <br/> **注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md) | 0  <br/> 優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。 <br/> | 1 Hour  <br/> |  
  
1. [ **追加] を選択します**。
  
    > [!NOTE]
    > 右上 **の [クラシック ビュー** ] を選択して、作成した TXT レコードを表示します。  

1. その他の MX レコードがある場合は、編集ツールを選択してすべてのレコードを削除し、レコードごとに **削除** します。 
  
## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。
  
1. ランディング ページで、[ドメイン名] **を選択します**。

1. 変更するドメインの横にあるチェック ボックスをオンにします。
  
1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。

    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::
  
1. [高度 **なツール] を** 選択し、[高度な DNS レコード] **の横にある**[管理] を **選択します**。
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

1. [高度な DNS レコードの管理] ページで **、[+ADD RECORD] を選択します**。

1. [ **種類]** で、ドロップダウン リストから **[CNAME]** を選択します。
  
1. CNAME レコードのボックスに、次の表の値を入力またはコピーして貼り付けます。
    
    |**参照 | ホスト名**|**Alias to (エイリアス)**| **TTL** |
    |:-----|:-----|:-----|:-----|
    |その他のホスト| autodiscover  <br/> | autodiscover.outlook.com **この値はピリオドで終了できません (.)** <br/> 1 Hour  <br/> |
  
1. [ **追加] を選択します**。

    > [!NOTE]
    > 右上 **の [クラシック ビュー** ] を選択して、作成したレコードを表示します。  
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。 
  
1. まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。
  
1. ランディング ページで、[ドメイン名] **を選択します**。

1. 変更するドメインの横にあるチェック ボックスをオンにします。
    
1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。
 
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::
 
1. [高度 **なツール] を** 選択し、[高度な DNS レコード] **の横にある**[管理] を **選択します**。
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

1. [高度な DNS レコードの管理] ページで **、[+ADD RECORD] を選択します**。

1. [ **種類]** で、ドロップダウン リストから **[TXT]** を選択します。

1. In the boxes for the new record, type or copy and paste the following values.
    
    |**参照先**|**TXT Value**| **TTL**
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。 | 1 Hour  <br/> |
       
1. [ **追加] を選択します**。
  
    > [!NOTE]
    > 右上 **の [クラシック ビュー** ] を選択して、作成したレコードを表示します。  
  
## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスにネットワーク を使用している場合にのみ、このオプションをMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信用の SRV レコードが 2 件、ユーザーをサービスにサインインして接続するための CNAME レコードが 2 件必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。
  
1. ランディング ページで、[ドメイン名] **を選択します**。

1. 変更するドメインの横にあるチェック ボックスをオンにします。
    
1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。
  
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::

1. [高度 **なツール] を** 選択し、[高度な DNS レコード] **の横にある**[管理] を **選択します**。
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

1. [高度な DNS レコードの管理] ページで **、[+ADD RECORD] を選択します**。

1. 2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    [ **Service**] と [ **Protocol**] の値をドロップダウン リストから選びます。 
    
    | **Type** |**Service**|**Protocol**|**Weight**|**Port**|**Target**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    | SRV |_sip  <br/> |_tls  <br/> |100  <br/> |443  <br/> |sipdir.online.lync.com  <br/> **この値はピリオド (.) で終了できません。** <br/> | 1  <br/> | 1 Hour  <br/> |
    | SRV |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **この値はピリオド (.) で終了できません。** <br/> |1  <br/> | 1 Hour  <br/> |
  
1. [ **追加] を選択します**。
 
    > [!NOTE]
    > 右上 **の [クラシック ビュー** ] を選択して、作成したレコードを表示します。  

1. テーブルの 2 行目から値を選択して、他の SRV レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する 
    
1. まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。
  
1. ランディング ページで、[ドメイン名] **を選択します**。

1. 変更するドメインの横にあるチェック ボックスをオンにします。
    
1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。
 
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::
 
1. [高度 **なツール] を** 選択し、[高度な DNS レコード] **の横にある**[管理] を **選択します**。
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

1. [高度な DNS レコードの管理] ページで、[+ **レコードの追加] を選択します**。
    
1. 1 番目の CNAME レコードを追加します。
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    | **型**|**参照 | ホスト名**|**Alias to (エイリアス)**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | その他のホスト | sip  <br/> |sipdir.online.lync.com  <br/> **この値はピリオド (.) で終了できません。** <br/> |1 Hour  <br/> |
    | CNAME| その他のホスト | lyncdiscover  <br/> |webdir.online.lync.com  <br/> **この値はピリオド (.) で終了できません。** <br/> | 1 Hour  <br/> |
   
1. [ **追加] を選択します**。
 
    > [!NOTE]
    > 右上 **の [クラシック ビュー** ] を選択して、作成したレコードを表示します。  
   
1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高度なオプション: Intune とモバイル デバイスの管理 (Microsoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理では、ユーザーがサービスにデバイスを登録できるよう、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。
  
1. ランディング ページで、[ドメイン名] **を選択します**。

1. 変更するドメインの横にあるチェック ボックスをオンにします。
    
1. [ **アクション]** で 3 つのドットを選択し、ドロップダウン リストで [ **管理** ] を選択します。
 
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-1.png" alt-text="ドロップダウン リストから [管理] を選択します。":::
 
1. [高度 **なツール] を** 選択し、[高度な DNS レコード] **の横にある**[管理] を **選択します**。
    
    :::image type="content" source="../../media/dns-networksolutions/networksolutions-domains-2.png" alt-text="[高度な DNS レコード] の横にある [管理] を選択します。":::

    [続行] を選択 **して [高度** な DNS レコードの管理] ページに移動する必要がある場合があります。

1. [高度な DNS レコードの管理] ページで **、[+ADD RECORD] を選択します**。
  
1. 1 番目の CNAME レコードを追加します。
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    | **型**|**参照 | ホスト名**|**Alias to (エイリアス)**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | その他のホスト | enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> **この値はピリオド (.) で終了できません。** <br/> | 1 Hour  <br/> |
    | CNAME | その他のホスト |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **この値はピリオド (.) で終了できません。** <br/> | 1 Hour  <br/> |
   
1. [ **追加] を選択します**。
  
    > [!NOTE]
    > 右上 **の [クラシック ビュー** ] を選択して、作成したレコードを表示します。  

1. テーブルの 2 行目から値を選択して、他の CNAME レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
  

  
