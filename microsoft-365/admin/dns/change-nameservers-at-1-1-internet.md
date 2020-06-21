---
title: 1&1 の IONOS を設定するためにネームサーバーを変更する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Dns レコードを管理するために21Vianet が運用している Office 365 をセットアップする方法について説明します。 1&1 インターネットが DNS ホスティングプロバイダーである場合です。
ms.openlocfilehash: 79870d534e7d825fd59dbbbec54c796227f5faf1
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780375"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>IONOS 1 を&使用するように Microsoft 365 をセットアップするためにネームサーバーを変更

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
Microsoft 365 で Microsoft 365 の DNS レコードを管理するには、次の手順に従います。 (必要に応じ[て、すべての Microsoft 365 DNS レコードを 1&1 IONOS に管理](create-dns-records-at-1-1-internet.md)することができます。) 
  

    
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する


Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。
  
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
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **注**: これは例です。 Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. [**保存**] を選択し、もう一度**保存**します。 
    
8. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
9. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。
  
Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. DNS レコードの追加後にメールフローなどに問題が発生した場合は、「 [Microsoft 365 でドメインまたは DNS レコードを追加した後に問題を見つけて修正](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Microsoft 365 でのドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft 365 プライマリおよびセカンダリネームサーバーをポイントするようにします。 これにより、Microsoft 365 がドメインの DNS レコードを更新するように設定されます。 メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> ドメインの NS レコードを変更して、Microsoft 365 のネームサーバーを参照すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。 たとえば、この変更を行った後、ドメインに送信されるすべての電子メール (rob@ *your_domain*など) は、Microsoft 365 に送られ始めます。 
  
Microsoft 365 がドメインをセットアップできるように、NS レコードを変更する準備ができましたか? 次の手順を実行するか、[ビデオ (2 分 47 秒から開始) をご覧ください](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。
  
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
   
![名前サーバーの値を入力する](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. **[保存]** を選択します。
    
    ![[名前サーバーの設定] ページの [保存] を選択する](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
    ![[DNS 設定の編集] ダイアログボックスの [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  
### <a name="if-there-are-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがある場合

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
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
  
3. **[保存]** を選択します。
    
    ![[名前サーバーの設定] ページの [保存] を選択する](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. [ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。
    
    ![[DNS 設定の編集] ダイアログボックスの [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  


