---
title: 1&1 の間で MICROSOFT をセットアップするためにネームサーバーを変更する
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 1&1 インターネットが DNS ホスティング プロバイダーである場合に、21Vianet が運用している Office 365 をセットアップして DNS レコードを管理する方法について説明します。
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658034"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>1 対 1 の間で MICROSOFT 365 をセットアップするためにネーム&変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
Microsoft 365 で Microsoft 365 DNS レコードを管理する場合は、次の手順に従います。 (必要に応じて [、MICROSOFT 365 のすべての DNS レコードを 1&1 の間で管理できます](create-dns-records-at-1-1-internet.md)。 
  

    
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する


Microsoft 365 のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。
  
1. To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. [MY **DOMAINS] で、[Manage domains]** **(ドメインの管理) を選択します**。
    
3. [ **ドメイン センター] ページ** で、更新するドメインを探します。次に、その **ドメインの Panel** **(v)** コントロールを選択します。
    
4. [ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。
    
5. [TXT レコード **と SRV レコード] セクションで** 、[Add Record ] (レコードの追加) **を選択します**。
    
    (下へスクロールしなければならないことがあります。) 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **注**: これは例です。 Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. [保存 **] を** 選択し、[保存] **を再び** 選択します。 
    
8. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。
    
9. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。
  
Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常は DNS の変更が反映されるまで約 15 分かかります。 ただし、インターネットの DNS システム全体を更新するための変更を行った場合、それ以上の時間がかかる場合もあります。 IF you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Microsoft 365 でドメインのセットアップを完了するには、ドメイン レジストラーでドメインの NS レコードを変更して、Microsoft 365 プライマリ ネーム サーバーとセカンダリ ネーム サーバーをポイントします。 これにより、ドメインの DNS レコードを更新する Microsoft 365 がセットアップされます。 メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> Microsoft 365 ネーム サーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。 たとえば、ドメインに送信されたメール (rob@ *your_domain*  .com など) は、この変更を行った後に Microsoft 365 に届きます。 
  
Microsoft 365 でドメインをセットアップできるよう、NS レコードを変更する準備はできましたか? 次の手順を実行するか、[ビデオ (2 分 47 秒から開始) をご覧ください](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。
  
> [!IMPORTANT]
>  次の手順では、他の不要なネームサーバーを一覧から削除する方法と、正しいネームサーバーが一覧に表示されていない場合に追加する方法を示します。 >このセクションの手順を完了すると、次の 4 つのネームサーバーだけが表示されます。> ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. To get started, go to your domains page at 1&1 BY USING [THIS LINK](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. [MY **DOMAINS] で、[Manage domains]** **(ドメインの管理) を選択します**。
    
3. [ **ドメイン センター] ページ** で、更新するドメインを見つけ、そのドメインの **Panel** ( **v**) コントロールを選択します。
    
4. [ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。
    
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
   
   ![[ネーム サーバー 1] ボックスに値を入力する](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. [ **Additional name servers**] ドロップダウン リストで、[ **My secondary name servers**] を選びます。
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. **[Name server 2]、[Name server 3]、[Name server 4]** ボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
|||
|:-----|:-----|
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**ネーム サーバー 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**ネーム サーバー 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
![ネーム サーバーの値を入力する](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. **[保存]** を選択します。
    
    ![[ネーム サーバー設定] ページで [保存] を選択する](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。
    
    ![[DNS 設定の編集] ダイアログ ボックスで [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  
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
   
   ![ネーム サーバーの値を入力する](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. **[保存]** を選択します。
    
    ![[ネーム サーバー設定] ページで [保存] を選択する](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. [DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。
    
    ![[DNS 設定の編集] ダイアログ ボックスで [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
  


