---
title: ドメイン接続の使用
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: ドメイン接続が有効なレジストラーを使用して、ドメインを Microsoft 365 に追加する方法について説明します。
ms.openlocfilehash: 074ecc09323e09d3a668dd1c90f6034d8fce99eb
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210418"
---
# <a name="using-domain-connect"></a>ドメイン接続の使用

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。
  
[ドメイン接続](https://www.domainconnect.org/)が有効な登録機関は、数分かかる3つのステップのプロセスで、ドメインを Microsoft 365 に追加することができます。 
  
このウィザードでは、ドメインを所有していることを確認し、ドメインのレコードを自動的に設定することを確認します。そのため、Microsoft 365 およびその他の Microsoft 365 サービス (Teams など) が自分のドメインで作業します。
  
> [!NOTE]
> セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365 と統合するドメイン接続レジストラー

- [1&amp;IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy 販売店)
    - [MadDog ドメイン](https://www.maddogdomains.com/)
    - [不正名](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>電子メールと web サイトはどうなりますか?

セットアップが完了すると、ドメインの MX レコードが更新され、Microsoft 365 をポイントするようになり、ドメインのすべての電子メールが Microsoft 365 に送られ始めます。 ユーザーのドメインにメールを持つすべてのユーザーが Office 365 に追加され、メールボックスが設定されていることを確認してください。
  
ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。 ドメイン接続のセットアップ手順は、web サイトには影響しません。
