---
title: 'Microsoft 365 クライアントアプリケーションのサポート: モダン認証'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 の先進認証をサポートするプラットフォーム、クライアント、および PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 290a151e127b05e984b9d262c3b429b561201545
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806668"
---
# <a name="microsoft-365-client-app-support-modern-authentication"></a>Microsoft 365 クライアントアプリケーションのサポート: モダン認証

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

モダン認証を使用すると、さまざまなプラットフォーム間で Office クライアントアプリの Active Directory 認証ライブラリ (ADAL) ベースのサインインが有効になります。 これにより、多要素認証 (MFA)、スマートカード、証明書ベースの認証などのサインイン機能が有効になります。

[多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication)と[証明書ベース認証](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started)の詳細について説明します。

## <a name="supported-clients--platforms"></a>サポートされているクライアント & プラットフォーム

最新バージョンのクライアントおよびプラットフォームは、先進認証をサポートしています。 Microsoft 365 でのプラットフォームサポートの詳細については、「 [microsoft 365 のシステム要件](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)」を参照してください。
<br>
<br>

| クライアント | Android | iOS | Mac| Windows 10 <br> モダンアプリ| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Access | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Azure 管理者 | N/A | N/A | N/A | N/A | N/A |
| 会社のポータル | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Cortana | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Delve | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Edge | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Excel | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Exchange Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| フォーム | N/A | N/A | N/A | N/A | N/A |
| Office 365 管理 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |  |
| Kaizala | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office Lens| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Office mobile | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office ポータル | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| OneNote | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Outlook | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Planner | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power アプリ | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Power Automate | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power BI | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| PowerPoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Project | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Publisher | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Skype for Business | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |
| Skype for Business 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| SharePoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| SharePoint Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| 付箋 | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Stream | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |
| やるべきこと | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | 計画 | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Workplace analysis | N/A | N/A | N/A | N/A | N/A |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)