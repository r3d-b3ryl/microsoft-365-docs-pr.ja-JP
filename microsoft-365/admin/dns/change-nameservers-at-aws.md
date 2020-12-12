---
title: Amazon Web Services (AWS) で Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Amazon Web Services (AWS) で DNS レコードを管理するために Microsoft をセットアップする方法について説明します。 '
ms.openlocfilehash: 4700557c40973ab051cced81c129197a826964ab
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658454"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>Amazon Web Services (AWS) で Microsoft をセットアップするためにネームサーバーを変更する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
Microsoft が DNS レコードを管理する場合は、次の手順に従います。 (必要に応じて [、AWS ですべての Microsoft DNS レコードを管理できます](create-dns-records-at-aws.md))。
  
    
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [リソース **] ページで** 、[ホストゾーン] **を選択します**。
    
3. [ **ホストゾーン] ページ** の [ **ドメイン** 名] 列で、編集するドメインの名前を選択します。 
    
4. [レコード **セットの作成] を選択します**。
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**名前** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
|(このフィールドは空のままにします)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simple <br/> |
   
6. **[作成]** を選択します。
    
7. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
ドメイン レジストラーのサイトでレコードを追加した後、Microsoft に戻り、レコードの検索を要求します。
  
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
> Microsoft ネーム サーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。 たとえば、ドメインに送信されたメール (rob@ *your_domain*  .com など) は、この変更を行った後に Microsoft に届きます。 
  
> [!IMPORTANT]
>  次の手順では、他の不要なネームサーバーを一覧から削除する方法と、正しいネームサーバーが一覧に表示されていない場合に追加する方法を示します。 >このセクションの手順を完了すると、次の 4 つのネームサーバーだけが表示されます。> ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [リソース **] ページで** 、[ホストゾーン] **を選択します**。
    
3. [ **ホストゾーン] ページ** の [ **ドメイン** 名] 列で、編集するドメインの名前を選択します。 
    
4. [ **Nameserver**] レコード セットを選びます。 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. [ **Value**] ボックスの [ **NS - Name server**] レコード セットで、すべてのネームサーバーを選んでキーボードの **Delete** キーを押して削除します。 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (つまり、名前が **ns1.bdm.microsoftonline.com**、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com、または ns4.bdm.microsoftonline.com **))**   
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. TTL **(秒):** 領域で **、1h (1** 時間) を選択します。 
    
    ![1 時間に 1H を選択する](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. [ **Value**] ボックスの [ **NS - Name server**] レコード セットで、次の表の **第 1 行** の値を入力するかコピーして貼り付けてからキーボードの **Enter** キーを押し、次の **行** の値を入力するかコピーして貼り付けます。 
    
    > [!IMPORTANT]
    > Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration. 
  
|||
|:-----|:-----|
|**第 1 行** <br/> |ns1.bdm.microsoftonline.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
|**第 2 行** <br/> |ns2.bdm.microsoftonline.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
|**第 3 行** <br/> |ns3.bdm.microsoftonline.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
|**第 4 行** <br/> |ns4.bdm.microsoftonline.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |
   
   ![[値] ボックスに最初の行の値を入力するか貼り付けます。](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. [レコード **セットの保存] を選択します**。
    
    ![[レコード セットの保存] を選択する](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。 
