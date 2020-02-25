---
title: 任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: メールや Skype for Business Online などのサービスが独自のドメイン名を使用するように、Office 365 でドメインを追加してセットアップする方法について説明します。
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255156"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a>任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
最初に[ドメイン (ホスト固有の指示) を設定](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)し、レジストラーに関する指示があるかどうかを確認します。 
  
次の手順に従って、Office 365 にドメインを追加してセットアップします。これにより、電子メールや Skype for Business Online などのサービスが独自のドメイン名を使用するようになります。 これを行うには、ドメインを確認してから、ドメインのネームサーバーを Office 365 に変更して、適切な DNS レコードをセットアップできるようにします。 次のステートメントで状況を説明する場合は、次の手順を実行します。
  
- 独自のドメインがあり、Office 365 と連携するようにセットアップしたい。
    
- Office 365 で DNS レコードを管理したい ([独自の DNS レコードを管理することもできます](../setup/add-domain.md))。
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>確認のため TXT レコードまたは MX レコードを追加する
<a name="BKMK_verify"> </a>

> [!NOTE]
> これらのレコードのいずれか一方を作成します。推奨されるレコードの種類は TXT ですが、一部の DNS ホスティング プロバイダーではサポートしていないため、代わりに MX レコードを作成してもかまいません。 
  
Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>DNS ホスティング プロバイダーの Web サイトで、新しいレコードを作成できる場所を見つけます。

1. DNS ホスティング プロバイダーの Web サイトにサインインします。
    
2. ドメインを選びます。
    
3. ドメインの DNS レコードを編集できるページを見つけます。
    
### <a name="create-the-record"></a>レコードを作成する

TXT レコードと MX レコードのどちらを作成しているかに応じて、次のいずれかを実行します。
  
**TXT レコードを作成する場合は、以下の値を使います。**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Alias** または **Host Name** <br/> |**Value** <br/> |**TTL** <br/> |
|TXT  <br/> |次のいずれかを実行します。「 **@** 」と入力するか、フィールドを空白のままにするか、ドメイン名を入力します。    <br/> > [!NOTE]> このフィールドの要件は、DNS ホストによって異なります。           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> これは例です。Office 365 の表にある [ **宛先またはポイント先のアドレス**] の値を指定してください。          [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。      <br/> |
   
**MX レコードを作成する場合は、以下の値を使います。**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** または **Host Name**|**Value**|**優先度**|**TTL**|
|MX|**@** か自分のドメインの名前のいずれかを入力します。 |MS=ms *XXXXXXXX* > [!NOTE]> これは例です。Office 365 の表にある [ **宛先またはポイント先のアドレス**] の値を指定してください。          [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |**優先度**として、メールフローに使用される mx レコードとの競合を回避するには、既存の mx レコードの優先度よりも低い優先度を使用します。 優先度の詳細については、「[MX 優先度とは](../setup/domains-faq.md#what-is-mx-priority)」を参照してください。 |この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 |
   
### <a name="save-the-record"></a>レコードを保存する

Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  

1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。
    
2. [**ドメイン**] ページで、確認するドメインを選択します。 
    
  
3. [**セットアップ**] ページで、[**セットアップの開始**] を選択します。
 
    
  
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する
<a name="BKMK_nameservers"> </a>

Office 365 のドメインのセットアップウィザードの最後の手順に戻ると、1つのタスクが残っています。 Office 365 サービスを使用してドメインをセットアップするには、メールのように、ドメインレジストラーでドメインのネームサーバー (NS) レコードを変更して、Office 365 プライマリネームサーバーとセカンダリネームサーバーを指すようにします。 その後、Office 365 が DNS をホストするため、サービスに必要な DNS レコードが自動的に設定されます。 ネーム サーバー レコード自体は、ドメイン レジストラーが Web サイトのヘルプで説明している手順に従って更新できます。 DNS が不明である場合は、ドメイン レジストラーのサポートに問い合わせてください。

::: moniker range="o365-worldwide"
  
ドメインレジストラーの web サイトで、自分でドメインのネームサーバーを変更するには、次の手順を実行します。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 2つのネームサーバーレコードを作成するか、または次の値に一致するように既存のネームサーバーレコードを編集します。
    
|||
|:-----|:-----|
|1 番目のネーム サーバー  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|2 番目のネーム サーバー  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > 少なくとも2つのネームサーバーレコードを使用する必要があります。 他のネームサーバーが表示されている場合は、それらを削除するか、 **ns3.bdm.microsoftonline.com**および**ns4.bdm.microsoftonline.com**に変更することができます。 
  
3. 変更内容を保存します。
    
> [!CAUTION]
> Office 365 ネームサーバーを参照するようにドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。 メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。 そうしないと、この変更により、メールのアクセスが不足している、現在の web サイトにアクセスできないなど、サービスのダウンタイムが発生する可能性があります。 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 2つのネームサーバーレコードを作成するか、または次の値に一致するように既存のネームサーバーレコードを編集します。
    
|||
|:-----|:-----|
|1 番目のネーム サーバー  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|2 番目のネーム サーバー  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > 少なくとも2つのネームサーバーレコードを使用する必要があります。 他のネームサーバーが表示されている場合は、それらを削除するか、 **ns3.dns.partner.microsoftonline.cn**および**ns4.dns.partner.microsoftonline.cn**に変更することができます。 
  
3. 変更内容を保存します。
    
> [!CAUTION]
> 21Vianet のネームサーバーが運用している Office 365 をポイントするようにドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。 メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。 そうしないと、この変更により、メールのアクセスが不足している、現在の web サイトにアクセスできないなど、サービスのダウンタイムが発生する可能性があります。 

::: moniker-end
  
たとえば、電子メールと Web サイトのホスティングには、次のような追加の手順が必要になる場合があります。
  
- NS レコードを変更する前に、ドメインを使うすべてのメール アドレスを Office 365 に移動します。
    
- www.fourthcoffee.com などの Web サイト アドレスで現在使用されているドメインを追加する場合は、ドメインの追加中に、サイトが現在ホストされている場所でこの Web サイトをホストし続けるための手順を実行できます。 ドメインを追加して、サイトがホストされている場所に web サイトをホストしている場合は、次の手順を実行して、Office 365 をポイントするようにドメインの NS レコードを変更した後も、ユーザーが web サイトにアクセスできるようにすることができます。

1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

3. [ ドメイン] ページで、ドメインを選びます。

4. [ **DNS 設定**] で [**カスタムレコード**] を選択し、[**新しいカスタムレコード**] を選択します。

5. 追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。

6. [**保存**] を選択します。
    
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。 
  

