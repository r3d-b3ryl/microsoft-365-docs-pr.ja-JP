---
title: Google Domains で Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Google Domains でカスタム ドメインの DNS レコードを管理するために Microsoft をセットアップする方法について説明します。
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658442"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>Google Domains で Microsoft をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
Microsoft が DNS レコードを管理する場合は、次の手順に従います。 (必要に応じて [、Google Domains ですべての DNS レコードを管理できます](create-dns-records-at-google-domains.md))。
  
    
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
>  このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. [**サインイン**] を選びます。
    
2. ログイン資格情報を入力し、もう一度 [サインイン] **を選択します**。
    
2. [**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。 
    
3. [**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
|||||
|:-----|:-----|:-----|:-----|
|**名前** <br/> |**Type** <br/> |**TTL** <br/> |**データ** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. [**追加**] を選択します。
    
5. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
ドメイン レジストラーのサイトでレコードを追加したので、Microsoft に戻り、レコードの検索を要求します。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Microsoft でドメインのセットアップを完了するには、ドメイン レジストラーでドメインの NS レコードを変更して、Microsoft のプライマリ ネーム サーバーとセカンダリ ネーム サーバーをポイントします。 これにより、ドメインの DNS レコードを更新する Microsoft がセットアップされます。 メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> Microsoft ネーム サーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。 たとえば、ドメインに送信されたメール (たとえば *、rob@your_domain。*  com) は、この変更を行った後に Microsoft に公開されます。 
  
> [!IMPORTANT]
> 次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、正しいネームサーバーを追加する方法を説明します。 >このセクションの手順を完了すると、以下の 4 つのネームサーバーだけが表示されます。 
  
1. まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。
    
1. [**サインイン**] を選びます。
    
2. ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。
    
2. [**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。 
    
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
   
   ![Google-Domains-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. + **(追加) コントロールを選択** して空の行を作成します。 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. 他の 3 つのネームサーバー レコードを追加します。
    
    [カスタム ネーム **サーバーの** 使用] セクションで、表の次の行の値を使用してレコードを作成し、+ **(追加)** コントロールを選択して別の行を追加します。 
    
    4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
4. **[保存]** を選択します。
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
### <a name="if-there-are-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがある場合

1. 他のネームサーバーが一覧表示されている場合は、[編集] を選択 **します**。
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (つまり、名前が **ns1.bdm.microsoftonline.com**、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com、または ns4.bdm.microsoftonline.com **))**   
  
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
   
   ![Google-Domains-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. **+(add) コントロールを選択** して空の行を作成します。 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. 他の 2 つのネームサーバー レコードを追加します。
    
    [カスタムネーム サーバーの使用] セクションで、表の次の行の値を使用してレコードを作成し **、+(add)** コントロールを選択して別の行を追加します。 
    
    4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
6. **[保存]** を選択します。
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
