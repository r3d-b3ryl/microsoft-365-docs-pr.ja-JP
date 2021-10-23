---
title: Connect DNS レコードを 123-reg.co.uk にMicrosoft 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: ドメインを確認し、Microsoft の電子メール、Skype for Business、その他のサービスの DNS レコード 123-reg.co.uk 説明します。
ms.openlocfilehash: 2c9e917a7c63759d69e58ffda4dc8a35c76d04ca
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556963"
---
# <a name="connect-your-dns-records-at-123-regcouk-to-microsoft-365"></a>Connect DNS レコードを 123-reg.co.uk にMicrosoft 365

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。 
  
使用している DNS ホスティング プロバイダーが 123-reg.co.uk の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
これらのレコードを 123-reg.co.uk すると、ドメインはユーザーと一緒に動作Microsoft サービス。 
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ドメイン名の概要] ページで、確認するドメインの名前を選択します。 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="確認するドメインを選択します。":::

3. [ドメインの管理] ページの [高度な **ドメイン設定] で、[DNS** の管理] **を選択します**。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::
  
4. [DNS の管理] ページで、[高度な **DNS] タブを選択** します。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::
  
5. 新しい **レコードの [種類** ] ボックスで、ドロップダウン リストから **[TXT/SPF]** を選択し、次の表の他の値を入力またはコピーして貼り付けます。 
    
    ||||
    |:-----|:-----|:-----|
    |**Hostname** <br/> |**Type** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
6. [**追加**] を選択します。
    
7. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻り、レコードの検索を要求します。 Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
レコードを確認するには、次Microsoft 365。
  
1. 管理センターで、[ドメイン] の **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。
    
2. [ドメイン] ページで、確認するドメインを選択し、[セットアップの開始] **を選択します**。   
  
3. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [高度な **ドメイン設定] で、[DNS** の管理] **を選択します**。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::
  
4. [DNS の管理] ページで、[高度な **DNS] タブを選択** します。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::
    
5. 新しい **レコードの [種類** ] ボックスで、ドロップダウン リストから **[MX]** を選択し、次の表の他の値を入力またはコピーして貼り付けます。 
    
    |**Hostname**|**Type**|**Priority**|**Destination MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> 優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。 <br/> | *\<domain-key\>*  .mail.protection.outlook.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> **注: Microsoft アカウントから** 取得\<domain-key\> します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
  
6. [**追加**] を選択します。
  
7. その他の MX レコードがある場合は、そのレコードの **削除 (ごみ箱)** アイコンを選んでそれぞれ削除します。 
  
## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [高度な **ドメイン設定] で、[DNS** の管理] **を選択します**。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::
  
4. [DNS の管理] ページで、[高度な **DNS] タブを選択** します。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::
    
5. CNAME レコードを追加します。
    
    新しい **レコードの [種類** ] ボックスで、ドロップダウン リストから **[CNAME]** を選択し、次の表の他の値を入力またはコピーして貼り付けます。 
    
    |**Hostname**|**Type**|**Destination CNAME**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
  
6. **[追加]** を選択します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 ドメインの SPF レコードが既にある場合は、Microsfot 用に新しい SPF レコードを作成しない。 代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。 次に例を示します。 こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)を参照してください。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [高度な **ドメイン設定] で、[DNS** の管理] **を選択します**。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::
  
4. [DNS の管理] ページで、[高度な **DNS] タブを選択** します。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::
    
5. 新しい **レコードの [種類** ] ボックスで、ドロップダウン リストから **[TXT/SPF]** を選択し、次の表の他の値を入力またはコピーして貼り付けます。
    
    |**Hostname**|**Type**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
  
6. **[追加]** を選択します。

## <a name="advanced-option-skype-for-business"></a>詳細オプション: Skype for Business

このオプションは、チャット、電話会議、ビデオ通話Skype for Business、電話会議など、オンライン通信サービスにネットワーク を使用している場合にのみ、このオプションをMicrosoft Teams。 Skype 4 つのレコードが必要です。ユーザー間通信用の SRV レコードが 2 件、ユーザーをサービスにサインインして接続するための CNAME レコードが 2 件必要です。

### <a name="add-the-two-required-srv-records"></a>必要な 2 つの SRV レコードを追加する

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [高度な **ドメイン設定] で、[DNS** の管理] **を選択します**。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::
  
4. [DNS の管理] ページで、[高度な **DNS] タブを選択** します。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::
    
5. 2 つの SRV レコードの最初のレコードを追加します。
    
   新しい **レコードの [種類** ] ボックスで、ドロップダウン リストから **[SRV]** を選択し、次の表の他の値を入力またはコピーして貼り付けます。
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |**Hostname**|**Type**|**Priority**|**TTL**|**Destination SRV**|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません**<br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **この値は、末尾がピリオド (.) でなければなりません** <br> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
  
6. **[追加]** を選択します。
  
7. 他の SRV レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する 
    
1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

1. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

1. [ドメインの管理] ページの [高度な **ドメイン設定] で、[DNS** の管理] **を選択します**。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::
  
1. [DNS の管理] ページで、[高度な **DNS] タブを選択** します。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::
    
1. 1 番目の CNAME レコードを追加します。
    
    新しい **レコードの [種類** ] ボックスで、ドロップダウン リストから **[CNAME]** を選択し、次の表の他の値を入力またはコピーして貼り付けます。
    
    | **Hostname** |**Type**|**Destination CNAME**|
    |:-----|:-----|:-----|
    |sip  <br/>|CNAME  <br/> |sipdir.online.lync.com  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |lyncdiscover  <br/>|CNAME  <br/> |webdir.online.lync.com.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
  
1. **[追加]** を選択します。
  
1. 他の CNAME レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高度なオプション: Intune とモバイル デバイスの管理 (Microsoft 365

このサービスは、ドメインに接続するモバイル デバイスのセキュリティ保護とリモート管理に役立ちます。 モバイル デバイス管理では、ユーザーがサービスにデバイスを登録できるよう、2 つの CNAME レコードが必要です。

### <a name="add-the-two-required-cname-records"></a>必要な 2 つの CNAME レコードを追加する

1. まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。

2. On the Domain name overview page, select the name of the domain that you want to edit. 
    
   :::image type="content" source="../../media/dns-123reg/123reg-domains-1.png" alt-text="編集するドメインの名前を選択します。":::

3. [ドメインの管理] ページの [高度な **ドメイン設定] で、[DNS** の管理] **を選択します**。
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-2.png" alt-text="ドロップダウン リストから [DNS の管理] を選択します。":::
  
4. [DNS の管理] ページで、[高度な **DNS] タブを選択** します。 
  
   :::image type="content" source="../../media/dns-123reg/123reg-domains-3.png" alt-text="[高度な DNS] タブを選択します。":::
    
1. 1 番目の CNAME レコードを追加します。
    
    新しい **レコードの [種類** ] ボックスで、ドロップダウン リストから **[CNAME]** を選択し、次の表の他の値を入力またはコピーして貼り付けます。
    
 | **Hostname**|**Type**|**Destination CNAME**|
    |:-----|:-----|:-----|
    | enterpriseregistration <br/> | CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
    |enterpriseenrollment  <br/> | CNAME  <br/> |enterpriseenrollment.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
  
1. **[追加]** を選択します。
  
1. 他の CNAME レコードを追加します。
    
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。
  
