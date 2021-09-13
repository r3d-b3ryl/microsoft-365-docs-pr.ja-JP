---
title: ドメイン の使用Connect
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
description: ドメイン 管理者が有効なレジストラー Connectを使用して、ドメインをドメインに追加する方法Microsoft 365。
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176439"
---
# <a name="using-domain-connect"></a>ドメイン の使用Connect

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

[ドメイン接続](https://www.domainconnect.org/) 対応のレジストラを使用すると、3 ステップの手順を使って、数分でドメインを Microsoft 365 に追加できます。

ウィザードでは、ドメインを所有していることを確認してから、ドメインのレコードを自動的に設定するため、Microsoft 365 にメールが送信されます。Teams などの他の Microsoft 365 サービスはドメインを操作します。

> [!NOTE]
> セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365 と統合するドメイン接続レジストラ

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [Go Daddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)
  - [MadDog Web ホスティング](https://maddogwebhosting.com/domains/)
  - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>メールと Web サイトはどうなりますか?

セットアップを終了すると、ユーザーのドメインの MX レコードが Microsoft 365 を指定されるように更新され、そのドメイン宛てのすべてのメールが Microsoft 365 に送信されるようになります。 ユーザーのドメインにメールを持つすべてのユーザーが Microsoft 365 に追加され、メールボックスが設定されていることを確認してください。

ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。 ドメイン接続 のセットアップ手順は、自分の Web サイトには影響しません。
