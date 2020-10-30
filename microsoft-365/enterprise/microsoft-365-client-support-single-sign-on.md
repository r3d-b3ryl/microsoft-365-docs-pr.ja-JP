---
title: 'Microsoft 365 クライアントアプリのサポート: 単一 Sign-On'
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
description: この記事では、Microsoft 365 のシングルサインオンをサポートするプラットフォーム、クライアント、および PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806667"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Microsoft 365 クライアントアプリのサポート: 単一 Sign-On

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

シングルサインオン (SSO) を使用すると、ユーザーが Azure Active Directory のアプリケーションにサインオンするときに、セキュリティと利便性が向上します。 シングルサインオンを使用すると、ユーザーは1回サインインするだけで、オンプレミスの Active Directory ドメインサービス (AD DS)、ドメインに参加しているデバイス、サービス (SaaS) アプリケーションとしてのソフトウェア、web アプリケーションにアクセスできます。

[シングルサインオン](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)の詳細については、こちらを参照してください。

## <a name="supported-clients--platforms"></a>サポートされているクライアント & プラットフォーム

次のクライアントおよびプラットフォームの最新バージョンは、シングルサインオンをサポートしています。 Microsoft 365 でのプラットフォームサポートの詳細については、「 [microsoft 365 のシステム要件](https://products.office.com/office-system-requirements)」を参照してください。
<br>
<br>

| クライアント | Android | iOS | Mac| Windows 10 <br> モダンアプリ| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| 会社のポータル | N/A | ![サポート](../media/check-mark.png) | 計画 | ![サポート](../media/check-mark.png) | N/A |
| Cortana | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Delve | 計画 | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Edge | ![サポート](../media/check-mark.png) | 計画 | N/A | N/A | ![サポート](../media/check-mark.png) |
| Excel | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Kaizala | ![サポート](../media/check-mark.png) | 計画 | N/A | N/A | N/A |
| Office Lens| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office mobile | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office ポータル | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 | ![サポート](../media/check-mark.png) | 計画 |
| OneNote | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 |
| Outlook | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 | ![サポート](../media/check-mark.png) |
| Planner | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power アプリ | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | 計画 | N/A |
| Power Automate | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power BI | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | 計画 |
| PowerPoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Project | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Publisher | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Skype for Business | 計画 | 計画 | N/A | N/A | N/A |
| SharePoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| 付箋 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Stream | 計画 | 計画 | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 | N/A | 計画 |
| やるべきこと | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | N/A | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | 計画 |

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
