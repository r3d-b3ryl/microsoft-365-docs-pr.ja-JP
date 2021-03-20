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
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914968"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR コードを使用して Outlook モバイル アプリにサインインする

> [!IMPORTANT]
> この機能は、Microsoft 365 管理センターでターゲット リリースを有効にしている組織でのみ使用できます。 ターゲットリリースを有効にし、その動作の詳細については、「標準リリースオプションまたはターゲットリリースオプションを設定する」 [を参照してください](release-options-in-office-365.md)。 パブリック プレビューを通じて、今後数週間でさらに多くの組織に展開する予定です。 パブリック プレビューは、Microsoft 365 の機能への早期アクセスを提供します。

Microsoft 365 管理者は、ユーザー名とパスワードを入力することなく、モバイル デバイスで Outlook for Android または iOS アプリにサインインできます。 QR コードをスキャンすることで、ユーザーは安全に認証し、Outlook モバイルにサインインできます。

Outlook on the web または他のデスクトップ Outlook アプリケーションでは、ユーザーはモバイル デバイスで Outlook を使用できるという通知を表示する場合があります。 これらの通知は、管理者が Exchange Powershell を使用して管理できます。 ユーザーがモバイル デバイスでアプリをダウンロードする SMS テキスト メッセージを自分で送信する場合は、自分のコンピューターに QR コードが表示されます。 QR コードをスキャンして、自分の携帯電話またはタブレットで Outlook にログインできます。 この QR コードは、1 回だけ引き換え可能な短命トークンです。

> [!NOTE]
> 場合によっては、ユーザーが自分のコンピューターで再認証して QR コードを生成する必要があります。

## <a name="use-exchange-powershell"></a>Exchange PowerShell を使用する

この機能は既定でオンになっています。 この機能を無効にするには、以下の手順に従います。

1. [Exchange PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。
2. PowerShell を使用すると、Outlook モバイル アプリについてユーザーに通知する通知を無効にできます。 これにより、QR コードサインイン フローが表示されるのを防ぐものになります。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

関連項目

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)