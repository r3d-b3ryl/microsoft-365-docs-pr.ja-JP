---
title: Connect Web Services (AWS) で DNS レコードを削除して、Microsoft 365
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Microsoft の Amazon Web Services (AWS) で、ドメインを確認し、電子メール、Skype for Businessオンライン、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 1e148b13a89def2eb034ca0bcaa4287c890fe904
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586447"
---
# <a name="connect-your-dns-records-at-amazon-web-services-aws-to-microsoft-365"></a>Connect Web Services (AWS) で DNS レコードを削除して、Microsoft 365

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
AWS が DNS ホスティング プロバイダーの場合は、この記事の手順に従ってドメインを確認し、電子メールの DNS レコード、Skype Online for Business などについて設定します。
  
これらのレコードを AWS で追加すると、ドメインはユーザーと一緒に動作Microsoft サービス。
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
1. ランディング ページの [ドメイン] で **、[登録済み** ドメイン] **を選択します**。
    
1. [**ドメイン名]** で、設定するドメインを [ドメイン名] でMicrosoft 365。

    **注**: ドメインのホストゾーンを作成していない場合は、[ホストゾーンの作成] を選択して手順を完了してから、次の手順に進みます。 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="確認するドメインの名前を選択します。":::

1. [DNS **の管理] を選択します**。 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **ドメイン名]** で、確認するドメインのホストゾーン バージョンのドメイン名を選択します。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="確認するドメインの名前を選択します。":::

1. [レコード **の作成] を選択します**。
    
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |**レコード名** <br/> |**Record type** <br/> |**値** <br/> |**TTL (Seconds)** <br/> |**ルーティング ポリシー** <br/> |
    |(Leave this field empty.)  <br/> |TXT - 電子メール送信者の確認に使用されます  <br/> |MS=ms *XXXXXXXX*  <br/>**注:** これは例です。 Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md) |300  <br/> |シンプル  <br/> |
   
1. [レコード **の作成] を選択します**。
    
1. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻り、レコードの検索を要求します。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。

レコードを確認するには、次Microsoft 365。
  
1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。
    
1. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="[セットアップの開始] を選択します。":::

1. **[続行]** を選択します。
  
1. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>MX レコードを追加して、ドメインのメールがドメインに送信Microsoft 365

1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
1. ランディング ページの [ドメイン] で **、[登録済み** ドメイン] **を選択します**。
    
1. [**ドメイン名]** で、設定するドメインを [ドメイン名] でMicrosoft 365。

    **注**: ドメインのホストゾーンを作成していない場合は、[ホストゾーンの作成] を選択して手順を完了してから、次の手順に進みます。 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="ドメインの名前を選択します。":::

1. [DNS **の管理] を選択します**。 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **ドメイン名]** で、確認するドメインのホストゾーン バージョンのドメイン名を選択します。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="ドメインの名前を選択します。":::

1. [レコード **の作成] を選択します**。
    
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リスト **から [種類** ] **および [ルーティング** ] ポリシーの値を選択します)。 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
    
    |**レコード名**|**Record type**|**値**|**TTL (Seconds)**|**ルーティング ポリシー**|
    |:-----|:-----|:-----|:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |MX - Mail Exchange  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> 0 は、MX 優先度の値です。 この値を MX 値の先頭に追加して、スペースで他の値から分離します。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **注:** 自分の \<*domain-key*\> アカウントからMicrosoft 365します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md) | 300  <br/> | 簡単なルーティング <br/> |
  
1. [レコード **の作成] を選択します**。
  
1. その他の MX レコードがある場合は、レコードを選択し、[削除] を選択して削除 **します**。
  
## <a name="add-the-cname-record-required-for-microsoft-365"></a>ユーザーに必要な CNAME レコードをMicrosoft 365

1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
1. ランディング ページの [ドメイン] で **、[登録済み** ドメイン] **を選択します**。
    
1. [**ドメイン名]** で、設定するドメインを [ドメイン名] でMicrosoft 365。

    **注**: ドメインのホストゾーンを作成していない場合は、[ホストゾーンの作成] を選択して手順を完了してから、次の手順に進みます。 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="ドメインの名前を選択します。":::

1. [DNS **の管理] を選択します**。 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **ドメイン名]** で、確認するドメインのホストゾーン バージョンのドメイン名を選択します。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="ドメインの名前を選択します。":::

1. [レコード **の作成] を選択します**。
    
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リスト **から [種類** ] **および [ルーティング** ] ポリシーの値を選択します)。 
    
    |**レコード名**|**Record type**|**Value**| **TTL** |**ルーティング ポリシー**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - トラフィックを別のドメイン名にルーティングする  <br/> | autodiscover.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> | 300  <br/> |シンプル  <br/> |
  
6. [レコード **の作成] を選択します**。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)を参照してください。 SPF レコードを検証するには、次のいずれかの[SPF 検証ツールを使用できます](../setup/domains-faq.yml)。 
  
1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
1. ランディング ページの [ドメイン] で **、[登録済み** ドメイン] **を選択します**。
    
