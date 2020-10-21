---
title: Bluehost を使用して Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Bluehost で DNS レコードを管理するために Microsoft をセットアップする方法について説明します。 '
ms.openlocfilehash: c15ba11e0df57deaef61309f5bc6d1b2a60645b8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646465"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a>Bluehost を使用して Microsoft をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。 (必要に応じ [て、すべての DNS レコードを Bluehost で管理](create-dns-records-at-bluehost.md)できます。)
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。 
    
    (下へスクロールしなければならないことがあります。) 
    
3. [ **Domain_name** ] 領域の **dns ゾーンエディタ** 行で、[ **dns レコードの管理**] を選択します。
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (ドロップダウン リストから [**Type**] の値を選びます。) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. [ **Add record**] を選択します。
    
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、プライマリおよびセカンダリのネームサーバーをポイントするようにします。 これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。 メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。 たとえば、ドメインに送信されるすべての電子メール (rob@ *your_domain*  など) は、この変更を行った後に Microsoft に送られ始めます。 
  
> [!IMPORTANT]
>  次の手順では、リストからその他の不要なネームサーバーを削除する方法と、正しいネームサーバーが表示されていない場合には追加する方法について説明します。 > このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [ **ドメイン** ] ページの [ **domain_name** ] 領域で、ドメインのチェックボックスをオンにして、[ **ネームサーバー**] を選択します。
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. [ **Domain_name** ] 領域で、[ **カスタムネームサーバーを使用する**] を選択します。
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. 現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。
    
  - 既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。
    
  - 既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがない場合

1. [ **Use Custom Nameservers**] セクションで、次の表の値を入力またはコピーして貼り付けます。 
    
|||
|:-----|:-----|
|**最初の空の行** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2 つ目の空の行** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. [ **行の追加**] を選択します。
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. さらに [ **カスタム ネームサーバーの使用**] セクションで、次の表の最初の行の値を、新しい空の行に入力またはコピーして貼り付けます。 
    
|||
|:-----|:-----|
|**3 つ目の空の行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4 つ目の空の行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
  
4. 4番目のネームサーバーレコードを追加するには、[ **行の追加** ] をもう一度選択し、上記の表の最後の行の値を使用してレコードを作成します。 
    
5. [ **ネームサーバー設定の保存**] を選択します。
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  
### <a name="if-there-are-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがある場合

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。 
  
1. 他のネーム サーバーが表示されている場合は、各ネーム サーバーを選び、キーボードの **Delete** キーを押して削除します。 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. さらに [ **Use Custom Nameservers**] セクションで、次の表の値を入力またはコピーして貼り付けます。 
    
|||
|:-----|:-----|
|**最初の空の行** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2 つ目の空の行** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. [ **行の追加**] を選択します。
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. さらに [ **カスタム ネームサーバーの使用**] セクションで、次の表の最初の行の値を、新しい空の行に入力またはコピーして貼り付けます。 
    
|||
|:-----|:-----|
|**3 つ目の空の行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4 つ目の空の行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. 4番目のネームサーバーレコードを追加するには、[ **行の追加** ] をもう一度選択し、上記の表の最後の行の値を使用してレコードを作成します。 
    
6. [ **ネームサーバー設定の保存**] を選択します。
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  
