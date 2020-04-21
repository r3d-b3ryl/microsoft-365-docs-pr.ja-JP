---
title: Google ドメインで Microsoft をセットアップするためにネームサーバーを変更する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Google ドメインでカスタムドメインの DNS レコードを管理するように Microsoft をセットアップする方法について説明します。
ms.openlocfilehash: ac2f98a6ff783917d88a2bd8d28e8242e0ba41a8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629901"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>Google ドメインで Microsoft をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。 (必要に応じ[て、すべての DNS レコードを Google ドメインで管理](create-dns-records-at-google-domains.md)できます。)
  
    
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。 ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。
  
> [!NOTE]
>  このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. 開始するには、[このリンク](https://domains.google.com/registrar)を使用して Google domains のドメインページにアクセスしてください。 You'll be prompted to sign in. To do so:
    
1. [**サインイン**] を選択します。
    
2. ログイン資格情報を入力して、もう一度 [**サインイン**] を選択します。
    
2. [ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。 
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**名前** <br/> |**Type** <br/> |**TTL** <br/> |**Data** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **注:** これは例です。 この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. [**追加**] を選択します。
    
5. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft プライマリネームサーバーとセカンダリネームサーバーをポイントするようにします。 これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。 メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。 たとえば、ドメインに送信されるすべての電子メール (rob@ など*your_domain。*  この変更を行った後、com) は Microsoft に送られ始めます。 
  
> [!IMPORTANT]
> 次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、正しいネームサーバーを追加する方法を説明します。 > このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。 
  
1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
1. [**サインイン**] を選択します。
    
2. ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。
    
2. [ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。 
    
3. [ **ドメイン**] ページの [ **ネームサーバー**] セクションで、[ **カスタム ネームサーバーを使用**] を選びます。
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. 現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。
    
  - 既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。
    
  - 既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがない場合

1. 最初のネームサーバーを追加します。
    
    [ **ネームサーバー**] セクションにある [ **ネームサーバー**] ボックスに、次の表の最初の値を入力するか、コピーして貼り付けます。 
    
|||
|:-----|:-----|
|**1 番目のネーム サーバー** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2 番目のネーム サーバー** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**3 番目のネーム サーバー** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4 番目のネーム サーバー** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-ドメイン-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. 空の行を作成するには、[ **+ (追加)** ] コントロールを選択します。 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. 他の 3 つのネームサーバー レコードを追加します。
    
    [**カスタムの名前サーバーを使用**する] セクションで、表の次の行の値を使用してレコードを作成し、[ **+ (追加)** ] コントロールを選択して別の行を追加します。 
    
    4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
4. **[保存]** を選択します。
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  
### <a name="if-there-are-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがある場合

1. 他のネームサーバーが表示されている場合は、[**編集**] を選択します。
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. ネームサーバーを選んで、キーボードの **Delete** キーを押して、1 つずつ削除します。 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. [ **ネームサーバー**] セクションの [ **ネームサーバー**] 行に、次の表の値を入力するか、コピーして貼り付けます。 
    
|||
|:-----|:-----|
|**1 番目のネーム サーバー** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2 番目のネーム サーバー** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**3 番目のネーム サーバー** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4 番目のネーム サーバー** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-ドメイン-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. 空の行を作成するには、[ **+ (追加)** ] コントロールを選択します。 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. 他の 2 つのネームサーバー レコードを追加します。
    
    [**カスタムの名前サーバーを使用**する] セクションで、表の次の行の値を使用してレコードを作成し、[ **+ (追加)** ] コントロールを選択して別の行を追加します。 
    
    4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
6. **[保存]** を選択します。
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  
