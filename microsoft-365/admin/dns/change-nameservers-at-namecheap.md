---
title: Namecheap を使用して Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'DNS レコードを管理する場合は、Namecheap を使用して Microsoft カスタムドメインをセットアップする方法について説明します。 '
ms.openlocfilehash: 6fdec37e837c74666ada82af81d43faaa0a6d589
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629781"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a>Namecheap を使用して Microsoft をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。
  
Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。 (必要に応じ[て、すべての MICROSOFT DNS レコードを Namecheap で管理](create-dns-records-at-namecheap.md)することができます)。
  
    
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. **ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. [**ドメインリスト**] ページで、編集するドメインの名前を見つけて、[**管理**] を選択します。
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. [ **ADVANCED DNS**] を選択します。
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. [**ホストレコード**] セクションで、[**新しいレコードの追加**] を選択します。
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. [ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。
    
    > [!NOTE]
    > [**新しいレコードの追加**] を選択すると、[**種類**] ドロップダウンが自動的に表示されます。
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
    (ドロップダウンリストから [ **TTL** ] の値を選びます。) 
    
|**Type**|**Host**|**Value**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **注**: これは例です。 この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |30 分  <br/> |
   
   ![Namecheap-BP-検証-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. [**変更の保存**] (チェックマーク) コントロールを選択します。 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。
  
Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>ドメインのネーム サーバー (NS) レコードを変更する

Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft プライマリネームサーバーとセカンダリネームサーバーをポイントするようにします。 これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。 メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。
  
> [!CAUTION]
> ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。 たとえば、ドメインに送信されるすべての電子メール (rob@ *your_domain*など) は、この変更を行った後に Microsoft に送られ始めます。 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. **ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. [**ドメインリスト**] ページで、編集するドメインの名前を見つけて、[**管理**] を選択します。
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. [**ドメイン**] を選択します。
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. [ **NAMESERVERS**] セクションを探し、[ **Namecheap Default**] ドロップダウン リストから [ **Custom**] を選びます。 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. 現在表示されているページに既にネームサーバーが表示されているかどうかに応じて、次の2つの手順のいずれかに進みます。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがない場合
<a name="BKMK_ProcedureWithOUT"> </a>

1. [ **ADD NAMESERVER** ] を2回選択して、2つの新しい行を追加します。
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. [ **Nameserver**] ボックスに、次の表の値を入力するか、コピーして貼り付けます。
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. [**保存**] (チェックマーク) コントロールを選択します。 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。 
  
### <a name="if-there-are-nameservers-already-listed"></a>既に一覧表示されているネームサーバーがある場合

> [!CAUTION]
> これらの手順は、前途した 4 件の *正しい*  ネームサーバー以外にも既存のネームサーバーがある場合に  *のみ*  行ってください (つまり、現在のネームサーバーのうち *ns1.bdm.microsoftonline.com* 、 *ns2.bdm.microsoftonline.com* 、 **ns3.bdm.microsoftonline.com** 、 **ns4.bdm.microsoftonline.com** のいずれでも  **ない**  もの  **だけ**  を削除します)。 
  
1. [ **Nameserver**] ボックスに他のネーム サーバーが表示されている場合は、各ネームサーバーを選び、キーボードの **Delete** キーを押して、ネーム サーバーを削除します。 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. [ **ADD NAMESERVER** ] を2回選択して、2つの新しい行を追加します。 
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. [ **Nameserver**] ボックスに、次の表の値を入力するか、コピーして貼り付けます。
 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. [**保存**] (チェックマーク) コントロールを選択します。 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。 その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。
