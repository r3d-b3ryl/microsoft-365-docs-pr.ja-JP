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
ms.localizationpriority: high
ms.collection:
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: QR コードを使用して Outlook Mobile を認証し、ダウンロードする方法について学習します。
ms.openlocfilehash: cd3467816649c0111cfa8c34d9c1d90dc8cfa8e7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176141"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR コードを使用して Outlook Mobile アプリにサインインする

Microsoft 365 管理者は、ユーザーがユーザー名とパスワードを入力しなくても、モバイル デバイスにおいてAndroid 版 Outlook または iOS 版 Outlook アプリにサインインできるようにすることができます。 QR コードをスキャンすることで、ユーザーはセキュリティで保護された認証を行い、Outlook モバイルにサインインできます。

Outlook on the web または他のデスクトップ Outlook アプリケーションでは、モバイル デバイスで Outlook を使用できる旨の通知がユーザーに表示される場合があります。 管理者は、これらの通知を Exchange PowerShell を使用して管理することができます。 ユーザーがモバイル デバイスにアプリをダウンロードするために、自分自身に SMS メッセージを送信する場合、QR コードが自分のコンピューターに表示されます。 QR コードをスキャンして、スマートフォンまたはタブレットで Outlook にログインできます。 この QR コードは有効期限の短いトークンで、1 回のみ使用できます。

通知は、次の条件が満たされた場合にのみ生成されます。

1. テナントに対して QR コード エクスペリエンスが有効になっていること (このエクスペリエンスは既定で有効になっています)。

2. ユーザーが、iOS および Android 用の Outlook をまだ使用していないこと。

3. ユーザーが閲覧ウィンドウで空の状態であること (最初のメールを自動的に開くオプションを選択しないでください)。

4. ユーザーが通知を却下しなかったこと。

> [!NOTE]
> 場合によっては、ユーザーは QR コードを生成するために、自分のコンピューターで再認証する必要があります。

## <a name="use-exchange-powershell"></a>Exchange PowerShell を使用する

この機能は既定で有効になっています。 この機能を無効にするには、次の手順に従います。

1. [リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)。
2. PowerShell を使用すると、Outlook モバイル アプリに関するユーザーへの通知を無効にできます。 これにより、QR コードのサインイン フローも表示されなくなります。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>関連コンテンツ

[標準または対象指定リリース オプションを設定する](release-options-in-office-365.md) (article)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (article)
