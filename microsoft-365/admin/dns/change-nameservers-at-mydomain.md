---
title: MyDomain で Office 365 をセットアップするためにネームサーバーを変更する
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: ユーザーが MyDomain でカスタムドメインの DNS レコードを管理するように Office 365 をセットアップする方法について説明します。
ms.openlocfilehash: 90f1469bdf2f281be14e2a9e15a9fe7ac4a8cbee
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351618"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a>MyDomain で Office 365 をセットアップするためにネームサーバーを変更する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。
  
Office 365 に Office 365 DNS レコードを管理させる場合は、次の手順に従います ([MyDomain で Office 365 のすべての DNS レコードを管理することもできます](create-dns-records-at-mydomain.md))。
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。
    
2. [**お気に入り**] セクションで、[**Domain Central**] を選択します。
    
3. [**ドメイン**] で、編集するドメインの名前を選択します。
    
4. [**概要**] 行で、[**DNS**] を選択します。
    
5. [**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。
    
6. [**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
||
|:-----|
|**Content** <br/> |
|MS=ms *XXXXXXXX*  <br/> **注**: これは例です。 Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
7. [**追加**] を選択します。
    
8. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。
  
Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Office 365 でドメインをセットアップするには、Office 365 のプライマリ ネーム サーバーとセカンダリ ネーム サーバーを参照するように、ドメインの NS レコードをドメイン レジストラーで変更します。これで、ドメインの DNS レコードを更新するように Office 365 で設定されます。メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> ドメインの NS レコードを Office 365 のネーム サーバーをポイントするように変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。 たとえば、ドメインに送信されるすべての電子メール (rob@ など*your_domain。* この変更を行った後、com) は Office 365 に送られ始めます。 
  
> [!IMPORTANT]
> 次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、正しいネームサーバーを追加する方法を説明します。<br/> When you have completed the steps in this section, the only nameservers that should be listed are these four:
  
1. まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。
    
2. [**お気に入り**] セクションで、[**Domain Central**] を選択します。
    
3. [**ドメイン**] で、編集するドメインの名前を選択します。
    
4. **概要**行で、[**ネーム**サーバー] を選択します。
    
    ![MyDomain-BP-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. [ **Update Name Servers**] セクションで [ **Use different name servers**] を選びます。
    
    ![MyDomain-BP-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. 現在表示されているページに既にネームサーバーが表示されているかどうかに応じて、次の2つの手順のいずれかに進みます。
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>正しいネームサーバーが表示されている場合

- 正しいネームサーバーが表示されている場合は、この手順をスキップできます。
    
    ![MyDomain-BP-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>正しいネームサーバーが表示されていない場合

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。 
  
1. [ **Nameserver**] フィールドの各エントリを選び、キーボードの **Delete** キーを押して既存のネームサーバーを削除します。 
    
    ![MyDomain-BP-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. [**追加**] を2回選択して、2つの新しいネームサーバー行を追加します。 
    
    ![MyDomain-BP-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. レコードのボックスに、次の表の nameserver の値を入力するか、コピーして貼り付けます。
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![MyDomain-BP-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. [**保存**] を選択します。
    
    ![MyDomain-BP-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。 
