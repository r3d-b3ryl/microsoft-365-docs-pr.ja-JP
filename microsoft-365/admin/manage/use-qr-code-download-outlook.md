---
title: QR コードを使用して Outlook Mobile アプリにサインインする
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: QR コードを使用して Outlook Mobile を認証し、ダウンロードする方法について学習します。
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914968"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR コードを使用して Outlook Mobile アプリにサインインする

> [!IMPORTANT]
> この機能は、Microsoft 365 管理センターで対象指定リリースを有効にしている組織だけが使用できます。 対象指定リリースを有効にする方法と、その動作の詳細については、「[標準リリースまたはターゲット リリース オプションをセットアップする](release-options-in-office-365.md)」を参照してください。 パブリック プレビューを通じて、今後数週間でさらに多くの組織に展開される予定です。 パブリック プレビューでは、Microsoft 365 の機能に事前にアクセスすることができます。

Microsoft 365 管理者は、ユーザーがユーザー名とパスワードを入力しなくても、モバイル デバイスにおいてAndroid 版 Outlook または iOS 版 Outlook アプリにサインインできるようにすることができます。 QR コードをスキャンすることで、ユーザーはセキュリティで保護された認証を行い、Outlook モバイルにサインインできます。

Outlook on the web または他のデスクトップ Outlook アプリケーションでは、モバイル デバイスで Outlook を使用できる旨の通知がユーザーに表示される場合があります。 管理者は、これらの通知を Exchange PowerShell を使用して管理することができます。 ユーザーがモバイル デバイスにアプリをダウンロードするために、自分自身に SMS メッセージを送信する場合、QR コードが自分のコンピューターに表示されます。 QR コードをスキャンして、スマートフォンまたはタブレットで Outlook にログインできます。 この QR コードは有効期限の短いトークンで、1 回のみ使用できます。

> [!NOTE]
> 場合によっては、ユーザーは QR コードを生成するために、自分のコンピューターで再認証する必要があります。

## <a name="use-exchange-powershell"></a>Exchange PowerShell を使用する

この機能は既定で有効になっています。 この機能を無効にするには、次の手順に従います。

1. [リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。
2. PowerShell を使用すると、Outlook モバイル アプリに関するユーザーへの通知を無効にできます。 これにより、QR コードのサインイン フローも表示されません。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

関連トピック

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)