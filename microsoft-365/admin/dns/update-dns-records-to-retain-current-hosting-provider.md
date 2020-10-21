---
title: DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: カスタムドメインの DNS レコードを管理するように Microsoft を設定している場合は、Microsoft 外でホストされている既存のパブリック web サイトにトラフィックをルーティングする方法について説明します。
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645565"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する

 **DNS ホスティングプロバイダーでドメインの Microsoft レコードを管理する場合**は、このトピックの手順について心配する必要はありません。 Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。 
  
 Microsoft が**DNS レコードを管理している場合**、microsoft の外部でホストされている既存のパブリック web サイトにトラフィックをルーティングするには、ドメインを microsoft に追加した後、次の手順を実行します。 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで DNS レコードを更新する
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

2. [ **ドメイン** ] ページで、ドメインを選択し、[ **DNS レコード**] を選択します。

3. [ **DNS 設定**] で、[ **カスタムレコード**] を選択します。

4. [ **+ 新しいカスタム レコード** ] を選択し、次の項目を入力します。 
    
   - [ **DNS の種類** ] には、「 **A (アドレス)** 」と入力します。
    
   - [ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。
    
   - [ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。 
    
   これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。 
    
5. [**保存**] を選択します。 
    
さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。
  
1. [ **+ 新しいカスタム レコード** ] を選択し、次の項目を入力します。 
    
   - [ **DNS の種類** ] には、「 **CNAME (エイリアス)** 」と入力します。
    
   - [ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。
    
   - [ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。 
    
2. [**保存**] を選択します。 
    
最後に、次の操作を行います。
  
Microsoft を参照するように[、ドメインの NS レコードを更新](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)します。 
  
NS レコードが Microsoft を指すように更新されている場合、ドメインはすべて設定されています。 メールは Microsoft にルーティングされ、web サイトのアドレスへのトラフィックは引き続き現在の web サイトのホストに送られます。
 
