---
title: 任意のドメイン レジストラーで Microsoft 365 をセットアップするためにネームサーバーを変更する
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: メールや Skype for Business Online のようなサービスで独自のドメイン名を使用するために、Microsoft 365 でドメインを追加して設定する方法について説明します。
ms.openlocfilehash: a4218b03e3f23ba8bc39c5eb84b42f87a71b9a65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658601"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>任意のドメイン レジストラーで Microsoft 365 をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
最初 [にドメインのセットアップ (ホスト固有](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) の手順) を確認し、レジストラーの手順がインストールされていないか確認します。 
  
Microsoft 365 でドメインを追加および設定するには、次の手順に従って、メールや Teams のようなサービスで独自のドメイン名を使用します。 これを行うには、ドメインを確認し、ドメインのネームサーバーを Microsoft 365 に変更して、正しい DNS レコードを設定します。 次のステートメントで状況が説明されている場合は、次の手順に従います。
  
- 独自のドメインを所有し、Microsoft 365 で動作するドメインを設定する場合。
    
- Microsoft 365 で DNS レコードを管理する場合。 (必要に応じて、独自 [の DNS レコードを管理できます](../setup/add-domain.md))。
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>確認のため TXT レコードまたは MX レコードを追加する
<a name="BKMK_verify"> </a>

> [!NOTE]
> これらのレコードのいずれか一方を作成します。推奨されるレコードの種類は TXT ですが、一部の DNS ホスティング プロバイダーではサポートしていないため、代わりに MX レコードを作成してもかまいません。 
  
Microsoft 365 のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>DNS ホスティング プロバイダーの Web サイトで、新しいレコードを作成できる領域を見つける

1. DNS ホスティング プロバイダーの Web サイトにサインインします。
    
2. ドメインを選びます。
    
3. ドメインに関する DNS レコードを編集可能なページを探します。
    
### <a name="create-the-record"></a>レコードを作成する

TXT レコードと MX レコードのどちらを作成しているかに応じて、次のいずれかを実行します。
  
**TXT レコードを作成する場合は、以下の値を使います。**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Alias** または **Host Name** <br/> |**Value** <br/> |**TTL** <br/> |
|TXT  <br/> |次のいずれかを実行します。「 **@** 」と入力するか、フィールドを空白のままにするか、ドメイン名を入力します。    <br/> > [!NOTE]> このフィールドの要件は、DNS ホストによって異なります。           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> これは例です。 Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。  <br/> |
   
**MX レコードを作成する場合は、以下の値を使います。**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** または **Host Name**|**Value**|**Priority**|**TTL**|
|MX|**@** か自分のドメインの名前のいずれかを入力します。 |MS=ms *XXXXXXXX* > [!NOTE]> これは例です。 Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |**Priority** には、メール フローに使われる MX レコードとの競合を避けるために、既存の MX レコードよりも低い優先度を指定します。 優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。 |この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。 |
   
### <a name="save-the-record"></a>レコードを保存する

これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。
  
Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
 
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する
<a name="BKMK_nameservers"> </a>

Microsoft 365 のドメインセットアップ ウィザードの最後の手順に進むには、残りのタスクが 1 つ残っています。 メールなど、Microsoft 365 サービスでドメインをセットアップするには、ドメイン レジストラーでドメインのネームサーバー (または NS) レコードを変更して、Microsoft 365 プライマリネームサーバーとセカンダリ ネームサーバーをポイントします。 その後、Microsoft 365 は DNS をホストします。このため、サービスに必要な DNS レコードが自動的に設定されます。 ネーム サーバー レコード自体は、ドメイン レジストラーが Web サイトのヘルプで説明している手順に従って更新できます。 DNS が不明である場合は、ドメイン レジストラーのサポートに問い合わせてください。

::: moniker range="o365-worldwide"
  
ドメイン レジストラーの Web サイトでドメインのネームサーバーを自分で変更するには、次の手順を実行します。
  
1. ドメイン レジストラーの Web サイトで、ドメインのネームサーバーを変更できる領域、またはカスタム ネームサーバーを使用できる領域を探します。
    
2. ネームサーバー レコードを作成するか、次の値に一致する既存のネームサーバー レコードを編集します。
    
|||
|:-----|:-----|
|1 番目のネーム サーバー  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|2 番目のネーム サーバー  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|3 番目のネームサーバー  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|4 番目のネームサーバー  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > 4 つのレコードすべてが追加されるのが最善ですが、レジストラーでサポートされているレコードが 2 つのみである場合は、ns1.bdm.microsoftonline.com **を追加****ns2.bdm.microsoftonline.com。** 
  
3. 変更内容を保存します。
    
> [!CAUTION]
> Microsoft 365 ネームサーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。 メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。 そうしないと、この変更によってサービスのダウンタイムが発生する可能性があります。電子メール へのアクセスが不足したり、現在の Web サイトにアクセスできないなどです。 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。
    
2. 2 つのネームサーバー レコードを作成するか、次の値に一致する既存のネームサーバー レコードを編集します。
    
|||
|:-----|:-----|
|1 番目のネーム サーバー  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|2 番目のネーム サーバー  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > 少なくとも 2 つのネームサーバー レコードを使用する必要があります。 その他のネームサーバーが一覧表示されている場合は、それらを削除するか、または名前を変更して **ns3.dns.partner.microsoftonline.cn変更****ns4.dns.partner.microsoftonline.cn。** 
  
3. 変更内容を保存します。
    
> [!CAUTION]
> 21Vianet が運用している Office 365 ネームサーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。 メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。 そうしないと、この変更によってサービスのダウンタイムが発生する可能性があります。メール へのアクセスが不足したり、現在の Web サイトにアクセスできないなどです。 

::: moniker-end
  
たとえば、電子メールと Web サイトのホスティングには、次のような追加の手順が必要になる場合があります。
  
- NS レコードを変更する前に、ドメインを使用しているすべてのメール アドレスを Microsoft 365 に移動します。
    
- www.fourthcoffee.com などの Web サイト アドレスで現在使用されているドメインを追加する場合は、ドメインの追加中に、サイトが現在ホストされている場所でこの Web サイトをホストし続けるための手順を実行できます。 Microsoft 365 を指すドメインの NS レコードを変更した後も、ユーザーが引き続き Web サイトにアクセスできるよう、ドメインを追加して、サイトがホストされている場所で Web サイトをホストし続ける間、以下の手順を実行できます。

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

2. On the **Domains** page, select the domain and then choose **DNS Records**.

3. [DNS **設定] で**、[カスタム レコード **] を** 選択し、[新しいカスタム レコード] **を選択します**。

4. 追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。

5. **[保存]** を選択します。
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
