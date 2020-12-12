---
title: easyDNS で Microsoft 用の DNS レコードを作成する
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを easyDNS for Microsoft でセットアップする方法について説明します。
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656821"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>easyDNS で Microsoft 用の DNS レコードを作成する

探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.yml) を確認してください。 
  
次のすべての DNS レコードをレジストラーの Web サイトに追加して、メールを Microsoft にルーティングし、Teams と Skype for Business のドメインを使用する必要があります。
  
注: 現在、SRV レコードは、すべての easyDNS サービス パッケージで利用できるではありません。 Skype for Business に必要な SRV レコードを追加するには、easyDNS を使用してより高いサービス レベルにアップグレードする必要がある場合があります。
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>TXT レコードを持つドメインを所有している

1. 資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。 
    
2. [すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。
    
3. **[TXT レコード] 見出しの** 下で、[編集] ボタン (ボタンのアイコン) を選択します。 
    
4. テキスト フィールドに次のレコードを入力します。
    
    |**Host**|**テキスト**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (管理センターの [ドメイン] ページで提供された値を使用します)  <br/> |
   
5. [次へ **] を選択します**。 
    
6. レコードが正しいか確認し、[確認] を選択 **します**。 
    
7. 数分待って続行すると、作成したレコードがインターネットに伝達され、Microsoft によって検出されます。
    
8. これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
    
9. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
10. **[ドメイン]** ページで、確認するドメインを選択します。 
    
11. [セットアップ **] ページで** 、[セットアップの開始] **を選択します。**
    
12. **[ドメインの確認]** ページで、**[確認]** を選択します。 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>MX レコードを追加して Microsoft にメールをルーティングする

1. 資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。 
    
2. [すべてのドメイン **] 見出しの** 下で **、[dns]** を選択します。
    
3. [MX **レコード] 見出しの** 下で、[編集] ボタン (歯車アイコン) を選択します。 
    
4. テキスト フィールドに次のレコードを入力します。
    
    |**領域のメール**|**メール サーバー**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>.mail.protection.outlook.com (管理センター \<domain-key\> の [ドメイン] ページから値を取得する)  <br/> |0  <br/> |
   
2. バックアップ目的で他の MX レコードを保存する場合は、どこかにコピーします。 次に進む前に、ここに他のすべての MX レコードを削除します。
    
5. [次へ **] を選択します**。 
    
6. レコードが正しいか確認し、[確認] を選択 **します**。 
    
## <a name="add-the-required-cname-records"></a>必要な CNAME レコードを追加する

1. 資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。 
    
2. [すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。
    
3. **[CNAME/エイリアス レコード] 見出しの** 下で、[編集] ボタン (ボタンのアイコン) を選択します。 
    
4. テキスト フィールドに次のレコードを入力します。


    |**ホスト**|**住所 (末尾に ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. [次へ **] を選択します**。 
    
6. レコードが正しいか確認し、[確認] を選択 **します**。 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

1. 資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。 
    
2. [すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。
    
3. **[TXT レコード] 見出しの** 下で、[編集] ボタン (ボタンのアイコン) を選択します。 
    
4. テキスト フィールドに次のレコードを入力します。
    
    |**Host**|**テキスト**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. [次へ **] を選択します**。 
    
6. レコードが正しいか確認し、[確認] を選択 **します**。 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft で必要な 2 つの SRV レコードを追加する

注: 現在、SRV レコードは easyDNS の Domain Plus サービス レベルでは使用できません。 SRV レコードを追加するには、easyDNS を使用してより高いサービス レベルにアップグレードする必要がある場合があります。 
  
1. 資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。 
    
2. [すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。
    
3. **[SRV レコード] 見出しの** 下で、[編集] ボタン (ボタンボタン) を選択します。 
    
4. テキスト フィールドに次のレコードを入力します。
    
    |**サービス**|**PROTO**|**ホスト**|**PRI**|**WGT**|**ポート**|**TARGET(末尾に ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> |1800  <br/> |
   
5. [次へ **] を選択します**。 
    
6. レコードが正しいか確認し、[確認] を選択 **します**。 
    

