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
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050780"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR コードを使用して Outlook モバイル アプリにサインインする

> [!IMPORTANT]
> この Microsoft 365 機能はパブリック プレビュー中です。 パブリック プレビューでは、Microsoft 365 の機能に早期にアクセスできます。

Microsoft 365 管理者は、ユーザー名とパスワードを入力せずに、モバイル デバイスで Android 用 Outlook または iOS アプリにサインインできます。 QR コードをスキャンすることで、ユーザーは安全に認証し、Outlook Mobile にサインインできます。

Outlook on the web または他のデスクトップ Outlook アプリケーションでは、モバイル デバイスで Outlook を使用できるという通知がユーザーに表示される場合があります。 これらの通知は、管理者が Exchange Powershell を使用して管理できます。 ユーザーが SMS テキスト メッセージを送信してモバイル デバイスにアプリをダウンロードする場合は、自分のコンピューターに QR コードが表示されます。 QR コードをスキャンして、スマートフォンやタブレットで Outlook にログインできます。 この QR コードは、1 回だけ引き換えできる短い有効期限のトークンです。

> [!NOTE]
> 場合によっては、ユーザーが自分のコンピューターで再認証して QR コードを生成する必要があります。

## <a name="use-exchange-powershell"></a>Exchange PowerShell を使用する

このエクスペリエンスは既定で有効になっています。 この機能を無効にするには、次の手順に従います。

1. [Exchange PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。
2. PowerShell を使用すると、Outlook モバイル アプリについてユーザーに通知する通知を無効にできます。 これにより、QR コードのサインイン フローも表示されません。

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

関連項目

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)