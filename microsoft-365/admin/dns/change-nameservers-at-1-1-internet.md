---
title: Office 365 をセットアップするためにネームサーバーを変更する&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Dns レコードを管理するために21Vianet が運用している Office 365 をセットアップする方法について説明します。 1&1 インターネットが DNS ホスティングプロバイダーである場合です。
ms.openlocfilehash: 3678d5372b9edd8e9333ad78862694b450abe53a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352568"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a>Office 365 をセットアップするためにネームサーバーを変更する&1 IONOS

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
Office 365 で Office 365 DNS レコードを管理する場合は、以下の手順に従います。 (必要に応じ[て、1&1 の IONOS で Office 365 のすべての DNS レコードを管理](create-dns-records-at-1-1-internet.md)することができます。) 
  

    
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する


Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. まず、[このリンク](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)を使用して 1&1 IONOS でドメインページにアクセスします。 You'll be prompted to log in. 
    
2. [**マイドメイン**] で、[**ドメインの管理**] を選択します。
    
3. [**ドメインセンター** ] ページで、更新するドメインを見つけます。そのドメインの [Panel ( **v**) **]** コントロールを選択します。
    
4. [**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
5. [ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。
    
    (You may have to scroll down.) 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **注**: これは例です。 Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. [**保存**] を選択し、もう一度**保存**します。 
    
8. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
9. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
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
> ドメインの NS レコードを Office 365 のネーム サーバーをポイントするように変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。たとえば、この変更後、ドメイン (rob@ *your_domain*  .com など) に送信されるすべてのメールは、Office 365 に送信されるようになります。 
  
Office 365 でドメインをセットアップできるように、NS レコードを変更する準備ができましたか? 次の手順を実行するか、[ビデオ (2 分 47 秒から開始) をご覧ください](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
> [!IMPORTANT]
>  次の手順では、リストからその他の不要なネームサーバーを削除する方法と、正しいネームサーバーが表示されていない場合には追加する方法について説明します。 > このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. まず、[このリンク](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)を使用して 1&1 IONOS でドメインページにアクセスします。 You'll be prompted to log in. 
    
2. [**マイドメイン**] で、[**ドメインの管理**] を選択します。
    
3. [**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。
    
4. [**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。
    
5. [ **Name Server Settings**] セクションで、[ **Other name servers**] を選びます
    
    (下へスクロールしなければならないことがあります)。
    
6. 現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。
    
  - 既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。
    
  - 既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがない場合

1. [ **Name server 1**] ボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![[Name server 1] ボックスに値を入力する](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. [ **Additional name servers**] ドロップダウン リストで、[ **My secondary name servers**] を選びます。
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. **[Name server 2]、[Name server 3]、[Name server 4]** ボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
|||
|:-----|:-----|
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**ネーム サーバー 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**ネーム サーバー 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Entering name server values](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. [**保存**] を選択します。
    
    ![[名前サーバーの設定] ページの [保存] を選択する](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
    ![[DNS 設定の編集] ダイアログボックスの [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。 
  
### <a name="if-there-are-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがある場合

> [!CAUTION]
> これらの手順は、前途した 4 件の *正しい*  ネームサーバー以外にも既存のネームサーバーがある場合に  *のみ*  行ってください (つまり、現在のネームサーバーのうち *ns1.bdm.microsoftonline.com* 、 *ns2.bdm.microsoftonline.com* 、 **ns3.bdm.microsoftonline.com** 、 **ns4.bdm.microsoftonline.com** のいずれでも  **ない**  もの  **だけ**  を削除します)。 
  
1. [ **Name server**] にネームサーバーが既に表示されている場合は、各ネームサーバーを選び、キーボードの **Delete** キーを押して、ネームサーバーを削除します。 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. **[Name server 1]、[Name server 2]、[Name server 3]、[Name server 4]** ボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**ネーム サーバー 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**ネーム サーバー 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![名前サーバーの値を入力する](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. [**保存**] を選択します。
    
    ![[名前サーバーの設定] ページの [保存] を選択する](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
    ![[DNS 設定の編集] ダイアログボックスの [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。 
  


