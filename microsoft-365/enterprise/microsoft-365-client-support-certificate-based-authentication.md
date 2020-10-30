---
title: 'Microsoft 365 クライアントアプリケーションのサポート: 証明書ベースの認証'
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
description: この記事では、Microsoft 365 クライアントアプリによる証明書ベースの認証のサポートに関する詳細を確認します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 49ed1e329e83b73441c89de9a142bfb9dcac5395
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806696"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 クライアントアプリケーションのサポート: 証明書ベースの認証

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

証明書ベースの認証を使用すると、Windows、Android、または iOS デバイス上のクライアント証明書を使用して Azure Active Directory に認証できます。 この機能を構成すると、ユーザー名とパスワードの組み合わせを、モバイルデバイス上の特定のメールおよび Microsoft Office アプリケーションに入力する必要がなくなります。

[証明書ベースの認証](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)の詳細について説明します。

## <a name="supported-clients--platforms"></a>サポートされているクライアント & プラットフォーム

次のクライアントおよびプラットフォームの最新バージョンは、証明書ベースの認証をサポートしています。 Microsoft 365 でのプラットフォームサポートの詳細については、「 [microsoft 365 のシステム要件](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)」を参照してください。
<br>
<br>

| クライアント | Android | iOS | Mac| Windows 10 <br> モダンアプリ| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Access | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Azure 管理者 | N/A | N/A | N/A | N/A | N/A |
| 会社のポータル | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Cortana | 計画 | 計画 | N/A | ![サポート](../media/check-mark.png) | N/A |
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
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
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
| SharePoint Online 管理者 | 計画 | 計画 | N/A | N/A | N/A |
| 付箋 | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Stream | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | 計画 |
| やるべきこと | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | 計画 | 計画 | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Workplace analysis | N/A | N/A | N/A | N/A | N/A |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 | N/A | 計画 |

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

