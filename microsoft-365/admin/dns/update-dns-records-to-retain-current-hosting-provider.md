---
title: DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: カスタムドメインの DNS レコードを管理するように Office 365 を設定している場合、Office 365 の外部でホストされている既存のパブリック web サイトにトラフィックをルーティングする方法について説明します。
ms.openlocfilehash: de95818eea729cb11972faf986c9be40bb6e76da
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255356"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する

 **DNS ホスティング プロバイダーでドメインの Office 365 レコードを管理する場合は** 、このトピックの手順を考慮する必要はありません。Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。 
  
 **Office 365 が DNS レコードを管理する場合** 、Office 365 の外部でホストされている既存の一般向け Web サイトにトラフィックをルーティングするには、ドメインを Office 365 に追加した後で、次のように操作します。 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで DNS レコードを更新する
1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

2. [ **ドメイン** ] ページで、ドメインの一覧から、Web サイトで使用しているドメインを選択し、管理ウィンドウで [ **DNS 設定** ] を選択します。 
    
3. [**+ 新しいカスタム レコード**] を選択し、次を入力します。 
    
  - [ **DNS の種類** ] には、「 **A (アドレス)** 」と入力します。
    
  - [ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。
    
  - [ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。 
    
    これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。 
    
3. [**保存**] を選択します。 
    
さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。
  
1. [ **+ 新しいカスタム レコード** ] を選択し、次の項目を入力します。 
    
  - [ **DNS の種類** ] には、「 **CNAME (エイリアス)** 」と入力します。
    
  - [ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。
    
  - [ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。 
    
2. [**保存**] を選択します。 
    
最後に、次の操作を行います。
  
[TE102827792 を指すようにドメインの NS レコードを更新します](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx)。 
  
NS レコードが更新され、Office 365 を指すようになると、ドメインはすべてセットアップ済みです。メールは Office 365 にルーティングされ、Web サイト アドレスへのトラフィックは引き続き現在の Web サイト ホストに流れます。
 