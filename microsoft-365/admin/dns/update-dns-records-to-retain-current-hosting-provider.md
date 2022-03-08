---
title: DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: カスタム ドメインの DNS レコードを管理するために Microsoft を設定している場合は、Microsoft の外部でホストされている既存のパブリック Web サイトにトラフィックをルーティングする方法について説明します。
ms.openlocfilehash: 9bb12d4f73e8d95717ddd90492fb9cb97c73eec9
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314822"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する

 **DNS ホスティング プロバイダーで** ドメインの Microsoft レコードを管理する場合は、このトピックの手順について心配する必要はありません。 Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。 
  
 **Microsoft が DNS レコードを管理** している場合は、ドメインを Microsoft に追加した後、Microsoft の外部でホストされている既存のパブリック Web サイトにトラフィックをルーティングするには、次の手順を実行します。 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>サーバー内の DNS レコードを更新Microsoft 365 管理センター
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

1. [ドメイン **] ページで** 、ドメインを選択し、[DNS レコード] **を選択します**。

1. [ **+ レコードの追加] を選択** し、次の値を入力します。 
    
   - 型 **の** 場合は Enter: **A (Address)**
    
   - [ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。
    
   - [ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。 
    
   これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。 
    
1. [**保存**] を選択します。 
    
さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。
  
1. [ **+ レコードの追加] を選択** し、次の値を入力します。 
    
   - 型 **の** enter: **CNAME (Alias)**
    
   - [ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。
    
   - [ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。 
    
2. [**保存**] を選択します。 
    
最後に、次の操作を行います。
  
[Microsoft を指すドメインの NS](../setup/add-domain.md) レコードを更新します。 
  
NS レコードが Microsoft をポイントするために更新された場合、ドメインはすべてセットアップされます。 メールは Microsoft にルーティングされ、Web サイトアドレスへのトラフィックは引き続き現在の Web サイトのホストに送信されます。
