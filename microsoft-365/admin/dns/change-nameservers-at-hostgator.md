---
title: Hostgator で Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Hostgator でカスタム ドメインの DNS レコードを管理するために Microsoft をセットアップする方法について説明します。
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658022"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Hostgator で Microsoft 365 をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。
  
Microsoft が DNS レコードを管理する場合は、次の手順に従います。 (必要に応じて [、Hostgator ですべての Microsoft DNS レコードを管理できます](create-dns-records-at-hostgator.md)。
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>ドメインがホスティング アカウントを指すようにします。

> [!IMPORTANT]
> 次のセクション「 **確認のための TXT レコードを追加する** 」の手順の前に、この操作を実行する必要があります。
  
次の手順に従って、ドメインとホスティング アカウントの関連付けを行ってください。
  
1. まず、[このリンク](https://portal.hostgator.com/domain/manage)を使って Hostgator でカスタマー ポータル ページにアクセスします。ログインするように求められます。
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. [ドメイン **] タブを選択** します。
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. [ **ドメインの管理] ページ** の [マイ ドメイン **]** 領域で、更新するドメインを選択します。
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. [ドメイン **の概要] ページ** の [ネーム サーバー] **領域で、[** 変更] を選択 **します**。
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. ドメインの **[ネーム サーバー** ] ページの[ホスティング アカウントの選択] ドロップダウンリストで、ドメインに関連付けられているホスティング アカウントを選択します。
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. [Save **Name Servers] (ネーム サーバーの保存) を選択します**。
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

> [!IMPORTANT]
> この手順を実行する前に、この記事の最初のセクションの手順を実行する [必要](#point-your-domain-to-your-hosting-account)があります。
  
Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。
  
1. 開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。
    
    (Hostgator でホストされる各アカウントに一意の cPanel アドレスが割り当てられます。 cPanel アドレスは、以下のような形式になります。https://YourSiteAddress:secure-port-number。 Hostgator から届くサインアップ メールで、そのアドレスが指定されます。)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft. 
  
2. [コントロール **パネル] ページの**[ドメイン] 領域で **、[Advanced DNS Zone Editor] を選択します**。
    
    (下へスクロールしなければならないことがあります。) 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
|||||
|:-----|:-----|:-----|:-----|
|**名前** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
|Use your  *domain_name*  . (for example, fourthcoffee.com.)  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. [ **Add Record** ] を選択します。
    
5. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
ドメイン レジストラーのサイトでレコードを追加した後、Microsoft に戻り、レコードの検索を要求します。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Microsoft でドメインのセットアップを完了するには、ドメイン レジストラーでドメインの NS レコードを変更して、Microsoft のプライマリ ネーム サーバーとセカンダリ ネーム サーバーをポイントします。 これにより、ドメインの DNS レコードを更新する Microsoft がセットアップされます。 メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> Microsoft ネーム サーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。 たとえば、ドメインに送信されたメール (rob@ *your_domain*  .com など) は、この変更を行った後に Microsoft に届きます。
  
> [!IMPORTANT]
> 次の手順では、他の不要なネームサーバーを一覧から削除する方法と、正しいネームサーバーが一覧に表示されていない場合に追加する方法を示します。 このセクションの手順を完了すると、次の 4 つのネームサーバーだけが表示されます。 ns1.bdm.microsoftonline.com 、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、 **ns4.bdm.microsoftonline.com**。 
  
1. まず、[このリンク](https://portal.hostgator.com/domain/manage)を使って Hostgator でカスタマー ポータル ページにアクセスします。ログインするように求められます。
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. [ドメイン **] タブを選択** します。 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. [ **ドメインの管理] ページ** の [マイ ドメイン **]** 領域で、更新するドメインを選択します。 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. [ドメインの **概要] ページ** の [ネーム サーバー **]** 領域で、[変更] を選択 **します**。
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. ドメインの **[ネーム サーバー** ] ページの[ホスティング アカウントの選択] ドロップダウンリストで、ドメインに関連付けられているホスティング アカウントを選択します。 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Select **Manually set my name servers**.
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **注意**: 次の手順は、4 つの正しいネームサーバー以外の既存のネームサーバーがある場合にのみ実行してください。 (つまり、名前が **ns1.bdm.microsoftonline.com**、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com、または ns4.bdm.microsoftonline.com **))**  
  
        ドメインの [ **Name Servers**] ページにあるネームサーバーのリストで、各ネームサーバーを削除します。リストから選択してキーボードの **Delete** キーを押します。 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. ネームサーバーのリストに、次の表の最初の 2 つの値を入力するか、コピーして貼り付けます。
    
|||
|:-----|:-----|
|**Name Server 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. 他のネームサーバー値を追加します。
    
    Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record. 
    
    4 つの nameserver レコードの作成がすべて完了するまで、このプロセスを繰り返します。
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. [Save **Name Servers] (ネーム サーバーの保存) を選択します**。
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。
