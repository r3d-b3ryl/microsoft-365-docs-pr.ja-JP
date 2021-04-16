---
title: ドメイン接続の使用
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: ドメイン接続が有効なレジストラーを使用して Microsoft 365 にドメインを追加する方法について説明します。
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860657"
---
# <a name="using-domain-connect"></a>ドメイン接続の使用

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。
  
[ドメイン接続 ](https://www.domainconnect.org/) が有効なレジストラーを使用すると、数分かかる 3 つの手順で Microsoft 365 にドメインを追加できます。 
  
ウィザードでは、ドメインを所有し、ドメインのレコードを自動的に設定するだけなので、Microsoft 365 や Teams などの他の Microsoft 365 サービスにメールが届きます。
  
> [!NOTE]
> セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365 と統合されたドメイン接続レジストラー

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)
    - [MadDog Web ホスティング](https://maddogwebhosting.com/domains/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>メールと Web サイトは何が起こりますか?

セットアップが完了すると、ドメインの MX レコードが Microsoft 365 をポイントして更新され、ドメインのすべてのメールが Microsoft 365 に送信されます。 ドメインでメールを受け取るすべてのユーザーに対して、ユーザーを追加し、Microsoft 365 でメールボックスを設定してください。
  
ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。 ドメイン接続のセットアップ手順は、Web サイトには影響を与えかねない。
