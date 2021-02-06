---
title: QR コードを使用して Outlook モバイル アプリにサインインする
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
description: QR コードを使用して Outlook モバイルを認証およびダウンロードする方法について学習します。
ms.openlocfilehash: b9e433e0c7d3f5f3466924b318e242e5ac29181c
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122374"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR コードを使用して Outlook モバイル アプリにサインインする

> [!IMPORTANT]
> この Microsoft 365 機能はパブリック プレビュー中です。 パブリック プレビューでは、Microsoft 365 の機能に早期にアクセスできます。

Microsoft 365 管理者は、ユーザー名とパスワードを入力せずに、モバイル デバイスで Android 用 Outlook または iOS アプリにサインインできます。 QR コードをスキャンすることで、ユーザーは安全に認証し、Outlook Mobile にサインインできます。

Outlook on the web または他のデスクトップ Outlook アプリケーションでは、モバイル デバイスで Outlook を使用できるという通知がユーザーに表示される場合があります。 これらの通知は、管理者が Exchange Powershell を使用して管理できます。 ユーザーがモバイル デバイスにアプリをダウンロードするために SMS テキスト メッセージを送信する場合、自分のコンピューターに QR コードが表示されます。 QR コードをスキャンして、スマートフォンやタブレットで Outlook にログインできます。 この QR コードは、1 回だけ使用できる短い有効期限のトークンです。

> [!NOTE]
> 場合によっては、ユーザーが自分のコンピューターで再認証して QR コードを生成する必要があります。

## <a name="use-exchange-powershell"></a>Exchange PowerShell を使用する

このエクスペリエンスは既定で有効になっています。 この機能を無効にするには、次の手順に従います。

1. [Exchange PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。
2. PowerShell を使用すると、Outlook モバイル アプリについてユーザーに通知する通知を無効にできます。 これにより、QR コードのサインイン フローも表示されません。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

関連項目

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
