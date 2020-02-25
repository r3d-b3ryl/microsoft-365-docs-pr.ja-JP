---
title: EasyDNS for Office 365 で DNS レコードを作成する
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: ドメインを確認し、電子メール、Skype for Business Online、および easyDNS for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255372"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>EasyDNS for Office 365 で DNS レコードを作成する

探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.md) を確認してください。 
  
メールを Office 365 にルーティングするには、レジストラーの web サイトで以下の DNS レコードをすべて追加する必要があります。また、Teams と Skype for Business のドメインを使用することもできます。
  
注: SRV レコードは、現在、すべての easyDNS サービスパッケージでは利用できません。 Office 365 Skype for Business に必要な SRV レコードを追加するには、easyDNS を使用して、より高いサービスレベルにアップグレードする必要がある場合があります。
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>TXT レコードを使用してドメインを所有していることを確認する

1. に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。 
    
2. [**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**
    
3. [ **TXT records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。 
    
4. 次のレコードをテキストフィールドに入力します。
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS: msXXXXXXXX (管理センターの [ドメイン] ページでユーザーに提供された値を使用します)  <br/> |
   
5. [**次へ**] を選択します。 
    
6. レコードが正しいことを確認してから、[**確認**] を選択してください。 
    
7. 数分待ってから続行すると、作成したレコードがインターネット経由で伝達され、Office 365 によって検出されるようになります。
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。
    
10. [**ドメイン**] ページで、確認するドメインを選択します。 
    
11. [**セットアップ**] ページで、[セットアップの開始] を選択し**ます。**
    
12. [**ドメインの確認**] ページで、[**確認**] を選択します。 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>Office 365 に電子メールをルーティングするための MX レコードを追加する

1. に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。 
    
2. [**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**
    
3. [ **MX records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。 
    
4. 次のレコードをテキストフィールドに入力します。
    
    |**ゾーン用のメール**|**メールサーバー**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<\>mail.protection.outlook.com ([管理センタードメイン] ページ\<からドメインキー\>の値を取得する)  <br/> |.0  <br/> |
   
2. バックアップのために他の MX レコードを保存する場合は、その MX レコードを任意の場所にコピーします。 に進む前に、ここで他のすべての MX レコードを削除します。
    
5. [**次へ**] を選択します。 
    
6. レコードが正しいことを確認してから、[**確認**] を選択してください。 
    
## <a name="add-the-required-cname-records"></a>必要な CNAME レコードを追加する

1. に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。 
    
2. [**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**
    
3. [ **CNAME/Alias records** ] の見出しで、編集ボタン (レンチアイコン) を選択します。 
    
4. 次のレコードをテキストフィールドに入力します。


    |**ホスト**|**Address (末尾に "." を指定する必要があります)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com。  <br/> |
    |sip  <br/> |sipdir.online.lync.com。  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> |
   
5. [**次へ**] を選択します。 
    
6. レコードが正しいことを確認してから、[**確認**] を選択してください。 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する

1. に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。 
    
2. [**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**
    
3. [ **TXT records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。 
    
4. 次のレコードをテキストフィールドに入力します。
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. [**次へ**] を選択します。 
    
6. レコードが正しいことを確認してから、[**確認**] を選択してください。 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 個の SRV レコードを追加する

注: SRV レコードは現在、easyDNS ' ドメインおよびサービスレベルでは使用できません。 SRV レコードを追加するには、easyDNS を使用して、より高いサービスレベルにアップグレードする必要がある場合があります。 
  
1. に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。 
    
2. [**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**
    
3. [ **SRV records** ] の見出しの下で、[編集] ボタン (レンチアイコン) を選択します。 
    
4. 次のレコードをテキストフィールドに入力します。
    
    |**サービス**|**MASK**|**ホスト**|**度**|**WGT**|**ポート**|**TARGET (末尾に "." を指定する必要があります)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com。  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> |1800  <br/> |
   
5. [**次へ**] を選択します。 
    
6. レコードが正しいことを確認してから、[**確認**] を選択してください。 
    

