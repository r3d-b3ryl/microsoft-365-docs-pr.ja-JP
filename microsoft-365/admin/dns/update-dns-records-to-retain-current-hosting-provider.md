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
description: Microsoft がカスタム ドメインの DNS レコードを管理するように設定している場合に、Microsoft 社外でホストされている既存のパブリック Web サイトにトラフィックをルーティングする方法について説明します。
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572143"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する

 **DNS ホスティング プロバイダーでドメインの Microsoft レコードを管理する場合** は、このトピックの手順について心配する必要はありません。 Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。 
  
 **マイクロソフトが DNS レコードを管理している場合**、Microsoft 社外でホストされている既存のパブリック Web サイトにトラフィックをルーティングするために、ドメインを Microsoft に追加した後、次の操作を行います。 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Microsoft 365管理センターの DNS レコードを更新する
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

1. [ **ドメイン]** ページで、ドメインを選択し **、[DNS レコード**] を選択します。

1. **[ + レコードの追加 ]** を選択し、次の項目を入力します。 
    
   - **タイプの場合** は **、** 次のように入力します。
    
   - [ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。
    
   - [ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。 
    
   これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。 
    
1. [**保存**] を選択します。 
    
さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。
  
1. **[ + レコードの追加 ]** を選択し、次の項目を入力します。 
    
   - **タイプの場合** は、**次** のように入力します。
    
   - [ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。
    
   - [ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。 
    
2. [**保存**] を選択します。 
    
最後に、次の操作を行います。
  
[ドメインの NS レコードを更新](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) して、Microsoft を参照します。 
  
NS レコードが Microsoft を指す更新が行われた時点で、ドメインはすべてセットアップされます。 メールはマイクロソフトにルーティングされ、ウェブサイトのアドレスへのトラフィックは現在のウェブサイトのホストに引き続き送信されます。