1. [**ドメイン名]** で、設定するドメインを [ドメイン名] でMicrosoft 365。

    **注**: ドメインのホストゾーンを作成していない場合は、[ホストゾーンの作成] を選択して手順を完了してから、次の手順に進みます。 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="ドメインの名前を選択します。":::

1. [DNS **の管理] を選択します**。 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **ドメイン名]** で、確認するドメインのホストゾーン バージョンのドメイン名を選択します。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="ドメインの名前を選択します。":::

1. [レコード **の作成] を選択します**。
    
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リスト **から [Type]** の値を選択します)。 
    
    |**Record type** | **値**|
    |:-----|:-----|
    |TXT- 電子メール送信者の確認とアプリケーション固有の値の使用 |v=spf1 include:spf.protection.outlook.com -all  <br/> (画面の手順で必要になる引用符は自動的に補完されます。手動で入力する必要はありません。)  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。   |
  
6. [レコード **の作成] を選択します**。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスにネットワーク を使用している場合にのみ、このオプションをMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信用の SRV レコードが 2 件、ユーザーをサービスにサインインして接続するための CNAME レコードが 2 件必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
1. ランディング ページの [ドメイン] で **、[登録済み** ドメイン] **を選択します**。
    
1. [**ドメイン名]** で、設定するドメインを [ドメイン名] でMicrosoft 365。

    **注**: ドメインのホストゾーンを作成していない場合は、[ホストゾーンの作成] を選択して手順を完了してから、次の手順に進みます。 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="ドメインの名前を選択します。":::

1. [DNS **の管理] を選択します**。 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **ドメイン名]** で、確認するドメインのホストゾーン バージョンのドメイン名を選択します。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="ドメインの名前を選択します。":::

1. [レコード **の作成] を選択します**。
    
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**レコード名**|**Record type**|**値**|**TTL (Seconds)**|**ルーティング ポリシー**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV - サービス ロケータ|100 1 443 sipdir.online.lync.com. **この値は、ピリオド (.) で終了する必要があります。**><br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。 | 300 |Simple|
    |_sipfederationtls._tcp|SRV - サービス ロケータ|100 1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**<br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。    | 300 |シンプル|
  
7. 他の SRV レコードを追加するには、[別のレコードの追加] を選択し、テーブルの次の行の値を使用してレコードを作成し、もう一度 [レコードの作成] を **選択します**。 
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する 
    
1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
1. ランディング ページの [ドメイン] で **、[登録済み** ドメイン] **を選択します**。
    
1. [**ドメイン名]** で、設定するドメインを [ドメイン名] でMicrosoft 365。

    **注**: ドメインのホストゾーンを作成していない場合は、[ホストゾーンの作成] を選択して手順を完了してから、次の手順に進みます。 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="ドメインの名前を選択します。":::

1. [DNS **の管理] を選択します**。 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **ドメイン名]** で、確認するドメインのホストゾーン バージョンのドメイン名を選択します。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="ドメインの名前を選択します。":::

1. [レコード **の作成] を選択します**。 
    
1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リスト **から [種類** ] **および [ルーティング** ] ポリシーの値を選択します)。 

    |**レコード名**|**Record type**|**Value**| **TTL** |**ルーティング ポリシー**|
    |:-----|:-----|:-----|:-----|:-----|
    |sip  <br/> |CNAME - 正規名  <br/> |sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |300  <br/> |Simple  <br/> |
    |lyncdiscover  <br/> |CNAME - 正規名  <br/> |webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/>  |300  <br/> ||シンプル  <br/> |
  
1. 他の CNAME レコードを追加するには、[別のレコードの追加] を **選択** し、テーブルの次の行の値を使用してレコードを作成します。 

1. [レコード **の作成] を選択します**。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高度なオプション: Intune とモバイル デバイスの管理 (Microsoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理では、ユーザーがサービスにデバイスを登録できるよう、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
1. ランディング ページの [ドメイン] で **、[登録済み** ドメイン] **を選択します**。
    
1. [**ドメイン名]** で、設定するドメインを [ドメイン名] でMicrosoft 365。

    **注**: ドメインのホストゾーンを作成していない場合は、[ホストゾーンの作成] を選択して手順を完了してから、次の手順に進みます。 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="ドメインの名前を選択します。":::

1. [DNS **の管理] を選択します**。 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::

1. [ **ドメイン名]** で、確認するドメインのホストゾーン バージョンのドメイン名を選択します。

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="ドメインの名前を選択します。":::

1. [レコード **の作成] を選択します**。

1. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (ドロップダウン リスト **から [種類** ] **および [ルーティング** ] ポリシーの値を選択します)。 
    
    |**レコード名**|**Record type**|**Value**| **TTL** |**ルーティング ポリシー**|
    |:-----|:-----|:-----|:-----|:-----|
    |enterpriseregistration  <br/> |CNAME - 正規名  <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |300  <br/> |Simple  <br/> |
    |EnterpriseEnrollment  <br/> |CNAME - 正規名  <br/> | enterpriseenrollment-s.manage.microsoft.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/>|300  <br/> | |シンプル  <br/> |
  
1. 他の CNAME レコードを追加するには、[別のレコードの追加] を **選択** し、テーブルの次の行の値を使用してレコードを作成します。 

1. [レコード **の作成] を選択します**。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。