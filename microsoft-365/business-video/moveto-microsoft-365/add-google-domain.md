---
title: Google Workspace ドメインを追加する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Google Workspace から Microsoft 365 for business にドメインを移動する方法について説明します。
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794751"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Google Workspace ドメインを Microsoft 365 に追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Google Workspace ドメインを Microsoft 365 for business に追加して、ビジネス メール アドレスを使用し続けできます。

## <a name="try-it"></a>演習

1. 
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. Microsoft 365 管理センターの左側のナビゲーションで、[すべて表示]、[設定]、次に [ドメイン] の順 **に選択します**。 
1. Choose **Add domain,** enter your domain name then select **Use this domain**. 
1. Choose, **Add a TXT record to the domains DNS records,** select **Continue,** and copy the TXT value. 
1. [Google](https://admin.google.com)管理コンソールに戻り、[ドメイン]、[ドメインの管理]、[詳細の表示]、[ドメインの管理 **]、DNS** の順に選択し、下にスクロールしてカスタム リソース レコードを **表示します**。  
1. Open the record type drop-down, choose **TXT,** paste the TXT value you copied then select **Add**. 

    通常、更新には数分かかりますが、最大 48 時間かかる場合があります。 
1. Microsoft 365 管理センターに戻り、[確認] を **選択し、[** 閉じる] を **選択します**。 
1. ドメインをユーザーのプライマリ メールとして設定するには、左側のナビゲーションで [**ユーザー** アクティブ ユーザー]  >  **を選択します**。 
1. Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**. 
1. ユーザーごとにこのプロセスを繰り返します。 

    完了したら、メール アプリをインストールし、Officeアイテムを Microsoft 365 に移行する準備が整います。 